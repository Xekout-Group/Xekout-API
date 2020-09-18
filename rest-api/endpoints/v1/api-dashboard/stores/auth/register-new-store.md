---
description: Cadastrar uma nova loja na plataforma.
---

# Cadastrar nova Loja

{% api-method method="post" host="https://dev-api.xekout.app" path="/v1/admin/tenants" %}
{% api-method-summary %}
Cadastrar Lojas
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite o cadastro de uma nova loja.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Prefix" type="string" required=false %}
Usado na construção de uma chave para armazenamento de token em todos os provedores de armazenamento.
{% endapi-method-parameter %}

{% api-method-parameter name="Authentication" type="string" required=true %}
Bearer Token JWT para autenticação.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="platform" type="string" required=true %}
Identificador UUID referente a plataforma de utilização.
{% endapi-method-parameter %}

{% api-method-parameter name="card\_name" type="string" required=true %}
Nome no cartão de crédito.
{% endapi-method-parameter %}

{% api-method-parameter name="card\_number" type="string" required=true %}
Número do cartão de crédito.
{% endapi-method-parameter %}

{% api-method-parameter name="card\_cvv" type="string" required=true %}
Código de segurança do cartão de crédito.
{% endapi-method-parameter %}

{% api-method-parameter name="card\_month" type="integer" required=true %}
Mês de vencimento do cartão de crédito.
{% endapi-method-parameter %}

{% api-method-parameter name="card\_year" type="integer" required=true %}
Ano de vencimento do cartão de crédito.
{% endapi-method-parameter %}

{% api-method-parameter name="card\_document" type="string" required=true %}
CPF do dono do cartão de crédito.
{% endapi-method-parameter %}

{% api-method-parameter name="document" type="string" required=false %}
CNPJ da loja.
{% endapi-method-parameter %}

{% api-method-parameter name="fantasyName" type="string" required=true %}
Nome fantasia da loja
{% endapi-method-parameter %}

{% api-method-parameter name="email" type="string" required=true %}
Email de cadastro da loja
{% endapi-method-parameter %}

{% api-method-parameter name="phone" type="string" required=false %}
Número telefônico da loja
{% endapi-method-parameter %}

{% api-method-parameter name="whatsapp" type="string" required=false %}
Número de WhatsApp da loja
{% endapi-method-parameter %}

{% api-method-parameter name="domain" type="string" required=true %}
URL do dominio no Shopify, da loja.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Loja cadastrada com sucesso.
{% endapi-method-response-example-description %}

```text
{
	"status": "success",
	"code": 201010,
	"tenant": {
		"company": "string",
		"email": "string",
		"whatsapp": "string",
		"shopify_domain": "string",
		"subdomain": "string",
		"platform": integer
	}
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Não possível cadastrar a loja, campos inválidos.
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 400001,
  "message": "unique validation failed on shopify_domain"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="warning" %}
O código utilizado na resposta da requisição, é um código próprio do Xekout App, para definições e especificações de todos os códigos, acessar [Códigos Respostas](register-new-store.md).
{% endhint %}

