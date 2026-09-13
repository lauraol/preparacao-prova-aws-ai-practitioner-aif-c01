# 📚 Resumo de Estudo – Aula 01 | AWS Certified AI Practitioner (AIF-C01)

## 🎯 1. Estrutura da Certificação AWS

A AWS possui quatro níveis principais de certificação:

1. Foundational
2. Associate
3. Professional
4. Specialty

---

## 🤖 2. O que é Inteligência Artificial (IA)?

IA é a área da computação que busca simular capacidades humanas, como:

- Aprendizagem
- Tomada de decisão
- Reconhecimento de padrões
- Resolução de problemas

Exemplos de uso:

- Reconhecimento de imagens
- Conversão de áudio em texto
- Geração de conteúdo
- Previsões baseadas em dados

---

## 🧠 3. IA x Machine Learning x Deep Learning

Uma das figuras mais importantes da aula mostra a hierarquia entre os conceitos:

- IA (Artificial Intelligence): conceito mais amplo.
- Machine Learning (ML): subárea da IA que permite às máquinas aprenderem com dados.
- Deep Learning (DL): subárea do ML baseada em redes neurais profundas.
- Generative AI: subárea do Deep Learning focada na geração de novos conteúdos.

Decore a relação:

> IA → ML → Deep Learning → Generative AI

---

## ☁️ 4. Cloud Computing

Definição AWS:

> Entrega de recursos computacionais pela internet utilizando modelo de pagamento conforme o uso (pay-as-you-go).

### Benefícios mais cobrados

1. Troca CAPEX (Capital Expenditure, você comprava servidores e infraestrutura própria) por OPEX (Operational Expenditure, usa serviços na nuvem e paga apenas pelo que consome).
2. Economia de escala
3. Não precisar estimar capacidade futura
4. Maior velocidade e agilidade
5. Eliminação da gestão de datacenters
6. Alcance global em minutos

Memorize os 6 benefícios. A AWS costuma cobrar exatamente essa lista.

---

## 🏗️ 5. Modelos de Serviço Cloud

### IaaS (Infrastructure as a Service)

Fornece:

- Rede
- Servidores
- Armazenamento

Maior controle e flexibilidade.

### PaaS (Platform as a Service)

Fornece:

- Infraestrutura gerenciada
- Ambiente para desenvolvimento e implantação

Você foca na aplicação.

### SaaS (Software as a Service)

Produto pronto para uso.

Exemplos conhecidos:

- Gmail
- Office 365
- Salesforce

---

## 🌎 6. Infraestrutura Global AWS

Tópico muito importante para a prova.

### Região (Region)

- Área geográfica
- Contém múltiplas AZs

### Zona de Disponibilidade (AZ)

- Um ou mais datacenters
- Isolamento físico
- Alta disponibilidade

### Edge Location

- Ponto de presença
- Menor latência
- Utilizado por serviços como CloudFront

### Resumo rápido

| Termo | Função |
|---|---|
| Região | Área geográfica |
| AZ | Datacenters redundantes |
| Edge Location | Entrega rápida de conteúdo |

---

## 🔐 7. IAM (Identity and Access Management)

Serviço responsável por:

- Usuários
- Grupos
- Permissões
- Controle de acesso

### Conceitos cobrados

#### Princípio do Menor Privilégio

O usuário deve possuir apenas as permissões necessárias para executar sua função.

#### MFA

Multi-Factor Authentication, camada adicional de segurança.

#### IAM User

Representa uma pessoa ou aplicação.

#### IAM Group

Coleção de usuários com permissões semelhantes.

#### Root User

- ✅ Evitar uso diário.
- ✅ Ativar MFA.
- ✅ Não compartilhar credenciais.

Esses pontos aparecem frequentemente em simulados AWS.

---

## ✨ 8. IA Generativa (Generative AI)

Definição:

> Tecnologia capaz de criar novos conteúdos semelhantes aos dados utilizados durante o treinamento.

Pode gerar:

- Texto
- Imagem
- Áudio
- Vídeo
- Código

### Casos de uso típicos

- Chatbots
- Resumo de documentos
- Geração de imagens
- Perguntas e respostas
- Extração de informações

Na prova, se a questão envolver criação de conteúdo novo, quase sempre estamos falando de IA Generativa.

---

## 🏛️ 9. Foundation Models (FM)

Conceito fundamental para o exame.

### O que são?

Modelos treinados com enormes volumes de dados que podem ser reutilizados em diversas tarefas.

Exemplos citados:

- GPT
- Claude
- Amazon
- Meta
- Google

### Características

- Treinamento muito caro
- Grande volume de dados
- Reutilização para múltiplas aplicações

Prova: GPT é um exemplo de Foundation Model.

---

## 📖 10. LLM (Large Language Model)

Tipo específico de Foundation Model focado em linguagem humana.

### Características

- Bilhões de parâmetros
- Treinados com livros, artigos e websites
- Especializados em texto

### Usos comuns

- Criação de conteúdo
- Tradução
- Resumo
- Resposta a perguntas

---

## 📝 11. Prompts e Geração Probabilística

Conceito frequentemente cobrado.

Uma LLM:

1. Recebe um prompt
2. Calcula probabilidades para a próxima palavra
3. Escolhe uma das opções mais prováveis

Exemplo da aula:

> "Depois da chuva, as ruas estarão..."

Possíveis respostas:

- Molhadas
- Inundadas
- Escorregadias

Cada uma com uma probabilidade diferente.

### Conceito-chave

As LLMs são:

- ✅ Probabilísticas
- ❌ Não determinísticas

Ou seja, o mesmo prompt pode gerar respostas diferentes.

---

## 🎯 Questões que a AWS Adora Cobrar

### Quando usar IA Generativa?

- ✅ Criar imagens
- ✅ Gerar texto
- ✅ Resumir documentos
- ✅ Criar código

### Quando NÃO é IA Generativa?

- ❌ Banco de dados
- ❌ Indexação
- ❌ Redes
- ❌ Infraestrutura

### O que é um Foundation Model?

- ✅ Modelo base reutilizável treinado com grande volume de dados.

### O que é um LLM?

- ✅ Foundation Model especializado em linguagem humana.

### O que é o princípio do menor privilégio?

- ✅ Conceder apenas as permissões necessárias.

### Diferença entre Região e AZ?

- ✅ Região = local geográfico.
- ✅ AZ = datacenter isolado dentro da região.

---

## 🏆 Decore Antes da Prova

Se você lembrar apenas destes 10 pontos já responderá uma boa parte das questões:

1. IA → ML → Deep Learning → GenAI
2. Generative AI cria conteúdo novo.
3. Foundation Model é o modelo base.
4. GPT é um Foundation Model.
5. LLM é um modelo voltado para linguagem.
6. LLMs são probabilísticas, não determinísticas.
7. Região ≠ AZ ≠ Edge Location.
8. IAM aplica o princípio do menor privilégio.
9. Root User não deve ser usado no dia a dia.
10. Cloud Computing = pay-as-you-go.

Esses são os conceitos centrais desta Aula 01 e servem como base para praticamente todos os domínios da certificação AWS AI Practitioner (AIF-C01).
