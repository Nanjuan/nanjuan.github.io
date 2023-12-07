---
layout: post
title:  "Snyk Automation Scripts"
categories: [Productivity, Tutorial]
authorMain: Nestor N Torres
tag: Snyk
description: This repo is where I'll be posting my Snyk automation scripts that can be used to automate tasks inside Snyk. These scripts are for the enterprise version of Snyk not the free version for now. 
---
 
<a id="Top"></a> 
### Contact
- [LinkedIn](https://www.linkedin.com/in/nanjuan/)
- Email: nestor@nntorres.com

### Table
1. [Summary](#Summary)
2. [Prerequisites](#preinfo)
3. [CreateNewOrg](#CreateNewOrg)
4. [getOrgList](#getOrgList)

## Summary <a id="Summary"></a> 
This repo is where I'll be posting my Snyk automation scripts that can be used to automate tasks inside Snyk. These scripts are for the enterprise version of Snyk not the free version for now.

[Top](#Top)

## Prerequisites <a id="preinfo"></a>
## Configuration Setup Instructions

1. **File Rename:**  
   Rename the `config-template.py` to `config.py`.

2. **Adding Credentials:**  
   Inside `config.py`, you'll need to add your `groupId`, `sourceOrgId`, and `Authorization` tokens.

    - **groupId**:  
      This is your group ID value. To find it:
        - Navigate to your main group.
        - Look at the URL: `https://app.snyk.io/group/{groupId}`. The `{groupId}` portion is your value.
      
    - **sourceOrgId**:  
      This represents the organization you'll use to clone all the configurations. It's a best practice when setting up Snyk to have a default organization with all your configurations in one place, making it easier to clone configurations to other organizations.
        - Go to the settings of your default organization.
        - Locate the "organization id". This will be the value for `sourceOrgId` in your `config.py` file.

    - **Authorization Token**:
        - Navigate to the bottom left side of the screen and click on your account.
        - Choose 'Account Settings'.
        - Under 'API Token', click 'click to show'. This reveals the token, which you'll use as the `Authorization` in your `config.py` file.

[Top](#Top)

<a id="CreateNewOrg"></a>

## CreateNewOrg.py
This script will take a list of organization names from a .csv file with one organization per line, as shown in the example file `organization-names.csv`. The script will then create new organizations in the group selected in the config file. For configuration details, refer to the config file section.

###### One thing to note: This API endpoint will be replaced with a REST API. I will update the script once the update is released. If there is interest and if this comment is still here, the new endpoint hasn't been released, and I haven't updated the script.

[Top](#Top)

<a id="getOrgList"></a> 

## getOrgList.py
This script will retrieve a list of all your organizations from your Snyk portal along with the slug for each organization. It will then create a .csv file with each entry on a separate line. This is useful for integrating Snyk with AD for custom role mapping, especially when adding new developers to SSO. This ensures they are automatically added to specific applications. Find more info here: [Snyk Custom Mapping](https://docs.snyk.io/enterprise-setup/using-single-sign-on-sso-for-authentication/custom-mapping-option).


#### Reference: 

https://snyk.docs.apiary.io/#
https://apidocs.snyk.io/?version=2023-11-27


