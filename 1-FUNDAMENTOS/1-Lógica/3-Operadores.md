# ⚙️ Operadores - As Ferramentas da Programação

## 🧮 O que são Operadores?

**Operadores são símbolos que fazem operações com variáveis e valores.**

É como ter uma **caixa de ferramentas** para trabalhar com dados:
- **🔧 Chave de fenda** = Operador de soma (+)
- **🔨 Martelo** = Operador de multiplicação (*)
- **✂️ Alicate** = Operador de comparação (==)

## ➕ Operadores Aritméticos

### 🧮 Para fazer contas matemáticas:

| Operador | Nome | Exemplo | Resultado |
|----------|------|---------|-----------|
| `+` | Soma | `5 + 3` | `8` |
| `-` | Subtração | `5 - 3` | `2` |
| `*` | Multiplicação | `5 * 3` | `15` |
| `/` | Divisão | `10 / 2` | `5.0` |
| `%` | Resto da divisão | `10 % 3` | `1` |
| `**` | Potência (Python) | `2 ** 3` | `8` |

### 📝 Exemplos práticos:

#### Python:
\`\`\`python
# Calculadora básica
a = 10
b = 3

soma = a + b        # 13
subtracao = a - b   # 7
multiplicacao = a * b  # 30
divisao = a / b     # 3.333...
resto = a % b       # 1 (resto de 10 ÷ 3)
potencia = a ** b   # 1000 (10³)

print(f"Soma: {soma}")
print(f"Resto: {resto}")
\`\`\`

#### C:
\`\`\`c
#include <stdio.h>
#include <math.h>  // Para pow()

int main() {
    int a = 10, b = 3;
    
    int soma = a + b;           // 13
    int subtracao = a - b;      // 7
    int multiplicacao = a * b;  // 30
    float divisao = (float)a / b;  // 3.333...
    int resto = a % b;          // 1
    double potencia = pow(a, b); // 1000
    
    printf("Soma: %d\n", soma);
    printf("Resto: %d\n", resto);
    printf("Divisão: %.2f\n", divisao);
    
    return 0;
}
\`\`\`

## 🔍 Operadores de Comparação

### 📊 Para comparar valores:

| Operador | Nome | Exemplo | Resultado |
|----------|------|---------|-----------|
| `==` | Igual a | `5 == 5` | `True` |
| `!=` | Diferente de | `5 != 3` | `True` |
| `>` | Maior que | `5 > 3` | `True` |
| `<` | Menor que | `3 < 5` | `True` |
| `>=` | Maior ou igual | `5 >= 5` | `True` |
| `<=` | Menor ou igual | `3 <= 5` | `True` |

### 🎯 Exemplo: Sistema de notas

#### Python:
\`\`\`python
nota = float(input("Digite sua nota: "))

if nota >= 7:
    print("Aprovado! 🎉")
elif nota >= 5:
    print("Recuperação 📚")
else:
    print("Reprovado 😞")

# Comparações
print(f"Nota é maior que 8? {nota > 8}")
print(f"Nota é igual a 10? {nota == 10}")
\`\`\`

#### C:
\`\`\`c
#include <stdio.h>

int main() {
    float nota;
    
    printf("Digite sua nota: ");
    scanf("%f", &nota);
    
    if (nota >= 7) {
        printf("Aprovado!\n");
    } else if (nota >= 5) {
        printf("Recuperação\n");
    } else {
        printf("Reprovado\n");
    }
    
    // Comparações (1 = true, 0 = false)
    printf("Nota é maior que 8? %d\n", nota > 8);
    printf("Nota é igual a 10? %d\n", nota == 10);
    
    return 0;
}
\`\`\`

## 🧠 Operadores Lógicos

### 🔗 Para combinar condições:

| Operador | Nome | Python | C | Exemplo |
|----------|------|--------|---|---------|
| E | AND | `and` | `&&` | `(idade >= 18) and (tem_carteira == True)` |
| OU | OR | `or` | `\|\|` | `(chuva == True) or (frio == True)` |
| NÃO | NOT | `not` | `!` | `not (esta_dormindo)` |

### 🚗 Exemplo: Pode dirigir?

#### Python:
\`\`\`python
idade = int(input("Qual sua idade? "))
tem_carteira = input("Tem carteira? (s/n): ").lower() == 's'

# Operador AND - as DUAS condições devem ser verdadeiras
pode_dirigir = (idade >= 18) and tem_carteira

if pode_dirigir:
    print("Pode dirigir! 🚗")
else:
    print("Não pode dirigir! 🚫")

# Outros exemplos
esta_chovendo = True
esta_frio = False

# Operador OR - pelo menos UMA condição deve ser verdadeira
ficar_em_casa = esta_chovendo or esta_frio
print(f"Ficar em casa? {ficar_em_casa}")

# Operador NOT - inverte o valor
sair_de_casa = not ficar_em_casa
print(f"Sair de casa? {sair_de_casa}")
\`\`\`

#### C:
\`\`\`c
#include <stdio.h>
#include <stdbool.h>

int main() {
    int idade;
    char resposta;
    bool tem_carteira;
    
    printf("Qual sua idade? ");
    scanf("%d", &idade);
    
    printf("Tem carteira? (s/n): ");
    scanf(" %c", &resposta);  // Espaço antes do %c
    tem_carteira = (resposta == 's' || resposta == 'S');
    
    // Operador AND (&&)
    bool pode_dirigir = (idade >= 18) && tem_carteira;
    
    if (pode_dirigir) {
        printf("Pode dirigir!\n");
    } else {
        printf("Não pode dirigir!\n");
    }
    
    return 0;
}
\`\`\`

## 📐 Precedência de Operadores

### 🎯 Ordem de execução (do primeiro para o último):

1. **( )** - Parênteses
2. **\*\*** - Potência (Python)
3. **\*, /, %** - Multiplicação, Divisão, Resto
4. **+, -** - Soma, Subtração
5. **<, <=, >, >=** - Comparações
6. **==, !=** - Igualdade
7. **and/&&** - E lógico
8. **or/||** - OU lógico

### 📝 Exemplos:

\`\`\`python
# Python
resultado = 2 + 3 * 4    # = 2 + 12 = 14 (não 20!)
resultado = (2 + 3) * 4  # = 5 * 4 = 20

# Comparação complexa
idade = 20
tem_dinheiro = True
resultado = idade >= 18 and tem_dinheiro  # True
\`\`\`

## 🎮 Exercícios Práticos

### 📝 Exercício 1: Calculadora Completa
Crie uma calculadora que:
- Peça dois números
- Mostre soma, subtração, multiplicação e divisão
- Mostre se o primeiro é maior que o segundo

### 📝 Exercício 2: Sistema de Login
Crie um sistema que:
- Peça usuário e senha
- Usuário correto: "admin"
- Senha correta: "123456"
- Mostre se o login foi bem-sucedido

### 📝 Exercício 3: Pode Votar?
Verifique se uma pessoa pode votar:
- Idade >= 16: pode votar
- Idade >= 18: voto obrigatório
- Tem título de eleitor

### 💡 Soluções:

#### Exercício 1 - Python:
\`\`\`python
num1 = float(input("Primeiro número: "))
num2 = float(input("Segundo número: "))

print(f"Soma: {num1 + num2}")
print(f"Subtração: {num1 - num2}")
print(f"Multiplicação: {num1 * num2}")

if num2 != 0:
    print(f"Divisão: {num1 / num2}")
else:
    print("Não é possível dividir por zero!")

print(f"Primeiro é maior? {num1 > num2}")
\`\`\`

#### Exercício 2 - Python:
\`\`\`python
usuario = input("Usuário: ")
senha = input("Senha: ")

login_correto = (usuario == "admin") and (senha == "123456")

if login_correto:
    print("Login bem-sucedido! ✅")
else:
    print("Usuário ou senha incorretos! ❌")
\`\`\`

#### Exercício 3 - Python:
\`\`\`python
idade = int(input("Idade: "))
tem_titulo = input("Tem título de eleitor? (s/n): ").lower() == 's'

pode_votar = (idade >= 16) and tem_titulo
voto_obrigatorio = (idade >= 18) and tem_titulo

if voto_obrigatorio:
    print("Voto obrigatório! 🗳️")
elif pode_votar:
    print("Pode votar (facultativo) 📝")
else:
    print("Não pode votar ❌")
\`\`\`

## 🌟 Resumo

### Operadores são suas **ferramentas** para:
- **🧮 Fazer cálculos** (aritméticos)
- **🔍 Comparar valores** (comparação)
- **🧠 Combinar condições** (lógicos)

### 💡 Dicas importantes:
- Use **parênteses** para deixar claro a ordem
- **Teste sempre** suas condições
- **Cuidado** com divisão por zero
- **== é comparação**, = é atribuição

---

**➡️ Próximo passo**: [Tipos de Dados](../2-Tipos-de-Dados/1-Números.md)
