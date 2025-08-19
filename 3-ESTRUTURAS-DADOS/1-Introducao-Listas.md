# 📋 Introdução às Listas

## O que são Listas?

### Analogia da Lista de Compras 🛒

Imagine que você vai ao supermercado e faz uma lista de compras:
```
1. Leite
2. Pão
3. Ovos
4. Queijo
5. Maçãs
```

Uma **lista** em Python é exatamente isso: uma coleção ordenada de itens que você pode:
- ✅ Adicionar novos itens
- ✅ Remover itens
- ✅ Modificar itens existentes
- ✅ Ver quantos itens tem
- ✅ Procurar por um item específico

```python
# Lista de compras em Python
lista_compras = ["leite", "pão", "ovos", "queijo", "maçãs"]
```

## Criando Listas

### Formas Diferentes de Criar Listas

```python
# 1. Lista vazia
lista_vazia = []
outra_lista_vazia = list()

# 2. Lista com números
numeros = [1, 2, 3, 4, 5]

# 3. Lista com textos
frutas = ["maçã", "banana", "laranja"]

# 4. Lista mista (diferentes tipos)
mista = ["João", 25, True, 1.75]

# 5. Lista de listas (como uma tabela)
tabela = [
    ["Nome", "Idade", "Cidade"],
    ["Ana", 30, "São Paulo"],
    ["João", 25, "Rio de Janeiro"]
]
```

## Acessando Elementos da Lista

### Analogia dos Apartamentos 🏢

Imagine um prédio onde cada apartamento tem um número:
- Apartamento 0: Primeiro andar
- Apartamento 1: Segundo andar  
- Apartamento 2: Terceiro andar

Em Python, as listas funcionam igual:

```python
frutas = ["maçã", "banana", "laranja", "uva", "manga"]
#         [  0  ] [   1  ] [   2   ] [ 3 ] [  4  ]

# Acessando elementos pelo índice
print(frutas[0])    # maçã (primeiro elemento)
print(frutas[1])    # banana (segundo elemento)
print(frutas[2])    # laranja (terceiro elemento)

# Último elemento
print(frutas[4])    # manga
print(frutas[-1])   # manga (forma mais fácil de pegar o último)

# Penúltimo elemento
print(frutas[-2])   # uva
```

### Índices Negativos - Contando de Trás para Frente
```python
frutas = ["maçã", "banana", "laranja", "uva", "manga"]
#         [ -5  ] [  -4  ] [   -3   ] [-2 ] [ -1  ]

print(frutas[-1])   # manga (último)
print(frutas[-2])   # uva (penúltimo)
print(frutas[-5])   # maçã (primeiro, contando de trás)
```

## Operações Básicas com Listas

### 1. Verificar o Tamanho da Lista
```python
frutas = ["maçã", "banana", "laranja"]
quantidade = len(frutas)
print(f"Temos {quantidade} frutas na lista")  # Temos 3 frutas na lista
```

### 2. Verificar se um Item Existe
```python
frutas = ["maçã", "banana", "laranja"]

# Verificando se existe
if "banana" in frutas:
    print("Temos banana!")  # Esta mensagem vai aparecer

if "uva" in frutas:
    print("Temos uva!")     # Esta mensagem NÃO vai aparecer
else:
    print("Não temos uva")  # Esta mensagem vai aparecer
```

### 3. Adicionando Elementos

#### append() - Adiciona no Final
```python
frutas = ["maçã", "banana"]
print(f"Antes: {frutas}")

frutas.append("laranja")
print(f"Depois: {frutas}")  # ['maçã', 'banana', 'laranja']

# Analogia: É como adicionar um item no final da sua lista de compras
```

#### insert() - Adiciona em Posição Específica
```python
frutas = ["maçã", "banana", "laranja"]
print(f"Antes: {frutas}")

# Inserir "uva" na posição 1 (segunda posição)
frutas.insert(1, "uva")
print(f"Depois: {frutas}")  # ['maçã', 'uva', 'banana', 'laranja']

# Analogia: É como inserir um item no meio da sua lista
```

### 4. Removendo Elementos

#### remove() - Remove por Valor
```python
frutas = ["maçã", "banana", "laranja", "banana"]
print(f"Antes: {frutas}")

frutas.remove("banana")  # Remove a PRIMEIRA ocorrência
print(f"Depois: {frutas}")  # ['maçã', 'laranja', 'banana']
```

#### pop() - Remove por Posição
```python
frutas = ["maçã", "banana", "laranja"]
print(f"Antes: {frutas}")

# Remove o último elemento
fruta_removida = frutas.pop()
print(f"Removeu: {fruta_removida}")  # Removeu: laranja
print(f"Lista agora: {frutas}")      # ['maçã', 'banana']

# Remove elemento específico por posição
frutas = ["maçã", "banana", "laranja"]
fruta_removida = frutas.pop(0)  # Remove o primeiro (posição 0)
print(f"Removeu: {fruta_removida}")  # Removeu: maçã
print(f"Lista agora: {frutas}")      # ['banana', 'laranja']
```

## Exemplos Práticos Detalhados

