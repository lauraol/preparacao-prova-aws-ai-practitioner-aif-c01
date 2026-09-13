# Resumo de Estudo e Mapa Mental

## AWS Certified AI Practitioner (AIF-C01) | Aula 02

**Material-base:** `Aula 02 - IA.pptx`  
**Temas centrais:** Amazon Bedrock e Prompt Engineering

---

## 1. Foundation Models (FM)

Um **Foundation Model** é um modelo pré-treinado em grandes volumes de dados que pode ser reutilizado para diversas tarefas. Treinar um FM do zero é caro e demorado; por isso, as empresas normalmente reutilizam e adaptam modelos existentes.

### Exemplos

- GPT
- Claude
- Llama
- Amazon Nova
- Gemini

### Conceitos importantes para a prova

- Treinar do zero tende a exigir mais custo, tempo e capacidade computacional.
- Reutilizar um FM existente costuma ser a abordagem mais adequada.
- Um FM pode ser adaptado para casos de uso específicos.

---

## 2. Large Language Models (LLM)

LLMs são Foundation Models especializados em linguagem natural. Podem ser utilizados para:

- Responder perguntas
- Resumir textos
- Traduzir conteúdo
- Gerar textos

> **Todo LLM é um Foundation Model, mas nem todo Foundation Model é um LLM.**

---

## 3. Amazon Bedrock

O **Amazon Bedrock** é um serviço totalmente gerenciado para construir aplicações com IA Generativa na AWS.

### Características

- Não exige gerenciamento de servidores.
- Possui modelo de pagamento por uso.
- Permite escolher o Foundation Model mais adequado.
- Oferece recursos de RAG.
- Oferece suporte a agentes.
- Permite trabalhar com diferentes modelos por APIs gerenciadas.

### Ponto de prova

Quando a questão perguntar qual serviço AWS permite utilizar Foundation Models para construir aplicações de IA Generativa, a resposta tende a ser **Amazon Bedrock**.

---

## 4. Escolha de Foundation Models no Bedrock

A escolha do modelo deve considerar:

- Tipo de modelo
- Capacidades
- Performance
- Compliance
- Nível de customização
- Tamanho
- Licença
- Latência
- Custo

Modelos menores geralmente apresentam menor custo.

### Amazon Titan

Família de modelos base da AWS, com suporte a recursos relacionados a texto e imagem por APIs gerenciadas.

---

## 5. Fine-Tuning

**Fine-tuning** é a personalização de um Foundation Model existente usando dados próprios, com o objetivo de melhorar o desempenho em tarefas ou domínios específicos.

### Características

- Utiliza conjuntos de dados próprios.
- Os dados precisam seguir o formato exigido.
- Os dados de treinamento podem ser armazenados no Amazon S3.
- Economiza tempo e capacidade computacional quando comparado ao treinamento do zero.

### 5.1 Supervised Fine-Tuning

Utiliza dados rotulados com exemplos de pares de entrada e saída.

```text
Entrada → Saída esperada
Pergunta → Resposta correta
```

É indicado quando existem exemplos claros do comportamento desejado.

### 5.2 Reinforcement Fine-Tuning

Utiliza feedback e uma função de recompensa para avaliar as saídas do modelo.

Fluxo simplificado:

1. O modelo recebe dados de entrada ou prompts.
2. Uma função de recompensa avalia as respostas.
3. As respostas recebem pontuações.
4. O modelo aprende iterativamente buscando pontuações maiores.

### Macete para a prova

```text
Dados rotulados e pares entrada-saída
→ Supervised Fine-Tuning

Feedback e função de recompensa
→ Reinforcement Fine-Tuning
```

---

## 6. Destilação de Modelos

A **destilação** transfere conhecimento de um modelo maior para um modelo menor.

```text
Modelo maior = Professor
Modelo menor = Estudante
```

### Benefícios

- Modelo menor e mais rápido
- Redução de custo
- Menor consumo computacional
- Comportamento semelhante ao modelo original

### Compensação

Pode haver redução de acurácia, aceita em cenários nos quais eficiência, velocidade e custo são prioritários.

---

## 7. Avaliação de Modelos

A avaliação ajuda a controlar a qualidade de um modelo em tarefas como:

- Sumarização
- Perguntas e respostas
- Classificação de texto

### 7.1 Avaliação automática

