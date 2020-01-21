Please provide comments and feedback via the [github
repository](https://github.com/ropenscilabs/statistical-software).

# 1\. Introduction

This document serves as an organizing framework for rOpenSci’s project
for peer-review of statistical software. It lays out key considerations,
outstanding questions, and tasks for our first year of work, for
purposes of generating community feedback. The document consists of the
following sections:

  - **Scope of Statistical Software Review** in which we address the
    scope of the project, and scopes of definition of “statistical
    software”.

  - **Statistical Software Peer Review Process** in which we consider
    questions regarding the possible forms and practices a peer review
    process might adopt.

  - **Standards for Statistical Software** in which we consider the
    kinds of standards which might be developed and applied to assess
    statistical software.

  - **Software Assessment** in which we provide a partial list of
    attributes and measures of software which might be usefully
    considered.

  - **Automation and Tooling** in which we briefly consider which
    aspects of the project might be amenable to, or might benefit the
    most from, the development of automation processes and tools.

The document aims to highlight what we consider some of the most
important questions which the project will have to address. In its
current form, this document does not aim to provide answers to any of
these questions, rather to provide a framework for community feedback.
The central questions which emerge from this document are given in
condensed form in an accompanying document which may be used to
structure and enable explicit feedback on the above aspects of the
project.

## 1.1 Project Aims

  - To foster a community of practice in which users and developers of
    statistical software mutually improve quality, reproducibility, and
    reliability of research.

  - To provide software creators with a set of tools to assess the
    quality of their work, and a process by which to improve it.

  - To provide statistical software developers, users, and consumers of
    results a discoverable “badge” that transparently conveys a level of
    assurance of software quality and may be usable as professional
    credit.

  - To create a set of standards that may be adopted and adapted by open
    source and private groups, academic journals, or other statistical
    software evaluation projects.

  - To focus on R as primary language, but separate language-specific
    from language-agnostic components so as to maximize adaptability to
    other contexts.

  - To focus on problems and solutions specific to statistical software.

## 1.2 Related projects and initiatives

The following internal and external projects related projects have
bearing on our work:

rOpenSci is simultaneously working on improving the automation and
documentation of infrastructure to support software peer reviews. This
will support many of the processes described herein, initially those in
metrics and diagnostic reports (below), as well as in managing the
review process.

Secondly, [under a separate project funded by the Moore
Foundation](https://ropensci.org/blog/2019/11/06/scientific-package-ecosystem/),
rOpenSci is building a system to automate the retrieval of information
related to use of software in published literature and automate
reporting of software impact as part of metadata in software
repositories. This builds on [Depsy](http://depsy.org/) and
[CiteAs](http://citeas.org/about) projects and may be leveraged for our
work on metrics (below).

Third, an initiative organized under the R Consortium, the [R Validation
Hub](https://www.pharmar.org/), seeks to provide guidance primarily to R
users in the pharmaceutical industry on validating R packages in
regulated contexts. We are working closely with that group to share
products and avoid duplicated efforts.

# 2\. Scope of Statistical Software Review

A core task is to define the kinds of software that will be covered by
our review process and standards, for which key questions are:

  - What categories of statistical software might be considered *in
    scope*?

  - What categories of statistical software might be considered *out of
    scope*?

  - How would these vary between a useful definition and typology for
    general use, and the specific case of our R-focused peer review
    system?

A key consideration in scope is identifying categories of software that
(a) will benefit from our peer review process, and (b) the review
process will be equipped to handle. That is, can standards and
procedures be defined that are applicable, and will authors and
reviewers be able to apply them? In considering these issues of
definition, it will be important to consider whether it may be
advantageous or necessary to develop different procedures for different
sub-categories, whether in terms of categories of external form or
categories of statistical software.

## 2.1 Defining “Statistical Software”

There is no ready definition for “statistical software”, but nor may
such a definition be essential to the success of the present project. As
a point of comparison, the Journal of Statistical Software journal
defines [its own scope](https://www.jstatsoft.org/pages/view/mission) as
“statistical computing in all areas of empirical research,” with
articles describing “comprehensive open-source implementations of broad
classes of statistical models and procedures or computational
infrastructure upon which such implementations can be built.”\[1\]

It will likely be nevertheless important for the present project to
develop some scheme for categorization, particularly because the set of
standards envisioned by this project will be variably applicable to
different categories, and understanding which standards may or may not
apply to a particular piece of software will provide important
information for review purposes. The following points provide examples
of the kinds of categories which may be usefully considered:

  - Supervised / regression models and algorithms

  - Unsupervised models and algorithms

  - Predictive / black box approaches

  - Parametric and analytically tractable approaches

  - Implementation of new methods

  - Re-implementation or improvement of methods

  - Workflow support for multiple methods or specific contexts

  - Summary statistic calculation

  - Statistical visualization and diagnostics

  - Power analysis and study design

  - “Wrappers” around internally-bundled or externally-installed
    routines coded by third parties

We conceive of categorization as providing useful direction in the
development and application of standards, particularly because different
standards are likely to apply to differing degrees for different
categories of software. Individual pieces of software will often fit
more than one of these categories, but we envision relating some kind of
categorical checklist directly to a corresponding checklist of relevant
or applicable standards.

## 2.2 Examples of Statistical Software

We now consider a few brief categorical examples, to illustrate the
kinds of decisions such a process of categorisation will likely face.

  - [**gtsummary**](https://github.com/ropensci/software-review/issues/334),
    submitted to rOpenSci and reject as out-of-scope.

<!-- -->

  - Creates presentation-ready tables summarizing data sets, regression
    models, \> and more. The code to create the tables is concise and
    highly \> customizable. Data frames can be summarized with any
    function, \> e.g. mean(), median(), even user-written functions.
    Regression models are \> summarized and include the reference rows
    for categorical variables. \> Common regression models, such as
    logistic regression and Cox proportional \> hazards regression, are
    automatically identified and the tables are \> pre-filled with
    appropriate column headers.
    
    This package appears not to contain any algorithmic implementations,
    yet is clearly aimed at enhancing a purely statistical workflow.
    Such a submission requires answering the question of whether
    software categorized as “workflow” only and which does not
    correspond to any other of the above categories, may be deemed in
    scope?

<!-- -->

  - [greta: simple and scalable statistical modelling in
    R](https://joss.theoj.org/papers/10.21105/joss.01601), published in
    JOSS.

<!-- -->

  - greta is an package for statistical modelling in R (R Core Team,
    2019) that \> has three core differences to commonly used
    statistical modelling software \> packages:
    
      - greta models are written interactively in R code rather than in
        a \> compiled domain specific language.
    
      - greta can be extended by other R packages; providing a
        fully-featured \> package management system for extensions.
    
      - greta performs statistical inference using TensorFlow (Abadi et
        al., \> 2015), enabling it to scale across modern
        high-performance computing \> systems.
    
    The `greta` package might be considered predominantly an interface
    to TensorFlow, yet it provides a new way to specify and work with
    purely statistical models. This might be considered under both
    workflow and wrapper categories, and serves here to illustrate the
    question of whether wrappers around, in this case,
    externally-installed software might be considered in scope? And if
    so, to what extent ought aspects of such externally-installed
    software also be directly addressed within a review process?

<!-- -->

  - [**modelStudio**](https://joss.theoj.org/papers/10.21105/joss.01798),
    published in JOSS.

<!-- -->

  - The `modelStudio`R package automates the process of model
    exploration. It \> generates advanced interactive and animated model
    explanations in the form \> of a serverless HTML site. It combines
    R(R Core Team, 2019) with D3.js \> (Bostock, 2016) to produce plots
    and descriptions for various local and \> global explanations. Tools
    for model exploration unite with tools for EDA \> to give a broad
    overview of the model behaviour.
    
    As with `gtsummary` above, this is clearly a package intended to
    enhance a workflow, and furthermore one which primarily serves to
    generate summary output as a `ht``ml` document, yet the models it
    considers, and all aspects of output produced, are purely
    statistical. This package could meet both workflow and visualization
    categories, and serves here to illustrate difficulties in
    considering the latter of these. The `D3.``js` library contains
    numerous indubitably statistical routines, and so this package might
    be argued to be a wrapper in the same category as `greta` is a
    wrapper around `TensorFlow`. An important question likely to arise
    in considering both of these is the extent to which the library
    being wrapped should also be *predominantly statistical* for a
    package to be in scope? (A requirement which `greta` would more
    easily fulfil than `gtsummary`.)

We have compiled a list of the descriptions of [all packages rejected by
rOpenSci](https://github.com/mpadge/statistical-software/blob/master/abstracts/ropensci-abstracts.md)
as being out of current scope because of current inability to consider
statistical packages, along with a selection of [recent statistical R
packages](https://github.com/mpadge/statistical-software/blob/master/abstracts/joss-abstracts.md)
accepted by JOSS. (The full list of all R package published by JOSS can
be viewed at <https://joss.theoj.org/papers//in/R>).

## 2.3 Computer Languages and Package Structures

Our scope of work for this project is focused on developing peer-review
for statistical software in the R language. This most likely will refer
to R *packages*. However, it may also consider review of other forms for
bundling R software, or software primarily written in other languages.
Moreover, R packages often contain code from a variety of other
languages, traditionally Fortran and C, now very commonly also C++, as
well as other non-compiled languages such as JavaScript, and compiled
languages such as Rust. It is accordingly expected that software review
will potentially encompass code in several languages. We will need to
determine the extent to which each of these categories may be in-scope
and how review may vary between them:

  - R packages containing compiled code in traditionally used compiled
    languages (Fortran C, C++)

  - R packages containing code in other languages (Rust, Python,
    JavaScript)

  - Packaging appropriate for other languages (such as Python) yet with
    some interface with the R language

  - R interfaces to algorithms or software developed independently in
    different languages (“wrapper” packages)

  - Other forms of bundling or presenting R code other than standard
    packages (scripts, modules, graphical / web user interfaces)

Moreover, the project aims to develop a set of language-independent
standards able to be transferred to other languages and systems for peer
review. In scoping and standards development, we will separate
language-agnostic concepts from language-specific implantation.

# 3\. Statistical Software Peer Review Process

Our point of departure for our process is the rOpenSci software peer
review process, which has operated for five years, reviewing \>200
packages primarily in the area of data lifecycle management. However, we
aim to reassess this process in light of other models and needs specific
to statistical software. Some core questions we seek to resolve are:

  - What are we reviewing? (Full packages? Only limited pieces of
    packages? Other forms of softare?)

  - What is the outcome of review?
    
      - Do we generally presume ultimate acceptance and work with
        package authors to improve quality prior to acceptance, as
        largely practiced in current rOpenSci system?
    
      - Or ought there be some possibility of rejection following
        review?
    
      - Do we develop and use some kind of “checklist” system, with a
        list of essential properties and practices which must be met
        prior to acceptance, along with potentially additional items
        reflecting current best practices which may be met?
    
      - To what extent can or should processes and procedures following
        review be formalized (and potentially automated)? This is
        related to issues of lifecycle considered below.

  - To what extent should the review process be automated or
    self-certified? Stages which might gain from automation include:
    
      - Compiling diagnostic reports throughout and following review
    
      - Using these to populate checklists of the kind mentioned above
    
      - Finding reviewers, through combinations of text mining, code
        analyses, web scraping, and other means.
    
      - Directly managing the review process, like current operations of
        the Journal of Statistical Software.
    
      - Monitoring ongoing use of, and community surrounding, our
        peer-reviewed software.

  - Which parts of the process should be open and which closed?

  - Should review be a one-off phenomenon, or should there be multiple
    review phases throughout the software lifecycle?

  - Should we maintain the separation or independence of reviewers from
    code development, or might it be better to encourage direct
    engagement of reviewers with ongoing code development?

  - Who should be in the pool of software reviewers and editors, and how
    might we find and cultivate such a pool?

## 3.1 Current Models

rOpenSci’s current software peer-review process, detailed in our
[developer
guide](https://devguide.ropensci.org/softwarereviewintro.html), is based
on a blend of practices from peer review of academic practices and code
review in open-source projects. Review takes place via an issue thread
in our [“software-review” repository on
GitHub](https://github.com/ropensci/software-review). The review process
is entirely open, with each issue thread used to manage the entire
process, coordinated by rOpenSci’s editors. After initial screening for
scope and minimal qualification by editors two reviewers provide
comments and feedback on software packages. After one or more rounds of
revisions, packages reach a point of approval, at which point they are
“accepted” by rOpenSci, symbolized both through a badge system, and
(generally) through transferring the software from an author’s private
domain to the [github.com/ropensci domain](https://github.com/ropensci).

The [Journal of Open Source Software](https://joss.theoj.org/) was based
on rOpenSci and follows a similar approach, with greater automation and
broader scope. The Journal of Statistical Software conducts a closed
review of both manuscript and software, with fewer prescriptive
standards. [BioConductor](https://www.bioconductor.org), in reviewing
packages for acceptance into its repository conducts an [open
review](https://www.bioconductor.org/developers/package-submission/)
primarily aimed at maintaining minimum standards and intercompatibilty.

Other initiatives further afield from academic peer review may offer
useful models. For instance, the Linux [Core Infrastructure
Initiative](https://www.coreinfrastructure.org/) provides badges to
project meeting [development best
practices](https://github.com/coreinfrastructure/best-practices-badge/blob/master/doc/criteria.md).
Badges are graded (passing/silver/gold), and awarded by package authors
self-certifying that they have implemented items on a checklist. The
[Debian](https://debian.org) system has an extensive set of standards
referred to as the [“Debian Policy”
document](https://www.debian.org/doc/debian-policy/ch-source.html#standards-conformance).
This document is versioned, and each Debian package must assert the
latest version of the standards to which it conforms. This requirement
enables potentially obsolete packages to be readily flagged, and readily
ensures the active maintenance of software. A continuously updated
[“Upgrading
Checklist”](https://www.debian.org/doc/debian-policy/upgrading-checklist.html)
explicitly describes the steps necessary to ensure conformance to each
consecutive upgrade of the Policy Document. There are also
language-specific policies, such as [for python
packages](https://www.debian.org/doc/packaging-manuals/python-policy/module_packages.html).

## 3.2 Software Life Cycle Considerations

The importance of considering Software “lifecycles” has long been
recognized for closed-source proprietary software, yet lifecycles have
only been given scant consideration in contexts of open source software
(exceptions include Stokes 2012; Lenhardt et al. 2014). A long history
and tradition in both practice and published literature on software
review (for example, Mili 2015; Ammann and Offutt 2017) generally
concludes that software review is most effective when it is an ongoing
process that is structurally embedded within a software lifecycle, and
when review occurs as frequently as possible. Such a practice contrasts
strongly with the singular nature of review as currently implemented by
rOpenSci.

An effective system for peer review of statistical software is thus may
lie somewhere between the “one-off” practices above, and frequent,
ongoing review typical of software development in active teams. An
[analysis of the effects of rOpenSci’s review process on a few metrics
of software development
activity](https://github.com/mpadge/statistical-software/tree/master/ros-review-effects)
revealed that software development tends to stagnate following review.
This may be interpreted to reflect software having reached a
sufficiently stable state requiring relatively little ongoing
maintenance. However, we note that metrics of community engagement with
software are generally positively related to the metrics of development
activity considered there. Slowing of software development following
review may also accordingly reflect or result in decreases in community
engagement.

Potential systems to enhance review of the kind current practiced by
rOpenSci, and particularly to encourage and enable more ongoing review
on smaller scales and shorter time frames, include pull-request reviews,
and systems for providing inline code reviews (such as
[watson-ruby](https://github.com/nhmood/watson-ruby)). In addition,
ongoing “review” may be explicit in considering the role of user
feedback, for instance, in defining and updating the scope of
statistical routines (see “Standards for Statistical Software” below).

## 3.3 Community

A core goal of the project is the building and maintenance of a
community of practice that will facilitate dissemination, adoption, and
improvement of standards and peer review. In striving for this goal, the
following questions are important:

  - What outreach should we conduct to maximize diversity and inclusion
    in the process?

  - How should this process involve other relevant communities in fields
    including software development, statistics, applied statistics (in
    various subfields)

  - What fora should we manage for developers, users, reviewers and
    editors to communicate? To what extent should we reuse existing fora
    from rOpenSci or other organizations?

We now briefly consider the three aspects of community relevant to this
project: communities of users, of developers, and of reviewers. Note
that several of the kinds of “metrics” alluded to in the following lines
are given explicit consideration at the end of this document.

**Software use and surrounding community:**

  - What sort of metrics might provide insight into community use of
    software?

  - How might such community engagement be enhanced to improve such
    metrics?

**Software development and surrounding community:**

  - What sort of metrics might provide insight into community
    development of software?

  - How might such community engagement be enhanced to improve such
    metrics?

**Reviewer pool and qualifications:**

  - What is the extent and type of effort expected of reviewers?

  - To what extent might searches for suitable reviewers be automated?

  - What sort of metrics might be useful in such searches?

In each case the project will strive to cultivate diverse, inclusive,
and geographically expansive communities, and metrics to describe such
aspects may also be important, as may automated tools to monitor
community engagement and development.

# 4\. Standards

An important output of the present project a set of standards which
serve as expectations for software and guides for reviewers to assess
software against.

Important general questions regarding standards include the following:

  - What kind of standards might apply to software in general?

  - How might such standards differ between different languages?

  - What kind of standards might specifically apply to statistical
    software? (See the following sub-section.)

  - To what extent should we aim for “verification” or “validation” of
    software?

We acknowledge that standards of the kind anticipated here will likely
be better conceived of to reflect ongoing processes of development. As
such, of equal importance to developing a set of standards *per se* will
be developing an understanding of the kinds of *processes* which may
have the most defining effect on resultant standards at any point in
time.

The remainder of this document employs a convenient distinction between:

  - “*General Standards*” which may be applied to all software
    considered within this project, irrespective of how it may be
    categorized under the times of categories of statistical software
    listed above; and

  - “*Specific Standards*” which apply to different degrees to
    statistical software depending on the software category.

It is likely that standards developed under the first category may
subsequently be deemed to be genuinely *Statistical Standards* yet which
are applicable across all categories, and we thus anticipate a degree of
fluidity between these two broad categories. Moreover, we do not pursue
*General Standards* any further in the present document, and merely
presume that these will emerge, or may be derived, from the following
considerations of *Specific Aspects of Software*.

## 4.1 Standards Specific to Statistical Software

The applicability of any concrete set of standards is likely to differ
between different categories of statistical. For example, metrics of
numerical accuracy will likely differ between categories primarily
describing analytical algorithms and those describing less tractable
routines which produce less directly reproducible results. Or consider
metrics derived from tests, which must be interpreted in *qualitatively*
different ways for packages entirely dependent on their own internal
code versus packages largely dependent on the results of calls to
external data providers (along with additional differences between, for
example, locally-installed “external” providers versus online sources of
external data).

Different standards must thus be considered to be differentially
applicable to different categories of software, and thus the interplay
between the scope of statistical software considered above and
throughout this project, and the standards emerging from the project,
will be of critical importance throughout the project. Such
considerations lead to the following kinds of questions which will
likely have to be addressed:

  - To what extent ought we aim for general standards at the expense of
    specific ability to assess particular categories of statistical
    software?

  - To what extent ought we strive for automation of software
    assessment, given the inherent risk of overseeing qualitative
    differences between different categories?

  - How much effort should be expended both developing a categorization
    of statistical software, and understanding the potential effects of
    such a categorization?

The following exemplify a few categories of statistical standards which
may be considered, emphasising restrictions of applicability to
alernative kinds of software.

  - **Numerical standards such as precision or convergence.** These will
    be applicable only to some restricted subset of all potential
    categories of statistical software (likely including but not limited
    to analytic and, to some extent, predictive routines) Moreover, even
    these two categories alone will likely require differing standards
    for precision or convergence.

  - **Method validity** It may be necessary or useful to develop
    standards for the *validity* of a chosen method, independent of its
    implementation. Questions of validity are commonly related to
    domains of application, and therefore must relate directly to any
    system for categorising statistical software. A method may (have
    been demonstrated to) be valid for some particular domain of
    application, and a software routine may be developed to adapt that
    method to some previously untried domain. It may then be necessary
    to consider potential (in)validity of that software, along with
    potential validity in other domains, themselves potentially not
    explicitly considered by the software authors.

  - **Software scope** The preceding considerations extend directly to
    general concerns of *scope*, whether in terms of domains of
    applicability, properties of input or output data, authorial
    intentions, or other contextual factors. Scope in all of these
    senses obviously must directly affect and determine the kinds of
    standards which may or may not apply to software, just as defining
    scope in these senses is also effectively an exercise in
    categorization of the kind described above.

  - **Reference standards** For software which implements or relies on
    standard routines, it may be necessary to designate reference data
    or implementations against which to compare outcomes, or guidance in
    selecting such references. For instance, the National Institute of
    Standards and Technology of the U.S. provides [a collection of
    reference data sets](https://www.itl.nist.gov/div898/strd/) with
    certified computational results which statistical software should be
    able to reproduce.

We envision the project proceeding from this initial stage by developing
parallel definitions for both categories of software (defining both
*in*-scope and *beyond*-scope, above), and specific standards. A simple
way to proceed may be to develop lists for both, along with a
representation of inter-connections between categories and standards.

## 4.2 Generally Applicable Standards

In addition to standards specific to the challenges of statistical
software, it will also be necessary to create or adopt standards
governing general aspects of software, such as interface, documentation,
and testing. Mili (2015) also provides a general list of software design
principles, divided between *Functional Attributes* (including
Correctness and Robustness), *Usability Attributes* (including Ease of
Use, Ease of Learning, Customizability, Calibrability, and
Interoperability), and *Structural Attributes* (including Design
Integrity, Modularity, Testability, and Adaptability).

### 5.1 Software Interface

There are likely aspects of overall software interface (“API”) that
might be considered, reviewed, encouraged, or expected. rOpenSci’s guide
on [package development, maintenance, and peer
review](https://devguide.ropensci.org/) provides standards of this type
for R packages, primarily within its first chapter. Another notable
example is the [tidyverse design
guide](https://principles.tidyverse.org/), and [Conventions for R
Modeling
Pacakges](https://tidymodels.github.io/model-implementation-principles/)
provides guidance for model-fitting APIs.

### 5.2 Documentation

Standards will include requirements for form and completeness of
documentation. As with interface, several sources already provide
starting points for reasonable documentation.

Some documentation requirements will be specific to the statistical
context. For instance, it is likely we will have requirements for
referencing appropriate literature or references for theoretical support
of implementations. Another area of importance is correctness and
clarity of definitions of statistical quantities produced by the
software, e.g., the definition of null hypotheses or confidence
intervals. Data included in software – that used in examples or tests –
will also have documentation requirements.

An additional area for consideration is the creation of tools for
documentation creation and evaluation based on metadata of statistical
method inputs and outputs and packaged data (Lenhardt et al. 2014).
Relationships between data and statistical software may be structured in
a sufficiently systematic way to permit systematic documentation.

<!---
https://github.com/tdwg/vocab/blob/master/sds/documentation-specification.md
--->

### 5.3 Testing

Testing is a critical area for standards, as tests are a concrete
manifestation of standards and the means by which authors may
demonstrate compliance. While testing is considered best practice and
test coverage often used as a measure of test completeness, guidance on
*what* to test is rare, especially in the context of R packages. Thus,
standards will need to provide guidance on the types and methods of
tests required for different statistical software categories.

In addition, statistical software may benefit from means or modes of
testing beyond the common frameworks used in and for R packages (e.g. R
RMD check, testhtat). A variety of other frameworks and workflows from
other languages and contexts may be relevant. Almost all testing as
currently implemented in R is “concrete testing” (Mili 2015), and little
consideration has been given in R to “stochastic” or “property-based”
testing, in which expectation values of inputs and outputs are tested,
rather than concrete instantiations of such. Other languages have
developed grammars for stochastic or property-based testing, notably
through the [hypothesis package for
python](https://github.com/HypothesisWorks/hypothesis). These grammars
enable specification of test assumptions as well as expected test
outputs. Assumptions in `hypothesis` are declared through simple
`@given` statements that might, for example, quantify an assumed
probability distribution for input data, while outputs are specified
through equivalent `@expect` statements that might, for example, specify
expected *distributional properties* of an output rather than just
concrete values.

The following are likely key questions which we will need to address
regarding testing:

  - To what extent should testing focus on *functional* or *integration*
    rather than *unit* testing?

  - Is it sufficient to consider test execution as an integral part of
    `R CMD check` only? Or might there by a case for developing
    alternative test execution environments and approaches? For
    instance, should there be an alternate workflow for long-running
    tests, tests requiring large data, or tests intended to be executed
    for other purposes?

  - Is it worthwhile concretely defining one or more goals of testing?
    (Such as error detection, error frequencies, error tolerance,
    accuracy.)

  - What are the test data? And how easy is it to input alternative data
    to tests?

  - Is there scope for “stochastic” or “property-based” testing?

  - What test reporter should be used? Does the `testthat` package and
    similar suffice? Or might it be worth considering new test reporting
    systems?

  - What aspects of tests and test data (both actual and permissible)
    might be worthwhile documenting in some kind of metadata format?

# 5\. Software Assessment

To additionally inform the general considerations described in the
preceding sections, this section presents a general (yet non-exhaustive)
overview of aspects of software which may be usefully considered for
standards-based assessment, both for retrospective purposes of peer
review, and for prospective use in developing software both in general,
and in preparation for peer-review. It will be important to consider the
applicability of each metric to different categories of statistical
software, as well as the extent to which the following aspects may be
more or less applicable or relevant at different phases of a software
lifecycle, or how expected values for, or results of applying, metrics
may vary throughout a software lifecycle.

## 5.1 General Software Metrics

The following is an incomplete list of the kinds of metrics commonly
used to evaluate software in general, and which might provide useful for
assessing statistical software in the present project.

  - Code structure
    
      - Cyclomatic complexity
    
      - Codebase size
    
      - Function size / number
    
      - Numbers of external calls within functions
    
      - Numbers and proportions of Exported / non exported functions
    
      - Code consistency
    
      - Dynamic metrics derived from function call networks or similar
        
          - Network-based metrics both for entire packages, for
            individual functions, and derived from analyses of test
            coverage
        
          - Functional overlap with other packages

  - Documentation metrics:
    
      - Numbers of documentation lines per function
    
      - Proportion of documentation to code lines
    
      - Presence of examples
    
      - Vignettes

  - Data documentation metrics
    
      - Intended and/or permitted kinds of input data
    
      - Nature of output data
    
      - Description of data used in tests

  - Meta struture
    
      - Dependencies
    
      - Reverse dependencies

  - Meta metrics
    
      - License (type, availability, compatibility)
    
      - Version control?
    
      - Availability of website
    
      - Availability of source code (beyond CRAN or similar)
    
      - Community:
        
          - Software downloads and usage statistics
        
          - Numbers of active contributors
        
          - Numbers or rates of issues reported
    
      - Maintenance:
        
          - Rate/Numbers of releases
        
          - Rate of response to reported issues
        
          - Last commit
        
          - Commit rate
    
      - stars (for github, or equivalent for other platforms)
    
      - forks

  - Extent of testing
    
      - Code coverage
    
      - Examples and their coverage
    
      - Range of inputs tested

## 5.2 Metrics specific to statistical software

Metrics specific to statistical software will depend on, and vary in
applicability or relevance with, the system for categorizing statistical
software expected to emerge from the initial phase of this project.
Details of this sub-section will be largely deferred until we have a
clearer view of what categories might best be considered, which we are
hopeful will emerge following the first committee meeting, and in
response to ensuing feedback. In the meantime, metrics can be
anticipated by referring to the preceding examples for categories of
statistical software (numerical standards, method validity, software
scope, and reference standards). We anticipate having a number of such
categories, along with a number of corresponding metrics for assessing
software in regard to each category. As mentioned at the outset,
software will generally be expected to fit within multiple categories,
and specific metrics will need to be developed to ensure validity for
software encompassing any potential combination of categories.

## 5.3 Diagnostics and Reporting

While the preceding sub-sections considered *what* might be assessed in
relation to statistical software, the project will also need to
explicitly consider *how* any resultant assessment might best be
presented and reported upon. Indeed, a key output of the project is
expected to be a suite of tools which can be used both in this and other
projects to construct, curate, and report upon a suite of peer-reviewed
software. Moreover, we will aim to develop these tools partly to provide
or enhance the *automation* of associated processes, aiming both to
enhance adaptability and transferability, and to ensure the scalability
of our own project.

It is useful in this context to distinguish between *collective* tools
useful for, of applicable to, collections of software, of individuals,
or of processes pertaining to either (here, primarily peer review), and
*singular* tools of direct applicability to individual pieces of
software. We envision needing to address the (likely relative)
importance of some of the following kinds of diagnostic and reporting
tools which may be usefully developed.

**Collective Tools**

  - Qualitative tools useful in assessing or formalizing categories of
    software

  - Quantitative tools to retrospectively assess such aspects as:
    
      - Collective “quality” of software
    
      - Community engagement
    
      - Effectiveness (or other metrics) of review

**Singular Tools**

  - Quantitative tools that can be prospectively used to
    
      - Improve or assure software quality
    
      - Document aspects of software quality
    
      - Aid modularity or transferability either of software, or of the
        tools themselves

  - Tools to formalize structural aspects of software such as tests (for
    example, through implementing new frameworks or grammars)

  - Extensions of extant packages such as **lintr**, **covr**,
    **goodpractice**

  - Comparisons of package metrics to distributions for other packages
    or systems (such as the CRAN archive directories)

  - Diagnostic and report aggregation, design, or automatic creation at
    any stage before, during, or after peer review.

The one question of abiding importance is the extent to which any such
tools, and/or the automation of processes which they may enable, might
enhance any of the following aspects:

  - Software development
  - Peer review of software
  - Wider communities of users or developers
  - The adaptation of our system to other domains

A good example for the effectiveness of automation in the kinds of peer
review processes envisioned to emerge from this project is provided by
submissions to the [Journal of Open Source
Software](https://joss.theoj.org/), which features [open
reviews](https://github.com/openjournals/joss-reviews/issues), many
aspects of which are automated by a custom-developed bot called
[“whedon”](https://github.com/whedon).

# 7\. Bibliography

<!---
Lots to put here, but some in addition to stuff in current document:

-   <https://www.alexpghayes.com/blog/type-stable-estimation/>,
    <https://www.alexpghayes.com/blog/testing-statistical-software/>

-   <https://tidymodels.github.io/model-implementation-principles/>

-   <https://github.com/pharmaR/white_paper>

-   <https://github.com/coreinfrastructure/best-practices-badge/blob/master/doc/criteria.md>
-->

Ammann, Paul, and Jeff Offutt. 2017. *Introduction to Software Testing*.
Cambridge University Press.

Mili, Ali. 2015. *Software Testing: Concepts and Operations*.

Vogel, David A. 2011. *Medical Device Software Verification, Validation
and Compliance*. Boston: Artech House.
<http://site.ebrary.com/id/10436227>.

Ammann, Paul, and Jeff Offutt. 2017. *Introduction to Software Testing*.
Cambridge University Press.

Mili, Ali. 2015. *Software Testing: Concepts and Operations*.

<div id="refs" class="references hanging-indent">

<div id="ref-ammann_introduction_2017">

Ammann, Paul, and Jeff Offutt. 2017. *Introduction to Software Testing*.
Cambridge University Press.

</div>

<div id="ref-lenhardt_data_2014">

Lenhardt, W., Stanley Ahalt, Brian Blanton, Laura Christopherson, and
Ray Idaszak. 2014. “Data Management Lifecycle and Software Lifecycle
Management in the Context of Conducting Science.” *Journal of Open
Research Software* 2 (1): e15. <https://doi.org/10.5334/jors.ax>.

</div>

<div id="ref-mili_software_2015">

Mili, Ali. 2015. *Software Testing: Concepts and Operations*.

</div>

<div id="ref-stokes_21_2012">

Stokes, David. 2012. “21 - Validation and Regulatory Compliance of
Free/Open Source Software.” In *Open Source Software in Life Science
Research*, edited by Lee Harland and Mark Forster, 481–504. Woodhead
Publishing Series in Biomedicine. Woodhead Publishing.
<https://doi.org/10.1533/9781908818249.481>.

</div>

</div>

1.  We explored whether we could usefully define topics of interest in a
    [preliminary text
    analysis](https://github.com/mpadge/statistical-software/tree/master/jss)
    of all historical submissions to JSS yet found no notable phrases or
    topics which might be useful to define or categorize statistical
    software, other than topics pertaining to particular areas of
    application.
