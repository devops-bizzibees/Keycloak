# Keycloak and WordPress Integration Project

Overview
This project demonstrates an end-to-end integration between Keycloak as an identity provider and WordPress for authentication management. It also covers setting up PostgreSQL on AWS Marketplace as the backend for Keycloak, emphasizing how to manage user roles effectively across platforms and streamline the login process with Single Sign-On (SSO) functionality. The project showcases DevOps skills in identity management, role-based access control, and AWS Marketplace infrastructure setup.

Key Objectives
Implement Single Sign-On (SSO) Authentication in WordPress Using Keycloak : 
Centralize user authentication for WordPress via Keycloak to allow users to log in through a unified Keycloak interface, which enhances security and ease of management.

Role-Based Access Control (RBAC) with Keycloak and WordPress :
Manage and map user roles between Keycloak and WordPress to ensure appropriate access control. This provides a seamless and consistent role-based experience for users across applications.

Deploy Keycloak with PostgreSQL on AWS Marketplace :
Deploy Keycloak using AWS Marketplace with PostgreSQL as its primary storage backend to support high availability and scale securely within the AWS infrastructure.


**Detailed Setup and Configuration Steps**
**Step 1: Configuring Keycloak as an Identity Provider for WordPress**
Install and Configure Keycloak Plugin in WordPress

In WordPress, installed a Keycloak authentication plugin (such as "Keycloak SSO" or similar) to enable SSO.
Configured the plugin by adding the Keycloak server details (including the Keycloak base URL, client ID, and client secret).
Enabled the OpenID Connect (OIDC) protocol in WordPress settings to establish secure token-based authentication.
Set Up Keycloak Client for WordPress

In Keycloak, created a new client for WordPress with configurations to allow SSO. Key configurations included:
Client ID: A unique identifier for WordPress in Keycloak.
Redirect URI: Set to point back to WordPress, allowing for token exchange post-authentication.
Scopes and Protocols: Configured to use OpenID Connect for secure authentication.
Ensured that the Client Authentication and Authorization settings aligned with WordPress, allowing the smooth exchange of tokens between WordPress and Keycloak.
Testing and Verifying Login through Keycloak

Tested user authentication by attempting a login from the WordPress interface. The login flow redirects the user to the Keycloak interface, allowing login through Keycloak.
Verified the token exchange, ensuring that authenticated users are redirected back to WordPress with correct session tokens.
**Step 2: Role Management in Keycloak and WordPress Mapping**
Create and Configure Roles in Keycloak

Defined custom roles within Keycloak, such as Editor, Author, and Admin, that mirror the WordPress role hierarchy.
Assigned permissions to each role in Keycloak, enabling granular control over user actions within the WordPress site.
Map Keycloak Roles to WordPress Roles

In WordPress, configured role mapping by updating the Keycloak client’s role mapper settings:
Role Mapper Configuration: Enabled the role mapper feature to pass Keycloak roles to WordPress during login.
Role Transformation: Configured Keycloak roles to automatically align with WordPress roles, allowing dynamic assignment of permissions based on Keycloak roles.
Tested role mapping by logging in with different user roles in Keycloak and verifying their respective permissions in WordPress.
Syncing Roles Across Systems

Configured periodic role synchronization between Keycloak and WordPress to ensure that any role updates in Keycloak immediately reflect in WordPress. Implemented regular audits of role permissions to verify alignment between Keycloak and WordPress, ensuring consistent and secure access management.



