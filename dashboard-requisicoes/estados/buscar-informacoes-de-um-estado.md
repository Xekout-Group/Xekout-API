---
description: Exibir as informações relacionadas a um estado na plataforma.
---

# 2.7.1. Buscar informações de um estado

{% api-method method="get" host="https://dev-api.xekout.app" path="/v1/admin/orders/:uuid" %}

{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Busca concluída com sucesso.
{% endapi-method-response-example-description %}

```text
{
  "status": "success",
  "code": 200002,
  "states": [
    {
      "id": integer,
      "name": "string",
      "uf": "string",
      "created_at": timestamp,
      "updated_at": timestamp
    }
  ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}

{% api-method-response-example-description %}
Não possível encontrar nenhum estado, correspondente a essa consulta .
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 404012,
  "message": "state not found or avaliable"
}
``

{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}
```

