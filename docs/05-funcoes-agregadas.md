# Funções Agregadas em SQLite

## Objetivo

Aprender a utilizar funções agregadas para realizar cálculos e análises sobre os dados armazenados em tabelas.

---

## Preparando o Ambiente

Crie a tabela:

```sql
CREATE TABLE alunos (
    id INTEGER PRIMARY KEY,
    nome TEXT NOT NULL,
    idade INTEGER,
    nota REAL
);
```

Insira os registros:

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

## COUNT()

Conta a quantidade de registros.

```sql
SELECT COUNT(*) AS total_alunos
FROM alunos;
```*
Resultado esperado: **4**

---

*# SUM*)

Soma os valores de uma coluna n*mérica.

```sql
SELECT SUM(nota) A* soma_notas
FROM alunos;
```

*esultado esperado: **31.5**

---

*# AVG()

Calcula a média dos valor*s.

```sql
SELECT AVG(nota) AS med*a_notas
FROM alunos;
```

Resultad* esperado: **7.875**

---

## MAX(*

Retorna o maior valor encontrado*

```sql
SELECT MAX(nota) AS maior*nota
FROM alunos;
```

Resultado e*perado: **9.5**

---

## MIN()

Re*orna o menor valor encontrado.

``*sql
SELECT MIN(nota) AS menor_nota*FROM alunos;
```

Resultado espera*o: **6.5**

---

## Utilizando Ali*s

Alias permite renomear colunas *xibidas no resultado.

```sql*SELECT AVG(nota)*AS media_da_turma
FROM alunos;
```*
Resultado esperado: **7.875**

--*

## GROUP BY

O comando `GROUP BY* agrupa registros.

Crie a tabela:*
```sql
CREATE TABLE matriculas (
*   id INTEGER PRIMARY KEY,
   *curso TEXT,
*   quantidade INTEGER
);
```

Insi*a os dados:

```sql
INSERT INTO ma*riculas (curso, quantidade)
VALUES*('ADS', 30);

INSERT INTO matricul*s (curso, quantidade)
VALUES ('ADS*, 25);

INSERT INTO matriculas (cu*so, quantidade)
VALUES ('Ciência d* Computação', 20);

INSERT INTO ma*riculas (curso, quantidade)
VALUES*('Ciência da Computação', 15);
```*
Consulta:

```*ql*SELECT curso,
       SUM(quantidad*) AS total_alunos
FROM matriculas
*ROUP BY curso;
```

Resultado espe*ado:

- ADS → 55
- Ciência da Comp*tação → 35

---

## HAVING

O coma*do `HAVING` filtra os grupos criad*s pelo `GROUP BY`.

```sql
SELECT *urso,
       SUM(quantidade) AS to*al_alunos
FROM matriculas
GROUP BY*curso
HAVING SUM(quantidade) > 40;*```

Resultado esperado:

- ADS → *5

---

## Relatório Completo

```*ql
SELECT
    COUNT(*) AS total_al*nos,
    AVG(nota) AS media_notas,*    MAX(nota) AS maior_nota,
    M*N(nota) AS menor_nota
FROM alunos;*```

Resultado esperado:

- Total *e alunos: 4
- Média das notas: 7.8*5
- Maior nota: 9.5
- Menor nota: *.5

---

*# Resumo

- `COUNT()` → Conta regi*tros
- `SUM*)` → Soma valores
- `AVG()` → Calc*la média
-*`*AX()` → Retorna o maior valor
- `M*N()` → Retorna o menor valor
- `GR*UP BY` → Agrupa registros
- `HAVIN*` → Filtra grupos

---

## Exercíc*os Práticos

1. Conte a quantidade*de alunos cadastrados.
2. Calcule * média das notas.
3. Descubra a ma*or nota.
4. Descubra a menor nota.*5. Calcule a soma das notas.
6. Mo*te um relatório utilizando todas a*
