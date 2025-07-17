# aws-alb-okta-oidc-example
This cloudformation template will create a full stack example of OIDC Authentication on an AWS ALB.

Resources created include subdomain dns, ssl cert, alb, and route handling lambdas.

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
  
# Convenience Functionality
* Handle HTTP to HTTPS redirect at ALB level
* 404 handler

# Screenshot
<img width="841" height="919" alt="Preview Image" src="https://github.com/user-attachments/assets/b47af331-9bdc-4fe7-817b-0c258ad85630" />
