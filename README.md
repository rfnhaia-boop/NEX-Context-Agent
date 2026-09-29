# NEX Context Agent

Ferramenta interativa de captação e diagnóstico inicial da NEX.

## O que entrega

- captura obrigatória de nome, e-mail e WhatsApp;
- 15 perguntas sobre empresa, oferta, cliente, aquisição, vendas e operação;
- hipótese diagnóstica individual;
- simulador ajustável de mídia, cliques, leads, vendas e CAC;
- ideias para o primeiro ciclo de aquisição;
- quatro prompts personalizados;
- plano inicial de 30 dias.

## Executar

Abra `/context-agent/` usando qualquer servidor estático.

## Integração com banco ou CRM

Enquanto não existe um backend conectado, o progresso é salvo em `localStorage` na chave `nex-context-v3`.

Payload atual:

```js
window.NEXContextAgent.getPayload()
```

Formato:

```js
{
  version: 3,
  lead: { name, email, phone },
  answers: {},
  questionIndex: 0,
  completed: false,
  updatedAt: "ISO-8601"
}
```

Eventos disponíveis:

```js
window.addEventListener('nex:lead-captured', event => {
  // Enviar event.detail ao backend/CRM.
})

window.addEventListener('nex:context-updated', event => {
  // Salvar o progresso de event.detail.
})
```

Na integração definitiva, substitua ou complemente o salvamento local por uma chamada autenticada ao backend. Não coloque chaves privadas no navegador.

## Ativos visuais

Nesta versão os ativos são carregados da publicação oficial do projeto. Eles podem ser migrados para o próprio repositório durante a integração com o restante do sistema.