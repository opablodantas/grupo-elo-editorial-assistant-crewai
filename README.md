
# 📚 Assistente Editorial Multiagente – Desafio Grupo Elo Editorial

Este projeto foi desenvolvido como parte do **Desafio Grupo Elo Editorial**, com o objetivo de criar um **Assistente Editorial Multiagente** utilizando **CrewAI** e **Gemini (Google Generative AI)**.

O sistema conecta usuários ao catálogo fictício de livros, oferecendo informações detalhadas sobre obras, locais de compra e abertura de tickets de suporte.

---

## 🎯 Objetivo

* Consultar um **catálogo de livros** em formato JSON.
* Fornecer **detalhes da obra** (título, autor, sinopse, etc.).
* Informar **onde comprar**, tanto online quanto em lojas físicas.
* Abrir **tickets simulados** de suporte (opcional, mas implementado).

---

## 🧩 Arquitetura

O projeto é baseado em **CrewAI** para orquestração de agentes e tarefas:

* **Orquestrador** → Detecta a intenção do usuário e delega ao agente correto.
* **Agente de Catálogo** → Busca informações sobre o livro.
* **Agente Comercial** → Indica pontos de venda (online ou físicos).
* **Agente de Suporte** → Abre tickets e responde dúvidas.

Ferramentas implementadas:

* `get_book_details(book_title: str)`
* `find_stores_selling_book(book_title: str, city?: str)`
* `open_support_ticket(name, email, subject, message)`

---

## ⚙️ Tecnologias Utilizadas

* **Python 3.11.5**
* [FastAPI](https://fastapi.tiangolo.com/) → API REST.
* [CrewAI](https://docs.crewai.com/) → Framework de orquestração multiagente.
* [LangChain](https://www.langchain.com/) + [Google Generative AI](https://ai.google.dev/) → LLM (Gemini).
* **FAISS** → Busca vetorial para catálogo.
* **dotenv** → Gerenciamento de variáveis de ambiente.

---

## 📂 Estrutura de Dados

* `data/mock_catalog.json` → Base fictícia de livros.
* `data/mock_tickets.json` → Armazena tickets abertos.

---

## 🚀 Como Executar

### 1. Clone o repositório

```bash
git clone https://github.com/opablodantas/grupo-elo-editorial-assistant-crewai.git
cd seu-repo
```

### 2. Crie um ambiente virtual

```bash
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows
```

### 3. Instale as dependências

```bash
pip install -r requirements.txt
```

### 4. Configure as variáveis de ambiente

Crie um arquivo `.env` na raiz do projeto:

```env
GOOGLE_API_KEY=SEU_TOKEN_FREE_AQUI
GEMINI_MODEL=gemini-1.5-flash
```

### 5. Execute o assistente

* **Modo CLI**

```bash
python assistente_editorial.py
```


## 📦 Requisitos

Arquivo `requirements.txt`:

```
fastapi == 0.115.9
uvicorn == 0.35.0
crewai == 0.28.9rc2
langchain == 0.1.20
langchain-community == 0.0.38
langchain-google-genai == 1.0.4
google-generativeai == 0.5.4
faiss-cpu == 1.12.0
python-dotenv == 1.1.0
```

---

## 📝 Exemplo de Fluxo

**Usuário:** “Quero saber sobre ‘A Abelha’.”
**Bot:** “📖 Título: A Abelha … ✍️ Autor: … 📚 Sinopse: … Deseja saber onde comprar? (sim/não)”

**Usuário:** “Em São Paulo.”
**Bot:** “🏬 Na sua cidade (São Paulo): Livraria X, Livraria Y 🌐 Online: Amazon, Submarino”

**Usuário:** “Abra um ticket sobre submissão.”
**Bot:** “🎫 Ticket aberto! ID: TCK-ABC123, status: open.”

---

## 💡 Feedback Pessoal

> "Foi um desafio muito empolgante. Tenho certeza de que meu projeto não cumpriu todos os requisitos esperados, mas essa experiência me trouxe a noção de que, por mais que eu estude, sempre haverá coisas novas para aprender na área de tecnologia. Estou acostumado a construir assistentes usando **PDF como base de dados**, mas trabalhar com **JSON** foi algo completamente diferente — e igualmente empolgante. Espero ter outras oportunidades de ser selecionado na Elo."


