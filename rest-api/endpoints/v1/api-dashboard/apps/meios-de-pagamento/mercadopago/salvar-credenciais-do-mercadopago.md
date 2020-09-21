# Salvar credenciais do MercadoPago

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/admin/apps/mercadopago/:subdomain" %}
{% api-method-summary %}
Salvar credenciais do MercadoPago 
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
Email de cadastro da conta do MercadoPago.
{% endapi-method-parameter %}

{% api-method-parameter name="access\_token" type="string" required=true %}
Token de acesso da conta do MercadoPago.
{% endapi-method-parameter %}

{% api-method-parameter name="public\_key" type="string" required=true %}
Chave pública da conta do MercadoPago.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
Para encontrar as credenciais de testes da conta acesse o [link](https://www.mercadopago.com.br/developers/panel/credentials).
{% endhint %}



