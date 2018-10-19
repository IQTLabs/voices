---
title: Reading
feature_text: |
  ## Download Page Links
  Voices Obscured in Complex Environmental Settings
feature_image: "https://picsum.photos/1300/400?random"
excerpt: "A short description of the VOiCES corpus"
aside: True
---

## Dataset Download

VOiCES is now publicly available on AWS. Check out the [AWS Registry of Open Data](https://registry.opendata.aws/lab41-sri-voices/) for details. Data structure
and microphone specifics are available in our [README](Lab41-SRI-VOiCES_README.md) file.  

### Dependencies

To download VOiCES audio corpus, install the
[AWS Command Line Interface (CLI)](https://aws.amazon.com/cli/) and link to an active AWS account.
[Configure](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html) the AWS CLI by typing `aws configure` in the command line.

To list the content of the s3 bucket associated with VOiCES, run  
```aws s3 ls s3://lab41openaudiocorpus```

Download data using
```aws s3 sync <source> <target> [--options]```
or  
```aws s3 cp <source> <target> [--option]```

### Data Releases
Early 2018 : room-1 and room-2, 200 speakers
Fall 2018 (to be released soon!): room-3, 200 speakers
Additional rooms and speakers to be released Fall 2019
