# 3.1.1. Listar todas as lojas de um admin

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/admin/search/admin/shops/:uuid" %}
{% api-method-summary %}
Listar lojas de um admin
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite listar todas as lojas de um admin.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="uuid" type="string" required=true %}
UUID único referente ao cadastro do admin na plataforma.
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
  "tenants": [
    {
      "id": integer,
      "uuid": "string",
      "company": "string",
      "document": "string",
      "hasBills": boolean,
      "hasCard": boolean
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
Não foi possível encontrar nenhuma loja, correspondente a essa consulta.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 404104,
  "message": "no tenants available for this tenant"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

