# 🛡️ Try-Except - Tratamento de Erros

## O que são Erros?

### Analogia da Cozinha 👨‍🍳

Imagine que você está cozinhando e podem acontecer vários problemas:
- 🔥 O fogo pode acabar (erro de equipamento)
- 🧂 Pode faltar sal (erro de recurso)
- ⏰ Você pode queimar a comida (erro de tempo)
- 📖 A receita pode estar errada (erro de lógica)

Em programação, erros também acontecem! O **try-except** é como ter um plano B para quando algo dá errado.

```python
# Sem tratamento de erro - programa pode "quebrar"
numero = int(input("Digite um número: "))  # E se o usuário digitar "abc"?
resultado = 10 / numero                    # E se o usuário digitar 0?

# Com tratamento de erro - programa continua funcionando
try:
    numero = int(input("Digite um número: "))
    resultado = 10 / numero
    print(f"Resultado: {resultado}")
except:
    print("Ops! Algo deu errado. Tente novamente.")
```

## Anatomia do Try-Except

```python
try:
    # Código que pode dar erro
    codigo_perigoso()
except TipoDoErro:
    # O que fazer se der erro
    codigo_de_recuperacao()
else:
    # Executa se NÃO der erro
    codigo_de_sucesso()
finally:
    # Sempre executa (deu erro ou não)
    codigo_de_limpeza()
```

## Tipos Comuns de Erros

### 1. ValueError - Valor Inválido
```python
# Problema: Usuário digita texto quando esperamos número
try:
    idade = int(input("Sua idade: "))
    print(f"Você tem {idade} anos")
except ValueError:
    print("❌ Por favor, digite apenas números!")

# Exemplo prático:
def obter_idade_segura():
    while True:
        try:
            idade = int(input("Sua idade: "))
            if idade < 0:
                print("❌ Idade não pode ser negativa!")
                continue
            return idade
        except ValueError:
            print("❌ Digite apenas números!")

# idade_usuario = obter_idade_segura()
```

### 2. ZeroDivisionError - Divisão por Zero
```python
# Problema: Dividir por zero
def dividir_seguro(a, b):
    try:
        resultado = a / b
        return resultado
    except ZeroDivisionError:
        print("❌ Não é possível dividir por zero!")
        return None

# Testando:
print(dividir_seguro(10, 2))  # 5.0
print(dividir_seguro(10, 0))  # Mensagem de erro + None
```

### 3. IndexError - Índice Inválido
```python
# Problema: Acessar posição que não existe na lista
def acessar_lista_seguro(lista, posicao):
    try:
        elemento = lista[posicao]
        return elemento
    except IndexError:
        print(f"❌ Posição {posicao} não existe na lista!")
        return None

# Testando:
frutas = ["maçã", "banana", "laranja"]
print(acessar_lista_seguro(frutas, 1))   # banana
print(acessar_lista_seguro(frutas, 10))  # Mensagem de erro + None
```

### 4. KeyError - Chave Inexistente (Dicionários)
```python
# Problema: Acessar chave que não existe
def obter_info_pessoa(pessoa, chave):
    try:
        valor = pessoa[chave]
        return valor
    except KeyError:
        print(f"❌ Informação '{chave}' não encontrada!")
        return None

# Testando:
pessoa = {"nome": "João", "idade": 30}
print(obter_info_pessoa(pessoa, "nome"))      # João
print(obter_info_pessoa(pessoa, "telefone"))  # Mensagem de erro + None
```

## Múltiplos Tipos de Erro

```python
def calculadora_segura():
    try:
        num1 = float(input("Primeiro número: "))
        operacao = input("Operação (+, -, *, /): ")
        num2 = float(input("Segundo número: "))
        
        if operacao == "+":
            resultado = num1 + num2
        elif operacao == "-":
            resultado = num1 - num2
        elif operacao == "*":
            resultado = num1 * num2
        elif operacao == "/":
            resultado = num1 / num2
        else:
            print("❌ Operação inválida!")
            return
            
        print(f"Resultado: {resultado}")
        
    except ValueError:
        print("❌ Digite apenas números válidos!")
    except ZeroDivisionError:
        print("❌ Não é possível dividir por zero!")
    except Exception as e:
        print(f"❌ Erro inesperado: {e}")

# calculadora_segura()
```

## Capturando Informações do Erro

```python
def processar_arquivo(nome_arquivo):
    try:
        with open(nome_arquivo, 'r') as arquivo:
            conteudo = arquivo.read()
            return conteudo
    except FileNotFoundError as e:
        print(f"❌ Arquivo não encontrado: {nome_arquivo}")
        print(f"Detalhes do erro: {e}")
    except PermissionError as e:
        print(f"❌ Sem permissão para acessar: {nome_arquivo}")
        print(f"Detalhes do erro: {e}")
    except Exception as e:
        print(f"❌ Erro inesperado ao processar arquivo")
        print(f"Tipo do erro: {type(e).__name__}")
        print(f"Mensagem: {e}")

# processar_arquivo("arquivo_inexistente.txt")
```

## Usando Else e Finally

```python
def conectar_banco_dados():
    conexao = None
    try:
        print("🔄 Tentando conectar ao banco...")
        # Simular conexão (pode dar erro)
        import random
        if random.choice([True, False]):
            raise ConnectionError("Falha na conexão")
        
        conexao = "Conexão estabelecida"
        print("✅ Conectado com sucesso!")
        
    except ConnectionError as e:
        print(f"❌ Erro de conexão: {e}")
        return None
        
    else:
        # Só executa se NÃO deu erro
        print("🎉 Pronto para usar o banco de dados!")
        return conexao
        
    finally:
        # Sempre executa (deu erro ou não)
        print("🧹 Limpando recursos...")
        if conexao:
            print("🔌 Fechando conexão...")

# resultado = conectar_banco_dados()
```

