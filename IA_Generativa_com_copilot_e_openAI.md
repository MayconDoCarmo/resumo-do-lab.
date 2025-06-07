# 🤖 Explorando os Recursos de IA Generativa com Copilot e OpenAI

A inteligência artificial generativa está transformando a forma como interagimos com software, escrevemos código, analisamos dados e até mesmo criamos conteúdo. Com o **GitHub Copilot** e os serviços da **OpenAI no Azure**, é possível acelerar o desenvolvimento, automatizar tarefas e potencializar a criatividade com segurança e produtividade.

> 💡 Ideal para desenvolvedores, analistas de dados, profissionais de negócio e equipes que desejam adotar IA no seu fluxo de trabalho.

---

## 📌 O que é IA Generativa?

A **IA Generativa** utiliza modelos de linguagem como o **GPT** para criar novos conteúdos a partir de instruções humanas (prompts). Entre os principais usos:

- Geração de texto, código e documentos
- Resumos automáticos
- Tradução e reescrita
- Assistência de programação
- Respostas conversacionais e chatbots

---

## 🛠️ Ferramentas Usadas

| Ferramenta            | Função Principal                                         |
|------------------------|----------------------------------------------------------|
| GitHub Copilot         | Geração de código e sugestões em tempo real no editor    |
| Azure OpenAI Service   | Acesso aos modelos GPT da OpenAI de forma segura         |
| Visual Studio Code     | Editor de código com suporte ao Copilot                  |
| Azure Portal           | Provisionamento e gerenciamento de recursos OpenAI       |

---

## ✅ Pré-requisitos

- Conta no GitHub com acesso ao **Copilot** (versão individual ou empresarial)
- Assinatura ativa no [Portal do Azure](https://portal.azure.com)
- Permissão para criar recursos no Azure
- Familiaridade básica com Python, JavaScript ou outras linguagens (opcional)

---

## ✨ Etapa 1: Ativando o GitHub Copilot

1. Acesse [https://github.com/features/copilot](https://github.com/features/copilot)
2. Faça login e ative a licença (gratuita para estudantes ou paga para usuários comuns)
3. Instale a extensão **GitHub Copilot** no Visual Studio Code
4. Faça login com sua conta GitHub no VS Code
5. Pronto! O Copilot já começa a sugerir código conforme você digita.

### 💡 Exemplos de uso:
```
javascript
// Criar uma função que verifica se um número é primo
function isPrime(n) {
  if (n <= 1) return false;
  for (let i = 2; i < n; i++) {
    if (n % i === 0) return false;
  }
  return true;
}
```

###⚙️ Etapa 2: Criando um Recurso Azure OpenAI
1. No Portal do Azure, pesquise por "Azure OpenAI"

2. Clique em Criar e configure:

- Nome: openai-lab

- Local: East US (região com suporte)

- Plano: Standard

3.Após criado, vá em Model Deployments e implante modelos como:

- gpt-4

- gpt-3.5-turbo

- text-embedding-ada-002

## 💬 Etapa 3: Interagindo com a API do GPT
Você pode utilizar Python para fazer chamadas à API:

```
import openai

openai.api_type = "azure"
openai.api_key = "<SUA_CHAVE>"
openai.api_base = "https://<SEU_ENDPOINT>.openai.azure.com/"
openai.api_version = "2023-05-15"

response = openai.ChatCompletion.create(
    engine="gpt-4",
    messages=[
        {"role": "user", "content": "Explique o que é IA generativa"},
    ]
)

print(response['choices'][0]['message']['content'])
```
✅ Substitua engine, api_key e endpoint pelos dados do seu portal.

## 🧠 Casos de Uso Reais
-	Assistência em código, geração de testes, documentação automática
- Criação de chatbots, geração de respostas automáticas
-	Tutoria interativa, criação de materiais de estudo
- Escrita de posts, e-mails, slogans e conteúdo para redes sociais
-	Geração de queries SQL, explicações de dashboards, análises automatizadas
 
## 🔐 Boas Práticas de Uso
- Evite compartilhar dados sensíveis nos prompts

- Implemente controle de acesso via RBAC ou API Key

- Ative logs e monitoramento no Azure

- Use a política de uso responsável da OpenAI
