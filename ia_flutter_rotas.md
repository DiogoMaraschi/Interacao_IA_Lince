# 🤖 IA como Apoio — Flutter Rotas

> Atividade desenvolvida utilizando IA como ferramenta de apoio para estudos sobre navegação e rotas no Flutter.

---

# 📚 Conteúdos estudados

- Rotas anônimas
- Rotas nomeadas
- Navigator
- Pilha de navegação
- Passagem de parâmetros
- Retorno de valores entre telas
- Boas práticas

---

# 1️⃣ Rotas anônimas

## ❓ Pergunta feita para IA

```txt
O que são rotas anônimas em Flutter e como elas funcionam?
```

## 💡 Resposta da IA

Rotas anônimas são navegações onde a tela de destino é criada diretamente no momento da navegação, sem possuir um nome registrado no MaterialApp.

Normalmente são feitas utilizando o método `Navigator.push()` junto com `MaterialPageRoute`.

## 💻 Exemplo

```dart
Navigator.push(
  context,
  MaterialPageRoute(
    builder: (context) {
      return TelaDetalhes();
    },
  ),
);
```

## 🧠 Meu entendimento

Entendi que nas rotas anônimas eu crio diretamente a próxima tela no momento que quero navegar. É simples para projetos pequenos, mas pode dificultar a organização quando existem muitas telas.

---

# 2️⃣ Métodos do Navigator

## ❓ Pergunta feita para IA

```txt
Quais métodos do Navigator são comumente utilizados e por quê?
```

## 💡 Resposta da IA

O Navigator controla uma pilha de telas no Flutter.

Métodos comuns:

- `push()` → adiciona uma nova tela.
- `pushNamed()` → navega usando uma rota cadastrada.
- `pop()` → remove a tela atual e volta.
- `pushReplacement()` → substitui uma tela por outra.
- `pushNamedAndRemoveUntil()` → remove várias telas da pilha.

## 💻 Exemplo

```dart
Navigator.pop(context);
```

## 🧠 Meu entendimento

O Navigator funciona como uma pilha. Cada nova tela é colocada por cima da anterior e o pop remove a tela atual.

---

# 3️⃣ Navigator.push()

## ❓ Pergunta feita para IA

```txt
Qual a função do Navigator.push() na navegação com rotas anônimas?
```

## 💡 Resposta da IA

O `Navigator.push()` adiciona uma nova rota na pilha de navegação.

A tela anterior continua existindo abaixo da nova tela.

## 💻 Exemplo

```dart
Navigator.push(
  context,
  MaterialPageRoute(
    builder: (context) => Tela2(),
  ),
);
```

## 🧠 Meu entendimento

O push não substitui a tela atual, ele apenas coloca uma nova tela por cima permitindo voltar depois com pop.

---

# 4️⃣ Vantagens e desvantagens das rotas anônimas

## ❓ Pergunta feita para IA

```txt
Quais as vantagens e desvantagens de usar rotas anônimas?
```

## 💡 Resposta da IA

Vantagens:

- Simples de implementar.
- Fácil para poucas telas.
- Não precisa configurar rotas antes.

Desvantagens:

- Pode ficar desorganizado em projetos grandes.
- As telas ficam mais acopladas.
- Dificulta manutenção.

## 💻 Exemplo

```dart
Navigator.push(
  context,
  MaterialPageRoute(
    builder: (_) => TelaPerfil(),
  ),
);
```

## 🧠 Meu entendimento

Rotas anônimas são boas para navegações simples, porém em aplicativos maiores as rotas nomeadas deixam o projeto mais organizado.

---

# 5️⃣ Rotas nomeadas

## ❓ Pergunta feita para IA

```txt
O que são rotas nomeadas em Flutter e como elas funcionam?
```

## 💡 Resposta da IA

Rotas nomeadas são telas registradas utilizando um nome.

Esse registro normalmente acontece dentro do MaterialApp usando o atributo `routes`.

