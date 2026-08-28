# 🧠 AI Knowledge Assistant

> **RAG-based AI assistant for semantic document search, contextual Q&A and persistent knowledge management using FAISS, embeddings and Google Gemini.**

![Python](https://img.shields.io/badge/Python-3.9+-blue?style=for-the-badge&logo=python&logoColor=white)
![Gemini](https://img.shields.io/badge/Google%20Gemini-1.5%20Flash-8E75B2?style=for-the-badge&logo=google&logoColor=white)
![Gradio](https://img.shields.io/badge/Gradio-Interface-FF7C00?style=for-the-badge&logo=gradio&logoColor=white)
![FAISS](https://img.shields.io/badge/FAISS-Vector%20Search-0052CC?style=for-the-badge)
![RAG](https://img.shields.io/badge/RAG-Retrieval%20Augmented%20Generation-6C63FF?style=for-the-badge)
![Google Drive](https://img.shields.io/badge/Google%20Drive-Persistence-4285F4?style=for-the-badge&logo=googledrive&logoColor=white)

---

## 💼 Sobre o Projeto

O **AI Knowledge Assistant** é uma aplicação de Inteligência Artificial Generativa desenvolvida para transformar documentos em uma **base de conhecimento pesquisável, persistente e consultável em linguagem natural**.

A solução utiliza uma arquitetura de **Retrieval-Augmented Generation (RAG)** para combinar recuperação semântica de informações com geração de respostas contextualizadas.

O fluxo integra:

- processamento de documentos;
- divisão do conteúdo em chunks;
- geração de embeddings;
- indexação vetorial com FAISS;
- busca por similaridade;
- recuperação de contexto;
- geração de respostas com Google Gemini.

O projeto foi desenvolvido no **Challenge ONE AI Tech Builder**, integrante do programa **Oracle Next Education (ONE) / Alura**.

---

## 🎯 Objetivo

Desenvolver um assistente capaz de reduzir o esforço necessário para localizar e interpretar informações distribuídas em documentos extensos.

A proposta é permitir que usuários consultem documentos pessoais, técnicos ou corporativos utilizando linguagem natural e recebam respostas baseadas no conteúdo efetivamente disponível na base de conhecimento.

---

## 💡 Problema

Empresas, profissionais e estudantes acumulam grandes volumes de informação em arquivos como PDFs, documentos de texto, manuais, relatórios e materiais técnicos.

O problema não está apenas em armazenar esses documentos, mas em **recuperar rapidamente informações relevantes dentro deles**.

Buscas tradicionais por palavras-chave podem falhar quando:

- o usuário não conhece o termo exato utilizado no documento;
- a informação está distribuída em diferentes trechos;
- o conteúdo precisa ser interpretado em contexto;
- vários documentos precisam ser consultados ao mesmo tempo.

O AI Knowledge Assistant utiliza busca semântica e RAG para tornar esse conhecimento mais acessível.

---

## 🧠 Como a Solução Funciona

```text
Documentos
PDF | DOCX | TXT | MD
        ↓
Extração de Texto
        ↓
Divisão em Chunks
        ↓
Sentence Transformers
        ↓
Embeddings
        ↓
FAISS
Indexação Vetorial
        ↓
Pergunta do Usuário
        ↓
Embedding da Consulta
        ↓
Busca por Similaridade
        ↓
Contexto Recuperado
        ↓
Google Gemini
        ↓
Resposta Contextualizada
```

A aplicação separa o processo em duas etapas principais:

**Indexação**
- processamento dos documentos;
- criação de chunks;
- geração dos embeddings;
- armazenamento no índice vetorial.

**Consulta**
- transformação da pergunta em embedding;
- recuperação dos trechos semanticamente mais relevantes;
- envio do contexto recuperado ao modelo de linguagem;
- geração da resposta final.

---

## ✨ Principais Funcionalidades

### 📂 Gestão de Documentos

- importação automática de documentos armazenados no Google Drive;
- upload manual de novos arquivos;
- suporte a PDF, DOCX, TXT e Markdown;
- criação e atualização de bases documentais.

### 🧠 Busca Semântica

- divisão automática dos documentos em chunks;
- geração de embeddings;
- indexação com FAISS;
- recuperação dos trechos mais relevantes para cada pergunta.

### 💬 Consulta em Linguagem Natural

O usuário pode realizar perguntas diretamente sobre a base documental.

O sistema recupera o contexto relevante e utiliza o Google Gemini para gerar respostas contextualizadas a partir das informações encontradas.

### 💾 Persistência da Base

A estrutura da base pode ser armazenada no Google Drive, preservando:

- documentos;
- chunks;
- metadados;
- índice FAISS.

Isso permite reutilizar a base entre diferentes sessões no Google Colab sem reconstruir todo o pipeline.

### 📤 Recursos Adicionais

- exportação da conversa em `.txt`;
- limpeza do histórico;
- exemplos de perguntas;
- interface interativa em Gradio;
- seleção de diferentes bases documentais.

---

## 🏗️ Arquitetura da Solução

```text
                   ┌─────────────────────┐
                   │     Documentos      │
                   │ PDF DOCX TXT MD     │
                   └──────────┬──────────┘
                              ↓
                   ┌─────────────────────┐
                   │  Extração de Texto  │
                   └──────────┬──────────┘
                              ↓
                   ┌─────────────────────┐
                   │       Chunks        │
                   └──────────┬──────────┘
                              ↓
                   ┌─────────────────────┐
                   │     Embeddings      │
                   │ Sentence Transformers│
                   └──────────┬──────────┘
                              ↓
                   ┌─────────────────────┐
                   │        FAISS        │
                   │   Vector Search     │
                   └──────────┬──────────┘
                              ↑
                              │
Pergunta → Embedding → Busca por Similaridade
                              │
                              ↓
                   ┌─────────────────────┐
                   │ Contexto Recuperado │
                   └──────────┬──────────┘
                              ↓
                   ┌─────────────────────┐
                   │    Google Gemini    │
                   └──────────┬──────────┘
                              ↓
                   ┌─────────────────────┐
                   │      Resposta       │
                   └─────────────────────┘
```

---

## 🛠️ Tecnologias Utilizadas

| Tecnologia | Aplicação |
|---|---|
| **Python** | Desenvolvimento da solução |
| **Google Gemini** | Geração das respostas |
| **Sentence Transformers** | Geração de embeddings |
| **FAISS** | Indexação e busca vetorial |
| **Gradio** | Interface web interativa |
| **Google Colab** | Ambiente de desenvolvimento e execução |
| **Google Drive** | Persistência dos documentos e índices |
| **PyPDF / PyPDF2** | Extração de conteúdo de PDFs |
| **python-docx** | Processamento de documentos DOCX |

---

## 📚 Base de Conhecimento de Demonstração

Para demonstrar o funcionamento do projeto, foi utilizada uma base documental com conteúdos relacionados a:

- Inteligência Artificial;
- Governança de IA;
- Análise de Dados.

Entre os documentos utilizados estão:

- **Governança de IA no Setor Público**
- **Manual de Inteligência Artificial**
- **Inteligência Artificial: Avanços e Tendências**
- **Análise de Dados: Da Teoria à Prática**

A arquitetura permite substituir ou ampliar essa base com outros documentos.

---

## 📸 Demonstração da Aplicação

A interface foi desenvolvida com **Gradio** e executada em ambiente Google Colab.

Como a aplicação utiliza uma instância temporária do Gradio, o endereço público gerado durante a execução não permanece disponível após o encerramento da sessão.

### Interface principal

A interface permite selecionar uma base documental, adicionar documentos e realizar consultas em linguagem natural.

![Interface principal do AI Knowledge Assistant](docs/prints/Alura-Agente-Imagem-do-Agente.png)

### Exemplo de consulta e resposta

O exemplo abaixo demonstra uma consulta realizada sobre a base documental e a resposta contextualizada gerada pelo assistente.

![Exemplo de consulta ao AI Knowledge Assistant](docs/prints/Alura-Agente-Imagem-Pergunta-Respondida.png)

---

## 💾 Persistência da Base de Conhecimento

A solução utiliza o Google Drive para armazenar os artefatos necessários à reutilização da base:

```text
Google Drive/
│
├── Agente_Alura_Documentos/
│   ├── documento_01.pdf
│   ├── documento_02.docx
│   └── documento_03.txt
│
└── alura_agente_base/
    ├── chunks.pkl
    ├── metadados.json
    ├── indice.faiss
    └── arquivos/
```

Essa abordagem evita a reconstrução completa da base sempre que uma nova sessão do Colab é iniciada.

---

## 📁 Estrutura do Repositório

```text
Challenge-ONE-AI-Tech-Builder-AI-Knowledge-Assitant/
│
├── docs/
│   └── prints/
│
├── Challenge_Alura_Agente.py
│
├── Analise-de-Dados-da-Teoria-a-Prática.pdf
├── Inteligencia-Artificial-Avanços-e-Tendências.pdf
├── Manual-de-Inteligencia-Artificial.pdf
├── Recomendações-de-Governança-Uso-da-IA-no-Poder-Público.pdf
│
└── README.md
```

---

## 🔐 Segurança

Credenciais e chaves de API não devem ser armazenadas diretamente no código nem versionadas no GitHub.

Para executar a aplicação, as credenciais necessárias devem ser configuradas utilizando mecanismos apropriados de gerenciamento de secrets do ambiente.

---

## 💡 Competências Demonstradas

O projeto aplica conhecimentos e práticas relacionados a:

- Generative AI;
- Retrieval-Augmented Generation (RAG);
- Large Language Models;
- semantic search;
- embeddings;
- vector search;
- FAISS;
- document processing;
- NLP;
- knowledge management;
- prompt engineering;
- Python;
- Gradio;
- Google Gemini;
- persistência de dados;
- arquitetura de aplicações de IA.

---

## 🗺️ Roadmap

Possíveis evoluções futuras incluem:

- Agentic RAG;
- orquestração de fluxos com LangGraph;
- busca híbrida semântica + palavras-chave;
- reranking;
- avaliação automática da qualidade das respostas;
- observabilidade do pipeline RAG;
- ampliação dos mecanismos de citação e rastreabilidade;
- containerização com Docker;
- API REST;
- deploy persistente em Cloud;
- autenticação e controle de acesso.

---

## 🎓 Contexto Acadêmico

Projeto desenvolvido no **Challenge ONE AI Tech Builder**, integrante do programa **Oracle Next Education (ONE) / Alura**.

O desafio teve como objetivo aplicar conceitos de Inteligência Artificial na construção de uma solução capaz de processar documentos e permitir consultas utilizando linguagem natural.

---

## 👤 Autor

**Marcus Guedes**

Marketing • Gestão de Projetos • Data Analytics • Inteligência Artificial aplicada a negócios

- GitHub: [MCLG1661](https://github.com/MCLG1661)
- LinkedIn: [Marcus Guedes](https://www.linkedin.com/in/marcusguedes/)

---

⭐ Projeto de estudo e portfólio voltado à aplicação prática de **RAG, busca semântica, embeddings e Inteligência Artificial Generativa para gestão de conhecimento documental**.
