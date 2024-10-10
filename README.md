## 🔒 Projeto de Criptografia XOR em C

Este projeto implementa uma criptografia usando o operador XOR (^) em C, onde uma mensagem de texto é criptografada e, posteriormente, pode ser descriptografada com a mesma chave.

## 📜 Descrição

O algoritmo usa o operador XOR para embaralhar cada caractere da mensagem original com base em uma chave repetida ao longo da mensagem. A chave usada neste exemplo é a palavra "CRIPTOGRAFIA" com um tamanho fixo de 12 caracteres.

## 🚀 Funcionalidades

Criptografia de mensagens utilizando XOR com uma chave de 12 caracteres.
Descriptografia de mensagens criptografadas para recuperar o texto original.
Verificação do tamanho da mensagem (máximo de 60 caracteres).
Exibe a mensagem criptografada como valores numéricos e descriptografada como texto legível.

## 💻 Execução

Estrutura do Código

```bash
#include <stdio.h>
#define MAX 200

void criptografar(char *mensagemOrig, char *mensagemCripto, char *chave)
{
    int i, tamanhoChave = 12, tamanhoMensagem = 0;

    for (i = 0; mensagemOrig[tamanhoMensagem] != '\0'; i++)
    {
        tamanhoMensagem++;
    }
    for (i = 0; i < tamanhoMensagem; i++)
    {
        mensagemCripto[i] = mensagemOrig[i] ^ chave[i % tamanhoChave];
        printf("%d ", mensagemCripto[i]);
    }
    mensagemCripto[tamanhoMensagem] = '\0';
}

void descriptografar(char *mensagemCripto, char *resultado, char *chave)
{
    int i, tamanhoChave = 12, tamanhoMensagem = 0;

    for (i = 0; resultado[tamanhoMensagem] != '\0'; i++)
    {
        tamanhoMensagem++;
    }
    for (i = 0; i < tamanhoMensagem; i++)
    {
        resultado[i] = mensagemCripto[i] ^ chave[i % tamanhoChave];
        printf("%c", resultado[i]);
    }
}

int main()
{
    char chave[] = "CRIPTOGRAFIA";
    char mensagemOrig[MAX], mensagemCripto[MAX], resultado[MAX];
    int tamanhoMensagem = 0;

    scanf("%[^\n]", mensagemOrig);

    for (int i = 0; mensagemOrig[tamanhoMensagem] != '\0'; i++)
    {
        tamanhoMensagem++;
    }

    int i;
    for (i = 0; i < tamanhoMensagem; i++)
    {
        resultado[i] = 'a';
    }
    resultado[i] = '\0';

    if (tamanhoMensagem < 61)
    {
        printf("Mensagem Cifrada: ");
        criptografar(mensagemOrig, mensagemCripto, chave);

        printf("\nMensagem Original: ");
        descriptografar(mensagemCripto, resultado, chave);
    }
    else
    {
        printf("ERRO - A mensagem deve possuir tamanho máximo de 60 caracteres.");
    }

    printf("\n");
    return 0;
}
```

## 📝 Como Usar

# 1. Entrada

Digite caracteres para ser criptografada. A mensagem será cifrada usando a chave "CRIPTOGRAFIA".

# 2. Criptografia

O programa irá exibir a mensagem criptografada usando o operador XOR.

# 3. Descriptografia

Após a criptografia, o programa também descriptografará a mensagem, exibindo a versão original.

# 4. Verificação

O programa inclui uma verificação para garantir que a mensagem tenha no máximo 60 caracteres.

## 🛠️ Como Compilar e Executar

# Compilação

IDE:

- Pode-se optar em compilar dentro de uma IDE, desde que obtenha as extensões necessárias.

Terminal:

- Para compilar o código, use um compilador de C, como o GCC. No terminal, execute o seguinte comando:

```bash
gcc criptografia.c -o criptografia
```

# Execução
Após a compilação, execute o programa com o seguinte comando:

```bash
./criptografia
```

Em seguida, insira a mensagem que deseja criptografar.

## ⚠️ Limitações

- O programa suporta apenas mensagens de até 60 caracteres.
- O algoritmo usa uma chave fixa de 12 caracteres, "CRIPTOGRAFIA", o que torna a segurança limitada para uso em sistemas complexos.

## 📄 Licença

Este projeto está licenciado sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.




