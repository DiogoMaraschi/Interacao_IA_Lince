# 🤖 IA como Apoio — Coleções em Dart

> Atividade desenvolvida utilizando IA como ferramenta de apoio para estudos sobre coleções em Dart.

---

# 📚 Conteúdos estudados

- Listas (`List`)
- Conjuntos (`Set`)
- Mapas (`Map`)
- Iteração
- Métodos úteis
- Performance
- Boas práticas

---

# 1️⃣ Trabalhando com Listas

## ❓ Pergunta feita para IA

```txt
Quais as boas práticas no uso de listas em dart?
```

## 💡 Resposta da IA

- Utilizar tipagem explícita.
- Evitar listas muito grandes sem necessidade.
- Preferir métodos nativos para manipulação.
- Manter listas organizadas e legíveis.

## 💻 Exemplo

```dart
List<String> nomes = ["Lucas", "Maria", "João"];

nomes.add("Ana");

print(nomes);
```

## 🧠 Meu entendimento
- Importante utilizar métodos nativos para manipulação das listas, evitar modificar a lista durante a iteração, e trabalhar com listas tipadas.

---

# 2️⃣ Performance com Listas

## ❓ Pergunta feita para IA

```txt
Que práticas posso adotar para trazer uma melhor performance ao usar listas em dart?
```

## 💡 Resposta da IA

- Evitar loops desnecessários.
- Utilizar `forEach`, `map` e `where` quando apropriado.
- Evitar recriar listas frequentemente.
- Utilizar listas tipadas.

## 💻 Exemplo

```dart
List<int> numeros = [1, 2, 3, 4, 5];

List<int> pares = numeros.where((n) => n % 2 == 0).toList();

print(pares);
```

## 🧠 Meu entendimento
- Não só para listas, mas evitar loops desnecessarios e complexos para deixar o código mais leve, não recriar listas sem necessidade, e tipar as listas.

---

# 3️⃣ O que evitar no uso de listas

## ❓ Pergunta feita para IA

```txt
O que não é recomendado fazer quando usado listas em dart?
```

## 💡 Resposta da IA

- Alterar listas durante iteração.
- Utilizar `dynamic` sem necessidade.
- Criar listas excessivamente grandes.
- Duplicar dados sem necessidade.

## 💻 Exemplo

```dart
List<int> numeros = [1, 2, 3];

for (var numero in numeros) {
  print(numero);
}
```

## 🧠 Meu entendimento
- Listas grandes demoram a serem percorridas, então usar apenas quando necessario. Cuidar ao manter dados duplicados, preferir tipar a lista a usar dynamic sempre.

---

# 4️⃣ Quando usar Listas e Mapas

## ❓ Pergunta feita para IA

```txt
Como entender quando usar listas e quando usar mapas?
```

## 💡 Resposta da IA

- `List` é ideal para coleções ordenadas.
- `Map` é indicado para estruturas chave-valor.
- Listas acessam elementos por índice.
- Mapas acessam elementos por chave.

## 💻 Exemplo

```dart
List<String> frutas = ["Maçã", "Banana"];

Map<String, int> estoque = {
  "Maçã": 10,
  "Banana": 5
};
```


# 5️⃣ Trabalhando com Mapas

## ❓ Pergunta feita para IA

```txt
Em dart quais práticas são interessantes no uso de mapas.
```

## 💡 Resposta da IA

- Utilizar chaves padronizadas.
- Evitar mapas excessivamente aninhados.
- Verificar existência de chaves antes do acesso.

## 💻 Exemplo

```dart
Map<String, dynamic> usuario = {
  "nome": "Lucas",
  "idade": 25
};

print(usuario["nome"]);
```

## 🧠 Meu entendimento
- Utilizar containsKey para verificar se a chave existe antes de utilizar previne contra erros. Usar maps dentro de maps pode tornar o código copmlexo de ler e de difícil manutenção, interessante usar classes no lugar.

---

# 6️⃣ Métodos úteis para List e Set

## ❓ Pergunta feita para IA

```txt
Quais métodos podem me auxiliar no uso de listas e sets em dart?
```

## 💡 Resposta da IA

- `add()`
- `remove()`
- `contains()`
- `where()`
- `map()`
- `first`
- `last`

## 💻 Exemplo

```dart
Set<int> numeros = {1, 2, 3};

numeros.add(4);

print(numeros.contains(2));
```

## 🧠 Meu entendimento
- `add()` = adiciona um novo elemento.
- `remove()` = remove um elemento específico.
- `contains()` = verifica se determinado valor existe na coleção.
- `where()` = filtra elementos com base na condição.
- `map()` = transforma elementos da coleção em novos valores.
- `first` = retorna o primeiro elemento.
- `last` = retorna o último elemento.
---

# 7️⃣ Cuidados ao usar Sets

## ❓ Pergunta feita para IA

```txt
Quais cuidados devo levar ao usar sets?
```

## 💡 Resposta da IA

