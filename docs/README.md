---
layout: home
permalink: index.html

# Please update this with your repository name and title
repository-name: eYY-4yp-project-template
title:
---

[comment]: # "This is the standard layout for the project, but you can clean this and use your own template"

## Acceleration of deep neural network based nanopore super accuracy basecalling

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
### Abstract

Nanopore sequencing is a technique that is used to real-time analyze long DNA and RNA fragments which is being rapidly adopted in genomics. Monitoring changes in an electric current passing through a protein nanopore (a nanopore is a nano-size pore or cavity) as a nucleic acid and using the resulting signals to identify specific DNA or RNA fragments are the working principles of the Nanopore sequencing. Although it can be used to get real-time data sequencing which provides immediate access to the results, There are challenges in the data processing or the computational analysis side of nanopore sequencing due to the large volume of data and, the amount of computational resources required making the current basecalling implementation that uses GPUs requires few days.



### Motivation
DNA sequencing plays a crucial role in molecular biology, enabling scientists to determine the precise order of nucleotides (adenine, cytosine, guanine, and thymine) within a DNA molecule. This technology has revolutionized fields like genetics, genomics, and personalized medicine by providing valuable insights into the genetic makeup of organisms. Nanopore sequencing, a technique used for real-time analysis of long DNA and RNA fragments, has emerged as a powerful tool in genomics. However, the processing and analysis of large datasets pose significant challenges in nanopore sequencing data analysis. In this article, we will explore the challenges involved and the solutions researchers are developing to accelerate the analysis of nanopore sequencing data.

#### Challenges in Nanopore Sequencing Data Analysis

Nanopore sequencing presents several challenges that need to be addressed for efficient data analysis:

1. Handling Large Datasets: Nanopore sequencing generates enormous amounts of raw signal data, which requires efficient algorithms and computational techniques to process and analyze effectively.

2. Pre-processing Steps: Raw data from nanopore sequencing undergoes pre-processing steps, including signal calibration, noise reduction, and quality filtering, before further analysis.

3. Basecalling: Basecalling is a critical step in nanopore sequencing that converts raw electrical signals into DNA bases. The noisy nature of the signal makes achieving accurate results computationally demanding.

#### Oxford Nanopore Sequencing

Oxford Nanopore sequencing, developed by Oxford Nanopore Technologies, is an innovative next-generation DNA and RNA sequencing technology that has gained significant attention in the scientific community. It utilizes nanopore-based sensing to analyze DNA or RNA molecules, offering several unique features.

The working principle of Oxford Nanopore sequencing involves preparing the DNA sample by fragmenting it into smaller pieces and attaching adapters to facilitate attachment to the nanopore sequencing device. The device contains an array of nanopores, tiny protein channels embedded in a membrane. As individual DNA strands pass through the nanopore, they cause disruptions in the electrical current, which are detected and recorded. Changes in the electrical current are measured and converted into signals, allowing for the determination of base sequences.

The collected electrical signals are processed using specialized software, which compares them to a reference genome and reconstructs the original DNA sequence. The resulting DNA sequence can be further analyzed for various applications such as identifying genetic variations, studying gene expression levels, detecting epigenetic modifications, and detecting structural variations. Additionally, Oxford Nanopore sequencing allows for metagenomic analysis, long-range genomic analysis, and transcriptome assembly.


#### Advantages of Oxford Nanopore Sequencing

Oxford Nanopore sequencing offers several advantages compared to other sequencing technologies:

1. Real-Time Sequencing: Oxford Nanopore sequencing provides real-time sequencing data, allowing researchers to observe the results immediately and make rapid decisions during the sequencing process.

2. Long Read Lengths: This technology produces long sequencing reads, enabling genome assembly, resolving complex genomic regions, and detecting structural variants.

3. Portable and Flexible Instruments: Oxford Nanopore sequencing platforms, such as MinION and GridION, are portable, compact, and suitable for on-site or point-of-care applications. The modular nature of the platform allows for scalability and flexibility in throughput and data production.

4. Direct DNA/RNA Sequencing: Unlike other sequencing technologies, Oxford Nanopore sequencing enables direct sequencing of native DNA or RNA molecules without additional amplification or synthesis steps, reducing potential biases and artifacts.

5. Broad Range of Applications: Oxford Nanopore sequencing is applicable to various research areas, including whole-genome sequencing, transcriptomics, metagenomics, epigenetics, and real-time monitoring of DNA or RNA modifications.

6. Cost-Effective: Oxford Nanopore sequencing offers competitive pricing and cost-effective sequencing of small to large genomes

