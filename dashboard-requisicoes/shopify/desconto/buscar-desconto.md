---
description: Buscar informações de desconto.
---

# 2.9.2.1. Buscar desconto

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/shopify/discount/{domain}/{coupom\_code}" %}
{% api-method-summary %}
Get Desconto
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite buscar informações de desconto, referentes a um cupom de uma loja.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="coupom\_code" type="string" required=true %}
Código de cupom de desconto.
{% endapi-method-parameter %}

{% api-method-parameter name="domain" type="string" required=true %}
Dominio da loja no Shopify.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Caso a operação tenha sucesso, retorna as informações de desconto referente ao cupom.
{% endapi-method-response-example-description %}

```
{
  "code": 200110,
  "status": "success",
  "priceRule": {
    "id": integer,
    "value_type": "string",
    "value": "string",
    "customer_selection": "string",
    "target_type": "string",
    "target_selection": "string",
    "allocation_method": "string",
    "allocation_limit": null,
    "once_per_customer": boolean,
    "usage_limit": integer,
    "starts_at": timestamp,
    "ends_at": timestamp,
    "created_at": timestamp,
    "updated_at": timestamp,
    "entitled_product_ids": [],
    "entitled_variant_ids": [],
    "entitled_collection_ids": [],
    "entitled_country_ids": [],
    "prerequisite_product_ids": [],
    "prerequisite_variant_ids": [],
    "prerequisite_collection_ids": [],
    "prerequisite_saved_search_ids": [],
    "prerequisite_customer_ids": [],
    "prerequisite_subtotal_range": {
      "greater_than_or_equal_to": "string"
    },
    "prerequisite_quantity_range": null,
    "prerequisite_shipping_price_range": null,
    "prerequisite_to_entitlement_quantity_ratio": {
      "prerequisite_quantity": null,
      "entitled_quantity": null
    },
    "title": "string",
    "admin_graphql_api_id": "string"
  }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Não possui autorização para completar a operação.
{% endapi-method-response-example-description %}

```
{
  "code": 401100,
  "status": "error",
  "message": "Operation not permitted"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
Loja se encontra inativa.
{% endapi-method-response-example-description %}

```
{
  "code": 403001,
  "status": "error",
  "message": "Unactivated account"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "code": 404103,
  "status": "error",
  "message": "Invalid or expired discount coupon"
}

{
  "code": 404100,
  "status": "error",
  "message": "Tenant with shop name not exist"
}

{
  "code": 404104,
  "status": "error",
  "message": "Price rule not found"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

