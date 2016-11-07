# Cloudformation Templates
This repository contains some of the [Amazon Web Services](http://aws.amazon.com) [Cloudformation templates](https://aws.amazon.com/cloudformation/) that I use to provision infrastructure on Amazon's cloud service.

The templates are:

To create a stack from the CLI using the templates:

```
aws cloudformation create-stack --stackname <STACKNAME> \
  --template-body file:///path/to/template.yaml \
  --parameters file:///path/to/parameters.json
```

Keith Sharp, [kms@passback.co.uk](mailto:kms@passback.co.uk)
