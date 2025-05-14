Explorando o Azure Open AI Playground: De Parâmetros a Aplicações Práticas

🌟 Sobre o Projeto
Este repositório documenta meus aprendizados com o Azure Open AI Playground, explorado no curso da DIO. Como desenvolvedor técnico, usei o Azure AI Studio para interagir com modelos de IA generativa (ex.: GPT-4o Mini), testando ajustes de temperatura e top-p, categorização de texto, geração de imagens, integração com Blob Storage para RAG, e chamadas de API. Aqui, compartilho o que aprendi, exemplos originais e reflexões sobre como aplicar IA em projetos reais.
📚 O que Aprendi
O Azure Open AI Playground é um ambiente poderoso para prototipar IA generativa. Meus principais aprendizados:

Azure AI Studio e Playground: Interface para testar modelos como GPT-4o Mini sem codificação, configurando prompts, parâmetros e integração com dados externos.
Temperatura e Top-p:
Temperatura: Controla aleatoriedade. Baixa (0.0) para precisão (ex.: código); alta (1.0) para criatividade (ex.: textos narrativos).
Top-p: Limita palavras por probabilidade. Alto (1.0) para diversidade; baixo (0.3) para coerência.
Combinações: Temperatura alta + top-p alto = máxima criatividade; temperatura baixa + top-p baixo = precisão. Padrão sugerido: temperatura 0.65, top-p 0.3.


Categorização de Texto:
Usei zero-shot para categorizar textos, mas one-shot (com exemplos) garantiu formatação consistente e explicações.
Prompts mal definidos exigem iteração para corrigir erros do modelo.


Geração de Imagens:
Criei imagens com prompts descritivos, mas o alto consumo de tokens requer cuidado.


Blob Storage e RAG:
Configurei Blob Storage para armazenar documentos e Azure Cognitive Search (plano S1) para indexação, suportando buscas semânticas.
Implementei RAG para responder perguntas baseadas em documentos, ajustando prompts para evitar referências imprecisas e erros 429.


Chamada de API:
Criei um loop simples para interagir com a API, usando endpoints e autenticação. Configurei mensagens de sistema para definir comportamento.
Gerenciei cotas para evitar erros 429, ajustando limites no cliente.


Custos: Cobrança por tokens exige monitoramento. Limitei respostas (ex.: 500 tokens) para otimizar uso.

Meus Insights

Prototipagem Rápida: O Playground é um laboratório para testar ideias sem código, ideal para validar conceitos antes de implementar via API.
Prompt Engineering: Prompts claros com one-shot são como queries otimizadas. Ajustes finos de temperatura/top-p maximizam resultados.
RAG e Integração: Blob Storage com RAG é promissor para chatbots baseados em documentos, mas exige prompts precisos e gestão de cotas.
Custo Consciente: Testes enxutos e limites rígidos evitam gastos excessivos.
Futuro com API: O Playground prepara para a API, onde aplicarei esses conceitos em automações ou análise de dados.

🚀 Como Testar
Quer explorar o Playground? Um guia técnico:

Pré-requisitos:

Conta no Microsoft Azure.
Configure um recurso do Azure Open AI no portal.


Passos:

Acesse o Azure AI Studio e vá ao Playground.
Escolha um modelo (ex.: GPT-4o Mini).
Teste prompts:
Narrativo: "Escreva uma história curta sobre um robô explorador em Marte." (temperatura: 0.8, top-p: 0.9)
Categorização: "Categorize o texto: 'Nova tecnologia reduz emissões de carbono.' Inclua motivo." (temperatura: 0.3, top-p: 1.0)
Imagem: "Floresta encantada com criaturas bioluminescentes." (use com moderação)
RAG: "Quais são os requisitos de um contrato em um PDF corporativo?" (configure Blob Storage com PDFs)


Itere com base no output, ajustando parâmetros ou prompts.


Dica Técnica:

Comece com temperatura 0.65 e top-p 0.3. Use temperatura baixa para precisão (ex.: código) e alta para criatividade (ex.: histórias). Monitore tokens para evitar erros 429.



📝 Exemplos de Prompts Testados

Narrativo: "Escreva uma história curta sobre um robô explorador em Marte." (temperatura: 0.0, top-p: 0.3 → história direta; temperatura: 1.0, top-p: 0.9 → narrativa com detalhes criativos)
Categorização: "Categorize o texto: 'Nova tecnologia reduz emissões de carbono.' Inclua motivo." (temperatura: 0.3, top-p: 1.0 → Sustentabilidade, com explicação clara)
Imagem: "Floresta encantada com criaturas bioluminescentes e névoa mística." (alta demanda de tokens)
RAG: "Quais são os requisitos de um contrato em um PDF corporativo?" (usando Blob Storage, temperatura: 0.3 → resposta com referências ao documento)
API: "Como criar uma API REST em Python?" (loop simples, temperatura: 0.3 → passos estruturados)

🛠 Tecnologias

Azure Open AI Service
Azure AI Studio
Azure Blob Storage
Azure Cognitive Search
Modelos da Open AI (GPT-4o Mini)

📚 Recursos

Documentação do Azure Open AI
Azure AI Studio
Curso da DIO

🤝 Contribuições
Explorando IA? Compartilhe seus experimentos! Pode:

Abrir uma issue com prompts, ajustes de parâmetros ou configurações de RAG.
Enviar um pull request com exemplos ou otimizações.

📬 Contato
Dúvidas? Me acha no GitHub Issues_span style="color: rgb(0, 0, 0); font-family: "Times New Roman"; font-size: medium; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: 400; letter-spacing: normal; orphans: 2; text-align: start; text-indent: 0px; text-transform: none; widows: 2; word-spacing: 0px; -webkit-text-stroke-width: 0px; white-space: normal; text-decoration-thickness: initial; text-decoration-style: initial; text-decoration-color: initial; display: inline !important; float: none;"> ou por seu-email@exemplo.com.

Feito por [Seu Nome]Baseado no curso da DIO: Azure Open AI no Playground