Depois é possível navegar apenas chamando o nome da rota.

## 💻 Exemplo

```dart
MaterialApp(
  routes: {
    '/home': (context) => TelaHome(),
    '/perfil': (context) => TelaPerfil(),
  },
);
```

## 🧠 Meu entendimento

Entendi que funciona como uma tabela onde cada texto representa uma tela do aplicativo.

---
---

# 6️⃣ Navegar para rota nomeada

## ❓ Pergunta feita para IA

```txt
Como posso navegar para uma rota nomeada específica?
```

## 💡 Resposta da IA

Para navegar utilizando rotas nomeadas usamos o método `Navigator.pushNamed()`.

Ele procura a rota cadastrada no `MaterialApp` e adiciona essa tela na pilha de navegação.

## 💻 Exemplo

```dart
Navigator.pushNamed(
  context,
  '/perfil',
);
```

Também pode ser escrito usando:

```dart
Navigator.of(context).pushNamed(
  '/perfil',
);
```

## 🧠 Meu entendimento

Entendi que as duas formas usam o Navigator. A diferença é apenas a escrita, mas ambas acessam o navegador da aplicação.

---

# 7️⃣ Vantagens das rotas nomeadas

## ❓ Pergunta feita para IA

```txt
Quais as vantagens de usar rotas nomeadas em relação às rotas anônimas?
```

## 💡 Resposta da IA

As rotas nomeadas ajudam a organizar aplicativos maiores.

Vantagens:

- Centralizam as rotas.
- Evitam criar telas manualmente em vários lugares.
- Facilitam manutenção.
- Melhoram a organização do projeto.

## 💻 Exemplo

```dart
MaterialApp(
  routes: {
    '/login': (_) => Login(),
    '/home': (_) => Home(),
  },
);
```

## 🧠 Meu entendimento

Com rotas nomeadas consigo deixar todas as telas registradas em um local, facilitando alterações futuras.

---

# 8️⃣ Definindo rotas nomeadas

## ❓ Pergunta feita para IA

```txt
Como posso definir rotas nomeadas em meu aplicativo Flutter?
```

## 💡 Resposta da IA

As rotas são configuradas dentro do `MaterialApp`, utilizando o atributo `routes`.

Cada chave representa o nome da rota e o valor representa a tela que será aberta.

## 💻 Exemplo

```dart
MaterialApp(
  initialRoute: '/',

  routes: {
    '/': (context) => TelaInicial(),
    '/detalhes': (context) => TelaDetalhes(),
  },
);
```

## 🧠 Meu entendimento

O MaterialApp funciona como o controlador principal das rotas, sabendo qual tela abrir para cada nome.

---

# 9️⃣ Passando parâmetros em rotas

## ❓ Pergunta feita para IA

```txt
Como posso acessar os parâmetros passados em uma rota nomeada?
```

## 💡 Resposta da IA

Podemos enviar informações através do atributo `arguments` do Navigator.

Na tela de destino usamos `ModalRoute` para recuperar esses dados.

## 💻 Exemplo

Enviando:

```dart
Navigator.pushNamed(
  context,
  '/detalhes',
  arguments: 'Produto 1',
);
```

Recebendo:

```dart
final argumento =
    ModalRoute.of(context)!.settings.arguments;
```

## 🧠 Meu entendimento

Os argumentos permitem levar informações de uma tela para outra, como um id de produto ou informações de usuário.

---

# 🔟 Classe para argumentos

## ❓ Pergunta feita para IA

```txt
Como posso passar mais de um parâmetro em uma rota nomeada?
```

## 💡 Resposta da IA

Uma boa prática é criar uma classe contendo os dados que precisam ser enviados.

Assim podemos enviar vários valores dentro de um único objeto.

## 💻 Exemplo

```dart
class Argumentos {
  final int id;
  final String nome;

  Argumentos(
    this.id,
    this.nome,
  );
}
```

Uso:

