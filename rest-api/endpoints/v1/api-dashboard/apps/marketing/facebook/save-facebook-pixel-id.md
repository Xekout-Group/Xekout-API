# Salvar Pixel ID do facebook

{% api-method method="post" host="https://dev-api.xekout.app" path="/v1/admin/apps/facebook/:subdomain" %}
{% api-method-summary %}
Salvar Salvar Pixel ID do facebook do PayPal
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="subdomain" required=true %}
Subdomain da loja cadastrada na Xekout.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Prefix" %}
Bearer Token JWT para autenticação.
{% endapi-method-parameter %}

{% api-method-parameter name="Authentication" required=true %}
Usado na construção de uma chave para armazenamento de token em todos os provedores de armazenamento.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="pixelData" type="string" required=true %}
Objeto contendo as informações do Pixel.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "status": "success",
  "code": 200004,
  "message": "Gateway PayPal update successfuly"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 404013,
  "message": "Tenant not found"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

Atualmente podem ser utilizando os seguintes tipos de Pixel do Facebook: **Purchase**, **Lead**, **AddPaymentInfo**, **AddToCart** e **InitiateCheckout**.

Os parâmetros utilizados no objeto pixelData são:

| Tipo | Nome | Descrição |
| :--- | :--- | :--- |
| string | name | Nome do evento. |
| string | product\_type | Tipo de produtos. |
| integer | payment\_type | Formas de pagamento a ser utilizada, podendo ser 1 \(cartão\), 2 \(boleto\), ou 3 \(qrcode\). |
| string | products | Se vão ser utilizando todos os produtos, ou apenas produtos selecionados. |
| string | event | Evento do pixel, podendo ser Purchase, Lead, AddPaymentInfo, AddToCart e InitiateCheckout. |
| string | token | Token do app no facebook. |
| string | app\_id | Id do app no facebook. |
| string | id | ID do pixel no facebook. |

