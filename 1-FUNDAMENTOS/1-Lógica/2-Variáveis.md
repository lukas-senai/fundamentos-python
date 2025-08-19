# 📦 Variáveis - As Caixinhas da Programação

Agora que você entende algoritmos, vamos aprender sobre **variáveis** - um dos conceitos mais importantes da programação! Pense nelas como caixinhas etiquetadas onde guardamos informações.

## 🏷️ O que são Variáveis?

### Imagine variáveis como **caixinhas com etiquetas**:

```
┌─────────────┐    ┌─────────────┐    ┌─────────────┐
│   NOME      │    │    IDADE    │    │   ALTURA    │
│             │    │             │    │             │
│  "Maria"    │    │     25      │    │    1.65     │
└─────────────┘    └─────────────┘    └─────────────┘
```

- **Etiqueta** = Nome da variável
- **Conteúdo** = Valor armazenado
- **Caixinha** = Espaço na memória do computador

### Na Programação
```python
# Criando nossas "caixinhas"
nome = "Maria"           # Texto (string)
idade = 25               # Número inteiro (int)
altura = 1.65            # Número decimal (float)
casada = False           # Verdadeiro/Falso (bool)
```

## 🎯 Por que Usar Variáveis?

### 1. 💾 **Armazenar Informações**
```python
# Sem variáveis (ruim)
print("Olá, Maria!")
print("Maria tem 25 anos")
print("Maria mede 1.65m")

# Com variáveis (bom)
nome = "Maria"
idade = 25
altura = 1.65

print(f"Olá, {nome}!")
print(f"{nome} tem {idade} anos")
print(f"{nome} mede {altura}m")
```

### 2. 🔄 **Reutilizar Valores**
```python
preco = 100.00
desconto = 0.10

preco_com_desconto = preco - (preco * desconto)
print(f"Preço original: R$ {preco}")
print(f"Preço com desconto: R$ {preco_com_desconto}")
```

### 3. 🔧 **Facilitar Mudanças**
```python
# Mudando apenas uma linha, tudo se atualiza
nome_loja = "TechStore"  # Mude aqui e tudo muda!

print(f"Bem-vindo à {nome_loja}!")
print(f"Obrigado por comprar na {nome_loja}")
print(f"Volte sempre à {nome_loja}!")
```

## 🏗️ Criando Variáveis em Python

### Sintaxe Básica
```python
nome_da_variavel = valor
```

### Exemplos Práticos
```python
# Informações pessoais
nome = "Maria"
sobrenome = "Santos"
idade = 30
peso = 65.5
tem_carteira = True

# Informações de produto
produto = "Notebook"
preco = 2500.99
em_estoque = True
quantidade = 15

# Cálculos
nota1 = 8.5
nota2 = 7.0
nota3 = 9.2
media = (nota1 + nota2 + nota3) / 3
```

## 🎨 Tipos de Dados Básicos

### 1. 🔤 **String (str)** - Texto
```python
nome = "Python"
frase = "Eu amo programar!"
endereco = "Rua das Flores, 123"

# Aspas simples ou duplas funcionam
linguagem = 'Python'
mensagem = "Olá, mundo!"
```

### 2. 🔢 **Integer (int)** - Números Inteiros
```python
idade = 25
ano = 2024
temperatura = -5
pontos = 1000
```

### 3. 🔢 **Float** - Números Decimais
```python
altura = 1.75
preco = 29.99
pi = 3.14159
temperatura = 36.5
```

### 4. ✅ **Boolean (bool)** - Verdadeiro/Falso
```python
maior_de_idade = True
chovendo = False
tem_desconto = True
aprovado = False
```

### 5. ❌ **None** - Valor Vazio
```python
resultado = None  # Ainda não tem valor
resposta = None   # Será preenchido depois
```

## 🏷️ Regras para Nomes de Variáveis

### ✅ **Permitido**
```python
nome = "João"           # Letras minúsculas
IDADE = 25              # Letras maiúsculas
nome_completo = "..."   # Underscore (snake_case)
idade2 = 30             # Números no final
_privado = "secreto"    # Underscore no início
```

### ❌ **Não Permitido**
```python
2idade = 25        # ❌ Não pode começar com número
nome-completo = "" # ❌ Hífen não é permitido
class = "A"        # ❌ Palavra reservada do Python
nome completo = "" # ❌ Espaços não são permitidos
```

### 🎯 **Boas Práticas**
```python
# ✅ Nomes descritivos
idade_usuario = 25
preco_produto = 99.90
nome_completo = "Ana Silva"

# ❌ Nomes confusos
x = 25
p = 99.90
n = "Ana Silva"

# ✅ Snake_case (padrão Python)
data_nascimento = "01/01/1990"
salario_bruto = 5000.00

# ❌ CamelCase (não é padrão Python)
dataNascimento = "01/01/1990"
salarioBruto = 5000.00
```

## 🔄 Atribuição e Reatribuição

