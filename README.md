# Terraform Provider Sources

This repo contains Terraform configuration that includes terraform block with required_providers, where the version and source are specified for the **random** provider.

# Purpose of required_providers

With the release of Terraform v.0.13 they have changed the way Terraform downloads and install the providers used in the configuration. Now you can download the needed providers automatically by using the command `terraform init` if they are stored in the official terraform [registry](https://registry.terraform.io/). If your project needs specific providers, you can use `required_providers` and specify your version and source for the providers. You can read more [here](https://www.terraform.io/language/providers/requirements#requiring-providers)

## If you need you can use a custom local stored providers:

There are 2 default layouts of providers stored locally:

- Packed layout - the distribution is a zip file obtained from the provider’s origin registry:
```
HOSTNAME/NAMESPACE/TYPE/terraform-provider-TYPE_VERSION_TARGET.zip
```

- Unpacked layout - a directory containing the result of extracting the provider’s distribution zip file.: 
```
HOSTNAME/NAMESPACE/TYPE/VERSION/TARGET 
```

The sample in the repo uses **random** provider that is downloaded from the official hashicorp namespace registry. 

# Prerequisite
You need to have [Terraform CLI >0.13](https://learn.hashicorp.com/tutorials/terraform/install-cli) installed on you workstation. 

# How to use the repo

* Clone this repo locally to a folder of your choice
```
git clone https://github.com/51r/terraform-provider-sources.git
```

* Make sure you are in the main directory of the repo:
```
cd terraform-provider-sources
```

* initialize Terraform to download the required providers.
```
terraform init
```

* Check the plan in order to see the changes which terraform is going to made.
```
terraform plan
```

* Apply the plan which terraform is going to execute based on our configuration (main.tf)
```
terraform apply
```


