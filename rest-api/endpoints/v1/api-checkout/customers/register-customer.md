---
description: Cadastrar um novo cliente na plataforma.
---

# Cadastrar Cliente

{% api-method method="post" host="https://api.xekout.app" path="/v1/auth/customer" %}
{% api-method-summary %}
Cadastrar Cliente
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint cadastrar um novo cliente. 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="Content-Type" %}
Cabeçalho que informa ao cliente qual realmente é o tipo de conteúdo retornado.
{% endapi-method-parameter %}

{% api-method-parameter name="Cookies" type="string" required=true %}
Enviando atributo state para verificação da origem da requisição.
{% endapi-method-parameter %}

{% api-method-parameter name="X-Request-Number" type="number" required=true %}
Identificador do estado enviando no Cookies.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="user" type="object" required=true %}
Objeto relacionado as informações do _customer_.
{% endapi-method-parameter %}

{% api-method-parameter name="store" type="string" required=true %}
Domínio da loja códificado utilizando base64.
{% endapi-method-parameter %}

{% api-method-parameter name="cart\_token" type="string" required=true %}
Token do carrinho da loja no Shopify.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=201 %}
{% api-method-response-example-description %}
Cadastro do cliente realizado com sucesso.
{% endapi-method-response-example-description %}

```text
{
	"status": "success",
	"code": 201000,
	"customer": {
		"id": integer,
		"name": "string",
		"email": "string",
		"phone": "string",
		"phone_code_id": integer,
		"cpf": "string",
		"token_access": "string",
		"remember_token": boolean,
		"state_id": "string",
		"active": boolean,
		"gender": "string",
		"email_verified_at": timestamp,
		"shopify_user_id": integer,
		"gateway_user_id": integer,
		"gateway_id": integer,
		"user_address_id": integer,
		"api_token": "string",
		"birth": "string",
		"store_user_token": "string",
		"status": boolean,
		"created_at": timestamp,
		"updated_at": timestamp
	}
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Não possível cadastrar o cliente, campos inválidos. Os seguintes erros podem ser retornados:
{% endapi-method-response-example-description %}

```text
{
  "status": "error",
  "code": 400001,
  "message": "The customer name contains invalid characters or numbers"
}

{
  "status": "error",
  "code": 400001,
  "message": "CPF is invalid"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "status": "error",
  "code": 401003,
  "message": "Origin can't be verified"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "status": "error",
  "code": 404013,
  "message": "Tenant not found for this domain"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=406 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
{
  "status": "error",
  "code": 406000,
  "message": "User don't registered"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

#### user Object

O objeto contendo as informações do parâmetro _**user**_ é definido da seguinte forma:

| Tipo | Nome | Descrição |
| :--- | :--- | :--- |
| string | name | Nome completo do cliente |
| string | email | Email do cliente |
| string | phone | Número de telefone do cliente |
| string | cpf | Número do CPF do cliente |
| string | cep | CEP do endereço do cliente |
| string | number | Número do endereço |
| string | address | Nome do endereço |
| string | neighborhood | Nome do bairro |
| string | city | Cidade |
| string | complement | Complemento |
| Object | state | Informações do estado |
| Object | country | Informações do país |

#### state Object

O objeto contendo as informações do parâmetro _**user.state**_ é definido da seguinte forma:

| Tipo | Nome | Descrição |
| :--- | :--- | :--- |
| string | name | Nome do estado |
| number | id | Identificador do estado |

#### country Object

O objeto contendo as informações do parâmetro _**user.country**_ é definido da seguinte forma:

| Tipo | Nome | Descrição |
| :--- | :--- | :--- |
| string | iso | Código ISO do país |
| number | id | Identificador do país |

{% hint style="warning" %}
Clientes na plataforma Xekout App, são definidos como _users_.
{% endhint %}



