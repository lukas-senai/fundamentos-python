# 🧮 Projeto: Calculadora Completa

## 🎯 Objetivo do Projeto

Vamos criar uma calculadora que funciona no terminal, aplicando tudo que aprendemos: funções, loops, condicionais, tratamento de erros e muito mais!

## 📋 Funcionalidades

✅ Operações básicas (+, -, *, /)
✅ Histórico de cálculos
✅ Salvar histórico em arquivo
✅ Interface amigável
✅ Tratamento de erros

## 🛠️ Código Completo

```python
import os
from datetime import datetime

class Calculadora:
    def __init__(self):
        self.historico = []
        self.arquivo_historico = "historico_calculadora.txt"
        self.carregar_historico()
    
    def limpar_tela(self):
        """Limpa a tela do terminal"""
        os.system('cls' if os.name == 'nt' else 'clear')
    
    def mostrar_menu(self):
        """Exibe o menu principal"""
        print("=" * 50)
        print("🧮 CALCULADORA PYTHON")
        print("=" * 50)
        print("1. ➕ Somar")
        print("2. ➖ Subtrair") 
        print("3. ✖️  Multiplicar")
        print("4. ➗ Dividir")
        print("5. 📊 Ver histórico")
        print("6. 🗑️  Limpar histórico")
        print("7. 💾 Salvar histórico")
        print("8. 🚪 Sair")
        print("=" * 50)
    
    def obter_numeros(self):
        """Obtém dois números do usuário com validação"""
        while True:
            try:
                num1 = float(input("Digite o primeiro número: "))
                num2 = float(input("Digite o segundo número: "))
                return num1, num2
            except ValueError:
                print("❌ Por favor, digite números válidos!")
                print()
    
    def somar(self, a, b):
        """Realiza soma"""
        resultado = a + b
        operacao = f"{a} + {b} = {resultado}"
        self.adicionar_historico(operacao)
        return resultado
    
    def subtrair(self, a, b):
        """Realiza subtração"""
        resultado = a - b
        operacao = f"{a} - {b} = {resultado}"
        self.adicionar_historico(operacao)
        return resultado
    
    def multiplicar(self, a, b):
        """Realiza multiplicação"""
        resultado = a * b
        operacao = f"{a} × {b} = {resultado}"
        self.adicionar_historico(operacao)
        return resultado
    
    def dividir(self, a, b):
        """Realiza divisão com tratamento de erro"""
        if b == 0:
            print("❌ Erro: Não é possível dividir por zero!")
            return None
        
        resultado = a / b
        operacao = f"{a} ÷ {b} = {resultado}"
        self.adicionar_historico(operacao)
        return resultado
    
    def adicionar_historico(self, operacao):
        """Adiciona operação ao histórico com timestamp"""
        timestamp = datetime.now().strftime("%d/%m/%Y %H:%M:%S")
        entrada_historico = f"[{timestamp}] {operacao}"
        self.historico.append(entrada_historico)
    
    def mostrar_historico(self):
        """Exibe o histórico de cálculos"""
        if not self.historico:
            print("📭 Histórico vazio!")
            return
        
        print("\n📊 HISTÓRICO DE CÁLCULOS:")
        print("-" * 60)
        for i, calculo in enumerate(self.historico, 1):
            print(f"{i:2d}. {calculo}")
        print("-" * 60)
        print(f"Total de cálculos: {len(self.historico)}")
    
    def limpar_historico(self):
        """Limpa o histórico após confirmação"""
        if not self.historico:
            print("📭 Histórico já está vazio!")
            return
        
        confirmacao = input("⚠️  Tem certeza que deseja limpar o histórico? (s/n): ")
        if confirmacao.lower() in ['s', 'sim', 'y', 'yes']:
            self.historico.clear()
            print("✅ Histórico limpo com sucesso!")
        else:
            print("❌ Operação cancelada!")
    
    def salvar_historico(self):
        """Salva o histórico em arquivo"""
        if not self.historico:
            print("📭 Nenhum histórico para salvar!")
            return
        
        try:
            with open(self.arquivo_historico, "w", encoding="utf-8") as arquivo:
                arquivo.write("HISTÓRICO DA CALCULADORA\n")
                arquivo.write("=" * 50 + "\n\n")
                
                for calculo in self.historico:
                    arquivo.write(calculo + "\n")
                
                arquivo.write(f"\nTotal de cálculos: {len(self.historico)}\n")
                arquivo.write(f"Arquivo gerado em: {datetime.now().strftime('%d/%m/%Y %H:%M:%S')}\n")
            
            print(f"✅ Histórico salvo em '{self.arquivo_historico}'!")
            
        except Exception as e:
            print(f"❌ Erro ao salvar arquivo: {e}")
    
    def carregar_historico(self):
        """Carrega histórico do arquivo se existir"""
        try:
            with open(self.arquivo_historico, "r", encoding="utf-8") as arquivo:
                linhas = arquivo.readlines()
                
                # Procura por linhas que contêm cálculos (com timestamp)
                for linha in linhas:
                    if linha.startswith("[") and "]" in linha:
                        self.historico.append(linha.strip())
                        
        except FileNotFoundError:
            # Arquivo não existe ainda, tudo bem
            pass
        except Exception as e:
            print(f"⚠️  Aviso: Erro ao carregar histórico: {e}")
    
    def executar(self):
        """Loop principal da calculadora"""
        print("🎉 Bem-vindo à Calculadora Python!")
        
        while True:
            self.mostrar_menu()
            
            try:
                opcao = input("Escolha uma opção (1-8): ").strip()
                
                if opcao == "1":  # Somar
                    print("\n➕ SOMA")
                    num1, num2 = self.obter_numeros()
                    resultado = self.somar(num1, num2)
                    print(f"✅ Resultado: {num1} + {num2} = {resultado}")
                
                elif opcao == "2":  # Subtrair
                    print("\n➖ SUBTRAÇÃO")
                    num1, num2 = self.obter_numeros()
                    resultado = self.subtrair(num1, num2)
                    print(f"✅ Resultado: {num1} - {num2} = {resultado}")
                
                elif opcao == "3":  # Multiplicar
                    print("\n✖️ MULTIPLICAÇÃO")
                    num1, num2 = self.obter_numeros()
                    resultado = self.multiplicar(num1, num2)
                    print(f"✅ Resultado: {num1} × {num2} = {resultado}")
                
                elif opcao == "4":  # Dividir
                    print("\n➗ DIVISÃO")
                    num1, num2 = self.obter_numeros()
                    resultado = self.dividir(num1, num2)
                    if resultado is not None:
                        print(f"✅ Resultado: {num1} ÷ {num2} = {resultado}")
                
                elif opcao == "5":  # Ver histórico
                    self.mostrar_historico()
                
                elif opcao == "6":  # Limpar histórico
                    self.limpar_historico()
                
                elif opcao == "7":  # Salvar histórico
                    self.salvar_historico()
                
                elif opcao == "8":  # Sair
                    print("👋 Obrigado por usar a Calculadora Python!")
                    print("💾 Não esqueça de salvar seu histórico!")
                    break
                
                else:
                    print("❌ Opção inválida! Escolha entre 1 e 8.")
                
            except KeyboardInterrupt:
                print("\n\n👋 Programa interrompido pelo usuário!")
                break
            except Exception as e:
                print(f"❌ Erro inesperado: {e}")
            
            # Pausa para o usuário ver o resultado
            input("\n⏸️  Pressione Enter para continuar...")
            self.limpar_tela()

# Executar a calculadora
if __name__ == "__main__":
    calculadora = Calculadora()
    calculadora.executar()
```