However, nanopore sequencing faces limitations in terms of computational resources. Processing the sequencing data can be time-consuming, limiting scalability and efficiency. To address these challenges, researchers are exploring approaches such as algorithmic optimizations, parallel computing, and hardware accelerators to accelerate data processing and analysis, reduce processing time, and improve accessibility and cost-effectiveness.

In summary, Oxford Nanopore sequencing is a powerful tool that offers real-time sequencing, long read lengths, portability, and a broad range of applications. Despite computational limitations, ongoing advancements aim to enhance the technology and unleash its full potential in genomic research and analysis.


<details>
  <summary>Related Works
  
  There are few areas which have related works on Nanopore sequencing.

* Data compression techniques
* Techniques related to the file format for handling nanopore data
* Deep learning related improvements
* Hardware Acceleration
  </summary>

1. Impact of lossy compression of nanopore raw signal data on basecalling and consensus accuracy

This rsearch has been focused on the first area in which researchers have explored the use of lossy compression for nanopore raw data using two state-of-the-art lossy time-series compressors, and evaluate the tradeoff between compressed size and basecalling/consensus accuracy. 

According to the conclusion of the research, they have found that lossy compression with existing tools can reduce the compressed size by 35–50% over lossless compression with less than 0.2% percent reduction in basecalling accuracy.

2. Fast nanopore sequencing data analysis with SLOW5

The emergence of nanopore sequencing, enabled by devices from Oxford Nanopore Technologies (ONT), has revolutionized genomics by allowing the sequencing of native DNA and RNA molecules without a theoretical upper limit on read length. However, the large data volumes generated by ONT devices and the computational bottlenecks associated with analyzing the data have posed significant challenges.

Nanopore sequencing data is typically stored in the FAST5 file format, which is based on hierarchical data format 5 (HDF5). However, the FAST5 format lacks efficient parallelization capabilities, leading to slow analysis times. To address this limitation, a new file format called SLOW5 has been introduced. SLOW5 is specifically engineered for efficient parallelization and acceleration of nanopore data analysis.

SLOW5 retains all the information present in the FAST5 format but does not rely on the HDF5 library for file access. It uses a tab-separated values (TSV) file format for encoding metadata and time series signal data for each nanopore read. SLOW5 also includes a binary index file that facilitates parallel
file access. Additionally, SLOW5 can be encoded in a compact binary format called BLOW5, which offers further space savings and supports compression algorithms like zlib and ’vbz’ for efficient storage and parallel access. 

Compared to FAST5, SLOW5 offers several advantages. It is approximately 25% smaller in size, leading to reduced storage requirements. It enables faster data access, as demonstrated by improved read rates compared to FAST5 when using multiple CPU(Central Processing Units) threads. This improved data access translates to significant performance gains in data analysis, particularly for applications like DNA methylation profiling using tools such as Nanopolish/f5c. The runtime for such analyses can be reduced from more than two weeks to approximately 10.5 hours on a high-performance computer, representing a substantial improvement. 

The benefits of SLOW5 extend to different computer architectures, ranging from large high-performance computing systems to smaller devices like portable computers. SLOW5 consistently improves data access and overall execution times across a diverse range of hardware setups. To facilitate the adoption of SLOW5, software tools have been developed for efficient conversion from FAST5 to SLOW5 and for live conversion during a sequencing run. These tools ensure that the transition from FAST5 to SLOW5 is not a barrier and provide users with raw data in the compressed BLOW5 format, resulting in minimal additional workflow time.

The introduction of SLOW5 addresses the inherent limitations of the FAST5 format and provides a scalable framework for efficient analysis of nanopore signal data. The simplicity, efficiency, and open-source nature of SLOW5 encourage active software development in the field of nanopore data analysis,
similar to the impact of the SAM/BAM format in genome informatics

3. Flexible and efcient handling of nanopore sequencing signal data with slow5tools

The study on ’Flexible and efcient handling of nanopore
sequencing signal data with slow5tools’ introduces key
tools and techniques for working with SLOW5 files. slow5lib
and pyslow5 are highlighted as tools for reading and writing SLOW5 files, offering sequential access and easy access in Python, respectively. The study focuses on compression techniques, implementing three schemes in slow5lib: ZLibrary (zlib), Zstandard (zstd), and StreamVByte (svb). These
schemes efficiently compress SLOW5 records and the raw signal field, providing flexibility for users. Additionally, the study discusses slow5tools as a tool for FAST5/SLOW5 conversion,
supporting Unix systems and various C/C++ compilers. The tool utilizes multiprocess and POSIX thread approaches to enhance the conversion process. In summary, the study presents essential tools and techniques, including slow5lib, pyslow5, and slow5tools, for efficient handling of SLOW5 files. These
tools enable sequential access, compression, and conversion, providing flexibility and ease of use for both C and Python programmers.

