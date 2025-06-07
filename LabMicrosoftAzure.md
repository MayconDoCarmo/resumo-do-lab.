# resumo-do-lab.

Microsoft Azure - Localizando Serviços por Categoria
Durante o laboratório, aprendi que o Azure oferece uma grande variedade de serviços para atender diferentes necessidades. Esses serviços são organizados por categorias, e dentro delas, por temas específicos. Por exemplo, na categoria Análise, há o tema Processamento de Big Data, que inclui os seguintes serviços:

Analysis Services

Clusters HDInsight

Data Factories

Data Lake Analytics

Data Lake Storage Gen1

Azure Databricks

Microsoft Graph Data Connect

Azure HDInsight em Clusters AKS

Essa estrutura facilita a navegação e localização de serviços na interface do Azure.

SLA e Alta Disponibilidade
O SLA (Service Level Agreement) define o tempo garantido de disponibilidade do serviço pela Microsoft. Por exemplo:

SLA de 99%: até 1,68 hora por semana (7,2 horas/mês) de indisponibilidade.

SLA de 99,9%: reduz para 10,1 minutos por semana (43,6 minutos/mês).

Para aumentar a disponibilidade, é possível configurar redundância ao criar máquinas virtuais, com réplicas em diferentes servidores ou regiões. Isso ajuda tanto na recuperação de desastres quanto na melhoria do desempenho.

É essencial planejar bem a arquitetura do sistema e validar a infraestrutura usada, pois isso impacta diretamente nos custos.

Criação de Máquinas Virtuais – Imagem e Arquitetura
Na criação de uma máquina virtual no Azure, a plataforma já fornece uma estimativa de custo. Entre as configurações disponíveis estão:

Reinicialização automática

Monitoramento

Tipo de disco

Modelo de redundância

Localização dos data centers: o site datacenters.microsoft.com/globe/explore oferece um mapa interativo com a infraestrutura global da Microsoft, incluindo regiões do Azure e suas geografias.

Configurações Detalhadas ao Criar uma VM
Ao configurar uma máquina virtual, você pode ajustar:

Nome da máquina

Região e zona de disponibilidade

Tipo de segurança e autenticação

Sistema operacional

Tamanho da máquina

Usuário administrador

Disco, rede, monitoramento e governança

Além disso, é possível ativar acesso via desktop remoto, facilitando a entrega de máquinas virtuais para colaboradores sem necessidade de um equipamento físico.

Armazenamento no Azure
Para configurar o armazenamento, é necessário definir:

Grupo de recursos

Nome único da conta de armazenamento

Região (com base em latência e custo)

Tipo de desempenho: Standard ou Premium

Redundância:

LRS (Local)

ZRS (Zona)

GRS (Geográfica)

GZRS (Geográfica com zona)

Outras opções incluem definir o tipo de armazenamento (quente ou frio), configurações de rede, criptografia, entre outras.

Menu: Armazenamento de Dados

Containers: gerenciamento de pastas e backups

Compartilhamento de arquivos: conexão via SMB (Windows, Linux e Mac)

Filas: configuração de mensageria

Tabelas: criação de tabelas no Azure

