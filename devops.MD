# Introduction
At The Startup Factory, we thrive to help small-scale developments which can be engaged to valid business hypotheses and used to make effective decisions.

Our processes are designed to be simple, repeatable and based upon open tools we have practical experience with and know well. We have the appetite and the motivation to try new things, being at the cutting edge so that your ideas don’t lose impact with the best technology. These guidelines are a starting point serving to fulfil the former need, but still allowing us to pursue the latter - technology choices are not as fixed as the core approaches are.

# We value deployments that are
* Automated
  * _Codifying_ processes as code that can be run and stored in version control

* Parameterised
  * Exposing configuration as variables which can be alter per environment

* Reproducible
  * Avoiding side effects, adhoc processes, or unmanaged state

* Immutable
  * Containerising and keeping the images in a well-known state

# Cloud providers
Our solutions can be cloud-agnostic but we prefer AWS and have been using it before it became fashionable. We also use other platforms such as Heroku for quick proofs-of-concept tii.

# Version control
Everything involved in getting software deployed should be codified - that is, expressed through code, and version controlled - and undergo the well-fashioned review processes from peers. Processes shouldn’t depend upon individuals, and information shouldn't be siloed.

# Containers
We use Docker to construct reproducible and immutable environments. Each software component should be capable of producing a Docker image as part of its build, and configuration parameters for those components should be exposed as environment variables.

# Infrastructure
AWS uses Cloud Formation to describe deployment infrastructure but Cloud Formation templates become unwieldy as the size of a project grows. To make this managable, we use Troposphere to generate these templates.

# Provisioning
Whereas infrastructure concerns machines and networks, provisioning is about what runs on those machines.

Packer from Hashicorp is a tool for building machine images from configuration files. It can output AMIs for importing into AWS and it’s also compatible with Virtualbox, Docker, Google Compute Engine and Azure.

We prefer Ansible as a provisioner and Packer for generating machine images for various architectures.

# Security
We treat private keys *very* carefully: we don’t email them, or send them over IM, or commit them to version control. We don’t share private keys at all (it’s in the name!).

We think carefully about public network access to various systems and seek to minimise attack surfaces through IP whitelisting and selective port-forwarding, etc.

# Builds
Software should be built on and deployable continuously. We use Jenkins and it builds feature branches so that merging incorrect code is avoided.

# Tests
The application will test the business ideas, and we ensure that the infrastructure is tested properly too.
