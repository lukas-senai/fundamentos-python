# 📋 Cheat Sheet - Comandos Essenciais Python

## 🎯 Guia Rápido para Consulta

Este é seu guia de consulta rápida com os comandos mais importantes do Python!

## 📊 Tipos de Dados Básicos

```python
# Números
idade = 25              # int (inteiro)
altura = 1.75           # float (decimal)

# Texto
nome = "João"           # str (string)
sobrenome = 'Silva'     # Aspas simples ou duplas

# Booleano
ativo = True            # bool (verdadeiro/falso)
inativo = False
```

## 🔧 Operações Básicas

```python
# Matemática
soma = 5 + 3           # 8
subtracao = 10 - 4     # 6
multiplicacao = 3 * 7  # 21
divisao = 15 / 3       # 5.0
resto = 17 % 5         # 2 (resto da divisão)

# Comparação
igual = 5 == 5         # True
diferente = 5 != 3     # True
maior = 10 > 5         # True
menor_igual = 3 <= 5   # True
```

## 📝 Entrada e Saída

```python
# Mostrar na tela
print("Olá mundo!")
print(f"Meu nome é {nome}")  # f-string

# Receber do usuário
nome = input("Digite seu nome: ")
idade = int(input("Digite sua idade: "))  # Converter para número
```

## 🔀 Estruturas de Controle

### If/Else
```python
if idade >= 18:
    print("Maior de idade")
elif idade >= 13:
    print("Adolescente")
else:
    print("Criança")
```

### For (repetir com lista)
```python
# Com lista
frutas = ["maçã", "banana", "uva"]
for fruta in frutas:
    print(fruta)

# Com números
for i in range(5):      # 0, 1, 2, 3, 4
    print(i)

for i in range(1, 6):   # 1, 2, 3, 4, 5
    print(i)
```

### While (repetir enquanto)
```python
contador = 0
while contador < 5:
    print(contador)
    contador += 1       # contador = contador + 1
```

## 📋 Listas

```python
# Criar lista
numeros = [1, 2, 3, 4, 5]
nomes = ["Ana", "Bruno", "Carlos"]

# Adicionar
numeros.append(6)           # Adiciona no final
numeros.insert(0, 0)        # Adiciona na posição 0

# Acessar
primeiro = numeros[0]       # Primeiro item
ultimo = numeros[-1]        # Último item

# Remover
numeros.remove(3)           # Remove o valor 3
item = numeros.pop()        # Remove e retorna o último
del numeros[0]              # Remove por posição

# Tamanho
tamanho = len(numeros)      # Quantidade de itens
```

## 📚 Dicionários

```python
# Criar dicionário
pessoa = {
    "nome": "João",
    "idade": 30,
    "cidade": "São Paulo"
}

# Acessar
nome = pessoa["nome"]
idade = pessoa.get("idade", 0)  # Valor padrão se não existir

# Adicionar/Modificar
pessoa["profissao"] = "Programador"
pessoa["idade"] = 31

# Remover
del pessoa["cidade"]

# Verificar se existe
if "nome" in pessoa:
    print("Nome existe!")
```

## 🔧 Funções

```python
# Função simples
def saudacao():
    print("Olá!")

# Função com parâmetros
def somar(a, b):
    return a + b

# Função com valor padrão
def apresentar(nome, idade=0):
    print(f"Nome: {nome}, Idade: {idade}")

# Chamar funções
saudacao()
resultado = somar(5, 3)
apresentar("Ana")
apresentar("Bruno", 25)
```

## 📁 Arquivos

```python
# Escrever arquivo
with open("arquivo.txt", "w", encoding="utf-8") as arquivo:
    arquivo.write("Olá mundo!")

# Ler arquivo
with open("arquivo.txt", "r", encoding="utf-8") as arquivo:
    conteudo = arquivo.read()
    print(conteudo)

# JSON
import json

# Salvar em JSON
dados = {"nome": "João", "idade": 30}
with open("dados.json", "w") as arquivo:
    json.dump(dados, arquivo)

# Carregar JSON
with open("dados.json", "r") as arquivo:
    dados = json.load(arquivo)
```

## ⚠️ Tratamento de Erros

```python
try:
    numero = int(input("Digite um número: "))
    resultado = 10 / numero
    print(f"Resultado: {resultado}")
except ValueError:
    print("Erro: Digite um número válido!")
except ZeroDivisionError:
    print("Erro: Não é possível dividir por zero!")
except Exception as e:
    print(f"Erro inesperado: {e}")
```

## 📦 Imports Úteis

```python
import random
numero_aleatorio = random.randint(1, 100)

import datetime
agora = datetime.datetime.now()

import math
raiz = math.sqrt(16)  # 4.0

import os
os.system("clear")    # Linux/Mac
os.system("cls")      # Windows
```

## 🎯 Dicas Rápidas

```python
# Múltiplas variáveis
a, b, c = 1, 2, 3

# Trocar valores
a, b = b, a

# Lista de números
numeros = list(range(1, 11))  # [1, 2, 3, ..., 10]

# Verificar tipo
tipo = type(variavel)

# Converter tipos
texto = str(123)      # "123"
numero = int("456")   # 456
decimal = float("7.8") # 7.8

# Operadores úteis
resultado = 5 if idade >= 18 else 0  # Operador ternário
```

## 🔍 Métodos de String

```python
texto = "Python é Incrível"

# Maiúscula/Minúscula
texto.upper()         # "PYTHON É INCRÍVEL"
texto.lower()         # "python é incrível"
texto.title()         # "Python É Incrível"

# Verificações
texto.startswith("Python")  # True
texto.endswith("vel")        # True
"Python" in texto           # True

# Substituir
texto.replace("Python", "Java")

# Dividir
palavras = texto.split(" ")  # ["Python", "é", "Incrível"]
```

---

## 💡 Lembre-se

- **Indentação é importante!** Use 4 espaços
- **Nomes descritivos** para variáveis e funções
- **Comentários** para explicar código complexo
- **Teste sempre** seu código com diferentes valores
