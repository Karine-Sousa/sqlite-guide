# Primeiros Passos com SQLite

## Objetivo

Aprender a criar um banco de dados, tabelas e inserir os primeiros registros utilizando SQLite.

---

## Pré-requisitos

Antes de iniciar, certifique-se de que:

- SQLite está instalado
- O comando `sqlite3` funciona no terminal
- Você concluiu as etapas do arquivo `02-instalacao.md`

---

## Criando um Banco de Dados

Abra o terminal e execute:

```bash
sqlite3 escola.db
```

O SQLite criará automaticamente o arquivo:

```text
escola.db
```

Esse arquivo armazenará todo o banco de dados.

---

## Verificando o Banco Aberto

No prompt do SQLite, você verá algo semelhante a:

```text
SQLite version 3.x.x
sqlite>
```

Isso indica que o banco está pronto para uso.

---

## Criando a Primeira Tabela

Digite o comando:

```sql
CREATE TABLE alunos (
    id INTEGER PRIMARY KEY,
    nome TEXT NOT NULL,
    curso TEXT
);
```

---

## Verificando a Estrutura da Tabela

Para visualizar a tabela criada:

```sql
.schema alunos
```

Resultado esperado:

```sql
CREATE TABLE alunos (
    id INTEGER PRIMARY KEY,
    nome TEXT NOT NULL,
    curso TEXT
);
```

---

## Listando Tabelas

Execute:

```sql
.tables
```

Resultado:

```text
alunos
```

---

## Inserindo Dados

Adicione um aluno:

```sql
INSERT INTO alunos (nome, curso)
VALUES ('Maria Silva', 'ADS');
```

Adicione outro:

```sql
INSERT INTO alunos (nome, curso)
VALUES ('João Santos', 'Ciência da Computação');
```

---

## Consultando os Dados

Visualize todos os registros:

```sql
SELECT * FROM alunos;
```

Resultado esperado:

```text
1|Maria Silva|ADS
2|João Santos|Ciência da Computação
```

---

## Formatando a Exibição dos Resultados

Ative o modo coluna:

```sql
.mode column
```

Ative os cabeçalhos:

```sql
.headers on
```

Execute novamente:

```sql
SELECT * FROM alunos;
```

Resultado:

```text
id   nome          curso
--   ------------  ---------------------
1    Maria Silva   ADS
2    João Santos   Ciência da Computação
```

---

## Salvando e Saindo

Para encerrar o SQLite:

```sql
.exit
```

ou

```sql
.quit
```

---

## Resumo

Nesta etapa você aprendeu a:

Criar um banco de dados

Criar uma tabela

Inserir registros

Consultar informações

Listar tabelas

Encerrar uma sessão SQLite

---

## Próximos Passos

Continue para:

```text
04-consultas-basicas.md
```

onde serão apresentadas consultas SQL utilizando:

- SELECT
- WHERE
- ORDER BY
- UPDATE
- DELETE
