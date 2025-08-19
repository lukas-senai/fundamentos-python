# ✨ Boas Práticas: Código Limpo

## 🎯 Por que Código Limpo Importa?

Imagine que você escreveu um código hoje e precisa modificá-lo daqui a 6 meses. Se ele estiver bagunçado, será como tentar encontrar uma agulha no palheiro! 🔍

## 📝 Nomes Significativos

### ❌ Ruim
```python
# Nomes confusos
a = 25
b = 30
c = a + b

def calc(x, y):
    return x * y * 0.1

lista = ["João", "Maria", "Pedro"]
```

### ✅ Bom
```python
# Nomes claros e descritivos
idade_joao = 25
idade_maria = 30
soma_idades = idade_joao + idade_maria

def calcular_desconto(preco, quantidade):
    """Calcula desconto de 10% baseado no preço e quantidade"""
    return preco * quantidade * 0.1

nomes_funcionarios = ["João", "Maria", "Pedro"]
```

## 🏗️ Funções Pequenas e Focadas

### ❌ Função Gigante
```python
def processar_pedido(pedido):
    # Validar dados (20 linhas)
    if not pedido["nome"]:
        print("Nome obrigatório")
        return False
    if not pedido["email"]:
        print("Email obrigatório")
        return False
    # ... mais validações
    
    # Calcular preço (15 linhas)
    preco_total = 0
    for item in pedido["itens"]:
        preco_total += item["preco"] * item["quantidade"]
    # ... mais cálculos
    
    # Salvar no banco (10 linhas)
    # ... código de banco
    
    # Enviar email (12 linhas)
    # ... código de email
    
    return True
```

### ✅ Funções Pequenas
```python
def validar_pedido(pedido):
    """Valida se o pedido tem todos os dados necessários"""
    if not pedido.get("nome"):
        return False, "Nome é obrigatório"
    if not pedido.get("email"):
        return False, "Email é obrigatório"
    return True, "Pedido válido"

def calcular_total_pedido(itens):
    """Calcula o valor total do pedido"""
    total = 0
    for item in itens:
        total += item["preco"] * item["quantidade"]
    return total

def salvar_pedido_banco(pedido):
    """Salva o pedido no banco de dados"""
    # Código específico para salvar
    pass

def enviar_email_confirmacao(email, pedido):
    """Envia email de confirmação do pedido"""
    # Código específico para email
    pass

def processar_pedido(pedido):
    """Processa um pedido completo"""
    # Validar
    valido, mensagem = validar_pedido(pedido)
    if not valido:
        print(f"Erro: {mensagem}")
        return False
    
    # Calcular total
    pedido["total"] = calcular_total_pedido(pedido["itens"])
    
    # Salvar
    salvar_pedido_banco(pedido)
    
    # Notificar
    enviar_email_confirmacao(pedido["email"], pedido)
    
    return True
```

## 📖 Comentários Úteis

### ❌ Comentários Inúteis
```python
# Incrementa i em 1
i += 1

# Loop que percorre a lista
for item in lista:
    print(item)

# Função que soma dois números
def somar(a, b):
    return a + b  # Retorna a soma
```

### ✅ Comentários Valiosos
```python
# Aplicamos desconto progressivo: 5% até 100 itens, 10% acima disso
if quantidade <= 100:
    desconto = 0.05
else:
    desconto = 0.10

def calcular_juros_compostos(principal, taxa, tempo):
    """
    Calcula juros compostos usando a fórmula: M = C(1 + i)^t
    
    Args:
        principal (float): Valor inicial do investimento
        taxa (float): Taxa de juros (ex: 0.05 para 5%)
        tempo (int): Período em anos
    
    Returns:
        float: Montante final após aplicação dos juros
    """
    return principal * (1 + taxa) ** tempo

# HACK: API externa tem bug com acentos, removemos temporariamente
nome_limpo = remover_acentos(nome_usuario)
```

## 🎨 Formatação Consistente

### ✅ Código Bem Formatado
```python
class GerenciadorTarefas:
    """Gerencia uma lista de tarefas do usuário"""
    
    def __init__(self):
        self.tarefas = []
        self.contador_id = 1
    
    def adicionar_tarefa(self, titulo, descricao=""):
        """Adiciona uma nova tarefa à lista"""
        tarefa = {
            "id": self.contador_id,
            "titulo": titulo,
            "descricao": descricao,
            "concluida": False,
            "data_criacao": datetime.now()
        }
        
        self.tarefas.append(tarefa)
        self.contador_id += 1
        
        return tarefa["id"]
    
    def marcar_concluida(self, tarefa_id):
        """Marca uma tarefa como concluída"""
        for tarefa in self.tarefas:
            if tarefa["id"] == tarefa_id:
                tarefa["concluida"] = True
                return True
        
        return False
    
    def listar_pendentes(self):
        """Retorna lista de tarefas não concluídas"""
        return [
            tarefa for tarefa in self.tarefas 
            if not tarefa["concluida"]
        ]
```

