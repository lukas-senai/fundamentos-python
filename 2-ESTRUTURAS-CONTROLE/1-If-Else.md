# 🤔 Tomando Decisões: If e Else

## O que são Condicionais?

Imagine que você está saindo de casa e precisa decidir se leva guarda-chuva. Você olha pela janela e pensa:

**"SE está chovendo, ENTÃO levo guarda-chuva, SENÃO não levo"**

Isso é exatamente como funciona o `if` e `else` em Python! O computador toma decisões baseadas em condições.

## 🌟 A Estrutura Básica

### If Simples
```python
# Exemplo: Verificando se pode dirigir
idade = 18

if idade >= 18:
    print("Você pode dirigir!")
    print("Parabéns pela maioridade!")
```

**Como funciona:**
1. Python verifica se `idade >= 18` é verdadeiro
2. **SE** for verdadeiro, executa o código indentado
3. **SE** for falso, pula essa parte

### If-Else (Se-Senão)
```python
# Exemplo: Entrada em festa
idade = 16

if idade >= 18:
    print("Pode entrar na festa!")
    print("Divirta-se!")
else:
    print("Desculpe, você é menor de idade")
    print("Volte quando fizer 18 anos")
```

**Como funciona:**
1. **SE** a condição for verdadeira → executa o primeiro bloco
2. **SENÃO** → executa o bloco do `else`

## 🎯 Exemplo Detalhado: Sistema de Notas

Vamos criar um sistema que avalia se um aluno foi aprovado:

```python
# Sistema de aprovação escolar
nome = "Maria"
nota = 7.5

print(f"Analisando a situação de {nome}...")
print(f"Nota obtida: {nota}")

if nota >= 7.0:
    print("🎉 APROVADO!")
    print("Parabéns pelo seu desempenho!")
    print("Você pode avançar para a próxima série.")
else:
    print("😔 REPROVADO")
    print("Não desanime! Estude mais e tente novamente.")
    print("A nota mínima é 7.0")

print("Fim da análise.")
```

## 🔄 If-Elif-Else (Múltiplas Condições)

Às vezes precisamos verificar várias condições, como um semáforo:

```python
# Sistema de semáforo
cor = "amarelo"

if cor == "verde":
    print("🟢 SIGA em frente!")
elif cor == "amarelo":
    print("🟡 ATENÇÃO! Prepare-se para parar")
elif cor == "vermelho":
    print("🔴 PARE! Aguarde o sinal verde")
else:
    print("❓ Cor inválida no semáforo")
```

**Como funciona:**
1. Verifica a primeira condição (`if`)
2. Se falsa, verifica a segunda (`elif`)
3. Se falsa, verifica a terceira (`elif`)
4. Se todas forem falsas, executa o `else`

## 🎮 Exemplo Prático: Jogo de Adivinhação

```python
# Jogo simples de adivinhação
numero_secreto = 42
palpite = 35

print("🎯 JOGO DE ADIVINHAÇÃO")
print(f"Seu palpite: {palpite}")
print(f"Número secreto: {numero_secreto}")

if palpite == numero_secreto:
    print("🎉 ACERTOU! Você é um gênio!")
elif palpite < numero_secreto:
    print("📈 Muito baixo! Tente um número maior")
else:
    print("📉 Muito alto! Tente um número menor")

print("Obrigado por jogar!")
```

## 🧠 Operadores de Comparação

Para tomar decisões, precisamos comparar valores:

```python
a = 10
b = 5

# Igualdade
print(a == b)  # False (10 não é igual a 5)

# Diferença
print(a != b)  # True (10 é diferente de 5)

# Maior que
print(a > b)   # True (10 é maior que 5)

# Menor que
print(a < b)   # False (10 não é menor que 5)

# Maior ou igual
print(a >= 10) # True (10 é maior ou igual a 10)

# Menor ou igual
print(b <= 5)  # True (5 é menor ou igual a 5)
```

## 💡 Exercícios Práticos

### 1. Classificador de Idade
```python
# Complete o código
idade = 25

# Classifique em: criança (0-12), adolescente (13-17), 
# adulto (18-59), idoso (60+)
```

### 2. Calculadora de Desconto
```python
# Complete o código
valor_compra = 150

# Se compra >= 100: desconto de 10%
# Se compra >= 50: desconto de 5%
# Senão: sem desconto
```

### 3. Verificador de Senha
```python
# Complete o código
senha = "python123"

# Verifique se a senha tem pelo menos 8 caracteres
# e contém números
```

---
**Próximo:** [For](2-For.md) 🧮
