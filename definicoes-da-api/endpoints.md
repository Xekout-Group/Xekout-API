---
description: 'Endpoints para testar se a API está funcionando, e URL base.'
---

# 1.2. Endpoints de teste e URL Base

## Base API

* **Base URL**: /v1
* **Versão**: 1.0.5
* **Schemes**: http

{% hint style="info" %}
Versionamento da API pode ser encontrado na página de [Versões da API](versao.md).
{% endhint %}

## Endpoints de teste

{% api-method method="get" host="https://dev-api.xekout.app" path="/" %}

{% api-method method="get" host="https://dev-api.xekout.app" path="/checker" %}
{% api-method-summary %}

{% endapi-method-summary %}

{% api-method-description %}
Este endpoint verifica as informações da API.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Requisição realizada com sucesso.
{% endapi-method-response-example-description %}

```text
[
  {
    "status": {
      "running": boolean,
      "date": timestamp,
      "os_version": "string"
    },
    "api_info": {
      "name": "string",
      "version": "string",
      "description": "string",
      "maintainer": "string",
      "license": "string"
    },
    "engines": {
      "node_version": "string",
      "adonisjs_version": "string"
    },
    "keyword": [
      "string"
    ]
  }
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
Erro no servidor.
{% endapi-method-response-example-description %}

```text
Não foi possivel se conectar ao servidor.
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

