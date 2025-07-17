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

# Screenshot - Home
<img width="842" height="1354" alt="Image" src="https://github.com/user-attachments/assets/ce2be4a4-5120-4977-b05f-eb74851a37bd" />

# Screenshot - Profile
<img width="942" height="1221" alt="Image" src="https://github.com/user-attachments/assets/c455cb4d-8959-4193-ac28-9c079081a52d" />

# Screenshot - Admin
<img width="942" height="1323" alt="Image" src="https://github.com/user-attachments/assets/205d324d-2716-44ef-9a99-b87965aa0c79" />

# Screenshot - Reports
<img width="922" height="1249" alt="Image" src="https://github.com/user-attachments/assets/b48e2fed-0cd2-406e-a7bf-66ca8b2177ca" />
