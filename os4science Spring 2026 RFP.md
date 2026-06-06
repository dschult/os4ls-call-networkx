### NetworkX LOI Submission:
---
#### Title (54/60 chars)
**NetworkX for Big Data, Agentic Access and Algorithms**

Summary: (3000 chars)
---
##### Prompt
*Briefly describe the purpose of the proposal and the software project(s) it involves.*

##### Text (2970/3000 chars)
We propose three focus areas for NetworkX(NX) over the next two years.
1) Scalability: Improved interoperability with big data, e.g. cloud-native datasets, in-memory node/edge data with SciPy and Pandas, and no-code-change GPU dispatching.
2) AI-native: Provide agentic context via skills and example workflows with an emphasis on building pipelines relevant for life science applications.
3) Algorithms: improved algorithms for life sciences: centrality, community detection, isomorphism and drawing.

Two bottlenecks of NX interoperability are data conversion and streaming data. Each network analysis library stores data differently, and network biologists often use multiple libraries. Even within NX our linear algebra tooling requires conversion to SciPy sparse arrays, our GPU backend converts to on-chip memory. We aim to reduce conversions by providing direct access to core data structures and by building a caching system to reduce conversions by backends. We will also implement established streaming formats and create a new flexible streaming format to mesh with cloud-native datasets. In the other direction, we will add a new sparse format to SciPy sparse arrays that uses the NX data structure, so SciPy's csgraph tools will have direct access to NX graphs.

Scalability is also impacted by two new promising Python language features: free-threading and read-only dicts. These could have major impact on our scalability issues. We will take advantage of the native acceleration from free-threading and native read-only dicts are ideal for NX's subgraph system.

Agentic tools require domain context to facilitate creating complex workflows. Our docs are often praised, but we don't have many examples of life science workflows. Agentic tools also read tests to learn library context. AI tool effectiveness will improve via adding agent skills in whatever form they evolve to, adding integration tests across entire workflows and documenting these life science pipelines explicitly. Our nx-guides allow deep dives via jupyter notebooks that provide both humans and agentic tools context and building blocks that can be combined into complex workflows.

Our algorithm updates will focus on NX subpackages for Centrality Measures(CM) and Drawing Tools(DT) and we intend to continue updating the popular Community Detection(CD) and Subgraph Isomorphism(SI) tools. CM shows the relative importance of nodes to the network structure. This can find crucial molecules in reaction networks, regions in drug-design, super-spreaders in epidemics. We know of new algorithms and improvements in existing algorithms. DT provides visual cues that help researchers gauge progress and look for new relationships. We plan to implement our new Matplotlib Drawing suite and remove technical debt in our connections to GraphViz and iplotx. Our current funding has improved CM and SI considerably, but there are new approaches in each we want to implement to stay relevant.

####### Expected Value (1500 chars)
---
##### Prompt
*If the proposal is successfully funded, what does success look like?*
*We're seeking to understand:*
- what type of capabilities the proposal is unlocking for the scientific community;
- how upstream and downstream software will be improved by the proposal;
- how the proposed work supports or implements novel functionality that enables AI
  and large-scale data analysis.

##### Text (1497/1500 chars)
NX will be more performant at scale, more accessible for AI and have improved/updated algorithms/apis.

Computational biologists will in some cases avoid data conversion and duplicate storage of large datasets, and reduce conversion bottlenecks in others, especially for workflows crossing libraries. It will be easier to move network data across JSON streams. Libraries using SciPy sparse arrays for network storage will access NX data structures directly. Workflows and pipelines which use (pandas/polars) DataFrames to store node or edge data will no longer copy that data to do network analysis. Caching will help most other libraries working with NX including our backends.

New agentic friendly nx-guides, tests and reference doc improvements, along with agentic skills and more network biology examples throughout will help associate context with methods, extract examples with desired tasks, and provide building blocks that enable building complex workflows to address frontier level questions. We will create an in-depth nx-guide on genomics and one on spatial biology and a set of nx-guides working through course material and data from Cal Tech and Colgate Univ Computational Biology courses. Improved context, direction and easier workflow extraction will help both humans and AI-agentic tools.

Focused algorithm efforts will provide an updated CM suite with improved and new algorithms in a unified api. There will be new algorithms for CD and SI and new a matplotlib drawing api.

#### Landscape Analysis (1500 chars)
---
##### Prompt
We are looking for proposals from software projects with demonstrated traction
and adoption. Briefly describe other software tools that the audience for this
proposal primarily uses (including proprietary alternatives, if they exist),
and how the software project(s) in your proposal compare in terms of user base,
adoption, functionality, and maturity relative to their target audience. You
can add indicators of adoption and usage as needed. Please indicate if the
software is used in AI applications and workflows.

##### Text (1452/1500 chars)
Competing non-Python packages (some of which have Python interfaces) include rustworkx, cuGraph, Cytoscape, Gephi, Boost and igraph. Each of these tools are mature and established, with sizable user populations. Multiple tools are often used by the same scientist with data exchanged by file transfer. Some tools like NVIDIA's CuGraph and Scipy's csgraph allow non-file (in-memory) exchange with NetworkX. NetworkX's API is a de facto, unstructured standard for interacting with graph data. Many libraries adopt NX-like patterns in the design of their own APIs, for example CuGraph and rustworkx. In practice, NX is the fundamental package for network analysis in Python, and when describing the scientific python ecosystem is frequently listed with scikit-learn, statsmodels, and scikit-image in the layer above SciPy, Pandas, and Matplotlib. NX has millions of monthly downloads, hundreds of citations per year, and hundreds of contributors over the years. We don't have direct data on AI usage of NetworkX, but anecdotal evidence shows AI preference for using NX with network analysis. Nearly 440,000 GitHub repositories include NX as a dependency including over 11,500 packages. These include scikit-image, Pythran, ScanPy, SPARQL, micro-SAM, aioway, Proteinix, asf_search, QBioCode, and hypernetX. A Google scholar search for "AI life sciences NetworkX" shows 963 papers in 2026 so far discussing both AI usage and NetworkX for the life sciences.

#### Projects Supported (urls)
NetworkX
SciPy

#### Categories: (3 tags)
---
##### Prompt

Please check up to three tags describing the type of software and its target scientific audience.

**Software type:**
- [ ] Data formats and storage
- [ ] Knowledge representation and ontologies
- [X] Scientific computing
- [ ] Statistical modeling
- [ ] Workflows and computational pipelines
- [ ] Data visualization
- [X] Interoperability
- [ ] Software ecosystem infrastructure
- [X] Hardware acceleration and scalability
- [ ] Machine learning frameworks
- [ ] Agentic frameworks
- [ ] Benchmarking and evaluation tools

**Scientific domain:**
- [ ] Genomics and transcriptomics
- [ ] Structural and molecular biology
- [ ] Cell and developmental biology
- [ ] Evolutionary biology
- [ ] Immunology
- [ ] Biological and biomedical imaging
- [ ] Bioinformatics and computational biology
- [ ] Synthetic biology
- [ ] Spatial biology
- [ ] Neuroscience
- [ ] Infectious disease and epidemiology
- [ ] Computational drug discovery
- [ ] Other



