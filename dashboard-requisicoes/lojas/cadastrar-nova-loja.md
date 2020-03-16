---
description: Cadastrar uma nova loja na plataforma.
---

# 2.2.1. Cadastrar nova Loja

{% api-method method="post" host="https://dev-api.xekout.app" path="/v1/admin/tenants" %}
{% api-method-summary %}
Cadastrar Lojas
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite o cadastro de uma nova loja.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Prefix" type="string" required=false %}
Usado na construção de uma chave para armazenamento de token em todos os provedores de armazenamento.
{% endapi-method-parameter %}

{% api-method-parameter name="Authentication" type="string" required=true %}
Bearer Token JWT para autenticação.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="fantasyName" type="string" required=true %}
Nome fantasia da loja
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
Email de cadastro da loja
{% endapi-method-parameter %}

{% api-method-parameter name="phone" type="string" required=false %}
Número telefônico da loja
{% endapi-method-parameter %}

{% api-method-parameter name="whatsapp" type="string" required=false %}
Número de WhatsApp da loja
{% endapi-method-parameter %}

{% api-method-parameter name="domain" type="string" required=true %}
URL do dominio no Shopify, da loja
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Loja cadastrada com sucesso.
{% endapi-method-response-example-description %}

```text
{
  "status": "success",
  "code": 201010,
  "admin": [
    {
     "id": 1,
      "uuid": "string",
      "plan_id": integer,
      "company": "string",
      "document": "string",
      "url_store": "string",
      "shopify_domain": "string",
      "shopify_id": integer,
      "email": "string",
      "whatsapp": "string",
      "about": "string",
      "privacy": "string",
      "term": "string",
      "cep": "string",
      "city": "string",
      "phone": "string",
      "status": boolean,
      "googleanalytics_id": integer,
      "googletagmanager_id": integer,
      "googleads_id": integer,
      "gateway_id": integer,
      "platform_id": integer,
      "file_id": integer,
      "state_id": integer,
      "facebook_pixel_id": integer,
      "facebook_pixel_id_2": integer,
      "facebook_pixel_billet": boolean,
      "facebook_pixel_card": boolean,
      "jivochat": null,
      "tidio_key": null,
      "tawk": null,
      "smartlook": null,
      "whatsapp_integration": boolean,
      "whatsapp_number": boolean,
      "discount_card": null,
      "discount_card_call": null,
      "discount_billet": integer,
      "discount_billet_call": "string",
      "discount_debit": integer,
      "trading_name": "string",
      "googleads_label": "string",
      "token": "string",
      "hotzapp_url": "string",
      "hotpayment_type_idzapp_url": integer,
      "payment_type_id": integer,
      "shopify_token": integer,
      "country_id": integer,
      "hostname_id": integer,
      "partner_id": integer,
      "created_at": timestamp,
      "updated_at": timestamp
    }
  ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Não possível cadastrar a loja, campos inválidos.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 400007,
  "message": "field error or null data"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="warning" %}
O código utilizado na resposta da requisição, é um código próprio do Xekout App, para definições e especificações de todos os códigos, acessar [Códigos Respostas](../../codigos-de-resposta/codigos-de-resposta-1.md).
{% endhint %}

