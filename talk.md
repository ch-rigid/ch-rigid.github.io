# ChRiGiD: Engineering of Data Analysis Pipelines

## Slide 1: Title

Good morning. I'm Jan Vitek from Charles University in Prague. I'm here to present the progress of the ChRiGiD project, funded under the ERC CZ programme, grant LL2325.

## Slide 2: Research Themes

The project is organized around three research themes.

First, practical data science -- we study how data scientists actually work and where things go wrong, through user studies, interviews, and large-scale analysis of real-world code. We have started practical collaborations with data scientists to understand all steps of the process.

Second, type systems -- we develop type systems for dynamic languages, focusing on gradual typing, set-theoretic types, and type inference. The goal is to catch errors without getting in the way of programmers.

Third, tools and languages -- we build compilers, runtime systems, and development tools, including JIT compilation, automated test generation, reproducibility tools, and data lineage tracking.

## Slide 3: 2023--2025 Highlights

Let me give you a quick overview of where we stand. Over the past two years we have published 14 peer-reviewed papers and released 4 open-source software artifacts. The team currently has 11 members from several countries.

On the organizational side, we were selected to host SPLASH 2027, which is one of the top conferences in programming languages. This will be the first time it takes place in Central Europe, with an expected budget of around one million dollars and 400 to 500 attendees.

We organized the PLISS 2025 summer school in Bertinoro, Italy, together with King's College, ČVUT, and Northeastern University.

We launched joint research meetings between Charles University and ČVUT on programming languages, which is a new initiative for both institutions.

We also submitted a HORIZON FRITES proposal under the EU Pathfinder Open call, together with CNRS, TU Kaiserslautern, Ericsson, and others. It was not funded this round, but we plan to resubmit.

Finally, we hosted three visiting researchers: Noller from Ruhr University Bochum, Thakur from IIT, and Sihler from Ulm University.

## Slide 4: Staff

Here is the team. On the faculty side, we have myself as PI, Jan Kofroň, Pavel Parízek, and Tomáš Petříček. Our researchers are Robert Grimm, Joel Jakubovic, and Mickael Laurent. Jakob Hain and Matěj Kocourek are PhD students, Anastasija Skotorenko is a research assistant, and Lucie Lerch handles administration. Four alumni have moved on during the project: Boruch-Gruszecki, Blicha, Ježek, and Sihler.

## Slide 5: Publications 2024

In 2024 we published six papers.

Parízek and Hermann presented work on data lineage analysis. This paper describes scanners which use modular symbolic data flow analysis to automatically trace how data values flow through databases and application code.

We had a paper on decidable subtyping of existential types. Julia's subtyping turns out to be undecidable; the paper proposes a restriction that stratifies types into method signatures over value types to recover decidability, and a corpus analysis shows that nearly all Julia programs already conform to this restriction.

Boruch-Gruszecki led work on gradual compartmentalization via capabilities. Gradient allows incrementally migrating applications to object capabilities for intra-process isolation, combining runtime authority enforcement with type-system tracking to provide continuous security guarantees during the migration.

We had two papers at ECOOP, one on pure methods for roDOT and one on reproducible large-scale code analysis. The roDOT paper explores purity conditions and proves that methods of certain types are side-effect free, with all proofs mechanized in Coq. The Fault in Our Stars paper proposes a standardized experimental design methodology for choosing inputs of studies working with large-scale software repositories, advocating for clear population definitions and discouraging the use of extrinsic attributes like GitHub stars.

And at VMIL, we presented work on reducing feedback pollution in R. Just-in-time compilers record information about past invocations to optimize future ones, but over time feedback vectors lose precision. The paper proposes an approach that achieves a 30% decrease in polluted compilations.

## Slide 6: Publications 2025

In 2025 we published eight papers.

Highlights include a paper on copy-and-patch JIT compilation for R. Copy-and-patch stitches together pre-compiled native code fragments from the existing GNU R interpreter, achieving very fast compilation times -- 980 bytecode instructions per millisecond -- with 1.15x to 1.91x speedups over GNU R.

Petříček's work on Denicek, a computational substrate for end-user programming. Denicek represents a program as a series of edits that construct and transform a document, and provides three operations -- edit application, merging, and conflict resolution -- that can be composed to implement collaborative editing, programming by demonstration, and incremental recomputation.

We had a paper on reproducibility for R. The tool r4r automates the creation of minimal, self-contained Docker execution environments through dynamic program analysis, capturing all runtime dependencies. It achieves exact reproducibility for 97.5% of deterministic notebooks.

Jakubovic's work on unifying Unix executables and Smalltalk methods. The paper argues that the Unix executable should be identified with the Smalltalk method, and shows that a Smalltalk VM implementation via the filesystem falls out naturally from this premise, offering a path to realizing Smalltalk's benefits within Unix.

Laurent's work toward a typed intermediate language for R. The paper documents the design of FIŘ, a new typed intermediate representation for the R JIT compiler, where type annotations capture properties such as sharing, effects, and compiler speculations to enable copy elimination and other optimizations.

We also had a paper on static analysis. Slicito is a tool that lets developers interactively combine static analysis techniques of varying precision, using interprocedural data-flow analysis to narrow scope before applying symbolic execution.

We had a paper on ethics of sentiment analysis and theology.

And we presented work on concurrency error localization. The paper introduces a fuzzing technique for multithreaded C# programs on .NET that controls thread scheduling through suspending and resuming threads, using a hybrid systematic-random strategy to find errors triggered by specific interleavings.

## Slide 7: Open-Source Software

We released four open-source software artifacts. All of these are available on GitHub under permissive licenses.

Shantay is a tool for processing the EU Digital Services Act transparency database. It produces comprehensive reports with timelines from the DSA transparency data, supporting analysis of platform compliance and content moderation practices.

Denicek is the computational substrate for document-oriented end-user programming. It simplifies implementing programming experiences like collaborative editing and programming by demonstration by representing programs as series of edits on documents.

We built R bytecode compilers in both Rust and Java to compare performance with the original R compiler. These serve as a prototype for a new compiler-as-a-service infrastructure, where compilation requests are offloaded to a server with feedback-driven optimizations.

And Smalltix is an implementation of a Smalltalk VM through the filesystem, connecting Unix executables with Smalltalk methods. It demonstrates how the benefits of Smalltalk's live programming environment can be realized within Unix without sequestering the system in a sealed image and VM.
