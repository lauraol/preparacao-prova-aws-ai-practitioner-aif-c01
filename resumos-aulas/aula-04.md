# Resumo de Estudo – Aula 04

## AWS Certified AI Practitioner (AIF-C01)

**Fonte:** Aula 04 - IA.pptx  
**Temas centrais:** Amazon SageMaker, IA Responsável, Governança, Conformidade e riscos da IA Generativa.

---

## 1. Amazon SageMaker

O **Amazon SageMaker** é um serviço totalmente gerenciado para desenvolver, treinar, implantar e monitorar modelos de Machine Learning. Ele centraliza o ciclo de vida de ML e reduz a necessidade de provisionar e administrar infraestrutura manualmente.

### Fluxo de ML de ponta a ponta

1. Buscar, limpar e preparar dados.
2. Construir e treinar o modelo.
3. Avaliar os resultados.
4. Implantar o modelo.
5. Monitorar seu funcionamento em produção.

### Problemas que o SageMaker ajuda a resolver

- Falta de conhecimento especializado em ML.
- Dificuldade de implantação de modelos em produção.
- Limitações de escalabilidade.
- Custos elevados de infraestrutura.
- Complexidade na preparação e no gerenciamento dos dados.
- Requisitos de governança, segurança e conformidade.

---

## 2. Algoritmos integrados

O SageMaker disponibiliza algoritmos para diferentes tipos de problema:

### Supervisionados

Treinados com dados rotulados.

- Regressão linear.
- Classificação.
- K-Nearest Neighbors, ou KNN, para classificação e regressão.

### Não supervisionados

Treinados com dados não rotulados.

- **PCA:** reduz o número de features.
- **K-means:** identifica agrupamentos nos dados.
- Detecção de anomalias.

### Outros casos

- Processamento de linguagem natural.
- Sumarização.
- Classificação e detecção em imagens.

---

## 3. Automatic Model Tuning (AMT)

O **SageMaker Automatic Model Tuning** automatiza o ajuste de hiperparâmetros.

### Funcionamento

- Define-se uma métrica objetivo.
- O AMT seleciona faixas de hiperparâmetros.
- Define estratégia de busca.
- Controla o tempo máximo do job.
- Pode aplicar parada antecipada.

### Benefícios

- Redução de esforço manual.
- Economia de tempo e custos.
- Menor risco de manter configurações subótimas.

---

## 4. Tipos de inferência e implantação

### Inferência em tempo real

- Baixa latência.
- Processa uma previsão por vez.
- Indicada para aplicações web e mobile que precisam de respostas rápidas.
- Payload de até 25 MB por registro.
- Processamento de até 60 segundos.

### Inferência serverless

- Não exige gerenciamento de servidores.
- Escala automaticamente.
- Indicada para uso esporádico e períodos de ociosidade.
- Pode apresentar cold start.
- Payload de até 4 MB por registro.
- Processamento de até 60 segundos.

### Inferência assíncrona

- Adequada para payloads grandes e processamento demorado.
- Não é voltada para resposta imediata; o cliente recebe o resultado após o processamento.
- Requisições e respostas ficam no Amazon S3.
- Payload de até 1 GB por registro.
- Processamento de até uma hora.

### Batch Transform

- Processa um dataset inteiro.
- Adequado para múltiplas previsões em lote.
- Entradas e saídas ficam no Amazon S3.
- Payload de até 100 MB por mini lote.
- Processamento de até uma hora.

### Como escolher

| Necessidade | Tipo recomendado |
| --- | --- |
| Resposta imediata e tráfego constante | Tempo real |
| Uso esporádico e tolerância a cold start | Serverless |
| Arquivo grande ou processamento demorado | Assíncrona |
| Dataset completo e processamento em massa | Batch Transform |

---

## 5. SageMaker Studio

O **SageMaker Studio** oferece uma interface unificada para:

- Desenvolvimento de ML de ponta a ponta.
- Colaboração entre equipes.
- Ajuste e depuração de modelos.
- Implantação.
- Automação de fluxos de trabalho.