Emprega métricas estatísticas e conjuntos de dados para mensurar:

- Acurácia
- Qualidade
- Velocidade
- Eficiência
- Possíveis vieses

### 7.2 Avaliação humana

Uma equipe avalia as respostas com base em métricas, critérios e tarefas definidas previamente. É útil para aspectos subjetivos, como clareza, utilidade e adequação.

### Métricas importantes

#### ROUGE

Usada na avaliação de textos gerados, especialmente resumos.

#### BLEU

Usada principalmente para avaliar traduções automáticas e comparar o texto gerado com uma referência.

#### BERTScore

Avalia a similaridade semântica entre o texto gerado e um texto de referência, utilizando modelos BERT pré-treinados.

#### Perplexidade

Avalia quão bem o modelo prevê o próximo token.

> **Quanto menor a perplexidade, melhor a capacidade de previsão do próximo token.**

---

## 8. RAG (Retrieval-Augmented Generation)

RAG significa **Geração Aumentada por Recuperação**. Permite que um Foundation Model utilize informações externas aos dados usados em seu treinamento.

### Fluxo simplificado

1. O usuário faz uma pergunta.
2. O sistema localiza informações relevantes em uma base externa.
3. Os trechos relevantes são recuperados.
4. O conteúdo é fornecido ao modelo como contexto.
5. O modelo produz uma resposta fundamentada nesse contexto.

### Benefício principal

Permite trabalhar com conteúdo corporativo ou atualizado sem retreinar constantemente o Foundation Model.

### Pegadinha de prova

```text
Informação muda frequentemente
→ RAG

Necessidade de especializar comportamento ou tarefa
→ Fine-Tuning
```

---

## 9. Tokenização

Tokenização é o processo de converter texto bruto em uma sequência de tokens.

### Formas comuns

- Tokenização por palavras
- Tokenização por subpalavras

Palavras podem ser divididas em prefixos, sufixos ou outras unidades menores. A quantidade de tokens de entrada e saída é um fator importante de custo no Amazon Bedrock.

---

## 10. Embeddings

Embeddings são vetores numéricos criados a partir de textos, imagens ou áudios.

### Para que servem

- Representar significado semântico
- Comparar informações
- Melhorar buscas
- Apoiar busca semântica
- Apoiar aplicações RAG

> Conteúdos semanticamente relacionados tendem a possuir embeddings semelhantes.

---

## 11. Guardrails no Amazon Bedrock

Guardrails controlam a interação entre usuários e Foundation Models.

### Usos principais

- Filtrar conteúdo inadequado
- Remover ou bloquear informações pessoais
- Aplicar controles à entrada e à saída
- Reduzir alucinações

### Conceito importante

**Alucinação** ocorre quando o modelo gera informação falsa, incorreta ou sem sustentação adequada.

---

## 12. Agentes no Amazon Bedrock

Agentes coordenam tarefas com múltiplas etapas e podem executar ações predefinidas.

### Capacidades apresentadas na aula

- Coordenar tarefas na ordem correta
- Transferir informações entre etapas
- Executar ações predefinidas
- Utilizar RAG para recuperar informações quando necessário
- Orquestrar interações entre modelos, ações e bases de conhecimento

### Regra mental

```text
LLM → gera respostas
RAG → recupera conhecimento
Agente → coordena e executa tarefas
```

---

## 13. Monitoramento com Amazon CloudWatch

O Amazon Bedrock pode enviar logs de invocação para Amazon CloudWatch e Amazon S3. Esses registros podem incluir textos e imagens. Métricas do Bedrock também podem ser publicadas no CloudWatch.

---

## 14. Preços no Amazon Bedrock

### Sob demanda

- Modelo pay-as-you-go
- Sem compromisso de longo prazo
- Adequado para cargas imprevisíveis
- Cobrança conforme o uso e os tokens processados

### Throughput provisionado

- Reserva de capacidade por determinado período
- Associado à quantidade máxima de tokens de entrada e saída processados
- Adequado quando é necessário garantir capacidade

### Batch

- Processa múltiplas inferências em lote
- Pode oferecer desconto em comparação com outras formas de execução

### Principais fatores de custo

- Número de tokens de entrada
- Número de tokens de saída
- Tamanho do modelo
- Tipo de processamento

Temperatura, Top K e Top P não alteram diretamente o modelo de cobrança, embora possam influenciar o conteúdo gerado.

