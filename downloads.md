---
title: Reading
feature_text: |
  ## Download Page Links
  Voices Obscured in Complex Environmental Settings
feature_image: "/images/VOICES_Download_Image.jpg"
excerpt: "A short description of the VOiCES corpus"
aside: True
---

# Getting Started With VOiCES

## Downloading the from S3

VOiCES is now publicly available on AWS. Check out the [AWS Registry of Open Data](https://registry.opendata.aws/lab41-sri-voices/) for details. Data structure
and microphone specifics are available in our [README](Lab41-SRI-VOiCES_README.md) file.  

The easiest way to access the data is through the [AWS Command Line Interface (CLI)](https://aws.amazon.com/cli/).  Follow that link to setup and configure the AWS CLI.  The VOiCES data is stored on the `lab41openaudiocorpus` S3 bucket.

To list the content of the s3 bucket associated with VOiCES, run
```
aws s3 ls s3://lab41openaudiocorpus
```
There will be three files present:

```
VOiCES_release.tar.gz (417.5 GiB)
VOiCES_devkit.tar.gz (27.5 GiB)
VOiCES_competition.tar.gz (19.5 GiB)
```

Download data using `aws s3 sync <source> <target> [--options]` or
`aws s3 cp <source> <target> [--option]`.  For example, to download the devkit to current directory run the following:

```
aws s3 cp s3://lab41openaudiocorpus/VOiCES_devkit.tar.gz .
```
All files are compressed archives and can be decompressed using gzip.
