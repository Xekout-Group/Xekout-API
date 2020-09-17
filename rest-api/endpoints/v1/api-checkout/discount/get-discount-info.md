---
description: Buscar informações do desconto
---

# Buscar desconto

{% api-method method="get" host="https://api.xekout.app" path="/v1/shopify/discount/:store\_domain/code" %}
{% api-method-summary %}
Buscar informações do desconto
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint para buscar _price rules_ referente ao desconto na API do Shopify. 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="store\_domain" type="string" required=true %}
Domínio da loja cadastrada na Xekout.
{% endapi-method-parameter %}

{% api-method-parameter name="code" type="string" required=true %}
Cupom de desconto fornecido pelo lojista.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" %}
Cabeçalho que informa ao cliente qual realmente é o tipo de conteúdo retornado.
{% endapi-method-parameter %}

{% api-method-parameter name="Cookies" required=true type="string" %}
Enviando atributo state para verificação da origem da requisição.
{% endapi-method-parameter %}

{% api-method-parameter name="X-Request-Number" required=true type="string" %}
Identificador do estado enviando no Cookies.
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

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
    "usage_limit": null,
    "starts_at": timestamp,
    "ends_at": null,
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
    "prerequisite_subtotal_range": null,
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

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "code": 400100,
  "status": "error",
  "message": "Price rule not exist"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "code": 401003,
  "status": "error",
  "message": "Origin can't be verified"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "code": 404100,
  "status": "error",
  "message": "Not Found"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="danger" %}
O valor no campo code sempre precisa ser enviado codificado no formato base64. O não envio nesse formato resultará em respota HTTP 404.
{% endhint %}