---

## 15. Amazon Nova

Amazon Nova é uma família de Foundation Models construída pela AWS e acessível por meio do Amazon Bedrock.

### Família apresentada na aula

- **Nova Premier:** modelo de maior capacidade, inclusive para atuar como modelo professor.
- **Nova Pro:** equilíbrio entre acurácia, velocidade e custo.
- **Nova Lite:** baixo custo para processamento de imagem, vídeo e texto.
- **Nova Micro:** modelo somente de texto, com baixa latência e baixo custo.
- **Nova Canvas:** geração de imagens.
- **Nova Reel:** geração de vídeos.
- **Nova Sonic:** conversação e voz em múltiplos idiomas.

---

# Prompt Engineering

## 16. O que é Engenharia de Prompt?

Engenharia de Prompt é o processo de desenvolver, projetar e otimizar prompts para melhorar as saídas dos Foundation Models de acordo com uma necessidade.

### Estrutura de um bom prompt

```text
Instrução
+ Contexto
+ Dados de entrada
+ Indicador ou formato de saída
```

### Componentes

- **Instrução:** descreve a tarefa e como o modelo deve executá-la.
- **Contexto:** fornece informações externas para orientar o modelo.
- **Dado de entrada:** conteúdo que será processado.
- **Indicador de saída:** define o formato, o tamanho ou a estrutura esperada.

---

## 17. Prompt Negativo

Prompt negativo informa explicitamente o que o modelo não deve incluir ou fazer.

### Benefícios

- Evitar conteúdo indesejado
- Manter o foco
- Aumentar a clareza
- Reduzir informações irrelevantes

### Exemplo

```text
Produza um resumo em três tópicos.
Não inclua opiniões pessoais.
Não use termos técnicos sem explicação.
```

---

## 18. Parâmetros de Inferência

### Temperatura

Controla a diversidade ou criatividade da resposta.

```text
Temperatura baixa
→ respostas mais conservadoras e focadas nos tokens mais prováveis

Temperatura alta
→ respostas mais diversas, criativas e imprevisíveis
```

### Top K

Limita a escolha aos **K tokens mais prováveis**.

```text
Top K baixo → conjunto menor de candidatos
Top K alto → conjunto maior e mais variado
```

### Top P

Limita os candidatos com base na soma acumulada de probabilidades até atingir o valor definido.

```text
Top P baixo → conjunto mais restrito
Top P alto → conjunto mais amplo e diverso
```

### Comprimento máximo

Define o limite de tamanho da resposta.

### Stop Sequences

Tokens ou sequências que orientam o modelo a interromper a geração.

---

## 19. Técnicas de Prompting

### Zero-Shot Prompting

O modelo recebe uma tarefa sem exemplos prévios.

```text
Classifique o comentário como positivo, neutro ou negativo.
```

### One-Shot Prompting

O modelo recebe um único exemplo antes da tarefa.

### Few-Shot Prompting

O modelo recebe alguns exemplos para compreender o padrão esperado.

```text
Entrada: ótimo atendimento
Saída: positivo

Entrada: entrega atrasada
Saída: negativo

Agora classifique: atendimento razoável
```

### Chain of Thought

A tarefa é organizada em uma sequência de etapas para aumentar a estrutura e a coerência da resolução.

```text
Primeiro identifique o problema.
Depois liste os dados relevantes.
Em seguida avalie as opções.
Por fim apresente a conclusão.
```

### RAG Prompting

O prompt é complementado com informações recuperadas de fontes externas para gerar uma resposta mais contextualizada.

### Prompt Templates

Modelos de prompt reutilizáveis que ajudam a padronizar entradas e saídas e podem ser usados na orquestração de agentes.

---

# Comparação: Fine-Tuning vs. RAG vs. Agentes

| Necessidade | Abordagem |
|---|---|
| Especializar o comportamento do modelo | Fine-Tuning |
| Usar informações externas ou atualizadas | RAG |
| Executar e coordenar tarefas em várias etapas | Agentes |
| Reduzir custo e latência com modelo menor | Destilação |
| Restringir entradas, saídas e conteúdo | Guardrails |

---

# Mapa Mental

