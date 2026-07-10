# 🤖 IA como Apoio — Flutter Internacionalização

> Atividade desenvolvida utilizando IA como ferramenta de apoio para estudos sobre internacionalização em aplicativos Flutter.

---

# 📚 Conteúdos estudados

- Internacionalização (i18n)
- Localização (l10n)
- Pacote INTL
- Arquivos ARB
- Tradução de textos
- Formatos regionais
- Datas, horas e moedas

---

# 1️⃣ Internacionalização

## ❓ Pergunta feita para IA

```txt
O que é internacionalização e qual sua importância?
```

## 💡 Resposta da IA

Internacionalização é o processo de preparar um aplicativo para funcionar em diferentes idiomas e regiões.

O objetivo é permitir que o mesmo aplicativo consiga adaptar textos, formatos de data, moeda e outras informações conforme o idioma ou localização do usuário.

## 💻 Exemplo

Sem internacionalização:

```dart
Text(
  'Bem vindo',
);
```

Com internacionalização:

```dart
Text(
  AppLocalizations.of(context).bemVindo,
);
```

## 🧠 Meu entendimento

Entendi que internacionalizar não é apenas traduzir textos. Também envolve adaptar formatos e regras conforme cada região.

---

# 2️⃣ Internacionalização no Flutter

## ❓ Pergunta feita para IA

```txt
Como funciona a internacionalização no Flutter?
```

## 💡 Resposta da IA

O Flutter possui suporte a internacionalização utilizando ferramentas como:

- flutter_localizations
- intl
- arquivos ARB

Os textos são separados do código e armazenados em arquivos de tradução.

Cada idioma possui seu próprio arquivo.

## 💻 Exemplo estrutura:

```txt
lib/
 |
 ├── l10n/
 |     |
 |     ├── app_pt.arb
 |     └── app_en.arb
 |
 └── main.dart
```

Arquivo português:

```json
{
  "titulo": "Cadastro"
}
```

Arquivo inglês:

```json
{
  "titulo": "Register"
}
```

Uso:

```dart
Text(
  AppLocalizations.of(context).titulo,
);
```

## 🧠 Meu entendimento

Separar os textos em arquivos próprios deixa o aplicativo preparado para receber novos idiomas sem alterar as telas.

---

# 3️⃣ Configurando idiomas

## ❓ Pergunta feita para IA

```txt
Como posso adicionar suporte para diferentes idiomas em meu aplicativo Flutter?
```

## 💡 Resposta da IA

É necessário configurar os idiomas suportados no MaterialApp e criar os arquivos de tradução.

## 💻 Exemplo

```dart
MaterialApp(
  localizationsDelegates:
      AppLocalizations.localizationsDelegates,

  supportedLocales:
      AppLocalizations.supportedLocales,
);
```

Arquivos:

```txt
app_pt.arb
app_en.arb
app_es.arb
```

## 🧠 Meu entendimento

O MaterialApp precisa saber quais idiomas existem e onde buscar as traduções.

---

# 4️⃣ Arquivos ARB

## ❓ Pergunta feita para IA

```txt
Quais as dicas de uso dos arquivos ARB?
```

## 💡 Resposta da IA

Arquivos ARB armazenam as mensagens utilizadas na aplicação.

Boas práticas:

- Utilizar nomes claros nas chaves.
- Evitar textos fixos dentro das telas.
- Organizar mensagens.
- Manter todos os idiomas atualizados.

## 💻 Exemplo

Evitar:

```json
{
  "texto1": "Salvar"
}
```

Melhor:

```json
{
  "botaoSalvar": "Salvar"
}
```

Uso:

```dart
Text(
  AppLocalizations.of(context).botaoSalvar,
);
```

## 🧠 Meu entendimento

As chaves precisam representar o significado do texto, não apenas o texto em si, facilitando alterações futuras.

---

# 5️⃣ Funcionamento do INTL

## ❓ Pergunta feita para IA

```txt
Quais cuidados devo ter ao usar o INTL?
```

## 💡 Resposta da IA

Alguns cuidados importantes:

- Não deixar textos fixos no código.
- Cuidar diferenças entre idiomas.
- Tratar plural.
- Utilizar formatos corretos para datas e números.

## 💻 Exemplo

```dart
DateFormat.yMd(
  'pt_BR',
).format(
  DateTime.now(),
);
```

## 🧠 Meu entendimento

Cada região pode representar informações de maneiras diferentes, então não basta traduzir palavras.

---

# 6️⃣ Formatos de data, hora e moeda

## ❓ Pergunta feita para IA

```txt
Como posso lidar com diferentes formatos de data, hora e moeda em diferentes idiomas?
```

## 💡 Resposta da IA

