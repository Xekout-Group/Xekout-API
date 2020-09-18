---
description: >-
  URL de redirecionamento (Callback) do Shopify, para geração do Access Token
  para a loja.
---

# URL de redirecionamento \(callback\)

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/shopify/callback" %}
{% api-method-summary %}
Callback do Shopify
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite instalar o app XekoutApp em uma loja cadastrada na plataforma do Shopify.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="state" type="string" required=true %}
Usado para verificar a origem da requisição.
{% endapi-method-parameter %}

{% api-method-parameter name="code" type="string" required=true %}
Token temporário, parâmetro que precisa ser trocado por um token de acesso permanente.
{% endapi-method-parameter %}

{% api-method-parameter name="hmac" required=true %}
Usado para validar a solicitação usando a validação do HMAC para garantir que a solicitação veio do Shopify.
{% endapi-method-parameter %}

{% api-method-parameter name="shop" type="string" required=true %}
Domínio da loja no Shopify.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Caso a operação tenha sucesso, redireciona para a url de autenticação do app.
{% endapi-method-response-example-description %}

```text
Nada
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Erros indicando que o servidor não pode ou não processará a solicitação devido a algo que é percebido como um erro do cliente.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 400101,
  "message": "HMAC validation failed"
}

{
  "status": "error",
  "code": 400100,
  "message": "Required parameters are missing"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 403100,
  "message": "Request origin cannot be verified"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="warning" %}
**URLs de redirecionamento** precisam está na lista de permissões do app, insira o URL de retorno de callback do seu aplicativo no seguinte formato:

{https forwarding address}/v1/shopify/callback
{% endhint %}