In the SLOW5 benchmarking experiments, genomic DNA
from the human NA12878 reference sample was sequenced using an ONT PromethION device. The benchmarking was performed on multi-FAST5 files generated by MinKNOW, with
the original FAST5 files compressed using zlib compression.
The experiments excluded single-FAST5 format due to slower
data access and larger file size compared to multi-FAST5
format. The computational benchmarking utilized slow5lib
integrated with f5c v.0.2 CPU version, which employs POSIX
threads for multi-threaded access to FAST5 and SLOW5 files.
Guppy and minimap2 were used to obtain FASTQ and BAM files, respectively. Measurements included overall execution time, CPU utilization percentage, and execution time for individual components.

4. Beyond sequencing: machine learning algorithms extract biology hidden in Nanopore signal data

This review paper has been focused on discussing machine learning applications on nanopore sequencing. Other than sequencing genomes and transcriptomes, this paper discusses on
    
    * extracting biological information from these signals allow the detection of DNA and RNA modifications
    * estimation of poly(A) tail length
    * prediction of RNA secondary structures

Nanopore basecalling is a process in nanopore sequencing
that converts raw ion current signals into a readable sequence
of DNA or RNA bases. During sequencing, as a nucleic acid
molecule passes through a nanopore, changes in ion current
are detected and recorded. Basecalling algorithms analyze
these signals to determine the corresponding sequence of
bases. Due to the noisy nature of the signals and the presence of similar signal ranges for different bases, basecalling can be challenging. However, advancements in basecalling
algorithms, such as using Hidden Markov Models (HMMs)
or Recurrent Neural Networks (RNNs), have significantly
improved the accuracy and reliability of nanopore basecalling.
These algorithms help decode the ion current signals and
produce high-quality base sequences, enabling researchers to
study and understand the genetic information contained within
the DNA or RNA molecules.

Early basecalling methods typically achieved an accuracy
of 85% or lower. Since then, significant advancements have
been made in basecalling algorithms to improve nanopore
sequencing accuracy. These improvements have been a driving
force in achieving over 98.3% accuracy in correctly identifying
bases.

A. Hidden Markov model-based basecallers

HMMs are statistical models employed in Computational
Biology to uncover concealed patterns or information from observable sequences, such as nucleotide sequences. Basecallers, like ONT’s Metrichor and Nanocall, utilize HMMs to interpret
the signal data in nanopore sequencing.
HMM basecallers have limitations in predicting sequences
in nanopore sequencing due to their focus on short-range
dependencies between k-mers (contiguous subsequences of
length k which consists of k nucleotides (A, T, C, or G)).
They may not account for long-range dependencies effectively.
Additionally, inaccuracies in the nucleotide sequence model
describing the expected current values of k-mers can introduce
biases in HMM basecallers.

B. RNN based basecallers

To address constraints of Hidden Markov model-based basecallers, basecalling tools like Albacore, nanonetvi, DeepNano, and BasecRAWller utilize a recurrent neural network (RNN)
framework. This approach helps overcome the limitations of
HMM basecallers by leveraging the capabilities of RNNs to
capture and model both short-range and long-range dependencies in the data.

• Unidirectional RNN

Unidirectional RNNs calculate the current hidden state
and the associated probability distribution of bases using
information from the single current input vector and the
prior hidden state. This allows for the prediction of the
next base in the sequence.

• Bidirectional RNN

To enhance the precision of predictions, tools like Albacore, nanonet, and DeepNano employ a bidirectional RNN. This type of RNN incorporates information from
both the past and future states of the ion current input
vector. Although bidirectional RNNs provide improved
accuracy, they can require more time for processing due
to the additional computations involved.

C. Segmentation-free basecallers

Early basecallers rely on a segmentation process to determine segment boundaries based on abrupt signal changes. However, this segmentation approach is prone to errors due to
variable translocation speeds and noisy signals. To overcome
these challenges, segmentation-free basecallers have been developed, such as ONT’s Albacore version 2.0.1v and the open source software Chiron. Chiron takes a different approach by
combining a convolutional neural network (CNN) to extract
signal features and a recurrent neural network (RNN) to predict nucleotide probabilities. It further employs a connectionist temporal classification (CTC) decoder, which selects the base
with the highest probability at each position and maps them
together to form the final complete sequence. By eliminating
the need for segmentation, Chiron improves the accuracy and
efficiency of basecalling in nanopore sequencing.

