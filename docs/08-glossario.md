# Glossário de Termos

## Objetivo

Apresentar os principais conceitos utilizados em Banco de Dados, SQL e SQLite para auxiliar estudantes e iniciantes.

---

## Banco de Dados

Conjunto organizado de informações armazenadas de forma estruturada para permitir consulta, atualização e gerenciamento dos dados.

---

## SQLite

Sistema Gerenciador de Banco de Dados Relacional (SGBD) leve, gratuito e baseado em arquivos.

Não necessita de servidor dedicado para funcionamento.

---

## SQL

Sigla para Structured Query Language.

Linguagem utilizada para criar, consultar, atualizar e remover dados em bancos de dados relacionais.

---

## Tabela

Estrutura utilizada para armazenar dados em linhas e colunas.

Exemplo:

```text
alunos
```

```text
id | nome | curso
```

---

## Registro

Cada linha de uma tabela.

Exemplo:

```text
1 | Maria Silva | ADS
```

Este conjunto de dados representa um registro.

---

## Campo

Cada coluna de uma tabela.

Exemplo:

```text
nome
curso
idade
```

---

## Chave Primária

Campo que identifica de forma única cada registro de uma tabela.

Exemplo:

```text
id
```

Não pode possuir valores duplicados.

---

## Chave Estrangeira

Campo responsável por criar um relacionamento entre tabelas.

Permite associar informações sem duplicar dados.

---

## Relacionamento

Ligação existente entre duas ou mais tabelas.

Exemplo:

```text
Cursos → Alunos
```

Um curso pode possuir vários alunos.

---

## Consulta

Comando utilizado para recuperar informações do banco de dados.

Exemplo:

```sql
SELECT * FROM alunos;
```

---

## SELECT

Comando utilizado para consultar dados.

Exemplo:

```sql
SELECT nome
FROM alunos;
```

---

## WHERE

Cláusula utilizada para filtrar registros.

Exemplo:

```sql
SELECT *
FROM alunos
WHERE curso = 'ADS';
```

---

## ORDER BY

Comando utilizado para ordenar resultados.

Exemplo:

```sql
SELECT *
FROM alunos
ORDER BY nome;
```

---

## INSERT

Comando utilizado para adicionar registros.

Exemplo:

```sql
INSERT INTO alunos (nome)
VALUES ('Maria');
```

---

## UPDATE

Comando utilizado para alterar registros existentes.

Exemplo:

```sql
UPDATE alunos
SET curso = 'ADS'
WHERE id = 1;
```

---

## DELETE

Comando utilizado para excluir registros.

Exemplo:

```sql
DELETE FROM alunos
WHERE id = 1;
```

---

## COUNT

Função utilizada para contar registros.

Exemplo:

```sql
SELECT COUNT(id)
FROM alunos;
```

---

## SUM

Função utilizada para somar valores.

Exemplo:

```sql
SELECT SUM(nota)
FROM alunos;
```

---

## AVG

Função utilizada para calcular médias.

Exemplo:

```sql
SELECT AVG(nota)
FROM alunos;
```

---

## MAX

Função utilizada para localizar o maior valor de uma coluna.

Exemplo:

```sql
SELECT MAX(nota)
FROM alunos;
```

---

## MIN

Função utilizada para localizar o menor valor de uma coluna.

Exemplo:

```sql
SELECT MIN(nota)
FROM alunos;
```

---

## JOIN

Comando utilizado para combinar informações de duas ou mais tabelas relacionadas.

Exemplo:

```sql
SELECT alunos.nome,
       cursos.nome
FROM alunos
INNER JOIN cursos
ON alunos.id_curso = cursos.id;
```

---

## GROUP BY

Comando utilizado para agrupar registros com características em comum.

Exemplo:

```sql
SELECT curso,
       COUNT(id)
FROM alunos
GROUP BY curso;
```

---

## HAVING

Cláusula utilizada para filtrar grupos após o agrupamento.

Exemplo:

```sql
SELECT curso,
       COUNT(id)
FROM alunos
GROUP BY curso
HAVING COUNT(id) > 5;
```

---

## Integridade Referencial

Conjunto de regras que garante a consistência dos relacionamentos entre tabelas.

Evita referências inválidas e registros órfãos.

---

## SGBD

Sigla para Sistema Gerenciador de Banco de Dados.

Responsável por armazenar, organizar e gerenciar dados.

Exemplos:

- SQLite
- MySQL
- PostgreSQL
- SQL Server
- Oracle Database

---

## Backup

Cópia de segurança dos dados armazenados em um banco de dados.

Seu objetivo é permitir a recuperação das informações em caso de falhas ou exclusões acidentais.

---

## Índice (Index)

Estrutura utilizada para acelerar consultas em tabelas.

Melhora o desempenho em pesquisas frequentes.

---

## Normalização

Processo de organização dos dados para reduzir redundâncias e melhorar a integridade das informações.

---

## Boas Práticas

Conjunto de recomendações para criar bancos de dados mais seguros, organizados e eficientes.

Incluem:

- Padronização de nomes
- Uso de chaves primárias
- Criação de backups
- Documentação adequada
- Validação de dados

---

## Resumo

Neste guia foram abordados os principais conceitos necessários para iniciar seus estudos em SQLite e Banco de Dados Relacionais.

Com esse conhecimento você já é capaz de:

- Criar bancos de dados
- Criar tabelas
- Inserir registros
- Consultar informações
- Atualizar dados
- Excluir registros
- Criar relacionamentos
- Utilizar funções agregadas
- Aplicar boas práticas

---

## Próximos Estudos

Após concluir este guia, recomenda-se estudar:

- Subconsultas (Subqueries)
- Views
- Triggers
- Índices Avançados
- Modelagem de Dados
- Banco de Dados PostgreSQL
- Banco de Dados MySQL
- SQL Avançado
