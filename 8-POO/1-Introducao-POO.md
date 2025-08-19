# 🏗️ Programação Orientada a Objetos - Introdução

## 🎯 O que é POO?

Imagine que você está construindo um jogo. Em vez de ter variáveis soltas para cada personagem, você cria um "molde" chamado **Classe** e a partir dele cria vários **Objetos** (personagens).

## 🎮 Exemplo Simples

```python
class Personagem:
    def __init__(self, nome, vida):
        self.nome = nome
        self.vida = vida
    
    def atacar(self):
        print(f"{self.nome} está atacando!")

# Criando objetos (personagens)
heroi = Personagem("Link", 100)
vilao = Personagem("Ganondorf", 150)

heroi.atacar()  # Link está atacando!
vilao.atacar()  # Ganondorf está atacando!
```

## 🔑 Conceitos Principais

- **Classe**: O molde/receita
- **Objeto**: A coisa criada a partir do molde
- **Atributos**: Características (nome, vida)
- **Métodos**: Ações que o objeto pode fazer (atacar)

## 🎓 Quer Dominar POO?

POO é um universo imenso e poderoso! Para aprender completamente, incluindo:
- Herança e Polimorfismo
- Encapsulamento
- Métodos especiais
- Design Patterns
- Projetos práticos com classes

**👉 Acesse o tutorial: [POO em Python](https://github.com/lukas-senai/poo-python-tutorial)**
