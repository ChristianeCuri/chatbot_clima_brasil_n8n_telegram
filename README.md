# Chatbot Clima Brasil — Telegram + N8N

Bot para Telegram que informa a temperatura atual de qualquer cidade do Brasil, construído com **N8N** e a **API do OpenWeatherMap**.


## 1- Como funciona
O usuário envia uma mensagem via telegram para o bot com o nome da cidade e recebe uma resposta com as condições climáticas atuais, conforme o exemplo a seguir:

**Usuário:** 
/tempo São Paulo
OU
São Paulo

**Bot:**
☀️ Clima em São Paulo

🌡️ Temperatura: 24°C

🤔 Sensação térmica: 26°C

⬇️ Mínima: 20°C  |  ⬆️ Máxima: 28°C

💧 Umidade: 70%

💨 Vento: 12.6 km/h

📋 Condição: céu limpo


## 2- Estrutura do Workflow

```mermaid
flowchart LR
    A([📨 Telegram Trigger]) --> B([🔍 Extrair Cidade])
    B --> C{Cidade Informada?}
    C -->|sim| D([🌐 Buscar Clima])
    C -->|não| E([💬 Mensagem de Ajuda])
    D --> F([✏️ Formatar Resposta])
    F --> G([📤 Enviar Clima])
    E --> H([📤 Enviar Ajuda])
```

## 3- Pré-requisitos
- n8n instalado
- Conta no OpenWeatherMap
- Bot criado no Telegram 
- Ferramentas para rodar localmente ou em servidor
