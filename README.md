# aws-alb-okta-oidc-example
This cloudformation template will create a full stack example of OIDC Authentication on an AWS ALB.

Resources created include alb, listener rules with authenticate-oidc, lambdas, dns, ssl cert, vpc, subnets, gateways, security groups and of course iam roles.

# AWS Docs
* https://docs.aws.amazon.com/elasticloadbalancing/latest/application/listener-authenticate-users.html#configure-user-authentication
* https://docs.aws.amazon.com/elasticloadbalancing/latest/APIReference/API_AuthenticateOidcActionConfig.html

# Pre-Reqs
* Okta Org (configured with domain auth.mydomain.com in this example)
* Okta Application created (with optional custom auth server)
* Logout functionality requires trusted origin configuration
* Domains correctly configured in aws route 53 zone

# Core Functionality
* Protected & Public Routes
  * Authenticate-oidc configured per ListenerRule / path
  * Different routes can request different scopes
  * Different routes can use different OIDC configurations
* Redirect Based Authentication Flow
* Displays ALB token header values
* ALB (clear cookie) & Okta Logout
  
# Logout Functionality NOTICE
* Due to the fact that you cannot easily use cloudformation parameter values within inlined lambdas - the location header redirect value must be updated to reference your okta domain
  
# Convenience Functionality
* Handle HTTP to HTTPS redirect at ALB level
* 404 handler

# Cloudformation Required Parameters
| Name  | Default / Example | Description |
| ------------- | ------------- | ------------- |
| OktaClientId  | 0oataz9r87sgKiSpn697 | OIDC Client ID |
| OktaClientSecret  | hh4DNQUebSQOkmyPTaZpNDHBitM3J5qFG2Aao-CrmqI7XIVD4EHhmBkNMlgjODPt | OIDC Client Secret |
| OidcOktaDomain  | auth.mydomain.com | Your Okta domain or custom domain e.g. dev-23503294.okta.com |
| OidcOktaAuthServerId  | 0oataz9r87sgKiSpn697 | ID Value for Okta Auth Server. If you are using a custom authorization server use the identifier e.g. 'ausakx45dmHwzI9D3697', otherwise use 'default' |
| RecordName  | alb.aws.mydomain.com | Domain for the ALB |
| HostedZoneId  | Z03265102AV3N4S6IPRL3 | The ID of the Route53 hosted zone for your subdomain |

# AWS Services
<img width="1242" height="1582" alt="Image" src="https://github.com/user-attachments/assets/8991e67d-d2cf-4572-b513-4a8f2717d201" />

# Screenshot - Home
<img width="842" height="1354" alt="Image" src="https://github.com/user-attachments/assets/ce2be4a4-5120-4977-b05f-eb74851a37bd" />

# Screenshot - Profile
<img width="942" height="1221" alt="Image" src="https://github.com/user-attachments/assets/c455cb4d-8959-4193-ac28-9c079081a52d" />

# Screenshot - Admin
<img width="942" height="1323" alt="Image" src="https://github.com/user-attachments/assets/205d324d-2716-44ef-9a99-b87965aa0c79" />

# Screenshot - Reports
<img width="922" height="1249" alt="Image" src="https://github.com/user-attachments/assets/b48e2fed-0cd2-406e-a7bf-66ca8b2177ca" />