---

## 6. SageMaker Data Wrangler

Ferramenta para preparação de dados tabulares, texto e imagens.

### Recursos

- Seleção e importação de dados.
- Limpeza e exploração.
- Visualização.
- Transformação e processamento.
- Engenharia de features.
- Suporte a SQL.
- Verificação de qualidade de dados.
- Criação de um modelo rápido, o Quick Model.
- Exportação do fluxo de dados.

---

## 7. Features e Feature Store

### Features

São as entradas usadas pelo modelo durante treinamento e inferência. Features de boa qualidade favorecem desempenho, consistência e reutilização.

### SageMaker Feature Store

- Repositório centralizado de features.
- Compartilha dados entre treinamento e inferência.
- Permite definir transformações.
- Recebe features publicadas pelo Data Wrangler.
- Torna as features localizáveis no SageMaker Studio.

---

## 8. SageMaker Clarify

O **SageMaker Clarify** trabalha principalmente com avaliação, explicabilidade e detecção de viés.

### Avaliação de Foundation Models

- Avalia modelos fundacionais.
- Pode usar avaliações humanas ou métricas integradas.
- Permite usar datasets integrados ou próprios.
- Faz parte do SageMaker Studio.

### Explicabilidade

Ajuda a entender:

- Como o modelo realiza previsões.
- Quais features influenciam o resultado.
- Por que uma previsão foi negativa ou incorreta.
- Como o modelo se comporta antes e depois da implantação.

### Detecção de viés

- Detecta viés em datasets e modelos.
- Usa métricas estatísticas.
- Analisa as features indicadas.

---

## 9. Tipos de viés

### Viés de amostragem

Os dados não representam adequadamente a população e podem favorecer ou prejudicar grupos.

### Viés de medição

Ferramentas ou métodos usados na coleta produzem dados falhos ou distorcidos.

### Viés do observador

As crenças da pessoa que coleta ou interpreta os dados influenciam o resultado.

### Viés de confirmação

Informações que confirmam crenças prévias recebem mais atenção. Está mais associado à decisão humana.

### Possível mitigação

Quando classes estão desbalanceadas, pode-se usar **data augmentation** para aumentar a representação dos grupos com poucos exemplos.

---

## 10. SageMaker Ground Truth e RLHF

O **SageMaker Ground Truth** oferece suporte à rotulagem, revisão e avaliação humana.

### Possibilidades

- Criar labels para dados.
- Revisar e avaliar modelos.
- Alinhar modelos às preferências humanas.
- Envolver funcionários, terceiros ou trabalhadores do Amazon Mechanical Turk.
- Utilizar Ground Truth Plus como serviço gerenciado de rotulagem.

### RLHF

**Reinforcement Learning from Human Feedback** incorpora feedback humano à função de recompensa para melhorar o alinhamento do modelo com preferências e objetivos humanos.

---

## 11. Governança de ML no SageMaker

### Model Cards

Documentam informações essenciais do modelo:

- Uso pretendido.
- Classificação de risco.
- Detalhes do treinamento.

### Model Dashboard

- Centraliza a visualização dos modelos.
- Mostra modelos implantados para inferência.
- Ajuda a identificar violações de limites de qualidade, viés e explicabilidade.

### Role Manager

Define papéis e permissões para diferentes personas, como cientistas de dados e engenheiros de MLOps.

### Model Monitor

- Monitora continuamente ou de forma agendada os modelos em produção.
- Detecta desvios de qualidade e drift.
- Gera alertas que podem indicar necessidade de corrigir dados e retreinar o modelo.

### Model Registry

- Cataloga e versiona modelos.
- Armazena metadados.
- Gerencia aprovação.
- Apoia automação da implantação e compartilhamento.

---

## 12. SageMaker Pipelines

O **SageMaker Pipelines** é um recurso de CI/CD para Machine Learning. Automatiza construção, treinamento, teste e implantação de modelos.