## 🛡️ Tratamento de Erros Claro

### ❌ Tratamento Genérico
```python
def dividir(a, b):
    try:
        return a / b
    except:
        return None
```

### ✅ Tratamento Específico
```python
def dividir(a, b):
    """
    Divide dois números com tratamento de erro específico
    
    Raises:
        TypeError: Se os argumentos não forem números
        ZeroDivisionError: Se o divisor for zero
    """
    if not isinstance(a, (int, float)) or not isinstance(b, (int, float)):
        raise TypeError("Argumentos devem ser números")
    
    if b == 0:
        raise ZeroDivisionError("Não é possível dividir por zero")
    
    return a / b

# Uso com tratamento específico
try:
    resultado = dividir(10, 2)
    print(f"Resultado: {resultado}")
except TypeError as e:
    print(f"Erro de tipo: {e}")
except ZeroDivisionError as e:
    print(f"Erro matemático: {e}")
```

## 📊 Constantes e Configurações

### ✅ Usando Constantes
```python
# Configurações no topo do arquivo
MAX_TENTATIVAS_LOGIN = 3
TIMEOUT_CONEXAO = 30  # segundos
TAMANHO_MAXIMO_ARQUIVO = 5 * 1024 * 1024  # 5MB

# Mensagens padronizadas
MENSAGENS = {
    "LOGIN_SUCESSO": "Login realizado com sucesso!",
    "LOGIN_ERRO": "Usuário ou senha incorretos",
    "ARQUIVO_MUITO_GRANDE": f"Arquivo deve ter no máximo {TAMANHO_MAXIMO_ARQUIVO // (1024*1024)}MB"
}

def fazer_login(usuario, senha):
    tentativas = 0
    
    while tentativas < MAX_TENTATIVAS_LOGIN:
        if validar_credenciais(usuario, senha):
            print(MENSAGENS["LOGIN_SUCESSO"])
            return True
        
        tentativas += 1
        print(f"{MENSAGENS['LOGIN_ERRO']} (Tentativa {tentativas}/{MAX_TENTATIVAS_LOGIN})")
    
    return False
```

## 🧪 Exemplo Prático: Refatoração

### ❌ Código Problemático
```python
def p(d):
    r = []
    for i in d:
        if i["t"] == "c" and i["v"] > 1000:
            x = i["v"] * 0.1
            i["d"] = x
            i["vf"] = i["v"] - x
            r.append(i)
    return r
```

### ✅ Código Refatorado
```python
def aplicar_desconto_clientes_vip(pedidos):
    """
    Aplica desconto de 10% para clientes VIP com pedidos acima de R$ 1000
    
    Args:
        pedidos (list): Lista de pedidos com tipo e valor
    
    Returns:
        list: Pedidos de clientes VIP com desconto aplicado
    """
    VALOR_MINIMO_VIP = 1000
    PERCENTUAL_DESCONTO_VIP = 0.10
    TIPO_CLIENTE_VIP = "vip"
    
    pedidos_com_desconto = []
    
    for pedido in pedidos:
        eh_cliente_vip = pedido["tipo_cliente"] == TIPO_CLIENTE_VIP
        valor_qualifica = pedido["valor"] > VALOR_MINIMO_VIP
        
        if eh_cliente_vip and valor_qualifica:
            desconto = pedido["valor"] * PERCENTUAL_DESCONTO_VIP
            
            pedido["desconto"] = desconto
            pedido["valor_final"] = pedido["valor"] - desconto
            
            pedidos_com_desconto.append(pedido)
    
    return pedidos_com_desconto
```

## 💡 Checklist de Código Limpo

### ✅ Antes de Finalizar seu Código

- [ ] **Nomes**: Variáveis e funções têm nomes claros?
- [ ] **Funções**: Cada função faz apenas uma coisa?
- [ ] **Tamanho**: Funções têm menos de 20 linhas?
- [ ] **Comentários**: Explicam o "porquê", não o "como"?
- [ ] **Formatação**: Código está bem indentado e organizado?
- [ ] **Erros**: Tratamento de erro é específico e útil?
- [ ] **Constantes**: Números mágicos foram substituídos por constantes?
- [ ] **Duplicação**: Não há código repetido?

## 🎯 Benefícios do Código Limpo

✅ **Manutenção mais fácil**: Mudanças rápidas e seguras
✅ **Menos bugs**: Código claro = menos erros
✅ **Trabalho em equipe**: Outros programadores entendem seu código
✅ **Produtividade**: Desenvolvimento mais rápido a longo prazo
✅ **Profissionalismo**: Demonstra qualidade e cuidado
