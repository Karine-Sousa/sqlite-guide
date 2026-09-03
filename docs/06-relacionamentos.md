# Relacionamentos em SQLite

## Objetivo

Compreender como relacionar tabelas em um banco de dados utilizando chaves primárias e chaves estrangeiras.

Os relacionamentos permitem organizar os dados de forma estruturada, evitando duplicações e facilitando a manutenção das informações.

---

## Conceitos Fundamentais

### Chave Primária (Primary Key)

A chave primária identifica de forma única cada registro de uma tabela.

Exemplo:

```sql
CREATE TABLE cursos (
    id INTEGER PRIMARY KEY,
    nome TEXT NOT NULL
);
```

Neste exemplo, a coluna `id` identifica cada curso de forma única.

---

### Chave Estrangeira (Foreign Key)

A chave estrangeira cria um vínculo entre duas tabelas.

Ela aponta para a chave primária de outra tabela.

Exemplo:

```sql
FOREIGN KEY (id_curso)
REFERENCES cursos(id)
```

---

## Cenário de Exemplo

Uma escola possui:

- Cursos
- Alunos

Cada aluno pertence a um curso.

Nesse caso:

- Um curso pode possuir vários alunos.
- Um aluno pertence a apenas um curso.

---

## Criando a Tabela de Cursos

```sql
CREATE TABLE cursos (
    id INTEGER PRIMARY KEY,
    nome TEXT NOT NULL
);
```

Inserindo dados:

```sql
INSERT INTO cursos (nome)
VALUES ('ADS');

INSERT INTO cursos (nome)
VALUES ('Ciência da Computação');

INSERT INTO cursos (nome)
VALUES ('Sistemas para Internet');
```

---

## Criando a Tabela de Alunos

```sql
CREATE TABLE alunos (
    id INTEGER PRIMARY KEY,
    nome TEXT NOT NULL,
    id_curso INTEGER,
    FOREIGN KEY (id_curso)
        REFERENCES cursos(id)
);
```

Observe que a coluna `id_curso` é uma chave estrangeira.

---

## Inserindo Alunos

```sql
INSERT INTO alunos (nome, id_curso)
VALUES ('Maria Silva', 1);

INSERT INTO alunos (nome, id_curso)
VALUES ('João Santos', 2);

INSERT INTO alunos (nome, id_curso)
VALUES ('Ana Souza', 1);
```

---

## Consultando as Tabelas

Tabela cursos:

```sql
SELECT * FROM cursos;
```

Resultado esperado:

```text
1 | ADS
2 | Ciência da Computação
3 | Sistemas para Internet
```

Tabela alunos:

```sql
SELECT * FROM alunos;
```

Resultado esperado:

```text
1 | Maria Silva | 1
2 | João Santos | 2
3 | Ana Souza   | 1
```

---

## Utilizando JOIN

O comando JOIN permite combinar informações de tabelas relacionadas.

### Exemplo

```sql
SELECT
    alunos.nome,
    cursos.nome AS curso
FROM alunos
INNER JOIN cursos
ON alunos.id_curso = cursos.id;
```

Resultado esperado:

```text
Maria Silva | ADS
João Santos | Ciência da Computação
Ana Souza   | ADS
```

---

## Entendendo o INNER JOIN

O INNER JOIN retorna apenas os registros que possuem correspondência nas duas tabelas.

Neste caso:

- O aluno possui um curso.
- O curso existe na tabela cursos.

Somente esses registros são retornados.

---

## Relacionamento Um para Muitos

O exemplo anterior representa um relacionamento do tipo:

### Um Curso → Muitos Alunos

Exemplo:

```text
ADS
 ├─ Maria Silva
 ├─ Ana Souza
 └─ Carlos Lima
```

Um curso pode possuir vários alunos.

Um aluno pertence a apenas um curso.

---

## Integridade Referencial

A integridade referencial garante que os relacionamentos permaneçam válidos.

Exemplo:

Não é possível associar um aluno a um curso inexistente.

Valor inválido:

```sql
INSERT INTO alunos (nome, id_curso)
VALUES ('Pedro', 99);
```

O curso 99 não existe.

---

## Benefícios dos Relacionamentos

- Evitam duplicação de dados.
- Melhoram a organização das informações.
- Facilitam consultas complexas.
- Aumentam a consistência dos dados.
- Tornam o banco mais escalável.

---

## Resumo

Conceitos aprendidos:

- Chave Primária (Primary Key)
- Chave Estrangeira (Foreign Key)
- Relacionamento Um para Muitos
- Integridade Referencial
- INNER JOIN

---

## Exercícios Práticos

1. Crie a tabela `professores`.
2. Cadastre três professores.
3. Crie uma relação entre professores e cursos.
4. Realize consultas utilizando JOIN.
5. Liste todos os alunos e seus respectivos cursos.
6. Cadastre um novo curso e associe alunos a ele.

---

## Boas Práticas

- Utilize chaves primárias em todas as tabelas.
- Nomeie as colunas de forma padronizada.
- Crie relacionamentos apenas quando houver necessidade.
- Utilize JOIN para recuperar dados relacionados.
- Evite armazenar informações repetidas.

---

## Próximo Capítulo

Arquivo:

```text
07-boas-praticas.md
```

Temas abordados:

- Padronização de nomes
- Organização de tabelas
- Segurança dos dados
- Backup
- Performance
- Documentação de banco de dados
