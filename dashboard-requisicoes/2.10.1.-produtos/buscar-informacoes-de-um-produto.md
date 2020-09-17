---
description: Exibir as informações relacionadas a um admin cadastrado na plataforma.
---

# 2.10.1.2. Buscar informações de um produto

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/admin/products/{store\_domain}/{product\_id}" %}
{% api-method-summary %}
Buscar Produto
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite buscar um produto por seu ID.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="product\_id" type="string" required=true %}
ID do produto no Shopify.
{% endapi-method-parameter %}

{% api-method-parameter name="store\_domain" type="string" required=true %}
Domínio da loja no Shopify.
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

{% api-method-query-parameters %}
{% api-method-parameter name="since\_id" type="string" required=false %}
Restrinja os resultados para após o ID especificado.
{% endapi-method-parameter %}

{% api-method-parameter name="presentment\_currencies" type="string" %}
Retorne os preços de apresentação em apenas algumas moedas, especificadas por uma lista separada por vírgula dos códigos de moeda.
{% endapi-method-parameter %}

{% api-method-parameter name="fields" type="string" %}
Mostrar apenas determinados campos, especificados por uma lista separada por vírgula de nomes de campos.
{% endapi-method-parameter %}

{% api-method-parameter name="published\_status" type="string" required=false %}
Mostrar produtos pelo status publicado.
{% endapi-method-parameter %}

{% api-method-parameter name="published\_at\_max" type="string" required=false %}
Mostrar produtos publicados antes da data.
{% endapi-method-parameter %}

{% api-method-parameter name="updated\_at\_min" type="string" required=false %}
Mostrar produtos atualizados pela última vez após a data.
{% endapi-method-parameter %}

{% api-method-parameter name="created\_at\_max" type="string" required=false %}
Mostrar produtos criados antes da data.
{% endapi-method-parameter %}

{% api-method-parameter name="created\_at\_min" type="string" required=false %}
Mostrar produtos criados após a data.
{% endapi-method-parameter %}

{% api-method-parameter name="collection\_id" type="string" required=false %}
Filtre os resultados por ID da coleção de produtos.
{% endapi-method-parameter %}

{% api-method-parameter name="product\_type" type="string" required=false %}
Filtre os resultados por tipo de produto.
{% endapi-method-parameter %}

{% api-method-parameter name="handle" type="string" required=false %}
Filtre os resultados por identificador do produto.
{% endapi-method-parameter %}

{% api-method-parameter name="vendor" type="string" required=false %}
Filtre os resultados por fornecedor do produto.
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="string" required=false %}
Retorne a tantos resultados por página_._
{% endapi-method-parameter %}

{% api-method-parameter name="title" type="string" required=false %}
Filtre os resultados por título do produto.
{% endapi-method-parameter %}

{% api-method-parameter name="ids" type="string" required=false %}
Retorne apenas produtos especificados por uma lista separada por vírgula de IDs de produtos.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Informações do produto.
{% endapi-method-response-example-description %}

```text
{
  "code": 200003,
  "status": "success",
  "productGet": {
    "id": integer,
    "title": "string",
    "body_html": null,
    "vendor": "string",
    "product_type": "",
    "created_at": timestamp,
    "handle": "string",
    "updated_at": timestamp,
    "published_at": null,
    "template_suffix": null,
    "published_scope": "string",
    "tags": "",
    "admin_graphql_api_id": "string",
    "variants": [
      {
        "id": integer,
        "product_id": integer,
        "title": "string",
        "price": "string",
        "sku": "",
        "position": integer,
        "inventory_policy": "string",
        "compare_at_price": null,
        "fulfillment_service": "string",
        "inventory_management": null,
        "option1": "string",
        "option2": null,
        "option3": null,
        "created_at": timestamp,
        "updated_at": timestamp,
        "taxable": boolean,
        "barcode": null,
        "grams": 0,
        "image_id": null,
        "weight": 0,
        "weight_unit": "string",
        "inventory_item_id": integer,
        "inventory_quantity": integer,
        "old_inventory_quantity": integer,
        "requires_shipping": boolean,
        "admin_graphql_api_id": "string"
      }
    ],
    "options": [
      {
        "id": integer,
        "product_id": integer,
        "name": "string",
        "position": integer,
        "values": [
          "string"
        ]
      }
    ],
    "images": [],
    "image": null
  }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
Loja inativa ou sem app instalado.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 403001,
  "message": "Unactivated account"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Loja não encontrada ou não existe.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 404100,
  "message": "Tenant with shop name not exist"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

