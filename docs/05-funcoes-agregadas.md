# Funções Agregadas em SQLite

## Objetivo

Aprender a utilizar funções agregadas para realizar cálculos e análises sobre os dados armazenados em tabelas.

As funções agregadas são utilizadas para resumir informações e gerar relatórios.

---

## Pré-requisitos

Antes de iniciar, certifique-se de que a tabela `alunos` está criada e possui registros.

Exemplo:

```sql
CREATE TABLE alunos (
    id INTEGER PRIMARY KEY,
    nome TEXT NOT NULL,
    idade INTEGER,
    nota REAL
);
```

Inserindo alguns dados:

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

## Função COUNT()

A função `COUNT()` retorna a quantidade de registros.

### Exemplo

```sql
SELECT COUNT(*) AS total_alunos
FROM alun*s;
```

### Resultado Esperado

``*text
total_alunos
------------
4
`*`

---

## Função SUM()

A função *SUM()` realiza a soma dos valores *e uma coluna numérica.

### Exempl*

```sql
SELECT SUM(nota) AS soma_*otas
FROM alunos;
```

### Resulta*o Esperado

```text
soma_notas
---*------
31.5
```

---

## Função AV*()

A função `AVG()` calcula a méd*a dos valores.

### Exemplo

```sq*
SELECT AVG(nota) AS media_notas
F*OM alunos;
```

### Resultado Espe*ado

```text
media_notas
---------*-
7.875
```

---

## Função MAX()
*A função*`MAX()` retorna o maior valor enco*trado na coluna.

### Exemplo

```*ql
SELECT MAX(nota) AS maior_nota
*ROM alunos;
```

### Resultado Esp*rado

```text
maior_nota
---------*
9.5
```

---

## Função MIN()

A *unção `MIN()` retorna o menor valo* encontrado.

### Exemplo

```*ql
SELECT MIN(nota) AS menor_nota
*ROM alunos;
*``

### Resultado Esperado

```tex*
menor_nota
----------
6.5
```

*--

## Utilizando Alias

Alias per*ite*renomear colunas no resultado da c*nsulta.

### Exemplo

```sql
*ELECT AVG(nota) AS media_da_turma
*ROM alunos;
```

### Resultado Esp*rado

```text*media_da_turma
--------------
7.87*
```

---

## Agrupando Dados com *ROUP BY

O comando `GROUP BY`*é utilizado para agrupar registros*

Crie uma tabela para o exemplo:
*```sql
CREATE TABLE matric*las (
    id INTEGER PRIMARY KEY,
*   curso TEXT,
    quantidade INTE*ER
);
```

Inserindo dados:

```sq*
INSERT INTO matriculas (curso, qu*ntidade)
VALUES ('ADS', 30);

INSE*T INTO matriculas (curso, quantida*e)
VALUES ('ADS', 25);

INSERT INT* matriculas (curso, quantidade)
VA*UES ('Ciência da Computação', 20);*
INSERT INTO matriculas (curso, qu*ntidade)
VALUES ('Ciência da Compu*ação', 15);
```

### Exemplo

```s*l
SELECT curso,
       SUM(quantid*de) AS total_alunos
FROM matricula*
GROUP BY curso;
```

### Resultad* Esperado

```text*ADS                     55
Ciência*da Computação   35
```

*--

## Filtrando Grupos com HAVING*
O comando*`HAVING` permite aplicar filtros a*ós o agrupamento.

### Exemplo

``*sql
SELECT curso,
       SUM(quant*dade) AS total_alunos
FROM matricu*as
GROUP BY curso
HAVING total_alu*os > 40;
```

### Resultado Espera*o

```text
ADS   *55
```

*--

## Exemplo de*Relatório

Calcular:

- Quant*dade de alunos
- Média das notas
-*Maior nota
- Menor nota

```sql
SE*ECT
    COUNT**) AS total_alunos,
    AVG(nota) *S media,
    MAX(nota) AS maior_no*a,
    MIN(nota) AS menor_nota*FROM alunos;
```

### Resultado Es*erado

```text
total_alunos | medi* | maior_nota | menor_nota
-------*----------------------------------*-----
4            | 7.875 | 9.5*       | 6.5
```

*--

## Resumo das Funções

| Funçã* | Finalidade |
|----------|------*-----|
| COUNT() | Conta registros*|
| SUM() | Soma valores |
| AVG()*| Calcula média |
| MAX*) | Retorna o maior valor |
| MIN(* | Retorna o menor valor |

---

#* Exercícios Práticos

1.*Conte a*quantidade de alunos cadastrados.
*. Calcule a média das notas.
3. Ex*ba a maior nota da turma.
4. Exiba*a menor nota da turma.
5.*Calcule a soma de todas as notas.
*. Crie um relatório contendo todas*as funções agregadas.

---

## Boa* Práticas

- Utilize aliases para *acilitar a leitura dos resultados.*- Nomeie as colunas de forma clara*
- Combine funções agregadas com f*ltros quando necessário.
- Utilize*`GROUP BY` para análises mais deta*hadas.

---

## Próximos Passos

C*ntinue para:

```text
06-relaciona*entos.md
```

No próximo capítulo *erão apresentados:

- Chave Primár*a
- Chave Estrangeira
- Integridad* Referencial
- Relacionamentos ent*e Tabelas
- Modelagem Relacional
`*
