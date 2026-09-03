# Funções Agregadas em SQLite

## Objetivo

Aprender a realizar cálculos e análises utilizando funções agregadas.

---

## Base de Dados para Exemplos

Crie a tabela:

```sql
CREATE TABLE alunos (
    id INTEGER PRIMARY KEY,
    nome TEXT NOT NULL,
    idade INTEGER,
    nota REAL
);
```

Adicione os registros:

```sql
INSERT INTO alunos (nome, idade, nota)
VALUES ('Maria', 20, 8.5);

INSERT INTO alunos (nome, idade, nota)
VALUES ('João', 22, 7.0);

INSERT INTO alunos (nome, idade, nota)
VALUES ('Ana', 21, 9.5);

INSERT INTO alunos (nome, idade, nota)
VALUES ('Carlos', 23, 6.5);
```

---

## Contar Registros

Consulta:

```sql
SELECT COUNT(id) AS total_alunos
FROM alunos;
```

Resultado esperado:

```text
4
```

---

## Somar Valores

Consulta:

```sql
SELECT SUM(nota) AS soma_notas
FROM alunos;
```

Resultado esperado:

```text
31.5
```

---

## Calcular Média

Consulta:

```sql
SELECT AVG(nota) AS media_notas
FROM alunos;
```

Resultado esperado:

```text
7.875
```

---

## Maior Valor

Consulta:

```sql
SELECT MAX(nota) AS maior_nota
FROM alunos;
```

Resultado esperado:

```text
9.5
```

---

## Menor Valor

Consulta:

```sql
SELECT MIN(nota) AS menor_nota
FROM alunos;
```

Resultado esperado:

```text
6.5
```

---

## Renomeando Colunas

Consulta:

```sql
SELECT AVG(nota) AS media_da_turma
FROM alunos;
```

Resultado esperado:

```text
7.875
```

---

## Agrupando Dados

Crie a tabela:

```sql
CREATE TABLE matriculas (
    id INTEGER PRIMARY KEY,
    curso TEXT,
    quantidade INTEGER
);
```

Insira os dados:

```sql
INSERT INTO matriculas (curso, quantidade)
VALUES ('ADS', 30);

INSERT INTO matriculas (curso, quantidade)
VALUES ('ADS', 25);

INSERT INTO matriculas (curso, quantidade)
VALUES ('Ciência da Computação', 20);

INSERT INTO matriculas (curso, quantidade)
VALUES ('Ciência da Computação', 15);
```

Consulta:

```sql
SELECT curso,
       SUM(quantidade) AS total_alunos
FROM matriculas
GROUP BY curso;
```

Resultado esperado:

```text
ADS: 55
Ciência da Computação: 35
```

---

## Filtrando Grupos

Consulta:

```sql
SELECT curso,
       SUM(quantidade) AS total_alunos
FROM matriculas
GROUP BY curso
HAVING SUM(quantidade) > 40;
```

Resultado esperado:

```text
ADS: 55
```

---

## Relatório Consolidado

Consulta:

```sql
SELECT
    COUNT(id) AS total_alunos,
    AVG(nota) AS media,
    MAX(nota) AS maior_nota,
    MIN(nota) AS menor_nota
FROM alunos;
```

Resultado esperado:

```text
Total de alunos: 4
Média: 7.875
