# 📚 Dicionários em Python

## 🎯 O que são Dicionários?

Imagine que você tem uma **agenda telefônica**. Nela, cada pessoa tem um nome (chave) e um número de telefone (valor). Os dicionários em Python funcionam exatamente assim!

```python
# Como uma agenda telefônica
agenda = {
    "João": "11999887766",
    "Maria": "11888776655",
    "Pedro": "11777665544"
}
```

## 🔑 Conceitos Fundamentais

### O que é uma Chave-Valor?
- **Chave**: É como o "nome" na agenda (deve ser único)
- **Valor**: É como o "telefone" na agenda (pode se repetir)

```python
# Estrutura básica
dicionario = {
    "chave1": "valor1",
    "chave2": "valor2",
    "chave3": "valor3"
}
```

## 🛠️ Criando Dicionários

### Método 1: Criação Direta
```python
# Dicionário de idades
idades = {
    "Ana": 25,
    "Bruno": 30,
    "Carlos": 28
}

# Dicionário de notas
notas = {
    "Matemática": 8.5,
    "Português": 9.0,
    "História": 7.5
}
```

### Método 2: Dicionário Vazio
```python
# Criando vazio e adicionando depois
pessoa = {}
pessoa["nome"] = "João"
pessoa["idade"] = 25
pessoa["cidade"] = "São Paulo"

print(pessoa)  # {'nome': 'João', 'idade': 25, 'cidade': 'São Paulo'}
```

## 🔍 Acessando Valores

### Método Seguro - get()
```python
agenda = {"João": "11999887766", "Maria": "11888776655"}

# Método seguro (recomendado)
telefone_joao = agenda.get("João")
print(telefone_joao)  # 11999887766

# Se não existir, retorna None
telefone_pedro = agenda.get("Pedro")
print(telefone_pedro)  # None

# Ou define um valor padrão
telefone_pedro = agenda.get("Pedro", "Não encontrado")
print(telefone_pedro)  # Não encontrado
```

### Método Direto - []
```python
# Método direto (cuidado com erros!)
telefone_maria = agenda["Maria"]
print(telefone_maria)  # 11888776655

# CUIDADO: Isso dará erro se a chave não existir
# telefone_pedro = agenda["Pedro"]  # KeyError!
```

## ✏️ Modificando Dicionários

### Adicionando/Alterando
```python
estoque = {"maçã": 10, "banana": 15}

# Adicionando novo item
estoque["laranja"] = 20

# Alterando item existente
estoque["maçã"] = 25

print(estoque)  # {'maçã': 25, 'banana': 15, 'laranja': 20}
```

### Removendo Itens
```python
# Método 1: del
del estoque["banana"]

# Método 2: pop() - remove e retorna o valor
valor_removido = estoque.pop("laranja")
print(f"Removido: {valor_removido}")  # Removido: 20

print(estoque)  # {'maçã': 25}
```

## 🔄 Percorrendo Dicionários

### Percorrendo Chaves
```python
notas = {"Matemática": 8.5, "Português": 9.0, "História": 7.5}

print("Matérias:")
for materia in notas:
    print(f"- {materia}")
```

### Percorrendo Valores
```python
print("Notas:")
for nota in notas.values():
    print(f"- {nota}")
```

### Percorrendo Chaves e Valores
```python
print("Relatório de Notas:")
for materia, nota in notas.items():
    print(f"{materia}: {nota}")
```

## 🎯 Exemplo Prático: Sistema de Cadastro

```python
def sistema_cadastro():
    usuarios = {}
    
    while True:
        print("\n=== SISTEMA DE CADASTRO ===")
        print("1. Cadastrar usuário")
        print("2. Buscar usuário")
        print("3. Listar todos")
        print("4. Sair")
        
        opcao = input("Escolha uma opção: ")
        
        if opcao == "1":
            nome = input("Nome: ")
            email = input("Email: ")
            idade = int(input("Idade: "))
            
            usuarios[nome] = {
                "email": email,
                "idade": idade
            }
            print(f"✅ {nome} cadastrado com sucesso!")
            
        elif opcao == "2":
            nome = input("Nome para buscar: ")
            usuario = usuarios.get(nome)
            
            if usuario:
                print(f"📋 Dados de {nome}:")
                print(f"Email: {usuario['email']}")
                print(f"Idade: {usuario['idade']}")
            else:
                print("❌ Usuário não encontrado!")
                
        elif opcao == "3":
            if usuarios:
                print("\n📋 TODOS OS USUÁRIOS:")
                for nome, dados in usuarios.items():
                    print(f"Nome: {nome}")
                    print(f"Email: {dados['email']}")
                    print(f"Idade: {dados['idade']}")
                    print("-" * 20)
            else:
                print("📭 Nenhum usuário cadastrado!")
                
        elif opcao == "4":
            print("👋 Até logo!")
            break
        else:
            print("❌ Opção inválida!")

# Executar o sistema
sistema_cadastro()
```

## 💡 Métodos Úteis

```python
dados = {"a": 1, "b": 2, "c": 3}

# Obter todas as chaves
chaves = list(dados.keys())
print(chaves)  # ['a', 'b', 'c']

# Obter todos os valores
valores = list(dados.values())
print(valores)  # [1, 2, 3]

# Obter pares chave-valor
pares = list(dados.items())
print(pares)  # [('a', 1), ('b', 2), ('c', 3)]

# Verificar se chave existe
if "a" in dados:
    print("Chave 'a' existe!")

# Limpar dicionário
dados.clear()
print(dados)  # {}
```

## 🏋️ Exercícios Práticos

### Exercício 1: Contador de Palavras
```python
def contar_palavras(texto):
    palavras = texto.lower().split()
    contador = {}
    
    for palavra in palavras:
        if palavra in contador:
            contador[palavra] += 1
        else:
            contador[palavra] = 1
    
    return contador

# Teste
frase = "python é legal python é útil"
resultado = contar_palavras(frase)
print(resultado)  # {'python': 2, 'é': 2, 'legal': 1, 'útil': 1}
```

### Exercício 2: Agenda de Contatos
```python
def agenda_contatos():
    contatos = {}
    
    # Adicionar contatos
    contatos["João"] = {"telefone": "11999887766", "email": "joao@email.com"}
    contatos["Maria"] = {"telefone": "11888776655", "email": "maria@email.com"}
    
    # Buscar contato
    nome = input("Nome do contato: ")
    contato = contatos.get(nome)
    
    if contato:
        print(f"📞 {nome}: {contato['telefone']}")
        print(f"📧 Email: {contato['email']}")
    else:
        print("Contato não encontrado!")

agenda_contatos()
```

## 🎯 Dicas Importantes

1. **Chaves devem ser únicas**: Não pode ter duas chaves iguais
2. **Chaves devem ser imutáveis**: Use strings, números ou tuplas
3. **Use get() para acessar**: Evita erros se a chave não existir
4. **Dicionários são mutáveis**: Podem ser alterados após criação

## ➡️ Próximo Passo
Agora que você domina dicionários, vamos aprender sobre [Manipulação de Arquivos](../4-FUNCOES/1-Definindo-Funcoes.md)!
