# Instalação do SQLite

## Objetivo

Instalar o SQLite e verificar se a ferramenta está funcionando corretamente no sistema operacional Windows.

---

## Passo 1: Baixar o SQLite

1. Acesse o site oficial do SQLite.
2. Procure pela seção **Precompiled Binaries for Windows**.
3. Faça o download do pacote **sqlite-tools-win-x64**.
4. Extraia os arquivos em uma pasta, por exemplo:

```text
C:\SQLite
```

---

## Passo 2: Adicionar o SQLite ao PATH

1. Abra o menu Iniciar.
2. Pesquise por **Variáveis de Ambiente**.
3. Clique em **Editar as variáveis de ambiente do sistema**.
4. Selecione **Variáveis de Ambiente**.
5. Em **Path**, clique em **Editar**.
6. Clique em **Novo**.
7. Adicione:

```text
C:\SQLite
```

8. Clique em **OK** para salvar.

---

## Passo 3: Verificar a Instalação

Abra o Prompt de Comando e execute:

```bash
sqlite3
```

Resultado esperado:

```text
SQLite version 3.x.x
Enter ".help" for usage hints.
Connected to a transient in-memory database.
Use ".open FILENAME" to reopen on a persistent database.
```

---

## Possíveis Erros

### Erro

```text
'sqlite3' não é reconhecido como um comando interno ou externo
```

### Causa

A pasta do SQLite não foi adicionada corretamente à variável PATH.

### Solução

- Verifique se o diretório foi incluído no PATH.
- Feche e abra novamente o Prompt de Comando.
- Execute novamente:

```bash
sqlite3
```

---

## Utilizando o SQLite no VS Code

### Instalar Extensão

1. Abra o VS Code.
2. Clique em **Extensions**.
3. Pesquise por:

```text
SQLite Viewer
```

ou

```text
SQLite
```

4. Instale a extensão desejada.

---

## Teste Final

Criar um banco de dados:

```bash
sqlite3 escola.db
```

Se o comando for executado sem erros, a instalação foi concluída com sucesso.

---

## Próximos Passos

Após a instalação, siga para:

- 03-primeiros-passos.md
- Criação de tabelas
- Inserção de registros
- Consultas SQL básicas
