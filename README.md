# NGINX VM
This example shows how to run a shell script in IBM Compute VM Instance to Install Nginx using terraform. 

# Generic IBM Cloud Service Template

An [IBM Cloud Schematics](https://cloud.ibm.com/docs/services/schematics/) template that allows creation of any of the available services in the IBM Cloud catalog.

Schematics uses [Terraform](https://www.terraform.io/) as the infrastructure as code engine. With this template, you can provision and manage infrastructure as a single unit.

See the [Terraform provider docs](https://ibm-cloud.github.io/tf-ibm-docs/) for available resources for the IBM Cloud.


## Create an environment with this template

Environments can be used to separate software components into development tiers (e.g. staging, QA, and production).

1. In IBM Cloud, go to the menu and select the [Schematics dashboard](https://cloud.ibm.com/docs/services/schematics).
2. In the left navigation menu, select **Templates** to access the template catalog.
3. Click **Create** on the `vm-remote-exec` template. You are taken to a configuration page where you can define metadata about your environment.
4. Define values for your [variables](#variables).
5. This template installs Nginx on the VM Instance. You can view the device details here on the dashboard https://cloud.ibm.com/resources.


## Variables

|Variable Name|Description|Default Value|
|-------------|-----------|-------------|
|softlayer-username|Your IBM Cloud Infrastructure (SoftLayer) user name| |
|softlayer-api-key|Your IBM Cloud Infrastructure (SoftLayer) API key| |
|ssh-key| The public key contents for the SSH keypair.| |
|private-key| The private key contents for the SSH keypair.| |
|ssh-label|An identifying label to assign to the SSH key|ssh_key_scale_group|
|datacenter|The data center for the local load balancer. You can run bluemix cs locations to see a list of all data centers in your region|wdc01|
|vm-hostname|Hostname for the computing instance|virtual-guest|
|vm-domain|Domain for the computing instance|example.com|
|vm-cores|The number of CPU cores to allocate|1|
|vm-memory|The amount of memory to allocate, expressed in MBs|4096|
|vm-os-reference-code|The operating system reference code that is used to provision the computing instance|CENTOS_7|
|vm-post-install-script-uri|The URI for the NGINX install script|https://raw.githubusercontent.com/Cloud-Schematics/vm-local-exec/master/nginx.sh|


## Next steps

After setting up your environment with this template, you can run **Plan** to preview how Schematics will deploy resources to your environment. When you are ready to deploy the cluster, run **Apply**.
