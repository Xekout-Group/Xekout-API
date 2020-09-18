---
description: Listar todas os carrinhos de compras cadastrados na plataforma.
---

# Listar carrinhos de compras

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/admin/carts/:subdomain" %}
{% api-method-summary %}
Listar todos os Carrinhos de Compras
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite listar todos os carrinhos de compras de uma loja cadastrados na plataforma.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="subdomain" type="string" required=true %}
Sub domínio da loja cadastrada na Xekout.
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
{% api-method-parameter name="perPage" type="string" required=false %}
Quantidade de itens por página.
{% endapi-method-parameter %}

{% api-method-parameter name="page" type="string" required=false %}
Número da página.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Listagem de lojas concluída com sucesso.
{% endapi-method-response-example-description %}

```text
{
  "status": "success",
  "code": 200003,
  "items": [
    {
      "name": "string",
      "user_id": integer,
      "email": "string",
      "phone": "string",
      "cart_token": "string",
      "created_at": timestamp,
      "cart_id": integer
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

