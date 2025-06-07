# 🧠 Análise de Sentimentos com Language Studio no Azure AI

Este guia mostra como realizar uma **Análise de Sentimentos** usando o **Language Studio**, uma plataforma de inteligência artificial do Azure. Essa ferramenta permite classificar automaticamente o tom emocional de textos — útil para empresas, desenvolvedores e analistas de dados.

> 💡 Ideal para feedbacks de clientes, comentários em redes sociais, análises de produtos e pesquisas de opinião.

---

## 📌 O que é a Análise de Sentimentos?

A **Análise de Sentimentos** é uma técnica de **Processamento de Linguagem Natural (PLN)** usada para identificar emoções em textos. Ela classifica conteúdos como:

- **Positivo**
- **Negativo**
- **Neutro**
- **Misto**

Com base em um modelo de aprendizado de máquina, o Azure AI retorna **pontuações de confiança** para cada tipo de sentimento.

---

## ✅ Pré-requisitos

- Conta no [Portal do Azure](https://portal.azure.com)
- Acesso ao serviço **Azure AI Language**
- Navegador moderno (Edge, Chrome, Firefox)
- Textos ou arquivos para análise
- Azure Data Studio ou SQL Server Management Studio (opcional)

---

## 🧪 Etapa 1: Acessando o Language Studio

1. Acesse: [https://language.azure.com](https://language.azure.com)
2. Faça login com sua conta Azure.
3. No painel principal, selecione **"Sentiment Analysis"**.
4. Clique em **"Try it out"** para testar com textos de exemplo ou seus próprios.

---

## 📝 Etapa 2: Inserindo o Texto

1. No campo de entrada, digite ou cole o texto que deseja analisar.
2. Clique em **"Run"**.
3. Os resultados aparecem com uma análise detalhada por frase, como:
```
json
{
  "sentiment": "positive",
  "confidenceScores": {
    "positive": 0.95,
    "neutral": 0.04,
    "negative": 0.01
  }
}
```
✅ Quanto maior o valor, maior a confiança do modelo naquele tipo de sentimento.

## 📂 Etapa 3: Criar um Projeto com Arquivo CSV
Você pode processar textos em lote com arquivos .csv ou .json.

Criando o projeto:
Vá para Projects > Create project.

Escolha o tipo: "Text classification" > "Sentiment Analysis".

Nomeie o projeto (ex: analise_feedback).

Faça o upload do seu dataset.


Exemplo de CSV:
```
csv
Copiar
Editar
id,text
1,"A experiência foi incrível, adorei o suporte!"
2,"Demoraram demais para me atender, não gostei."
3,"Achei razoável, nada de especial."
🌐 Etapa 4: Configurando Acesso à API (Opcional)
Se desejar usar via API:
```

Crie um recurso Azure AI Language no Portal do Azure.

Copie a chave de acesso (API Key) e o endpoint.

Faça chamadas via código (ex: Python, C#, etc.).

Exemplo com curl:
```
´´bash
Copiar
Editar
curl -X POST "https://<SEU-ENDPOINT>/language/:analyze-text?api-version=2023-04-01" \
-H "Ocp-Apim-Subscription-Key: <SUA-CHAVE>" \
-H "Content-Type: application/json" \
-d '{
  "kind": "SentimentAnalysis",
  "parameters": {
    "text": "O produto é ótimo, recomendo para todos.",
    "language": "pt"
  }
}
```


## 📊 Etapa 5: Usos Comuns da Análise de Sentimentos
Área	Aplicações típicas
Atendimento ao cliente	Classificação de feedbacks
Marketing	Análise de menções em redes sociais
Produtos	Avaliações de usuários em apps e lojas
Pesquisa	Resultados de enquetes e formulários
Recursos Humanos	Termômetro do clima organizacional

🛡️ Boas Práticas de Segurança
✅ Use Private Endpoints para produção.

🔐 Armazene dados sensíveis com criptografia (em repouso e em trânsito).

🎯 Controle o acesso com RBAC e Azure Policy.

📜 Ative logs e auditorias via Azure Monitor ou Defender for Cloud.

📚 Recursos Recomendados
Documentação oficial do Azure AI Language

API REST para Análise de Sentimentos

Azure AI Studio - Visão Geral

✅ Conclusão
Você aprendeu a realizar uma análise de sentimentos com o Language Studio do Azure AI de forma prática e sem necessidade de código. É uma ferramenta poderosa para explorar textos e extrair emoções de forma automatizada.

🚀 Experimente também outros recursos do Azure AI como Extração de Entidades, Mineração de Opiniões e Detecção de Idioma!


