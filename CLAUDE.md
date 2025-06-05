# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Docker container project that builds a Terraform 1.12 development environment based on Debian with Fish shell. The container includes Terraform, tflint, and trivy for infrastructure-as-code development and security scanning.

## Common Commands

### Building Docker Images
- `make test.build.arm64` - Build ARM64 container image
- `make test.build.amd64` - Build AMD64 container image
- `make test` - Build and test both ARM64 and AMD64 images

### Testing
- `make test.arm64` - Build and clean up ARM64 image (for testing)
- `make test.amd64` - Build and clean up AMD64 image (for testing)

### Cleanup
- `make test.rmi.arm64` - Remove ARM64 image
- `make test.rmi.amd64` - Remove AMD64 image

## Architecture

The project consists of:
- **Dockerfile** (`docker/Dockerfile`): Multi-stage build that installs Terraform 1.12.*, tflint, and trivy on a Debian base with Fish shell
- **Makefile**: Provides cross-platform build targets for ARM64 and AMD64 architectures
- **Container Registry**: Images are tagged for `ghcr.io/bearfield/terraform:test.1.12`

## Container Details

The container includes:
- Base: `ghcr.io/bearfield/debian-fish:bookworm`
- Terraform version: 1.12.*
- Additional tools: tflint (Terraform linter), trivy (security scanner)
- Shell: Fish shell with Debian environment