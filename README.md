# Análise de Sentimentos com Azure AI Language Studio

- Este repositório contém exemplos e guias para utilizar o Azure AI Language Studio na análise de sentimentos em textos, parte dos Serviços de IA do Azure.

## Visão Geral
 
- O Azure AI Language Studio oferece ferramentas de Processamento de Linguagem Natural (NLP), incluindo Análise de Sentimentos, que permite:

Identificar se um texto tem tom positivo, negativo ou neutro.

Extrair opiniões específicas em frases (análise granular).

Aplicar em avaliações de clientes, redes sociais, suporte ao cliente e mais.

# Documentação Oficial: Azure AI Language Studio

# Como Começar
- Pré-requisitos
Conta no Azure (Crie uma gratuitamente);
Recurso do "Azure AI Language" criado no Portal Azure;
Dados para análise (textos, reviews, tweets, etc.)

# Configuração no Language Studio
- Acesse o Language Studio e faça login.

- Selecione "Análise de Sentimentos" no menu.

- Cole seu texto ou carregue um arquivo (JSON, TXT, etc.).

- Execute a análise e visualize os resultados:

Sentimento geral (positivo/negativo/neutro).

Detalhamento por frase (confiança e polaridade).

## Exemplo de Código (Python com Azure SDK)
python
from azure.ai.textanalytics import TextAnalyticsClient  
from azure.core.credentials import AzureKeyCredential  

# Configuração  
key = "SUA_CHAVE_AZURE"  
endpoint = "SEU_ENDPOINT_AZURE"  

# Autenticação  
client = TextAnalyticsClient(endpoint, AzureKeyCredential(key))  

# Texto para análise  
texts = ["Adorei o produto! Entrega rápida.", "Péssimo atendimento, não recomendo."]  

# Análise de Sentimento  
result = client.analyze_sentiment(texts)  
for doc in result:  
    print(f"Texto: {doc.sentiment} (Confiança: {doc.confidence_scores})")  
Saída:

Texto: positive (Confiança: {'positive': 0.99, 'neutral': 0.01, 'negative': 0.0})  
Texto: negative (Confiança: {'positive': 0.02, 'neutral': 0.1, 'negative': 0.88})  
## Aplicações Comuns
Monitoramento de redes sociais (Twitter, reviews).

Chatbots para identificar frustração do usuário.

Pesquisas de satisfação (NPS, feedback).
