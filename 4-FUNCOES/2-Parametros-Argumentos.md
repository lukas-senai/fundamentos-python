# 📝 Parâmetros e Argumentos

## Diferença Entre Parâmetros e Argumentos

### Analogia do Restaurante 🍽️

Imagine um restaurante:
- **Parâmetros** são como os "espaços em branco" no cardápio: "Sanduíche de _____ com _____"
- **Argumentos** são os ingredientes específicos que você escolhe: "Sanduíche de **frango** com **queijo**"

```python
def fazer_sanduiche(carne, acompanhamento):  # carne e acompanhamento são PARÂMETROS
    return f"Sanduíche de {carne} com {acompanhamento}"

# Quando chamamos a função:
pedido = fazer_sanduiche("frango", "queijo")  # "frango" e "queijo" são ARGUMENTOS
```

## Tipos de Parâmetros

### 1. Parâmetros Obrigatórios (Posicionais)
```python
def apresentar_pessoa(nome, idade, cidade):
    print(f"{nome} tem {idade} anos e mora em {cidade}")

# Todos os argumentos são obrigatórios
apresentar_pessoa("Ana", 25, "São Paulo")
# apresentar_pessoa("Ana")  # ❌ Erro! Faltam argumentos
```

### 2. Parâmetros com Valores Padrão
```python
def fazer_cafe(tipo="expresso", acucar=False, leite=False):
    cafe = f"Café {tipo}"
    if acucar:
        cafe += " com açúcar"
    if leite:
        cafe += " com leite"
    return cafe

# Diferentes formas de chamar:
print(fazer_cafe())                           # Café expresso
print(fazer_cafe("cappuccino"))               # Café cappuccino
print(fazer_cafe("latte", True, True))        # Café latte com açúcar com leite
print(fazer_cafe(acucar=True))                # Café expresso com açúcar
```

### 3. Argumentos Nomeados (Keywords)
```python
def criar_perfil(nome, idade, profissao, cidade="Não informado"):
    return f"{nome}, {idade} anos, {profissao}, mora em {cidade}"

# Usando argumentos nomeados (pode mudar a ordem!)
perfil1 = criar_perfil(nome="João", profissao="Programador", idade=30)
perfil2 = criar_perfil(idade=25, nome="Maria", profissao="Designer", cidade="Rio de Janeiro")

print(perfil1)
print(perfil2)
```

## Exemplos Práticos Detalhados

### Exemplo 1: Calculadora Avançada
```python
def calcular(operacao, num1, num2, mostrar_calculo=True):
    """
    Calculadora que pode mostrar ou não o cálculo
    """
    if operacao == "soma":
        resultado = num1 + num2
        simbolo = "+"
    elif operacao == "subtracao":
        resultado = num1 - num2
        simbolo = "-"
    elif operacao == "multiplicacao":
        resultado = num1 * num2
        simbolo = "*"
    elif operacao == "divisao":
        if num2 != 0:
            resultado = num1 / num2
            simbolo = "/"
        else:
            return "Erro: Divisão por zero!"
    else:
        return "Operação não reconhecida!"
    
    if mostrar_calculo:
        return f"{num1} {simbolo} {num2} = {resultado}"
    else:
        return resultado

# Testando diferentes formas de usar:
print(calcular("soma", 10, 5))                    # 10 + 5 = 15
print(calcular("multiplicacao", 3, 4, False))     # 12
print(calcular(num1=20, num2=4, operacao="divisao"))  # 20 / 4 = 5.0
```

### Exemplo 2: Sistema de Cadastro
```python
def cadastrar_usuario(nome, email, idade=None, telefone=None, ativo=True):
    """
    Cadastra um usuário com informações obrigatórias e opcionais
    """
    usuario = {
        "nome": nome,
        "email": email,
        "ativo": ativo
    }
    
    if idade is not None:
        usuario["idade"] = idade
    
    if telefone is not None:
        usuario["telefone"] = telefone
    
    return usuario

# Diferentes formas de cadastrar:
user1 = cadastrar_usuario("Ana", "ana@email.com")
user2 = cadastrar_usuario("João", "joao@email.com", idade=30)
user3 = cadastrar_usuario("Maria", "maria@email.com", telefone="11999999999", idade=25)
user4 = cadastrar_usuario(email="pedro@email.com", nome="Pedro", ativo=False)

print(user1)
print(user2)
print(user3)
print(user4)
```