</details>

### Methodology

1. Understand the codebase
2. Find the bottlenecks using timestamps
3. Research on optimising the bottlenecks
4. Test for the performance improvement & Accuracy 

### Scope

Acceleration of Slorado basecaller with memory utilization and algorithmic optimization

### Experiment Setup and Implementation

Contiguous Memory Allocation of RNN Weights and matrix multiplication are the main bottlenecks.

1. Optimizing Contiguous Memory Allocation of RNN Weights
2. Optimizing Large matrix multiplication

Winograd's matrix multiplication code was implemented in CUDA to replace current matrix multiplication function utilizing Cublas functions for basic matrix algebra kernels. The reason is to select winograd algorithm is the lowest time complexity it has among other matrix multiplication algorithms. 

<details>
  <summary>Winograd matrix multiplication algorithm
  </summary>

parameters: A=Tensor A, B=Tensor B, C=Tensor C

Execution Steps:
1) Calculate width and height values of sub-matrices
int rowsA = A.size(0);
int colsA = A.size(1);
int rowsB = B.size(0);
int colsB = B.size(1);
int subRowsA=rowsA/2;
int subColsA=colsA/2;
int subRowsB=rowsB/2;
int subColsB=colsB/2;
2) Allocate space in global memory for each of the
sub-matrices such that (subRowsA* subColsA *
sizeof(float)) is allocated for A11, A12, A21, A22 and
(subRowsB* subColsB * sizeof(float)) for B11, B12,
B21, B22
3) Set sub-matrices
4) Allocate space in global memory for intermediate
matrices S1, S2, S3, S4, S5, S6, S7, S8, m1, m2, m3,
m4, m5, m6, m7
5) Calculate S1=A21+A22, S2=S1-A11, S3=A11+A21,
S4=A12- S2, S5=B12-B11, S6=B22-S5,S7=B22-
B12,S8=S6-B21
6) if (rowsA <= BLOCK_THRESHOLD) then Calculate
m1=S2*S6 , m2=A11*B11, m3=A12*B21, m4=S3*S7,
m5=S1*S5, m6=S4*B22, m7=A22*S8
7) else
Call winograd_mm(S2, S6, m1)
Call winograd_mm(A11, B11, m2)
Call winograd_mm(A12, B21, m3)
Call winograd_mm(S3, S7, m4)
Call winograd_mm(S1, S5, m5)
Call winograd_mm(S4, B22, m6)
Call winograd_mm(A22, S8, m7)
8) Synchronize all threads
9) Caculate C11=M2+M3, C12=M1+M2+M5+M6,
C21=M1+M2+M4-M7, C22=M1+M2+M4+M5
10) Merge C11, C12, C21, and C22 into output matrix C
11) Convert matrix C into a Tensor
12) Free all allocated global memory
</details>
<details>
  <summary> CUDA device functions for compute C11, C12, C21, C22 and C</summary>

``````
__global__ void computeC12 (float* C, float* m1 ,float* m2 ,float* m5 ,float* m6 , int subWidth)
{

    int tx = threadIdx.x;
    int ty = threadIdx.y;

    int row = blockIdx.y * TILE_Y + ty;
    int column = blockIdx.x * TILE_X + tx;

    __shared__ float as[ TILE_Y ][ TILE_X ];
    /* This line declares a shared memory array 'as' with dimensions TILE_Y by TILE_X. Shared memory is used for cooperative thread block-level data sharing.*/
    float Csub ; /*to store the intermediate sum.*/

    as[ty ][ tx ]= m1 [( row )* subWidth + column ];
    Csub =as[ty ][ tx ];
    as[ty ][ tx ]= m2 [( row )* subWidth + column ];
    Csub += as[ty ][ tx ];
    as[ty ][ tx ]= m5 [( row )* subWidth + column ];
    Csub += as[ty ][ tx ];
    as[ty ][ tx ]= m6 [( row )* subWidth + column ];
    Csub += as[ty ][ tx ];
    C[( row )* subWidth + column ]= Csub;

}
``````

``````
__global__ void computeC11 (float* C,float* m2 ,float* m3, int subWidth)
{
    int tx = threadIdx.x;
    int ty = threadIdx.y;

    int row = blockIdx.y * TILE_Y + ty;
    int column = blockIdx.x * TILE_X + tx;

    __shared__ float as[ TILE_Y ][ TILE_X ];
    float Csub;

    as[ty ][ tx ]= m2 [( row )* subWidth + column ];
    Csub =as[ty ][ tx ];
    as[ty ][ tx ]= m3 [( row )* subWidth + column ];
    Csub += as[ty ][ tx ];
    C[( row )* subWidth + column ]= Csub;

}

