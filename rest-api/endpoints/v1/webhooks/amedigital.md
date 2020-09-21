---
description: Assinaturas dos eventos relacionados a pedidos/pagamento na AmeDigital.
---

# AmeDigital

{% api-method method="post" host="https://dev-api.xekout.app" path="/v1/amedigital/notifications" %}
{% api-method-summary %}
Notificações da AmeDigital
{% endapi-method-summary %}

{% api-method-description %}
Webhook de notificações da AmeDigitial.
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
Para melhor entendimento do funcionamento da url de notificações da AmeDigital, e das informações recebidas no payload acessar [documentação](https://amedigital.github.io/).
{% endhint %}



