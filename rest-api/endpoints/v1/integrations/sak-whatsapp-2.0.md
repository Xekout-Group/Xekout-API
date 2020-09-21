# SAK \(WhatsApp 2.0\)

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/api/whatsapp2" %}
{% api-method-summary %}
Buscar credenciais do MercadoPago
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

{% api-method-query-parameters %}
{% api-method-parameter name="token" type="string" required=true %}
Token para integração com o SAK fornecido pela Xekout.
{% endapi-method-parameter %}

{% api-method-parameter name="type" type="string" required=true %}
Tipo de consulta, pode ser do tipo _**orders**_ ou _**checkouts**_
{% endapi-method-parameter %}

{% api-method-parameter name="created\_at\_min" type="string" required=true %}
Timestamp informando a data de criação minima dos pedidos/checkouts.
{% endapi-method-parameter %}

{% api-method-parameter name="created\_at\_max" type="string" required=true %}
Timestamp informando a data de criação máxima dos pedidos/checkouts.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Retorno para consulta do topo _**checkouts**_.
{% endapi-method-response-example-description %}

```text

[
  {
    "type": "checkout",
    "api_token": "string",
    "order": {
      "token": "string",
      "checkout_url": "string",
      "id": integer,
      "status": "string",
      "values": {
        "total": float
      },
      "costumer": {
        "name": "string",
        "email": "string",
        "doc": "string",
        "phone_number": "string",
        "address": "string",
        "address_number": "string",
        "address_comp": "string",
        "address_district": "string",
        "address_city": "string",
        "address_state": "string",
        "address_country": "string",
        "address_zip_code": "string"
      },
      "products": [
        {
          "id": integer,
          "name": "string",
          "price": "string",
          "qty": integer,
          "image": "string"
        }
      ]
    },
    "created_at": timestamp,
    "updated_at": timestamp
  }
]
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

{% hint style="warning" %}
O response muda conforme o _**type**_ é alterado entre as opções.
{% endhint %}

Retorno de consulta do tipo _**order**_:

```text
{
    "type": "order",
    "api_token": "wxa_a364bab1b34f4a90bd73fc6b78398673",
    "order": {
      "financial_status": "string",
      "billet_url": "string",
      "codigo_barras": "string",
      "gateway": "string",
      "token": "string",
      "checkout_url": "string",
      "id": "string",
      "status": "string",
      "payment_type": "string",
      "values": {
        "total": "string"
      },
      "costumer": {
        "name": "string",
        "email": "string",
        "doc": "strig",
        "phone_number": "string",
        "address": "string",
        "address_number": "string",
        "address_comp": "string",
        "address_district": "string",
        "address_city": "string",
        "address_state": "string",
        "address_country": "string"
      },
      "products": [
        {
          "id": "35802567278746",
          "name": "produto teste",
          "price": "string",
          "qty": "string",
          "image": "string"
        }
      ]
    },
    "created_at": timestamp
  }
```

Retorno de consulta do tipo _**checkouts**_:

```text

[
  {
    "type": "checkout",
    "api_token": "string",
    "order": {
      "token": "string",
      "checkout_url": "string",
      "id": integer,
      "status": "string",
      "values": {
        "total": float
      },
      "costumer": {
        "name": "string",
        "email": "string",
        "doc": "string",
        "phone_number": "string",
        "address": "string",
        "address_number": "string",
        "address_comp": "string",
        "address_district": "string",
        "address_city": "string",
        "address_state": "string",
        "address_country": "string",
        "address_zip_code": "string"
      },
      "products": [
        {
          "id": integer,
          "name": "string",
          "price": "string",
          "qty": integer,
          "image": "string"
        }
      ]
    },
    "created_at": timestamp,
    "updated_at": timestamp
  }
]
```