### Exemplo 1: Sistema de Tarefas
```python
# Criando uma lista de tarefas
tarefas = []

# Adicionando tarefas
tarefas.append("Estudar Python")
tarefas.append("Fazer exercícios")
tarefas.append("Ler um livro")

print("=== LISTA DE TAREFAS ===")
for i in range(len(tarefas)):
    print(f"{i + 1}. {tarefas[i]}")

# Marcando uma tarefa como concluída (removendo)
print(f"\nConcluí: {tarefas.pop(0)}")

print("\n=== TAREFAS RESTANTES ===")
for i in range(len(tarefas)):
    print(f"{i + 1}. {tarefas[i]}")
```

### Exemplo 2: Controle de Estoque
```python
# Lista de produtos em estoque
estoque = ["notebook", "mouse", "teclado", "monitor"]

print("=== ESTOQUE ATUAL ===")
print(f"Temos {len(estoque)} produtos:")
for produto in estoque:
    print(f"- {produto}")

# Cliente quer comprar um mouse
produto_desejado = "mouse"
if produto_desejado in estoque:
    estoque.remove(produto_desejado)
    print(f"\n✅ {produto_desejado} vendido!")
else:
    print(f"\n❌ {produto_desejado} não está em estoque")

# Chegou um novo produto
novo_produto = "webcam"
estoque.append(novo_produto)
print(f"📦 {novo_produto} adicionado ao estoque")

print("\n=== ESTOQUE ATUALIZADO ===")
for produto in estoque:
    print(f"- {produto}")
```

### Exemplo 3: Notas de Alunos
```python
# Lista de notas
notas = [8.5, 7.0, 9.2, 6.8, 8.0]

print("=== ANÁLISE DAS NOTAS ===")
print(f"Notas: {notas}")
print(f"Quantidade de provas: {len(notas)}")

# Calculando a média
soma_notas = 0
for nota in notas:
    soma_notas += nota

media = soma_notas / len(notas)
print(f"Média: {media:.1f}")

# Encontrando maior e menor nota
maior_nota = notas[0]
menor_nota = notas[0]

for nota in notas:
    if nota > maior_nota:
        maior_nota = nota
    if nota < menor_nota:
        menor_nota = nota

print(f"Maior nota: {maior_nota}")
print(f"Menor nota: {menor_nota}")

# Verificando aprovação
if media >= 7.0:
    print("🎉 APROVADO!")
else:
    print("📚 Precisa estudar mais")
```

## Exercícios Práticos

### Exercício 1: Lista de Filmes Favoritos
```python
# Crie uma lista com seus 5 filmes favoritos
filmes = []  # Complete aqui

# Adicione mais um filme à lista
# Seu código aqui

# Remova o primeiro filme da lista
# Seu código aqui

# Verifique se "Titanic" está na sua lista
# Seu código aqui

# Imprima quantos filmes você tem na lista
# Seu código aqui
```

### Exercício 2: Carrinho de Compras
```python
def gerenciar_carrinho():
    carrinho = []
    
    while True:
        print("\n=== CARRINHO DE COMPRAS ===")
        print("1. Adicionar produto")
        print("2. Remover produto") 
        print("3. Ver carrinho")
        print("4. Sair")
        
        opcao = input("Escolha uma opção: ")
        
        if opcao == "1":
            # Adicionar produto
            # Seu código aqui
            pass
        elif opcao == "2":
            # Remover produto
            # Seu código aqui
            pass
        elif opcao == "3":
            # Mostrar carrinho
            # Seu código aqui
            pass
        elif opcao == "4":
            print("Obrigado por usar nosso sistema!")
            break

# Descomente para testar:
# gerenciar_carrinho()
```

### Exercício 3: Organizador de Números
```python
def organizar_numeros():
    numeros = [15, 3, 8, 12, 7, 1, 9]
    
    print(f"Lista original: {numeros}")
    
    # 1. Encontre o maior número
    # Seu código aqui
    
    # 2. Encontre o menor número  
    # Seu código aqui
    
    # 3. Calcule a soma de todos os números
    # Seu código aqui
    
    # 4. Conte quantos números são maiores que 10
    # Seu código aqui
    
    # 5. Crie uma nova lista só com números pares
    # Seu código aqui

# Teste sua função:
organizar_numeros()
```

## Dicas Importantes

1. **Listas começam no índice 0**, não 1!
   ```python
   lista = ["primeiro", "segundo", "terceiro"]
   #        [    0    ] [   1    ] [    2    ]
   ```

2. **Cuidado com índices que não existem**:
   ```python
   lista = ["a", "b", "c"]
   # print(lista[5])  # ❌ Erro! Índice não existe
   ```

3. **Use nomes descritivos para suas listas**:
   ```python
   # ❌ Ruim
   l = ["João", "Maria", "Pedro"]
   
   # ✅ Bom  
   nomes_alunos = ["João", "Maria", "Pedro"]
   ```

4. **Listas são mutáveis** (podem ser modificadas):
   ```python
   frutas = ["maçã", "banana"]
   frutas.append("laranja")  # Modifica a lista original
   print(frutas)  # ['maçã', 'banana', 'laranja']
   ```

---

**Próximo:** [Métodos de Listas](./2-Introducao-Dicionarios.md) 🔧
