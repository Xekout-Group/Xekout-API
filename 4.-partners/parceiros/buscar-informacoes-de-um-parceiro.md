---
description: Buscar informações relacionadas a um parceiro na plataforma.
---

# 4.1.2. Buscar informações de um parceiro

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/partner/account/:uuid" %}
{% api-method-summary %}
Buscar parceiro
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite a busca de um parceiro, por meio do código UUID.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="uuid" type="string" required=true %}
UUID único referente ao cadastro do parceiro.
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
  "partner": [
    {
      "id": integer,
      "uuid": "string",
      "name": "string",
      "cpf": "string",
      "email": "string",
      "cellphone": "string",
      "gender": "string,
      "code": "string",
      "instagram": "string",
      "facebook": "string",
      "cep": "string",
      "address": "string",
      "number": "string",
      "complement": "string",
      "neighborhood": "string",
      "city": "string",
      "state_id": integer,
      "status": boolean,
      "email_verified_at": timestamp
      "login_at": timestamp,
      "file_id": integer,
      "bank_name": "string",
      "agency_number": "string",
      "account_number": "string",
      "partner_id": integer,
      "has_transaction": boolean,
      "created_at": timestamp,
      "updated_at": timestamp
    }
  ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Não possível encontrar nenhum parceiro, correspondente a essa consulta .
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 404001,
  "message": "partner not found"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

