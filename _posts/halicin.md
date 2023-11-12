\section{Technical background, research approach, and results of the paper}

\subsection{Motivation}
\citet{stokes_2020_a}, hereon referred to as "the authors", address the global health concern of the proliferation of antibiotic-resistant bacteria by leveraging artificial intelligence (AI) for large-scale, high-throughput drug screening. 

% However, the Achilles's heel of medicine is that bacteria, and cells in general, mutate and adapt to a precarious environment \cite{swings_2017_adaptive}. These can then pass antibiotic-resistant determinants that render existing antibiotics powerless to fight infections. Traditional means of screening can not scale beyond millions of compounds \citep{liu_2023_deep}, a tiny fraction of the estimated search space in the order of $10^{60}$\citep{wang_2023_scientific}. 

Antibiotics are amongst the essential tools to fight against microbial infections. However, the Achilles's heel of medicine is that existing antibiotics can pressure bacteria to adapt to them through mutation and passing antibiotic-resistant determinants, rendering them useless. Thus, re-purposing and discovering new drugs to mitigate the proliferation of them are urgent to prevent deaths associated to antibiotic-resistant infections \citep{stokes_2020_a}.

There is a vast chemical space (in the order of $10^{60}$ compounds) to explore for possible candidates \cite{pavel_2022_the}. Nonetheless, most of this search space consist of non-usable biochemicals which can not be anticipated beforehand, thus would render its exploration and testing a waste of resources. Traditional means of screening can not scale beyond millions of compounds, and may suffer from the de-replication problem: same compounds are repeatedly discovered. A tangential problem is to find compounds structurally similar to existing ones, which could be deleterious in the long-term because bacteria that developed resistance to a drug may well be resistant to analogues\cite{liu_2023_deep}. An alternative that can bypass this flaw resorts to \textit{in silico} methods, i.e., computer simulations, in particular deep-learning to exploit its feature-extraction capabilities to model complex relationships \citep{jimnezluna_2020_drug}. \textit{In silico} methods vectorize molecules to obtain a representation that can be processed by a machine, and can conveniently scale. These features can be handcrafted based on domain-expertise, denoted as "molecular fingerprints", and they can be obtained from Dragon descriptors, Morgan fingerprints or using the open-source package RDKit \citep{yang_2019_analyzing}. However, domain-knowledge is often disputable, and experts may disagree on what are the putative features of a molecule. Another approach is to have a graph representation of a molecule whereby its hidden state is learnt via a deep graph convolutional neural network in a downstream, prediction task. The strength of a graph representation includes retaining the geometrical information (e.g spatial atom-atom bonding) of the molecule that could be relevant to determine its function. 


\subsection{Model architecture and dataset}
The authors adopt a hybrid architecture, called Chemprop\footnote{Code available at: \url{https://github.com/chemprop/chemprop/tree/master}}, that leverages both molecular fingerprints and learn a hidden representation for each molecule, combining the strengths of both worlds: the incorporation of expert knowledge, and flexibility of learning task-dependent, global hidden representations. It is a Directed Message-Passing Neural Network (DMPNN), a variant of the Message-Passing Neural Network, where message passing is asymmetrical, and is done among bonds instead of atoms in order to avoid redundant messages\citep{yang_2019_analyzing}. 
The authors frame drug discovery as a binary function classification task given a molecule, and validate their model's findings through rigorous wet-lab testing (see Figure \ref{fig:pipeline}). 

\begin{figure}
\centering{\includegraphics[width=\textwidth]{pipeline.png}}
\caption{\text{a)} A depiction of the DMPNN representing a molecule. Each vertex is an atom, and each edge is a bond. Messages of hidden states are passed along edges (e.g. the yellow and read arrows at the top). \text{b)} denotes the training and validation phase of the DMPNN, making predictions for $10^8$ molecules. \text{c) and d)} describe the screening of such molecules based on prediction scores, structural similarity and toxicity to filter the most promising candidates, along with experimental validation in the wet lab. Figure edited and extracted from \citep{stokes_2020_a}} \label{fig:pipeline}
\end{figure}

