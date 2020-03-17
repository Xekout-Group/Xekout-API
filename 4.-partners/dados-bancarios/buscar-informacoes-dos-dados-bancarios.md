---
description: Buscar informações dos dados bancários de um parceiro.
---

# 4.2.2. Buscar informações dos dados bancários

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/partner/banks/:uuid" %}
{% api-method-summary %}
Buscar Dados Bancários
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite buscar as informações dos dados bancários de um parceiro.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="UUID" type="string" required=false %}
UUID referente ao cadastro dos dados bancários do parceiro.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter %}
Usado na construção de uma chave para armazenamento de token em todos os provedores de armazenamento.
{% endapi-method-parameter %}

{% api-method-parameter name="Authentication" type="string" required=true %}
Bearer Token JWT para autenticação.
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=204 %}
{% api-method-response-example-description %}
Informações atualizadas com sucesso.
{% endapi-method-response-example-description %}

```
{
  "status": "success",
  "code": 204001,
  "message": "bank inforupdate successfulys"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Não possível encontrar nenhum dado bancário, correspondente a essa consulta.
{% endapi-method-response-example-description %}

```
{
  "status": "error",
  "code": 404005,
  "message": "bank info not found"
} 
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=406 %}
{% api-method-response-example-description %}
Não foi possível atualizar as informações bancárias.
{% endapi-method-response-example-description %}

```
{
  "status": "error",
  "code": 406002,
  "message": "partner has transactions active"
} 
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



