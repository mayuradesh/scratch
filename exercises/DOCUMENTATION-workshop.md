# Documenatation Workshop 

## Overview
This is a trial workshop session to assist us in understanding the guidlines for writting mosip-related document.

### Types of documents

 _Admin Portal_


Using the admin portal, the administrator can now retrieve an individual's lost rid or misplaced rid. Using the admin portal, the *admin* can now control the levels of location hierarchy they require while creating the registration centres. The level of the hierarchy can be configured through configuration property value.
Using the admin portal, the administrator can now map the users to a registration centre and to a zone
Using the Admin portal, the administrator can now create and update dynamic fields such as **Gender**, **Blood Type**, **Residence Status**, **Marital Status** etc.Using the admin portal, the administrator can now configure the number of kiosks in a particular reg centre during the process of creating the registration centre.

_Setting up Registration client_ 


Step-1. Download TPM utility and run to get machine keys. Find the instructions to check out, build and run the utilities here.

Step-2. Whitelist the machine keys in server db. Machine name and keys output from utility should be updated in server.

**Use the below api to create / whitelist your machine**
curl -X POST "https://<HOSTNAME>/v1/masterdata/machine

**NOTE** : 
-> Replace appropriate HOSTNAME in the above curl command
-> In case, we are trying to whitelist NON-TPM machine, Please set publicKey and signPublicKey with same value 

step-3: Know your userid and required roles.
  Create the user in the keycloak.

Map the user to same center as that of the machine that is created/whitelisted in Step-2.

Either one of these roles must be assigned to the user in keycloak - "REGISTRATION_Supervisor, "Reg_OFFICER"
  
Step-4. Download registration client and start reg-client
Registration client package can be downloaded from below URL, if env is setup with mosip standard deployment.
  