# 🖼️ Interface Gráfica - Introdução

## 🎯 O que são Interfaces Gráficas?

Em vez de usar apenas texto no terminal, você pode criar **janelas, botões e menus** que os usuários podem clicar! É como sair da era do MS-DOS para o Windows.

## 🪟 Exemplo com Tkinter

```python
import tkinter as tk
from tkinter import messagebox

def cumprimentar():
    nome = entrada_nome.get()
    messagebox.showinfo("Olá!", f"Olá, {nome}! Bem-vindo ao Python!")

# Criar janela
janela = tk.Tk()
janela.title("Meu Primeiro App")
janela.geometry("300x150")

# Adicionar elementos
tk.Label(janela, text="Digite seu nome:").pack(pady=10)
entrada_nome = tk.Entry(janela)
entrada_nome.pack(pady=5)

botao = tk.Button(janela, text="Cumprimentar", command=cumprimentar)
botao.pack(pady=10)

# Executar aplicação
janela.mainloop()
```

## 🛠️ Bibliotecas Populares

- **Tkinter**: Vem com Python (básico)
- **PyQt/PySide**: Interfaces profissionais
- **Kivy**: Apps mobile e desktop
- **Streamlit**: Apps web interativos

## 🎓 Quer Criar Apps Visuais?

Interfaces gráficas abrem um mundo de possibilidades! Para dominar completamente, incluindo:
- Layouts e posicionamento
- Eventos e interações
- Menus e barras de ferramentas
- Gráficos e visualizações
- Apps desktop profissionais
- Distribuição de aplicações

**👉 Acesse o tutorial: [GUI em Python](https://github.com/lukas-senai/gui-python)**
