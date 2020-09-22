# Sistema

{% api-method method="put" host="https://dev-api.xekout.app" path="/v1/admin/apps/paypal/:subdomain" %}
{% api-method-summary %}
Salvar credenciais do PayPal
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="subdomain" required=true %}
Subdomain da loja cadastrada na Xekout.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Prefix" %}
Bearer Token JWT para autenticação.
{% endapi-method-parameter %}

{% api-method-parameter name="Authentication" required=true %}
Usado na construção de uma chave para armazenamento de token em todos os provedores de armazenamento.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="email" type="string" required=true %}
Email de cadastro da conta do PayPal.
{% endapi-method-parameter %}

{% api-method-parameter name="account" type="string" required=true %}
Email cadastrado no app _Account_ no aplicativo do PayPal.
{% endapi-method-parameter %}

{% api-method-parameter name="client\_id" type="string" required=true %}
Cliente ID gerado para o aplicativo do PayPal.
{% endapi-method-parameter %}

{% api-method-parameter name="secret\_id" type="string" required=true %}
Segredo ID gerado para o aplicativo do PayPal.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "status": "success",
  "code": 200004,
  "message": "Gateway PayPal update successfuly"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 404013,
  "message": "Tenant not found"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

