# 🤖 IA como Apoio — Flutter Persistência de Dados

> Atividade desenvolvida utilizando IA como ferramenta de apoio para estudos sobre persistência de dados em Flutter utilizando SharedPreferences.

---

# 📚 Conteúdos estudados

- Persistência de dados
- Armazenamento local
- SharedPreferences
- Salvando informações
- Recuperando informações
- Limitações
- Boas práticas

---

# 1️⃣ Persistência de dados

## ❓ Pergunta feita para IA

```txt
O que é persistência de dados em aplicativos Flutter e por que é importante?
```

## 💡 Resposta da IA

Persistência de dados é a capacidade do aplicativo de salvar informações para que elas continuem disponíveis mesmo depois que o aplicativo for fechado.

Sem persistência, os dados armazenados em variáveis são perdidos quando o aplicativo é encerrado.

## 💻 Exemplo

```txt
Sem persistência:

Usuário digita nome
        ↓
Fecha aplicativo
        ↓
Nome perdido


Com persistência:

Usuário digita nome
        ↓
Salva localmente
        ↓
Fecha aplicativo
        ↓
Abre novamente
        ↓
Nome continua disponível
```

## 🧠 Meu entendimento

Entendi que variáveis existem apenas enquanto o aplicativo está aberto. Quando preciso manter informações após fechar o app, preciso salvar esses dados utilizando alguma forma de persistência.

---

# 2️⃣ Tipos de dados persistidos

## ❓ Pergunta feita para IA

```txt
Quais são os diferentes tipos de dados que podem ser persistidos em um aplicativo Flutter?
```

## 💡 Resposta da IA

Existem diferentes formas de salvar informações:

- SharedPreferences para dados simples.
- Banco de dados local para informações maiores.
- Arquivos locais.
- Banco de dados externo através de APIs.

Exemplos de informações:

- Configurações do usuário.
- Tema escolhido.
- Login.
- Preferências.
- Listas simples.

## 💻 Exemplo

```txt
Tema escuro = true

Nome usuário = João

Volume = 80
```

## 🧠 Meu entendimento

Cada tipo de informação pode exigir uma estratégia diferente. Nem todo dado precisa de banco de dados, informações simples podem usar SharedPreferences.

---

# 3️⃣ SharedPreferences

## ❓ Pergunta feita para IA

```txt
O que é o pacote SharedPreferences em Flutter e como ele funciona?
```

## 💡 Resposta da IA

SharedPreferences é um pacote utilizado para salvar pequenos dados localmente no dispositivo.

Ele funciona utilizando o conceito de chave e valor.

Cada informação é armazenada utilizando uma chave para ser recuperada posteriormente.

## 💻 Exemplo

```dart
final prefs = await SharedPreferences.getInstance();

prefs.setString(
  'nome',
  'Diogo',
);
```

Recuperando:

```dart
final nome = prefs.getString(
  'nome',
);
```

## 🧠 Meu entendimento

O SharedPreferences funciona parecido com um Map, onde eu salvo uma chave associada a um valor e depois consigo buscar utilizando essa chave.

---

# 4️⃣ Funcionamento chave e valor

## ❓ Pergunta feita para IA

```txt
Como o SharedPreferences organiza os dados salvos?
```

## 💡 Resposta da IA

Ele trabalha armazenando informações utilizando chave e valor.

A chave identifica a informação salva.

## 💻 Exemplo

```txt
"usuario" : "Pedro"

"idade" : 25

"logado" : true
```

Em código:

```dart
prefs.setInt(
  'idade',
  25,
);
```

Buscar:

```dart
prefs.getInt(
  'idade',
);
```

## 🧠 Meu entendimento

A chave precisa ser bem definida, porque é através dela que consigo recuperar o valor posteriormente.

---

# 5️⃣ Tipos aceitos no SharedPreferences

## ❓ Pergunta feita para IA

```txt
Quais tipos de dados posso salvar no SharedPreferences?
```

## 💡 Resposta da IA

O SharedPreferences suporta tipos simples:

- String
- int
- double
- bool
- List<String>

## 💻 Exemplo

```dart
prefs.setBool(
  'ativo',
  true,
);

prefs.setDouble(
  'altura',
  1.80,
);
```

## 🧠 Meu entendimento

SharedPreferences não é feito para armazenar objetos complexos diretamente. Para objetos maiores é necessário converter ou usar outra solução.

---

# 6️⃣ Limitações do SharedPreferences

## ❓ Pergunta feita para IA

```txt
Quais são as limitações do SharedPreferences em termos de armazenamento de dados?
```

## 💡 Resposta da IA

O SharedPreferences é indicado apenas para armazenar pequenas quantidades de dados simples.

Algumas limitações:

- Não é indicado para grandes volumes de informação.
- Não trabalha com consultas complexas.
- Não possui relacionamentos entre dados.
- Não substitui um banco de dados.
- Não é indicado para informações sensíveis.

## 💻 Exemplo

Uso adequado:

```txt
Tema = escuro

Usuário logado = true

Idioma = português
```

Uso inadequado:

```txt
Lista com milhares de produtos

Histórico completo de vendas

Banco de clientes
```

## 🧠 Meu entendimento

