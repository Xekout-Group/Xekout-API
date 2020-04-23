---
description: Listar todas as lojas cadastrados na plataforma.
---

# 2.2.3. Listar lojas

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/admin/tenants" %}
{% api-method-summary %}
Listar Lojas
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite listar todas as lojas de um admin.
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
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Busca concluída com sucesso.
{% endapi-method-response-example-description %}

```text
{
  "status": "success",
  "code": 200003,
  "tenant": {
    "total": integer,
    "perPage": integer,
    "page": integer,
    "lastPage": integer,
    "data": [
      {
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
      }
    ]
  }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Não possível encontrar nenhuma loja, correspondente a essa consulta .
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

