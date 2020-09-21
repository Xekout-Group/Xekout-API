# Salvar credenciais salvas do AppMax

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/admin/apps/appmax/:subdomain" %}
{% api-method-summary %}
Salvar credenciais do AppMax
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
{% api-method-parameter name="token\_production" type="string" required=true %}
Token de produção da conta do AppMax.
{% endapi-method-parameter %}

{% api-method-parameter name="enable\_interest" type="string" required=true %}
Boolean para definir se utiliza parcelamento com/sem juros no AppMax.
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
Email da conta do AppMax.
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
  "message": "Update successfuly"
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

