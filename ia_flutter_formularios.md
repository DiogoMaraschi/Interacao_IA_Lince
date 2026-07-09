# 🤖 IA como Apoio — Flutter Formulários

> Atividade desenvolvida utilizando IA como ferramenta de apoio para estudos sobre formulários no Flutter.

---

# 📚 Conteúdos estudados

- TextField
- TextFormField
- Controllers
- Validação de campos
- CheckBox
- Radio
- Customização de campos
- Formulários

---

# 1️⃣ TextField

## ❓ Pergunta feita para IA

```txt
O que é um widget TextField em Flutter e para que ele serve?
```

## 💡 Resposta da IA

O `TextField` é um widget utilizado para entrada de texto no Flutter.

Ele permite que o usuário digite informações como nome, email, senha ou números.

É muito utilizado em formulários, telas de login, cadastro e busca.

## 💻 Exemplo

```dart
TextField(
  decoration: InputDecoration(
    labelText: 'Nome',
  ),
);
```

## 🧠 Meu entendimento

Entendi que o TextField é o campo básico para receber texto digitado pelo usuário. Ele é parecido com uma caixa de texto em outras interfaces.

---

# 2️⃣ Obtendo valor de um TextField

## ❓ Pergunta feita para IA

```txt
Como posso obter o valor digitado pelo usuário em um TextField?
```

## 💡 Resposta da IA

Para obter o valor digitado em um `TextField`, podemos utilizar um `TextEditingController`.

O controller fica ligado ao campo e permite acessar o texto digitado.

## 💻 Exemplo

```dart
final controladorNome = TextEditingController();

TextField(
  controller: controladorNome,
);

print(controladorNome.text);
```

## 🧠 Meu entendimento

O controller funciona como uma ponte entre o campo da tela e o código. Com ele consigo pegar o texto que o usuário digitou.

---

# 3️⃣ TextField x TextFormField

## ❓ Pergunta feita para IA

```txt
Qual a diferença entre um TextField e um TextFormField?
```

## 💡 Resposta da IA

O `TextField` é um campo de texto simples.

O `TextFormField` é uma versão integrada ao widget `Form`, permitindo validação com `validator`, salvamento com `onSaved` e uso com `FormState`.

## 💻 Exemplo

```dart
Form(
  child: TextFormField(
    validator: (valor) {
      if (valor == null || valor.isEmpty) {
        return 'Campo obrigatório';
      }

      return null;
    },
  ),
);
```

## 🧠 Meu entendimento

Entendi que TextField é mais simples, enquanto TextFormField é mais indicado quando estou criando formulários com validação.

---

# 4️⃣ Parâmetros importantes do TextField

## ❓ Pergunta feita para IA

```txt
Quais parâmetros importantes do TextField?
```

## 💡 Resposta da IA

Alguns parâmetros importantes do `TextField` são:

- `controller`: controla o texto digitado.
- `decoration`: configura aparência do campo.
- `keyboardType`: define o tipo de teclado.
- `obscureText`: esconde o texto, usado para senha.
- `maxLength`: limita quantidade de caracteres.
- `onChanged`: executa algo quando o texto muda.

## 💻 Exemplo

```dart
TextField(
  keyboardType: TextInputType.emailAddress,
  maxLength: 50,
  decoration: InputDecoration(
    labelText: 'Email',
    prefixIcon: Icon(Icons.email),
  ),
);
```

## 🧠 Meu entendimento

Percebi que o TextField tem muitos parâmetros que controlam tanto o comportamento quanto a aparência do campo.

---

# 5️⃣ Validação de campo

## ❓ Pergunta feita para IA

```txt
O que significa validar um campo de texto em Flutter?
```

## 💡 Resposta da IA

Validar um campo significa verificar se o valor digitado atende a uma regra.

Exemplos:

- Campo obrigatório.
- Email válido.
- Senha com tamanho mínimo.
- Número dentro de um intervalo.

## 💻 Exemplo

```dart
TextFormField(
  validator: (valor) {
    if (valor == null || valor.isEmpty) {
      return 'Informe um valor';
    }

    return null;
  },
);
```

## 🧠 Meu entendimento

Entendi que validar é conferir se o usuário preencheu corretamente antes de continuar uma ação, como cadastrar ou enviar um formulário.

---
---

# 6️⃣ Validação síncrona e assíncrona

## ❓ Pergunta feita para IA

```txt
Qual a diferença entre validação síncrona e assíncrona?
```

## 💡 Resposta da IA

