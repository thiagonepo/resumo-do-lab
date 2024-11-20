# RESUMO do Laboratório Microsoft Azure - Localizando Serviços por Categoria

Durante o laboratório, aprendi que existem diversos serviços no Azure, cada um destinado a atender necessidades específicas, e esses serviços estão organizados de forma categorizada.

---

Dentro de cada categoria, há uma subdivisão por tópicos específicos, como exemplificado na categoria **Análise**, onde o tópico **Processamento de Big Data** inclui os seguintes serviços:

- Analysis Services
- Clusters HDInsight
- Data Factories
- Data Lake Analytics
- Data Lake Storage Gen1
- Azure Databricks
- Microsoft Graph Data Connect
- Azure HDInsight em clusters AKS

Essa estrutura de categorização facilita a localização de serviços na console do Azure.

---

## SLA e Alta Disponibilidade

O **Acordo de Nível de Serviço** (SLA, na sigla em inglês) define o tempo de disponibilidade garantido por um provedor de nuvem. Por exemplo, um SLA de 99% significa que o tempo de inatividade é de 1,68 hora por semana ou 7,2 horas por mês. Já um SLA de 99,9% reduz significativamente esse tempo de inatividade para 10,1 minutos por semana ou 43,6 minutos por mês.

É possível configurar máquinas virtuais com redundância em outros servidores ou locais, o que pode aumentar a disponibilidade. Isso pode ser útil em estratégias de **ambientes resilientes**, onde, em caso de falhas, o ambiente pode ser mantido em outra localidade, ou mesmo para melhorar a velocidade de acesso, pois a informação pode ser obtida de múltiplos locais.

Ao projetar a arquitetura do sistema, é crucial validar a infraestrutura a ser utilizada, pois as cobranças podem ser significativamente impactadas por escolhas inadequadas.

## Criação de Máquinas Virtuais / Imagem e Arquitetura

Na interface de criação de máquinas virtuais, é possível verificar a estimativa de custo para a máquina virtual e também gerenciar sua configuração. A criação envolve a definição de opções como:

- Reinício automático
- Monitoramento
- Discos
- Peças
- Modelo de redundância

## Data Centers - Globais

O portal **datacenters.microsoft.com/globe/explore** oferece um mapa interativo em 2D ou 3D, permitindo visualizar a localização dos datacenters da Microsoft ao redor do mundo. O mapa exibe regiões do Azure, suas geografias e informações sobre a infraestrutura global da Microsoft, com filtros que ajudam a obter uma visão detalhada da presença global da plataforma Azure.

## Criação de Máquinas Virtuais e Área de Trabalho Remota

A criação de máquinas virtuais no Azure é simplificada, com diversas opções de configuração para facilitar a gestão da infraestrutura. Todas as máquinas virtuais e recursos no Azure requerem a definição de um **grupo de recursos**, que é a segunda configuração a ser feita ao criar uma máquina virtual. Outras opções de configuração incluem:

- Nome da máquina
- Região
- Zona de disponibilidade
- Tipo de segurança
- Sistema operacional
- Tamanhos
- Tipo de autenticação
- Criação de um usuário administrador

Além disso, é possível configurar:

- Disco
- Rede
- Gerenciamento
- Monitoramento

Outras opções úteis incluem a configuração de desktop remoto, que facilita o acesso a máquinas para funcionários sem a necessidade de fornecer computadores físicos.

## Armazenamento

Ao configurar o armazenamento, a assinatura já vem pré-configurada, e deve-se escolher o grupo de recursos. O nome da conta de armazenamento deve ser único.

**Observação:** Conta de armazenamento é o nome do armazenamento criado.

- **Região:** Escolher com base em requisitos de latência ou custo.  
- **Desempenho:** Pode ser configurado como `Standard` ou `Premium`, o que impacta a latência.  
- **Redundância:** Diversos tipos de redundância, como **LRS** (local), **GRS** (geográfica), **ZRS** (zona) e **GZRS** (zona geográfica), determinam a proteção dos dados.

Além disso, é possível configurar o tipo de armazenamento (quente ou frio), a rede, a criptografia e outras opções.

### Menu: Armazenamento de Dados

Configuração de armazenamento, recebimento, compartilhamento e organização de dados no Azure:

- Containers: Gerenciamento de pastas (inclui opção de configurar backup).
- Compartilhamento de arquivos: Ferramenta para criar conexões SMB para Windows, Linux e Mac.
- Filas: Configuração de mensageria.
- Tabelas: Criação de tabelas.


### Migração de Dados

É possível criar projetos de migração para transferir arquivos e dados da infraestrutura on-premises para a nuvem utilizando ferramentas como **AZCopy** ou **Azure Databox**.

- AZCopy: Ferramenta leve para terminal, disponível para Linux, Windows e Mac, utilizada para transferir arquivos.
- Azure Data Box: Um dispositivo de armazenamento com capacidade para 80TB. O cliente grava os dados no disco rígido e o envia de volta ao Azure.
- Data Box Disk: Limite de 35TB.
- Data Box Heavy: Limite de 800TB.
- Data Box Job: Limite de 1TB.

Cada serviço do **Azure Data Box** tem valores diferentes.

### Gerenciador de Armazenamento do Microsoft Azure

Aplicação para gestão de armazenamento. Após a instalação, a ferramenta permite sincronizar e visualizar informações sobre assinaturas e contas de armazenamento.

## Identidade e Segurança (Entra ID)

O gerenciamento de usuários no Azure deve ser feito por meio do **Entra ID**, que define funções e permissões. Diferente do RBAC, os usuários gerenciados no **Entra ID** têm permissões restritas à gestão de usuários e funções relacionadas.

É possível criar usuários e convidar externos, inclusive para grupos.

Entra Connect: Sincroniza os usuários do ambiente on-premises para a nuvem.


Contas deletadas podem ser recuperadas até 30 dias após a exclusão.

### Defender for Cloud

Aplicativo nativo da nuvem e híbrido que oferece insights sobre a segurança do ambiente, com recomendações para melhorar a proteção.

Recomendações de segurança: Validador de segurança e sugestões para aprimorar a segurança do ambiente.


## Calculadoras de Custos

O Azure disponibiliza duas calculadoras:

1. **Calculadora de Preços:** Estimativa de preços para os recursos do Azure.
2. **TCO (Total Cost Ownership):** Calculadora que estima o custo total de propriedade ao migrar de um ambiente on-premises para o Azure.

O uso dessas ferramentas é essencial para avaliar os custos e evitar surpresas financeiras.

## Portal de Confiança do Serviço

Este portal oferece diversas ferramentas de governança, como:

- Normas de Auditoria: Compliance com regulamentos específicos de cada país.
- Bloqueio de Recursos: Controle de acesso a recursos.
- Purview: Ferramenta de governança e compliance.


## Ferramentas de Implantação do Azure

Cloud Shell: Interface para execução de comandos PowerShell ou Bash, com necessidade de uma conta de armazenamento.

Bicep: Auxilia na automação da criação de máquinas virtuais.

Azure Arc: Ferramenta para gerenciar máquinas fora do Azure, permitindo atualizações e acesso remoto direto pela console.


## Ferramentas de Monitoramento do Azure

Diversas ferramentas para monitorar o ambiente e a saúde dos recursos:

- Azure Monitor: Ferramenta abrangente com insights para análise e visão detalhada da infraestrutura.
- Service Health: Exibe a saúde dos recursos e manutenções agendadas.
- Advisor: Fornece recomendações sobre a infraestrutura para garantir a otimização e benefícios.
