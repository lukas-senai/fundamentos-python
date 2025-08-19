# 📊 Números em Python

## O que são Números na Programação?

Imagine que você está organizando sua coleção de livros. Alguns dados são **quantidades** (como "tenho 25 livros"), outros são **medidas** (como "este livro tem 15.5 cm de altura"). Em Python, trabalhamos com diferentes tipos de números para diferentes situações!

## 🔢 Tipos de Números

### 1. Números Inteiros (int)
São números **sem vírgula** - como contar objetos:

```python
# Exemplos de números inteiros
idade = 25
livros = 10
temperatura = -5
pontos = 0

print("Minha idade:", idade)
print("Quantidade de livros:", livros)
```

### 2. Números Decimais (float)
São números **com vírgula** (mas usamos ponto em Python):

```python
# Exemplos de números decimais
altura = 1.75
preco = 29.90
temperatura = 36.5
nota = 8.7

print("Minha altura:", altura, "metros")
print("Preço do produto: R$", preco)
```

## 🧮 Operações Matemáticas

Python é como uma calculadora super poderosa:

```python
# Operações básicas
a = 10
b = 3

soma = a + b          # 13
subtracao = a - b     # 7
multiplicacao = a * b # 30
divisao = a / b       # 3.333...
divisao_inteira = a // b  # 3 (só a parte inteira)
resto = a % b         # 1 (resto da divisão)
potencia = a ** b     # 1000 (10 elevado a 3)

print("Soma:", soma)
print("Divisão:", divisao)
print("Resto da divisão:", resto)
```

## 🎯 Exemplo Prático: Calculadora de Gorjeta

```python
# Calculando gorjeta em um restaurante
valor_conta = 85.50
percentual_gorjeta = 10

# Calculando a gorjeta
gorjeta = valor_conta * percentual_gorjeta / 100
total = valor_conta + gorjeta

print("Valor da conta: R$", valor_conta)
print("Gorjeta (10%): R$", gorjeta)
print("Total a pagar: R$", total)
```

## 💡 Exercícios

1. **Calculadora Simples**: Crie um programa que calcule a área de um retângulo
2. **Conversor**: Converta temperatura de Celsius para Fahrenheit
3. **Calculadora de IMC**: Calcule o Índice de Massa Corporal

---
**Próximo:** [Textos (Strings)](2-Textos.md) 📝
