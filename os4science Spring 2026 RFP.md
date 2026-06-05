---
title: os4science Spring 2026 RFP
tags: [os4science 2026]

---

os4science Spring 2026 RFP

#### Dates:
- LOI June 8, 2026 
- results of LOI June 23
- Full Propsal July 21
- results of full proposal October 2026

#### LOI form:  https://renphil.fillout.com/os4ls
Os4science.org funding 2026

###### possible LOI for scientific python project
skills
dispatching
summits


### NetworkX LOI Submission:
---
#### Title (54/60 chars)
**NetworkX for Big Data, Agentic Access and Algorithms**

#### Summary (3000 chars)
---
##### Prompt
*Briefly describe the purpose of the proposal and the software project(s) it involves.*

###### Todo:
- add freethreading
- add skills  (is mentioned)
- more dispatching?   (is mentioned)

##### Text (3578/3000 chars)
Previous funding for NetworkX(NX) has lead to a robust developer community, a system of nx-guides for documentation, a dispatching system allowing no-code-change switch of hardware from CPUs to GPUs, and updated algorithms for Subgraph Isomorphism and Community Detection.

We use the term network here, but graph theory uses graph to mean the same thing.

We propose three focus areas for work over the next two years.
1) Big Data interoperability with data analysis libraries and bio-related dataset formats.
2) nx-guides and workflow examples aimed at providing AI agentic context for
   building bio-related workflows and pipelines.
3) Centrality and Visualization algorithms, API and test unification.

A consistent bottleneck to interoperability of network analysis software is data conversion.  Cytoscape, Gephi, iGraph and NX store network information differently and network analysis bioresearch workflows typically use at least two of these tools.  Even within NX our no-code-change dispatching to GPU requires costly conversion.  And our linear algebra tooling requires conversion to SciPy sparse arrays.  Researchers have to convert their data between tools.  NX provides a robust read/write subpackage to allow conversion and storage in many file formats. These do well with moderately sized datasets. We also have tools to read and write JSON datasets with an eye toward streaming graphs via webpages.  But each of these requires converting the dataset from one libraries internal representation to the transfer format and then again to the other libraries internal format.

Agentic tools require domain context to facilitate creating complex workflows.  Our docs are often praised, but we don't have many examples of life science workflows.  Agentic tools also use tests to learn context about how a library works.  We propose to overhaul our docs, tests, and tutorial guides (nx-guides) with an eye toward improving AI tool effectiveness, and to improve, enhance and modernize our bio-related documentation.  In addition, we will create tooling for agentic directions and recipes.  We envision these as "skills" files, but we'll use what the AI world evolves toward between now and the work of the grant.

It is important that we continue to upgrade our subpackages with the latest algorithms and unify our API within subpackages of functions. Based on informal discussions with computational biologists using our tools, we intend to focus on the NX Centrality Measures (CM) and Drawing Tools (DT) subpackages during this grant period.

CM shows the relative importance of nodes to the network structure. This is used to find crucial molecules in reaction networks, super-spreaders in disease transmission, critical regions in drug design.  We have many centrality measures. But their interfaces differ and we don't compare the results in our docs. We'll build tests, docs, and nx-guides which compare results across the different measures. We are also missing some new centrality algorithms and improvements in existing algorithms.

DT is a popular feature even though NX does not focus on graphics.  We provide basic drawing tools because visual cues help researchers gauge progress and look for new relationships. We also provide close connections to specialized libraries like GraphViz and interlibrary tools like iplotx which is designed for both NX and iGraph drawing. Recent funding allowed API development for our new Matplotlib drawing suite. We will implement this API and refactor existing functions to use this new API in a backward compatible way.

#### Expected Value (1500 chars)
---
##### Prompt
*If the proposal is successfully funded, what does success look like?*
*We're seeking to understand:*
- what type of capabilities the proposal is unlocking for the scientific community;
- how upstream and downstream software will be improved by the proposal;
- how the proposed work supports or implements novel functionality that enables AI
  and large-scale data analysis.

##### Text (1867/1500 chars)
Our computational biology users and their AI tools will spend less time converting data between and within libraries and avoid duplicate storage of large datasets.  They can avoid the conversion bottleneck for workflows crossing tools in different libraries.  It will be easier to move network data across JSON streams as well as via file transfer.  Libraries using SciPy sparse arrays for their storage will be able to access NX data structures directly.  Workflows and pipelines which use (pandas/polars) DataFrames to store node or edge data no longer need to copy that data to do network analysis.  We will also build a caching system to store conversions so those still needed will not need to be repeated. This will help most libraries working with NX (including our backends) even if they don't use Scipy or DataFrames.

The agentic friendly nx-guides, tests and reference doc improvements, along with agentic directive files and more bio-related examples throughout will help agentic tools effectively associate context with methods, extract examples with desired tasks, and compose building block workflows into complex pipelines that address frontier level questions.  We will create a genomics nx-guide and a spatial biology nx-guide using course exercises and data from Cal Tech and Colgate Univ Computational Biology courses.  These and other nx-guides will be supported by more life science examples in the reference docs and tests.  These should help humans and also provide better context and easier workflow extraction by AI-agentic tools.

Focused algorithm efforts will provide updated centrality measures and a new drawing api within NX as well as connections to specialized drawing packages.  In addition, new centrality measures will be added and both docs and tests will compare results across centrality measures for life science applications.

#### Landscape Analysis (1500 chars) 
---
##### Prompt
We are looking for proposals from software projects with demonstrated traction and adoption. Briefly describe other software tools that the audience for this proposal primarily uses (including proprietary alternatives, if they exist), and how the software project(s) in your proposal compare in terms of user base, adoption, functionality, and maturity relative to their target audience. You can add indicators of adoption and usage as needed. Please indicate if the software is used in AI applications and workflows.

##### Text (1724/1500 chars)
Competing non-Python packages (some of which have Python interfaces) include Cytoscape, Boost, igraph, and Gephi. These are mature, established tools, with sizable user populations. Because these tools are often used in combination, some mechanisms exist to transport data between them. CuGraph, an open source GPU based package, is also being developed by Nvidia while maintaining a NetworkX style API and interoperability with NetworkX Graph objects.  The only other non-toy Python package for network analysis we are aware of is graph-tool. graph-tool is primarily developed by one person and is written in C++ and based on Boost. It can sometimes perform better on large networks than NX; however, it is not integrated into the open source scientific Python ecosystem and community, and, according to various online metrics, has only a small fraction of the number of NX users.  In fact, NX is the fundamental package for network analysis in Python, and when describing the scientific ecosystem is frequently included with scikit-learn, statsmodels, and scikit-image in the layer above SciPy, Pandas, and Matplotlib.  NX has millions of monthly downloads, hundreds of citations per year, and hundreds of contributors over the years. We don't have direct data on AI usage of NetworkX, but anecdotal evidence shows AI preference for using NX with Python network analysis. Nearly 440,000 GitHub repositories include NX as a dependency including over 11,500 packages. These include scikit-image, Pythran, ScanPy, plotly, Deep Graph Library, eht-imaging, Caffe, and OpenPilot.  Google scholar search for "AI life sciences NetworkX" shows 963 papers in 2026 so far discussing both AI usage and NetworkX for e.g. drug design;

#### Projects Supported (urls)
NetworkX
SciPy

#### Categories: (3 tags)
-> Scientific computing
-> Computational pipelines 
-> Data visualization
Hardware acceleration
Genomics and transcriptomics
Developmental biology
Evolutionary biology
Spatial biology
Infectious diseases



