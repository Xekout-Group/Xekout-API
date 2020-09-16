---
description: Guia de primeiros passos da API
---

# Começando

{% hint style="danger" %}
Todas as requisições  HTTP precisam serem enviadas com o header `Content-Type: application/json`. Se o header não estiver presente, isso resultará em respostas mal formadas ou na rejeição da solicitação.
{% endhint %}

> Se você encontrar algum problema entre em contato com o desenvolvedor responsável através do suporte.

### Paginação

As solicitações que retornam vários itens e suportam paginação podem utilizar dois parâmetros para isso. Você pode especificar outras páginas com o parâmetro `?page`. Para alguns recursos, você também pode definir um tamanho de página personalizado utilizando o parâmetro `?perPage`.

### URL base dos Ambientes

* Development: [https://localhost:3333](https://localhost:3333) \(Local\)
* Staging: [https://dev-api.xekout.app](https://dev-api.xekout.app) \(Offine\)
* Production: [https://api.xekout.app](https://api.xekout.app) \(Online\)

### 