O SharedPreferences é útil para configurações e dados pequenos. Para informações grandes ou estruturadas, é melhor utilizar um banco de dados.

---

# 7️⃣ Quando usar SharedPreferences

## ❓ Pergunta feita para IA

```txt
Quando devo usar SharedPreferences em vez de outras opções de persistência de dados?
```

## 💡 Resposta da IA

SharedPreferences deve ser utilizado quando precisamos salvar informações simples que precisam continuar existindo após fechar o aplicativo.

É comum utilizar para:

- Preferências do usuário.
- Configurações.
- Pequenos estados.
- Dados simples.

## 💻 Exemplo

```dart
prefs.setBool(
  'modoEscuro',
  true,
);
```

Ao abrir o aplicativo novamente:

```dart
bool? tema = prefs.getBool(
  'modoEscuro',
);
```

## 🧠 Meu entendimento

Se preciso apenas lembrar uma escolha do usuário, SharedPreferences resolve bem. Se precisar manipular muitos registros, devo escolher outra solução.

---

# 8️⃣ Lidando com erros

## ❓ Pergunta feita para IA

```txt
Como posso lidar com erros ao usar SharedPreferences?
```

## 💡 Resposta da IA

É importante considerar que uma chave pode não existir ou o valor pode ser nulo.

Podemos utilizar verificações e valores padrão.

## 💻 Exemplo

```dart
final nome =
    prefs.getString('nome') ?? 'Sem nome';

print(nome);
```

## 🧠 Meu entendimento

Como o retorno pode ser null, preciso tratar esses casos para evitar erros no aplicativo.

---

# 9️⃣ Boas práticas usando SharedPreferences

## ❓ Pergunta feita para IA

```txt
Quais são as melhores práticas para usar SharedPreferences de forma eficiente?
```

## 💡 Resposta da IA

Algumas boas práticas:

- Criar constantes para as chaves.
- Evitar salvar muitos dados.
- Não repetir código de acesso.
- Organizar a lógica em classes separadas.
- Tratar valores nulos.

## 💻 Exemplo

Evitar:

```dart
prefs.getString(
  'nomeUsuario',
);
```

em vários lugares.

Melhor:

```dart
class Chaves {
  static const nome =
      'nomeUsuario';
}
```

Uso:

```dart
prefs.getString(
  Chaves.nome,
);
```

## 🧠 Meu entendimento

Organizar as chaves evita erros de digitação e facilita manutenção quando o projeto cresce.

---

# 🔟 Salvando objetos no SharedPreferences

## ❓ Pergunta feita para IA

```txt
Como salvar objetos utilizando SharedPreferences?
```

## 💡 Resposta da IA

O SharedPreferences não salva objetos diretamente.

Uma solução é transformar o objeto em JSON e salvar como String.

## 💻 Exemplo

Objeto:

```dart
class Usuario {

  String nome;

  Usuario(
    this.nome,
  );

}
```

Transformando:

```dart
String json =
    jsonEncode(
      usuario.toJson(),
    );

prefs.setString(
  'usuario',
  json,
);
```

## 🧠 Meu entendimento

Como SharedPreferences aceita apenas tipos simples, objetos precisam ser convertidos para texto antes de salvar.

---

# 1️⃣1️⃣ SharedPreferences em listas

## ❓ Pergunta feita para IA

```txt
Como salvar uma lista de tarefas usando SharedPreferences?
```

## 💡 Resposta da IA

Podemos utilizar `setStringList` para listas simples de texto.

## 💻 Exemplo

```dart
List<String> tarefas = [
  'Estudar Flutter',
  'Fazer atividade',
];

prefs.setStringList(
  'tarefas',
  tarefas,
);
```

Recuperando:

```dart
List<String>? tarefas =
    prefs.getStringList(
      'tarefas',
    );
```

## 🧠 Meu entendimento

Para listas simples o SharedPreferences já possui suporte. Para listas de objetos é necessário converter para JSON.

---

# 1️⃣2️⃣ SharedPreferences x Banco de dados

## ❓ Pergunta feita para IA

```txt
Qual a diferença entre SharedPreferences e um banco de dados?
```

## 💡 Resposta da IA

SharedPreferences:

- Armazena poucos dados.
- Estrutura chave e valor.
- Simples de utilizar.

Banco de dados:

- Trabalha com muitos registros.
- Permite buscas.
- Permite filtros.
- Possui melhor organização para grandes volumes.

## 💻 Exemplo

SharedPreferences:

```txt
usuarioLogado = true
```

Banco:

```txt
Tabela Produtos

id | nome | valor
1  | PC   | 2000
2  | TV   | 3000
```

## 🧠 Meu entendimento

SharedPreferences é mais parecido com salvar configurações. Banco de dados é usado quando preciso armazenar e consultar muitas informações.

---

# ✅ Conclusão

A utilização da IA ajudou a entender como funciona a persistência de dados no Flutter.

Foi possível compreender que variáveis existem apenas durante a execução do aplicativo e que ferramentas como SharedPreferences permitem manter informações mesmo após fechar o app.

Também ficou claro que SharedPreferences deve ser usado para dados simples, enquanto informações maiores devem utilizar outras formas de armazenamento.