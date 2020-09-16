# Endpoints

### Base API

* **Base URL**: /v1
* **Versão**: 1.0.5
* **Schemes**: http

{% api-method method="get" host="https://api.xekout.app" path="/" %}
{% api-method-summary %}
API Hello
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-Type" required=false %}
cabeçalho que informa ao cliente qual realmente é o tipo de conteúdo retornado.
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "message": "Welcome to Xekout App Rest API"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.xekout.app" path="/checker" %}
{% api-method-summary %}
API Checker
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint verifica as informações da API.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-Type" %}
cabeçalho que informa ao cliente qual realmente é o tipo de conteúdo retornado.
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Requisição realizada com sucesso.
{% endapi-method-response-example-description %}

```text
{
    "status": {
      "running": true,
      "uptime": integer,
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
    "db": {
      "db_name": "string"
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





### Métodos aceitos

| Verbo HTTP | Descrição |
| :--- | :--- |
| **GET** | É usado para ler ou recuperar uma representação de um recurso. |
| POST |  |
| PUT | É mais utilizado para substituir \(ou atualizar\) recursos, executando a requisição para uma URI. |
| DELETE | É usado para excluir um recurso identificado por um URI. |
| PATCH | É usado para modificar parcialmente os recursos. |

