---
description: Assinaturas dos eventos relacionados a pedidos/pagamento no AppMax.
---

# AppMax

{% api-method method="post" host="https://dev-api.xekout.app" path="/v1/appmax/notifications" %}
{% api-method-summary %}
Notificações no AppMax
{% endapi-method-summary %}

{% api-method-description %}
Webhook de notificações no AppMax.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Ok
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "status": "error",
  "code": 400103,
  "message": "Data for webhook invalid."
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "status": "error",
  "code": 401100,
  "message": "Operation not permitted."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
Para melhor entendimento do funcionamento da url de notificações do AppMax, e das informações recebidas no payload acessar [documentação](http://docs.appmax.com.br/api/).
{% endhint %}

