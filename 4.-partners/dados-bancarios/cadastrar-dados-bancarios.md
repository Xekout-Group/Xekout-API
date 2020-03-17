---
description: Cadastrar dados bancários de um paceiro.
---

# 4.2.1. Cadastrar dados bancários

{% api-method method="post" host="https://dev-api.xekout.app" path="/v1/partner/banks" %}
{% api-method-summary %}
Cadastrar Dados Bancários
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite o cadastro de dados bancários de um parceiro.
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

{% api-method-body-parameters %}
{% api-method-parameter name="partner\_id" type="string" required=true %}
Identificador único do cadastro do parceiro.
{% endapi-method-parameter %}

{% api-method-parameter name="bank\_name" type="string" required=true %}
Nome do banco
{% endapi-method-parameter %}

{% api-method-parameter name="agency\_number" type="string" required=true %}
Número da agência bancária
{% endapi-method-parameter %}

{% api-method-parameter name="account\_number" type="string" required=true %}
Número da conta da agência bancária
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Parceiro cadastrado com sucesso.
{% endapi-method-response-example-description %}

```text
{
  "status": "success",
  "code": 201013,
  "bankInfo": {
    "id": integer,
    "uuid": "string",
    "partner_id": integer,
    "bank_name": "string",
    "agency_number": "string",
    "account_number": "string",
    "created_at": timestamp,
    "updated_at": timestamp
  }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Erro ao tentar cadastrar os dados bancários do parceiro.
{% endapi-method-response-example-description %}

```
{
  "status": "error",
  "code": 400016,
  "message": "error on try register bank"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