```dart
Navigator.pushNamed(
  context,
  '/perfil',
  arguments: Argumentos(
    1,
    'Pedro',
  ),
);
```

## 🧠 Meu entendimento

Criar uma classe deixa o envio de dados mais organizado do que passar vários valores separados.

---
---

# 1️⃣1️⃣ Parâmetros opcionais

## ❓ Pergunta feita para IA

```txt
Como posso tornar os parâmetros opcionais em uma rota nomeada?
```

## 💡 Resposta da IA

Como os argumentos podem vir nulos, podemos utilizar o operador `?` e verificar antes de usar.

Também podemos criar valores padrão.

## 💻 Exemplo

```dart
final argumento =
    ModalRoute.of(context)
        ?.settings
        .arguments;
```

## 🧠 Meu entendimento

Nem sempre uma rota precisa receber dados. Usar null safety evita erros quando nenhum argumento é enviado.

---

# 1️⃣2️⃣ Retornando valores entre telas

## ❓ Pergunta feita para IA

```txt
Como retornar um valor ao finalizar uma rota no Flutter?
```

## 💡 Resposta da IA

O método `pop()` pode fechar uma tela e enviar um valor de volta para a tela anterior.

A tela anterior pode esperar esse retorno utilizando `await`.

## 💻 Exemplo

Tela 1:

```dart
final resultado =
    await Navigator.pushNamed(
      context,
      '/confirmacao',
    );
```

Tela 2:

```dart
Navigator.of(context).pop(
  true,
);
```

## 🧠 Meu entendimento

O push envia para uma nova tela, enquanto o pop pode voltar trazendo uma resposta.

Exemplo: uma tela de confirmação pode retornar verdadeiro ou falso.

---

# 1️⃣3️⃣ Cuidados ao usar rotas

## ❓ Pergunta feita para IA

```txt
Quais cuidados devo ter ao usar as rotas?
```

## 💡 Resposta da IA

Alguns cuidados importantes:

- Evitar nomes duplicados.
- Evitar passar muitos dados por argumento.
- Verificar valores nulos.
- Organizar nomes das rotas.
- Evitar criar vários MaterialApp.

## 💻 Exemplo

```dart
static const routeName = '/produto';
```

## 🧠 Meu entendimento

Criar constantes para nomes das rotas ajuda a evitar erros de digitação e facilita mudanças futuras.

---

# 1️⃣4️⃣ Boas práticas em rotas

## ❓ Pergunta feita para IA

```txt
Quais as boas práticas ao usar rotas em Flutter?
```

## 💡 Resposta da IA

Boas práticas:

- Usar rotas nomeadas em projetos maiores.
- Separar cada tela em um arquivo.
- Usar constantes para nomes.
- Criar classes para argumentos.
- Usar pop para retornar resultados.

## 💻 Exemplo

```dart
class TelaProduto {
  static const rota = '/produto';
}
```

## 🧠 Meu entendimento

Rotas organizadas deixam o projeto mais fácil de crescer e dar manutenção.

---

# 1️⃣5️⃣ Diferença entre arguments e pop

## ❓ Pergunta feita para IA

```txt
Qual a diferença entre enviar argumentos e retornar valores com pop?
```

## 💡 Resposta da IA

Arguments envia dados para a próxima tela.

Pop retorna informações para a tela anterior.

## 💻 Exemplo

Indo:

```dart
Navigator.pushNamed(
  context,
  '/editar',
  arguments: usuario,
);
```

Voltando:

```dart
Navigator.pop(
  context,
  usuarioAtualizado,
);
```

## 🧠 Meu entendimento

Arguments é usado no caminho de ida e pop com valor é usado no caminho de volta.

---

# ✅ Conclusão

A utilização da IA ajudou a entender melhor como funciona a navegação no Flutter.

Foi possível compreender rotas anônimas, rotas nomeadas, passagem de parâmetros e retorno de valores.

Também entendi que o Navigator trabalha como uma pilha, onde novas telas são adicionadas com push e removidas com pop.