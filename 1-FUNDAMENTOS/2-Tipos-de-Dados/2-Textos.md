# 📝 Textos (Strings) em Python

## O que são Strings?

Imagine que você está escrevendo uma carta. As **palavras, frases e textos** que você escreve são chamados de "strings" em programação. É como se fossem "cordas de letras" amarradas juntas!

## 🎭 Criando Textos

### Aspas Simples ou Duplas
```python
# Ambas funcionam igual!
nome = "Maria"
sobrenome = 'Silva'
frase = "Olá, mundo!"

print(nome)
print(sobrenome)
print(frase)
```

### Textos Longos (Aspas Triplas)
```python
# Para textos com várias linhas
poema = """
Roses are red,
Violets are blue,
Python is awesome,
And so are you!
"""
print(poema)
```

## 🔧 Manipulando Textos

### Juntando Textos (Concatenação)
É como colar palavras:

```python
nome = "João"
sobrenome = "Santos"

# Método 1: Usando +
nome_completo = nome + " " + sobrenome
print(nome_completo)  # João Santos

# Método 2: Usando f-strings (mais moderno!)
apresentacao = f"Olá, eu sou {nome} {sobrenome}"
print(apresentacao)  # Olá, eu sou João Santos
```

### Métodos Úteis
```python
texto = "Gosto de ouvir Música"

# Transformações
print(texto.upper())      # GOSTO DE OUVIR MÚSICA
print(texto.lower())      # gosto de ouvir música
print(texto.title())      # Gosto De Ouvir Música

# Informações
print(len(texto))         # 21 (quantidade de caracteres)
print(texto.count("o"))   # 3 (quantas vezes "i" aparece)

# Verificações
print(texto.startswith("Gosto"))  # True
print(texto.endswith("Música"))   # False
```

## 🎯 Exemplo Prático: Criador de Email

```python
# Criando email automático
nome = "Ana"
sobrenome = "Costa"
empresa = "techcorp"

# Criando o email
email = f"{nome.lower()}.{sobrenome.lower()}@{empresa}.com"
print("Seu email é:", email)  # ana.costa@techcorp.com

# Criando uma saudação personalizada
saudacao = f"Bem-vinda, {nome.title()}! Seu email {email} foi criado com sucesso."
print(saudacao)
```

## 💡 Exercícios

1. **Gerador de Username**: Crie um username usando primeira letra do nome + sobrenome
2. **Contador de Palavras**: Conte quantas palavras tem uma frase
3. **Formatador de Nome**: Transforme "joão silva" em "João Silva"

---
**Próximo:** [If Else](../../2-ESTRUTURAS-CONTROLE/1-If-Else.md) 📋
