# Lince Tech Academy - Flutter: Programação Assíncrona

## Introdução

Durante esta atividade utilizei uma ferramenta de Inteligência Artificial como apoio para estudar conceitos relacionados à programação assíncrona no Flutter.

O objetivo foi entender como funcionam operações assíncronas, Future, async/await, requisições HTTP, manipulação de JSON e boas práticas na organização do código.

---

# Programação Assíncrona

## Pergunta feita para IA:

O que é programação assíncrona em Flutter e por que ela é importante?

## Resposta da IA:

Programação assíncrona é uma forma de executar tarefas que podem demorar para serem concluídas sem bloquear a execução principal do aplicativo.

No Flutter isso é muito importante porque a interface precisa continuar respondendo enquanto outras operações acontecem.

Exemplos de operações assíncronas:

- Buscar dados em uma API;
- Ler arquivos;
- Acessar banco de dados;
- Fazer downloads.

Sem programação assíncrona, o aplicativo poderia ficar congelado esperando uma operação terminar.

## Minha observação:

Entendi que operações demoradas não devem bloquear a tela do usuário. A programação assíncrona permite que o Flutter continue funcionando enquanto aguarda uma resposta.

---

# Cuidados com programação assíncrona

## Pergunta feita para IA:

Quais cuidados devo ter usando programação assíncrona?

## Resposta da IA:

Alguns cuidados importantes são:

- Sempre tratar erros;
- Evitar chamadas desnecessárias;
- Não bloquear a Thread principal;
- Verificar se o Widget ainda existe antes de atualizar a tela;
- Organizar chamadas externas fora das telas.

## Minha observação:

Percebi que usar async melhora o aplicativo, porém se for usado sem organização pode deixar o código difícil de controlar.

---

# Isolates no Flutter

## Pergunta feita para IA:

O que são isolates em Flutter?

## Resposta da IA:

Isolates são unidades de execução separadas no Dart.

Eles permitem executar tarefas pesadas sem afetar a Thread principal onde a interface é executada.

São úteis para:

- Processamento de muitos dados;
- Conversões grandes;
- Operações que exigem muito processamento.

## Minha observação:

Entendi que Future não cria outra Thread, apenas trabalha de forma assíncrona. Para processamento pesado usamos Isolates.

---

# Event Loop

## Pergunta feita para IA:

Qual o conceito do Loop de Eventos em Flutter?

## Resposta da IA:

O Event Loop é responsável por controlar a ordem de execução das tarefas.

Ele verifica eventos pendentes e executa quando possível.

O Dart trabalha com:

- Eventos síncronos;
- Microtasks;
- Futures.

## Minha observação:

O Event Loop é o que permite que várias tarefas sejam organizadas sem travar o aplicativo.

---

# Future

## Pergunta feita para IA:

O que é um Future em Dart e como ele funciona?

## Resposta da IA:

Future representa um valor que será entregue no futuro.

Ele pode terminar de duas formas:

- Com sucesso retornando um valor;
- Com erro retornando uma exceção.

Exemplo:

```dart
Future<String> buscarUsuario() async {
  return "João";
}
```

## Minha observação:

Comparei Future como uma promessa de retorno. Eu faço uma chamada e quando terminar recebo o resultado.

---

# Async e Await

## Pergunta feita para IA:

Como posso usar async e await para trabalhar com Future?

## Resposta da IA:

O async informa que uma função possui código assíncrono.

O await pausa aquela execução até receber o resultado do Future.

Exemplo:

```dart
void carregarDados() async {

  String usuario = await buscarUsuario();

  print(usuario);

}
```

## Minha observação:

O async e await deixam o código mais simples de entender, parecendo uma execução normal.

---

# Tratamento de erros com Try Catch

## Pergunta feita para IA:

Como lidar com erros em operações assíncronas usando try-catch?

## Resposta da IA:

Podemos utilizar try-catch para capturar erros durante uma operação.

Exemplo:

```dart
try {

  var resposta = await buscarDados();

} catch(erro) {

  print("Erro encontrado");

}
```

## Minha observação:

É importante tratar erros principalmente em APIs, pois a internet ou servidor podem falhar.

---

# Métodos HTTP

## Pergunta feita para IA:

Traga a explicação dos métodos HTTP.

## Resposta da IA:

Os principais métodos HTTP são:

### GET

Utilizado para buscar informações.

Exemplo:
Buscar uma lista de usuários.

### POST

Utilizado para criar novos dados.

