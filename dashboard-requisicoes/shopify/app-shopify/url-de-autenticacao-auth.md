---
description: URL de autenticação dos dados da loja e do admin responsável.
---

# 2.9.1.3. URL de autenticação \(auth\)

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/shopify/auth" %}
{% api-method-summary %}
Autenticação na XekoutApp
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite a autenticação da loja e do admin, na plataforma XekoutApp.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="hostname" type="string" required=false %}
Domínio da loja no Shopify.
{% endapi-method-parameter %}

{% api-method-parameter %}
Token temporário, parâmetro que precisa ser trocado por um token de acesso permanente.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Caso a operação tenha sucesso, redireciona para a url de login da plataforma XekoutApp.
{% endapi-method-response-example-description %}

```text
Nada
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Falha ao tentar capturar dados necessários para processar a operação.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 400100,
  "message": "Required parameters are missing"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}
Não possui autorização para completar a operação.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 401100,
  "message": "Operation not permitted"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

