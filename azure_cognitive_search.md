# 🔎 Azure Cognitive Search: Utilizando AI Search para Indexação e Consulta de Dados

O **Azure Cognitive Search** é uma solução completa de busca como serviço (Search-as-a-Service) que permite criar experiências avançadas de pesquisa com suporte a **inteligência artificial**, **linguagem natural** e análise semântica.

> 💡 Ideal para sistemas que precisam de busca personalizada em documentos, sites, bases de conhecimento, arquivos PDF, dados SQL, entre outros.

---

## 📌 O que é o Azure Cognitive Search?

É um serviço gerenciado que permite importar dados, extrair informações relevantes, indexar conteúdo e oferecer uma experiência de busca rápida e inteligente aos usuários. Pode ser enriquecido com **Cognitive Skills**, como análise de sentimentos, OCR, tradução e mais.

---

## ✅ Pré-requisitos

- Conta no [Portal do Azure](https://portal.azure.com)
- Acesso ao serviço **Azure Cognitive Search**
- Uma fonte de dados (como SQL, Blob Storage ou Cosmos DB)
- Permissão para criar recursos no Azure
- JSON ou arquivos de exemplo para testes (PDF, DOCX, CSV)

---

## 🛠️ Etapa 1: Criar um Serviço de Pesquisa

1. Acesse o [Portal do Azure](https://portal.azure.com).
2. Pesquise por **"Cognitive Search"** ou **"Serviço de Pesquisa"**.
3. Clique em **Criar** e preencha os campos:

| Campo               | Valor Exemplo             |
|---------------------|---------------------------|
| **Nome**            | `search-demo`             |
| **Camada de preço** | `Basic` (para testes)     |
| **Grupo de Recursos** | `rg-busca-ai`           |
| **Localização**     | `Brazil South`            |

4. Clique em **Revisar e Criar**.

---

## 📦 Etapa 2: Conectar uma Fonte de Dados

1. Após criado, vá até o serviço de pesquisa.
2. No menu esquerdo, clique em **Importar dados**.
3. Escolha a fonte, por exemplo:

- **Blob Storage** para arquivos PDF, imagens, textos
- **SQL Database** para dados relacionais
- **Cosmos DB** para NoSQL

4. Conceda permissões (via conexão segura ou chave).
5. Avance para definir um **índice**.

---

## 🧠 Etapa 3: Enriquecer com AI (Skillset)

Você pode aplicar **Cognitive Skills** ao pipeline para extrair mais informações. Exemplos:

- Extração de texto com OCR
- Detecção de idioma
- Análise de sentimentos
- Reconhecimento de entidade (pessoas, locais, etc)
- Tradução automática

> 🧪 Para usar AI Search, o Azure criará um **Skillset** (conjunto de habilidades cognitivas). Você pode usar modelos prontos ou personalizados com Azure Machine Learning.

---

## 📇 Etapa 4: Criar o Índice de Busca

1. Escolha os campos que deseja indexar:
   - `id`, `content`, `title`, `language`, etc.
2. Marque se o campo é **chave**, **pesquisável**, **ordenável**, ou **facetable** (para filtros).
3. Configure se deseja incluir **busca semântica**.

Exemplo de campo configurado:
```
json
{
  "name": "content",
  "type": "Edm.String",
  "searchable": true,
  "filterable": false,
  "sortable": false,
  "facetable": false
}
```

## 🔍 Etapa 5: Consultando Dados
Você pode fazer buscas no índice de várias formas:

📥 Usando a Interface no Portal
Vá até o serviço

Clique em Testar Índice

Escreva termos de busca (ex: "inteligência artificial")

## 🔗 Via API REST
```
bash

curl -X GET "https://<SEU-SERVICO>.search.windows.net/indexes/<SEU-INDICE>/docs?search=azure" \
  -H "api-key: <SUA-CHAVE>" \
  -H "Content-Type: application/json"
```
💻 Via Código (Ex: Python)

```
python

from azure.search.documents import SearchClient
from azure.core.credentials import AzureKeyCredential

client = SearchClient(
    endpoint="https://<SEU-SERVICO>.search.windows.net",
    index_name="meu-indice",
    credential=AzureKeyCredential("SUA-CHAVE")
)

results = client.search("análise de dados")
for result in results:
    print(result)

```

## 🧰 Recursos Avançados
- Autocomplete e Sugeridores: autocompletar nomes, palavras ou expressões.

- Filtros e Facetas: para navegação refinada.

- Buscas Semânticas (Semantic Search): retorna resultados com melhor interpretação contextual.

- Ranking Personalizado: combine regras com aprendizado de máquina.

## 🛡️ Segurança e Governança
- Use chaves de API ou Azure AD para autenticação.

- Restrinja IPs e use Private Endpoints.

- Habilite logs de diagnóstico com Azure Monitor.

- Criptografia em trânsito (HTTPS) e em repouso (AES-256).

## 📚 Recursos Recomendados
Documentação do Azure Cognitive Search

Guia de Semantic Search

Quickstart com Python

## ✅ Conclusão
Com o Azure Cognitive Search, você pode transformar qualquer conjunto de dados em uma experiência de busca inteligente, escalável e segura. O uso de AI Search permite que documentos e registros sejam interpretados com contexto e precisão — sem necessidade de estruturas complexas.