Exemplo:
Cadastrar um usuário.

### PUT

Atualiza um registro inteiro.

### PATCH

Atualiza apenas algumas informações.

### DELETE

Remove algum dado.

## Minha observação:

Cada método representa uma ação diferente que queremos realizar com uma API.

---

# Códigos HTTP

## Pergunta feita para IA:

Como lidar com diferentes códigos de resposta HTTP?

## Resposta da IA:

Alguns códigos comuns:

## 200

A requisição ocorreu com sucesso.

## 404

O recurso não foi encontrado.

## 500

Erro interno no servidor.

Exemplo:

```dart
if(response.statusCode == 200){

 print("Sucesso");

}else{

 print("Erro");

}
```

## Minha observação:

Antes de utilizar uma resposta de API sempre precisamos validar se ocorreu corretamente.

---

# JSON

## Pergunta feita para IA:

O que é JSON e como ele é usado no Flutter?

## Resposta da IA:

JSON é um formato utilizado para troca de informações entre sistemas.

Exemplo:

```json
{
 "nome": "Maria",
 "idade": 25
}
```

No Flutter podemos converter JSON para objetos Dart.

## Minha observação:

É o formato mais comum utilizado quando consumimos APIs.

---

# Acessando valores JSON

## Pergunta feita para IA:

Como acessar valores específicos em um objeto JSON?

## Resposta da IA:

Podemos acessar através das chaves:

```dart
var nome = dados["nome"];
```

## Minha observação:

Funciona parecido com um Map onde cada chave possui um valor.

---

# Arrays JSON

## Pergunta feita para IA:

Como lidar com arrays em JSON no Flutter?

## Resposta da IA:

Quando recebemos uma lista JSON podemos percorrer os elementos.

Exemplo:

```json
[
 {
  "nome":"Ana"
 },
 {
  "nome":"Pedro"
 }
]
```

No Dart:

```dart
for(var item in lista){

 print(item["nome"]);

}
```

## Minha observação:

Entendi que muitas APIs retornam listas de objetos.

---

# Classes Dart com JSON

## Pergunta feita para IA:

Por que é útil mapear JSON para classes Dart?

## Resposta da IA:

Transformar JSON em classes deixa o código mais organizado.

Exemplo:

```dart
class Usuario {

 String nome;

 Usuario(this.nome);

 factory Usuario.fromJson(Map<String,dynamic> json){

  return Usuario(json["nome"]);

 }

}
```

## Minha observação:

Usar classes evita acessar textos diretamente e melhora a manutenção.

---

# Factory fromJson

## Pergunta feita para IA:

Como usar factory para criar objetos Dart a partir de JSON?

## Resposta da IA:

O factory cria um objeto utilizando os dados recebidos.

Exemplo:

```dart
factory Usuario.fromJson(Map json){

 return Usuario(json["nome"]);

}
```

## Minha observação:

É uma forma organizada de converter respostas da API.

---

# Método toJson()

## Pergunta feita para IA:

Como usar toJson para converter objetos Dart em JSON?

## Resposta da IA:

O método transforma objetos novamente em Map.

Exemplo:

```dart
Map<String,dynamic> toJson(){

 return {
  "nome": nome
 };

}
```

## Minha observação:

É usado principalmente quando precisamos enviar informações para uma API.

---

# Organização das requisições

## Pergunta feita para IA:

Como organizar minhas requisições no Flutter?

## Resposta da IA:

Boas práticas:

- Criar classes de Service;
- Separar regra de negócio da tela;
- Criar Models;
- Tratar erros;
- Evitar código repetido.

## Minha observação:

Separar responsabilidades deixa o projeto mais fácil de alterar.

---

# Loading em requisições

## Pergunta feita para IA:

Como exibir uma mensagem de carregamento enquanto uma requisição está acontecendo?

## Resposta da IA:

Podemos controlar usando uma variável.

Exemplo:

```dart
bool carregando = true;

CircularProgressIndicator();
```

Enquanto busca os dados mostramos o carregamento.

Depois escondemos e exibimos as informações.

## Minha observação:

Melhora a experiência do usuário porque mostra que algo está acontecendo.

---

# Conclusão

Com essa atividade consegui compreender melhor como o Flutter trabalha com operações assíncronas.

Os conceitos de Future, async/await, HTTP e JSON são essenciais para desenvolver aplicativos conectados com APIs externas.

Também percebi a importância de organizar o código utilizando Models e Services para facilitar manutenção.