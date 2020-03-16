---
description: >-
  Este tópico está relacionado a descrever a estrutura da mensagem de resposta
  das requisições.
---

# 4.1.1. Estrutura da mensagem

As mensagens de resposta normalmente possuem dois atributos obrigatórios, abaixo um exemplo em formato JSON de uma mensagem de resposta.

```text
{
  "status": "string",
  "code": integer
}
```

O atributo status, se refere a o tipo de resposta que pode ser de dois tipos **sucesso** \(_success_\) ou **erro** \(_error_\).

O atributo code, se refere ao código próprio da plataforma **Xekout App**, para definição dos códigos utilizados acessar o tópico [Códigos de Resposta](./).