### Principais etapas

- **Processing:** processamento e engenharia de features.
- **Training:** treinamento.
- **Tuning:** ajuste de hiperparâmetros.
- **AutoML:** treinamento automático.
- **Model:** criação ou registro do modelo.
- **ClarifyCheck:** verifica drift de viés e explicabilidade.
- **QualityCheck:** verifica drift de qualidade dos dados e do modelo.

---

## 13. JumpStart, Canvas e MLflow

### SageMaker JumpStart

- Hub de modelos e soluções pré-construídas.
- Contém Foundation Models e modelos de visão computacional e NLP.
- Inclui modelos de fornecedores como Hugging Face, Meta, Databricks e Stability AI.
- Permite personalização e implantação na VPC.
- Oferece soluções para previsão de demanda, risco de crédito e detecção de fraude.

### SageMaker Canvas

- Interface visual no-code.
- Permite construir modelos sem escrever código.
- Acessa modelos do Bedrock e do JumpStart.
- Usa AutoML por meio do SageMaker Autopilot.
- Integra-se ao Data Wrangler.
- Pode usar modelos prontos do Rekognition, Comprehend e Textract.

### MLflow no SageMaker

- Gerencia o ciclo de vida de ML.
- Rastreia experimentos e execuções.
- Usa MLflow Tracking Servers integrados ao SageMaker Studio.

---

## 14. Recursos adicionais

### Network Isolation

Executa containers de jobs sem acesso de saída à internet. Nesse modo, eles também não acessam diretamente o Amazon S3.

### SageMaker DeepAR

- Algoritmo de previsão de séries temporais.
- Utiliza redes neurais recorrentes, ou RNNs.

---

## 15. IA Responsável, segurança, governança e conformidade

### IA Responsável

Busca sistemas transparentes e confiáveis, com mitigação de riscos durante todo o ciclo de vida: design, desenvolvimento, implantação, monitoramento e avaliação.

### Segurança

Protege:

- Confidencialidade.
- Integridade.
- Disponibilidade.
- Dados, ativos de informação e infraestrutura.

### Governança

Define políticas, diretrizes e supervisão para gerar valor, gerenciar riscos e alinhar sistemas a requisitos legais e regulatórios.

### Conformidade

Garante aderência a regulamentações e diretrizes, especialmente em áreas sensíveis como saúde, finanças e aplicações jurídicas.

---

## 16. Dimensões da IA Responsável

- **Justiça:** inclusão e prevenção de discriminação.
- **Explicabilidade:** capacidade de explicar resultados.
- **Privacidade e segurança:** proteção e controle do uso dos dados.
- **Transparência:** clareza sobre funcionamento e uso.
- **Veracidade e robustez:** confiabilidade inclusive em situações inesperadas.
- **Governança:** definição e aplicação de práticas responsáveis.
- **Safety:** algoritmos seguros e benéficos.
- **Controlabilidade:** alinhamento a valores e intenções humanas.

---

## 17. Serviços AWS relacionados à IA Responsável

- **Amazon Bedrock:** avaliação humana ou automática de modelos.
- **Guardrails for Amazon Bedrock:** bloqueio de tópicos, filtragem de conteúdo nocivo e ocultação de PII.
- **SageMaker Clarify:** avaliação, explicabilidade e detecção de viés.
- **SageMaker Data Wrangler:** balanceamento e correção dos dados.
- **SageMaker Model Monitor:** acompanhamento de qualidade em produção.
- **Amazon Augmented AI (A2I):** revisão humana de previsões.
- **Role Manager, Model Cards e Model Dashboard:** governança.

### AWS AI Service Cards

Documentam:

- Casos de uso pretendidos.
- Limitações.
- Escolhas de design responsável.
- Boas práticas de implantação e otimização.

---

## 18. Interpretabilidade x Explicabilidade

### Interpretabilidade

É o grau em que uma pessoa consegue compreender a causa de uma decisão e responder diretamente “como” e “por que” o modelo tomou determinada decisão.

