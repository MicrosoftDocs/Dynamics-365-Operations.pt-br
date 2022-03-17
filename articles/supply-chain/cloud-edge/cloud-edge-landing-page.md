---
title: Unidades de escala em uma topologia híbrida distribuída
description: Este tópico oferece informações sobre unidades de escala de nuvem e de borda para cargas de trabalho de gerenciamento de fabricação e depósito.
author: cabeln
ms.date: 04/22/2021
ms.topic: article
ms.search.form: ScaleUnitWorkloadsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 30f455f37b5161878cf9c864b92966aa74da051f
ms.sourcegitcommit: b52ff5dfd32580121f74a5f262e5c2495e39d578
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376173"
---
# <a name="scale-units-in-a-distributed-hybrid-topology"></a>Unidades de escala em uma topologia híbrida distribuída

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> A capacidade da unidade de escala do Microsoft Dynamics 365 Supply Chain Management é disponibilizada para você de acordo com os termos que regem o uso do serviço. Para obter mais informações, consulte as [Informações Legais do Microsoft Dynamics](https://go.microsoft.com/fwlink/?LinkID=290927).
>
> Quando você habilita unidades de escala de nuvem e de borda, você será solicitado a afirmar que entendeu que alguns dados relacionados à configuração e ao processamento de unidades de escala de nuvem e de borda podem ser armazenados em um data center localizado nos Estados Unidos. Para saber mais sobre o processamento de dados para unidades de escala de nuvem e de borda, consulte a seção [Processamento de dados durante o gerenciamento de unidades de escala](#data-processing-management) posteriormente neste tópico.

## <a name="core-value-proposition-for-a-distributed-hybrid-topology"></a>Principal proposta de valor para uma topologia híbrida distribuída

As empresas que trabalham com fabricação e distribuição devem ser capazes de executar os principais processos comerciais 24/7, sem interrupção e em grande escala. Uma topologia híbrida distribuída permite que as empresas executem os principais processos de fabricação e de depósito de missão crítica sem interrupção, mesmo quando enfrentam problemas ocasionais de conectividade de rede ou de latência.

Uma topologia híbrida distribuída introduz o conceito de *unidades de escala*, que permite a distribuição de cargas de trabalho de chão de fábrica e de execução de depósito em diferentes ambientes. Essa funcionalidade pode ajudar a melhorar o desempenho, prevenir interrupções de serviço e maximizar o tempo de atividade. As unidades de escala são fornecidas pelos seguintes suplementos para a assinatura do Supply Chain Management:

- Suplemento de unidade de escala de nuvem para o Dynamics 365 Supply Chain Management
- Suplemento de unidade de escala de borda para o Dynamics 365 Supply Chain Management

Os recursos de carga de trabalho estão sendo liberados continuamente por meio de melhorias incrementais.

## <a name="scale-units-and-dedicated-workloads"></a>Unidades de escala e cargas de trabalho dedicadas

Unidades de escala estendem o ambiente do hub do Supply Chain Management central adicionando capacidade de processamento dedicado. As unidades de escala podem ser executadas na nuvem. Como alternativa, elas podem ser executadas na [borda](cloud-edge-edge-scale-units-lbd.md) em suas instalações locais.

:::image type="content" source="./media/cloud_edge-HeroDiagram.png" alt-text="Dynamics 365 com unidades de escala.":::

As unidades de escala fornecem resiliência, confiabilidade e dimensionamento para as cargas de trabalho atribuídas. As unidades de escala de borda podem estar temporariamente desconectadas do ambiente de hub de nuvem e os trabalhadores continuam trabalhando nas cargas de trabalho atribuídas na borda.

Uma *carga de trabalho* é um conjunto definido de funcionalidades comerciais que podem ser fatoradas e delegadas a uma unidade de escala. Embora a carga de trabalho para o gerenciamento de depósito tenha sido liberada, a carga de trabalho para a execução de fabricação ainda está na versão preliminar.

Você pode configurar seu ambiente de hub e unidades de escala de nuvem para cargas de trabalho selecionadas usando o [portal do Gerente de Unidade de Escala](https://sum.dynamics.com). Você também pode atribuir várias cargas de trabalho por unidade de escala. Para obter informações sobre os pré-requisitos e as limitações de unidades de escala de nuvem na versão atual, consulte a seção [Pré-requisitos e limitações de unidades de escala de nuvem](#cloud-scale-unit-prerequisites) posteriormente neste tópico.

### <a name="dedicated-warehouse-management-workload-capabilities-in-a-scale-unit"></a>Recursos dedicados de carga de trabalho de gerenciamento de depósito em uma unidade de escala

A carga de trabalho de gerenciamento de depósito permite que operações de depósito sejam escaladas e executadas em um ambiente resistente usando janelas de manutenção isoladas. A carga de trabalho de gerenciamento de depósito oferece suporte à maioria dos processos de gerenciamento de depósito de hub empresarial. Para obter mais informações, consulte [Cargas de trabalho de gerenciamento de depósito para unidades de escala de nuvem e de borda](cloud-edge-workload-warehousing.md).

### <a name="dedicated-manufacturing-execution-workload-capabilities-in-a-scale-unit"></a>Recursos dedicados de carga de trabalho de execução de fabricação em uma unidade de escala

A carga de trabalho de fabricação oferece os seguintes recursos:

- Os operadores de máquina e os supervisores de chão de fábrica podem acessar o plano de produção operacional.
- Os operadores de máquina podem manter o plano atualizado ao executar trabalhos de fabricação discretos e de processo.
- O supervisor de chão de fábrica pode ajustar o plano operacional.
- Os trabalhadores podem acessar o tempo e a presença de entrada e de saída na borda para garantir o cálculo correto do pagamento do trabalhador.

Para obter mais informações, consulte [Cargas de trabalho de execução de fabricação para unidades de escala de nuvem e de borda](cloud-edge-workload-manufacturing.md).

## <a name="considerations-before-you-enable-the-distributed-hybrid-topology-for-supply-chain-management"></a>Considerações antes de habilitar a topologia híbrida distribuída do Supply Chain Management

Ao habilitar a topologia híbrida distribuída, você faz a transição do ambiente de nuvem do Supply Chain Management para que funcione como um hub. Você também pode associar ambientes adicionais que são configurados como unidades de escala na nuvem ou na borda.

### <a name="prerequisites-and-limitations-for-cloud-scale-units"></a><a name="cloud-scale-unit-prerequisites"></a>Pré-requisitos e limitações para unidades de escala de nuvem

Na versão atual das unidades de escala, alguns recursos ainda não estão disponíveis, mas podem ser adicionados em versões incrementais ao longo do tempo.

#### <a name="you-must-be-a-licensed-customer-of-supply-chain-management"></a>Você deve ser um cliente licenciado do Supply Chain Management

Para integrar a topologia distribuída, é necessário ter uma licença do Supply Chain Management. Seu ambiente de nuvem existente se tornará o hub na topologia híbrida. Você pode declarar os ambientes de área restrita e de produção como ambientes de hub e adicionar unidades de escala de acordo com os suplementos adquiridos.

#### <a name="your-existing-project-must-be-administered-via-the-global-commercial-version-of-lcs"></a>O projeto existente deve ser administrado por meio da versão comercial global do LCS

O projeto do Microsoft Dynamics Lifecyle Services (LCS) deve atender aos seguintes requisitos de versão:

- O projeto deve ser administrado por meio da versão comercial global do LCS em [lcs.dynamics.com](https://lcs.dynamics.com).
- Não há suporte para versões locais do LCS (como [eu.lcs.dynamics.com](https://eu.lcs.dynamics.com) e [fr.lcs.dynamics.com](https://fr.lcs.dynamics.com)).
- Não há suporte para versões do Governmental Cloud do LCS.
- Não há suporte para a versão Mooncake do LCS.

#### <a name="your-current-production-environment-must-be-of-the-self-service-type-in-lcs"></a>O ambiente de produção atual deve ser do tipo autoatendimento no LCS

O ambiente de produção atual deve estar marcado com o tipo **Autoatendimento** no LCS. Este tipo indica que o locatário do projeto do LCS já foi convertido para oferecer suporte ao modelo de hospedagem do Azure Service Fabric.

> [!IMPORTANT]
> Não há suporte para tipos de ambiente executados como infraestrutura como serviço (IaaS). Esses ambientes são geralmente marcados com o tipo **Gerenciado pela Microsoft** no LCS. Se você tiver ambientes desse tipo, trabalhe com o seu contato da Microsoft para entender a linha do tempo de migração para o tipo **Autoatendimento**.

A Microsoft está no processo de transição de todos os ambientes de nuvem do Supply Chain Management do modelo IaaS para uma topologia hospedada no Service Fabric. Essa mudança apresenta melhor escalabilidade e facilita o gerenciamento de serviços. Portanto, as operações de implantação e manutenção são mais rápidas. Da mesma forma, os componentes de serviços estão sendo migrados para o conceito de microsserviços e o modelo de hospedagem de serviços [mudará](/virtualization/windowscontainers/about/containers-vs-vm) de um modelo de máquina virtual (VM) para uma arquitetura conteinerizada leve.

Por fim, a mesma infraestrutura de serviço conteinerizada baseada em Service Fabric capacitará as instâncias de nuvem e borda do serviço, independentemente de uma instância ser um hub na nuvem ou uma unidade de escala na nuvem ou na borda.

Antes de realizar a integração à topologia híbrida que oferece suporte a unidades de escala, o locatário do projeto deve ser transferido para o modelo hospedado pelo Service Fabric. Além disso, qualquer ambiente que atue como hub deverá ser convertido.

> [!TIP]
> Para obter informações sobre o status do locatário do projeto do LCS, procure o tipo de ambiente no [LCS](https://lcs.dynamics.com/) ou entre em contato com seu parceiro ou contato da Microsoft.

#### <a name="local-business-data-on-premises-environments-arent-supported-as-hubs-for-scale-units"></a>Não há suporte para dados corporativos locais como hubs para unidades de escala

Os ambientes locais não podem funcionar como hubs de unidades de escala. Os ambientes de hub devem ser sempre hospedados em nuvem.

#### <a name="scale-unit-management-capabilities-are-limited"></a>Os recursos de gerenciamento da unidade de escala são limitados

Os recursos de gerenciamento que podem ajudar com a movimentação de cargas de trabalho são limitados. Algumas operações de gerenciamento não são compatíveis por autoatendimento e talvez seja necessário solicitar suporte por seu parceiro ou contato da Microsoft. Os exemplos incluem algumas movimentações de carga de trabalho entre unidades de escala e movimentações ad-hoc temporárias em cenários de desastre.

#### <a name="metrics-and-measurements-arent-yet-available"></a>Métricas e medições ainda não estão disponíveis

Métricas e medidas que podem ajudar você a selecionar o melhor aplicativo para as unidades de escala ainda não estão disponíveis. Trabalhe com seu contato da Microsoft ou parceiro de implantação para selecionar o aplicativo mais apropriado.

### <a name="data-processing-during-management-of-scale-units"></a><a name="data-processing-management"></a>Processamento de dados durante o gerenciamento de unidades de escala

Ao habilitar o ambiente do Dynamics 365 para oferecer suporte à topologia híbrida distribuída para unidades de escala de nuvem e borda, alguns serviços de gerenciamento serão hospedados somente nos Estados Unidos, como o LCS. Esse comportamento afeta a transferência e o armazenamento de algumas informações administrativas e de configuração usadas pelo [portal do Gerente de Unidade de Escala](https://sum.dynamics.com). Eis alguns exemplos:

- Nomes e IDs de locatários
- IDs de projeto do LCS
- Endereços de email do administrador e do proprietário do projeto usados para entrar
- IDs de ambiente para unidades de hub e escala
- Configurações de carga de trabalho, incluindo os nomes e os endereços físicos de entidades legais e instalações, para que a topologia possa ser mostrada em um mapa geográfico
- Métricas coletadas (como latência e produtividade) que serão mostradas na página de análise do mapa para ajudar você a selecionar o melhor uso das unidades de escala

Os dados transferidos e armazenados nos data centers dos EUA serão excluídos de acordo com as políticas de retenção de dados da Microsoft. Sua privacidade é importante para a Microsoft. Para saber mais, leia nossa [política de privacidade](https://go.microsoft.com/fwlink/?LinkId=521839).

## <a name="onboard-to-the-distributed-hybrid-topology-for-supply-chain-management"></a>Integrar à topologia híbrida distribuída do Supply Chain Management

### <a name="try-out-the-distributed-hybrid-topology"></a>Experimentar a topologia híbrida distribuída

O processo de integração para a topologia híbrida distribuída tem dois estágios. Durante o primeiro estágio, é necessário [experimentar](cloud-edge-try-out.md) a solução e validar as personalizações para garantir que elas funcionarão em uma topologia distribuída que inclua unidades de escala. (É possível usar ambientes de desenvolvimento existentes para fazer a validação). Em seguida, você pode continuar até o segundo estágio, no qual você adquire ambientes de produção.

## <a name="select-your-lcs-project-tenant-and-the-detailed-onboarding-process"></a>Selecione o locatário de projeto do LCS e o processo de integração detalhado

As unidades de escala são oferecidas em várias unidades de manutenção de estoque (SKUs) e opções de preço. Portanto, você pode escolher a opção que melhor atende ao volume de transação mensal planejado e os requisitos de desempenho.

> [!TIP]
> Para identificar o dimensionamento que melhor atende às suas necessidades, trabalhe com seu parceiro de implementação e a Microsoft para compreender o tamanho da transação mensal de que precisa.

A SKU de nível de entrada é conhecida como *Básica* e a SKU de melhor desempenho é conhecida como *Padrão*. Cada SKU é pré-carregada com um número específico de transações mensais. No entanto, é possível aumentar o orçamento de transações mensais adicionando suplementos excedentes para cada SKU.

:::image type="content" source="media/SKUs-highlevel.png" alt-text="Suplementos de unidades de escala de nuvem.":::

> [!NOTE]
> Os suplementos de unidade de escala não são acoplados a um número limitado de usuários. Eles estão disponíveis para qualquer usuário na sua assinatura existente (desde que o administrador tenha atribuído as funções de usuário necessárias a eles).

A compra de cada suplemento da unidade de escala fornece um volume mensal de transações e também um número específico de slots de ambiente no LCS. Para cada Suplemento da Unidade de Escala de Nuvem, você tem direito a um novo slot de produção e um novo slot de área restrita. Durante o processo de integração, um novo projeto do LCS será adicionado com esses três slots. Os direitos de uso dos slots estão vinculados para que eles sejam usados como unidades de escala com um hub de nuvem.

Os suplementos excedentes não concedem o direito a novos slots de ambiente.

Se você quiser adquirir mais ambientes de área restrita, é possível comprar slots de área restrita regulares adicionais. A Microsoft pode ajudar você a habilitar esses slots como unidades de escala de área restrita para a topologia híbrida.


Após concluir o planejamento de integração à topologia híbrida distribuída do Supply Chain Management, você usará o [portal do Gerente de Unidade de Escala](https://aka.ms/SCMSUM) para iniciar o processo de integração. No portal, selecione a guia **Locatários do Dynamics 365**. Essa guia mostra a lista de locatários dos quais sua conta faz parte e onde você é proprietário ou administrador de ambiente para um projeto do LCS.

Se o locatário que você está procurando não estiver nessa lista, acesse [LCS](https://lcs.dynamics.com/v2) e verifique se você é um administrador de ambiente ou um proprietário de projeto do projeto do LCS desse locatário. Somente contas do Azure Active Directory (Azure AD) do locatário selecionado estão autorizadas a concluir a experiência de inscrição.

> [!NOTE]
> Após aplicar alterações ao LCS, a lista de locatários poderá levar até 30 minutos para refletir as alterações.

Para cada locatário, a lista mostra o status de integração.

:::image type="content" source="media/cloud_edge-EnableHybrid1.png" alt-text="Lista de locatários na guia Locatários do Dynamics 365.":::

Selecione **Clique aqui para começar** para solicitar a integração do locatário do LCS. Você deve aceitar os termos. Você também deve fornecer um endereço de email comercial em que a Microsoft possa enviar comunicações relacionadas ao processo de integração.

:::image type="content" source="media/cloud_edge-EnableHybrid2.png" alt-text="Envio de inscrição para um locatário.":::

A Microsoft revisará a solicitação e informará sobre as próximas etapas enviando um email para o endereço fornecido no formulário de inscrição. A Microsoft trabalhará com você para habilitar as unidades de escala na topologia híbrida para seu cenário de negócios.

Depois que a integração for concluída, você poderá usar a porta para configurar unidades de escala e cargas de trabalho.

### <a name="manage-scale-units-and-workloads-by-using-the-scale-unit-manager-portal"></a><a name="scale-unit-manager-portal"></a>Gerenciar unidades de escala e cargas de trabalho usando o portal de Gerente de Unidade de Escala

Acesse o [portal do Gerente e Unidade de Escala](https://aka.ms/SCMSUM) e entre usando sua conta de locatário. Na página **Configurar unidades de escala**, você poderá adicionar um ambiente de hub, caso ainda não esteja listado. Você pode selecionar o hub a ser configurado com unidades de escala e cargas de trabalho.

:::image type="content" source="media/cloud_edge-Manage.png" alt-text="Portal do Gerente de Unidade de Escala, página Configurar unidades de escala.":::

Para adicionar uma ou mais unidades de escala que estejam disponíveis em suas assinaturas, selecione **Adicionar unidades de escala**.

Na guia **Cargas de trabalho definidas**, use o botão **Criar carga de trabalho** para adicionar uma carga de trabalho de gerenciamento de depósito a uma das unidades de escala. Para cada carga de trabalho, você deve especificar o contexto dos processos que serão propriedade da carga de trabalho. Para cargas de trabalho de gerenciamento de depósito, o contexto é um depósito específico em um site e uma entidade legal específicos.

:::image type="content" source="media/cloud_edge-DefineWorkload.png" alt-text="Definir caixa de diálogo de cargas de trabalho.":::

#### <a name="manage-workloads"></a><a name="manage-workloads"></a>Gerenciar cargas de trabalho

Quando uma ou mais cargas de trabalho são habilitadas, use a opção **Gerenciar cargas de trabalho** para iniciar e gerenciar processos como os listados na tabela a seguir.

| Processar | Descrição |
|---|---|
| Pausar a comunicação da unidade de escala | Pausar mensagens de pipeline entre o hub e uma unidade de escala. Esse processo interromperá a comunicação e drenará o pipeline de dados entre o hub e as unidades de escala. Você deve executar esse processo antes de executar uma operação de serviço do Supply Chain Management no hub ou na unidade de escala, mas isso também pode ser usado em outras situações. |
| Continuar a comunicação da unidade de escala | Continuar as mensagens de pipeline entre o hub e uma unidade de escala. Talvez seja necessário usar esse processo, por exemplo, depois de executar uma operação de serviço do Supply Chain Management no hub ou na unidade de escala. |
| Atualizar cargas de trabalho | Sincronizar nova funcionalidade entre as cargas de trabalho da unidade de escala e do hub. Talvez seja necessário usar esse processo, por exemplo, quando a manutenção tiver causado a alteração das consultas de troca de dados e/ou tiver adicionado novas tabelas ou campos à carga de trabalho. |
| Transferir cargas de trabalho para uma unidade de escala | Agende uma carga de trabalho que está sendo executada no momento no hub para ser movida para uma unidade de escala. Quando esse processo for executado, a sincronização de dados fluirá e o hub e a unidade de escala serão definidos para alterar a propriedade da carga de trabalho. |
| Transferir unidade de escala para o hub | Agende uma carga de trabalho que está sendo executada no momento em uma unidade de escala a ser movida para o hub. Quando esse processo for executado, a sincronização de dados fluirá e o hub e a unidade de escala serão definidos para alterar a propriedade da carga de trabalho.
| Transição de emergência para hub | <p>Transfira imediatamente uma carga de trabalho existente para o hub. *Esse processo alterará a propriedade apenas dos dados disponíveis no momento no hub.*</p><p><strong>Aviso:</strong> esse processo pode causar perda de dados para dados não sincronizados e falha no processamento comercial. Portanto, ele deve ser usado somente em emergências, nas quais os processos comerciais devem ser processados no hub porque a unidade de escala tem uma interrupção que não pode ser atenuada em um período razoável.</p> |
| Topologia de desativação distribuída | Remova uma implantação de unidade de escala e execute somente no hub, sem o processamento da carga de trabalho. |

:::image type="content" source="media/sum-manage-workloads.png" alt-text="Experiência de gerenciamento de unidade de escala e carga de trabalho.":::

> [!TIP]
> Com o tempo, melhorias incrementais serão adicionadas à experiência do Gerente de Unidade de Escala para facilitar as operações de gerenciamento do ciclo de vida. Os recursos específicos da versão atual estão documentados em um manual de integração disponível para clientes que estão no processo de integração à topologia híbrida distribuída do Supply Chain Management. <!-- KFM: Add a link to the handbook when it is published -->

## <a name="feature-management-considerations-for-workloads"></a>Considerações de gerenciamento de recursos para cargas de trabalho

Esta seção explica alguns aspectos importantes que devem ser considerados ao instalar cargas de trabalho e adicionar ou remover recursos em uma implantação de topologia híbrida distribuída. Diversos cenários podem influenciar se você terá de executar um [upgrade de carga de trabalho](#manage-workloads) depois de fazer alterações. Porém, normalmente isso precisa ser feito quando você atualiza ou adiciona novas consultas de troca de dados e/ou quando adiciona novas tabelas ou campos a uma carga de trabalho já instalada.

### <a name="mandatory-features-for-installing-a-workload"></a>Recursos obrigatórios para instalar uma carga de trabalho

Quando você instala uma carga de trabalho, o processo de instalação cria uma definição de carga de trabalho que contém informações sobre as tabelas de dados usadas quando os dados são sincronizados entre as duas implantações. A criação de uma definição de carga de trabalho é processada automaticamente com base nos recursos habilitados no [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). A tabela a seguir lista os recursos que devem estar habilitados para gerar as definições de carga de trabalho necessárias para executar uma carga de trabalho de depósito ou de fabricação.

| Recurso obrigatório | Carga de trabalho |
|---|---|
| Atribuição automática dos GUIDs na criação de usuários do WHS | Depósito |
| Bloqueio de trabalho em toda a organização | Depósito |
| Detalhes da etiqueta do ciclo de remessa | Depósito |
| Suporte à unidade de escala para listas de trabalho do aplicativos de depósito | Depósito |
| Execução do piso de produção | Fabricação |

Quando você implantar uma carga de trabalho usando as [ferramentas de implantação de unidade de escala para ambientes de desenvolvimento de uma caixa](https://github.com/microsoft/SCMScaleUnitDevTools) ou o [portal do gerente de unidade de escala](https://sum.dynamics.com), todos os recursos obrigatórios serão habilitados automaticamente. No entanto, se você fizer uma implantação de teste manual que não tenha um ou mais dos recursos obrigatórios, a instalação da carga de trabalho não será bem-sucedida e será exibida uma mensagem listando os recursos ausentes. Nesse caso, você deverá habilitar esses recursos manualmente e disparar a instalação da carga de trabalho mais uma vez.

### <a name="enabling-or-disabling-features-that-have-data-synchronization-dependencies"></a>Habilitando ou desabilitando recursos que têm dependências de sincronização de dados

Os recursos que afetam a seleção de dados sincronizados entre o hub e as respectivas unidades de escala também afetam a maneira como a definição de carga de trabalho é criada. Por isso é importante que esses recursos sejam habilitados antes da instalação da carga de trabalho. Se você habilitar esse tipo de recurso enquanto estiver executando uma carga de trabalho, deverá regenerar a definição da carga de trabalho executando um [upgrade da carga de trabalho](#manage-workloads) depois de habilitar o recurso. Da mesma forma, se você desabilitar um recurso que tem dependências de sincronização de dados enquanto estiver executando uma carga de trabalho, deverá executar um [upgrade da carga de trabalho](#manage-workloads) para remover as informações de sincronização de dados relevantes da definição da carga de trabalho.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