### Primeira Atribuição
```python
contador = 0
print(contador)  # Saída: 0
```

### Reatribuição (Mudando o Valor)
```python
contador = 0      # Valor inicial
print(contador)   # Saída: 0

contador = 5      # Novo valor
print(contador)   # Saída: 5

contador = contador + 1  # Incremento
print(contador)   # Saída: 6
```

### Atribuição Múltipla
```python
# Várias variáveis com o mesmo valor
a = b = c = 0
print(a, b, c)  # Saída: 0 0 0

# Várias variáveis com valores diferentes
nome, idade, altura = "João", 25, 1.75
print(nome)     # Saída: João
print(idade)    # Saída: 25
print(altura)   # Saída: 1.75
```

## 🔍 Verificando Tipos

### Função type()
```python
nome = "Python"
idade = 25
altura = 1.75
ativo = True

print(type(nome))    # <class 'str'>
print(type(idade))   # <class 'int'>
print(type(altura))  # <class 'float'>
print(type(ativo))   # <class 'bool'>
```

### Função isinstance()
```python
idade = 25

print(isinstance(idade, int))    # True
print(isinstance(idade, str))    # False
print(isinstance(idade, float))  # False
```

## 🎮 Exemplos Práticos

### 📊 **Sistema de Notas**
```python
# Dados do aluno
nome_aluno = "Carlos"
disciplina = "Matemática"

# Notas
nota1 = 8.5
nota2 = 7.0
nota3 = 9.2
nota4 = 6.8

# Cálculos
media = (nota1 + nota2 + nota3 + nota4) / 4
aprovado = media >= 7.0

# Resultados
print(f"Aluno: {nome_aluno}")
print(f"Disciplina: {disciplina}")
print(f"Média: {media:.1f}")
print(f"Situação: {'Aprovado' if aprovado else 'Reprovado'}")
```

### 🛒 **Sistema de Compras**
```python
# Produto
nome_produto = "Smartphone"
preco_original = 1200.00
desconto_percentual = 15
quantidade = 2

# Cálculos
valor_desconto = preco_original * (desconto_percentual / 100)
preco_com_desconto = preco_original - valor_desconto
total_compra = preco_com_desconto * quantidade

# Nota fiscal
print("=== NOTA FISCAL ===")
print(f"Produto: {nome_produto}")
print(f"Preço original: R$ {preco_original:.2f}")
print(f"Desconto ({desconto_percentual}%): R$ {valor_desconto:.2f}")
print(f"Preço unitário: R$ {preco_com_desconto:.2f}")
print(f"Quantidade: {quantidade}")
print(f"Total: R$ {total_compra:.2f}")
```

## 💡 Dicas Importantes

### 1. 🎯 **Case Sensitivity**
Python diferencia maiúsculas de minúsculas:
```python
nome = "João"
Nome = "Maria"
NOME = "Pedro"

print(nome)  # João
print(Nome)  # Maria
print(NOME)  # Pedro
```

### 2. 🔄 **Variáveis são Referências**
```python
a = 10
b = a      # b recebe o valor de a
a = 20     # Mudando a não afeta b

print(a)   # 20
print(b)   # 10
```

### 3. 📝 **Nomes Significativos**
```python
# ❌ Ruim
x = 1200
y = 0.15
z = x * y

# ✅ Bom
salario = 1200
taxa_imposto = 0.15
imposto = salario * taxa_imposto
```

## 🎮 Exercícios Práticos

### 🏃‍♂️ **Exercício 1: Dados Pessoais**
Crie variáveis para armazenar:
- Seu nome completo
- Sua idade
- Sua altura
- Se você gosta de programar (True/False)

Depois, imprima todas as informações.

### 🔢 **Exercício 2: Calculadora Simples**
Crie variáveis para dois números e calcule:
- Soma
- Subtração
- Multiplicação
- Divisão

### 🏪 **Exercício 3: Loja Virtual**
Crie um sistema que calcule o total de uma compra:
- Nome do produto
- Preço unitário
- Quantidade
- Desconto (%)
- Total final

### 🎯 **Exercício 4: Conversor de Temperatura**
Crie variáveis para converter Celsius para Fahrenheit:
- Temperatura em Celsius
- Fórmula: F = (C × 9/5) + 32
- Resultado em Fahrenheit

## 🔗 Próximos Passos

Agora que você domina variáveis, vamos aprender sobre [Operadores](3-Operadores.md) - as ferramentas que nos permitem fazer cálculos e comparações com nossas variáveis!

---

### 📝 Resumo do Capítulo
- ✅ Variáveis são como caixinhas etiquetadas para guardar dados
- ✅ Python tem tipos básicos: str, int, float, bool, None
- ✅ Nomes devem ser descritivos e seguir as regras
- ✅ Use snake_case para nomes de variáveis
- ✅ Variáveis podem ser reatribuídas a qualquer momento

**Próximo:** [Operadores - Fazendo Cálculos e Comparações →](3-Operadores.md)
