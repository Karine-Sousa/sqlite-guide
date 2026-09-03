# Consultas Básicas em SQLite

## Objetivo

Aprender a consultar, filtrar, atualizar e excluir dados armazenados em tabelas utilizando comandos SQL básicos.

---

## Pré-requisitos

Antes de iniciar, você deve ter:

- SQLite instalado
- Banco de dados criado
- Tabela `alunos` criada
- Alguns registros cadastrados

Exemplo:

```sql
INSERT INTO alunos (nome, curso)
VALUES ('Maria Silva', 'ADS');

INSERT INTO alunos (nome, curso)
VALUES ('João Santos', 'Ciência da Computação');

INSERT INTO alunos (nome, curso)
VALUES ('Ana Souza', 'ADS');
```

---

## Consultando Todos os Registros

Para visualizar todos os registros da tabela:

```sql
SELECT * FROM alunos;
```

Resultado:

```text
id | nome         | curso
-----------------------------------
1  | Maria Silva  | ADS
2  | João Santos  | Ciência da Computação
3  | Ana Souza    | ADS
```

---

## Consultando Colunas Específicas

Para exibir apenas determinadas colunas:

```sql
SELECT nome, curso
FROM alunos;
```

Resultado:

```text
nome         | curso
-------------------------
Maria Silva  | ADS
João Santos  | Ciência da Computação
Ana Souza    | ADS
```

---

## Filtrando Registros com WHERE

Para localizar alunos de um curso específico:

```sql
SELECT *
FROM alunos
WHERE curso = 'ADS';
```

Resultado:

```text
1 | Maria Silva | ADS
3 | Ana Souza   | ADS
```

---

## Ordenando Registros

### Ordem Crescente

```sql
SELECT *
FROM alunos
ORDER BY nome ASC;
```

### Ordem Decrescente

```sql
SELECT *
FROM alunos
ORDER BY nome DESC;
```

---

## Limitando a Quantidade de Resultados

Exibir apenas os dois primeiros registros:

```sql
SELECT *
FROM alunos
LIMIT 2;
```

Resultado:

```text
1 | Maria Silva | ADS
2 | João Santos | Ciência da Computação
```

---

## Atualizando Dados

Alterar o curso de um aluno:

```sql
UPDATE alunos
SET curso = 'Sistemas para Internet'
WHERE id = 1;
```

Verificar atualização:

```sql
SELECT * FROM alunos;
```

Resultado:

```text
1 | Maria Silva | Sistemas para Internet
```

---

## Excluindo Registros

Excluir um aluno:

```sql
DELETE FROM alunos
WHERE id = 3;
```

Consultar novamente:

```sql
SELECT * FROM alunos;
```

Resultado:

```text
1 | Maria Silva | Sistemas para Internet
2 | João Santos | Ciência da Computação
```

---

## Consultando Valores Únicos

Exibir apenas cursos sem repetição:

```sql
SELECT DISTINCT curso
FROM alunos;
```

Resultado:

```text
ADS
Ciência da Computação
Sistemas para Internet
```

---

## Contando Registros

Verificar quantos alunos existem na tabela:

```sql
SELECT COUNT(*)
FROM alunos;
```

Resultado:

```text
2*```

---

## Resumo dos Comandos

* Comando | Função |
|----------|--*-------|
| SELECT | Consultar dado* |
| WHERE | Filtrar registros |
|*ORDER BY | Ordenar resultados |
| *IMIT | Limitar resultados |
| UPDA*E | Atualizar registros |
| DELETE*| Excluir registros |
| DISTINCT |*Remover duplicidades |
| COUNT | C*ntar registros |

---

## Exercíci* Proposto

Realize as seguintes co*sultas:

1. Liste todos os alunos.*2. Exiba apenas os nomes dos aluno*.
3. Filtre alunos do curso ADS.
4* Ordene os alunos por nome.
5. Atu*lize o curso de um aluno.
6. Exclu* um registro.
7. Conte quantos alu*os existem cadastrados.

---

## P*óximos Passos

Continue para:

```*ext
05-funcoes-agregadas.md
```

N*le serão apresentados:

- COUNT()
* AVG()
- SUM()
- MAX()
- MIN()

Es*as funções são amplamente utilizad*s em relatórios e análises de dado*.
