# 🤖 IA como Apoio — Concorrência com Future em Dart

> Atividade da Lince Tech Academy utilizando IA como ferramenta de apoio nos estudos de Dart.
> A formatação foi feita com auxílio de IA, mas as perguntas e os campos de meus entendimentos foram preenchidas por mim.

---

# 📚 Conteúdos estudados

* Programação síncrona
* Programação assíncrona
* Future
* await
* async
* Tratamento de erros em Future
* Execução paralela de tarefas
* Future.error
* Simulação de demora

---

# ❓ Pergunta 1

## Pergunta feita para IA

```txt
O que é um Future em Dart e como ele me ajuda a lidar com tarefas que levam tempo?
```

## 💡 Resposta da IA

* `Future` representa um valor que estará disponível futuramente.
* Permite executar tarefas demoradas sem bloquear o restante do programa.
* Muito utilizado para chamadas de API, leitura de arquivos e banco de dados.

## 🧠 Meu entendimento

* Future funciona como uma promessa de retorno.
* O código continua executando enquanto espera o resultado.
* Isso melhora experiência do usuário e evita travamentos.

---

# ❓ Pergunta 2

## Pergunta feita para IA

```txt
O que significam os termos assíncrono e síncrono?
```

## 💡 Resposta da IA

* Síncrono executa uma tarefa por vez.
* Assíncrono permite continuar executando enquanto espera outra tarefa terminar.

Exemplo conceitual:

```dart
print('Inicio');
print('Fim');
```

vs

```dart
print('Inicio');
await carregar();
print('Fim');
```

## 🧠 Meu entendimento

* Código síncrono segue ordem rígida.
* Código assíncrono permite esperar resultados sem parar todo o programa.

---

# ❓ Pergunta 3

## Pergunta feita para IA

```txt
O que acontece se um Future falhar e como posso lidar com esse erro?
```

## 💡 Resposta da IA

* Futures podem lançar exceções.
* Podemos utilizar `try` e `catch`.

Exemplo:

```dart
try {
  await buscarDados();
} catch (e) {
  print(e);
}
```

## 🧠 Meu entendimento

* Tratamento de erro continua sendo importante em código assíncrono.
* O `await` facilita capturar exceções.

---

# ❓ Pergunta 4

## Pergunta feita para IA

```txt
Existe uma forma de executar várias tarefas assíncronas em paralelo?
```

## 💡 Resposta da IA

Exemplo:

```dart
await Future.wait([
 carregarUsuario(),
 carregarProdutos(),
]);
```

* `Future.wait()` espera várias tarefas terminarem.

## 🧠 Meu entendimento

* Permite otimizar tempo de execução.
* As tarefas começam juntas e esperamos todas finalizarem.

---

# ❓ Pergunta 5

## Pergunta feita para IA

```txt
Em quais situações devo usar Futures em meu código Dart?
```

## 💡 Resposta da IA

* Chamadas HTTP
* Leitura de arquivos
* Banco de dados
* Processos demorados

## 🧠 Meu entendimento

* Sempre que existir espera por recurso externo.
* Evita bloquear a interface da aplicação.

---

# ❓ Pergunta 6

## Pergunta feita para IA

```txt
Quais cuidados devo tomar não usando await em funções Future?
```

## 💡 Resposta da IA

* O código pode continuar antes do resultado chegar.
* Erros podem não ser capturados corretamente.

## 🧠 Meu entendimento

* Sem `await`, preciso controlar o fluxo manualmente.
* Posso receber resultados em ordem inesperada.

---

# ❓ Pergunta 7

## Pergunta feita para IA

```txt
Como lidar com erros usando Future?
```

## 💡 Resposta da IA

Exemplo:

```dart
buscar()
.then((valor) {
 print(valor);
}).catchError((erro) {
 print(erro);
});
```

## 🧠 Meu entendimento

* Existem duas formas principais:
* `try/catch`
* `then/catchError`

---

# ❓ Pergunta 8

## Pergunta feita para IA

```txt
De quais formas posso esperar que um Future seja concluído e obter o resultado?
```

## 💡 Resposta da IA

Exemplos:

```dart
await carregar();
```

ou

```dart
carregar().then((valor) {});
```

## 🧠 Meu entendimento

* `await` deixa leitura mais simples.
* `then()` mostra claramente fluxo por callbacks.

---

# ❓ Pergunta 9

## Pergunta feita para IA

```txt
Como posso simular um erro em um Future usando Future.error?
```

## 💡 Resposta da IA

Exemplo:

```dart
Future<String> buscar() {
 return Future.error('Erro');
}
```

## 🧠 Meu entendimento

* Future.error ajuda testar cenários de falha.

---

# ❓ Pergunta 10

## Pergunta feita para IA

```txt
Como posso criar uma função que retorna um Future que simula uma demora do programa?
```

## 💡 Resposta da IA

Exemplo:

```dart
Future<String> carregar() async {
 await Future.delayed(
   Duration(seconds: 2),
 );

 return 'Concluído';
}
```

## 🧠 Meu entendimento

* `Future.delayed()` é útil para testar carregamentos.
* Ajuda entender funcionamento da concorrência.

---

# ❓ Pergunta 11

## Pergunta feita para IA

```txt
Qual a diferença entre usar then() e await?
```

## 💡 Resposta da IA

* `then()` usa callbacks.
* `await` deixa o fluxo parecido com código síncrono.

## 🧠 Meu entendimento

* Achei `await` mais legível.
* `then()` pode ser útil em encadeamentos.

---

# ❓ Pergunta 12

## Pergunta feita para IA

```txt
O Future executa em outra thread?
```

## 💡 Resposta da IA

* Não necessariamente.
* Futures trabalham com fila de eventos.

## 🧠 Meu entendimento

* Concorrência não significa múltiplas threads.
* O Dart organiza execução utilizando Event Loop.

---

# ✅ Conclusão

* Com essa atividade consegui entender melhor como Dart trabalha com concorrência utilizando Future.
* Aprendi diferença entre código síncrono e assíncrono, formas de esperar resultados e como tratar erros.
* Também entendi que Future não significa execução paralela automaticamente, mas sim controle de tarefas que levam tempo.
* A IA ajudou como apoio para visualizar conceitos e exemplos antes da implementação prática.