## Parâmetros Especiais

### *args - Múltiplos Argumentos Posicionais
```python
def somar_todos(*numeros):
    """
    Soma qualquer quantidade de números
    *args permite receber vários argumentos como uma tupla
    """
    total = 0
    for numero in numeros:
        total += numero
    return total

# Pode receber qualquer quantidade de números:
print(somar_todos(1, 2, 3))           # 6
print(somar_todos(10, 20, 30, 40))    # 100
print(somar_todos(5))                 # 5
print(somar_todos())                  # 0
```

### **kwargs - Múltiplos Argumentos Nomeados
```python
def criar_produto(**detalhes):
    """
    Cria um produto com qualquer quantidade de características
    **kwargs permite receber argumentos nomeados como um dicionário
    """
    produto = {}
    for chave, valor in detalhes.items():
        produto[chave] = valor
    return produto

# Pode receber qualquer quantidade de características:
produto1 = criar_produto(nome="Notebook", preco=2500, marca="Dell")
produto2 = criar_produto(nome="Mouse", preco=50, cor="Preto", wireless=True)

print(produto1)
print(produto2)
```

### Combinando *args e **kwargs
```python
def funcao_completa(obrigatorio, padrao="valor padrão", *args, **kwargs):
    """
    Função que aceita todos os tipos de parâmetros
    """
    print(f"Obrigatório: {obrigatorio}")
    print(f"Padrão: {padrao}")
    
    if args:
        print(f"Argumentos extras: {args}")
    
    if kwargs:
        print(f"Argumentos nomeados: {kwargs}")

# Testando:
funcao_completa("valor1")
print("---")
funcao_completa("valor1", "valor2", "extra1", "extra2", nome="João", idade=30)
```

## Exercícios Práticos

### Exercício 1: Gerador de Mensagens
```python
def gerar_mensagem(nome, evento="aniversário", idade=None, personalizada=False):
    """
    Gera mensagens para diferentes ocasiões
    """
    # Seu código aqui
    pass

# Teste suas funções:
print(gerar_mensagem("Ana"))
print(gerar_mensagem("João", "formatura"))
print(gerar_mensagem("Maria", "aniversário", 25))
print(gerar_mensagem("Pedro", personalizada=True))
```

### Exercício 2: Calculadora de Média
```python
def calcular_media(*notas, mostrar_detalhes=False):
    """
    Calcula a média de qualquer quantidade de notas
    Se mostrar_detalhes=True, mostra todas as notas
    """
    # Seu código aqui
    pass

# Teste:
print(calcular_media(8, 7, 9))                    # Deve mostrar só a média
print(calcular_media(8, 7, 9, mostrar_detalhes=True))  # Deve mostrar notas e média
```

### Exercício 3: Criador de Perfis
```python
def criar_perfil_completo(nome, **informacoes):
    """
    Cria um perfil com nome obrigatório e outras informações opcionais
    """
    # Seu código aqui
    pass

# Teste:
perfil = criar_perfil_completo("Ana", idade=25, profissao="Programadora", cidade="SP")
print(perfil)
```

## Dicas Importantes

1. **Ordem dos Parâmetros**:
   ```python
   def funcao(posicionais, padrao=valor, *args, **kwargs):
       pass
   ```

2. **Argumentos Nomeados são Mais Claros**:
   ```python
   # ❌ Difícil de entender
   enviar_email("joão@email.com", "Olá!", True, False, "urgente")
   
   # ✅ Muito mais claro
   enviar_email(
       destinatario="joão@email.com",
       mensagem="Olá!",
       copia_oculta=True,
       confirmar_leitura=False,
       prioridade="urgente"
   )
   ```

3. **Valores Padrão Mutáveis** (Cuidado!):
   ```python
   # ❌ Problema comum
   def adicionar_item(item, lista=[]):
       lista.append(item)
       return lista
   
   # ✅ Forma correta
   def adicionar_item(item, lista=None):
       if lista is None:
           lista = []
       lista.append(item)
       return lista
   ```

---

**Próximo:** [Escopo de Variáveis](../5-TRATAMENTO-ERROS/) 🔍
