# 🤖 IA como Apoio — Flutter Widgets Básicos

> Atividade desenvolvida utilizando IA como ferramenta de apoio para estudos sobre widgets básicos no Flutter.

---

# 📚 Conteúdos estudados

- Widgets
- Row
- Column
- Stack
- Image
- Text
- ListView
- ListTile
- Organização de layouts
- Manipulação de listas

---

# 1️⃣ Widget Row

## ❓ Pergunta feita para IA

```txt
Explique o conceito de um widget Row em Flutter.
```

## 💡 Resposta da IA

O `Row` é um widget utilizado para organizar outros widgets na horizontal.

Ele recebe uma lista de widgets através do atributo `children`.

É muito utilizado quando precisamos colocar componentes lado a lado.

## 💻 Exemplo

```dart
Row(
  children: [
    Icon(Icons.person),
    Text('Usuário'),
  ],
);
```

## 🧠 Meu entendimento

Entendi que o Row funciona como uma linha onde posso adicionar vários widgets lado a lado. Ele é usado quando quero organizar elementos na horizontal.

---

# 2️⃣ Espaçamento em Row

## ❓ Pergunta feita para IA

```txt
Como posso adicionar espaçamento uniforme entre os widgets em um Row?
```

## 💡 Resposta da IA

Podemos utilizar o atributo `mainAxisAlignment` para controlar o espaçamento dos elementos.

Algumas opções:

- start
- center
- end
- spaceBetween
- spaceAround
- spaceEvenly

## 💻 Exemplo

```dart
Row(
  mainAxisAlignment: MainAxisAlignment.spaceEvenly,
  children: [
    Text('A'),
    Text('B'),
    Text('C'),
  ],
);
```

## 🧠 Meu entendimento

O mainAxisAlignment controla como os elementos ficam distribuídos no eixo principal do Row, que nesse caso é o eixo horizontal.

---

# 3️⃣ MainAxisAlignment x CrossAxisAlignment no Row

## ❓ Pergunta feita para IA

```txt
Qual a diferença entre MainAxisAlignment e CrossAxisAlignment em um Row?
```

## 💡 Resposta da IA

No Row:

- MainAxisAlignment controla o alinhamento horizontal.
- CrossAxisAlignment controla o alinhamento vertical.

## 💻 Exemplo

```dart
Row(
  mainAxisAlignment: MainAxisAlignment.center,
  crossAxisAlignment: CrossAxisAlignment.start,
);
```

## 🧠 Meu entendimento

Entendi que o eixo principal depende do widget utilizado. No Row o principal é horizontal, já o secundário é vertical.

---

# 4️⃣ Widget Column

## ❓ Pergunta feita para IA

```txt
Explique o conceito de um widget Column em Flutter.
```

## 💡 Resposta da IA

O `Column` organiza widgets em uma coluna vertical.

Ele também utiliza o atributo `children` para receber vários widgets.

## 💻 Exemplo

```dart
Column(
  children: [
    Text('Nome'),
    Text('Idade'),
    ElevatedButton(
      onPressed: () {},
      child: Text('Enviar'),
    ),
  ],
);
```

## 🧠 Meu entendimento

O Column é parecido com o Row, porém trabalha na vertical. É muito usado para montar telas com vários componentes.

---

# 5️⃣ MainAxisAlignment x CrossAxisAlignment no Column

## ❓ Pergunta feita para IA

```txt
Qual a diferença entre MainAxisAlignment e CrossAxisAlignment em um Column?
```

## 💡 Resposta da IA

No Column:

- MainAxisAlignment controla o eixo vertical.
- CrossAxisAlignment controla o eixo horizontal.

## 💻 Exemplo

```dart
Column(
  mainAxisAlignment: MainAxisAlignment.center,
  crossAxisAlignment: CrossAxisAlignment.start,
);
```

## 🧠 Meu entendimento

No Column os eixos invertem comparado ao Row. O eixo principal passa a ser de cima para baixo.

---
---

# 6️⃣ Widget Stack

## ❓ Pergunta feita para IA

```txt
Explique o conceito de um widget Stack em Flutter.
```

## 💡 Resposta da IA

O `Stack` é um widget utilizado para posicionar widgets um sobre o outro.

Diferente do Row e Column, ele trabalha utilizando camadas.

O primeiro widget da lista fica atrás e os próximos são desenhados por cima.

## 💻 Exemplo

```dart
Stack(
  children: [
    Container(
      width: 200,
      height: 200,
      color: Colors.blue,
    ),

    Text(
      'Texto sobreposto',
    ),
  ],
);
```

