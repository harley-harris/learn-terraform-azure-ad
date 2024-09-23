## Learn Terraform Azure AD

This is a companion repository for the Hashicorp [Manage Azure Active Directory (AD) Users and Groups](https://developer.hashicorp.com/terraform/tutorials/it-saas/azure-ad) tutorial. 
It contains Terraform conifguration files for you to use to learn how to to manage Azure AD users and groups using
Terraform.

## How to deploy

### Configure the Azure CLI

You need a Microsoft Azure account with a tenant deployed. You can just use the default tenant that is deployed when you create a free Azure account.

Run:

```bash
$ az login
```

This redirects you to the browser so you can login to your Azure account and authenticate the session.

### Provision users/groups through Terraform

There are some dependency issues if the users haven't been deployed before trying to assign the group memberships. Haven't fixed it yet but a workaround is: 

```bash
$ terraform apply -target azuread_user.users # deploys only the users first
```

```bash
$ terraform apply # applies the groups and memberships
```