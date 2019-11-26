# Building AMIs

AMIs can be built for HIPAA-compliant and non-HIPAA compliant implementations. Currently the only difference is the name prefix for the AMI.

AMIs are built with Salt and Packer via an assumed role in the CTL account.

## Dependencies

* An AWS account with proper permissions
* Packer 0.11.0+
* jq
* awscli

## Assuming the Role

You need an account with AssumeRole access to the Packer role in the CTL environment. This requires having an MFA deviced configured.

First source the assume role script to get temporary credentials exported:

```text
$ . scripts/assume_role_with_mfa.sh arn:aws:iam::423681189101:role/Packer
MFA Device ARN: arn:aws:iam::423681189101:mfa/your.username
MFA Token: 123123
Assumed the role arn:aws:iam::423681189101:role/Packer
Session name is PackerSession1479335978
```

This script can be ran at any time. MFA sessions are valid for 12 hours, while roles are valid for 1 hour. The script will only refresh the MFA session or role if they are expired.

## Versioning

AMIs are named based on an env-specific prefix and a dynamic version based on git details like tag, branch, or sha. They are additionally given a suffix based on the current timestamp.

The AMI name is defined in each template file as follows:

```text
{{user `ami_name_prefix`}}-{{user `juicebox_version`}}-{{isotime \"2006.01.02.030405\"}}",
```

The `ami_name_prefix` variable is defined in env-specific Packer var files. This yields AMIs that can be grabbed as needed for deployment.

+================+=====================================+================================================================+ \| Branch or Tag \| Format \| Examples \| +================+=====================================+================================================================+ \| v3.4.2 tag \| prefix-SEMVER-timetamp \| juicebox-uvaprod-3.4.2-2017.03.22.055218 \| +—————-+————————————-+—————————————————————-+ \| develop Branch \| prefix-dev-GITVERSION-timestamp \| juicebox-uvaprod-dev-3.4.2-8-g9f28f1a-2017.03.22.055218 \| +—————-+————————————-+—————————————————————-+ \| release Branch \| prefix-release-GITVERSION-timestamp \| juicebox-uvaprod-release-3.4.2-8-g9f28f1a-2017.03.22.055218 \| +—————-+————————————-+—————————————————————-+ \| master Branch \| prefix-stable-GITVERSION-timestamp \| juicebox-uvaprod-stable-3.4.2-8-g9f28f1a-2017.03.22.055218 \| +—————-+————————————-+—————————————————————-+ \| other Branches \| prefix-test-BRANCH-timestamp \| juiebox-uvaprod-test-feature\_JB-1158-dev-ami-2017.03.16.101002 \| +—————-+————————————-+—————————————————————-+

## Building the AMIs

The ENV argument is required for building non-HIPAA AMIs.

To build a UVA AMI:

To build a Blueprint AMI:

```text
$ make ami ENV=blueprintdev
```

_broken / testing needed_ To build a HIPAA-compliant AMI, we have:

## Consuming

These AMIs can be consumed by Terraform’s `aws_ami` data source and used to launch single instances or auto-scaling groups.

