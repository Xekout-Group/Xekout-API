---
description: Assinaturas dos eventos relacionados a pedidos/pagamento no PicPay.
---

# PicPay

{% api-method method="post" host="https://dev-api.xekout.app" path="/v1/picpay/notifications" %}
{% api-method-summary %}
Notificações do PicPay
{% endapi-method-summary %}

{% api-method-description %}
Webhook de notificações do PicPay.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="x-seller-token" type="string" required=false %}
Token gerado e fornecido pelo PicPay.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="referenceId" %}
Identificador da transação.
{% endapi-method-parameter %}

{% api-method-parameter name="authorizationId" type="string" required=false %}
Idenficador único da autorização.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

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
  "message": "Error when try get picpay payment status."
}

{
  "status": "error",
  "code": 400105,
  "message": "Invalid seller token provided."
}

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
Para melhor entendimento do funcionamento da url de notificações do PicPay acessar [documentação](https://ecommerce.picpay.com/doc/#).
{% endhint %}



