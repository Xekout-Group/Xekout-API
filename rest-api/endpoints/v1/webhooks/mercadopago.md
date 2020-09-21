---
description: Assinaturas dos eventos relacionados a pagamentos do MercadoPago.
---

# MercadoPago

{% api-method method="post" host="https://dev-api.xekout.app" path="/v1/mercadopago/notifications" %}
{% api-method-summary %}
Notificações do MercadoPago
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

{
  "status": "error",
  "code": 400100,
  "message": "No valid data for webhook."
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

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "status": "error",
  "code": 404103,
  "message": "Order not found"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
Para melhor entendimento do funcionamento da url de notificações do AppMax, e das informações recebidas no payload acessar [documentação](https://www.mercadopago.com.br/developers/pt/guides/notifications/webhooks).
{% endhint %}

{% hint style="warning" %}
Para 
{% endhint %}

