# Security Hardened Image with Packer, Terraform, and STIGs

This repository contains the files and instructions for creating a security hardened image for a Linux server using Packer, Terraform, and STIGs (Security Technical Implementation Guides).

## Prerequisites

- [Packer](https://www.packer.io/)
- [Terraform](https://www.terraform.io/)
- A configuration management tool (such as ansible, chef, or puppet)

## How to Use

1. Clone this repository
2. Review the `packer.json` file and customize it to suit your needs. This file specifies the base image to use, the packages and security settings to be installed, and the configuration management tool to use.
3. Run `packer build packer.json` to build the image.
4. Once the image is built, use Terraform to create a new instance based on the image. Review the `main.tf` file and customize it to suit your needs.
5. Run `terraform apply` to create the instance.

## Layers

To ensure that the image is compliant with STIGs, it is recommended to use a layered approach. This means that you should separate your security hardening configuration into multiple layers, each of which addresses a specific set of requirements. For example, you might have one layer that configures the firewall, another layer that installs security updates, and another layer that configures access controls. By separating the configuration into layers, you can more easily maintain and update the image.

## Tips

- Use a configuration management tool to automate the configuration of your image. This will make it easier to maintain and update the image over time.
- Test the image thoroughly before deploying it to production. This will help ensure that the image meets your security requirements and does not have any unintended consequences.
- Keep the image up-to-date by regularly applying security updates and re-building the image.
