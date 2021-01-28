APIX.Hub Installation from AWS Marketplace
===

APIX.Hub is deployed via CloudFormation template.

The following information is requested in parameters:

			ADServerAddress: "This setting is the address (IP, DNS Name, or URL) for the LDAP server of your organization. For example ldaps://ldap.company.com:636"
			ADUseSSL: "This setting allows for enabling SSL for the LDAP connection to your server's organization. Default is true."
			SuperUserEMAIL: "This is the email of the user which already exists in your organization's AD. This user will be configured as an administrator in APIX.Hub"
			SuperUserFirstName: "This is the FirstName of the user which already exists in your organization's AD. This user will be configured as an administrator in APIX.Hub"
			SuperUserLastName: "This is the LastName of the user who already exists in your organization's AD. This user will be configured as an administrator in APIX.Hub"
			ADSearchRoot: "This is the node in the Active Directory Domain Services hierarchy where the search starts. For example 'DC=company,DC=com'"
			ADServiceAccountUserDN: "APIX.Hub needs a service account to connect to the organization's active directory. This is the username for that service account. For example 'jsmith' or 'CN=JSmith,OU=Sales,DC=Fabrikam,DC=COM'"
			ADServiceAccountPassword: "APIX.Hub needs a service account to connect to the organization's active directory. This is the password for that service account. "
			InstanceType: EC2 instance type used by APIX.Hub


The template needs to acknowledge that AWS CloudFormation might create IAM resources with custom names.
When the template is deployed, in Outputs can be seen APIXHubHost URL.

Accessing APIX.Hub
===

Open APIXHubHost URL in your browser. URL can be found in CloudFormation outputs.

To log in use username/password combination for a user available in LDAP. 

To login as an administrator, please use username specified in parameters as SuperUserEMAIL. Password will be validated via LDAP.

To connect to the EC2 use AWS Systems Manager.

