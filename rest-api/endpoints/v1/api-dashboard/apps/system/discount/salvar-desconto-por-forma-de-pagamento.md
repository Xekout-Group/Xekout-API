# Salvar desconto por forma de pagamento

{% api-method method="put" host="https://dev-api.xekout.app" path="/v1/admin/apps/paypal/:subdomain" %}
{% api-method-summary %}
Atualizar desconto por forma de pagamento
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
{% api-method-parameter name="card" type="string" required=false %}
Valor string para porcentagem oferecida no desconto do tipo cartão.
{% endapi-method-parameter %}

{% api-method-parameter name="card\_message" type="string" required=false %}
Mensagem a ser exibida no checkout na forma de pagamento por Cartão.
{% endapi-method-parameter %}

{% api-method-parameter name="billet" type="string" required=false %}
Valor string para porcentagem oferecida no desconto do tipo boleto.
{% endapi-method-parameter %}

{% api-method-parameter name="billet\_message" type="string" required=false %}
Mensagem a ser exibida no checkout na forma de pagamento por Boleto.
{% endapi-method-parameter %}

{% api-method-parameter name="billet\_active" type="string" required=false %}
Boolean para definir se o desconto por forma de pagamento Boleto está ativo.
{% endapi-method-parameter %}

{% api-method-parameter name="card\_active" type="string" required=false %}
Boolean para definir se o desconto por forma de Segredo ID gerado para o aplicativo do PayPal.
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
  "message": "Discount update successfuly"
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

