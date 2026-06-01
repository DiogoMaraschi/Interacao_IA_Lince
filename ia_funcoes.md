# 🤖 IA como Apoio — Funções em Dart

> Atividade desenvolvida utilizando IA como ferramenta de apoio para estudos sobre funções em Dart.

---

# 📚 Conteúdos estudados

* Introdução a funções
* Funções com parâmetros
* Funções com retorno
* Parâmetros opcionais
* Parâmetros nomeados
* Funções como objeto
* Callbacks
* Organização de código

---

# 1️⃣ Introdução às Funções

## ❓ Pergunta feita para IA

```txt
Quais cuidados devo ter ao criar funções em dart?
```

## 💡 Resposta da IA

* Utilizar nomes claros e descritivos.
* Fazer uma única responsabilidade por função.
* Evitar funções muito grandes.
* Utilizar tipos de retorno explícitos.

## 💻 Exemplo

```dart
String saudar(String nome) {
  return 'Olá, $nome';
}
```

## 🧠 Meu entendimento
- Funções ajudam a organizar o código e evitar repetição.
- É importante que tenham uma responsabilidade bem definida.
- Nomes claros facilitam a leitura e manutenção do código.
---

# 2️⃣ Funções Recursivas

## ❓ Pergunta feita para IA

```txt
Posso chamar minha função dentro dela mesma?
```

## 💡 Resposta da IA

Sim. Esse conceito é chamado de recursão. Deve ser utilizado com cuidado para evitar loops infinitos.

## 💻 Exemplo

```dart
int contagemRegressiva(int numero) {
  if (numero == 0) {
    return 0;
  }

  return contagemRegressiva(numero - 1);
}
```

## 🧠 Meu entendimento
- A função pode chamar ela mesma, desde que exista uma condição de parada.
- Sem uma condição de parada ocorre recursão infinita e pode causar estouro de memória.
- Nem todo problema precisa de recursão, muitas vezes um loop resolve de forma mais simples.

---

# 3️⃣ Quantidade de Parâmetros

## ❓ Pergunta feita para IA

```txt
Existe limite de parâmetros a serem recebidos em uma função?
```

## 💡 Resposta da IA

Não existe um limite prático comum, porém funções com muitos parâmetros costumam indicar necessidade de refatoração.

## 💻 Exemplo

```dart
void criarUsuario(
  String nome,
  int idade,
  String email,
) {
  print(nome);
}
```

## 🧠 Meu entendimento
- Não existe um limite que normalmente afete o desenvolvimento.
- Muitas vezes uma função com muitos parâmetros pode indicar que ela está assumindo responsabilidades demais.
- Dependendo do caso pode ser melhor criar uma classe para agrupar informações relacionadas.
---

# 4️⃣ Uso de dynamic em Funções

## ❓ Pergunta feita para IA

```txt
É recomendado usar dynamic nos parâmetros de uma função?
```

## 💡 Resposta da IA

O uso de `dynamic` reduz a segurança de tipos. Deve ser utilizado apenas quando realmente necessário.

## 💻 Exemplo

```dart
void imprimir(dynamic valor) {
  print(valor);
}
```

## 🧠 Meu entendimento
- Assim como nas variáveis, o uso de dynamic reduz a segurança de tipos.
- O ideal é deixar claro o tipo esperado pelo parâmetro.
- Utilizar dynamic apenas quando realmente for necessário receber tipos diferentes.
---

# 5️⃣ Parâmetros Opcionais e Obrigatórios

## ❓ Pergunta feita para IA

```txt
Quando usar os operadores de valores opcionais e valores requeridos em uma função dart?
```

## 💡 Resposta da IA

* Utilize `required` quando o parâmetro for obrigatório.
* Utilize parâmetros opcionais quando fizer sentido permitir ausência de valor.

## 💻 Exemplo

```dart
void criarUsuario({
  required String nome,
  int? idade,
}) {
  print(nome);
}
```

## 🧠 Meu entendimento
- Utilizar required quando a função não consegue executar sem aquele valor.
- Utilizar opcionais quando faz sentido existir um valor ausente.
- O Dart ajuda bastante com isso através do Null Safety.
---

# 6️⃣ Parâmetros Nomeados

## ❓ Pergunta feita para IA

```txt
O que são parâmetros nomeados em uma função?
```

## 💡 Resposta da IA

Permitem informar explicitamente qual parâmetro está sendo enviado para a função.

## 💻 Exemplo

```dart
void cadastrarUsuario({
  required String nome,
  required String email,
}) {
  print(nome);
}
```

Uso:

```dart
cadastrarUsuario(
  nome: 'Diogo',
  email: 'teste@email.com',
);
```

## 🧠 Meu entendimento
- Melhoram muito a legibilidade das chamadas de função.
- Evitam confusão quando existem vários parâmetros do mesmo tipo.
- São muito utilizados no Flutter para construção de widgets.
---

# 7️⃣ Function como Tipo

## ❓ Pergunta feita para IA

```txt
Quais métodos existem para variáveis do tipo Function em dart?
```

## 💡 Resposta da IA

Funções podem ser armazenadas em variáveis, passadas como parâmetros e retornadas por outras funções.

## 💻 Exemplo

