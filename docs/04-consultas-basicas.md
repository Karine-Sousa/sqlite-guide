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

Para verificar quantos alunos estão cadastrados na tabela, utilize a função `COUNT()`.

### Exemplo

```sql
SELECT COUNT(*) AS total_alunos
FROM alunos;
```*
### Resultado Esperado

```text
t*tal_alunos
------------
2
```

* função `COUNT(*)` conta todas as linhas da tabela e retorna a quantidade total de registros.

---

## Resumo dos Comandos

| Comando | Função |
|----------|-------*--|
| SELECT | Consultar dados |
|*WHERE | Filtrar registros |
| ORDE* BY | Ordenar resultados |
| LIMIT*| Limitar resultados |
| UPDATE*| Atualizar registros |
| DELETE |*Excluir registros |
| DISTINCT | R*mover duplicidades |
| COUNT | Con*ar registros |

---

##*Exercício Proposto

1.*Liste todos os alunos cadastrados.*2. Exiba apenas os nomes dos aluno*.
3. Filtre os alunos do curso ADS*
4. Ordene os alunos por nome.
5. *tualize o curso de um aluno.
6. Ex*lua um registro.
7. Conte quantos *lunos existem cadastrados.

---

#* Próximos Passos

Continue para*

```text
05-funcoes-agregadas.md
*``

Neste*próximo capítulo serão apresentado*:

- COUNT()
- AVG()
- SUM*)
- MAX()
* MIN()

Ess*s funções são amplamente utilizada* em consultas analíticas e*geração de relatórios.
````*
