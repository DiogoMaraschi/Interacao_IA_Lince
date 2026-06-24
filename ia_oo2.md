# 🤖 IA como Apoio — Orientação a Objetos II em Dart

> Atividade da Lince Tech Academy utilizando IA como ferramenta de apoio nos estudos de Dart.
> A formatação foi feita com auxílio de IA, mas as perguntas e os campos de meus entendimentos foram preenchidas por mim.

---

# 📚 Conteúdos estudados

* Sobrescrita de métodos
* Getters e Setters
* Classes abstratas
* Herança
* Interfaces
* Enumeradores (enum)
* Métodos estáticos
* Organização de código orientado a objetos

---

# ❓ Pergunta 1

## Pergunta feita para IA

```txt
O que significa sobrescrever um método em Dart e por que eu faria isso?
```

## 💡 Resposta da IA

* Sobrescrever significa redefinir um método herdado.
* Permite alterar comportamentos específicos mantendo a estrutura da classe pai.

## 🧠 Meu entendimento

* Sobrescrita permite reutilizar comportamentos sem precisar reescrever tudo.
* Cada classe filha pode adaptar regras específicas mantendo consistência.

---

# ❓ Pergunta 2

## Pergunta feita para IA

```txt
Como posso chamar o método original de uma classe pai em um método sobrescrito?
```

## 💡 Resposta da IA

Exemplo:

```dart
class Animal {
  void emitirSom() {
    print('Som genérico');
  }
}

class Cachorro extends Animal {
  @override
  void emitirSom() {
    super.emitirSom();
    print('Au au');
  }
}
```

## 🧠 Meu entendimento

* O `super` permite acessar comportamentos da classe pai.
* Pode ser útil para complementar uma lógica sem substituir totalmente.

---

# ❓ Pergunta 3

## Pergunta feita para IA

```txt
Como posso criar um getter para acessar um atributo privado de uma classe?
```

## 💡 Resposta da IA

Exemplo:

```dart
class Pessoa {
  String _nome = '';

  String get nome => _nome;
}
```

## 🧠 Meu entendimento

* Getter cria acesso controlado a atributos privados.
* Ajuda no encapsulamento.

---

# ❓ Pergunta 4

## Pergunta feita para IA

```txt
Em quais situações é melhor usar getters e setters em vez de acessar atributos diretamente?
```

## 💡 Resposta da IA

* Quando existir validação.
* Quando houver regras de negócio.

## 🧠 Meu entendimento

* Getters e setters ajudam a controlar alterações.
* Permitem validar antes de salvar valores.

---

# ❓ Pergunta 5

## Pergunta feita para IA

```txt
O que é uma classe abstrata e como ela difere de uma classe normal?
```

## 💡 Resposta da IA

* Classe abstrata não pode ser instanciada.
* Serve como modelo para outras classes.

Exemplo:

```dart
abstract class Forma {
  double calcularArea();
}
```

## 🧠 Meu entendimento

* Classes abstratas servem para definir comportamentos obrigatórios.

---

# ❓ Pergunta 6

## Pergunta feita para IA

```txt
Quando devo usar classes abstratas em vez de classes concretas?
```

## 💡 Resposta da IA

* Quando existir comportamento comum entre classes.

## 🧠 Meu entendimento

* Uso abstração quando quero definir regras sem criar objetos diretamente.

---

# ❓ Pergunta 7

## Pergunta feita para IA

```txt
O que é herança em Dart e como ela funciona?
```

## 💡 Resposta da IA

Exemplo:

```dart
class Veiculo {}

class Carro extends Veiculo {}
```

## 🧠 Meu entendimento

* Herança permite reutilizar código.
* A classe filha herda atributos e métodos.

---

# ❓ Pergunta 8

## Pergunta feita para IA

```txt
Qual a diferença entre herança e composição?
```

## 💡 Resposta da IA

* Herança representa relação "é um".
* Composição representa relação "tem um".

## 🧠 Meu entendimento

* Nem sempre herança é a melhor solução.
* Composição costuma deixar o código mais desacoplado.

