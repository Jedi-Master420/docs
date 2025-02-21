---
title: Allowing built-in authentication for users outside your provider
intro: 'You can configure fallback authentication to allow built-in authentication for people who don''t have an account on your CAS, LDAP, or SAML authentication provider.'
redirect_from:
  - /enterprise/admin/user-management/allowing-built-in-authentication-for-users-outside-your-identity-provider
  - /enterprise/admin/authentication/allowing-built-in-authentication-for-users-outside-your-identity-provider
  - /admin/authentication/allowing-built-in-authentication-for-users-outside-your-identity-provider
  - /enterprise/admin/authentication/authenticating-users-for-your-github-enterprise-server-instance/allowing-built-in-authentication-for-users-outside-your-identity-provider
  - /admin/identity-and-access-management/authenticating-users-for-your-github-enterprise-server-instance/allowing-built-in-authentication-for-users-outside-your-identity-provider
versions:
  ghes: '*'
type: how_to
topics:
  - Accounts
  - Authentication
  - Enterprise
  - Identity
shortTitle: Fallback authentication
---

## About built-in authentication for users outside your provider

By default, when you enable external authentication for {% data variables.product.product_name %}, built-in authentication is disabled for your instance. For more information, see "[About authentication for your enterprise](/admin/identity-and-access-management/managing-iam-for-your-enterprise/about-authentication-for-your-enterprise#external-authentication)."

If you're unable to add specific accounts to your external authentication provider, such as accounts for contractors or machine users, you can configure fallback authentication. Fallback authentication allows built-in authentication for outside users and to access a fallback account if your authentication provider is unavailable.

If you configure built-in authentication and a person successfully authenticates with SAML or CAS, the person will no longer have the option to authenticate with a username and password. Se o usuário se autenticar com êxito via LDAP, as credenciais não serão mais consideradas internas.

{% warning %}

**Aviso:** se desabilitar a autenticação integrada, você terá que suspender individualmente todos os usuários que não devem mais ter acesso à instância. Para obter mais informações, consulte "[Suspender e cancelar a suspensão de usuários](/enterprise/{{ currentVersion }}/admin/guides/user-management/suspending-and-unsuspending-users)."

{% endwarning %}

## Configuring built-in authentication for users outside your provider

{% data reusables.enterprise_site_admin_settings.access-settings %}
{% data reusables.enterprise_site_admin_settings.management-console %}
{% data reusables.enterprise_management_console.authentication %}
4. Selecione seu provedor de identidade. ![Opção Select identity provider (Selecionar provedor de identidade)
](/assets/images/enterprise/management-console/identity-provider-select.gif)
5. Selecione **Allow creation of accounts with built-in authentication** (Permitir a criação de contas com autenticação integrada). ![Opção Select built-in authentication (Selecionar autenticação integrada)](/assets/images/enterprise/management-console/built-in-auth-identity-provider-select.png)
6. Leia o aviso e clique em **Ok**.

{% data reusables.enterprise_user_management.two_factor_auth_header %}
{% data reusables.enterprise_user_management.2fa_is_available %}

## Inviting users outside your provider to authenticate to your instance

Quando aceitar o convite, o usuário poderá fazer login com seu próprio nome de usuário e senha, em vez de fazer login via IdP.

{% data reusables.enterprise_site_admin_settings.sign-in %}
{% data reusables.enterprise_site_admin_settings.access-settings %}
{% data reusables.enterprise_site_admin_settings.invite-user-sidebar-tab %}
{% data reusables.enterprise_site_admin_settings.invite-user-reset-link %}

## Leia mais

- "[Using CAS for enterprise IAM](/admin/identity-and-access-management/using-cas-for-enterprise-iam)"
- "[Using LDAP for enterprise IAM](/admin/identity-and-access-management/using-ldap-for-enterprise-iam)"
- "[Using SAML for enterprise IAM](/admin/identity-and-access-management/using-saml-for-enterprise-iam)"
