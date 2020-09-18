---
description: Listar todas as faturas cadastrados na plataforma.
---

# Listar faturas

{% api-method method="get" host="https://api.xekout.app" path="/v1/admin/orders" %}
{% api-method-summary %}
Listar todos as faturas
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite listar todas as faturas cadastrados na plataforma.
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
Listagem de faturas concluída com sucesso.
{% endapi-method-response-example-description %}

```text
{
  "status": "success",
  "code": 200002,
  "items": [
    {
      "id": integer,
      "uuid": "string",
      "product_id": "string",
      "total": decimal,
      "status_id": integer,
      "validate": "string",
      "period": "string",
      "quantity_approved": "string",
      "tenant_id": integer,
      "hostname_id": integer,
      "start": timestamp,
      "end": timestamp,
      "billet_code": "string",
      "billet_url": "string",
      "billet_pdf": "string",
      "gateway_transaction_id": "string",
      "gateway_id": integer,
      "products": "string",
      "created_at": timestamp,
      "updated_at": timestamp
    }
  ],
  "total": integer,
  "perPage": integer,
  "page": integer,
  "lastPage": integer,
  "platform": integer
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

{% hint style="danger" %}
O objeto da _invoice_ retornado na lista pode sofrer alterações.
{% endhint %}

