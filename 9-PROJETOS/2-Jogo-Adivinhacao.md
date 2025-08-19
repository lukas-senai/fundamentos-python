# 🎯 Projeto: Jogo da Adivinhação Simples

## 🎮 Objetivo do Projeto

Criar um jogo onde o computador pensa em um número e você tenta adivinhar! Vamos começar com uma versão simples e depois melhorar.

## 🎯 Funcionalidades

✅ Computador escolhe número aleatório
✅ Jogador faz palpites
✅ Dicas de "maior" ou "menor"
✅ Contador de tentativas

## 🛠️ Versão Básica (Para Iniciantes)

```python
import random

# O computador escolhe um número
numero_secreto = random.randint(1, 100)
tentativas = 0

print("🎯 JOGO DA ADIVINHAÇÃO")
print("Pensei em um número entre 1 e 100!")
print("Tente adivinhar qual é!")

# Loop do jogo
while True:
    # Pedir palpite do jogador
    palpite = int(input("\nQual é o seu palpite? "))
    tentativas += 1
    
    # Verificar se acertou
    if palpite == numero_secreto:
        print(f"🎉 PARABÉNS! Você acertou!")
        print(f"O número era {numero_secreto}")
        print(f"Você usou {tentativas} tentativas")
        break
    
    # Dar dicas
    elif palpite < numero_secreto:
        print("📈 O número é MAIOR!")
    else:
        print("📉 O número é MENOR!")
```

## 🔧 Versão Melhorada

Agora vamos adicionar algumas melhorias:

```python
import random

def jogar_adivinhacao():
    # Configurações do jogo
    numero_secreto = random.randint(1, 100)
    tentativas = 0
    max_tentativas = 7
    
    print("🎯 JOGO DA ADIVINHAÇÃO")
    print("Pensei em um número entre 1 e 100!")
    print(f"Você tem {max_tentativas} tentativas!")
    print("-" * 40)
    
    # Loop do jogo
    while tentativas < max_tentativas:
        tentativas_restantes = max_tentativas - tentativas
        print(f"\nTentativas restantes: {tentativas_restantes}")
        
        try:
            palpite = int(input("Qual é o seu palpite? "))
            
            # Verificar se está no intervalo
            if palpite < 1 or palpite > 100:
                print("❌ Digite um número entre 1 e 100!")
                continue
            
            tentativas += 1
            
            # Verificar se acertou
            if palpite == numero_secreto:
                print(f"\n🎉 PARABÉNS! Você acertou!")
                print(f"O número era {numero_secreto}")
                print(f"Você usou {tentativas} tentativas")
                return
            
            # Dar dicas
            elif palpite < numero_secreto:
                print("📈 O número é MAIOR!")
            else:
                print("📉 O número é MENOR!")
                
            # Dica de proximidade
            diferenca = abs(palpite - numero_secreto)
            if diferenca <= 5:
                print("🔥 Você está muito perto!")
            elif diferenca <= 15:
                print("♨️ Está esquentando!")
            
        except ValueError:
            print("❌ Por favor, digite um número válido!")
    
    # Se chegou aqui, perdeu
    print(f"\n💔 Suas tentativas acabaram!")
    print(f"O número era: {numero_secreto}")
    print("🎮 Tente novamente!")

# Perguntar se quer jogar novamente
while True:
    jogar_adivinhacao()
    
    jogar_novamente = input("\nQuer jogar novamente? (s/n): ")
    if jogar_novamente.lower() != 's':
        print("👋 Obrigado por jogar!")
        break
```

## 🎯 Como Funciona

### 1. **Gerando Número Aleatório**
```python
numero_secreto = random.randint(1, 100)
```
- `random.randint(1, 100)` escolhe um número entre 1 e 100

### 2. **Loop Principal**
```python
while tentativas < max_tentativas:
    # Código do jogo aqui
```
- Continua até acabar as tentativas ou acertar

### 3. **Comparações**
```python
if palpite == numero_secreto:
    # Acertou!
elif palpite < numero_secreto:
    # Número é maior
else:
    # Número é menor
```

## 🏋️ Exercícios para Praticar

1. **Fácil**: Mude o intervalo para 1-50
2. **Médio**: Adicione diferentes níveis de dificuldade
3. **Difícil**: Conte quantos jogos o jogador ganhou

## 💡 O que Aprendemos

✅ Usar `random.randint()` para números aleatórios
✅ Loops `while` para repetir o jogo
✅ Condicionais `if/elif/else` para comparações
✅ Tratamento de erros com `try/except`
✅ Funções para organizar o código

## ➡️ Próximo Projeto
Agora vamos criar uma [Lista de Tarefas](3-Lista-Tarefas.md) para organizar nosso dia!