Em geral, interpretabilidade está mais associada a modelos mais simples ou a explicações diretas sobre o processo de decisão.

### Explicabilidade

Permite compreender a natureza e o comportamento do modelo por meio das entradas e saídas, mesmo sem conhecer exatamente seu mecanismo interno.

Ela é especialmente útil para modelos complexos, como redes neurais, e pode ser obtida por meio de técnicas de análise pós-hoc.

### Trade-off

Maior transparência e interpretabilidade podem resultar em menor desempenho. Em alguns casos, explicabilidade suficiente é mais prática do que interpretabilidade total.

### Árvores de decisão

- Alta interpretabilidade.
- Usadas em classificação e regressão.
- Dividem dados em ramos com base nas features.
- Podem sofrer overfitting quando possuem ramos em excesso.

### Partial Dependence Plots (PDP)

- Mostram o efeito de uma feature sobre a previsão.
- Mantêm as demais features constantes.
- São úteis para modelos considerados caixa-preta, como redes neurais.

---

## 19. Human-Centered Design (HCD)

Abordagem que prioriza as necessidades humanas no projeto de sistemas de IA.

Princípios:

- Clareza, simplicidade e usabilidade.
- Redução de riscos em situações de alta pressão.
- Reflexão e responsabilização pelo processo decisório.
- Decisões livres de viés.
- Treinamento de pessoas para reconhecer vieses.
- Aprendizado conjunto entre humanos e IA.
- Personalização e acessibilidade.

---

## 20. Capacidades e desafios da IA Generativa

### Capacidades

- Adaptabilidade.
- Responsividade.
- Simplicidade.
- Criatividade e exploração.
- Eficiência no uso de dados.
- Personalização.
- Escalabilidade.

### Desafios

- Violações regulatórias.
- Riscos sociais.
- Segurança e privacidade.
- Toxicidade.
- Alucinações.
- Baixa interpretabilidade.
- Não determinismo.
- Plágio e fraude.

---

## 21. Toxicidade, alucinação, plágio e fraude

### Toxicidade

Conteúdo ofensivo, perturbador ou inapropriado.

Mitigações:

- Curadoria dos dados de treinamento.
- Remoção de expressões ofensivas.
- Uso de guardrails para detectar e filtrar conteúdo.

### Alucinações

Afirmações incorretas que parecem verdadeiras. Podem surgir porque LLMs selecionam a próxima palavra por probabilidade.

Mitigações:

- Orientar usuários a verificar as respostas.
- Consultar fontes independentes.
- Identificar conteúdo gerado como não verificado quando necessário.

### Plágio e fraude

Uso de conteúdo gerado sem atribuição, por exemplo em trabalhos acadêmicos ou candidaturas. A origem exata de uma saída de LLM pode ser difícil de rastrear.

---

## 22. Ataques e usos indevidos de prompts

### Data Poisoning

Introdução de dados maliciosos ou enviesados no treinamento para influenciar as saídas do modelo.

### Prompt Injection e Hijacking

Inserção de instruções no prompt para sequestrar o comportamento do modelo e direcioná-lo às intenções do atacante.

### Exposure

Exposição de informações sensíveis ou confidenciais durante treinamento ou inferência.

### Prompt Leaking

Divulgação não intencional de prompts, entradas, instruções internas ou dados protegidos.

### Jailbreaking

Tentativa de contornar restrições éticas e controles de segurança para obter conteúdo ou funcionalidades não autorizados.

---

## 23. Cargas de trabalho reguladas

Setores como serviços financeiros, saúde e aeroespacial podem demandar controles adicionais.

Características:

- Auditoria.
- Arquivamento.
- Relatórios periódicos.
- Requisitos especiais de segurança.
- Explicabilidade e rastreabilidade de decisões reguladas.

### Desafios de conformidade

- Complexidade e opacidade dos modelos.
- Mudanças do sistema ao longo do tempo.
- Capacidades emergentes e não planejadas.
- Viés algorítmico e humano.
- Privacidade e desinformação.
- Necessidade de responsabilização algorítmica.

