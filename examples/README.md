# Example Workflows

This directory contains example workflows demonstrating different use cases for the HCP Packer Promote to Channel Action.

## Examples

### [basic-promotion.yml](basic-promotion.yml)
Simple manual promotion workflow triggered via `workflow_dispatch`. Perfect for one-off promotions or testing.

**Use case**: Manual promotion of a specific iteration to a channel

### [build-and-promote.yml](build-and-promote.yml)
Complete CI/CD pipeline that builds a Packer image and automatically promotes it to a staging channel.

**Use case**: Automated build and promotion workflow

### [multi-channel-promotion.yml](multi-channel-promotion.yml)
Promotes an iteration to multiple channels (staging, then optionally production) with verification steps.

**Use case**: Multi-stage promotion with approval gates

### [conditional-promotion.yml](conditional-promotion.yml)
Automatically determines the target channel based on the branch being pushed to.

**Use case**: Branch-based promotion strategy

## Usage

Copy the example workflow that matches your use case to `.github/workflows/` in your repository and customize as needed.

## Prerequisites

All examples require:
- HCP Packer organization and bucket configured
- OIDC workload identity federation configured
- GitHub secret `HCP_CRED_FILE` containing the credential file JSON
- Workflow permissions: `id-token: write` and `contents: read`

## Customization

- Replace `my-bucket` with your actual HCP Packer bucket name
- Update channel names to match your channel structure
- Adjust HCP CLI version if needed
- Modify iteration ID retrieval logic based on your workflow

