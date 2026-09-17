# Resumo de Estudo – Aula 03 AWS AI Practitioner (AIF-C01)

## Visão Geral

A aula aborda Amazon Q, conceitos de IA, Machine Learning, Redes Neurais, IA Generativa, tipos de aprendizado de máquina e principais serviços de IA da AWS.

## 1. Amazon Q

### Amazon Q Business

- Assistente de IA generativa para uso corporativo, com foco em conhecimento interno.
- Realiza perguntas e respostas, resumos, geração de conteúdo e automações baseadas em dados da empresa.
- Utiliza modelos fundacionais por meio do Amazon Bedrock.
- Respeita permissões de acesso dos usuários e integra-se ao IAM Identity Center.
- Permite controles administrativos, incluindo guardrails e políticas de acesso.

### Amazon Q Developer

- Auxilia desenvolvedores.
- Sugere código em tempo real.
- Ajuda em troubleshooting, custos AWS e documentação.
- Integra-se a IDEs como VS Code, Visual Studio e JetBrains.

### PartyRock

- Ambiente para experimentação com IA Generativa.
- Interface semelhante ao Amazon Q.

---

## 2. Inteligência Artificial (IA)

IA é a área que desenvolve sistemas capazes de executar tarefas normalmente associadas à inteligência humana.

Capacidades:

- Percepção
- Raciocínio
- Aprendizagem
- Resolução de problemas
- Tomada de decisão

### Componentes da IA

1. Camada de Dados
2. Frameworks e Algoritmos
3. Modelos
4. Aplicações

---

## 3. Machine Learning (ML)

ML é um subconjunto da IA que aprende padrões a partir dos dados sem programação explícita de regras.

### IA x ML

- IA = campo amplo.
- ML = mecanismo de aprendizado baseado em dados.

---

## 4. Redes Neurais

- Composta por nós organizados em camadas.
- Aprende padrões identificando relações nos dados.
- Utilizada em reconhecimento de imagens, voz e linguagem.

### Exemplo

Reconhecimento de dígitos manuscritos.

---

## 5. IA Generativa (GenAI)

Subcategoria da IA que usa modelos fundacionais para gerar conteúdo novo, como texto, imagens, áudio e código.

Casos de uso:

- Geração de texto
- Resumos
- Extração de informações
- Geração de imagens
- Chatbots
- Perguntas e respostas

### Transformers e LLMs

Os Transformers são a arquitetura base de muitos modelos modernos de linguagem. Os LLMs (Large Language Models) são modelos grandes treinados com grandes volumes de texto e capazes de entender contexto e gerar textos coerentes.

Características:

- Processam frases inteiras.
- Entendem contexto.
- Geram texto semelhante ao humano.

Exemplos:

- ChatGPT → modelo generativo de texto.
- BERT → modelo de compreensão de linguagem, mais focado em representação/contexto do que em geração direta.

### Modelos de Difusão

Utilizados para geração de imagens.

### Modelos Multimodais

Aceitam múltiplos tipos de entrada e saída:

- Texto
- Imagem
- Áudio
- Vídeo

---

## 6. Conceitos Importantes para a Prova

### Modelos conhecidos

- GPT → geração de texto.
- BERT → entendimento bidirecional.
- RNN → séries temporais e fala.
- ResNet → visão computacional.
- SVM → classificação e regressão.
- WaveNet → síntese de voz.
- GAN → dados sintéticos.
- XGBoost → ensemble/boosting.

---

## 7. Dados para Treinamento

Princípio:
> Garbage In, Garbage Out (GIGO)

### Dados Rotulados

Possuem entrada e resposta correta.

- Usados em aprendizado supervisionado.

### Dados Não Rotulados

Sem resposta conhecida.

- Usados em aprendizado não supervisionado.

### Dados Estruturados

- Tabelas
- Séries temporais

### Dados Não Estruturados

- Textos
- Imagens
- Áudios
- Vídeos

---

## 8. Tipos de Aprendizado de Máquina

### Aprendizado Supervisionado

Dados rotulados.

#### Regressão

Prevê valores contínuos.
Exemplos:

- Preço de imóveis
- Temperatura
- Mercado financeiro

#### Classificação

Prevê categorias.
Exemplos:

- Spam
- Fraudes
- Diagnósticos

