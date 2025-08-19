# 🌐 APIs e Requisições Web - Introdução

## 🎯 O que são APIs?

APIs são como **garçons em um restaurante**! Você (seu programa) faz um pedido ao garçom (API), ele vai na cozinha (servidor) buscar sua comida (dados) e traz de volta para você.

## 🔗 Exemplo Básico

```python
import requests

# Fazendo uma requisição para uma API pública
resposta = requests.get("https://api.github.com/users/octocat")
dados = resposta.json()

print(f"Nome: {dados['name']}")
print(f"Seguidores: {dados['followers']}")
```

## 🌟 APIs Populares para Praticar

- **JSONPlaceholder**: API fake para testes
- **GitHub API**: Dados de repositórios e usuários
- **OpenWeatherMap**: Dados meteorológicos
- **ViaCEP**: Consulta de CEPs brasileiros

## 🎓 Quer Dominar APIs?

APIs são fundamentais no desenvolvimento moderno! Para aprender completamente, incluindo:
- Métodos HTTP (GET, POST, PUT, DELETE)
- Autenticação e tokens
- Tratamento de respostas e erros
- Criando suas próprias APIs
- Integração com bancos de dados
- Projetos práticos com APIs reais

**👉 Acesse o tutorial: [Implementando uma API](https://github.com/lukas-senai/implementando-api)**
