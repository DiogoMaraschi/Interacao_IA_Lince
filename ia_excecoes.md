# 🤖 IA como Apoio — Exceções em Dart

> Atividade da Lince Tech Academy utilizando IA como ferramenta de apoio nos estudos de Dart.
> A formatação foi feita com auxílio de IA, mas as perguntas e os campos de meus entendimentos foram preenchidos por mim.

---

# 📚 Conteúdos estudados

- Assert
- Erros e exceções
- Try, Catch e Finally
- Lançamento de exceções
- Rethrow
- Tratamento de erros
- Boas práticas com exceções

---

# ❓ Pergunta 1

## Pergunta feita para IA

```txt
Qual a diferença entre um erro e uma exceção em Dart?
```

## 💡 Resposta da IA

- Erros (`Error`) representam problemas graves de programação.
- Exceções (`Exception`) representam situações inesperadas que podem ser tratadas.
- Erros geralmente indicam falhas que não deveriam ocorrer.
- Exceções são utilizadas para situações previstas durante a execução.

## 🧠 Meu entendimento

- Errors normalmente indicam falhas de lógica ou problemas mais graves da aplicação.
- Exceptions representam situações que podem acontecer durante a execução e que podem ser tratadas pelo programa.
- Exemplo: acessar um índice inexistente em uma lista pode gerar uma exceção que pode ser tratada.

---

# ❓ Pergunta 2

## Pergunta feita para IA

```txt
Em quais situações devo esperar encontrar um erro, e em quais devo esperar uma exceção?
```

## 💡 Resposta da IA

- Erros acontecem por falhas de programação.
- Exceções acontecem por entradas inválidas, arquivos inexistentes, falhas de rede ou dados incorretos.
- Exceções normalmente podem ser recuperadas.

## 🧠 Meu entendimento

- Se o problema está relacionado a uma regra de negócio ou entrada do usuário, geralmente é uma exceção.
- Se o problema está relacionado ao próprio código, geralmente é um erro.
- Exceções permitem que a aplicação continue executando após o tratamento.

---

# ❓ Pergunta 3

## Pergunta feita para IA

```txt
O que fazem os blocos try, catch e finally em Dart?
```

## 💡 Resposta da IA

- `try` executa um trecho de código que pode gerar exceções.
- `catch` captura e trata exceções lançadas.
- `finally` executa sempre, independentemente de ocorrer erro ou não.

## 🧠 Meu entendimento

- O código que pode falhar fica dentro do `try`.
- O tratamento do erro fica dentro do `catch`.
- O `finally` é útil para liberar recursos ou executar alguma ação obrigatória no final do fluxo.

---

# ❓ Pergunta 4

## Pergunta feita para IA

```txt
Como posso capturar diferentes tipos de exceções usando catch?
```

## 💡 Resposta da IA

```dart
try {
  // código
} on FormatException {
  print('Formato inválido');
} on Exception catch (e) {
  print(e);
}
```

## 🧠 Meu entendimento

- Posso utilizar vários blocos `on` para tratar exceções específicas.
- Isso torna o tratamento mais preciso e facilita a identificação de problemas.

---

# ❓ Pergunta 5

## Pergunta feita para IA

```txt
Em quais situações é útil usar o bloco finally?
```

## 💡 Resposta da IA

- Fechamento de arquivos.
- Encerramento de conexões.
- Liberação de recursos.
- Execução de ações obrigatórias ao final do processo.

## 🧠 Meu entendimento

- O `finally` sempre será executado.
- É uma boa prática quando alguma ação precisa ocorrer independentemente do sucesso ou falha da operação.

---

# ❓ Pergunta 6

## Pergunta feita para IA

```txt
Por que eu precisaria lançar uma exceção em meu código?
```

## 💡 Resposta da IA

- Para informar que uma condição inválida foi encontrada.
- Para interromper a execução de uma operação inválida.
- Para permitir que outra parte do programa trate o problema.

## 🧠 Meu entendimento

- Lançar exceções permite sinalizar problemas de forma explícita.
- Isso facilita a manutenção e evita comportamentos inesperados.

