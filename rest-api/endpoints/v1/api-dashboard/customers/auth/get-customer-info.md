---
description: Exibir as informações relacionadas a um cliente cadastrado na plataforma.
---

# Buscar informações de um cliente

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/admin/users/:subdomain/:id" %}
{% api-method-summary %}
Buscar Cliente
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite a busca por um admin, por meio do código UUID.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="subdomain" type="string" required=true %}
Sub domínio da loja cadastrada.
{% endapi-method-parameter %}

{% api-method-parameter name="id" type="string" required=true %}
ID único referente ao cadastro do cliente.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

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
  "code": 200002,
  "user": {
    "name": "string",
    "id": integer,
    "email": "string",
    "phone": "string",
    "cpf": "string",
    "shopify_user_id": integer,
    "phone_code_id": integer,
    "store_user_token": "string",
    "created_at": timestamp,
    "updated_at": timestamp,
    "cart": [], //lista de carrinhos do cliente
    "orders": [], //lista de pedidos do cliente
    "addresses": [] // lista de endereços do cliente
  },
  "platform": 1
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Não foi possível encontrar nenhum cliente correspondente a essa consulta.
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
Clientes na plataforma Xekout App, são definidos como _users_.
{% endhint %}

Objeto de referencia para **orders** :

```text
{
    "id": integer,
    "id_fake": "string",
    "cart_token": "string",
    "gateway_transaction_id": "string",
    "shopify_order_id": "string",
    "order_id": "string",
    "order_status_id": integer,
    "installments": integer,
    "flag": "string",
    "end_card": "string",
    "discount": float,
    "subtotal": float,
    "cashback": float,
    "frete": float,
    "frete_name": "string",
    "total": float,
    "platform_id": integer,
    "tenant_id": integer,
    "gateway_id": integer,
    "shipping_id": integer,
    "coupon_id": integer,
    "coupon_code": "string",
    "gateway_message": null,
    "notification_paid": boolean,
    "notification_rejected": bollean,
    "notification_shopify_paid": boolean,
    "notification_shopify_rejected": boolean,
    "order_payment_id": integer,
    "notification_status_email": boolean,
    "import_problem": boolean,
    "cron_billet": boolean,
    "paid_at": timestamp,
    "shopify_url": "string",
    "hotzapp_import": boolean,
    "user_id": integer,
    "created_at": timestamp,
    "financial_status": "string",
    "address_id": integer,
    "additional_info": "string"
}
```

Objeto de referencia para _**carts**_ :

```text
{
    "original_price": float,
    "products": [
      {
        "product_id": integer,
        "product_title": "string",
        "product_quantity": integer,
        "product_image": "string",
        "product_variant_id": integer,
        "product_type": "string",
        "product_url": "integer",
        "product_discount": float,
        "product_value": float,
        "product_observation": "string"
      }
    ]
  }
```

