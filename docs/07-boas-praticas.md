# Boas Práticas em SQLite

## Objetivo

Conhecer práticas recomendadas para criar bancos de dados organizados, seguros, fáceis de manter e preparados para crescimento.

---

## Padronização de Nomes

Utilize nomes claros e consistentes para tabelas e colunas.

### Recomendado

```text
alunos
cursos
professores
data_nascimento
nome_completo
```

### Evite

```text
tbl1
dados2
x
abc
```

Nomes descritivos facilitam a manutenção e o entendimento do banco de dados.

---

## Defina Chaves Primárias

Toda tabela deve possuir uma chave primária.

Exemplo:

```sql
CREATE TABLE alunos (
    id INTEGER PRIMARY KEY,
    nome TEXT NOT NULL
);
```

A chave primária garante a identificação única de cada registro.

---

## Evite Dados Duplicados

Não repita informações que podem ser armazenadas em outra tabela.

### Exemplo Incorreto

```text
Aluno | Curso
Maria | ADS

Aluno | Curso
João  | ADS
```

### Exemplo Correto

Tabela cursos:

```text
1 | ADS
```

Tabela alunos:

```text
Maria | 1
João  | 1
```

Utilize relacionamentos para evitar redundância.

---

## Utilize Tipos de Dados Adequados

Escolha o tipo de dado correto para cada coluna.

Exemplo:

```sql
CREATE TABLE alunos (
    id INTEGER,
    nome TEXT,
    nota REAL
);
```

Tipos mais comuns:

```text
INTEGER  → números inteiros
REAL     → números decimais
TEXT     → textos
BLOB     → arquivos binários
NULL     → valor vazio
```

---

## Utilize NOT NULL Quando Necessário

Campos obrigatórios devem ser definidos como NOT NULL.

Exemplo:

```sql
CREATE TABLE alunos (
    id INTEGER PRIMARY KEY,
    nome TEXT NOT NULL
);
```

Dessa forma o nome não poderá ficar vazio.

---

## Faça Backup Regularmente

Mantenha cópias atualizadas do banco de dados.

Exemplo de backup:

```text
escola.db
```

Cópia:

```text
backup_escola.db
```

Benefícios:

- Proteção contra perda de dados
- Recuperação de falhas
- Maior segurança

---

## Teste Antes de Excluir Dados

Antes de executar um DELETE, utilize SELECT para conferir os registros.

Exemplo:

```sql
SELECT *
FROM alunos
WHERE id = 5;
```

Depois:

```sql
DELETE FROM alunos
WHERE id = 5;
```

Essa prática evita exclusões acidentais.

---

## Teste Antes de Atualizar Dados

Verifique o registro antes de executar UPDATE.

Exemplo:

```sql
SELECT *
FROM alunos
WHERE id = 1;
```

Atualização:

```sql
UPDATE alunos
SET nome = 'Maria Silva'
WHERE id = 1;
```

---

## Sempre Utilize WHERE em UPDATE e DELETE

Exemplo correto:

```sql
UPDATE alunos
SET curso = 'ADS'
WHERE id = 1;
```

Exemplo perigoso:

```sql
UPDATE alunos
SET curso = 'ADS';
```

O segundo comando altera todos os registros da tabela.

---

## Documente
