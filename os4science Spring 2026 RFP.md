### NetworkX LOI Submission:
---
#### Title (54/60 chars)
**NetworkX for Big Data, Agentic Access and Algorithms**

Summary: (3000 chars)
---
##### Prompt
*Briefly describe the purpose of the proposal and the software project(s) it involves.*

##### Text (3541/3000 chars)
#Previous funding for NetworkX(NX) has lead to a robust developer community, a system of nx-guides for documentation, a dispatching system allowing no-code-change switch of hardware from CPUs to GPUs, and updated algorithms for Subgraph Isomorphism and Community Detection.
#
#We use the term network here, but graph theory uses graph to mean the same thing.

We propose three focus areas for NetworkX(NX) over the next two years.
1) Big Data interoperability with data analysis libraries and bio-related dataset formats.
2) nx-guides and workflow examples aimed at providing AI agentic context for
   building bio-related workflows and pipelines.
3) Centrality and Visualization algorithms, API and test unification.

A consistent bottleneck to interoperability of network analysis software is data conversion. Cytoscape, Gephi, iGraph and NX store network information differently and biological network analysis scientists typically use at least two of these tools. Even within NX our no-code-change dispatching to GPU requires costly conversion. And our linear algebra tooling requires conversion to SciPy sparse arrays. We aim to limit conversions by providing direct access to the data structure, and adding caching so that repeated conversions are not needed. We will also explore new Python features that could change how NX deals with big data: free-threading and read-only dicts. We have many naively parallelizable algorithms for which free-threading should perform well. And our data structures are nested dicts, often in a read-only setting after initial construction.

Agentic tools require domain context to facilitate creating complex workflows. Our docs are often praised, but we don't have many examples of life science workflows. Agentic tools also read tests to learn context about how a library works. We propose to overhaul our docs, tests, and tutorial guides (nx-guides) with an eye toward improving AI tool effectiveness, and to improve, enhance and modernize our bio-related documentation. In addition, we will create tooling for agentic directions and recipes. We envision these as "skills" files, but we'll use what the AI world evolves toward between now and the work of the grant.

It is important that we continue to upgrade our subpackages with the latest algorithms and unify our API within subpackages of functions. Based on informal discussions with computational biologists using our tools, we intend to focus on the NX Centrality Measures (CM) and Drawing Tools (DT) subpackages during this grant period.

CM shows the relative importance of nodes to the network structure. This is used to find crucial molecules in reaction networks, super-spreaders in disease transmission, and critical regions in drug design. We have many centrality measures. But their interfaces differ and we don't compare the results in our docs. We will build tests, docs, and nx-guides which compare results across the different measures. We will also add two new centrality algorithms and update using recently published improvements in existing algorithms.

Drawing is a popular feature even though NX does not focus on graphics. We provide basic Matplotlib drawing tools because visual cues help researchers gauge progress and look for new relationships. We provide close connections to the specialized drawing tool GraphViz and the interlibrary graphics tool iplotx. Recent funding allowed API development for our new Matplotlib drawing suite. We will implement this API and refactor existing functions to use this new API.

####### Expected Value (1500 chars)
---
##### Prompt
*If the proposal is successfully funded, what does success look like?*
*We're seeking to understand:*
- what type of capabilities the proposal is unlocking for the scientific community;
- how upstream and downstream software will be improved by the proposal;
- how the proposed work supports or implements novel functionality that enables AI
  and large-scale data analysis.

##### Text (1785/1500 chars)
Our computational biology users and their AI tools will spend less time converting data between libraries and avoid duplicate storage of large datasets. They will reduce conversion bottlenecks for workflows crossing tools. It will be easier to move network data across JSON streams as well as via file transfer. Libraries using SciPy sparse arrays for their storage will be able to access NX data structures directly. Workflows and pipelines which use (pandas/polars) DataFrames to store node or edge data will no longer need to copy that data to do network analysis. We will also build a caching system to store conversions to avoid repeats. Caching will help most libraries working with NX (including our backends) even if they don't use Scipy or DataFrames.

New agentic friendly nx-guides, tests and reference doc improvements, along with agentic directive files and more bio-related examples throughout will help associate context with methods, extract examples with desired tasks, and compose building block workflows into complex pipelines that address frontier level questions. We will create an in-depth nx-guide on genomics and one on spatial biology and a set of nx-guides working through course material and data from Cal Tech and Colgate Univ Computational Biology courses. These in depth guides will be supported by new life science examples in the reference docs and tests. Improved context, direction and easier workflow extraction will help both humans and AI-agentic tools.

Focused algorithm efforts will provide an updated CM suite with improved as well as new algorithms and with unified testing and api design. A new matplotlib drawing api as well as better connections to network graphics packages will help our users visualize results quickly and effectively.

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

##### Text (1459/1500 chars)
Competing non-Python packages (some of which have Python interfaces) include rustworkx, cuGraph, Cytoscape, Gephi, Boost and igraph. Each of these tools are mature and established, with sizable user populations. Multiple tools are often used by the same scientist with data exchanged by file transfer. Some tools like NVIDIA's CuGraph and Scipy's csgraph allow non-file (in-memory) exchange with NetworkX. NetworkX's API is a defacto, unstructured standard for interacting with graph data. Many libraries adopt NX-like patterns in the design of their own APIs, for example CuGraph and rustworkx. In practice, NX is the fundamental package for network analysis in Python, and when describing the scientific python ecosystem is frequently listed with scikit-learn, statsmodels, and scikit-image in the layer above SciPy, Pandas, and Matplotlib. NX has millions of monthly downloads, hundreds of citations per year, and hundreds of contributors over the years. We don't have direct data on AI usage of NetworkX, but anecdotal evidence shows AI preference for using NX with Python network analysis. Nearly 440,000 GitHub repositories include NX as a dependency including over 11,500 packages. These include scikit-image, Pythran, ScanPy, SPARQL, micro-SAM, aioway, Proteinix, asf_search, QBioCode, and hypernetX. A Google scholar search for "AI life sciences NetworkX" shows 963 papers in 2026 so far discussing both AI usage and NetworkX for the life sciences.

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
- [ ] Scientific computing
- [ ] Statistical modeling
- [ ] Workflows and computational pipelines
- [ ] Data visualization
- [ ] Interoperability
- [ ] Software ecosystem infrastructure
- [ ] Hardware acceleration and scalability
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



