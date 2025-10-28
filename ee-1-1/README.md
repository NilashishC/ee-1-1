# Ansible Execution Environment Definition

This directory contains the definition files for an Ansible Execution Environment Definition.

## Files Generated

- `execution-environment.yml` - Main EE definition file
- `requirements.yml` - Ansible Galaxy collection requirements


## Configuration

### Base Image
- **Base Image**: `registry.redhat.io/ansible-automation-platform-25/ee-minimal-rhel9:latest`

### Ansible Collections (2)
- `community.crypto`
- `google.cloud`

## Building the Execution Environment

To build this Execution Environment Definition, run:

```bash
ansible-builder build -t ee-1-1:latest -f execution-environment.yml --container-runtime podman
```

## Prerequisites

- [ansible-builder](https://ansible-builder.readthedocs.io/) installed
- Container runtime (Podman or Docker)

## Usage

Once built, you can use this Execution Environment with:

```bash
# Run with ansible-navigator
ansible-navigator run playbook.yml --execution-environment-image ee-1-1:latest

# Or with ansible-runner
ansible-runner run . -p playbook.yml --container-imageee-1-1:latest
```

## Customization

You can modify the `ee-1-1.yaml` file to add additional dependencies or build steps as needed.