## 🎯 Como Funciona

### 1. **Classe Calculadora**
- Organiza todo o código de forma limpa
- Mantém o histórico como atributo da classe
- Métodos específicos para cada funcionalidade

### 2. **Tratamento de Erros**
```python
# Validação de entrada
try:
    num1 = float(input("Digite o primeiro número: "))
except ValueError:
    print("❌ Por favor, digite números válidos!")

# Divisão por zero
if b == 0:
    print("❌ Erro: Não é possível dividir por zero!")
    return None
```

### 3. **Histórico Inteligente**
- Salva cada operação com data/hora
- Persiste dados em arquivo
- Carrega automaticamente na inicialização

### 4. **Interface Amigável**
- Menu claro e organizado
- Emojis para melhor visualização
- Confirmações para ações importantes

## 🏋️ Desafios Extras

1. **Adicionar mais operações**: potência, raiz quadrada, porcentagem
2. **Calculadora científica**: funções trigonométricas
3. **Interface gráfica**: usar tkinter
4. **Histórico avançado**: buscar por data, exportar para Excel

## 💡 O que Aprendemos

✅ Organização de código com classes
✅ Tratamento robusto de erros
✅ Manipulação de arquivos
✅ Formatação de data/hora
✅ Interface de usuário no terminal
✅ Validação de entrada do usuário

## ➡️ Próximo Projeto
Vamos criar um [Jogo da Adivinhação](2-Jogo-Adivinhacao.md) ainda mais divertido!
