# 📁 Manipulação de Arquivos em Python

## 🎯 Por que Trabalhar com Arquivos?

Imagine que você criou um programa incrível, mas toda vez que fecha ele, perde todos os dados! 😱 
É aí que entram os **arquivos** - eles são como gavetas digitais onde guardamos informações permanentemente.

## 📖 Lendo Arquivos

### O Básico - open() e read()
```python
# Abrindo e lendo um arquivo
arquivo = open("meu_arquivo.txt", "r", encoding="utf-8")
conteudo = arquivo.read()
print(conteudo)
arquivo.close()  # SEMPRE feche o arquivo!
```

### Método Seguro - with open()
```python
# Método recomendado (fecha automaticamente)
with open("meu_arquivo.txt", "r", encoding="utf-8") as arquivo:
    conteudo = arquivo.read()
    print(conteudo)
# Arquivo é fechado automaticamente aqui!
```

### Lendo Linha por Linha
```python
# Lendo linha por linha
with open("lista_compras.txt", "r", encoding="utf-8") as arquivo:
    for linha in arquivo:
        print(f"Item: {linha.strip()}")  # strip() remove quebras de linha
```

## ✏️ Escrevendo Arquivos

### Criando/Sobrescrevendo Arquivo
```python
# Modo "w" - write (sobrescreve o arquivo)
with open("diario.txt", "w", encoding="utf-8") as arquivo:
    arquivo.write("Hoje foi um dia incrível!\n")
    arquivo.write("Aprendi sobre arquivos em Python.\n")
```

### Adicionando ao Arquivo
```python
# Modo "a" - append (adiciona ao final)
with open("diario.txt", "a", encoding="utf-8") as arquivo:
    arquivo.write("Esta linha foi adicionada depois!\n")
```

## 🎯 Exemplo Prático: Lista de Tarefas

```python
def lista_tarefas():
    arquivo_tarefas = "tarefas.txt"
    
    def carregar_tarefas():
        try:
            with open(arquivo_tarefas, "r", encoding="utf-8") as arquivo:
                tarefas = []
                for linha in arquivo:
                    tarefas.append(linha.strip())
                return tarefas
        except FileNotFoundError:
            return []  # Se arquivo não existe, retorna lista vazia
    
    def salvar_tarefas(tarefas):
        with open(arquivo_tarefas, "w", encoding="utf-8") as arquivo:
            for tarefa in tarefas:
                arquivo.write(tarefa + "\n")
    
    def mostrar_menu():
        print("\n=== LISTA DE TAREFAS ===")
        print("1. Ver tarefas")
        print("2. Adicionar tarefa")
        print("3. Remover tarefa")
        print("4. Sair")
    
    tarefas = carregar_tarefas()
    
    while True:
        mostrar_menu()
        opcao = input("Escolha uma opção: ")
        
        if opcao == "1":
            if tarefas:
                print("\n📋 SUAS TAREFAS:")
                for i, tarefa in enumerate(tarefas, 1):
                    print(f"{i}. {tarefa}")
            else:
                print("📭 Nenhuma tarefa encontrada!")
                
        elif opcao == "2":
            nova_tarefa = input("Digite a nova tarefa: ")
            tarefas.append(nova_tarefa)
            salvar_tarefas(tarefas)
            print("✅ Tarefa adicionada!")
            
        elif opcao == "3":
            if tarefas:
                print("\n📋 TAREFAS ATUAIS:")
                for i, tarefa in enumerate(tarefas, 1):
                    print(f"{i}. {tarefa}")
                
                try:
                    indice = int(input("Número da tarefa para remover: ")) - 1
                    if 0 <= indice < len(tarefas):
                        tarefa_removida = tarefas.pop(indice)
                        salvar_tarefas(tarefas)
                        print(f"✅ Tarefa '{tarefa_removida}' removida!")
                    else:
                        print("❌ Número inválido!")
                except ValueError:
                    print("❌ Digite um número válido!")
            else:
                print("📭 Nenhuma tarefa para remover!")
                
        elif opcao == "4":
            print("👋 Até logo!")
            break
        else:
            print("❌ Opção inválida!")

# Executar o programa
lista_tarefas()
```

## 🛡️ Tratamento de Erros com Arquivos

```python
def ler_arquivo_seguro(nome_arquivo):
    try:
        with open(nome_arquivo, "r", encoding="utf-8") as arquivo:
            return arquivo.read()
    except FileNotFoundError:
        print(f"❌ Arquivo '{nome_arquivo}' não encontrado!")
        return None
    except PermissionError:
        print(f"❌ Sem permissão para ler '{nome_arquivo}'!")
        return None
    except Exception as e:
        print(f"❌ Erro inesperado: {e}")
        return None

# Uso seguro
conteudo = ler_arquivo_seguro("dados.txt")
if conteudo:
    print(conteudo)
```

## 📊 Trabalhando com CSV (Dados Tabulares)

```python
def trabalhar_com_csv():
    # Criando um arquivo CSV
    dados_vendas = [
        "Produto,Quantidade,Preço",
        "Notebook,5,2500.00",
        "Mouse,20,45.00",
        "Teclado,15,120.00"
    ]
    
    # Salvando CSV
    with open("vendas.csv", "w", encoding="utf-8") as arquivo:
        for linha in dados_vendas:
            arquivo.write(linha + "\n")
    
    # Lendo e processando CSV
    print("📊 RELATÓRIO DE VENDAS:")
    with open("vendas.csv", "r", encoding="utf-8") as arquivo:
        linhas = arquivo.readlines()
        
        # Pular cabeçalho
        for linha in linhas[1:]:
            dados = linha.strip().split(",")
            produto = dados[0]
            quantidade = int(dados[1])
            preco = float(dados[2])
            total = quantidade * preco
            
            print(f"{produto}: {quantidade} unidades × R${preco:.2f} = R${total:.2f}")

trabalhar_com_csv()
```

## 💡 Dicas Importantes

1. **Sempre use encoding="utf-8"**: Para caracteres especiais funcionarem
2. **Use with open()**: Fecha o arquivo automaticamente
3. **Trate erros**: FileNotFoundError é muito comum
4. **strip()**: Remove espaços e quebras de linha desnecessárias
