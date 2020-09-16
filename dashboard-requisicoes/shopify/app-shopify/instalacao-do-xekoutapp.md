---
description: Instalar o app da Xekout em uma loja.
---

# 2.9.1.1. Instalação do XekoutApp

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/shopify/install" %}
{% api-method-summary %}
Install
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite instalar o app XekoutApp em uma loja cadastrada na plataforma do Shopify.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="shop" type="string" required=true %}
Domínio da loja no Shopify.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Caso a operação tenha sucesso, redireciona para a instalação do app no dashboard da Shopify.
{% endapi-method-response-example-description %}

```text
Nada
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 400102,
  "message": "Missing shop parameter. Please add ?shop=your-shop.myshopify.com to your request"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

