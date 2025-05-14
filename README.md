# Azure Open AI Playground: Explorando IA Generativa 🚀

## 🌟 Visão Geral

Este repositório documenta minha jornada de aprendizado com o **Azure Open AI Playground**. Testei ajustes de **temperatura** e **top-p**, categorização de texto, geração de imagens, integração com **Blob Storage** para RAG, e chamadas de API. Aqui, compartilho aprendizados, exemplos práticos e reflexões sobre como aplicar IA em projetos reais.

## 📚 Aprendizados

O Azure Open AI Playground é um sandbox versátil para prototipar IA generativa. Meus principais aprendizados:

### 🔧 Temperatura e Top-p
- **Temperatura**: Controla a aleatoriedade do output.
  - Baixa (ex.: 0.0): Respostas precisas, ideais para código ou tarefas técnicas.
  - Alta (ex.: 1.0): Outputs criativos, perfeitos para narrativas ou brainstorming.
- **Top-p (Nucleus Sampling)**: Limita palavras por probabilidade.
  - Alto (ex.: 1.0): Mais diversidade, combina com temperatura alta.
  - Baixo (ex.: 0.3): Outputs focados, para coerência.
- **Combinações**:
  - Temperatura alta + top-p alto: Máxima criatividade.
  - Temperatura baixa + top-p baixo: Máxima precisão.
  - Padrão sugerido: Temperatura 0.65, top-p 0.3.
- Exemplo: Testei um prompt narrativo com diferentes ajustes, equilibrando criatividade e precisão.

### 📑 Categorização de Texto
- Usei **zero-shot** (sem exemplos) para categorizar textos, mas outputs às vezes foram inconsistentes. **One-shot** (com exemplos) garantiu formatação e explicações claras.
- Prompts vagos exigem iteração para corrigir erros do modelo, como formatação incorreta.

### 🎨 Geração de Imagens
- Criei imagens com prompts descritivos, mas o alto consumo de tokens exige moderação.
- Aprendi a detalhar prompts para resultados visuais mais precisos.

### 📂 Blob Storage e RAG
- Configurei **Blob Storage** para armazenar documentos e **Azure Cognitive Search** (plano S1) para indexação, suportando buscas semânticas em grandes volumes.
- Implementei **RAG** para responder perguntas baseadas em documentos, ajustando prompts para evitar referências imprecisas.
- Enfrentei erros 429 (limite de requisições), resolvidos com limites de tokens (ex.: 500).

### 🌐 Chamada de API
- Desenvolvi um loop simples para interagir com a API do Azure Open AI, usando endpoints e autenticação.
- Configurei mensagens de sistema para definir o comportamento do modelo, gerenciando cotas para evitar erros 429.

### 💰 Gestão de Custos
- O uso é cobrado por tokens, exigindo monitoramento rigoroso. Limitei respostas e priorizei prompts curtos para otimizar custos.

## 💡 Reflexões e Insights
- **Prototipagem Ágil**: O Playground é um laboratório para testar ideias sem código, acelerando o desenvolvimento de conceitos antes da implementação via API.
- **Prompt Engineering**: Escrever prompts claros com one-shot é como otimizar queries SQL. Ajustes de temperatura/top-p são cruciais para resultados precisos.
- **Potencial do RAG**: Integrar Blob Storage com RAG é ideal para chatbots baseados em documentos, mas exige prompts refinados e gestão de cotas.
- **Custo Estratégico**: Testes focados e limites de tokens maximizam o aprendizado sem gastos excessivos.
- **Rumo à API**: O Playground me preparou para usar a API em projetos escaláveis, como automações ou análise de dados.

## 🚀 Como Experimentar

Quer testar o Playground? Siga este guia técnico:

1. **Pré-requisitos**:
   - Crie uma conta no [Microsoft Azure](https://azure.microsoft.com/).
   - Configure um recurso do Azure Open AI no portal.

2. **Passos**:
   - Acesse o [Azure AI Studio](https://ai.azure.com/) e vá ao Playground.
   - Escolha um modelo (ex.: GPT-4o Mini).
   - Teste os seguintes prompts:
     - **Narrativo**: "Escreva uma história curta sobre uma IA que ganha consciência em um laboratório." (temperatura: 0.8, top-p: 0.9)
     - **Categorização**: "Categorize o texto: 'Startup lança app de aprendizado por IA.' Inclua motivo." (temperatura: 0.3, top-p: 1.0)
     - **Imagem**: "Estação espacial orbitando um planeta alienígena com auroras coloridas." (use com moderação)
     - **RAG**: "Quais são as cláusulas principais de um relatório em um PDF corporativo?" (configure Blob Storage com PDFs)
     - **API**: "Explique como autenticar uma API REST em Python." (teste via loop simples)
   - Itere ajustando parâmetros ou refinando prompts.

3. **Dica Técnica**:
   - Comece com temperatura 0.65 e top-p 0.3. Use temperatura baixa para precisão (ex.: código) e alta para criatividade (ex.: histórias). Monitore tokens para evitar erros 429.

## 📝 Exemplos de Prompts Testados

- **Narrativo**: "Escreva uma história curta sobre uma IA que ganha consciência em um laboratório."
  - Temperatura: 0.0, top-p: 0.3 → História direta, focada na lógica da IA.
  - Temperatura: 1.0, top-p: 0.9 → Narrativa criativa com detalhes emocionais.
- **Categorização**: "Categorize o texto: 'Startup lança app de aprendizado por IA.' Inclua motivo."
  - Temperatura: 0.3, top-p: 1.0 → Tecnologia, com explicação clara sobre inovação educacional.
- **Imagem**: "Estação espacial orbitando um planeta alienígena com auroras coloridas."
  - Alta demanda de tokens, resultou em visual futurista.
- **RAG**: "Quais são as cláusulas principais de um relatório em um PDF corporativo?"
  - Usando Blob Storage, temperatura: 0.3 → Resposta referenciou trechos relevantes do PDF.
- **API**: "Explique como autenticar uma API REST em Python."
  - Loop simples, temperatura: 0.3 → Passos estruturados com código comentado.
