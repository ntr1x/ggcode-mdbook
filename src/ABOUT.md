# About

GGCode is a template-based and framework agnostic source code generation tool. It is written in Rust and created by developers for developers. It is inspired by Terraform and Helm, but not limited to clouds and Kubernetes.

It is primarily a code and configuration generation tool, regardless of how you intend to utilize the resulting code and configurations. With GGCode, you can generate various elements such as your code, Kubernetes manifests, Compose descriptors, Ansible playbooks, Helm charts, etc. We use it to distribute and standardize our configuration patterns across tens of our projects.

GGcode project consists of two aspects:
- `ggcode` command-line applicaiton
- a set of community-driven config repositories