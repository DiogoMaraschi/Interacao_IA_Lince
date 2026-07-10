# 🤖 IA como Apoio — Flutter Gerenciamento de Estados

> Atividade desenvolvida utilizando IA como ferramenta de apoio para estudos sobre gerenciamento de estados em Flutter utilizando Provider.

---

# 📚 Conteúdos estudados

- Estado local
- Estado compartilhado
- Gerenciamento de estados
- Provider
- ChangeNotifierProvider
- ChangeNotifier
- Consumer
- Reconstrução de widgets

---

# 1️⃣ Gerenciamento de estados

## ❓ Pergunta feita para IA

```txt
O que é gerenciamento de estados em Flutter e por que é importante?
```

## 💡 Resposta da IA

Gerenciamento de estados é a forma como uma aplicação controla, altera e compartilha informações que podem mudar durante sua execução.

Um estado pode ser qualquer informação dinâmica, como:

- usuário logado
- contador
- tema escolhido
- dados vindos de uma API

Quando esse estado muda, a interface precisa ser atualizada.

## 💻 Exemplo

```dart
int contador = 0;

setState(() {
  contador++;
});
```

## 🧠 Meu entendimento

O estado representa informações que podem mudar no aplicativo. O gerenciamento de estado define como essas informações serão atualizadas e compartilhadas com os widgets.

---

# 2️⃣ Estado local e estado global

## ❓ Pergunta feita para IA

```txt
Qual a diferença entre estado local e estado global em um aplicativo Flutter?
```

## 💡 Resposta da IA

Estado local pertence normalmente a apenas um widget, sendo controlado por um StatefulWidget.

Estado compartilhado é utilizado quando vários widgets precisam acessar a mesma informação.

## 💻 Exemplo estado local

```dart
class Contador extends StatefulWidget {

}

class _ContadorState extends State<Contador> {

  int valor = 0;

}
```

## 💻 Exemplo estado compartilhado

```dart
Provider
 |
 ├── Tela A
 |
 └── Tela B
```

## 🧠 Meu entendimento

Se apenas um widget precisa controlar uma informação posso utilizar StatefulWidget.

Quando vários widgets precisam acessar o mesmo valor, usar um gerenciador como Provider ajuda na organização.

---

# 3️⃣ Vantagens de usar gerenciador de estados

## ❓ Pergunta feita para IA

```txt
Quais as vantagens de usar um gerenciador de estados em um projeto Flutter?
```

## 💡 Resposta da IA

Algumas vantagens:

- Evita passar valores manualmente por vários widgets.
- Centraliza regras de alteração.
- Facilita manutenção.
- Permite compartilhar dados na árvore de widgets.
- Melhora organização do código.

## 💻 Exemplo sem gerenciador

```txt
Tela
 |
 Widget
 |
 Widget filho
 |
 variável
```

## 💻 Exemplo com Provider

```txt
Provider
 |
 Qualquer widget abaixo acessa
```

## 🧠 Meu entendimento

O Provider evita ficar enviando informações por vários construtores até chegar no widget que realmente precisa delas.

---

# 4️⃣ Provider

## ❓ Pergunta feita para IA

```txt
O que é o pacote Provider em Flutter e para que ele serve?
```

## 💡 Resposta da IA

Provider é uma biblioteca de gerenciamento de estados baseada no InheritedWidget.

Ele permite disponibilizar valores em um ponto da árvore de widgets para que widgets descendentes possam acessar.

## 💻 Exemplo

```dart
Provider(
  create: (context) => MeuObjeto(),
  child: MeuApp(),
);
```

## 🧠 Meu entendimento

O Provider funciona de forma hierárquica. Os widgets abaixo dele conseguem acessar os dados disponibilizados.

---

# 5️⃣ Evitando reconstruções desnecessárias

## ❓ Pergunta feita para IA

```txt
Como o Provider ajuda a evitar a reconstrução desnecessária de widgets?
```

## 💡 Resposta da IA

O Provider permite que apenas os widgets que utilizam determinado estado sejam reconstruídos quando ocorre uma alteração.

Diferente de atualizar uma tela inteira, apenas partes necessárias podem ser redesenhadas.

## 💻 Exemplo

```dart
Consumer<MeuProvider>(
  builder: (context, provider, child) {
    return Text(
      provider.valor,
    );
  },
);
```

## 🧠 Meu entendimento

Usando Consumer consigo limitar quais widgets precisam atualizar quando um valor mudar.

---