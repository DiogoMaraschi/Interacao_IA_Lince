# IA Flutter SQLite

## O que é um banco de dados SQLite e como ele funciona em Flutter?

SQLite é um banco de dados relacional leve, armazenado em um único arquivo dentro do aplicativo. Ele permite salvar dados localmente, sem necessidade de conexão com a internet ou um servidor externo.

No Flutter, normalmente utilizamos o pacote `sqflite` para criar e manipular o banco de dados.

### Observações

- O banco fica salvo no dispositivo.
- É indicado para aplicativos que precisam armazenar informações localmente.
- Não depende de conexão com a internet.

---

# Quais são as vantagens de usar SQLite em aplicativos Flutter?

- Não necessita de servidor.
- Funciona offline.
- Possui boa performance.
- Fácil integração com Flutter.
- Banco de dados relacional.
- Permite persistir dados entre execuções do aplicativo.

### Observações

É ideal para aplicativos que precisam salvar informações como usuários, favoritos, histórico, configurações e cache.

---

# Quais são os tipos de dados básicos que posso armazenar em SQLite?

Os principais tipos são:

- INTEGER
- TEXT
- REAL
- BLOB
- NULL

### Observações

Mesmo sendo um banco simples, ele atende praticamente todas as necessidades de um aplicativo mobile.

---

# Como inserir novos registros em uma tabela SQLite usando Flutter?

Utiliza-se o comando SQL:

```sql
INSERT INTO pessoa(nome, email)
VALUES ('Diogo', 'diogo@email.com');
```

No Flutter normalmente utilizamos:

```dart
await db.insert(
  'pessoa',
  {
    'nome': 'Diogo',
    'email': 'diogo@email.com',
  },
);
```

### Observações

O método `insert()` retorna o ID do registro inserido.

---

# Como inserir vários registros de uma vez?

Pode ser feito de três formas:

- Executando vários INSERTs.
- Utilizando Batch.
- Utilizando Transaction.

### Observações

O uso de transações melhora o desempenho quando vários registros serão inseridos.

---

# Como obter o ID do último registro inserido?

O método `insert()` retorna um inteiro contendo o ID gerado automaticamente.

```dart
final id = await db.insert(...);
```

### Observações

Esse ID normalmente é utilizado para criar relacionamentos entre tabelas.

---

# Como filtrar resultados utilizando WHERE?

Utiliza-se a cláusula WHERE.

```sql
SELECT *
FROM pessoa
WHERE nome = 'Diogo';
```

### Observações

WHERE evita trazer registros desnecessários.

---

# Como agrupar resultados utilizando GROUP BY?

Exemplo:

```sql
SELECT tipoSanguineo,
COUNT(*)
FROM pessoa
GROUP BY tipoSanguineo;
```

### Observações

É utilizado para estatísticas e agrupamentos.

---

# Como excluir registros?

Utiliza-se o comando DELETE.

```sql
DELETE FROM pessoa
WHERE id = 1;
```

### Observações

Nunca utilizar DELETE sem WHERE.

Errado:

```sql
DELETE FROM pessoa;
```

Esse comando apaga todos os registros.

---

# Quais cuidados devo ter com UPDATE, INSERT e DELETE?

## UPDATE

Sempre utilizar WHERE.

Errado:

```sql
UPDATE pessoa
SET nome = 'Carlos';
```

Correto:

```sql
UPDATE pessoa
SET nome = 'Carlos'
WHERE id = 1;
```

---

## DELETE

Sempre utilizar WHERE.

---

## INSERT

Validar os dados antes da inserção.

### Observações

Os comandos UPDATE e DELETE sem WHERE podem alterar ou excluir todos os registros da tabela.

---

# Como criar tabelas relacionadas?

Exemplo:

Tabela Pessoa

- id
- nome

Tabela Telefone

- id
- numero
- idPessoa

O campo `idPessoa` referencia o `id` da tabela Pessoa.

### Observações

Esse relacionamento permite que uma pessoa possua vários telefones.

---

# Como consultar tabelas relacionadas utilizando JOIN?

```sql
SELECT
p.nome,
t.numero
FROM pessoa p
JOIN telefone t
ON p.id = t.idPessoa;
```

### Observações

JOIN é utilizado para combinar informações de tabelas relacionadas.

---

# O que são transações?

Transações agrupam várias operações em uma única execução.

Fluxo:

BEGIN

↓

Executa todas as operações

↓

COMMIT

Caso aconteça algum erro:

ROLLBACK

### Observações

Ou todas as operações acontecem, ou nenhuma acontece.

Isso garante integridade dos dados.

---

# Como reverter uma transação?

Utiliza-se:

```sql
ROLLBACK;
```

### Observações

Rollback desfaz todas as alterações realizadas durante a transação.

---

# Quais as vantagens das transações?

- Evitam inconsistência dos dados.
- Garantem integridade.
- Melhoram segurança em operações críticas.
- Muito utilizadas em sistemas bancários e financeiros.

---

# Como criar um banco e uma tabela em Flutter?

Normalmente utiliza-se:

```dart
openDatabase()
```

No callback `onCreate` executa-se:

```sql
CREATE TABLE pessoa(
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    nome TEXT,
    email TEXT
);
```

### Observações

O banco é criado apenas na primeira execução.

---

# Dicas para otimizar consultas

- Utilizar WHERE sempre que possível.
- Buscar apenas as colunas necessárias.
- Criar índices quando necessário.
- Evitar SELECT * quando não for preciso.
- Utilizar transações para grandes quantidades de inserções.

---

# CRUD

CRUD representa as quatro operações básicas de um banco de dados.

Create → INSERT

Read → SELECT

Update → UPDATE

Delete → DELETE

---

# Resumo Final

## Principais comandos SQL

CREATE TABLE → cria tabela

INSERT → insere registros

SELECT → consulta registros

UPDATE → altera registros

DELETE → exclui registros

WHERE → filtra registros

GROUP BY → agrupa registros

JOIN → relaciona tabelas

BEGIN → inicia transação

COMMIT → confirma alterações

ROLLBACK → desfaz alterações

---

# Conclusão

SQLite é uma excelente opção para aplicações Flutter que necessitam armazenar dados localmente. Durante esse estudo foi possível compreender como realizar operações de CRUD, relacionamentos entre tabelas, consultas utilizando JOIN, agrupamentos com GROUP BY e a importância das transações para garantir a integridade dos dados. Também foi possível entender boas práticas, como sempre utilizar WHERE em UPDATE e DELETE e utilizar transações quando várias alterações precisam ocorrer juntas.