---

# ❓ Pergunta 9

## Pergunta feita para IA

```txt
O que é uma interface em Dart e como ela define um contrato de comportamento?
```

## 💡 Resposta da IA

* Interface define métodos obrigatórios.

Exemplo:

```dart
abstract interface class Arquivo {
  void abrir();
}
```

## 🧠 Meu entendimento

* Interfaces obrigam implementação mantendo padronização.

---

# ❓ Pergunta 10

## Pergunta feita para IA

```txt
Como uma classe pode implementar uma interface?
```

## 💡 Resposta da IA

Exemplo:

```dart
class ArquivoTexto implements Arquivo {
  @override
  void abrir() {}
}
```

## 🧠 Meu entendimento

* Implementar significa assumir responsabilidade pelos métodos.

---

# ❓ Pergunta 11

## Pergunta feita para IA

```txt
Qual a diferença entre herança e implementação de interfaces?
```

## 💡 Resposta da IA

* Herança reutiliza implementação.
* Interface define contrato.

## 🧠 Meu entendimento

* Interface obriga comportamento.
* Herança compartilha código.

---

# ❓ Pergunta 12

## Pergunta feita para IA

```txt
Quais cenários devo usar métodos estáticos em vez de métodos de instância?
```

## 💡 Resposta da IA

Exemplo:

```dart
class Calculadora {
  static double soma(double a, double b) {
    return a + b;
  }
}
```

## 🧠 Meu entendimento

* Método estático não depende de objeto.
* Útil para funções utilitárias.

---

# ❓ Pergunta 13

## Pergunta feita para IA

```txt
Como acessar um método estático sem criar uma instância da classe?
```

## 💡 Resposta da IA

```dart
Calculadora.soma(2, 3);
```

## 🧠 Meu entendimento

* O acesso é feito diretamente pela classe.

---

# ❓ Pergunta 14

## Pergunta feita para IA

```txt
O que são enumeradores em Dart e para que servem?
```

## 💡 Resposta da IA

Exemplo:

```dart
enum Status {
  ativo,
  inativo
}
```

## 🧠 Meu entendimento

* Enum ajuda a limitar valores possíveis.

---

# ❓ Pergunta 15

## Pergunta feita para IA

```txt
Em quais situações é melhor usar enumeradores em vez de constantes?
```

## 💡 Resposta da IA

* Quando existir conjunto fixo de opções.

## 🧠 Meu entendimento

* Enum reduz erros e melhora legibilidade.

---

# ❓ Pergunta 16

## Pergunta feita para IA

```txt
Como posso criar um setter para modificar um atributo privado com validação?
```

## 💡 Resposta da IA

Exemplo:

```dart
class Produto {
  double _preco = 0;

  set preco(double valor) {
    if (valor > 0) {
      _preco = valor;
    }
  }
}
```

## 🧠 Meu entendimento

* Setter é útil para proteger regras do objeto.

---

# ❓ Pergunta 17

## Pergunta feita para IA

```txt
Como posso sobrescrever um método da classe pai?
```

## 💡 Resposta da IA

Utilizando `@override`.

## 🧠 Meu entendimento

* A anotação deixa explícito que estou alterando comportamento herdado.

---

# ❓ Pergunta 18

## Pergunta feita para IA

```txt
O que são métodos estáticos e como diferem dos métodos de instância?
```

## 💡 Resposta da IA

* Estáticos pertencem à classe.
* Instância pertencem ao objeto.

## 🧠 Meu entendimento

* Métodos estáticos não acessam estado do objeto diretamente.

---

# ✅ Conclusão

* Com essa atividade consegui reforçar conceitos mais avançados de orientação a objetos em Dart.
* Entendi melhor quando utilizar herança, interfaces, classes abstratas e composição.
* Também consegui visualizar melhor o uso de getters, setters e métodos estáticos para organizar responsabilidades no projeto.
* A IA ajudou como apoio para consolidar conceitos e trazer exemplos simples para estudo antes da implementação prática.
