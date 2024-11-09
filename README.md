# Get Next Line (GNL)

## Objetivo
A função `get_next_line` tem como objetivo ler linhas de um arquivo, uma por vez, a partir de um file descriptor (fd). Ao chamar `get_next_line` repetidamente, o programa deve ler o arquivo ou entrada padrão de forma contínua, linha a linha. A função retorna a linha lida com o caractere de nova linha (`\n`) no final, se houver, ou `NULL` caso não haja mais nada para ler ou ocorra algum erro.

### Características Principais
- **Parâmetros:** A função recebe um `fd` como argumento.
- **Retorno:** Retorna a linha lida do arquivo. Caso o arquivo termine ou ocorra um erro, a função retorna `NULL`.
- **Funções Externas Permitidas:** `read`, `malloc`, `free`.
- **Arquivo de Cabeçalho:** `get_next_line.h` contendo o protótipo da função.
- **Funções Auxiliares:** Devem estar no arquivo `get_next_line_utils.c`.

### Requisitos e Restrições
1. **Leitura Incremental:** `get_next_line` deve ser chamada repetidamente para ler o arquivo linha a linha, sem carregar o arquivo completo na memória de uma só vez.
2. **Variáveis Globais Proibidas:** A função não pode utilizar variáveis globais.
3. **Compilação com BUFFER_SIZE:** O tamanho do buffer de leitura deve ser definido por uma flag (`-D BUFFER_SIZE=n`) ao compilar, o que permite flexibilidade na leitura.
4. **Comportamento com Arquivo Binário:** A função pode ter comportamento indefinido ao ler arquivos binários.

## Exemplo de Compilação
A função deve ser compilada com um valor de `BUFFER_SIZE` definido, por exemplo:
```bash
cc -Wall -Wextra -Werror -D BUFFER_SIZE=42 <files>.c
# get_next_line
```
## Desafios Adicionais (Bônus)

A parte bônus requer que `get_next_line`:

* Utilize apenas uma única variável estática.
* Suporte múltiplos file descriptors simultaneamente, mantendo a continuidade de leitura para cada um de forma independente.

### Arquivos do Bônus

A implementação bônus deve estar nos arquivos:

* `get_next_line_bonus.c`
* `get_next_line_bonus.h`
* `get_next_line_utils_bonus.c`


