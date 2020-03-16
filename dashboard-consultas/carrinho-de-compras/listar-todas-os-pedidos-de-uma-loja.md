# 3.2.1. Listar todos os carrinhos de compras uma loja

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/admin/search/tenant/carts/:uuid" %}
{% api-method-summary %}
Listar carrinhos de compras de uma loja
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite listar todos os carrinhos de compras de uma loja.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="uuid" type="string" required=true %}
UUID único referente ao cadastro da loja na plataforma.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Prefix" %}
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
  "carts": [
    [
      {
        "uuid": "string",
        "total": decimal,
        "product_url": "string",
        "name": "string",
        "email": "string",
        "whatsapp": "string",
        "date": datetime
      },
    ...
  ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
UUID inválido ou não existe.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 400010,
  "message": "this uuid is invalid for this request"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Não foi possível encontrar nenhum carrinho de compras correspondente a essa consulta.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 404003,
  "message": "no carts found for this tenant"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

