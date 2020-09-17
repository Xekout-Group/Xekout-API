---
description: Lista estados cadastrados.
---

# Estados

{% api-method method="get" host="https://api.xekout.app" path="/v1/auth/gateways" %}
{% api-method-summary %}
Listar estados
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint lista todos os estados cadastrados.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter type="string" name="Content-Type" %}
Cabeçalho que informa ao cliente qual realmente é o tipo de conteúdo retornado.
{% endapi-method-parameter %}

{% api-method-parameter type="string" name="Cookies" required=true %}
Enviando atributo state para verificação da origem da requisição.
{% endapi-method-parameter %}

{% api-method-parameter type="string" name="X-Request-Number" required=true %}
Identificador do estado enviando no Cookies.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="uf" type="string" required=false %}
UF do estado a ser filtrado.
{% endapi-method-parameter %}

{% api-method-parameter name="store" type="string" required=true %}
Domínio da loja cadastrada na Xekout, codificado em base64.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "status": "success",
  "code": 200003,
  "states": [
    {
      "id": integer,
      "name": "string",
      "uf": "string"
    },
  ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "code": 401003,
  "status": "error",
  "message": "Origin can't be verified"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a cake matching this query.
{% endapi-method-response-example-description %}

```
{
  "code": 404000,
  "status": "error",
  "message": "Tenant not found"
}

{
  "status": "error",
  "code": 404012,
  "message": "Not state avaliable for this query"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="warning" %}
O envio do parâmetro de consulta _UF ****_não é obrigatório, o seu envio é apenas para buscar as informações de um unico estado.
{% endhint %}

