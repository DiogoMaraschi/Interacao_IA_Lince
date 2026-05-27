# 🤖 IA como Apoio — Variáveis em Dart

> Atividade da Lince Tech Academy utilizando IA como ferramenta de apoio nos estudos de Dart.
> A formatação foi feita com auxílio de IA, mas as perguntas e os campos de meus entedimentos foram preenchidas por mim.

---

# 📚 Conteúdos estudados

- Variáveis
- Null Safety
- late
- final e const
- Strings
- Números
- Booleanos

---

# ❓ Pergunta 1

## Pergunta feita para IA

```txt
Quais as boas práticas em dart declarando variáveis?
```

## 💡 Resposta da IA

- Utilizar nomes claros e descritivos.
- Preferir `final` sempre que o valor não mudar.
- Evitar uso excessivo de `dynamic`.
- Manter padrão de nomenclatura (`camelCase`).
- Declarar o tipo explicitamente quando melhorar a leitura.

## 🧠 Meu entendimento
- No geral o dart não reinventa a roda, utiliza muito dos padrões das demais linguagens, além de ser fortemente tipada e lidar com opcionais, assim como no Swift que venho estudando. 

---

# ❓ Pergunta 2

## Pergunta feita para IA

```txt
Quais cuidados tomar quando crio variáveis com valor nulo trabalhando com dart?
```

## 💡 Resposta da IA

- Evitar acessar variáveis nulas sem validação.
- Utilizar `?`, `??` e `!` corretamente.
- Aproveitar o Null Safety do Dart.
- Validar valores antes do uso.

## 🧠 Meu entendimento
- Desembrulhar as opcionais é algo importante pra não haver crash por nullExcection.

- String? nome;
Indica que o nome pode ser uma String ou ser null.

- String? nome; 
  print(nome ?? 'Nome não informado!'); 
Usa um valor default em caso de null.

- String? nome; 
  print(nome!); 
Força a desembrulhar a variavel como se não fosse null, mesmo que possa ser, podendo gerar exceção. 

- Usar opcionais apenas em variaveis que podem vir a ter um valor null, nunca em valores que precisam ter valor.

- Caso a variavel não seja opcional, o null safety vai exigir que tenha uma valor antes de ser utilizada. 

---

# ❓ Pergunta 3

## Pergunta feita para IA

```txt
No dart quando usar variáveis nulas e quando usar o modificador late?
```

## 💡 Resposta da IA

- Variáveis nulas são úteis quando o valor realmente pode não existir.
- `late` é usado quando o valor será inicializado posteriormente.
- `late` evita inicialização imediata.

## 🧠 Meu entendimento
- Usar variáveis nulas apenas quando o valor realmente pode não existir, dados de API podem vir incompletos, ou sejam valores opcionais.
-Usar late quando é um valor nonNull, mas que será inicializado posteriormente.
---

# ❓ Pergunta 4

## Pergunta feita para IA

```txt
Gostaria de entender quais os benefícios de utilização do modificador "late" no Dart.
```

## 💡 Resposta da IA

- Permite inicialização posterior.
- Ajuda na performance em alguns cenários.
- Muito utilizado com dependências e inicializações demoradas.

## 🧠 Meu entendimento
- Útil quando o valor ainda não está disponível no momento da criação, null safety continua agindo.
- Cuidado para não acessar a variável antes de atribuir valor.
---

# ❓ Pergunta 5

## Pergunta feita para IA

```txt
Mostre cenários onde não se deveria usar o late no dart.
```

## 💡 Resposta da IA

- Quando a variável pode não ser inicializada.
- Em valores simples que já podem ser definidos imediatamente.
- Quando o uso aumenta a complexidade desnecessariamente.

## 🧠 Meu entendimento
- Como qualquer modificador, é importante usar apenas onde o caso pede, porque pode causar complexidade.
---

# ❓ Pergunta 6

## Pergunta feita para IA

```txt
Quais as diferenças entre final e const em dart?
```

## 💡 Resposta da IA

- `final` recebe valor apenas uma vez.
- `const` representa constantes em tempo de compilação.
- `const` é imutável e otimizado para valores fixos.

## 🧠 Meu entendimento
- final posso atribuir valor no tempo de execução.
- const preciso atribuir valor no tempo de compilação.
- Porém final posso atribuir listas e mexer nelas, em const o conteúdo fica fixo.

---

# ❓ Pergunta 7

## Pergunta feita para IA

```txt
Em dart mostre quando usar final e const.
```

## 💡 Resposta da IA

```dart
final dataAtual = DateTime.now();

const pi = 3.14;
```

## 🧠 Meu entendimento
- final é usado quando o valor só será conhecido em execução.
- const é utilizado para valores fixos.

---

# ❓ Pergunta 8

## Pergunta feita para IA

```txt
Me traga um exemplo do uso do método split() em dart.
```

## 💡 Resposta da IA

```dart
String texto = "maça,banana,uva";

List<String> frutas = texto.split(",");

print(frutas);
```

## 🧠 Meu entendimento
- É um método usado para separar texto utilizando um char específico, nesse caso a ',' mas pode ser usado espaço ' ' para separar nomes completos, ou ler arquivos DSV e dados de API.

---

# ❓ Pergunta 9

## Pergunta feita para IA

```txt
Traga a documentação dos métodos de variáveis inteiras.
```

## 💡 Resposta da IA

Alguns métodos úteis para inteiros em Dart:

- `toString()`
- `abs()`
- `compareTo()`
- `clamp()`
- `isEven`
- `isOdd`

## 🧠 Meu entendimento
- toString: converte o valor int para String.
- abs: retorna o valor absoluto.
- compareTo(num): retorna 1 se for maior, 0 se for igual, -1 se for menor.
- clamp(min,max): limita o valor dentro do intervalo.
- isEven: bool que retorna se é par.
- isOdd: bool que retorna se é impar.

---

# ❓ Pergunta 10

## Pergunta feita para IA

```txt
Como funcionam variáveis booleanas em dart?
```

## 💡 Resposta da IA

- Variáveis booleanas utilizam o tipo `bool`.
- Possuem apenas dois valores: `true` e `false`.
- São muito usadas em condições e validações.

```dart
bool usuarioLogado = true;
```

## 🧠 Meu entendimento
- Representa valores lógicos, true or false, pode ser usado em variável ou em condições.
- Pode acompanhar os operadores lógicos como &&, ! e ||, =, !=, <,>, <=, =>.
---

# ✅ Conclusão
- Com essa atividade consegui entender melhor como o Dart lida com variáveis, principalmente em relação ao Null Safety e opcionais. Também achei interessante perceber que ele possui várias semelhanças com o Swift, principalmente na tipagem forte e no uso de opcionais.

A IA ajudou bastante para esclarecer dúvidas rápidas e trazer exemplos simples dos conceitos. Os pontos que mais me chamaram atenção foram o uso do late, a diferença entre final e const e como o Dart tenta evitar erros relacionados a null.

