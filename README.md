import hashlib


def criptografar(texto):
    resultado = ""
    i = 0
    texto = texto.upper()

    while i < len(texto):
        letra = texto[i]

        if "A" <= letra <= "Z":
            codigo = ord(letra)
            codigo = ((codigo - ord("A") + 3) % 26) + ord("A")
            letra = chr(codigo)

        resultado += letra
        i += 1

    return resultado


def descriptografar(texto):
    resultado = ""
    i = 0
    texto = texto.upper()

    while i < len(texto):
        letra = texto[i]

        if "A" <= letra <= "Z":
            codigo = ord(letra)
            codigo = ((codigo - ord("A") - 3) % 26) + ord("A")
            letra = chr(codigo)

        resultado += letra
        i += 1

    return resultado


def gerar_hash(texto):
    return hashlib.sha256(
        texto.encode("utf-8")
    ).hexdigest()


def menu():
    while True:
        print("\n===================================")
        print(" SISTEMA DE PROTEÇÃO DE INFORMAÇÕES")
        print("===================================")
        print("1 - Criptografar mensagem")
        print("2 - Descriptografar mensagem")
        print("3 - Gerar hash SHA-256")
        print("4 - Sair")
        print("===================================")

        opcao = input("Escolha uma opção: ").strip()

        if opcao == "1":
            mensagem = input("Digite a mensagem: ")
            print("Resultado:", criptografar(mensagem))

        elif opcao == "2":
            mensagem = input("Digite a mensagem criptografada: ")
            print("Resultado:", descriptografar(mensagem))

        elif opcao == "3":
            mensagem = input("Digite a mensagem para gerar o hash: ")
            print("Hash SHA-256:", gerar_hash(mensagem))

        elif opcao == "4":
            print("Programa encerrado!")
            break

        else:
            print("Opção inválida! Tente novamente.")


if __name__ == "__main__":
    menu()
3. Arquivo README.md
O README é a página inicial do projeto no GitHub. Crie esse arquivo e cole o texto abaixo.


markdown

# 🔐 Proteção de Informações com Python

Projeto educativo sobre proteção de informações utilizando Python,
Cifra de César, hash SHA-256 e estruturas de repetição `while`.

## 📌 Objetivo

Desenvolver um programa interativo que permita criptografar mensagens,
descriptografar mensagens e gerar hashes de textos.

## 🚀 Funcionalidades

- Criptografar mensagens usando a Cifra de César.
- Descriptografar mensagens com deslocamento de 3 posições.
- Gerar hash SHA-256.
- Menu interativo com repetição `while`.
- Validação de opções inválidas.

## 🛠️ Tecnologias utilizadas

- Python 3
- Biblioteca padrão `hashlib`
- Estruturas condicionais `if`, `elif` e `else`
- Estruturas de repetição `while`

## ▶️ Como executar

1. Instale o Python 3.
2. Baixe ou clone este repositório.
3. Abra o terminal na pasta do projeto.
4. Execute:

```bash
python main.py
```

Em alguns sistemas, utilize `python3 main.py`.

## 🧪 Exemplo

Mensagem original:

```text
ABC XYZ
```

Mensagem criptografada:

```text
DEF ABC
```

## 🔎 Conceitos aprendidos

- Laços de repetição.
- Manipulação de strings.
- Conversão de caracteres com `ord()` e `chr()`.
- Geração de hash com SHA-256.
- Organização de um projeto Python.

## ⚠️ Observação de segurança

A Cifra de César é apenas um exemplo didático e não oferece
segurança real. SHA-256 é uma função de hash, não uma criptografia
reversível. Para proteger dados reais, utilize bibliotecas
criptográficas apropriadas.

## 📚 Finalidade

Projeto desenvolvido para fins educacionais e prática de lógica
de programação em Python.
4. Arquivo .gitignore
Esse arquivo evita que arquivos temporários e configurações locais sejam enviados ao repositório.


text

__pycache__/
*.py[cod]
.venv/
venv/
.ipynb_checkpoints/
.DS_Store
