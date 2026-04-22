> “Se você já revisou um Pull Request sem descrição, sabe o custo disso. Hoje vamos ver como usar IA para padronizar, acelerar e melhorar a qualidade dos PRs.”

- PR com título: “fix”
- Descrição: vazia
- Você como Reviewer tentando entender tudo pelo diff

> “Um bom PR não economiza tempo só para quem revisa — economiza para todo o time.”

# Estrutura ideal de um Pull Request

> A IA só funciona bem se existir estrutura. Essa estrutura **vai ser diferente** a depender do seu time, como ele quer trabalhar e da estrutura dele.

Um exemplo de uma estrutura recomendada, seria:
- Título claro
- Contexto / problema
- Solução aplicada
- Como testar
- Impactos / riscos
- Checklist

## Exemplos práticos:

> “ajustes no login”

> “Corrige falha de autenticação ao expirar token JWT”

> “Pense no PR como uma mini documentação da mudança. Se alguém ler daqui 3 meses, precisa entender sem contexto adicional. Um PR bem feito é como um commit com esteroides.”

# Geração automática de descrição com IA

> “Agora que temos uma estrutura, vamos automatizar isso.”

O que a IA pode fazer:
- Gerar descrição a partir do diff
- Sugerir título
- Organizar seções automaticamente

Código alterado (diff) -> Contexto inferido, lista de mudanças, passos de teste

> “A IA não ‘entende intenção’, ela infere padrões. Por isso, quanto melhor o diff e os commits, melhor o resultado.”

# Resumo de alterações a partir de diffs

Diffs grandes geram um reviewer perdido 😵‍💫

Devemos então, **transformar diff em resumo semântico**

Por exemplo, podemos ter um diff com:

+120 linhas em autenticação
-30 linhas de código legado

A IA pode gerar o seguinte resumo:

“Refatoração do fluxo de login”
“Remoção de lógica duplicada”
“Adição de validação de token”

> “O diff mostra ‘o que mudou’. O resumo mostra ‘por que isso importa’.”

# Checklist automatizado

Checklist evita erros básicos e padroniza qualidade. Assim como o PR em si, **vai ser customizado pro seu caso e time**.

Exemplos de possíveis itens em um checklist:

- [ ] Testes foram adicionados?
- [ ] Impacta outras áreas?
- [ ] Possui rollback?
- [X] Performance foi considerada?

Com IA podemos:

- Gerar itens adicionais ao checklist, baseado no tipo de mudança
- Adaptar conforme backend/frontend/docs

> “Isso tira da memória do dev e coloca no processo.”

> “Na próxima PR que você abrir, tente gerar a descrição com IA e revise como se fosse um reviewer.”

```markdown
Sua tarefa é analisar o diff abaixo e gerar um Pull Request profissional seguindo a estrutura definida.

## Contexto

* Repositório: [nome do projeto]
* Stack: [ex: Node.js + React]
* Objetivo da mudança: [descreva brevemente, se souber]

## Diff da alteração

[COLE AQUI O DIFF]

## Instruções

1. Gere um título objetivo e descritivo.
2. Crie a descrição do PR com as seguintes seções:

### 🧠 Contexto

Explique o problema que motivou a mudança.

### 🚀 Solução

Descreva o que foi feito e como resolve o problema.

### 📦 Alterações principais

Liste as mudanças mais relevantes de forma clara e resumida.

### 🧪 Como testar

Explique passo a passo como validar a alteração.

### ⚠️ Riscos / impactos

Aponte possíveis efeitos colaterais ou áreas afetadas.

### ✅ Checklist

Gere automaticamente um checklist apropriado com base no tipo de mudança.

## Regras

* Seja conciso, mas completo
* Não invente contexto que não pode ser inferido
* Use linguagem profissional
* Prefira bullets ao invés de parágrafos longos
* Se algo não estiver claro no diff, sinalize como suposição

## Saída esperada

Retorne apenas o conteúdo do Pull Request pronto para ser colado no GitHub.
```