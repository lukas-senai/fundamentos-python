# 🔧 Definindo Funções

## O que são Funções?

Imagine que você tem uma receita de bolo que usa muito. Em vez de escrever todos os ingredientes e passos toda vez, você simplesmente diz "faça o bolo de chocolate". Uma **função** em Python é exatamente isso: um conjunto de instruções que você pode reutilizar sempre que precisar.

### Analogia da Máquina de Suco 🥤

Pense numa máquina de fazer suco:
- **Entrada**: Você coloca frutas
- **Processamento**: A máquina corta, mistura e processa
- **Saída**: Sai o suco pronto

```python
# Função é como uma máquina de suco
def fazer_suco(fruta):
    resultado = f"Suco de {fruta} fresquinho!"
    return resultado

# Usando a "máquina"
meu_suco = fazer_suco("laranja")
print(meu_suco)  # Suco de laranja fresquinho!
```

## Anatomia de uma Função

```python
def nome_da_funcao(parametros):
    """Documentação da função"""
    # Corpo da função
    return resultado
```

### Explicação Detalhada:

1. **`def`**: Palavra que diz "vou criar uma função"
2. **`nome_da_funcao`**: O nome que você dá para sua função
3. **`(parametros)`**: Os "ingredientes" que a função precisa
4. **`:`**: Indica que o código da função vem a seguir
5. **Corpo**: As instruções que a função executa
6. **`return`**: O que a função "entrega" de volta

## Exemplos Progressivos

### Exemplo 1: Função Simples (sem parâmetros)
```python
def cumprimentar():
    print("Olá! Bem-vindo ao Python!")

# Chamando a função
cumprimentar()  # Olá! Bem-vindo ao Python!
```

### Exemplo 2: Função com Parâmetro
```python
def cumprimentar_pessoa(nome):
    print(f"Olá, {nome}! Como você está?")

cumprimentar_pessoa("Maria")  # Olá, Maria! Como você está?
cumprimentar_pessoa("João")   # Olá, João! Como você está?
```

### Exemplo 3: Função que Retorna Valor
```python
def somar(a, b):
    resultado = a + b
    return resultado

# Guardando o resultado
soma = somar(5, 3)
print(f"5 + 3 = {soma}")  # 5 + 3 = 8
```

### Exemplo 4: Função Mais Complexa
```python
def calcular_idade_em_dias(anos):
    """
    Calcula quantos dias uma pessoa viveu
    (aproximadamente, sem considerar anos bissextos)
    """
    dias = anos * 365
    return dias

idade_anos = 25
idade_dias = calcular_idade_em_dias(idade_anos)
print(f"Você viveu aproximadamente {idade_dias} dias!")
```

## Por que Usar Funções?

### 1. **Reutilização** 🔄
```python
def calcular_area_retangulo(largura, altura):
    return largura * altura

# Posso usar quantas vezes quiser
area1 = calcular_area_retangulo(5, 3)
area2 = calcular_area_retangulo(10, 7)
area3 = calcular_area_retangulo(2, 8)
```

### 2. **Organização** 📁
```python
# Em vez de código bagunçado:
nome = input("Seu nome: ")
print(f"Olá, {nome}")
idade = int(input("Sua idade: "))
if idade >= 18:
    print("Você é maior de idade")
else:
    print("Você é menor de idade")

# Melhor com funções:
def obter_nome():
    return input("Seu nome: ")

def obter_idade():
    return int(input("Sua idade: "))

def verificar_maioridade(idade):
    if idade >= 18:
        return "Você é maior de idade"
    else:
        return "Você é menor de idade"

# Código principal limpo
nome = obter_nome()
print(f"Olá, {nome}")
idade = obter_idade()
print(verificar_maioridade(idade))
```

## Exercícios Práticos

### Exercício 1: Calculadora Básica
```python
# Crie funções para as operações básicas
def somar(a, b):
    # Seu código aqui
    pass

def subtrair(a, b):
    # Seu código aqui
    pass

# Teste suas funções
print(somar(10, 5))     # Deve imprimir 15
print(subtrair(10, 5))  # Deve imprimir 5
```

### Exercício 2: Conversor de Temperatura
```python
def celsius_para_fahrenheit(celsius):
    # Fórmula: F = C * 9/5 + 32
    # Seu código aqui
    pass

# Teste
print(celsius_para_fahrenheit(0))   # Deve imprimir 32.0
print(celsius_para_fahrenheit(100)) # Deve imprimir 212.0
```

### Exercício 3: Validador de Senha
```python
def senha_eh_forte(senha):
    # Uma senha forte tem pelo menos 8 caracteres
    # Retorne True se for forte, False se não for
    # Seu código aqui
    pass

# Teste
print(senha_eh_forte("123"))        # False
print(senha_eh_forte("minhasenha123")) # True
```

## Dicas Importantes

1. **Nomes Descritivos**: Use nomes que expliquem o que a função faz
   ```python
   # ❌ Ruim
   def calc(x, y):
       return x * y
   
   # ✅ Bom
   def calcular_area_retangulo(largura, altura):
       return largura * altura
   ```

2. **Uma Função, Uma Tarefa**: Cada função deve fazer apenas uma coisa
   ```python
   # ❌ Função fazendo muitas coisas
   def processar_usuario(nome, idade):
       print(f"Olá, {nome}")
       if idade >= 18:
           print("Maior de idade")
       return idade * 365
   
   # ✅ Funções separadas
   def cumprimentar(nome):
       print(f"Olá, {nome}")
   
   def verificar_maioridade(idade):
       if idade >= 18:
           print("Maior de idade")
   
   def calcular_dias_vividos(idade):
       return idade * 365
   ```

---

**Próximo:** [Parâmetros e Argumentos](2-Parametros-Argumentos.md) 📝
