---
layout: home
permalink: index.html

# Please update this with your repository name and title
repository-name: eYY-4yp-project-template
title:
---

[comment]: # "This is the standard layout for the project, but you can clean this and use your own template"

# Acceleration of deep neural network based nanopore super accuracy basecalling

#### Team

- E/17/012, R. A. A. U. Amarasinghe, [email](mailto:e17012@eng.pdn.ac.lk)
- E/17/201, W. T. Madushani, [email](mailto:e17201@eng.pdn.ac.lk)
- E/17/284, R. L. D. A. S. Rathnayaka, [email](mailto:e17284@eng.pdn.ac.lk)

#### Supervisors

- Prof. Roshan Ragel, [email](mailto:roshanr@eng.pdn.ac.lk)
- Dr. Damayanthi Herath, [email](mailto:damayanthiherath@eng.pdn.ac.lk)
- Dr. Hasindu Gamarachchi, [email](mailto:hasindu@unsw.edu.au)

#### Table of content

1. [Abstract](#abstract)
2. [Related works](#related-works)
3. [Methodology](#methodology)
4. [Experiment Setup and Implementation](#experiment-setup-and-implementation)
5. [Results and Analysis](#results-and-analysis)
6. [Conclusion](#conclusion)
7. [Publications](#publications)
8. [Links](#links)

---

DELETE THIS SAMPLE before publishing to GitHub Pages !!!
This is a sample image, to show how to add images to your page. To learn more options, please refer [this](https://projects.ce.pdn.ac.lk/docs/faq/how-to-add-an-image/)
![Sample Image](./images/sample.png)


## Abstract

Nanopore sequencing is a technique that is used to real-time analyze long DNA and RNA fragments which is being rapidly adopted in genomics. Monitoring changes in an electric current passing through a protein nanopore (a nanopore is a nano-size pore or cavity) as a nucleic acid and using the resulting signals to identify specific DNA or RNA fragments are the working principles of the Nanopore sequencing. Although it can be used to get real-time data sequencing which provides immediate access to the results, There are challenges in the data processing or the computational analysis side of nanopore sequencing due to the large volume of data and, the amount of computational resources required making the current basecalling implementation that uses GPUs requires few days.

## Related works
DNA sequencing plays a crucial role in molecular biology, enabling scientists to determine the precise order of nucleotides (adenine, cytosine, guanine, and thymine) within a DNA molecule. This technology has revolutionized fields like genetics, genomics, and personalized medicine by providing valuable insights into the genetic makeup of organisms. Nanopore sequencing, a technique used for real-time analysis of long DNA and RNA fragments, has emerged as a powerful tool in genomics. However, the processing and analysis of large datasets pose significant challenges in nanopore sequencing data analysis. In this article, we will explore the challenges involved and the solutions researchers are developing to accelerate the analysis of nanopore sequencing data.

#### Challenges in Nanopore Sequencing Data Analysis

Nanopore sequencing presents several challenges that need to be addressed for efficient data analysis:

1. Handling Large Datasets: Nanopore sequencing generates enormous amounts of raw signal data, which requires efficient algorithms and computational techniques to process and analyze effectively.

2. Pre-processing Steps: Raw data from nanopore sequencing undergoes pre-processing steps, including signal calibration, noise reduction, and quality filtering, before further analysis.

3. Basecalling: Basecalling is a critical step in nanopore sequencing that converts raw electrical signals into DNA bases. The noisy nature of the signal makes achieving accurate results computationally demanding.

### Oxford Nanopore Sequencing

Oxford Nanopore sequencing, developed by Oxford Nanopore Technologies, is an innovative next-generation DNA and RNA sequencing technology that has gained significant attention in the scientific community. It utilizes nanopore-based sensing to analyze DNA or RNA molecules, offering several unique features.

The working principle of Oxford Nanopore sequencing involves preparing the DNA sample by fragmenting it into smaller pieces and attaching adapters to facilitate attachment to the nanopore sequencing device. The device contains an array of nanopores, tiny protein channels embedded in a membrane. As individual DNA strands pass through the nanopore, they cause disruptions in the electrical current, which are detected and recorded. Changes in the electrical current are measured and converted into signals, allowing for the determination of base sequences.

The collected electrical signals are processed using specialized software, which compares them to a reference genome and reconstructs the original DNA sequence. The resulting DNA sequence can be further analyzed for various applications such as identifying genetic variations, studying gene expression levels, detecting epigenetic modifications, and detecting structural variations. Additionally, Oxford Nanopore sequencing allows for metagenomic analysis, long-range genomic analysis, and transcriptome assembly.
Advantages of Oxford Nanopore Sequencing

Oxford Nanopore sequencing offers several advantages compared to other sequencing technologies:

1. Real-Time Sequencing: Oxford Nanopore sequencing provides real-time sequencing data, allowing researchers to observe the results immediately and make rapid decisions during the sequencing process.

2. Long Read Lengths: This technology produces long sequencing reads, enabling genome assembly, resolving complex genomic regions, and detecting structural variants.

3. Portable and Flexible Instruments: Oxford Nanopore sequencing platforms, such as MinION and GridION, are portable, compact, and suitable for on-site or point-of-care applications. The modular nature of the platform allows for scalability and flexibility in throughput and data production.

4. Direct DNA/RNA Sequencing: Unlike other sequencing technologies, Oxford Nanopore sequencing enables direct sequencing of native DNA or RNA molecules without additional amplification or synthesis steps, reducing potential biases and artifacts.

5. Broad Range of Applications: Oxford Nanopore sequencing is applicable to various research areas, including whole-genome sequencing, transcriptomics, metagenomics, epigenetics, and real-time monitoring of DNA or RNA modifications.

6. Cost-Effective: Oxford Nanopore sequencing offers competitive pricing and cost-effective sequencing of small to large genomes

However, nanopore sequencing faces limitations in terms of computational resources. Processing the sequencing data can be time-consuming, limiting scalability and efficiency. To address these challenges, researchers are exploring approaches such as algorithmic optimizations, parallel computing, and hardware accelerators to accelerate data processing and analysis, reduce processing time, and improve accessibility and cost-effectiveness.

In summary, Oxford Nanopore sequencing is a powerful tool that offers real-time sequencing, long read lengths, portability, and a broad range of applications. Despite computational limitations, ongoing advancements aim to enhance the technology and unleash its full potential in genomic research and analysis.

There are few areas which have related works on Nanopore sequencing.

* Data compression techniques
* Techniques related to the file format for handling nanopore data
* Machine Learning techniques

1. Impact of lossy compression of nanopore raw signal data on basecalling and consensus accuracy

This rsearch has been focused on the first area in which researchers have explored the use of lossy compression for nanopore raw data using two state-of-the-art lossy time-series compressors, and evaluate the tradeoff between compressed size and basecalling/consensus accuracy. 

According to the conclusion of the research, they have found that lossy compression with existing tools can reduce the compressed size by 35–50% over lossless compression with less than 0.2% percent reduction in basecalling accuracy.

2. Flexible and efcient handling of nanopore sequencing signal data with slow5tools

This research has been focused on the second topic where researchers have done a good experiment on introducing a new file format called slow5 for handling nanopore data.

3. Fast nanopore sequencing data analysis with SLOW5

4. Beyond sequencing: machine learning algorithms extract biology hidden in Nanopore signal data

This review paper has been focused on discussing machine learning applications on nanopore sequencing. Other than sequencing genomes and transcriptomes, this paper discusses on
    * extracting biological information from these signals allow the detection of DNA and RNA modifications
    * estimation of poly(A) tail length
    * prediction of RNA secondary structures

    basecalling :
    Basecalling is a crucial step in nanopore sequencing, where raw ion current signal data is converted into a sequence of bases. The ion current signal represents the measured changes in current as a nucleic acid molecule translocates through a nanopore. The challenge lies in accurately determining the corresponding k-mers (sequences of five bases for RNA or six bases for DNA) based on the noisy signal data. This difficulty is amplified by the presence of homopolymers, where multiple k-mers share similar ion current signal ranges.

    Early basecalling methods typically achieved an accuracy of 85% or lower. Since then, significant advancements have been made in basecalling algorithms to improve nanopore sequencing accuracy. These improvements have been a driving force in achieving over 98.3% accuracy in correctly identifying bases.

    Hidden Markov model-based basecallers, such as ONT's Metrichor and Nanocall, use a hidden Markov model (HMM) to decode the signal data in nanopore sequencing. These basecallers consider the ion current signals as observable events and the k-mers as states within the HMM.

    HMM basecallers have limitations in predicting sequences in nanopore sequencing due to their focus on short-range dependencies between k-mers. They may not account for long-range dependencies effectively. Additionally, inaccuracies in the nucleotide sequence model describing the expected current values of k-mers can introduce biases in HMM basecallers. To address these constraints, basecalling tools like Albacore, nanonetvi, DeepNano, and BasecRAWller utilize a recurrent neural network (RNN) framework. This approach helps overcome the limitations of HMM basecallers by leveraging the capabilities of RNNs to capture and model both short-range and long-range dependencies in the data.

## Methodology

## Experiment Setup and Implementation

## Results and Analysis

## Conclusion

## Publications
[//]: # "Note: Uncomment each once you uploaded the files to the repository"

<!-- 1. [Semester 7 report](./) -->
<!-- 2. [Semester 7 slides](./) -->
<!-- 3. [Semester 8 report](./) -->
<!-- 4. [Semester 8 slides](./) -->
<!-- 5. Author 1, Author 2 and Author 3 "Research paper title" (2021). [PDF](./). -->


## Links

[//]: # ( NOTE: EDIT THIS LINKS WITH YOUR REPO DETAILS )

- [Project Repository](https://github.com/cepdnaclk/e17-4yp-Acceleration-of-deep-neural-network-based-nanopore-super-accuracy-basecalling)
- [Project Page](https://cepdnaclk.github.io/e17-4yp-Acceleration-of-deep-neural-network-based-nanopore-super-accuracy-basecalling)
- [Department of Computer Engineering](http://www.ce.pdn.ac.lk/)
- [University of Peradeniya](https://eng.pdn.ac.lk/)

[//]: # "Please refer this to learn more about Markdown syntax"
[//]: # "https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet"