```text
AWS AI PRACTITIONER | AULA 02
│
├── FOUNDATION MODELS
│   ├── Modelos pré-treinados
│   ├── Reutilizáveis
│   ├── Adaptáveis
│   └── Exemplos
│       ├── GPT
│       ├── Claude
│       ├── Llama
│       └── Amazon Nova
│
├── LLM
│   ├── Linguagem natural
│   ├── Perguntas e respostas
│   ├── Sumarização
│   ├── Tradução
│   └── Geração de texto
│
├── AMAZON BEDROCK
│   ├── Serviço totalmente gerenciado
│   ├── Pay-as-you-go
│   ├── Escolha de FM
│   ├── RAG
│   ├── Agentes
│   ├── Guardrails
│   └── CloudWatch e S3
│
├── CUSTOMIZAÇÃO
│   ├── Fine-Tuning
│   │   ├── Supervisionado
│   │   │   └── Dados rotulados
│   │   └── Por reforço
│   │       └── Função de recompensa
│   └── Destilação
│       ├── Professor
│       ├── Estudante
│       ├── Menor custo
│       └── Maior velocidade
│
├── AVALIAÇÃO
│   ├── Automática
│   │   ├── ROUGE
│   │   ├── BLEU
│   │   ├── BERTScore
│   │   └── Perplexidade
│   └── Humana
│       ├── Clareza
│       ├── Utilidade
│       └── Adequação
│
├── RAG
│   ├── Recupera fontes externas
│   ├── Fornece contexto ao FM
│   ├── Usa informações atualizadas
│   └── Evita retreinamento frequente
│
├── TOKENIZAÇÃO
│   ├── Texto → Tokens
│   ├── Palavras
│   ├── Subpalavras
│   └── Impacto no custo
│
├── EMBEDDINGS
│   ├── Vetores numéricos
│   ├── Significado semântico
│   ├── Busca semântica
│   └── Apoio ao RAG
│
├── GUARDRAILS
│   ├── Filtragem
│   ├── Proteção de informações pessoais
│   ├── Controles de entrada e saída
│   └── Redução de alucinações
│
├── AGENTES
│   ├── Coordenam etapas
│   ├── Executam ações
│   ├── Usam bases de conhecimento
│   └── Aproveitam RAG
│
├── PREÇOS
│   ├── Sob demanda
│   ├── Throughput provisionado
│   ├── Batch
│   └── Principal fator
│       └── Tokens de entrada e saída
│
└── PROMPT ENGINEERING
    ├── Estrutura
    │   ├── Instrução
    │   ├── Contexto
    │   ├── Entrada
    │   └── Formato de saída
    ├── Prompt negativo
    ├── Parâmetros
    │   ├── Temperatura
    │   ├── Top K
    │   ├── Top P
    │   ├── Comprimento
    │   └── Stop Sequences
    └── Técnicas
        ├── Zero-Shot
        ├── One-Shot
        ├── Few-Shot
        ├── Chain of Thought
        ├── RAG
        └── Prompt Templates
```

---



---

# Complementos de cobertura da Aula 02

## Amazon Nova 2

A aula também apresenta a família **Amazon Nova 2**, voltada à construção de aplicações complexas de IA, como chatbots interativos, análise de documentos e vídeos e criação de agentes.

### Modelos citados no material

- **Nova 2 Lite:** modelo rápido e econômico para cargas diárias envolvendo imagens, textos e documentos.
- **Nova 2 Sonic:** Foundation Model de voz para conversações em tempo real.
- **Nova 2 Multimodal Embeddings:** modelo de embeddings multimodal para busca semântica e aplicações de RAG agentivo.
- **Nova 2 Omni:** apresentado no material como modelo para geração de imagens.

O material menciona contexto de até 1 milhão de tokens para a família Nova 2.

---

## Exercícios apresentados na aula

### Exercício 1: respostas concisas e idioma específico

Uma empresa utiliza um LLM pré-treinado em um chatbot de recomendação e precisa de respostas concisas em um idioma específico.

**Resposta indicada no material:** ajustar o prompt.

**Raciocínio:** requisitos de idioma, concisão, formato e tom podem ser especificados e refinados por meio de engenharia de prompt.

### Exercício 2: busca com texto e imagens

O cenário exige processar consultas que contenham texto e imagens.

**Observação crítica:** o slide indica “modelo de embedding de texto” como resposta, mas o próprio requisito é multimodal. Entre as alternativas exibidas, **modelo de embedding multimodal** é a opção conceitualmente mais aderente ao processamento conjunto de texto e imagens. Este ponto deve ser validado com o instrutor ou com a documentação oficial usada pelo grupo.