## 🧠 Meu entendimento

Entendi que o Stack funciona como camadas, parecido com colocar um elemento por cima de outro. É útil quando preciso criar telas com sobreposição.

---

# 7️⃣ Stack x Row e Column

## ❓ Pergunta feita para IA

```txt
Quais as vantagens de usar Stack em vez de Row ou Column?
```

## 💡 Resposta da IA

O Stack deve ser usado quando precisamos sobrepor elementos.

Exemplos:

- Texto sobre uma imagem.
- Ícone em cima de outro componente.
- Elementos posicionados manualmente.

Row e Column são melhores para organização linear.

## 💻 Exemplo

```dart
Stack(
  children: [
    Image.network(
      'imagem',
    ),

    Positioned(
      bottom: 10,
      child: Text(
        'Título',
      ),
    ),
  ],
);
```

## 🧠 Meu entendimento

Row e Column organizam elementos em sequência. Stack é usado quando a posição dos widgets precisa ser mais livre.

---

# 8️⃣ Posicionamento no Stack

## ❓ Pergunta feita para IA

```txt
Como posso posicionar widgets específicos dentro de um Stack?
```

## 💡 Resposta da IA

Dentro do Stack podemos utilizar o widget `Positioned`.

Ele permite controlar a distância do elemento em relação aos lados.

Propriedades:

- top
- bottom
- left
- right

## 💻 Exemplo

```dart
Stack(
  children: [
    Positioned(
      top: 20,
      left: 10,
      child: Text(
        'Posicionado',
      ),
    ),
  ],
);
```

## 🧠 Meu entendimento

O Positioned funciona apenas dentro do Stack e permite escolher exatamente onde o widget deve aparecer.

---

# 9️⃣ Imagens locais no Flutter

## ❓ Pergunta feita para IA

```txt
Como posso exibir uma imagem de um arquivo local em Flutter?
```

## 💡 Resposta da IA

Para utilizar imagens locais é necessário adicionar o arquivo ao projeto e registrar no `pubspec.yaml`.

Depois usamos o widget Image.

## 💻 Exemplo

```yaml
assets:
  - imagens/logo.png
```

Uso:

```dart
Image.asset(
  'imagens/logo.png',
);
```

## 🧠 Meu entendimento

Diferente de uma imagem da internet, uma imagem local precisa estar dentro do projeto e ser declarada antes de ser utilizada.

---

# 🔟 Widget Text

## ❓ Pergunta feita para IA

```txt
Quais propriedades posso usar para controlar a aparência do texto (fonte, tamanho, cor)?
```

## 💡 Resposta da IA

O widget Text permite personalizar textos utilizando o `TextStyle`.

Algumas propriedades:

- fontSize
- color
- fontWeight
- fontStyle

## 💻 Exemplo

```dart
Text(
  'Olá Flutter',
  style: TextStyle(
    fontSize: 20,
    color: Colors.blue,
    fontWeight: FontWeight.bold,
  ),
);
```

## 🧠 Meu entendimento

O TextStyle funciona como uma configuração visual do texto. Nele consigo alterar tamanho, cor e estilo.

---

# 1️⃣1️⃣ Texto com várias linhas

## ❓ Pergunta feita para IA

```txt
Como posso exibir um texto em várias linhas?
```

## 💡 Resposta da IA

O Text pode quebrar linhas automaticamente ou utilizando o caractere `\n`.

Também podemos controlar a quantidade máxima de linhas.

## 💻 Exemplo

```dart
Text(
  'Primeira linha\nSegunda linha',
  maxLines: 2,
);
```

## 🧠 Meu entendimento

O Flutter consegue adaptar textos grandes automaticamente, mas também permite controlar manualmente as quebras.

---

# 1️⃣2️⃣ ListView

## ❓ Pergunta feita para IA

```txt
Como posso criar uma lista de rolagem vertical em Flutter?
```

## 💡 Resposta da IA

O `ListView` é um widget utilizado para criar listas com rolagem.

Diferente do Column, ele permite trabalhar com muitos elementos porque possui scroll.

## 💻 Exemplo

```dart
ListView(
  children: [
    Text('Item 1'),
    Text('Item 2'),
    Text('Item 3'),
  ],
);
```

## 🧠 Meu entendimento

Entendi que o ListView é utilizado quando existe uma quantidade maior de elementos e a tela precisa permitir rolagem.

---

# 1️⃣3️⃣ Itens dinâmicos em ListView