### Aprendizado Não Supervisionado

Dados sem rótulos.

Técnicas:

- Clustering
- Regras de Associação
- Detecção de Anomalias

Exemplos:

- Segmentação de clientes
- Cesta de compras
- Fraudes

### Aprendizado Semi-Supervisionado

Combina pequena quantidade de dados rotulados e muitos não rotulados.

### Aprendizado Auto-Supervisionado

O próprio modelo cria alvos a partir dos próprios dados, sem rótulos humanos explícitos.

É usado como base para pré-treinamento de muitos LLMs, como GPT e BERT.

### Aprendizado por Reforço (RL)

Aprende por recompensas.

Conceitos:

- Agente
- Ambiente
- Estado
- Ação
- Recompensa
- Política

### RLHF

Reinforcement Learning from Human Feedback.

Objetivo:

- Alinhar respostas da IA ao julgamento humano.
- Muito utilizado em LLMs.

---

## 9. Treinamento, Validação e Teste

### Treinamento

60–80%

### Validação

10–20%

### Teste

10–20%

---

## 10. Feature Engineering

Transformação de dados para melhorar o desempenho dos modelos.

Técnicas:

- Extração de atributos
- Seleção de atributos
- Transformação de atributos

---

## 11. Ajuste de Modelo

### Overfitting

- Vai muito bem no treino.
- Vai mal em dados novos.

### Underfitting

- Vai mal até durante o treino.
- Modelo simples demais.

### Modelo Balanceado

- Bom equilíbrio entre generalização e aprendizado.

---

## 12. Bias e Variância

### Bias (Viés)

- Erro sistemático.
- Associado a underfitting.

### Variância

- Sensibilidade excessiva ao conjunto de treino.
- Associada a overfitting.

---

## 13. Métricas

### Matriz de Confusão

Métrica usada para avaliar classificadores.

- TP (True Positive) → positivo corretamente previsto.
- FP (False Positive) → negativo incorretamente previsto como positivo.
- TN (True Negative) → negativo corretamente previsto.
- FN (False Negative) → positivo incorretamente previsto como negativo.

### AUC-ROC

- Mede a capacidade do modelo de separar classes.
- Próximo de 1 = excelente discriminabilidade.
- Próximo de 0,5 = desempenho próximo ao aleatório.

---

## 14. Inferência

### Tempo Real

- Chatbots
- Respostas imediatas

### Batch

- Grandes volumes de dados processados em lote.
- Foco em throughput, eficiência e custo, não necessariamente em resposta imediata.

---

## 15. Hyperparameter Tuning

Exemplos de hiperparâmetros:

- Learning Rate
- Batch Size
- Épocas
- Regularização

Técnicas:

- Grid Search
- Random Search
- SageMaker Automatic Model Tuning

---

## 16. Quando NÃO usar ML?

Prefira algoritmos tradicionais quando:

- O problema é determinístico.
- Existe uma regra ou fórmula exata para resolvê-lo.
- A solução precisa ser precisa e explicável sem depender de aproximações.

ML é mais adequado quando o problema envolve padrões complexos, dados e necessidade de generalização.

---

## Serviços de IA AWS para Memorizar

| Serviço | Função Principal |
| ---------- | ------------------ |
| Amazon Comprehend | NLP, análise de sentimento e extração de entidades |
| Amazon Translate | Tradução |
| Amazon Transcribe | Áudio → Texto |
| Amazon Polly | Texto → Voz |
| Amazon Rekognition | Imagens e vídeos |
| Amazon Lex | Chatbots |
| Amazon Personalize | Recomendações |
| Amazon Textract | Extração de texto de documentos |
| Amazon Kendra | Busca inteligente sobre documentos e dados corporativos |

---

## Dicas para a Prova

1. Q Business = conhecimento corporativo.
2. Q Developer = desenvolvimento.
3. Comprehend = NLP.
4. Transcribe = fala para texto.
5. Polly = texto para fala.
6. Rekognition = visão computacional.
7. Lex = chatbot.
8. Personalize = recomendações.
9. RLHF aparece frequentemente em questões sobre alinhamento de LLMs.
10. Saber diferenciar:

- Supervisionado
- Não supervisionado
- Reforço
- Semi-supervisionado
- Auto-supervisionado
