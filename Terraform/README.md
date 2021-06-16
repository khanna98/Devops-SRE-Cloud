# Getting Started with Terraform

## Tldr;

We need to have some basic knowledge of the IAC and some concepts before starting the hands on exercise.
We have:

- IAC and its definition
- Core Concepts of IAC
- Benefits of using IAC

### IAC - Infrastructure as code - Definition

Provisioning infra throught s/w to achieve consistent and predictable env.

**Core Concepts** -

1. Defined in code - hashicorp terraform
2. Stored in version source control - github
3. Declaritve and Imperative
   - Make a taco - **_Imperative_** - we need to give exact information and in a correct order for the s/w to make a taco. Like give ingredients, tell the process step by step.
   - Make a taco - **_Declaritive_** - It already has a predefined routine to get the ingredients and how to assemble them. Like we just need to create a func and add ingredients.
4. Idempotent and consistent
   - **_Idempotent_** - If a same instruction is given and the state of the world we want, we do nothing. If someones asks for a taco and we give them but then they again ask for it, so we just say that you already have a taco.
   - **_Non-idempotent_** - Everytime an instruction is given we do what is being said.
   - terraform attempts to be idempotent in a way like if we haven't changed anything about the config and we apply it to the same env, nothing will change in env coz the config matches with the reality of the infra it exists.
5. Push or Pull
   - **_Push_** - if someone asks for a taco, we will give it to them and push it.
   - **_Pull_** - if someone needs a thing, they'd just take it from us.

**Benefits of using IAC**

- Automated Deployments
- Consistent Environment
- Repeatable Process
- Reusable Components (follows DRY)
- Documented architecture

## Hands on Demo

We'll be making a basic config using terraform for a real world scenario.

### Automating Infrastructure Deployments

It is build on several key concepts like:

1. Provisioning Resources _(using terraform)_
2. Planning Updates
3. Using Source Control
4. Resuing templates

### Terraform Components

1. Terraform executable - It is self-contained, written in Go.
2. Terraform files - This file will contain our config changes. If terraform sees 1/more such files in a directory, it stiches config based on the content of the files.
3. Terraform Plugins - These help in communication with providers like AWS, GCP etc.
4. Terraform State - contains current state of the config within it. On updating the env, terraform compares the config with the state and sees if the changes are there and need to be deployed.