First, they train the DMPNN in a supervised setting to identify molecules that can inhibit the growth of _Escherichia coli_. They collect a dataset $\mathcal{D} = \{\textbf{X}, \textbf{y}\}$ consisting of $|\textbf{X}| = 2335$ unique molecules, each annotated with $y \in \{0, 1\}$ using $80\%$ growth inhibition as a cut-off. This results in an imbalanced dataset with only 120 molecules with growth inhibitory activity. It is split according to a ratio of 80%/20%/20% into training/validation/testing sets. 

A molecule is a group of atoms held by bonds. Each is represented as a directed graph $G=(V, E)$, where each $v \in V$ is an atom, and each $e_{vw} \in E$ is an edge between vertices $v, w$ representing a bond, where $e_{vw} \neq e_{wv}$. Both atom and bond have molecular fingerprints, as well as associated hidden representations $h_v, h_{vw}$ that are obtained via learnable matrices $\textbf{W}=\{W_i, W_m, W_a\}$[^1]. The goal of Chemprop, as described by \citet{yang_2019_analyzing}, is to learn the optimal hidden representations that can be used to predict a functional property of the molecule, which in this work is growth inhibition of \textit{E. coli}. A forward computation and training iteration of the network for a single molecule (Figure \ref{fig:pipeline}a) is described as follows: 

% works as follows :

\begin{enumerate}
\item Hidden state features for each bond are initialized at timestep $t = 0$:

