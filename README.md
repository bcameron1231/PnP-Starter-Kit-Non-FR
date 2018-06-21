
# PnP SharePoint Starter Kit for Standard Release Tenants
This is a clone of the PnP-Starter-Kit. This repo will not be maintained nor will I make any new contributions, but will allow you play around with the PnP Starter Kit features (some of them), without having to configure First Release for everyone. This should not be used in your production environments.

It will provision all of the non-FR functionality of the pnp-starter-kit. It doesn't have Personal Web Parts, DiscussNow, LOB Application, Azure Functions, API Management Requirements. 

## Pre-requirements (Copied from original repo)

Here are current pre-requirements for making this solution work in your tenant.

- You will need to be a tenant administrator to be able to deploy this solution
    - Notice that you can get free developer tenant from [Office 365 developer program](https://developer.microsoft.com/en-us/office/dev-program), if needed.
- Automatic end-to-end provisioning only works with English tenants
    - All solutions and web parts are also English in the current implementation
- Add used tenant administrator account as Term Store Administrator in the Taxonomy Term Store

- Ensure that you meet the [requirements for SharePoint Framework development](https://docs.microsoft.com/en-us/sharepoint/dev/spfx/set-up-your-development-environment) and are using the latest version of [PnP PowerShell](https://docs.microsoft.com/en-us/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps)
- Upload and deploy the [`sharepoint-starter-kit.sppkg`](./package/sharepoint-starter-kit.sppkg) from the [`/package`](./package) folder to your app catalog
- Use PnP PowerShell to connect to any site in your tenant with the [`Connect-PnPOnline` cmdlet](https://docs.microsoft.com/en-us/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps)
- Move to the `provisioning` folder and execute the following command (using your own tenant url and the prefix of your choosing): `.\deploy.ps1 -TenantUrl https://contosodemosk.sharepoint.com -SitePrefix demo`
    - This will provision 3 site collections with urls of `/sites/demoportal`, `/sites/demohr`, and `/sites/demomarketing`. Your urls may vary depending on the SitePrefix you use.

> Notice that this script also adds tenant level settings like themes, site designs, taxonomy term sets, and other adjustments. Therefore, it is recommended to test the script in an isolated test tenant and not immediately execute it within your production environment.

## Deploy Just Web Parts
If you are not first release for everyone, you can still deploy just the webparts by uploading the .sppkg file to the app catalog.


# Finally
I will re-iterate, this isn't my source code. It was used from the PnP-Starter-Kit in the SharePoint repo. I will not maintain this code, and it should only be deployed into test tenants. However, i have stripped out the webparts (personals,discussnow, lob, API management) from the solution. It will still deploy the demo sites and configure the pages with the webparts on it.