## ❓ Pergunta feita para IA

```txt
Como posso adicionar itens dinamicamente a um ListView?
```

## 💡 Resposta da IA

Para listas dinâmicas podemos utilizar o `ListView.builder`.

Ele cria os itens conforme necessário utilizando uma lista de dados.

## 💻 Exemplo

```dart
List<String> nomes = [
  'Pedro',
  'Maria',
  'Ana',
];

ListView.builder(
  itemCount: nomes.length,
  itemBuilder: (context, index) {
    return Text(
      nomes[index],
    );
  },
);
```

## 🧠 Meu entendimento

O builder é útil porque não preciso criar cada item manualmente. Posso transformar uma lista de dados em vários widgets.

---

# 1️⃣4️⃣ ListView.builder x ListView.separated

## ❓ Pergunta feita para IA

```txt
Quais as diferenças entre ListView.builder e ListView.separated?
```

## 💡 Resposta da IA

O `ListView.builder` cria elementos de uma lista dinamicamente.

O `ListView.separated` funciona de forma parecida, porém permite criar separadores entre os itens.

## 💻 Exemplo

```dart
ListView.separated(
  itemCount: 10,

  itemBuilder: (context, index) {
    return Text(
      'Item $index',
    );
  },

  separatorBuilder: (context, index) {
    return Divider();
  },
);
```

## 🧠 Meu entendimento

O separated facilita quando preciso dividir visualmente os elementos, evitando adicionar separadores manualmente.

---

# 1️⃣5️⃣ ListTile

## ❓ Pergunta feita para IA

```txt
Como posso usar ListTile para criar itens de lista em um ListView?
```

## 💡 Resposta da IA

O `ListTile` é um widget pronto para criar linhas de listas seguindo o Material Design.

Ele já possui espaços próprios para:

- título
- subtítulo
- ícone inicial
- ícone final

## 💻 Exemplo

```dart
ListTile(
  leading: Icon(
    Icons.person,
  ),

  title: Text(
    'Pedro',
  ),

  subtitle: Text(
    'Usuário ativo',
  ),
);
```

## 🧠 Meu entendimento

O ListTile evita criar manualmente linhas usando Row e Column, porque já entrega uma estrutura pronta.

---

# 1️⃣6️⃣ ListTile clicável

## ❓ Pergunta feita para IA

```txt
Como posso tornar os itens ListTile interativos (clicáveis)?
```

## 💡 Resposta da IA

O ListTile possui o atributo `onTap`, que permite executar uma ação quando o usuário toca no item.

## 💻 Exemplo

```dart
ListTile(
  title: Text(
    'Configurações',
  ),

  onTap: () {
    print(
      'Clicou',
    );
  },
);
```

## 🧠 Meu entendimento

O ListTile funciona parecido com um botão quando utilizamos o onTap, permitindo criar menus e listas interativas.

---

# 1️⃣7️⃣ ListTile x Text simples

## ❓ Pergunta feita para IA

```txt
Quais as vantagens de usar ListTile em vez de widgets de texto simples?
```

## 💡 Resposta da IA

O ListTile possui uma estrutura pronta para listas.

Vantagens:

- Melhor organização.
- Suporte a ícones.
- Suporte a clique.
- Segue o padrão Material Design.

Um Text apenas mostra uma informação na tela.

## 💻 Exemplo

```dart
ListTile(
  leading: Icon(
    Icons.email,
  ),

  title: Text(
    'Email',
  ),
);
```

## 🧠 Meu entendimento

Quando preciso apenas mostrar uma frase uso Text. Quando preciso criar itens de uma lista ou menu, o ListTile facilita porque já possui vários recursos.

---

# 1️⃣8️⃣ Imagem da internet

## ❓ Pergunta feita para IA

```txt
Como posso exibir uma imagem da internet em Flutter?
```

## 💡 Resposta da IA

Para carregar imagens online podemos utilizar o `Image.network`.

## 💻 Exemplo

```dart
Image.network(
  'https://site.com/imagem.png',
);
```

## 🧠 Meu entendimento

O Image.network busca a imagem através de um endereço externo, diferente do asset que utiliza arquivos dentro do projeto.

---

# ✅ Conclusão

A utilização da IA ajudou no entendimento dos principais widgets básicos do Flutter.

Foi possível compreender melhor como organizar telas utilizando Row, Column e Stack, além de aprender a trabalhar com textos, imagens e listas.

Os widgets estudados são a base para construir interfaces mais completas dentro do Flutter.