# ⏰ Loop While: Repetindo Enquanto...

## O que é um Loop While?

Imagine que você está enchendo uma banheira. Você não sabe exatamente quantos baldes de água vai precisar, mas sabe que deve continuar **ENQUANTO** a banheira não estiver cheia.

O `while` é exatamente isso: **"ENQUANTO esta condição for verdadeira, continue fazendo isso"**

## 🎯 Diferença entre For e While

### 🔢 For: "Faça X vezes"
```python
# Eu SEI que quero repetir 5 vezes
for i in range(5):
    print("Repetição", i)
```

### ⏳ While: "Faça ENQUANTO..."
```python
# Eu NÃO SEI quantas vezes, mas sei a condição para parar
contador = 0
while contador < 5:
    print("Repetição", contador)
    contador += 1  # MUITO IMPORTANTE!
```

## 🌟 Estrutura Básica

```python
# Estrutura do while
while condição:
    # código a ser repetido
    # SEMPRE modifique a variável da condição!
```

## 🎮 Exemplo Detalhado: Jogo de Adivinhação

```python
import random

print("🎯 JOGO DE ADIVINHAÇÃO")
print("Tente adivinhar o número de 1 a 10!")

numero_secreto = random.randint(1, 10)
tentativas = 0
acertou = False

while not acertou:  # Enquanto NÃO acertou
    tentativas += 1
    print(f"\n--- Tentativa {tentativas} ---")
    
    palpite = int(input("Seu palpite: "))
    
    if palpite == numero_secreto:
        print(f"🎉 PARABÉNS! Você acertou em {tentativas} tentativas!")
        acertou = True  # Isso faz o loop parar
    elif palpite < numero_secreto:
        print("📈 Muito baixo! Tente um número maior")
    else:
        print("📉 Muito alto! Tente um número menor")

print("Obrigado por jogar!")
```

**Como funciona:**
1. **Condição:** `not acertou` (enquanto não acertou)
2. **A cada volta:** pede um palpite e verifica
3. **Para quando:** `acertou = True`

## 💰 Exemplo Prático: Caixa Eletrônico

```python
print("🏧 CAIXA ELETRÔNICO")
print("=" * 20)

saldo = 1000.00
continuar = True

while continuar:
    print(f"\nSaldo atual: R$ {saldo:.2f}")
    print("\nOpções:")
    print("1 - Sacar")
    print("2 - Depositar") 
    print("3 - Sair")
    
    opcao = input("Escolha uma opção: ")
    
    if opcao == "1":  # Saque
        valor = float(input("Valor para saque: R$ "))
        if valor <= saldo:
            saldo -= valor
            print(f"✅ Saque realizado! Retire R$ {valor:.2f}")
        else:
            print("❌ Saldo insuficiente!")
            
    elif opcao == "2":  # Depósito
        valor = float(input("Valor para depósito: R$ "))
        saldo += valor
        print(f"✅ Depósito realizado! R$ {valor:.2f} adicionados")
        
    elif opcao == "3":  # Sair
        print("👋 Obrigado por usar nosso caixa eletrônico!")
        continuar = False  # Isso para o loop
        
    else:
        print("❌ Opção inválida!")

print("Sistema encerrado.")
```

## ⚠️ CUIDADO: Loop Infinito!

O maior perigo do `while` é criar um **loop infinito**:

```python
# ❌ NUNCA FAÇA ISSO!
contador = 0
while contador < 5:
    print("Isso nunca vai parar!")
    # Esqueci de incrementar o contador!
    # contador += 1  ← Isso deveria estar aqui!
```

**Como evitar:**
1. **Sempre** modifique a variável da condição
2. Teste com valores pequenos primeiro
3. Use `Ctrl+C` para parar se necessário

## 🔄 Padrões Comuns do While

### 1. Contador
```python
contador = 1
while contador <= 10:
    print(f"Contando: {contador}")
    contador += 1
```

### 2. Acumulador
```python
soma = 0
numero = 1

while numero <= 100:
    soma += numero
    numero += 1

print(f"Soma de 1 a 100: {soma}")
```

### 3. Validação de Entrada
```python
idade = -1  # Valor inválido para começar

while idade < 0 or idade > 120:
    idade = int(input("Digite sua idade (0-120): "))
    if idade < 0 or idade > 120:
        print("❌ Idade inválida! Tente novamente.")

print(f"✅ Idade válida: {idade} anos")
```

## 🎯 Exemplo Avançado: Sistema de Login

```python
print("🔐 SISTEMA DE LOGIN")
print("=" * 20)

usuario_correto = "admin"
senha_correta = "python123"
tentativas_maximas = 3
tentativas = 0
logado = False

while tentativas < tentativas_maximas and not logado:
    print(f"\nTentativa {tentativas + 1} de {tentativas_maximas}")
    
    usuario = input("Usuário: ")
    senha = input("Senha: ")
    
    if usuario == usuario_correto and senha == senha_correta:
        print("✅ Login realizado com sucesso!")
        print("🎉 Bem-vindo ao sistema!")
        logado = True
    else:
        tentativas += 1
        if tentativas < tentativas_maximas:
            print("❌ Usuário ou senha incorretos!")
            print(f"Restam {tentativas_maximas - tentativas} tentativas")
        else:
            print("🚫 Muitas tentativas incorretas!")
            print("Sistema bloqueado por segurança.")

if logado:
    print("\n--- ÁREA RESTRITA ---")
    print("Você está logado no sistema!")
```

## 💡 Exercícios Práticos

### 1. Calculadora Simples
```python
# Complete o código
# Crie uma calculadora que funciona até o usuário digitar "sair"
```

### 2. Jogo da Forca Simples
```python
# Complete o código
palavra_secreta = "python"
# O jogador tem 6 tentativas para adivinhar a palavra
```

### 3. Contador de Números Pares
```python
# Complete o código
# Conte quantos números pares existem de 1 a 100
```

---
**Próximo:** [Listas](../3-ESTRUTURAS-DADOS/1-Introducao-Listas.md) ⏹️
