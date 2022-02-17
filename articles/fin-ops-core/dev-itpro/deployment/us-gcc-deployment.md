---
title: Dynamics 365 Finance e Dynamics 365 Supply Chain Management na Nuvem da Comunidade Governamental dos EUA (GCC)
description: Este tópico fornece informações sobre os produtos Microsoft Dynamics 365 US Government que estão disponíveis para entidades governamentais e particulares qualificadas.
author: hasaid
ms.date: 11/12/2021
ms.topic: article
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: hasaid
ms.search.validFrom: 2021-11-09
ms.openlocfilehash: 0c8b88e5d190f6dc9beb9342909d1e489d4af10b
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062277"
---
# <a name="dynamics-365-finance-and-dynamics-365-supply-chain-management-in-us-government-community-cloud-gcc"></a>Dynamics 365 Finance e Dynamics 365 Supply Chain Management na Nuvem da Comunidade Governamental dos EUA (GCC)

[!include [banner](../includes/banner.md)]



Selecione os produtos Microsoft Dynamics 365 para o governo dos Estados Unidos (EUA) que estão disponíveis para entidades governamentais e particulares qualificadas. Essas entidades estão limitadas aos seguintes tipos:

- Entidades governamentais federais, estaduais, locais, tribais e territoriais
- Entidades particulares que usam o Dynamics 365 US Government para fornecer soluções para entidades governamentais ou membros qualificados da comunidade na nuvem
- Entidades privadas que têm dados de clientes sujeitos a regulamentações governamentais e o Dynamics 365 US Government é o serviço adequado para atender aos requisitos regulatórios

Para obter informações, consulte [Dynamics 365 US Government](/power-platform/admin/microsoft-dynamics-365-government).

## <a name="onboarding"></a>Integração

Para concluir a integração inicial de um projeto de implementação no Lifecycle Services (LCS) do Microsoft Dynamics, siga as instruções em [Integrar um projeto de implementação](../../../fin-ops-core/fin-ops/imp-lifecycle/onboard.md). No entanto, não use o link para o LCS público fornecido nessas instruções. Em vez disso, use a seguinte URL para abrir o LCS para a Nuvem da Comunidade Governamental dos EUA (GCC): <https://gov.lcs.microsoftdynamics.us>.

Depois que a integração inicial for concluída, siga as instruções em [Integração de projetos](../lifecycle-services/project-onboarding.md). Mais uma vez, use [LCS para GCC](https://gov.lcs.microsoftdynamics.us) em vez de LCS público.

## <a name="environment-deployment"></a>Implantação do ambiente

Depois de concluir a integração do projeto, você poderá revisar os recursos adicionais do LCS descritos em [Lifecycle Services (LCS) para clientes dos aplicativos de Finanças e Operações](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md). Em seguida, siga para a implantação do ambiente.

- Para implantar ambientes gerenciados pela Microsoft via LCS, siga as instruções em [Lifecycle Services (LCS) para clientes dos aplicativos de Finanças e Operações](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md#new-deployment-experience).
- Para ambientes hospedados na nuvem, consulte [Implantar e acessar ambientes de desenvolvimento](../../../fin-ops-core/dev-itpro/dev-tools/access-instances.md). Você também deve concluir o processo de integração do Gerenciador de Recursos para seus conectores, conforme descrito em [Concluir o processo de integração do Azure Resource Manager para projetos de Lifecycle Services do governo dos EUA](arm-onbarding-us-goverment.md).

> [!NOTE]
> Para os projetos de LCS do governo dos EUA, só há suporte para assinatura específicas do Azure Governamental.

## <a name="features-that-arent-available"></a>Recursos que não estão disponíveis

Alguns recursos não estarão disponíveis para implantação na GCC ou não estarão disponíveis para uso com o Dynamics 365 na GCC. Por exemplo, os serviços Azure DevOps não estarão disponíveis na GCC. No entanto, os serviços Azure DevOps local ou Azure DevOps público podem ser usados. Para obter informações detalhadas sobre a disponibilidade de recursos, consulte [os aplicativos comerciais Disponibilidade de recursos de aplicativos de negócios para o governo dos EUA](https://aka.ms/BAPFunctionalParity).

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="are-dynamics-365-finance-and-dynamics-365-supply-chain-management-supported-in-gcc-high"></a>O Dynamics 365 Finance e o Dynamics 365 Supply Chain Management têm suporte na GCC-High?

Não. O Dynamics 365 Finance e o Dynamics 365 Supply Chain Management têm suporte somente na GCC.

### <a name="can-i-use-public-azure-devops-with-finance-and-supply-chain-management-in-gcc"></a>Posso usar o Azure DevOps público com o Finance e o Supply Chain Management na GCC?

Sim, você pode usar serviços do Azure DevOps público se não tiver requisitos para uma solução certificada pelo Federal Risk and Authorization Management Program (FEDRAMP). Como alternativa, você pode usar o Azure DevOps Server.

### <a name="can-i-deploy-a-cloud-hosted-environment-tier-1-development-environment-on-an-azure-commercial-subscription"></a>Posso implantar um ambiente de desenvolvimento de nível 1 hospedado na nuvem em uma assinatura do Azure Commercial?

Não. No [LCS para GCC](https://gov.lcs.microsoftdynamics.us), você deve usar uma assinatura do Azure Governamental para implantar um ambiente hospedado na nuvem.

### <a name="what-can-i-do-if-i-need-a-package-from-the-shared-asset-library-but-it-isnt-available-in-lcs-for-gcc"></a>O que posso fazer se precisar de um pacote da Biblioteca de ativos compartilhados, mas ele não estiver disponível no LCS para GCC?

Você pode baixar o mesmo pacote da Biblioteca de ativos compartilhados no [LCS público](https://lcs.dynamics.com). Como alternativa, seu parceiro pode ajudar você a baixar o pacote.

### <a name="is-the-code-upgrade-tool-available-in-gcc"></a>A ferramenta de atualização de código está disponível na GCC?

Não, a ferramenta de atualização de código não está disponível na GCC no momento. No entanto, você pode criar um projeto de cliente potencial no [LCS público](https://lcs.dynamics.com) e usar a ferramenta de atualização de código. Observe que não será possível implantar ambientes em projetos de cliente potencial.

### <a name="can-my-partner-open-a-support-ticket-on-my-behalf"></a>Meu parceiro pode abrir um tíquete de suporte em meu nome?

Sim. No entanto, se o parceiro usar uma identidade que não seja da GCC, o tíquete de suporte será direcionado para a fila de suporte público. Recomendamos que você use o direito de cliente da GCC no LCS para abrir tíquetes de suporte.

## <a name="see-also"></a>Consulte também

- [Dynamics 365 US Government](/power-platform/admin/microsoft-dynamics-365-government)
- [Disponibilidade de recursos de aplicativos de negócios para o governo dos EUA](https://aka.ms/BAPFunctionalParity).
- [Guia do usuário do Lifecycle Services (LCS)](../../../fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide.md)
- [Visão geral da implantação de nuvem](../../../fin-ops-core/dev-itpro/deployment/cloud-deployment-overview.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