### Referenciais citados na aula

- NIST.
- ENISA.
- ISO.
- SOC.
- HIPAA.
- GDPR.
- PCI DSS.

---

## 24. Mapa rápido para a prova

| Se a questão mencionar... | Lembre-se de... |
| --- | --- |
| Ciclo completo de ML | SageMaker |
| Preparação e transformação de dados | Data Wrangler |
| Reutilização centralizada de features | Feature Store |
| Ajuste automático de hiperparâmetros | Automatic Model Tuning |
| Viés e explicabilidade | Clarify |
| Rotulagem e feedback humano | Ground Truth |
| Documentação do modelo | Model Cards |
| Visualização central dos modelos | Model Dashboard |
| Drift e qualidade em produção | Model Monitor |
| Versionamento e aprovação | Model Registry |
| CI/CD de ML | Pipelines |
| Modelos e soluções pré-treinados | JumpStart |
| Criação de ML sem código | Canvas |
| Experimentos e execuções | MLflow |
| Revisão humana de previsões | Amazon A2I |
| Controles de conteúdo e PII | Guardrails for Amazon Bedrock |
| Previsão de séries temporais | DeepAR |

---

## 25. Pegadinhas e pontos de atenção

1. **Clarify não monitora drift continuamente:** essa função é do Model Monitor.
2. **Model Registry não é painel de visualização:** ele cataloga e versiona modelos.
3. **Data Wrangler prepara dados:** o Feature Store centraliza e reutiliza features.
4. **Ground Truth envolve seres humanos:** é associado à rotulagem, avaliação e RLHF.
5. **JumpStart fornece modelos e soluções prontas:** Canvas é a interface no-code.
6. **Inference serverless pode ter cold start:** tempo real é melhor para respostas constantemente rápidas.
7. **Batch Transform trabalha com conjuntos de dados:** assíncrona é adequada para requisições individuais grandes ou demoradas.
8. **Interpretabilidade e explicabilidade não são sinônimos:** interpretabilidade busca compreender como a decisão foi formada; explicabilidade descreve o comportamento por entradas e saídas.
9. **Alucinação não é toxicidade:** alucinação é uma resposta plausível, porém incorreta; toxicidade é conteúdo ofensivo ou inadequado.
10. **Prompt injection não é data poisoning:** injection ocorre nas instruções de entrada; poisoning compromete dados de treinamento.

---

## 26. Questões da aula e respostas

### Questão 1

**Cenário:** implantar e consumir rapidamente um Foundation Model dentro da VPC.

**Resposta:** Amazon SageMaker JumpStart.

### Questões 2 e 3

**Cenário:** modelo médico precisa ser transparente e explicável para atender requisitos regulatórios.

**Resposta:** SageMaker Clarify.

### Questão 4

**Cenário:** estudante copia conteúdo de IA generativa para escrever redações.

**Conceito correto:** plágio.

> Atenção: o slide apresenta inconsistência na marcação da alternativa final. Pelo enunciado e pelas próprias opções, o conceito é **plágio**, correspondente à alternativa **C**.

---

## Checklist final

Antes da prova, confirme se você consegue explicar:

- [ ] O ciclo de ML no SageMaker.
- [ ] A diferença entre Data Wrangler e Feature Store.
- [ ] Quando usar inferência real-time, serverless, assíncrona ou batch.
- [ ] As diferenças entre Clarify, Ground Truth e Model Monitor.
- [ ] As funções de Model Cards, Dashboard, Registry e Pipelines.
- [ ] As diferenças entre JumpStart e Canvas.
- [ ] As dimensões da IA Responsável.
- [ ] Interpretabilidade versus explicabilidade.
- [ ] Toxicidade, alucinação, plágio e não determinismo.
- [ ] Poisoning, prompt injection, exposure, prompt leaking e jailbreaking.
- [ ] Os principais requisitos de governança e conformidade.
