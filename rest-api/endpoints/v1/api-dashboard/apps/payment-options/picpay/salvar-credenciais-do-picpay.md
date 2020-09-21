# Salvar credenciais do PicPay

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/admin/apps/picpay/:subdomain" %}
{% api-method-summary %}
Salvar credenciais do PicPay
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
{% api-method-parameter name="picpay\_token" type="string" required=true %}
Token fornecido pelo PicPay.
{% endapi-method-parameter %}

{% api-method-parameter name="seller\_token" type="string" required=true %}
Seller Token fornecido pelo PicPay.
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
Email da conta do PicPay.
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
  "message": "Gateway PicPay update successfuly"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
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