- Sets não permitem valores duplicados.
- Não garantem ordem dos elementos.
- Devem ser usados quando unicidade é importante.

## 💻 Exemplo

```dart
Set<String> nomes = {
  "Lucas",
  "Maria",
  "Lucas"
};

print(nomes);
```

## 🧠 Meu entendimento
- Diferente da lista, set não é ordenado, a posição do elemento pode variar já que as formas de manipulação do set acontece de outras formas. O foco é não ter duplicidade.

---

# 8️⃣ Método elementAtOrNull

## ❓ Pergunta feita para IA

```txt
Traga a documentação do método elementAtOrNull.
```

## 💡 Resposta da IA

O método `elementAtOrNull()` retorna o elemento em determinado índice ou `null` caso o índice não exista.

## 💻 Exemplo

```dart
List<String> nomes = ["Lucas", "Maria"];

print(nomes.elementAtOrNull(1));

print(nomes.elementAtOrNull(10));
```

## 🧠 Meu entendimento
- Um método que já traz contramedida, caso não tiver elemento no índice, retorna null.
---

# 9️⃣ Cenários favoráveis para Set e List

## ❓ Pergunta feita para IA

```txt
Mostre cenários favoráveis ao uso de set e listas em dart.
```

## 💡 Resposta da IA

- `List` é útil quando a ordem importa.
- `Set` é útil para evitar duplicidade.

## 💻 Exemplo

```dart
List<String> ranking = ["Ana", "Carlos", "Maria"];

Set<String> emailsUnicos = {
  "a@email.com",
  "b@email.com"
};
```

## 🧠 Meu entendimento
- Como disse a cima, set lida com valores únicos, já a lista lida com ordenados.
---

# 🔟 Método map()

## ❓ Pergunta feita para IA

```txt
Traga exemplos de uso do método map da estrutura de mapas do dart.
```

## 💡 Resposta da IA

O método `map()` permite transformar elementos de uma coleção.

## 💻 Exemplo

```dart
List<int> numeros = [1, 2, 3];

List<int> dobrados =
    numeros.map((numero) => numero * 2).toList();

print(dobrados);
```

## 🧠 Meu entendimento
- Map é util para trabalhar com valores em escala, como colocar todos os textos em upperCase, ou dar um desconto a produtos.

---

# 1️⃣1️⃣ Iteração eficiente em listas

## ❓ Pergunta feita para IA

```txt
Como iterar de forma eficiente em listas.
```

## 💡 Resposta da IA

- Utilizar `for in`.
- Utilizar `forEach` quando apropriado.
- Evitar loops desnecessários.

## 💻 Exemplo

```dart
List<String> nomes = ["Lucas", "Maria", "João"];

for (var nome in nomes) {
  print(nome);
}
```

## 🧠 Meu entendimento
- For in uso quando quero ter um controle melhor do loop, com break por exemplo, ou usar lógica mais complexa.
- ForEach uso quando vou executar ações simples e sem interromper o loop.
- Não criar loops que percorrem duas vezes o mesmo objeto.

---

# 1️⃣2️⃣ Diferença entre List, Set e Map

## ❓ Pergunta feita para IA

```txt
Qual a principal diferença entre List, Set e Map em dart?
```

## 💡 Resposta da IA

- `List` possui ordem e índice.
- `Set` não permite duplicados.
- `Map` trabalha com chave e valor.

## 💻 Exemplo

```dart
List<String> lista = ["A", "B"];

Set<String> conjunto = {"A", "B"};

Map<String, int> mapa = {
  "A": 1,
  "B": 2
};
```

## 🧠 Meu entendimento
- List = tem ordem, índice e permite repetidos.
- Set = sem duplicados, foco não é ordem.
- Map = chave e valor.

---

# 1️⃣3️⃣ Métodos úteis em coleções

## ❓ Pergunta feita para IA

```txt
Quais métodos são mais utilizados em coleções no dart?
```

## 💡 Resposta da IA

- `where()`
- `map()`
- `any()`
- `every()`
- `contains()`
- `reduce()`

## 💻 Exemplo

```dart
List<int> numeros = [1, 2, 3, 4];

bool possuiPar =
    numeros.any((numero) => numero % 2 == 0);

print(possuiPar);
```

## 🧠 Meu entendimento
- `where()` = filtra elementos com base na condição.
- `map()` = transforma elementos da coleção.
- `any()` = verifica se pelo menos um elemento atende a condição.
- `every()` = verifica se todos os elementos atendem a condição.
- `contains()` = verifica se a coleção possui determinado valor.
- `reduce()` = combina elementos em um único valor.

---

# ✅ Conclusão

A utilização da IA ajudou a compreender melhor o funcionamento das coleções no Dart, principalmente as diferenças entre listas, sets e mapas.

Além disso, os exemplos práticos facilitaram o entendimento dos métodos mais utilizados e das boas práticas relacionadas à performance e organização do código.