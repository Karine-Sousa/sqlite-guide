# Consultas Básicas em SQLite

## Objetivo

Aprender a consultar, filtrar, ordenar, atualizar e excluir dados em uma tabela utilizando os principais comandos SQL.

---

## Pré-requisitos

Antes de iniciar, certifique-se de que:

- O SQLite está instalado.
- O banco de dados foi criado.
- A tabela `alunos` já existe.
- Há registros cadastrados na tabela.

Exemplo de registros:

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

Para visualizar todos os dados da tabela:

```sql
SELECT * FROM alunos;
```

### Resultado Esperado

```text
id | nome         | curso
-----------------------------------
1  | Maria Silva  | ADS
2  | João Santos  | Ciência da Computação
3  | Ana Souza    | ADS
```

---

## Consultando Colunas Específicas

Para exibir apenas determinadas informações:

```sql
SELECT nome, curso
FROM alunos;
```

### Resultado Esperado

```text
nome         | curso
-------------------------
Maria Silva  | ADS
João Santos  | Ciência da Computação
Ana Souza    | ADS
```

---

## Filtrando Registros com WHERE

Para localizar apenas alunos de um curso específico:

```sql
SELECT *
FROM alunos
WHERE curso = 'ADS';
```

### Resultado Esperado

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

Para exibir apenas os dois primeiros registros:

```sql
SELECT *
FROM alunos
LIMIT 2;
```

### Resultado Esperado

```text
1 | Maria Silva | ADS
2 | João Santos | Ciência da Computação
```

---

## Atualizando Dados

Para alterar informações já cadastradas:

```sql
UPDATE alunos
SET curso = 'Sistemas para Internet'
WHERE id = 1;
```

Para verificar a alteração:

```sql
SELECT * FROM alunos;
```

### Resultado Esperado

```text
1 | Maria Silva | Sistemas para Internet
2 | João Santos | Ciência da Computação
3 | Ana Souza   | ADS
```

---

## Excluindo Registros

Para remover um registro da tabela:

```sql
DELETE FROM alunos
WHERE id = 3;
```

Para confirmar a exclusão:

```sql
SELECT * FROM alunos;
```

### Resultado Esperado

```text
1 | Maria Silva | Sistemas para Internet
2 | João Santos | Ciência da Computação
```

---

## Consultando Valores Únicos

Para listar apenas valores sem repetição:

```sql
SELECT DISTINCT curso
FROM alunos;
```

### Resultado Esperado

```text
Sistemas para Internet
Ciência da Computação
ADS
```

---

## Contando Registros

Para verificar quantos registros existem na tabela:

```sql
SELECT COUNT(*) AS total_alunos
FROM alunos;
```

### Resultado Esperado

```text
total_alunos
------------
3
```

A função `COUNT(*)` retorna a quantidade total de registros da tabela.

---

## Resumo dos Comandos

| Comando | Finalidade |
|----------|------------|
| SELECT | Consultar dados |
| WHERE | Filtrar registros |
| ORDER BY | Ordenar resultados |
| LIMIT | Limitar a quantidade de resultados |
| UPDATE | Atualizar registros |
| DELETE | Excluir registros |
| DISTINCT | Remover duplicidades |
| COUNT | Contar registros |

---

## Exercícios Práticos

1. Liste todos os alunos cadastrados.
2. Exiba apenas os nomes dos alunos.
3. Filtre apenas os alunos do curso ADS.
4. Ordene os alunos em ordem alfabética.
5. Atualize o curso de um aluno.
6. Exclua um registro.
7. Conte quantos alunos estão cadastrados.

---

## Boas Práticas

- Sempre utilize o comando `WHERE` ao executar `UPDATE` ou `DELETE`.
- Verifique os dados antes de alterar ou excluir registros.
- Utilize nomes de tabelas e colunas claros e padronizados.
- Teste suas consultas em ambientes de estudo antes de executá-las em produção.

---

## Próximos Passos

Continue para o arquivo:

```text
05-funcoes-agregadas.md
```

No próximo capítulo serão apresentadas as funções:

- COUNT()
- SUM()
- AVG()
- MAX()
- MIN()

Essas funções são essenciais para geração de relatórios e análise de dados.