## Exemplos Práticos Completos

### Exemplo 1: Sistema de Login Seguro
```python
def sistema_login():
    usuarios = {
        "admin": "123456",
        "user": "senha123",
        "joao": "minhasenha"
    }
    
    tentativas = 0
    max_tentativas = 3
    
    while tentativas < max_tentativas:
        try:
            print(f"\n=== LOGIN (Tentativa {tentativas + 1}/{max_tentativas}) ===")
            usuario = input("Usuário: ").strip()
            senha = input("Senha: ").strip()
            
            if not usuario or not senha:
                raise ValueError("Usuário e senha não podem estar vazios")
            
            if usuario not in usuarios:
                raise KeyError("Usuário não encontrado")
            
            if usuarios[usuario] != senha:
                raise PermissionError("Senha incorreta")
            
            print(f"✅ Bem-vindo, {usuario}!")
            return True
            
        except ValueError as e:
            print(f"❌ Erro de entrada: {e}")
        except KeyError as e:
            print(f"❌ {e}")
        except PermissionError as e:
            print(f"❌ {e}")
        except Exception as e:
            print(f"❌ Erro inesperado: {e}")
        
        tentativas += 1
    
    print("🚫 Muitas tentativas falharam. Acesso bloqueado!")
    return False

# sistema_login()
```

### Exemplo 2: Conversor de Temperatura Robusto
```python
def conversor_temperatura():
    print("=== CONVERSOR DE TEMPERATURA ===")
    print("1. Celsius para Fahrenheit")
    print("2. Fahrenheit para Celsius")
    
    try:
        opcao = int(input("Escolha uma opção (1 ou 2): "))
        
        if opcao not in [1, 2]:
            raise ValueError("Opção deve ser 1 ou 2")
        
        temperatura = float(input("Digite a temperatura: "))
        
        if opcao == 1:
            # Celsius para Fahrenheit
            resultado = (temperatura * 9/5) + 32
            print(f"{temperatura}°C = {resultado:.1f}°F")
        else:
            # Fahrenheit para Celsius
            resultado = (temperatura - 32) * 5/9
            print(f"{temperatura}°F = {resultado:.1f}°C")
            
    except ValueError as e:
        if "invalid literal" in str(e):
            print("❌ Digite apenas números!")
        else:
            print(f"❌ Erro de valor: {e}")
    except Exception as e:
        print(f"❌ Erro inesperado: {e}")

# conversor_temperatura()
```

## Exercícios Práticos

### Exercício 1: Calculadora Robusta
```python
def calculadora_robusta():
    """
    Crie uma calculadora que:
    1. Peça dois números ao usuário
    2. Peça a operação (+, -, *, /)
    3. Trate todos os possíveis erros
    4. Permita ao usuário tentar novamente se der erro
    """
    # Seu código aqui
    pass

# Teste sua calculadora:
# calculadora_robusta()
```

### Exercício 2: Validador de Email
```python
def validar_email(email):
    """
    Valide se um email é válido:
    1. Deve conter exatamente um @
    2. Deve ter texto antes e depois do @
    3. Deve ter pelo menos um ponto depois do @
    4. Trate erros de forma apropriada
    """
    try:
        # Seu código aqui
        pass
    except Exception as e:
        # Seu tratamento de erro aqui
        pass

# Teste:
# print(validar_email("joao@email.com"))     # True
# print(validar_email("email_invalido"))     # False
# print(validar_email("@email.com"))         # False
```

### Exercício 3: Leitor de Arquivo Seguro
```python
def ler_arquivo_seguro(nome_arquivo):
    """
    Leia um arquivo de forma segura:
    1. Tente abrir e ler o arquivo
    2. Trate erro se arquivo não existir
    3. Trate erro se não tiver permissão
    4. Retorne o conteúdo ou None se der erro
    """
    try:
        # Seu código aqui
        pass
    except FileNotFoundError:
        # Seu código aqui
        pass
    except PermissionError:
        # Seu código aqui
        pass
    except Exception as e:
        # Seu código aqui
        pass

# Teste:
# conteudo = ler_arquivo_seguro("teste.txt")
```

## Boas Práticas

### 1. Seja Específico com os Erros
```python
# ❌ Muito genérico
try:
    codigo_perigoso()
except:
    print("Deu erro")

# ✅ Específico e útil
try:
    codigo_perigoso()
except ValueError:
    print("Valor inválido fornecido")
except FileNotFoundError:
    print("Arquivo não encontrado")
```

### 2. Não Ignore Erros Silenciosamente
```python
# ❌ Ignora o erro (muito perigoso!)
try:
    operacao_importante()
except:
    pass  # Nunca faça isso!

# ✅ Pelo menos registre o erro
try:
    operacao_importante()
except Exception as e:
    print(f"Erro registrado: {e}")
    # Ou salve em um log
```

### 3. Use Finally para Limpeza
```python
def processar_dados():
    arquivo = None
    try:
        arquivo = open("dados.txt", "r")
        # processar dados...
    except FileNotFoundError:
        print("Arquivo não encontrado")
    finally:
        # Sempre fecha o arquivo, mesmo se der erro
        if arquivo:
            arquivo.close()
```

---
