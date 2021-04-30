---
title: Usar unidades de escala para ajudar a aumentar a resiliência para cargas de trabalho do Supply Chain Management
description: Este tópico oferece informações sobre unidades de escala de nuvem e de borda para cargas de trabalho de gerenciamento de fabricação e depósito.
author: cabeln
ms.date: 04/13/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: c47088edd89413d196e904bc7eaa115585bf8464
ms.sourcegitcommit: 639175a39da38edd13e21eeb5a1a5ca62fa44d99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/15/2021
ms.locfileid: "5899134"
---
# <a name="use-scale-units-to-help-increase-resilience-for-supply-chain-management-workloads"></a>Usar unidades de escala para ajudar a aumentar a resiliência para cargas de trabalho do Supply Chain Management

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> A capacidade da unidade de escala do Microsoft Dynamics 365 Supply Chain Management é disponibilizada para você de acordo com os termos que regem o uso do serviço. Para obter mais informações, consulte as [Informações Legais do Microsoft Dynamics](https://go.microsoft.com/fwlink/?LinkID=290927).
>
> Ao habilitar unidades de escala de nuvem e de borda, você afirma que entendeu que alguns dados relacionados à configuração e ao processamento de unidades de escala de nuvem e de borda podem ser armazenados em um data center localizado nos Estados Unidos. Para saber mais sobre o processamento de dados para unidades de escala de nuvem e de borda, consulte a seção [Processamento de dados durante o gerenciamento de unidades de escala](#data-processing-management) posteriormente neste tópico.

## <a name="core-value-proposition-for-scale-units"></a>Proposta de valor principal para unidades de escala

As empresas que trabalham com fabricação e distribuição devem ser capazes de executar os principais processos comerciais 24/7, sem interrupção e em grande escala. As unidades de escala de nuvem e de borda permitem que as empresas executem os principais processos de fabricação e de depósito de missão crítica sem interrupção, mesmo quando enfrentam problemas ocasionais de conectividade de rede ou de latência.

As unidades de escala de nuvem e de borda permitem a distribuição de cargas de trabalho de chão de fábrica e de execução de depósito entre diferentes ambientes. Essa funcionalidade pode ajudar a melhorar o desempenho, prevenir interrupções de serviço e maximizar o tempo de atividade. As unidades de escala são fornecidas pelos seguintes suplementos para a assinatura do Supply Chain Management:

- Suplemento da Unidade de Escala de Nuvem para Dynamics 365 Supply Chain Management (*disponível em abril de 2021*)
- Suplemento da Unidade de Escala de Borda para Dynamics 365 Supply Chain Management (*disponível em breve*)

Os recursos de carga de trabalho estão sendo liberados continuamente por meio de melhorias incrementais.

## <a name="scale-units-and-dedicated-workloads"></a>Unidades de escala e cargas de trabalho dedicadas

Unidades de escala estendem o ambiente do hub do Supply Chain Management central adicionando capacidade de processamento dedicado. As unidades de escala podem ser executadas na nuvem. Como alternativa, elas podem ser executadas na borda em suas instalações locais.

:::image type="content" source="./media/cloud_edge-HeroDiagram.png" alt-text="Dynamics 365 com unidades de escala":::

As unidades de escala fornecem resiliência, confiabilidade e dimensionamento para as cargas de trabalho atribuídas. As unidades de escala de borda podem estar temporariamente desconectadas do ambiente de hub de nuvem e os trabalhadores continuam trabalhando nas cargas de trabalho atribuídas na borda.

Uma *carga de trabalho* é um conjunto definido de funcionalidades comerciais que podem ser fatoradas e delegadas a uma unidade de escala. Embora a carga de trabalho para o gerenciamento de depósito tenha sido liberada, a carga de trabalho para a execução de fabricação ainda está na versão preliminar.

Você pode configurar seu ambiente de hub e unidades de escala de nuvem para cargas de trabalho selecionadas usando o [portal do Gerente de Unidade de Escala](https://sum.dynamics.com). Você também pode atribuir várias cargas de trabalho por unidade de escala. Para obter informações sobre os pré-requisitos e as limitações de unidades de escala de nuvem na versão atual, consulte a seção [Pré-requisitos e limitações de unidades de escala de nuvem](#cloud-scale-unit-prerequisites) posteriormente neste tópico.

### <a name="dedicated-warehouse-management-workload-capabilities-in-a-scale-unit"></a>Recursos dedicados de carga de trabalho de gerenciamento de depósito em uma unidade de escala

A carga de trabalho de gerenciamento de depósito é a primeira carga de trabalho distribuída para unidades de escala que foi liberada para disponibilidade geral.

Para o gerenciamento de depósito, as unidades de escala fornecem os seguintes recursos:

- O sistema pode processar métodos de ciclo selecionados para ordens de venda e reabastecimento de demanda.
- Os trabalhadores de depósito podem executar o trabalho de depósito de reabastecimento de demanda e vendas usando o aplicativo móvel do Gerenciamento de Depósito.
- Os trabalhadores de depósito podem consultar o estoque disponível usando o aplicativo móvel do Gerenciamento de Depósito.
- Os trabalhadores de depósito podem criar e executar movimentações de estoque usando o aplicativo móvel do Gerenciamento de Depósito.
- Os trabalhadores de depósito podem registrar ordens de compra e fazer armazenamento usando o aplicativo móvel do Gerenciamento de Depósito.

Para obter mais informações, consulte [Cargas de trabalho de gerenciamento de depósito para unidades de escala de nuvem e de borda](cloud-edge-workload-warehousing.md).

### <a name="dedicated-manufacturing-execution-workload-capabilities-in-a-scale-unit"></a>Recursos dedicados de carga de trabalho de execução de fabricação em uma unidade de escala

A primeira versão da carga de trabalho de fabricação está atualmente na versão preliminar e oferece os seguintes recursos:

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

A Microsoft está no processo de transição de todos os ambientes de nuvem do Supply Chain Management do modelo IaaS para uma topologia hospedada no Service Fabric. Essa mudança apresenta melhor escalabilidade e facilita o gerenciamento de serviços. Portanto, as operações de implantação e manutenção são mais rápidas. Da mesma forma, os componentes de serviços estão sendo migrados para o conceito de microsserviços e o modelo de hospedagem de serviços [mudará](https://docs.microsoft.com/virtualization/windowscontainers/about/containers-vs-vm) de um modelo de máquina virtual (VM) para uma arquitetura conteinerizada leve.

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

## <a name="onboarding-in-two-stages"></a>Integração em dois estágios

O processo de integração para a topologia híbrida distribuída tem dois estágios. Durante o primeiro estágio, é necessário validar as personalizações para garantir que elas funcionarão na topologia distribuída com unidades de escala. Os ambientes de área restrita e produção são movidos somente durante o segundo estágio.

### <a name="stage-1-evaluate-customizations-in-one-box-development-environments"></a>Estágio 1: avaliar personalizações em ambientes de desenvolvimento de uma caixa

Antes de começar a integrar os ambientes de área restrita ou de produção, recomendamos explorar unidades de escala em uma configuração de desenvolvimento, como um ambiente de uma caixa (também conhecido como ambiente de 1 camada), para poder validar processos, personalizações e soluções. Durante esse estágio, os dados e as personalizações serão aplicadas a ambientes de uma caixa. Um ambiente assume a função do hub e o outro assume a função de uma unidade de escala. Essa configuração oferece a melhor forma de identificar e corrigir problemas. A compilação de acesso antecipado mais recente (PEAP) também pode ser usada para concluir esse estágio.

Para o estágio 1, você deve usar as [ferramentas de implantação da unidade de escala para ambientes de desenvolvimento de uma caixa](https://github.com/microsoft/SCMScaleUnitDevTools). Essas ferramentas permitem configurar as unidades de hub e de escala em um ou dois ambientes de caixa separados. As ferramentas são fornecidas como uma versão binária e no código-fonte no GitHub. Estude a wiki do projeto, que inclui um [guia de uso passo a passo](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide) que descreve como as ferramentas são usadas.

### <a name="stage-2-acquire-add-ins-and-deploy-in-your-sandbox-and-production-environments"></a>Etapa 2: adquirir suplementos e implantar nos ambientes de área restrita e de produção

Para integrar um dos ambientes de área restrita ou de produção à nova topologia, é necessário adquirir suplementos para uma ou mais unidades de escala de nuvem (e, no futuro, para unidade de escala de borda). Os suplementos concederão slots de projeto e de ambiente correspondentes no [LCS](https://lcs.dynamics.com/) para que os ambientes da unidade de escala possam ser implantados.

> [!NOTE]
> Os suplementos da unidade de escala não são acoplados a um número limitado de usuários, mas podem ser usados por qualquer usuário na assinatura existente, com base nas funções que o administrador atribui.

As unidades de escala são oferecidas em várias unidades de manutenção de estoque (SKUs) e opções de preço. Portanto, você pode escolher a opção que melhor atende ao volume de transação mensal planejado e os requisitos de desempenho.

A SKU de nível de entrada é conhecida como *Básica* e a SKU de melhor desempenho é conhecida como *Padrão*. Cada SKU é pré-carregada com um número específico de transações mensais. No entanto, é possível aumentar o orçamento de transações mensais adicionando suplementos excedentes para cada SKU.

:::image type="content" source="media/SKUs-highlevel.png" alt-text="Suplementos de unidades de escala de nuvem":::

> [!TIP]
> Para identificar o dimensionamento que melhor atende às suas necessidades, trabalhe com seu parceiro e a Microsoft para compreender o tamanho da transação mensal de que precisa.

A compra de cada suplemento da unidade de escala fornece um volume mensal de transações e também um número específico de slots de ambiente no LCS. Para cada Suplemento da Unidade de Escala de Nuvem, você tem direito a um novo slot de produção e um novo slot de área restrita. Durante o processo de integração, um novo projeto do LCS será adicionado com esses três slots. Os direitos de uso dos slots estão vinculados para que eles sejam usados como unidades de escala com um hub de nuvem.

Os suplementos excedentes não concedem o direito a novos slots de ambiente.

Se você quiser adquirir mais ambientes de área restrita, é possível comprar slots de área restrita regulares adicionais. A Microsoft pode ajudar você a habilitar esses slots como unidades de escala de área restrita para a topologia híbrida.

## <a name="onboard-to-the-distributed-hybrid-topology-for-supply-chain-management"></a>Integrar à topologia híbrida distribuída do Supply Chain Management

### <a name="select-your-lcs-project-tenant-and-the-detailed-onboarding-process"></a>Selecione o locatário de projeto do LCS e o processo de integração detalhado

Após concluir o planejamento de integração à topologia híbrida distribuída do Supply Chain Management, você usará o [portal do Gerente de Unidade de Escala](https://aka.ms/SCMSUM) para iniciar o processo de integração. No portal, selecione a guia **Locatários do Dynamics 365**. Essa guia mostra a lista de locatários dos quais sua conta faz parte e onde você é proprietário ou administrador de ambiente para um projeto do LCS.

Se o locatário que você está procurando não estiver nessa lista, acesse [LCS](https://lcs.dynamics.com/v2) e verifique se você é um administrador de ambiente ou um proprietário de projeto do projeto do LCS desse locatário. Somente contas do Azure Active Directory (Azure AD) do locatário selecionado estão autorizadas a concluir a experiência de inscrição.

> [!NOTE]
> Após aplicar alterações ao LCS, a lista de locatários poderá levar até 30 minutos para refletir as alterações.

Para cada locatário, a lista mostra o status de integração.

:::image type="content" source="media/cloud_edge-EnableHybrid1.png" alt-text="Lista de locatários na guia Locatários do Dynamics 365":::

Selecione **Clique aqui para começar** para solicitar a integração do locatário do LCS. Você deve aceitar os termos. Você também deve fornecer um endereço de email comercial em que a Microsoft possa enviar comunicações relacionadas ao processo de integração.

:::image type="content" source="media/cloud_edge-EnableHybrid2.png" alt-text="Envio de inscrição para um locatário":::

A Microsoft revisará a solicitação e informará sobre as próximas etapas enviando um email para o endereço fornecido no formulário de inscrição. A Microsoft trabalhará com você para habilitar as unidades de escala na topologia híbrida para seu cenário de negócios.

Depois que a integração for concluída, você poderá usar a porta para configurar unidades de escala e cargas de trabalho.

### <a name="manage-cloud-scale-units-and-workloads-by-using-the-scale-unit-manager-portal"></a><a name="scale-unit-manager-portal"></a>Gerenciar unidades de escala de nuvem e cargas de trabalho usando o portal de Gerente de Unidade de Escala

Acesse o [portal do Gerente e Unidade de Escala](https://aka.ms/SCMSUM) e entre usando sua conta de locatário. Na página **Configurar unidades de escala**, você poderá adicionar um ambiente de hub, caso ainda não esteja listado. Você pode selecionar o hub a ser configurado com unidades de escala e cargas de trabalho.

:::image type="content" source="media/cloud_edge-Manage.png" alt-text="Experiência de gerenciamento de unidade de escala e carga de trabalho":::

Para adicionar uma ou mais unidades de escala que estejam disponíveis em suas assinaturas, selecione **Adicionar unidades de escala**.

Na guia **Cargas de trabalho definidas**, use o botão **Criar carga de trabalho** para adicionar uma carga de trabalho de gerenciamento de depósito a uma das unidades de escala. Para cada carga de trabalho, você deve especificar o contexto dos processos que serão propriedade da carga de trabalho. Para cargas de trabalho de gerenciamento de depósito, o contexto é um depósito específico em um site e uma entidade legal específicos.

:::image type="content" source="media/cloud_edge-DefineWorkload.png" alt-text="Criação de carga de trabalho":::

> [!TIP]
> Com o tempo, melhorias incrementais serão adicionadas à experiência do Gerente de Unidade de Escala para facilitar as operações de gerenciamento do ciclo de vida. Os recursos específicos da versão atual estão documentados em um manual integrado disponível para clientes que estão no processo de integração à topologia híbrida distribuída do Supply Chain Management. <!-- KFM: Add a link to the handbook when it is published -->

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
