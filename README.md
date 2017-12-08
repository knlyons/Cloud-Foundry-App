# Cloud Foundry application sample 

An [IBM Cloud Schematics](https://console.bluemix.net/docs/services/schematics/index.html) template to provision and manage a Cloud Foundry application. In addition to the Terraform configuration files, this template includes the source code for a sample application. The source code is pushed to IBM Cloud during deployment (i.e. if you trigger **Apply** in Schematics). See the Next Steps section for deployment information.

To use this template in a scenario where the source code of the application is updated regularly and re-deployed to the cloud, you should fork the repository or create your own Git repo using the Terraform configuration files as an example.

## Variables used in this template 

The following variables are used to customize the template. 

| Variable Name | Description | Default Value |
|---------------|-------------|---------------|
|ibm_cloud_apikey|Your IBM Cloud API key. You can get the value by running `bx iam api-key-create <key name>`.| - |
|ibm_cloud_organization|Your IBM Cloud org name.| - |
|ibm_cloud_space|Your IBM Cloud space name.| - |
|application_hostname|The hostname for the application's route. The resulting URL will be `<hostname>.mybluemix.net`. NOTE: This value must be unique across IBM Cloud. When you set a generic name, such as `test`, you are likely to encounter an error during deployment. You then have to change the variable and trigger the **Apply** again.| - |
|application_version|Version specification of the application. Changing this parameter indicates to Terraform that the application code has changed and needs to be redeployed.|`100`|
|application_instances|The number of Cloud Foundry application instances that you want to deploy.|`1`|

## Next steps

After setting up your environment with this template, you can run **Plan** to preview how Schematics will deploy resources (in this case, a Cloud Foundry application) to your environment. When you are ready to deploy the app, run **Apply**.

After a successful deployment, you can access the application using the provided hostname: `https:\\<hostname>.mybluemix.net`. The exact hostname is also written to the Terraform log for reference.  