``````
``````
__global__ void computeC22 (float* C,float* m1,float* m2, float* m4, float* m5, int subWidth)
{
    int tx = threadIdx.x;
    int ty = threadIdx.y;
    int row = blockIdx.y * TILE_Y + ty;
    int column = blockIdx.x * TILE_X + tx;
    __shared__ float as[ TILE_Y ][ TILE_X ];
    float Csub ;

    as[ty ][ tx ]= m1 [( row )* subWidth + column ];
    Csub =as[ty ][ tx ];
    as[ty ][ tx ]= m2 [( row )* subWidth + column ];
    Csub += as[ty ][ tx ];
    as[ty ][ tx ]= m4 [( row )* subWidth + column ];
    Csub += as[ty ][ tx ];
    as[ty ][ tx ]= m5 [( row )* subWidth + column ];
    Csub += as[ty ][ tx ];
    C[( row )* subWidth + column ]= Csub;

}

``````
``````
__global__ void computeC21 (float* C,float* m1, float* m2, float* m4, float* m7, int subWidth ){

    int tx = threadIdx.x;
    int ty = threadIdx.y;

    int row = blockIdx.y * TILE_Y + ty;
    int column = blockIdx.x * TILE_X + tx;
    __shared__ float as[ TILE_Y ][ TILE_X ];
    float Csub ;

    as[ty ][ tx ]= m1 [( row )* subWidth + column ];
    Csub =as[ty ][ tx ];
    as[ty ][ tx ]= m2 [( row )* subWidth + column ];
    Csub += as[ty ][ tx ];
    as[ty ][ tx ]= m4 [( row )* subWidth + column ];
    Csub += as[ty ][ tx ];
    as[ty ][ tx ]= m7 [( row )* subWidth + column ];
    Csub -= as[ty ][ tx ];
    C[( row )* subWidth + column ]= Csub;

}

``````
``````
__global__ void mergeSubmatrices(float* submatrix0, float* submatrix1, float* submatrix2, float* submatrix3, float* finalMatrix,int N, int M)
{
    int x = threadIdx.x;
    int y = threadIdx.y;

    finalMatrix[y * M + x] = submatrix0[y * N + x];
    finalMatrix[y * M + x + N] = submatrix1[y * N + x];
    finalMatrix[(y + N) * M + x] = submatrix2[y * N + x];
    finalMatrix[(y + N) * M + x + N] = submatrix3[y * N + x];
}
``````

</details>

### Results and Analysis

Current progress : ~52% performance improvement by optimizing Contiguous Memory Allocation of RNN Weights


### Conclusion

### Publications
[//]: # "Note: Uncomment each once you uploaded the files to the repository"

1. [Semester 7 report](https://www.overleaf.com/read/xrxwntnvjvzw)
2. [Semester 7 slides](https://docs.google.com/presentation/d/1dHEG9yFM64_zesxkOAz7Bek2ve_-AykZds2fYHVTiZQ/edit?usp=sharing)
3. [Semester 8 report](https://www.overleaf.com/read/pbsgyfsfshbf#30d8c6) 
4. [Semester 8 mid presentation slides](https://docs.google.com/presentation/d/1B0t23Atwd4plcLOh9_XFJz47RPqVpAGk/edit?usp=sharing&ouid=104472781387848199298&rtpof=true&sd=true)
5. [Semester 8 end presentation slides](https://docs.google.com/presentation/d/1QYtur04M6fK93ZOTVnGnpxzGpuMdrz8s/edit?usp=sharing&ouid=104472781387848199298&rtpof=true&sd=true)
<!-- 5. Author 1, Author 2 and Author 3 "Research paper title" (2021). [PDF](./). -->



### Links

[//]: # ( NOTE: EDIT THIS LINKS WITH YOUR REPO DETAILS )

- [Project Repository](https://github.com/cepdnaclk/e17-4yp-Acceleration-of-deep-neural-network-based-nanopore-super-accuracy-basecalling)
- [Project Page](https://cepdnaclk.github.io/e17-4yp-Acceleration-of-deep-neural-network-based-nanopore-super-accuracy-basecalling)
- [Department of Computer Engineering](http://www.ce.pdn.ac.lk/)
- [University of Peradeniya](https://eng.pdn.ac.lk/)

[//]: # "Please refer this to learn more about Markdown syntax"
[//]: # "https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet"