---

# ❓ Pergunta 7

## Pergunta feita para IA

```txt
Como posso personalizar mensagens de erro ao lançar exceções?
```

## 💡 Resposta da IA

```dart
throw Exception('Usuário não encontrado');
```

## 🧠 Meu entendimento

- Mensagens claras ajudam muito durante a depuração.
- O ideal é informar exatamente qual problema ocorreu para facilitar o diagnóstico.

---

# ❓ Pergunta 8

## Pergunta feita para IA

```txt
Quais são as melhores práticas para lançar exceções em Dart?
```

## 💡 Resposta da IA

- Utilizar mensagens claras.
- Lançar exceções apenas quando necessário.
- Não utilizar exceções para controle normal do fluxo.
- Tratar exceções apenas quando for possível resolver o problema.

## 🧠 Meu entendimento

- Exceções devem representar situações excepcionais.
- Não devem substituir validações comuns ou estruturas condicionais.

---

# ❓ Pergunta 9

## Pergunta feita para IA

```txt
Qual a diferença entre usar assert e lançar uma exceção para verificar condições?
```

## 💡 Resposta da IA

- `assert` é utilizado principalmente durante o desenvolvimento.
- Exceções funcionam também em produção.
- `assert` valida condições que nunca deveriam ser falsas.

## 🧠 Meu entendimento

- Assert é uma ferramenta para detectar erros de programação.
- Exceções são mais adequadas para situações que podem ocorrer durante a execução da aplicação.

---

# ❓ Pergunta 10

## Pergunta feita para IA

```txt
Em quais situações o assert é mais útil durante o desenvolvimento?
```

## 💡 Resposta da IA

```dart
assert(idade >= 0);
```

## 🧠 Meu entendimento

- Assert ajuda a identificar rapidamente estados inválidos do sistema.
- É útil para garantir pré-condições durante o desenvolvimento e testes.

---

# ❓ Pergunta 11

## Pergunta feita para IA

```txt
Como organizar minhas exceções no projeto?
```

## 💡 Resposta da IA

- Criar exceções específicas para cada domínio.
- Separar exceções em arquivos próprios.
- Utilizar nomes claros e consistentes.

## 🧠 Meu entendimento

- Em projetos maiores é interessante criar exceções personalizadas.
- Isso facilita o tratamento e a manutenção do código.

---

# ❓ Pergunta 12

## Pergunta feita para IA

```txt
Como os erros e exceções afetam a execução do meu programa?
```

## 💡 Resposta da IA

- Exceções interrompem o fluxo atual até serem tratadas.
- Erros geralmente encerram a execução da aplicação.
- O tratamento adequado evita falhas inesperadas.

## 🧠 Meu entendimento

- Quando uma exceção é lançada, o Dart procura um bloco `catch` para tratá-la.
- Caso não exista tratamento, a aplicação pode ser encerrada.
- Entender esse fluxo ajuda a escrever programas mais robustos.

---

# ❓ Pergunta 13

## Pergunta feita para IA

```txt
Qual a diferença entre throw e rethrow?
```

## 💡 Resposta da IA

- `throw` cria e lança uma nova exceção.
- `rethrow` relança uma exceção já capturada por um bloco `catch`.

## 🧠 Meu entendimento

- `throw` é utilizado quando quero gerar uma exceção.
- `rethrow` é utilizado quando quero registrar ou tratar parcialmente um erro e permitir que outra camada da aplicação continue tratando a mesma exceção.
- O `rethrow` preserva a origem da exceção, facilitando a depuração.

---

# ✅ Conclusão

- Com essa atividade consegui entender melhor a diferença entre erros e exceções em Dart, além de aprender como utilizar os blocos `try`, `catch` e `finally` para tratar problemas durante a execução do programa.
- Também compreendi quando utilizar `throw`, `rethrow` e `assert`, além da importância de criar mensagens de erro claras e objetivas.
- A IA ajudou a esclarecer conceitos rapidamente e a fornecer exemplos simples para reforçar o entendimento sobre tratamento de exceções e boas práticas em Dart.