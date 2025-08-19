# 📝 Projeto: Lista de Tarefas

## 🎯 Objetivo do Projeto

Criar um programa para gerenciar suas tarefas diárias! Você poderá adicionar, remover, marcar como concluída e ver todas as suas tarefas.

## 🎯 Funcionalidades

✅ Adicionar nova tarefa
✅ Ver todas as tarefas
✅ Marcar tarefa como concluída
✅ Remover tarefa
✅ Salvar tarefas em arquivo

## 🛠️ Versão Básica

```python
# Lista para guardar as tarefas
tarefas = []

def mostrar_menu():
    print("\n📝 LISTA DE TAREFAS")
    print("-" * 30)
    print("1. ➕ Adicionar tarefa")
    print("2. 📋 Ver tarefas")
    print("3. ✅ Marcar como concluída")
    print("4. ❌ Remover tarefa")
    print("5. 🚪 Sair")

def adicionar_tarefa():
    tarefa = input("Digite a nova tarefa: ")
    tarefas.append({"texto": tarefa, "concluida": False})
    print(f"✅ Tarefa '{tarefa}' adicionada!")

def ver_tarefas():
    if not tarefas:
        print("📭 Nenhuma tarefa cadastrada!")
        return
    
    print("\n📋 SUAS TAREFAS:")
    for i, tarefa in enumerate(tarefas, 1):
        status = "✅" if tarefa["concluida"] else "⏳"
        print(f"{i}. {status} {tarefa['texto']}")

def marcar_concluida():
    ver_tarefas()
    if not tarefas:
        return
    
    try:
        numero = int(input("Qual tarefa foi concluída? (número): "))
        if 1 <= numero <= len(tarefas):
            tarefas[numero-1]["concluida"] = True
            print(f"🎉 Tarefa {numero} marcada como concluída!")
        else:
            print("❌ Número inválido!")
    except ValueError:
        print("❌ Digite um número válido!")

def remover_tarefa():
    ver_tarefas()
    if not tarefas:
        return
    
    try:
        numero = int(input("Qual tarefa remover? (número): "))
        if 1 <= numero <= len(tarefas):
            tarefa_removida = tarefas.pop(numero-1)
            print(f"🗑️ Tarefa '{tarefa_removida['texto']}' removida!")
        else:
            print("❌ Número inválido!")
    except ValueError:
        print("❌ Digite um número válido!")

# Loop principal
while True:
    mostrar_menu()
    
    opcao = input("\nEscolha uma opção (1-5): ")
    
    if opcao == "1":
        adicionar_tarefa()
    elif opcao == "2":
        ver_tarefas()
    elif opcao == "3":
        marcar_concluida()
    elif opcao == "4":
        remover_tarefa()
    elif opcao == "5":
        print("👋 Até logo!")
        break
    else:
        print("❌ Opção inválida!")
    
    input("\nPressione Enter para continuar...")
```

## 🔧 Versão com Arquivo

Vamos salvar as tarefas em um arquivo para não perder quando fechar o programa:

```python
import json

def carregar_tarefas():
    """Carrega tarefas do arquivo"""
    try:
        with open("tarefas.json", "r", encoding="utf-8") as arquivo:
            return json.load(arquivo)
    except FileNotFoundError:
        return []  # Se não existe arquivo, lista vazia

def salvar_tarefas(tarefas):
    """Salva tarefas no arquivo"""
    with open("tarefas.json", "w", encoding="utf-8") as arquivo:
        json.dump(tarefas, arquivo, indent=2, ensure_ascii=False)

def adicionar_tarefa(tarefas):
    tarefa = input("Digite a nova tarefa: ")
    tarefas.append({"texto": tarefa, "concluida": False})
    salvar_tarefas(tarefas)  # Salva após adicionar
    print(f"✅ Tarefa '{tarefa}' adicionada!")

# No início do programa
tarefas = carregar_tarefas()

# Resto do código igual, mas sempre chame salvar_tarefas() 
# após modificar a lista
```

## 🎯 Como Funciona

### 1. **Estrutura da Tarefa**
```python
tarefa = {
    "texto": "Estudar Python",
    "concluida": False
}
```
- Cada tarefa é um dicionário com texto e status

### 2. **Lista de Tarefas**
```python
tarefas = [
    {"texto": "Estudar Python", "concluida": False},
    {"texto": "Fazer exercícios", "concluida": True}
]
```

### 3. **Salvando em JSON**
```python
import json

# Salvar
with open("tarefas.json", "w") as arquivo:
    json.dump(tarefas, arquivo)

# Carregar
with open("tarefas.json", "r") as arquivo:
    tarefas = json.load(arquivo)
```

## 🏋️ Exercícios para Praticar

1. **Fácil**: Adicione data de criação para cada tarefa
2. **Médio**: Adicione prioridade (alta, média, baixa)
3. **Difícil**: Adicione categorias (trabalho, pessoal, estudos)

## 💡 O que Aprendemos

✅ Listas de dicionários para dados estruturados
✅ Manipulação de arquivos JSON
✅ Funções para organizar código
✅ Loops e condicionais em aplicação real
✅ Tratamento de erros com try/except
