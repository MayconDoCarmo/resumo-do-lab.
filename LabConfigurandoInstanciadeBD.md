# 🛠️ Criando uma Instância Gerenciada de SQL no Azure (Windows & Linux)

Este guia completo demonstra como criar uma **Instância Gerenciada de SQL (Azure SQL Managed Instance)** no **Portal do Azure** e conectá-la a partir de sistemas **Windows** e **Linux**. Ideal para testes, desenvolvimento, homologação e até cenários iniciais de produção com alta compatibilidade com o SQL Server tradicional.

> ⚠️ **Importante:** Para ambientes de produção, é essencial configurar regras de segurança, redes privadas (Private Link) e backups conforme as políticas da empresa.

---

## 🧾 O que é o Azure SQL Managed Instance?

O **Azure SQL Managed Instance** é uma oferta PaaS (Plataforma como Serviço) da Microsoft que entrega o SQL Server com o gerenciamento automatizado da nuvem. Ele combina:
- Alta compatibilidade com SQL Server local (on-premises)
- Backups automáticos
- Alta disponibilidade embutida
- Escalabilidade sob demanda
- Suporte à integração com redes privadas (VNet)

> ✅ **Vantagem principal:** você não precisa se preocupar com patching, upgrades, ou configuração de cluster de alta disponibilidade.

---

## ✅ Pré-requisitos

Antes de começar, certifique-se de ter:

- Uma **conta ativa no Azure**
- Permissão para criar redes e instâncias SQL
- Um grupo de recursos existente ou permissão para criá-lo
- **SQL Server Management Studio (SSMS)** no Windows ou **Azure Data Studio** no Linux/macOS
- Uma senha segura (mínimo 12 caracteres, com letras maiúsculas, minúsculas, números e símbolos)

---

## 🔨 Etapa 1: Criar a Instância Gerenciada de SQL

1. Acesse o [Portal do Azure](https://portal.azure.com).
2. No menu superior, clique em **“Criar um recurso”** > Pesquise por `Instância Gerenciada de SQL`.
3. Clique em **"Criar"** e preencha os dados básicos:

| Campo                  | Exemplo                     |
|------------------------|-----------------------------|
| Assinatura             | Azure Subscription 1        |
| Grupo de Recursos      | `rg-lab-sql`                |
| Nome da Instância      | `sqlmi-lab-demo`            |
| Região                 | `Brazil South`              |
| Camada de Serviço      | General Purpose             |
| Autenticação           | SQL Server Authentication   |
| Usuário Administrador  | `sqladmin`                  |
| Senha                  | `SenhaSegura#2025`          |

---

## 🌐 Etapa 2: Configurar a Rede Virtual

Durante o processo de criação:

1. Crie uma **VNet dedicada** ou utilize uma existente.
2. Em **Sub-rede gerenciada**, crie uma sub-rede específica e delegue para `Microsoft.Sql/managedInstances`.
3. Valide as configurações de DNS e conectividade.

> 🧠 Dica: Você pode usar peering entre redes para conectar diferentes ambientes (ex: laboratório e produção).

---

## ⏳ Etapa 3: Provisionamento

- A criação da instância pode demorar **30 a 60 minutos**.
- Use esse tempo para preparar as ferramentas cliente, configurar grupos de segurança de rede ou revisar permissões.

---

## 🔗 Etapa 4: Conectar-se à Instância

Após a instância ser provisionada:

1. Vá até **"Conectividade"** nas configurações da instância.
2. Copie o **nome DNS público** (ex: `sqlmi-lab-demo.public.xxx.database.windows.net`).
3. Certifique-se de que a máquina cliente pode se conectar à VNet (via IP público, peering ou túnel VPN).

---

## 💻 Etapa 5: Acessar via Cliente SQL

### 🪟 Windows (SSMS)

1. Abra o **SQL Server Management Studio (SSMS)**.
2. Em **Server Name**, insira o DNS da instância.
3. Use **SQL Server Authentication**.
4. Informe o usuário e senha definidos.
5. Clique em **Connect**.

> 📌 Dica: Ative **Trust Server Certificate** se houver erro de certificado SSL.

---

### 🐧 Linux/macOS (Azure Data Studio ou sqlcmd)

#### 🔷 Usando Azure Data Studio:

1. Clique em “Nova Conexão”.
2. Preencha os campos:

| Campo         | Valor                                       |
|---------------|---------------------------------------------|
| Server        | `sqlmi-lab-demo.public.xxx.database.windows.net` |
| Autenticação  | SQL Login                                   |
| Username      | `sqladmin`                                  |
| Password      | SuaSenhaAqui                                |

3. Clique em **Conectar**.

#### 💻 Usando `sqlcmd` via Terminal:

```bash
sqlcmd -S sqlmi-lab-demo.public.xxx.database.windows.net -U sqladmin -P "SuaSenhaAqui"
