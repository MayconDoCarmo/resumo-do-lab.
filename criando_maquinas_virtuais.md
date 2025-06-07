# 🖥️ Criando Máquinas Virtuais no Microsoft Azure

Criar uma máquina virtual (VM) no Azure é uma das formas mais flexíveis de implementar servidores e serviços em nuvem. VMs podem hospedar desde aplicações web simples até ambientes corporativos completos.

---

## ✅ 1. Acesse o Portal do Azure

Acesse: [https://portal.azure.com](https://portal.azure.com)  
Faça login com sua conta Microsoft para acessar o painel de gerenciamento de recursos do Azure.

---

## 🧱 2. Iniciando a Criação da VM

No painel de navegação:

1. Clique em **"Máquinas Virtuais"** ou pesquise por **"Virtual Machines"**.
2. Clique em **"Criar"** → **"Máquina Virtual"**.
3. Selecione sua **assinatura** e **grupo de recursos** (ou crie um novo, se necessário).

---

## 📝 3. Configurando Detalhes Básicos

| Parâmetro          | Descrição |
|--------------------|-----------|
| **Nome da VM**     | Escolha um nome intuitivo e padronizado (ex: `vm-web-prod-01`). |
| **Região**         | Escolha uma região geograficamente próxima aos usuários finais para menor latência e melhor desempenho. |
| **Disponibilidade**| Selecione zonas ou conjuntos de disponibilidade para alta resiliência. |
| **Imagem do SO**   | Selecione o sistema operacional: Windows Server, Ubuntu, Red Hat, Debian, etc. |
| **Tamanho da VM**  | Defina com base no consumo de CPU, memória e carga de trabalho. Utilize o botão **"Alterar tamanho"** para ver estimativas de custo e performance.|

---

## 🔐 4. Definindo Credenciais de Acesso

Escolha o método de autenticação:

- Para **Windows**:
  - Nome de usuário
  - Senha segura (mínimo de 12 caracteres, com símbolos e números)
- Para **Linux**:
  - Nome de usuário
  - Autenticação por senha ou chave pública SSH

> 💡 **Dica:** Evite usar nomes genéricos como `admin` ou `user` por motivos de segurança.

---

## 🌐 5. Configurações de Rede

A configuração da rede é essencial para conectividade e segurança:

- **Rede Virtual (VNet)**: Crie uma nova VNet ou use uma existente.
- **Sub-rede**: Selecione uma sub-rede para segmentar o tráfego.
- **Endereço IP Público**: Necessário para conexão externa (como via RDP ou SSH).
- **Grupo de Segurança de Rede (NSG)**:
  - Defina regras de entrada/saída, como permitir RDP (porta 3389) ou SSH (porta 22).
  - Mantenha regras restritivas para segurança.

---

## 💽 6. Armazenamento e Disco

- **Tipo de disco do SO**: Standard HDD, Standard SSD, ou Premium SSD.
- **Disco de dados adicionais**: Podem ser adicionados conforme a necessidade.
- **Opções de criptografia**: Recomendado ativar a criptografia para segurança.

---

## 🔧 7. Configurações Avançadas (Opcional)

Você pode habilitar recursos como:

- **Monitoramento com o Azure Monitor**
- **Backup automático com Azure Backup**
- **Extensões de VM** (como agentes de segurança, scripts de inicialização, etc.)
- **Diagnóstico de inicialização** para depurar falhas

---

## 🔍 8. Revisar e Criar

- Revise todas as configurações nas abas exibidas.
- Clique em **"Revisar + criar"**.
- Após validação, clique em **"Criar"**.
- O Azure começará o provisionamento da VM (leva entre 1 e 5 minutos, geralmente).

---

## 🔗 9. Conectando-se à Máquina Virtual

Após a criação, vá até o painel da VM:

- Para **Windows**:
  - Clique em **"Conectar" → "RDP"**
  - Baixe o arquivo `.rdp` e conecte-se com as credenciais criadas.

- Para **Linux**:
  - Clique em **"Conectar" → "SSH"**
  - Use o comando SSH fornecido no terminal do seu computador.

> 🔒 **Importante:** Mantenha sempre a segurança da VM com regras NSG bem definidas, atualizações automáticas ativadas e, se possível, serviços como **Azure Bastion** para conexões seguras sem IP público.

---

## 📌 Boas Práticas Adicionais

- Utilize **tags** para organização e rastreamento de custos.
- Crie **políticas de governança** com Azure Policy.
- Considere automatizar implantações com **Azure Bicep** ou **ARM Templates**.
- Habilite **Auto Shutdown** em ambientes de desenvolvimento para economia.

---