```dart
int dobrar(int numero) {
  return numero * 2;
}

Function funcao = dobrar;

print(funcao(5));
```

## 🧠 Meu entendimento
- Em Dart funções são objetos de primeira classe.
- Posso armazenar uma função em uma variável, passar como parâmetro ou retornar de outra função.
- Esse conceito é bastante utilizado em callbacks.
---

# 8️⃣ Diferença entre olaMundo e olaMundo()

## ❓ Pergunta feita para IA

```txt
Qual a diferença entre chamar minha função chamado olaMundo das seguintes formas "olaMundo" e "olaMundo()".
```

## 💡 Resposta da IA

* `olaMundo` referencia a função.
* `olaMundo()` executa a função.

## 💻 Exemplo

```dart
void olaMundo() {
  print('Olá');
}

Function referencia = olaMundo;

olaMundo();
```

## 🧠 Meu entendimento
- olaMundo representa uma referência para a função.
- olaMundo() executa a função.
- Isso é importante quando trabalhamos com callbacks e eventos.
---

# 9️⃣ Funções Trabalhando com Strings

## ❓ Pergunta feita para IA

```txt
Mostre exemplos de uma função tratando strings com seus diferentes métodos.
```

## 💡 Resposta da IA

Funções podem utilizar métodos nativos das strings para transformar dados.

## 💻 Exemplo

```dart
String formatarNome(String nome) {
  return nome.toUpperCase();
}
```

```dart
String removerEspacos(String texto) {
  return texto.trim();
}
```

## 🧠 Meu entendimento
- Funções podem encapsular transformações de texto para reaproveitamento.
- Métodos como trim(), split(), toUpperCase() e toLowerCase() são bastante úteis.
- Centralizar esse tipo de lógica evita duplicação de código.
---

# 🔟 Maus Usos de Funções

## ❓ Pergunta feita para IA

```txt
Traga exemplos de mau uso de funções.
```

## 💡 Resposta da IA

* Funções muito grandes.
* Muitas responsabilidades.
* Uso excessivo de dynamic.
* Muitos parâmetros.

## 💻 Exemplo

```dart
void processarTudo() {
  // cadastro
  // validação
  // cálculo
  // envio de email
  // relatório
}
```

## 🧠 Meu entendimento
- Funções muito grandes ficam difíceis de entender e manter.
- Misturar várias responsabilidades na mesma função aumenta a complexidade.
- É interessante dividir o problema em funções menores e mais específicas.
---

# 1️⃣1️⃣ Organização de Funções

## ❓ Pergunta feita para IA

```txt
Como organizar minhas funções no código?
```

## 💡 Resposta da IA

* Separar responsabilidades.
* Agrupar funções relacionadas.
* Utilizar nomes consistentes.
* Evitar duplicação de código.

## 💻 Exemplo

```dart
String validarNome(String nome) {
  return nome.trim();
}

void salvarUsuario(String nome) {
  print(nome);
}
```

## 🧠 Meu entendimento
- Organizar funções por responsabilidade deixa o código mais limpo.
- Evitar duplicação de lógica ajuda na manutenção.
- Funções relacionadas podem ficar agrupadas na mesma classe ou arquivo.
---

# 1️⃣2️⃣ Funções com Retorno

## ❓ Pergunta feita para IA

```txt
Quando devo retornar um valor em uma função?
```

## 💡 Resposta da IA

Retorne valores quando o resultado da operação precisar ser utilizado em outra parte do código.

## 💻 Exemplo

```dart
int somar(int a, int b) {
  return a + b;
}
```

## 🧠 Meu entendimento
- Utilizo retorno quando preciso reaproveitar o resultado em outro lugar do código.
- Funções sem retorno normalmente executam alguma ação específica.
- O tipo de retorno ajuda a documentar o comportamento da função.
---

# 1️⃣3️⃣ Callbacks

## ❓ Pergunta feita para IA

```txt
O que é um callback em dart?
```

## 💡 Resposta da IA

Callback é uma função passada como parâmetro para outra função, permitindo executar comportamentos personalizados.

## 💻 Exemplo

```dart
void executar(Function acao) {
  acao();
}

executar(() {
  print('Executando callback');
});
```

## 🧠 Meu entendimento
- Callback é uma função passada como parâmetro para outra função.
- Quem recebe o callback decide quando executá-lo.
- Esse conceito é muito utilizado em Flutter em eventos como clique de botões e interações do usuário.
---

# 1️⃣4️⃣ Arrow Functions

## ❓ Pergunta feita para IA

```txt
Quando utilizar arrow functions (=>) em dart?
```

## 💡 Resposta da IA

São recomendadas para funções simples que possuem apenas uma expressão.

## 💻 Exemplo

```dart
int dobrar(int numero) => numero * 2;
```

## 🧠 Meu entendimento
- São úteis para funções pequenas e objetivas.
- Deixam o código mais compacto quando existe apenas uma expressão.
- Quando a lógica fica maior, normalmente a função tradicional fica mais legível.
---

# ✅ Conclusão

A utilização da IA ajudou a compreender conceitos fundamentais sobre funções em Dart, incluindo parâmetros, retorno de valores, callbacks e boas práticas de organização de código.
