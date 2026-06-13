#  Caderno Temático: Engenharia de Prompts com IA

> Projeto desenvolvido como parte do Desafio de Projeto da plataforma **DIO (Digital Innovation One)**  
> Utilizando **NotebookLM** como ferramenta central de aprendizagem ativa com Inteligência Artificial

---

## Contexto e Objetivos

### Por que Engenharia de Prompts?

A Engenharia de Prompts é a disciplina que define a qualidade da interação entre humanos e modelos de linguagem de grande porte (LLMs). Em um cenário onde profissionais de dados, analistas de BI e engenheiros de software passam a trabalhar lado a lado com IAs generativas, dominar essa habilidade deixou de ser diferencial e se tornou **competência essencial**.

Este caderno temático foi construído com um objetivo duplo:
1. **Aprender sistematicamente** os fundamentos, técnicas e boas práticas de Engenharia de Prompts
2. **Documentar o processo de aprendizagem ativa** com IA — usando o próprio NotebookLM como laboratório

### Objetivos de Estudo

| # | Objetivo | Critério de Sucesso |
|---|----------|---------------------|
| 1 | Compreender os princípios fundamentais de prompting eficaz | Explicar as 5 principais técnicas sem consulta |
| 2 | Dominar técnicas avançadas: Chain-of-Thought, Few-Shot, Role Prompting | Aplicar cada técnica em casos reais de trabalho |
| 3 | Entender como diferentes LLMs respondem a estruturas de prompt distintas | Comparar respostas de pelo menos 3 modelos |
| 4 | Construir um banco de prompts reutilizáveis para contexto profissional (BI/Dados) | Repositório com ≥10 prompts validados e documentados |
| 5 | Desenvolver pensamento crítico sobre outputs de IA | Identificar alucinações e limitações de forma sistemática |

---

## Curadoria de Fontes

Fontes abertas selecionadas e carregadas no NotebookLM para composição do caderno temático:

