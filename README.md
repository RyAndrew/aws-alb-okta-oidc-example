# aws-alb-okta-oidc-example
This cloudformation template will create a domain, ssl cert, alb, and some lambdas
It is a simple demo of an aws alb with okta oidc authentication

# Pre-Reqs
* Okta Org (configured for domain auth.mydomain.com)
* Custom Auth Server (or use /default)
* Domains correctly configured in aws

# Functionality
* Protected & Public Routes
* Redirect Based Login
* Displays ALB token header values
* ALB & Okta Logout

# Screenshot
<img width="841" height="919" alt="Preview Image" src="https://github.com/user-attachments/assets/b47af331-9bdc-4fe7-817b-0c258ad85630" />
