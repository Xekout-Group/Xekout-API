# Atualizar informações de um admin

{% api-method method="put" host="https://dev-api.xekout.app" path="/v1/admin/admins" %}
{% api-method-summary %}
Atualizar Admin
{% endapi-method-summary %}

{% api-method-description %}
Este endpoint permite a busca por um admin, por meio do código UUID.
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
{% api-method-parameter name="gender" type="string" required=false %}
Lembrar token de acesso
{% endapi-method-parameter %}

{% api-method-parameter name="remember\_token" type="string" required=false %}
Sexo do admin
{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=false %}
Nome do admin
{% endapi-method-parameter %}

{% api-method-parameter name="cellphone" type="string" required=false %}
Número de telefone do admin
{% endapi-method-parameter %}

{% api-method-parameter name="cep" type="string" required=false %}
CEP do endereço do admin
{% endapi-method-parameter %}

{% api-method-parameter name="address" type="string" required=false %}
Endereço do admin
{% endapi-method-parameter %}

{% api-method-parameter name="number" type="string" required=false %}
Número do endereço
{% endapi-method-parameter %}

{% api-method-parameter name="complement" type="string" required=false %}
Complemento do endereço
{% endapi-method-parameter %}

{% api-method-parameter name="neighborhood" type="string" required=false %}
Nome do Bairro do endereço
{% endapi-method-parameter %}

{% api-method-parameter name="city" type="string" required=false %}
Nome da cidade
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
  "code": 200000,
  "message": "Update successfully"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=401 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
Token de acesso não presente do header ou malformado.
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

