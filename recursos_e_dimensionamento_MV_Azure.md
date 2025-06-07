# ⚙️ Configurando Recursos e Dimensionamento em Máquinas Virtuais no Azure

Este guia mostra como configurar recursos de **CPU, memória, disco e rede** ao criar ou redimensionar uma **Máquina Virtual no Azure**, além de boas práticas para escalar a infraestrutura conforme a demanda do seu projeto.

> 📌 *Ideal para desenvolvedores, administradores de sistemas e arquitetos que desejam otimizar custos e desempenho em ambientes na nuvem.*

---

## 🧾 O que são os Recursos de uma VM?

Ao criar uma Máquina Virtual (VM) no Azure, você define recursos que impactam diretamente em:

- 🧠 **Capacidade de processamento (vCPU)**
- 💾 **Memória RAM**
- 📀 **Tipo e tamanho de disco**
- 🌐 **Configuração de rede**
- 💸 **Custo por hora ou mês**

Esses recursos podem ser ajustados conforme a necessidade, permitindo **escalabilidade elástica** e **gestão eficiente de custos**.

---

## ✅ Pré-requisitos

- Conta ativa no [Portal do Azure](https://portal.azure.com)
- Grupo de recursos existente
- Permissões de **contribuidor** ou **administrador**
- Conhecimento básico sobre tipos de workloads (produção, testes, banco de dados, etc.)

---

## 🚀 Etapa 1: Escolhendo o Tamanho Ideal da VM

1. No portal, vá para **Máquinas Virtuais** > **Criar VM**.
2. Na aba **"Tamanho"**, você poderá escolher entre diversos perfis:

| Tipo de VM         | Ideal para                           |
|--------------------|---------------------------------------|
| **B-Series (Burstável)** | Workloads leves, intermitentes      |
| **D-Series**        | Web apps, bancos de dados de médio porte |
| **E-Series**        | Workloads com uso intensivo de memória |
| **F-Series**        | Computações rápidas, com menos memória |
| **H/N-Series**      | Alta performance, uso científico ou IA |

> 🔍 Use a [calculadora de preços do Azure](https://azure.microsoft.com/en-us/pricing/calculator/) para estimar custos antes de escolher.

---

## 💾 Etapa 2: Configurando Discos

Durante ou após a criação da VM, vá até **"Discos"** para definir:

- **Disco do SO (Sistema Operacional)**: SSD Padrão, SSD Premium ou HDD
- **Discos de Dados**: adicionais para armazenamento de arquivos, bancos, logs, etc.
- **Cache de Leitura/Gravação**: acelera o desempenho de I/O

> 🧠 **Dica**: Use discos **Premium SSD** para bancos de dados ou aplicações críticas que exigem alta performance.

---

## 🌐 Etapa 3: Configurações de Rede

Na aba **"Rede"**, você pode:

- Associar a uma **VNet (Virtual Network)**
- Definir uma **sub-rede**
- Criar ou associar um **NSG (Network Security Group)** para controle de tráfego
- Definir o uso de **IP público** ou **Private IP** apenas

> 🔐 Para produção, recomenda-se desabilitar IP público e utilizar VPN, ExpressRoute ou Azure Bastion.

---

## 🔄 Etapa 4: Redimensionar uma VM Existente

Se a VM já estiver criada:

1. Vá para **Máquinas Virtuais** > Selecione a VM
2. No menu lateral, clique em **"Tamanho"**
3. Escolha outro SKU (tamanho da VM) compatível com sua região e disco atual
4. Clique em **"Redimensionar"**

> ⚠️ A VM será reiniciada durante esse processo.

---

## 📈 Etapa 5: Escalabilidade e Autoescalamento

### 🔹 Escalamento Vertical

Alterar recursos da **mesma VM** (vCPU, memória). Útil para cargas previsíveis.

### 🔸 Escalamento Horizontal

Criar múltiplas instâncias da VM com balanceamento de carga. Ideal para apps web, APIs e microsserviços.

### ⚙️ Usando o Azure Scale Set

1. Vá para **Conjuntos de dimensionamento de máquina virtual (VMSS)**
2. Configure:
   - Número mínimo e máximo de instâncias
   - Métricas de acionamento (ex: uso de CPU > 75%)
   - Políticas de instância (modo de atualização)

---

## 🔐 Boas Práticas de Configuração

- ✅ Crie um **grupo de recursos por ambiente** (dev/test/prod)
- ✅ Habilite **Auto Shutdown** para ambientes de teste/lab
- ✅ Use **Tags** para categorizar custos e recursos
- ✅ Ative o **Azure Monitor** e o **Log Analytics** para acompanhar uso e performance
- ✅ Verifique **quotas de vCPUs** por região em sua assinatura

---

## 📚 Recursos Adicionais

- [Catálogo de tamanhos de VM no Azure](https://learn.microsoft.com/azure/virtual-machines/sizes)
- [Recomendações de dimensionamento de carga](https://learn.microsoft.com/azure/architecture/best-practices/compute)
- [Azure Advisor](https://learn.microsoft.com/azure/advisor/) – Sugestões automáticas de otimização

---

## ✅ Conclusão

Agora você está pronto para **criar, configurar e dimensionar Máquinas Virtuais** no Azure de forma estratégica, segura e eficiente, aproveitando o que há de melhor na computação em nuvem.

> 🎯 **Próximos passos:** implemente autoscale, snapshots, backup e monitore o desempenho para ambientes resilientes e bem gerenciados.
