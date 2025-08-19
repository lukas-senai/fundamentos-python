# 🔄 Repetindo Ações: Loop For

## O que é um Loop For?

Imagine que você precisa escrever "Eu amo Python" 100 vezes no quadro. Você faria isso manualmente? Claro que não! Você criaria uma **regra de repetição**.

O loop `for` é como dizer: **"Para cada item desta lista, faça isso..."**

## 🎯 Conceito com Analogia

Pense no `for` como um **funcionário muito obediente**:

```
👨‍💼 Chefe: "Para cada aluno da turma, entregue um diploma"
🤖 For: "Sim senhor! Vou pegar a lista e entregar um por um"
```

O `for` pega uma lista e executa a mesma ação para cada item.

## 🌟 Estrutura Básica

### For com Range (Números)
```python
# Contando de 1 a 5
print("Vamos contar!")

for numero in range(1, 6):  # 1, 2, 3, 4, 5
    print(f"Número: {numero}")
    
print("Contagem terminada!")
```

**Como funciona:**
1. `range(1, 6)` cria uma sequência: 1, 2, 3, 4, 5
2. Para **cada** número dessa sequência:
   - Coloca o número na variável `numero`
   - Executa o código indentado
3. Repete até acabar a sequência

### For com Listas
```python
# Lista de frutas
frutas = ["maçã", "banana", "laranja", "uva"]

print("Frutas disponíveis:")
for fruta in frutas:
    print(f"- {fruta}")
```

## 🎮 Exemplo Detalhado: Tabuada

Vamos criar uma tabuada do 5 de forma didática:

```python
print("📚 TABUADA DO 5")
print("=" * 20)

numero = 5

for multiplicador in range(1, 11):  # 1 até 10
    resultado = numero * multiplicador
    print(f"{numero} x {multiplicador} = {resultado}")

print("=" * 20)
print("Tabuada concluída!")
```

**Passo a passo:**
1. **1ª volta:** multiplicador = 1 → 5 x 1 = 5
2. **2ª volta:** multiplicador = 2 → 5 x 2 = 10
3. **3ª volta:** multiplicador = 3 → 5 x 3 = 15
4. ...continua até 10

## 🏪 Exemplo Prático: Loja Virtual

```python
# Simulando vendas de uma loja
produtos = ["notebook", "mouse", "teclado", "monitor"]
precos = [2500, 50, 150, 800]

print("🛒 RELATÓRIO DE VENDAS")
print("-" * 30)

total_vendas = 0

for i in range(len(produtos)):  # 0, 1, 2, 3
    produto = produtos[i]
    preco = precos[i]
    
    print(f"Produto: {produto}")
    print(f"Preço: R$ {preco}")
    print(f"Status: Vendido ✅")
    print("-" * 20)
    
    total_vendas += preco

print(f"💰 Total de vendas: R$ {total_vendas}")
```

## 🎨 Diferentes Tipos de Range

### Range Simples
```python
# range(5) = 0, 1, 2, 3, 4
for i in range(5):
    print(f"Posição: {i}")
```

### Range com Início e Fim
```python
# range(2, 8) = 2, 3, 4, 5, 6, 7
for i in range(2, 8):
    print(f"Número: {i}")
```

### Range com Passo
```python
# range(0, 10, 2) = 0, 2, 4, 6, 8
print("Números pares de 0 a 8:")
for i in range(0, 10, 2):
    print(i)
```

## 🔤 For com Strings

Você pode percorrer cada letra de uma palavra:

```python
palavra = "PYTHON"

print("Analisando cada letra:")
for letra in palavra:
    print(f"Letra: {letra}")
```

## 🎯 Exemplo Avançado: Validador de Email

```python
emails = ["joao@gmail.com", "maria@", "pedro@yahoo.com", "ana@hotmail"]

print("📧 VALIDANDO EMAILS")
print("=" * 25)

emails_validos = 0

for email in emails:
    print(f"Verificando: {email}")
    
    if "@" in email and "." in email:
        print("✅ Email válido!")
        emails_validos += 1
    else:
        print("❌ Email inválido!")
    
    print("-" * 25)

print(f"📊 Resultado: {emails_validos} emails válidos de {len(emails)}")
```

## 💡 Exercícios Práticos

### 1. Contador de Vogais
```python
# Complete o código
frase = "Python é incrível"

# Conte quantas vogais (a, e, i, o, u) existem na frase
```

### 2. Calculadora de Média
```python
# Complete o código
notas = [8.5, 7.0, 9.2, 6.8, 8.0]

# Calcule a média das notas usando for
```

### 3. Gerador de Senhas
```python
# Complete o código
import random

caracteres = "abcdefghijklmnopqrstuvwxyz0123456789"

# Gere uma senha de 8 caracteres aleatórios
```

---
**Próximo:** [While - Repetição com Condição](3-While.md) ⏰
