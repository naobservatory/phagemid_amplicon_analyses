## Introduction

This repository contains code and data to analyze Amplicon sequencing runs of the NAO's phagemids. Samples were submitted for sequencing on 02 Feb 2023. More information on the sequencing run can be found in this [NAO internal google doc](https://docs.google.com/document/d/1YRjikGYGGN6P9ZY36nNZMrqFOs_UfweKkipn1_YooO4/edit).

## Sequence Download
Sequences can be downloaded from this S3 bucket using the following command:
`aws s3 cp s3://summer-seq-data/230203laura.tar sequences`

You should then unzip them using:
```
cd sequences ; tar -xvf 230203laura.tar
cd 230203laura ; gunzip *.fastq.gz
```

Finally concatenate all FASTQ files and move the resulting file to the output folder

```
cat *.fastq > phagemid_amplicon_nanopore.fastq
mv phagemid_amplicon_nanopore.fastq ../../output/sequences
```

