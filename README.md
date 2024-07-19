# UKDRI_Interview
Repository created to showcase work as part of task for an interview.

Script workflow guide:

Initialize Channels Based on Sequencing Data Type:
Reason: Different sequencing data types (single-end vs. paired-end) require different handling and processing. Proper initialization ensures the correct processing pathway is chosen.
Validate Input Files:
Reason: Ensuring the integrity and correctness of input files prevents errors downstream in the analysis. Validation checks help catch issues early, saving time and resources.
Run Quality Control on Raw Reads (FastQC, MultiQC):
Reason: Quality control is crucial to identify any issues with the sequencing data, such as low-quality reads or adapter contamination. This step ensures that only high-quality data is used for further analysis.
Trim and Filter Reads (Fastp):
Reason: Trimming removes adapters and low-quality bases from the reads, improving the overall quality of the data. Filtering ensures that only high-quality sequences are retained for downstream analysis.
Remove Human Contaminants (Bowtie2):
Reason: Environmental samples may contain human RNA contaminants. Removing these ensures that the analysis focuses on the relevant microbial and environmental RNA.
Remove rRNA (SortMeRNA):
Reason: Ribosomal RNA (rRNA) can dominate RNA sequencing data, obscuring the detection of mRNA and other RNA types. Removing rRNA enriches the sample for more informative transcripts.
Perform Quality Control on Cleaned Reads (FastQC, MultiQC):
Reason: Re-running quality control on the cleaned reads ensures that the trimming and filtering steps were successful and that the data is of high quality before further analysis.
Filter Quality Control Results:
Reason: Filtering the QC results helps to systematically exclude low-quality samples and focus on high-quality data for downstream processes.
Assemble the Transcriptome (RNA-Bloom):
Reason: Assembling the transcriptome from the RNA reads reconstructs the RNA sequences, providing a comprehensive view of the transcripts present in the sample.
Cluster and Dereplicate Assembled Sequences (MMseqs2):
Reason: Clustering and dereplication reduce redundancy in the assembled sequences, simplifying the dataset and improving the efficiency of downstream analyses.
Build Bowtie2 Indexes for Representative Sequences:
Reason: Creating indexes for the representative sequences allows efficient alignment of reads back to these sequences, facilitating accurate quantification and further analysis.
Align Reads to Representative Sequences (Bowtie2):
Reason: Aligning reads back to the representative sequences enables the quantification of transcript abundance and validation of the assembly.
Assess Assembly Quality (QUAST):
Reason: Assessing the quality of the assembly ensures that the assembled transcriptome is accurate and reliable, providing confidence in the downstream analyses.
Check Completeness of Assembly (BUSCO):
Reason: BUSCO evaluates the completeness of the transcriptome assembly by comparing it to a set of conserved genes, ensuring that the assembly captures the full diversity of the sample.
Translate Sequences for Functional Annotation:
Reason: Translating RNA sequences into protein sequences is necessary for functional annotation, allowing the identification of gene functions and pathways.
Annotate Sequences (KofamScan, EggNOG):
Reason: Functional annotation provides insights into the biological roles of the transcripts, helping to understand the metabolic capabilities and functional potential of the sample.
Identify Metabolic Pathways (MinPath):
Reason: Identifying metabolic pathways reveals the functional capabilities of the microbial community, providing insights into its ecological roles and interactions.
Prepare Reference for Abundance Estimation (RSEM):
Reason: Preparing a reference allows accurate estimation of transcript abundance, which is crucial for understanding the relative expression levels of different genes.
Estimate Abundance of Transcripts:
Reason: Quantifying transcript abundance provides information on the activity of different genes, reflecting the metabolic and functional state of the microbial community.
Integrate Functional and Abundance Information:
Reason: Integrating functional annotation with abundance data helps to link gene expression with functional potential, providing a comprehensive understanding of the community’s activity.
Generate Final Reports:
Reason: Final reports summarize the analysis results, providing a clear and comprehensive overview of the findings. These reports are crucial for interpreting the data and communicating results to stakeholders.
