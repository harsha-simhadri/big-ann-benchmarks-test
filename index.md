## The Billion-Scale Approximate Nearest Neighbor Search Challenge: NeurIPS 2021 Competition

### What is Approximate Nearest Neighbor Search?
Approximate Nearest Neighbor Search (ANNS) is a problem of fundamental importance to search, retrieval, and recommendation. In this problem, we are given a dataset P of points along with a pairwise distance function, typically the d-dimensional Euclidean metric or cosine similarity with d ranging from 50 to 1000. The goal is to design a data structure that, given a target k and a query point q, efficiently retrieves the k nearest neighbors of q in the dataset P according to the given distance function.
<br>
The challenge for ANNS algorithm designers is to craft a data structure that enables fast retrieval of the k nearest neighbors even as the database size grows. Several contemporary large-scale ANNS algorithms employ a class of data structure called an index which eliminates the need to compute a pair-wise distance between the search query and every record in the database. It can do this at the expense of a loss of accuracy, which is where the “approximate” term in ANNS comes into play. The trade-off between accuracy and search latency is an important consideration when designing and evaluating ANNS performance.

### Why this Competition?

In the past few years, we’ve seen a lot of new research and creative approaches tackling large-scale ANNS, including:
- Hash-based, partition-based, and graph-based indexing strategies ( as well as hybrid indexing approaches. )
- Mixing RAM and SSD storage to efficiently store and process large datasets that exceed the size of RAM
- Running on accelerator hardware such as GPUs, FPGAs, and other custom in-memory silicon.
- Leveraging machine learning for dimension reduction of the original vectors.
In addition to an uptick in academic interest, many implementation of these algorithms at scale now appear in production and high availability datacenter contexts: powering enterprise-grade, mission-critical, and web-scale search applications. In these deployment scenarios, benchmarks such as cost, preprocessing time, power consumption become just as important as the accuracy-vs-latency tradeoff.

Despite this, most empirical evaluations of algorithms have focused on smaller datasets of about a million points, e.g. [ann-bechmarks.com](http://ann-benchmarks.com/). However, deploying recent algorithmic advances in ANNS techniques for search, recommendation and ranking at scale require support at billion or substantially larger scale. Barring a few recent papers, there is limited consensus on which algorithms are effective at this scale.

We believe that this challenge will be impactful in several ways:
- Provides a comparative understanding of algorithmic ideas and their application at scale.
- Promotes the development of new techniques for the problem and demonstration of their value.
- Provides a compilation of datasets, many new, to enable future development of algorithms.
- Introduces of a standard benchmarking approach.
By providing a platform for the parties interested in this problem, we aim to en result in more collaboration and collectively advance the field at a more rapid pace.

#### Entry 
We expect registration to open in mid to late May. Watch ths site for more details on registration, finalized datasets, and competition rules. 

#### Timeline
We roughly aim for the following timeline:
- Mid To Late May :  release of data, guidelines, rules, and a call for participation. The competition registration web site goes on-line.
- Mid-June: Code and testing infrastructure released. Participants in need of compute resources will be required to submit an expression of interest.
- Early July: Allocation of compute resources and start of the competition timeline.
- Mid October: End of competition period and submission of code and report.
- Early November: Review of code by organizers and participants. Release of preliminary results on standardized machines.
- Early To Mid November: Participants can raise concerns about the evaluation.
- Early December: Final results published, and competitive results archived (the competition will go on if interest continues).

During NeurIPS Organizers overview the competition and results. Organizers also request the best entries (including leaderboard toppers, or promising new approaches) to present an overview followed by discussion.

### Datasets 
We intend to use the following 6 billion-scale datasets (please note that datasets are subject to change. The final decision on competition datasets will be in our official call-for-participation in mid to late May):
- Microsoft-Turing-ANNS is a new dataset being released by the Microsoft Turing team for this competition.
- Microsoft-SPACEV1B is a new dataset being released by Microsoft Bing for this competition.
- Facebook-simsearchnet is a new dataset being released by Facebook for this competition.
- Text-to-Image search from Yandex is a new cross-model dataset, where database and query vectors can potentially have different distributions in a shared representation space.
- The BIGANN dataset which contains 1 billion SIFT descriptors extracted from a large image dataset.
- The DEEP1B dataset consisting of the outputs of a DNN for a billion images on the web.
Links to the datasets, as well as query and sample sets, and the ground truth nearest neighbors of a query set, will be made available for download prior to the start of the competition. 


### Evaluation 
#### Standard hardware 
Participants are expected to release their code and will submit their ANNS implementation packaged as a docker container (details will be added). During the evaluation phase of the competition, we will download the docker container onto a private bare-metal machine and run the participant’s code on each of the aforementioned datasets. We will support 1 build parameter setting and up to 10 different search parameter sets for each dataset.
The competition will leverage machines that will be in complete control of the organizers. The exact hardware specification depends on the competition track. In the T1 track, we will constrain the size of RAM to 64GB. In the T2 track, in addition to 64GB of RAM, the machine will have also 1TB in SSD storage.
In the T1 and T2 tracks, we will collect the following benchmarks:
- search time ( measured as recall vs throughput )
- index build time

We will provide the exact details on how we collect and compute these benchmarks as well as additional machine and operating system specification before the competition begins.

#### Custom Hardware?
The T3 track of the competition will support non-standard hardware such as GPUs, AI accelerators, FPGAs, and custom in-memory silicon. In this track, participants will either 1) send their hardware (such as PCI boards) to us at their expense 2) if that is not possible, we will make scripts available so that those participants can run the evaluation themselves.
In the T3 track, we will collect the following benchmarks:
- search time ( measured as recall vs throughput )
- index build time
- cost and power ( measured as queries/second/watt and MSRP/watt )
We will ask the participant to provide details and proof of the custom hardware’s cost in the form of manufactured suggested retail price (MSRP).

The exact details on how we collect and compute these benchmarks as well as additional machine and operating system specification will be provided to participants before the competition begins.



<detail>
  <summary>#### Organizers</summary>
  <br>
  The following people have generously donated their expertise, time and resources to organize and run this competition:
  - Harsha Vardhan Simhadri, Microsoft Research India
  - George Williams, GSI Technology
  - Martin Aumüller, IT University of Copenhagen
  - Artem Babenko, Yandex
  - Dmitry Baranchuk, Yandex
  - Qi Chen, Microsoft Research Asia
  - Matthijs Douze, Facebook AI Research
  - Ravishankar Krishnaswamy, Microsoft Research India and IIT Madras
  - Gopal Srinivasa, Microsoft Research India
  - Suhas Jayaram Subramanya, Carnegie Mellon University
  - Jingdong Wang, Microsoft Research Asia
  The organizers may be reached at big-ann-benchmarks@googlegroups.com
</detail>