### Exercício 3: adequação ao tom de voz

Um chatbot precisa produzir respostas de acordo com o tom de voz da empresa.

**Observação crítica:** o slide marca a segunda alternativa, inferência em lote, mas a alternativa que descreve experimentar e refinar o prompt é conceitualmente mais alinhada ao requisito de tom de voz. Limite de tokens controla comprimento, batch trata do modo de processamento e temperatura alta aumenta diversidade, mas não garante o tom desejado.

### Exercício 4: orçamento limitado e flexibilidade

A empresa quer usar Amazon Bedrock sem compromisso de longo prazo.

**Resposta indicada no material:** sob demanda.

**Raciocínio:** o modelo sob demanda permite pagar conforme o uso e é adequado a cargas imprevisíveis ou sem compromisso prolongado.

---

## Cobertura por blocos de slides

- **Slides 1 a 3:** abertura e plano de estudos.
- **Slides 4 e 5:** Foundation Models e LLMs.
- **Slides 6 a 8:** Amazon Bedrock, seleção de modelos e Amazon Titan.
- **Slides 9 a 14:** fine-tuning supervisionado, fine-tuning por reforço, destilação, custos e casos de uso.
- **Slides 15 a 18:** avaliação automática, avaliação humana e métricas.
- **Slides 19 a 26:** RAG, tokenização, embeddings, guardrails, agentes e comparação de abordagens.
- **Slides 27 a 32:** monitoramento, preços, redução de custos, Amazon Nova e Amazon Nova 2.
- **Slides 33 a 45:** engenharia de prompt, prompts negativos, parâmetros de inferência e técnicas de prompting.
- **Slides 46 a 50:** exercícios de fixação.

---

## Pontos de atenção para a prova

1. **Fine-tuning não é sinônimo de RAG.** Fine-tuning adapta o modelo; RAG fornece conhecimento externo no momento da consulta.
2. **Agentes executam e coordenam ações.** RAG recupera informações; o LLM gera a resposta.
3. **Embeddings multimodais** são apropriados quando a busca precisa representar mais de uma modalidade, como texto e imagem.
4. **Engenharia de prompt** é a primeira opção quando o requisito envolve tom, idioma, concisão ou formato de saída.
5. **Inferência em lote** está relacionada ao processamento de múltiplas solicitações e economia, não ao alinhamento de tom.
6. **Temperatura, Top K e Top P** alteram diversidade e seleção de tokens, mas não substituem instruções claras no prompt.
7. **Modelos menores** tendem a ser mais econômicos, enquanto modelos maiores tendem a oferecer mais capacidade.
8. **Tokens de entrada e saída** são componentes centrais de custo em modelos baseados em texto.
9. **Guardrails** ajudam a aplicar controles, proteger informações e reduzir respostas inadequadas, mas não garantem correção absoluta.
10. **Avaliações automáticas e humanas são complementares.** Métricas automáticas ajudam na escala; avaliação humana é importante para critérios subjetivos.


# Revisão rápida para a prova

1. **Amazon Bedrock** permite construir aplicações de IA Generativa com diferentes Foundation Models.
2. **Fine-Tuning** adapta o comportamento ou desempenho do modelo para uma tarefa específica.
3. **RAG** conecta o modelo a informações externas ou atualizadas.
4. **Agentes** coordenam e executam tarefas em várias etapas.
5. **Embeddings** representam significado em vetores e apoiam busca semântica.
6. **Tokenização** divide entradas e saídas em tokens e influencia o custo.
7. **Guardrails** aplicam controles e ajudam a reduzir conteúdo inadequado e alucinações.
8. **Temperatura** controla diversidade e criatividade.
9. **Top K** limita uma quantidade fixa de tokens candidatos.
10. **Top P** limita candidatos por probabilidade acumulada.
11. **Zero-shot** não fornece exemplo; **few-shot** fornece alguns exemplos.
12. **ROUGE**, **BLEU**, **BERTScore** e **perplexidade** são métricas de avaliação.
13. **Quanto menor a perplexidade, melhor** a previsão do próximo token.
14. **Sob demanda** é adequado para flexibilidade e ausência de compromisso de longo prazo.
15. **Tokens de entrada e saída** são fatores centrais no custo do Bedrock.