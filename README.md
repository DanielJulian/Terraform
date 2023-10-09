# Terraform Course
https://www.youtube.com/watch?v=7xngnjfIlK4&ab_channel=DevOpsDirective

Terraform is a tool to manage infraestructure as code(IaC).
It allows to build, change and version infraestructure safely and efficiently.

Categories of IaC:
1- Ad hoc script: A shell script that calls amazon to create some EC2 instances.
2- Config management tools (Chef, ansible, etc): They allow to manage the software and config that is running,
most well suited for on prem setups.
3- Server templating tools
4- Orchestration tools: Like kubernetes for orchestrating containers.
5- Provisioning tools: Allows to manage the infrastructure that the software will be deployed on.


Declarative vs imperative:
Declarative Tools: you declare the end state of what you want. The tool figures out what it needs to do to reach that state.
Imperative: You tell the system exactly what you want to happen step by step.

Terraform is mostly declarative.

Terraform is cloud agnostic: It can work with any cloud or anything that provides an API.


## 

Terraform architecture:
Terraform Core: Its the engine that takes two inputs:
- A Terraform Config file 
- The Terraform current State
Then the terraform core figures out how to interact with the configured cloud provider in order to map the configuration into the current state.


We can store the state (a.k.a backend) locally or remotelly

99% of the time in real world projects, the state is stored remotelly either in terraform, or an S3 bucket, etc.
because it allows colaboratelly work, and you can automate pipelines to run terraform init, plan and apply automatically with git hooks. Also, since the state file contains passwords and sensitive data, its better if its stored remotely and not in local machines.