| # | Fonte | Tipo | Link | Relevância |
|---|-------|------|------|------------|
| 1 | **Prompt Engineering Guide** — DAIR.AI | Web/PDF | [promptingguide.ai](https://www.promptingguide.ai/) | Referência técnica completa e open-source; cobre Zero-Shot, Few-Shot, CoT, ReAct e mais |
| 2 | **Prompt Engineering** — OpenAI Official Docs | Web | [platform.openai.com/docs/guides/prompt-engineering](https://platform.openai.com/docs/guides/prompt-engineering) | Guia oficial da OpenAI com estratégias e táticas estruturadas |
| 3 | **Prompt Engineering Overview** — Anthropic Docs | Web | [docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview) | Perspectiva do criador do Claude; foco em clareza, contexto e formato |
| 4 | **Introduction to Prompt Engineering** — Microsoft Learn | Web | [learn.microsoft.com/azure/ai-services/openai/concepts/prompt-engineering](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/prompt-engineering) | Abordagem enterprise com foco em Azure OpenAI; relevante para contexto corporativo |
| 5 | **Prompting Guide for Gemini** — Google AI | Web | [ai.google.dev/gemini-api/docs/prompting-intro](https://ai.google.dev/gemini-api/docs/prompting-intro) | Visão do ecossistema Google; complementa a perspectiva multi-modelo |

> Todas as fontes são **abertas, gratuitas e em texto estruturado**, compatíveis com upload direto no NotebookLM.

---

## Engenharia de Prompts & Cicatrizes

Esta seção documenta o processo real de experimentação com prompts dentro do NotebookLM.  
Seguindo a lógica de **aprendizagem ativa**: cada tentativa — seja bem-sucedida ou não — gera conhecimento.

### Estratégia de Prompting Adotada

Para extrair o máximo do NotebookLM com as fontes carregadas, utilizei as seguintes abordagens progressivas:

---

#### Prompt 1 — Exploração Inicial (Zero-Shot)
**Objetivo:** Mapear o território do tema  
**Prompt enviado:**
```
O que é Engenharia de Prompts e por que ela é considerada uma habilidade profissional 
relevante em 2024 e 2025? Baseie sua resposta nas fontes carregadas.
```
**Resultado:** Resposta abrangente e bem estruturada. O NotebookLM citou trechos das fontes DAIR.AI e OpenAI automaticamente.  
**Aprendizado:** Zero-shot funciona bem para perguntas abertas e de mapeamento conceitual.

---

#### Prompt 2 — Aprofundamento Técnico (Few-Shot + Exemplos)
**Objetivo:** Entender Chain-of-Thought com exemplos práticos  
**Prompt enviado:**
```
Explique a técnica Chain-of-Thought (CoT) prompting. 
Use o seguinte formato para sua resposta:
- Definição em 2 frases
- Quando usar (3 cenários ideais)
- Exemplo de prompt SEM CoT
- Exemplo do mesmo prompt COM CoT
- Limitações conhecidas
```
**Resultado:** Excelente. A estrutura guiada produziu resposta muito mais acionável que a pergunta aberta.  
**Cicatriz:** Na primeira tentativa, esqueci de incluir "use as fontes carregadas" — a resposta veio do conhecimento geral do modelo, não das fontes. Ao adicionar a instrução de ancorar nas fontes, a qualidade aumentou e as citações apareceram.

---

#### Prompt 3 — Role Prompting (Persona)
**Objetivo:** Obter perspectiva especializada para contexto de BI/dados  
**Prompt enviado:**
```
Aja como um Engenheiro de Dados Sênior que precisa treinar sua equipe sobre uso 
eficiente de IAs generativas no trabalho diário com SQL, Python e Power BI.
Com base nas fontes deste caderno, crie um guia prático de 5 pontos sobre como 
escrever prompts melhores para tarefas de análise de dados.
```
**Resultado:** A persona funcionou — a resposta foi mais prática e contextualizada para dados do que as anteriores.  
**Cicatriz:** O modelo inicialmente ignorou a restrição de "5 pontos" e gerou 8. Refinei o prompt adicionando: *"Responda EXATAMENTE com 5 pontos numerados, sem adicionar seções extras."* — funcionou na segunda tentativa.

---

#### Prompt 4 — Prompt de Contraste (Troubleshooting)
**Objetivo:** Identificar quando prompts falham  
**Prompt enviado (versão ruim, intencional):**
```
Me fala sobre prompts
```
**Resultado:** Resposta genérica, superficial, sem ancoragem nas fontes.  
**Prompt refinado:**
```
Com base exclusivamente nas fontes carregadas neste caderno, liste as 3 principais 
causas de falha em prompts segundo os autores, e para cada causa, apresente a 
solução recomendada no formato: Causa → Solução → Exemplo.
```
**Resultado:** Completamente diferente. Estruturado, citado e acionável.  
**Aprendizado chave:** Vagueza no prompt = vagueza na resposta. Especificidade é tudo.

---

#### Prompt 5 — Meta-Prompt (Síntese Final)
**Objetivo:** Gerar o próprio mini-guia de revisão  
**Prompt enviado:**
```
Com base em todo o material deste caderno temático sobre Engenharia de Prompts, 
gere um resumo executivo estruturado com:
1. Os 5 conceitos mais importantes (com definição de 1 linha cada)
2. As 3 técnicas mais poderosas e quando aplicá-las
3. Um glossário de 10 termos essenciais
4. 5 prompts-modelo reutilizáveis para profissionais de dados

Formato: Markdown estruturado, adequado para um README no GitHub.
```
**Resultado:** Este prompt gerou a base do Miniguia de Estudo abaixo (seção seguinte).  
**Insight:** Usar o NotebookLM para gerar a própria documentação de estudo é o uso mais poderoso da ferramenta.

---

##  Miniguia de Estudo (Entrega Final)

### 1. Resumo Estruturado — Os 5 Conceitos Fundamentais

| Conceito | Definição |
|----------|-----------|
| **Prompt** | Instrução ou conjunto de instruções fornecido a um LLM para guiar sua resposta |
| **Zero-Shot Prompting** | Solicitar uma tarefa sem fornecer exemplos — depende do conhecimento pré-treinado do modelo |
| **Few-Shot Prompting** | Incluir 2–5 exemplos no prompt para guiar o padrão e formato da resposta esperada |
| **Chain-of-Thought (CoT)** | Instruir o modelo a "pensar passo a passo", melhorando raciocínio em tarefas complexas |
| **System Prompt / Role** | Definir o contexto, persona ou regras gerais de comportamento antes da conversa principal |

---

### 2. As 3 Técnicas Mais Poderosas

####  Chain-of-Thought (CoT)
**Quando usar:** Problemas lógicos, matemáticos, análises de dados, debugging de código  
**Como ativar:** Adicione *"Pense passo a passo"* ou *"Let's think step by step"* ao prompt  
**Exemplo:**
```
Analise este resultado de query SQL e identifique o problema, pensando passo a passo:
[cole o código/resultado aqui]
```

####  Role Prompting
**Quando usar:** Quando você precisa de expertise específica ou perspectiva contextualizada  
**Como ativar:** Comece com *"Aja como [persona com expertise relevante]..."*  
**Exemplo:**
```
Aja como um DBA especialista em Oracle ERP. Revise esta query e sugira otimizações 
para performance em tabelas com mais de 10 milhões de registros.
```

####  Structured Output Prompting
**Quando usar:** Quando o output será usado em documentação, código ou apresentação  
**Como ativar:** Especifique o formato exato da resposta esperada  
**Exemplo:**
```
Responda APENAS no seguinte formato JSON, sem texto adicional:
{"conceito": "...", "definição": "...", "exemplo": "...", "quando_usar": "..."}
```

---

### 3. Glossário de Termos Essenciais

| Termo | Definição |
|-------|-----------|
| **LLM** | Large Language Model — modelo de linguagem de grande porte treinado em vastos volumes de texto |
| **Token** | Unidade básica de processamento de texto em LLMs; aproximadamente 0,75 palavras em inglês |
| **Context Window** | Limite máximo de tokens que um modelo processa em uma única interação |
| **Temperatura** | Parâmetro que controla a criatividade/aleatoriedade das respostas (0 = determinístico, 1 = criativo) |
| **Hallucination** | Quando o modelo gera informação factualmente incorreta com aparente confiança |
| **Grounding** | Técnica de ancorar respostas em fontes específicas para reduzir alucinações |
| **RAG** | Retrieval-Augmented Generation — combinar busca em base de conhecimento com geração do LLM |
| **System Prompt** | Instrução de nível superior que define comportamento, persona ou restrições do modelo |
| **Iteração de Prompt** | Processo de refinamento progressivo do prompt até obter o resultado desejado |
| **Prompt Injection** | Ataque onde instruções maliciosas são inseridas no prompt para manipular o modelo |

---

### 4. Prompts Reutilizáveis para Profissionais de Dados

####  Para Análise de Dados
```
Aja como um analista de dados sênior. Analise os seguintes dados/resultados e:
1. Identifique os 3 principais insights
2. Aponte anomalias ou inconsistências
3. Sugira próximas análises relevantes
Dados: [cole aqui]
```

####  Para Debugging de Código/Query
```
Aja como um especialista em [SQL/Python/DAX/M]. O código abaixo está gerando 
[descreva o erro ou comportamento inesperado]. 
Analise passo a passo, identifique a causa raiz e forneça a correção comentada.
Código: [cole aqui]
```

####  Para Documentação Técnica
```
Com base no código/processo abaixo, gere uma documentação técnica no formato:
- Objetivo: (1 parágrafo)
- Pré-requisitos: (lista)
- Como funciona: (passo a passo numerado)
- Parâmetros/Variáveis: (tabela)
- Limitações conhecidas: (lista)
[cole o código/processo aqui]
```

####  Para Revisão e Qualidade
```
Revise o seguinte [documento/código/análise] com o olhar de um especialista em 
qualidade de dados. Pontue de 1 a 10 nos critérios: clareza, completude, 
consistência e acionabilidade. Para cada critério abaixo de 8, forneça sugestão 
específica de melhoria.
[cole o conteúdo aqui]
```

#### Para Apresentações Executivas
```
Transforme a análise técnica abaixo em uma narrativa executiva de no máximo 
5 bullet points, linguagem não-técnica, foco em impacto de negócio e 
recomendação clara de ação. Público: [descreva o perfil dos executivos].
Análise: [cole aqui]
```

---

## 🚀 Como Reproduzir Este Projeto

1. Acesse [NotebookLM](https://notebooklm.google.com/)
2. Crie um novo notebook com o tema "Engenharia de Prompts"
3. Faça upload/adicione as 5 fontes listadas na seção de Curadoria
4. Experimente os prompts documentados na seção de Cicatrizes (em ordem)
5. Documente seus próprios resultados e adicione ao fork deste repositório

---

## Autor

**Fabio Roberto de Moraes Belo**  
Data Analytics & BI | Prodesp — Governo do Estado de São Paulo  
Formação: Engenharia de Software | Pós em Segurança da Informação | MBA em andamento

[![DIO](https://img.shields.io/badge/DIO-Desafio%20de%20Projeto-purple)](https://www.dio.me/)
[![NotebookLM](https://img.shields.io/badge/NotebookLM-Caderno%20Tem%C3%A1tico-blue)](https://notebooklm.google.com/)

---

*Projeto desenvolvido para o Desafio de Projeto DIO — Inteligência Artificial como Ferramenta de Aprendizagem Ativa*
