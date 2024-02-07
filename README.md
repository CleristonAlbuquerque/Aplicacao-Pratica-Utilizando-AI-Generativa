# Aplicaçãoo Prática Utilizando AI Generativa
Esta é uma aplicação Prática utilizando AI Generativa do Microsoft Azure do bootcamp da Microsoft Azure AI Fundamentals da DIO.

## Introdução
Este repositório contém o passo a passo de como aplicar o AI Generativa na prática.

## Limitações
A utilização do Microsoft Azure AI Generativa é bloqueada para contas pessoais, o acesso é apenas para contas corporativas, conforme descrito na documentação, link da documentação: https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/13-azure-openai.html

## Documentações
As principais documentações
https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/12-generative-ai.html
https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/13-azure-openai.html
https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/14-azure-openai-content-filters.html

## Sobre o projeto prático
Devido as limitações de acesso no Microsoft AI Generativa da OpenAI, a prática ocorrerá no Microsoft Copilot, neste projeto prático, solicito a sugestão de código em Python do jogo da velha.

## Passo a passo

1. No prompt do Copilot, o seguinte comando
![image](https://github.com/CleristonAlbuquerque/Aplicacao-Pratica-Utilizando-AI-Generativa/assets/64879348/92900bf6-a626-4013-836f-09e6515e22d2)

2. O Copilot apresentará a solução
![image](https://github.com/CleristonAlbuquerque/Aplicacao-Pratica-Utilizando-AI-Generativa/assets/64879348/44a6f2e0-a925-4ed1-be86-df963bfe4ab4)

## Solução apresentada pelo Copilot

def exibir_tabuleiro(tabuleiro):
    for linha in tabuleiro:
        print(" ".join(linha))

def verificar_vitoria(tabuleiro, jogador):
    for linha in tabuleiro:
        if all(casa == jogador for casa in linha):
            return True

    for coluna in range(3):
        if all(tabuleiro[linha][coluna] == jogador for linha in range(3)):
            return True

    if tabuleiro[0][0] == tabuleiro[1][1] == tabuleiro[2][2] == jogador:
        return True

    if tabuleiro[0][2] == tabuleiro[1][1] == tabuleiro[2][0] == jogador:
        return True

    return False

def jogar_jogo_da_velha():
    tabuleiro = [[" " for _ in range(3)] for _ in range(3)]
    jogador_atual = "X"

    while True:
        exibir_tabuleiro(tabuleiro)
        linha, coluna = map(int, input(f"Jogador {jogador_atual}, escolha a linha e coluna (0 a 2): ").split())

        if tabuleiro[linha][coluna] != " ":
            print("Essa posição já está ocupada. Tente novamente.")
            continue

        tabuleiro[linha][coluna] = jogador_atual

        if verificar_vitoria(tabuleiro, jogador_atual):
            exibir_tabuleiro(tabuleiro)
            print(f"Jogador {jogador_atual} venceu!")
            break

        jogador_atual = "O" if jogador_atual == "X" else "X"

if __name__ == "__main__":
    jogar_jogo_da_velha()