Validação síncrona acontece imediatamente, usando uma regra local.

Exemplo:

- Verificar se o campo está vazio.
- Verificar tamanho mínimo.

Validação assíncrona depende de uma operação que pode demorar, como consultar banco de dados ou API.

Exemplo:

- Verificar se email já existe.
- Validar CPF em um serviço externo.

## 💻 Exemplo

```dart
String? validarNome(String? valor) {
  if (valor == null || valor.isEmpty) {
    return 'Nome obrigatório';
  }

  return null;
}
```

## 🧠 Meu entendimento

A validação síncrona é mais simples e acontece na hora. A assíncrona depende de uma resposta externa, então precisa trabalhar com Future.

---

# 7️⃣ CheckBox

## ❓ Pergunta feita para IA

```txt
O que é um widget CheckBox em Flutter e para que ele serve?
```

## 💡 Resposta da IA

O `Checkbox` é um widget usado para opções marcáveis.

Ele representa uma escolha verdadeira ou falsa.

É comum em opções como:

- Aceitar termos.
- Ativar notificações.
- Selecionar preferências.

## 💻 Exemplo

```dart
bool aceitou = false;

Checkbox(
  value: aceitou,
  onChanged: (valor) {
    aceitou = valor ?? false;
  },
);
```

## 🧠 Meu entendimento

Entendi que Checkbox trabalha com booleano. Ele pode estar marcado ou desmarcado.

---

# 8️⃣ Customizando CheckBox

## ❓ Pergunta feita para IA

```txt
Como posso alterar a cor e a forma de um CheckBox?
```

## 💡 Resposta da IA

O Checkbox permite customizar cores usando propriedades como `activeColor` e também alterar formato com `shape`.

## 💻 Exemplo

```dart
Checkbox(
  value: true,
  activeColor: Colors.green,
  shape: RoundedRectangleBorder(
    borderRadius: BorderRadius.circular(4),
  ),
  onChanged: (valor) {},
);
```

## 🧠 Meu entendimento

O Checkbox pode ser personalizado visualmente, mas ainda mantém o comportamento de marcado ou desmarcado.

---

# 9️⃣ Radio

## ❓ Pergunta feita para IA

```txt
O que é um widget Radio em Flutter e qual sua aplicabilidade?
```

## 💡 Resposta da IA

O `Radio` é utilizado quando o usuário deve escolher apenas uma opção dentro de um grupo.

Diferente do Checkbox, o Radio representa uma escolha única.

Exemplos:

- Forma de pagamento.
- Gênero.
- Sim ou não.
- Preferência entre opções.

## 💻 Exemplo

```dart
String opcao = 'sim';

Radio<String>(
  value: 'sim',
  groupValue: opcao,
  onChanged: (valor) {
    opcao = valor!;
  },
);
```

## 🧠 Meu entendimento

Entendi que Radio é usado quando só uma alternativa pode ser escolhida dentro de um grupo.

---

# 🔟 Customizando Radio

## ❓ Pergunta feita para IA

```txt
Como posso alterar a cor e a forma de um Rádio?
```

## 💡 Resposta da IA

O Radio permite alterar a cor usando propriedades como `activeColor` ou `fillColor`.

A forma do Radio é mais limitada que o Checkbox, pois ele normalmente segue o padrão circular do Material Design.

## 💻 Exemplo

```dart
Radio<String>(
  value: 'sim',
  groupValue: 'sim',
  activeColor: Colors.green,
  onChanged: (valor) {},
);
```

## 🧠 Meu entendimento

O Radio tem menos liberdade de formato, porque normalmente ele é circular. Mesmo assim, é possível alterar cores.

---

# 1️⃣1️⃣ Limitando caracteres

## ❓ Pergunta feita para IA

```txt
Como posso limitar o número de caracteres que o usuário pode digitar em um TextField?
```

## 💡 Resposta da IA

Podemos limitar a quantidade de caracteres usando o parâmetro `maxLength`.

## 💻 Exemplo

```dart
TextField(
  maxLength: 20,
);
```

## 🧠 Meu entendimento

O maxLength é útil quando um campo precisa ter limite, como nome de usuário, senha ou descrição curta.

---
---

# 1️⃣2️⃣ Tipo de teclado

## ❓ Pergunta feita para IA

```txt
Como posso alterar o tipo de teclado exibido para um TextField (numérico, email etc.)?
```

## 💡 Resposta da IA

O tipo do teclado pode ser alterado com o parâmetro `keyboardType`.

Exemplos:

