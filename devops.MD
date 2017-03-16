# Introduction
At The Startup Factory we are primarily interested in small-scale developments that are meant to test business hypotheses.

Our processes should be simple, easy to repeat and based upon tools we know well. On the other hand, we have the appetite and the motivation to try new things so that we don’t behind on technology. These guidelines are a starting point serving to fulfil the former need, but still allowing us to pursue the latter (i.e. technology choices are not as fixed as the core approaches are).

# We value deployments that are
* Automated
+ By codifying processes as executable code stored in version control

* Parameterised
+ By exposing configuration as environment variables

* Reproducible
+ By avoiding side effects, non-codified processes, and unmanaged state

* Immutable
+ By containerisation

# Cloud providers
We prefer AWS but might use Heroku for quick proofs-of-concept.

# Version control
Everything involved in getting software deployed should be codified - that is, expressed through code, and version controlled - and undergo the usual review processes. Processes shouldn’t depend upon individuals.

# Containers
We use Docker to construct reproducible and immutable environments. Each software component should be capable of producing a Docker image as part of its build, and configuration parameters for those components should be exposed as environment variables.

# Infrastructure
AWS uses Cloud Formation to describe deployment infrastructure but Cloud Formation templates become unwieldy as the size of a project grows. We use Troposphere to generate these templates.

# Provisioning
Whereas infrastructure concerns machines and networks, provisioning is about what runs on those machines.

Packer from Hashicorp is a tool for building machine images from configuration files. It can output AMIs for importing into AWS and it’s also compatible with Virtualbox, Docker, Google Compute Engine and Azure.

We prefer Ansible as a provisioner and Packer for generating machine images for various architectures.

# Security
We treat private keys *very* carefully: we don’t email them, or send them over IM, or commit them to version control. We don’t share private keys at all (it’s in the name!).

We think carefully about public network access to various systems and seek to minimise attack surfaces through IP whitelisting and selective port-forwarding, etc.

# Builds
Software should be built on and deployable through Jenkins. Jenkins should also build feature branches so that we don’t risk merging broken code into a deployment branch.