$
h_{vw}^0 = \tau(W_i \text{cat}(v, e_{vw})
$, where $v$ is the RDKit feature for the atom, and $e_{vw}$ is the RDKit feature for a bond. $W_i \in \mathbb {R}^{h\times h_i} $ is a learnable matrix of parameters associated to the hidden state of some edge $e_i$, \text{cat($\cdot$)} is a function that concatenates the atom and bond features, and $\tau$ is the ReLU activation function. 
\item Messages between bonds $m_{vw}^t$ and hidden states $h_{vw}^t$ are passed and updated, respectively, given simple heuristics:

$
m_{vw}^{t+1} = \sum\limits_{\substack{k\in{N(v) \setminus w}}} h_{kv}^t
$, where the message is an aggregation of hidden representations, and $N(v)$ are the neighbors of atom $v$. 

$
h_{vw}^{t+1} = \tau(h^0_{vw} + W_mm^{t+1}_{vw})
$, where $W_m \in \mathbb {R}^{h\times h} $ is a learnable matrix.  
\item Such message passing occurs for $t \in {1,...,T }$ through the whole graph, followed by a final message $m_v$ that returns the hidden representation $h_v$ for an atom $v$ of the molecule by summing the bond features as per:

$
m_{v} = \sum\limits_{\substack{k\in{N(v)}}} h_{kv}^T \\
h_{v} = \tau(W_a\text{cat}(v, m_v))
$, where $W_a \in \mathbb {R}^{h\times h} $ is a learnable matrix. 

\item The hidden representations for all atoms are obtained and aggregated to $h$. 
$
h = \sum\limits_{\substack{v\in{V}}} h_v 
$

\item The output $\hat y$ of the D-MPNN is then computed as a function of $h$. In order to ensure generalization, this prediction is made by also incorporating 200 global features $h_f$ obtained via RDKit:

$
\hat y = f(\text{cat}(h, h_f))
$, where $f(\cdot)$ is a feed-forward neural network. 

\item A loss function, in this case the binary cross-entropy, is computed based on the predicted output $\hat{y}$ and the ground truth value $y$, where $y \in \textbf{y}$. Then, its gradient is backpropagated to learn the optimal parameters $W_i, W_m, W_a$. 

\end{enumerate}

\subsection{Results}

The authors' final prediction is an average of an ensemble of 20 classifiers trained with different parameter initializations. Hyperaparameters are estimated using Bayesian optimization. Despite the class skewness, the model achieves a high test accuracy measured by the ROC-AUC of 89.6\%, evidencing its robustness. This is further reassuring given how their model is the highest performing in ablation studies examining different molecular fingerprints and architectures. 

Then, the authors use the DMPNN to screen more than 6000 molecules from the Drug Repurposing Hub (Figure \ref{fig:pipeline}cd). The most promising candidate according to prediction score, structural dissimilarity to known antibiotics, and predicted toxicity is named as halicin. They further validate it with multiple assays on a range of bacteria, as well as through rat animal models, observing long-term, broad-spectrum antibacterial activity \cite{marchant_2020_powerful}. 
 
\section{Critical analysis: limitations and future research directions}
\subsection{Efficient high-throughput screening}
The authors successfully leverage geometric deep learning as spatial-aware, pattern extractors in order to tackle an extremely challenging problem of drug repurposing, given the highly heterogeneous behavior of a drug's biochemicals and the sheer scale of their search space. They successfully overcome the bottleneck of traditional means as evidenced by how they then screened more than 107 million molecular structures from the ZINC15 database in a matter of 4 days, thus greatly reducing the cost of filtering potential candidates through conventional means. This has several real-world applications such as aiding biochemical labs in highly-efficient, fast screening of drugs to fight disease.
%thus greatly expanding the capabilities of drug screening and reducing associated costs. 
% From thousands of high-scoring candidates, they shortlist 23 based on , 
% Leveraging DMPNN to assess hundreds of millions to billions of molecules in a matter of days is an exponential improvement over traditional screening programs limited to testing a few million molecules (Liu, Gary (2023) . This includes finding it is structurally-divergent to existing antibiotics, and thus would not be subject to the long-term worry of antibiotic-resistant determinants, as well as low toxicity according to animal models, coupled with broad-spectrum antiobiotic efficacy. 
Furthermore, extensive in-silico and wet-lab testing ensure the potential and safety of the predicted halicin. In addition to the above characteristics such as being structurally divergent, halicin has also been touted for its unconventional mechanism of action. It disrupts the flow of protons across the cell membrane, instead of more traditional approaches like blocking enzymes involved in protein synthesis \cite{marchant_2020_powerful}. This is an unanticipated gain that could arguably be only predicted by a deep learning system that can extract patterns beyond human comprehension from the training data. 

% The authors also rigorously tested its safety and efficacy through laborious wet-lab experiments, showing its broad-spectrum antibiotic efficacy. 

\subsection{Black-box architecture}
Despite these strengths, their model has a major flaw: its predictions remain elusive to interpretation by the biomedical personnel. This is concerning, given that the authors can not guarantee that their model is not learning spurious correlations \cite{jimnezluna_2020_drug} from the training data, e.g., maybe halicin was a top candidate because an irrelevant bond frequent in training was observed. Furthermore, the model's parameters can not explain how physico-chemical properties of halicin correlate to its functional properties. 
% Furthermore, sometimes, chemists would be willing to sacrifice prediction accuracy in favour of explainable models that correlate biological effects with physicochemical properties (Luna, 2020).

One powerful approach to mitigate this is semi-supervision: to employ generative pretraining over molecular databases\footnote{There are many datasets of molecules, such as those benchmarked in \cite{yang_2019_analyzing}} so that the model can learn a-priori a global latent representation of what are molecules. This graph autoencoder can then be finetuned to a downstream task of function classification, borrowing its internal representation to guide learning. Ad-hoc processing of such task-dependent latent representation, using techniques such as principal component analysis as in \citep{soelistyo_2022_learning, soelistyo_2023_virtual}, coupled with SHAP value methods that explore correlations between the input space and hidden activations of the model can yield mechanistic insight into \textit{why} it predicts certain compound. For example, maybe the presence of certain subgraph of atoms is biologically essential to inhibit bacterial growth. The latent representation could also help cluster drugs with similar properties, enabling the model to make predictions beyond a binary label. For more explainable methods please see \citet{jimnezluna_2020_drug}. 
%  \footnote{Such approach would be more expressive as one can use the latent representation to cluster drugs with similar properties, instead of specifically identifying a single function like growth inhibition of \textit{E. coli}}
Such pretraining could also yield additional benefits such as robustness to the the original dataset's small size and heavy skewness towards samples with no inhibition activity. This is important since despite achieving high test accuracy on the original dataset, the authors later report only $51.5\%$ when evaluated on the Drug Repurposing Hub.
% . that 
% this would also help identify molecules which have inhibitory effect against harmful bacteria whilst avoiding those that synergize with the human body. For example, it is well-known 
% it can also help save resources in validating the safety of molecules and making explainable predictions beyond a single label of whether it has an inhibitory property. This is
% .could thus improve explainability (Luna, Jose (2020)).  T, which could have also  Furthermore, while the authors did extensive wet-lab validation of the drug halicin, some work could have been simplified had they observed what are the "atoms" or "bond" characteristic the model is attending to that could yield some mechanistic insight into \textit{why} the model predicted halicin.  
%  and explainability.  Additional benefits could span over the
% The model would have the advantage of learning a latent representation of what molecules are that could improve performance. 
% Furthermore, it would have been useful to screen a few more candidates other than invest resources to validate one. 
% \begin{itemize}
%     \item focus on interpretability 
% \end{itemize}
% such as where the molecule is supposed to act, or how neighboring molecules could influence its mechanism of action. Furthermore,
\subsection{Multimodal integration for contextualized predictions}
% \begin{itemize}
%     \item focus on multimodal integration
% \end{itemize}
% In addition to addressing the above black-box limitations as potential future work, 
Even if the black-box nature of deep learning is mitigated, it is noted that authors' adopted approach can only make context-agnostic predictions of a molecule's ability to inhibit \textit{E. coli}'s growth. For example, halicin may not universally inhibit its growth, such as when it lives in the human gut system repleted with other microorganisms. An exciting line of research is to integrate multiple modalities of data in order to make contextualized predictions of a molecule's functional property. This is a great opportunity for chemoinformatics given the need to unify the deeply fragmented public biochemical databases available, spanning datasets over drug-repositioning, drug-target prediction, drug-drug interaction datasets \cite{pavel_2022_the}, as well as a drug's side effects \cite{li_2022_graph}. 

Such effort to train models for contextualized predictions synergize well with the demands of transparency because a prediction would then be beyond a single probability value of a label. It would also depend on the aforementioned factors with potential benefits such as identifying molecules that selectively target harmful strains of \textit{E. coli}. This is important because it is well known that most strains of \textit{E. coli} are harmless and aid the digestive system of humans \cite{worldhealthorganization_2018_e}, while others can cause food poisoning. 
Therefore, halicin may not be a good candidate if it indiscriminately kills \textit{E. coli}. 

It is clear that a lot of work is yet to be done on building transparent models for drug repurposing beyond highly performing black-boxes.
% The adoption Future research directions include augmenting the model's prediction capabilities, not restricting it to predict    First,  There needs to be more effort in multimodal data integration in order to 
%  such as a molecule's environment, molecule-molecule interactions derived from biomedical knowledge graphs, and clinical relevant data (such as a molecule's known side effects when interacting with another)  could also augment the expressivity of the classifier.
The materialization of explainable models that can provide contextualized outputs can revolutionalize biomedical research, as they earn the trust of researchers whilst being highly performing. They can be deployed into real-world settings like clinical labs to aid rapid and efficient scientific discovery of drugs to tackle diverse global health concerns. In addition to fighting antibiotic resistance, applications can include repurposing existing drugs to fight viral variants, or mitigate neurological diseases like Alzheimer's or Parkinson's. 

[^1]: this is analogous to word embeddings that can be obtained via GLoVE and word2vec, where their hidden representations are learnt in a recurrent neural network's layers of abstraction. 