- `TextInputType.text`
- `TextInputType.number`
- `TextInputType.emailAddress`
- `TextInputType.phone`

## 💻 Exemplo

```dart
TextField(
  keyboardType: TextInputType.number,
);
```

## 🧠 Meu entendimento

O keyboardType melhora a experiência do usuário porque mostra um teclado mais adequado para o tipo de dado esperado.

---

# 1️⃣3️⃣ Ícone no TextField

## ❓ Pergunta feita para IA

```txt
Como posso adicionar um ícone ao lado do texto em um TextField?
```

## 💡 Resposta da IA

Podemos adicionar ícones usando `InputDecoration`, principalmente com `prefixIcon` ou `suffixIcon`.

## 💻 Exemplo

```dart
TextField(
  decoration: InputDecoration(
    prefixIcon: Icon(Icons.person),
    labelText: 'Nome',
  ),
);
```

## 🧠 Meu entendimento

O ícone ajuda a identificar visualmente o objetivo do campo, como usuário, senha, email ou telefone.

---

# 1️⃣4️⃣ Mensagens de erro

## ❓ Pergunta feita para IA

```txt
Como posso exibir mensagens de erro para o usuário se a validação falhar?
```

## 💡 Resposta da IA

Com `TextFormField`, o retorno do `validator` define a mensagem de erro.

Se retornar uma String, o erro aparece. Se retornar null, significa que está válido.

## 💻 Exemplo

```dart
TextFormField(
  validator: (valor) {
    if (valor == null || valor.isEmpty) {
      return 'Campo obrigatório';
    }

    return null;
  },
);
```

## 🧠 Meu entendimento

A mensagem de erro é exibida quando o validator encontra algum problema. O null significa que o campo passou na validação.

---

# 1️⃣5️⃣ Formulário com CheckBox

## ❓ Pergunta feita para IA

```txt
Crie um formulário com um CheckBox para aceitar termos e condições.
```

## 💡 Resposta da IA

Um formulário pode usar Checkbox para confirmar se o usuário aceitou os termos antes de continuar.

## 💻 Exemplo

```dart
bool aceitouTermos = false;

CheckboxListTile(
  title: Text('Aceitar termos e condições'),
  value: aceitouTermos,
  onChanged: (valor) {
    aceitouTermos = valor ?? false;
  },
);
```

## 🧠 Meu entendimento

O CheckboxListTile já junta texto e checkbox, deixando a interface mais simples de montar.

---

# 1️⃣6️⃣ Grupo de Radio

## ❓ Pergunta feita para IA

```txt
Crie um grupo de Radios para permitir que o usuário selecione sua preferência (Aceita ketchup: Não, Sim).
```

## 💡 Resposta da IA

Um grupo de Radio utiliza o mesmo `groupValue`, mas valores diferentes.

A opção marcada é aquela cujo `value` é igual ao `groupValue`.

## 💻 Exemplo

```dart
String aceitaKetchup = 'nao';

RadioListTile<String>(
  title: Text('Sim'),
  value: 'sim',
  groupValue: aceitaKetchup,
  onChanged: (valor) {
    aceitaKetchup = valor!;
  },
);

RadioListTile<String>(
  title: Text('Não'),
  value: 'nao',
  groupValue: aceitaKetchup,
  onChanged: (valor) {
    aceitaKetchup = valor!;
  },
);
```

## 🧠 Meu entendimento

O Radio trabalha em grupo. Cada opção tem um valor, e apenas uma delas fica selecionada por vez.

---

# 1️⃣7️⃣ Validando email

## ❓ Pergunta feita para IA

```txt
Como posso verificar se o texto digitado em um campo é um email válido?
```

## 💡 Resposta da IA

Uma forma simples é verificar se o texto contém `@` e `.`. Para validações mais completas, pode ser usada expressão regular.

## 💻 Exemplo

```dart
String? validarEmail(String? valor) {
  if (valor == null || valor.isEmpty) {
    return 'Email obrigatório';
  }

  if (!valor.contains('@')) {
    return 'Email inválido';
  }

  return null;
}
```

## 🧠 Meu entendimento

Para validação simples posso verificar partes básicas do email. Para uma aplicação real, uma validação mais completa seria melhor.

---

# ✅ Conclusão

A utilização da IA ajudou a compreender melhor os principais recursos de formulários no Flutter.

Foi possível entender a diferença entre TextField e TextFormField, o uso de controllers, validações, CheckBox e Radio.

Esses conceitos são importantes para criar telas de cadastro, login, filtros e formulários interativos.