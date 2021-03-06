---
description: 'Bloquear um cliente de uma loja, cadastrado na plataforma.'
---

# 2.8.1. Bloquear Cliente de uma Loja

{% api-method method="post" host="https://dev-api.xekout.app" path="/v1/admin/tenant/user/block/:uuid" %}
{% api-method-summary %}
Bloquear Cliente
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite bloquear um cliente de uma loja, cadastrado na plataforma.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="uuid" type="string" required=true %}
UUID único referente ao cadastro do cliente.
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
{% api-method-response-example httpCode=204 %}
{% api-method-response-example-description %}
Bloqueio concluída com sucesso.
{% endapi-method-response-example-description %}

```text
{
  "status": "success",
  "code": 204002,
  "message": "user blocked successfuly"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Não foi possível bloquear o cliente, o mesmo já está bloqueado.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 400004,
  "message": "user is already blocked"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Não foi possível encontrar um cliente que correspondam a essa consulta.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 404014,
  "message": "user not found for this tenant"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="danger" %}
Retorno 204, não retorna nenhum dado na resposta da requisição. A informação acima no campo de resposta, é apenas ilustrativa.
{% endhint %}