Cada país pode possuir regras diferentes para representar datas, horas, números e valores monetários.

O pacote `intl` permite formatar essas informações de acordo com o idioma e região do usuário.

## 💻 Exemplo

```dart
import 'package:intl/intl.dart';

void main() {

  double valor = 1500.50;

  var moeda = NumberFormat.currency(
    locale: 'pt_BR',
    symbol: 'R\$',
  );

  print(
    moeda.format(valor),
  );
}
```

Resultado:

```txt
R$ 1.500,50
```

Formato americano:

```dart
var moeda = NumberFormat.currency(
  locale: 'en_US',
  symbol: '\$',
);
```

Resultado:

```txt
$1,500.50
```

## 🧠 Meu entendimento

Cada região possui seu próprio padrão. Utilizar o INTL evita precisar criar regras manuais para cada país.

---

# 7️⃣ Internacionalização em formulários

## ❓ Pergunta feita para IA

```txt
Mostre o exemplo de um formulário de cadastro usando internacionalização.
```

## 💡 Resposta da IA

Com internacionalização, os textos exibidos no formulário deixam de ficar escritos diretamente no código.

Eles passam a vir dos arquivos de tradução.

## 💻 Exemplo

Antes:

```dart
TextField(
  decoration: InputDecoration(
    labelText: 'Nome',
  ),
);
```

Depois:

```dart
TextField(
  decoration: InputDecoration(
    labelText:
      AppLocalizations
        .of(context)
        .nome,
  ),
);
```

Arquivo português:

```json
{
  "nome": "Nome",
  "email": "E-mail",
  "salvar": "Salvar"
}
```

Arquivo inglês:

```json
{
  "nome": "Name",
  "email": "Email",
  "salvar": "Save"
}
```

## 🧠 Meu entendimento

A tela continua a mesma, apenas a origem dos textos muda. Isso facilita adicionar novos idiomas no futuro.

---

# 8️⃣ Tradução com parâmetros

## ❓ Pergunta feita para IA

```txt
Como trabalhar com textos que recebem valores usando internacionalização?
```

## 💡 Resposta da IA

Algumas mensagens precisam receber valores variáveis, como nomes ou quantidades.

O ARB permite criar mensagens com parâmetros.

## 💻 Exemplo

Arquivo ARB:

```json
{
  "bemVindo": "Olá {nome}"
}
```

Uso:

```dart
Text(
  AppLocalizations
    .of(context)
    .bemVindo(
      "Pedro",
    ),
);
```

Resultado:

```txt
Olá Pedro
```

## 🧠 Meu entendimento

Não devo montar frases usando várias concatenações, porque outros idiomas podem ter estruturas diferentes.

---

# 9️⃣ Plural utilizando INTL

## ❓ Pergunta feita para IA

```txt
Como tratar textos no plural usando internacionalização?
```

## 💡 Resposta da IA

Idiomas diferentes possuem regras diferentes para plural.

O INTL permite definir mensagens considerando quantidade.

## 💻 Exemplo

Arquivo ARB:

```json
{
  "quantidadeItens":
      "{quantidade, plural, =0{Nenhum item} =1{1 item} other{{quantidade} itens}}"
}
```

Uso:

```dart
Text(
  AppLocalizations
    .of(context)
    .quantidadeItens(5),
);
```

Resultado:

```txt
5 itens
```

## 🧠 Meu entendimento

O plural deve ser tratado pela ferramenta de internacionalização porque cada idioma possui suas próprias regras.

---

# 🔟 Cuidados ao internacionalizar

## ❓ Pergunta feita para IA

```txt
Quais cuidados devo ter ao criar aplicativos com suporte a vários idiomas?
```

## 💡 Resposta da IA

Alguns cuidados importantes:

- Evitar textos fixos dentro dos widgets.
- Pensar em tamanhos diferentes de textos.
- Testar todos os idiomas.
- Não concatenar frases.
- Utilizar formatação correta para cada região.

## 💻 Exemplo

Evitar:

```dart
Text(
  'Olá ' + nome,
);
```

Melhor:

```dart
Text(
  AppLocalizations
    .of(context)
    .mensagemUsuario(nome),
);
```

## 🧠 Meu entendimento

Cada idioma possui tamanhos e estruturas diferentes. O aplicativo precisa estar preparado para essas diferenças.

---

# ✅ Conclusão

A utilização da IA ajudou a entender como funciona a internacionalização no Flutter.

Foi possível compreender que internacionalizar um aplicativo vai além de traduzir textos.

Também envolve preparar formatos de datas, números, moedas e organizar os textos fora do código utilizando arquivos ARB.

Com o uso do INTL e das ferramentas de localização do Flutter, fica mais simples criar aplicativos preparados para diferentes idiomas e regiões.