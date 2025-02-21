---
title: Usar CAS
redirect_from:
  - /enterprise/admin/articles/configuring-cas-authentication
  - /enterprise/admin/articles/about-cas-authentication
  - /enterprise/admin/user-management/using-cas
  - /enterprise/admin/authentication/using-cas
  - /admin/authentication/using-cas
  - /enterprise/admin/authentication/authenticating-users-for-your-github-enterprise-server-instance/using-cas
  - /admin/identity-and-access-management/authenticating-users-for-your-github-enterprise-server-instance/using-cas
intro: 'If you use Central Authentication Service (CAS) to centralize access to multiple web applications, you can integrate {% data variables.product.product_name %} by configuring CAS authentication for your instance.'
versions:
  ghes: '*'
type: how_to
topics:
  - Accounts
  - Authentication
  - Enterprise
  - Identity
  - SSO
---

## About CAS authentication for {% data variables.product.product_name %}

CAS is a single sign-on (SSO) protocol that centralizes authentication to multiple web applications. For more information, see "[Central Authentication Service](https://en.wikipedia.org/wiki/Central_Authentication_Service)" on Wikipedia.

After you configure CAS, people who use {% data variables.product.product_location %} must use a personal access token to authenticate API or Git requests over HTTP(S). CAS credentials cannot be used to authenticate these requests. Para obter mais informações, consulte "[Criando um token de acesso pessoal](/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)."

If you configure CAS, people with accounts on your identity provider (IdP) do not consume a user license until the person signs into {% data variables.product.product_location %}.

{% data reusables.enterprise_user_management.built-in-authentication %}

## Considerações de nome de usuário no CAS

{% data reusables.enterprise_user_management.consider-usernames-for-external-authentication %} For more information, see "[Username considerations for external authentication](/admin/identity-and-access-management/managing-iam-for-your-enterprise/username-considerations-for-external-authentication)."

## Atributos CAS

Os atributos a seguir estão disponíveis.

| Nome do atributo  | Tipo        | Descrição                                                              |
| ----------------- | ----------- | ---------------------------------------------------------------------- |
| `nome de usuário` | Obrigatório | Nome do usuário no {% data variables.product.prodname_ghe_server %}. |

## Configurar o CAS

{% data reusables.enterprise_site_admin_settings.access-settings %}
{% data reusables.enterprise_site_admin_settings.management-console %}
{% data reusables.enterprise_management_console.authentication %}
3. Selecione **CAS**.

   ![Screenshot of selection of CAS for authentication](/assets/images/enterprise/management-console/cas-select.png)
4. {% data reusables.enterprise_user_management.built-in-authentication-option %}

   ![Screenshot of of fallback built-in authentication option for CAS](/assets/images/enterprise/management-console/cas-built-in-authentication.png)
5. No campo **Server URL** (URL do servidor), digite a URL completa do seu servidor CAS. Se o servidor CAS usar um certificado que não pode ser validado pelo {% data variables.product.prodname_ghe_server %}, você poderá usar o comando `ghe-ssl-ca-certificate-install` para instalá-lo como certificado confiável. Para obter mais informações, consulte "[Utilitários de linha de comando](/admin/configuration/configuring-your-enterprise/command-line-utilities#ghe-ssl-ca-certificate-install)".
