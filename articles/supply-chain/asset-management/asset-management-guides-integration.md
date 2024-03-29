---
title: Integrar Dynamics 365 Supply Chain Management (Gerenciamento de ativos) com Dynamics 365 Guides
description: Este artigo explica como integrar o módulo Gerenciamento de ativos no Microsoft Dynamics 365 Supply Chain Management com Dynamics 365 Guides para aproveitar guias de realidade misturada nos fluxos de trabalho de serviço e manutenção diários.
author: johanhoffmann
ms.date: 04/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-04-28
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: d06978bcbd6205111384f5c7cefdf34fdbdbfbf5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875674"
---
# <a name="integrate-dynamics-365-supply-chain-management-asset-management-with-dynamics-365-guides"></a>Integrar Dynamics 365 Supply Chain Management (Gerenciamento de ativos) com Dynamics 365 Guides

[!include [banner](../includes/banner.md)]

Você pode integrar o módulo **Gerenciamento de ativos** no Microsoft Dynamics 365 Supply Chain Management com Dynamics 365 Guides para aproveitar guias de realidade combinada nos fluxos de trabalho de serviço e manutenção diários. Se uma guia estiver associada a uma ordem de trabalho de gerenciamento de ativos, um trabalhador que abre a lista de verificação de manutenção da ordem de trabalho no aplicativo móvel do Supply Chain Management (Dynamics 365) verá que um guia está disponível. Em seguida, o trabalhador pode encontrar e abrir o guia no aplicativo do Dynamics 365 Guides HoloLens.

## <a name="prerequisites"></a>Pré-requisitos

Para poder anexar guias a ordens de trabalho de gerenciamento de ativos, você deve executar estes pré-requisitos:

- [Configurar o Dynamics 365 Supply Chain Management](../../fin-ops-core/fin-ops/index.md) versão 10.0.9 ou posterior.
- [Ative a gravação dupla para aplicativos de Supply Chain Management](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md).
- [Ative a versão de pré-lançamento](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#features-flighted-in-data-management-and-enabling-flighted-features) para o recurso **MRGuidesFeature**. (Para ambientes de produção, você deve primeiro enviar um tíquete de suporte para que seu locatário seja adicionado ao grupo de versão de pré-lançamento.)
- [Ative as seguintes chaves de configuração](/dynamicsax-2012/appuser-itpro/license-code-and-configuration-key-reference) na página **Configuração de licenças**:

    - Gerenciamento de ativos \> Realidade combinada de gerenciamento de ativos
    - Realidade combinada \> Guia de realidade combinada

- [Configurar Dynamics 365 Guides](/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) versão 200.0.0.96 ou posterior.

## <a name="use-dynamics-365-guides-with-asset-management"></a>Use Dynamics 365 Guides com Gerenciamento de ativos

Para associar uma guia, use a linha da lista de verificação de manutenção no gerenciamento de ativos. Você pode criar a associação por meio de um modelo de lista de verificação de manutenção, um tipo de trabalho de manutenção ou uma ordem de trabalho, pois todos os três contêm linhas da lista de verificação de manutenção. Você pode economizar tempo usando um modelo, pois um modelo pode ser associado a todos os tipos de trabalho de manutenção que o usam. Por exemplo, um guia associado a um tipo de trabalho de manutenção é associado automaticamente a todas as ordens de trabalho que especificam esse tipo de trabalho. Por outro lado, um guia associado diretamente a uma ordem de trabalho existe somente para essa ordem de trabalho.

### <a name="associate-a-guide-with-a-maintenance-checklist-template"></a>Associar uma guia a um modelo da lista de verificação de manutenção

Para associar uma guia a um modelo da lista de verificação de manutenção, siga estas etapas.

1. Crie uma guia usando o PC do Dynamics 365 Guides e os aplicativos do HoloLens. Para obter informações sobre como criar uma guia, consulte os artigos a seguir:

    - [Use o aplicativo do PC para criar uma guia](/dynamics365/mixed-reality/guides/pc-app-overview)
    - [Use o aplicativo do HoloLens para colocar os hologramas](/dynamics365/mixed-reality/guides/hololens-app-overview)

1. No Supply Chain Management, [crie um modelo de lista de verificação de manutenção](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-checklist-template).
1. Associe a guia criada por uma linha da lista de verificação de manutenção no novo modelo da lista de verificação de manutenção:

    1. Na Guia Rápida **Linhas da lista de verificação de manutenção**, selecione a linha com a qual você deseja associar a guia.
    1. Na Guia Rápida **Guias associadas**, selecione **Adicionar guia**.

        ![Associar uma guia a uma linha da lista de verificação de manutenção.](media/am-guides-integration-add-guide.png "Associar uma guia a uma linha da lista de verificação de manutenção")

    1. No campo **Nome**, selecione uma guia, e depois seleciona **Salvar**.

        ![Selecionar uma guia no campo Nome.](media/am-guides-integration-select-guide.png "Selecionar uma guia no campo Nome")

1. Associar o modelo da lista de verificação de manutenção a um tipo de trabalho:

    1. [Crie um tipo de trabalho de manutenção](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-job-type) ou selecione um tipo de trabalho de manutenção existente.
    1. No Painel de Ações, selecione **Padrões de tipos de trabalho de manutenção**.

        ![Botão Padrões do tipo de trabalho de manutenção.](media/am-guides-integration-job-defaults.png "Botão Padrões do tipo de trabalho de manutenção")

    1. Crie uma linha e selecione **Salvar**.

        ![Criar uma linha.](media/am-guides-integration-add-line.png "Criar uma linha")

    1. No Painel de Ação, selecione **Lista de verificação de manutenção**.

        ![Botão Lista de verificação de manutenção.](media/am-guides-integration-maintenance-checklist.png "Botão Lista de verificação de manutenção")

    1. Na Guia Rápida **Linhas da lista de verificação de manutenção**, adicione uma linha e mude o valor do campo **Tipo** como **Modelo**.

        ![Alterar o Valor do tipo.](media/am-guides-integration-checklist-lines.png "Alterar o Valor do tipo")

    1. Na Guia Rápida **Detalhes da linha**, no campo **Modelo**, selecione o modelo que você associou com a guia e selecione **Salvar**.

        ![Selecione o modelo.](media/am-guides-integration-checklist-line-details.png "Selecione o modelo")

1. [Crie uma ordem de trabalho](work-orders/manually-created-workorders.md#create-work-order) e selecione o tipo de trabalho de manutenção que usa o modelo de lista de verificação de manutenção com o qual você associou a guia. A guia é automaticamente associada à ordem de trabalho.

    ![Selecione um tipo de trabalho de manutenção.](media/am-guides-integration-create-work-order.png "Selecione um tipo de trabalho de manutenção")

1. Exiba a guia associada à ordem de trabalho e aos trabalhadores:

    1. Abra o [Espaço de trabalho móvel de gerenciamento de ativos](asset-management-mobile-workspace.md) para acessar a ordem de trabalho.
    1. [Abra a lista de verificação de manutenção](asset-management-mobile-workspace.md#view-maintenance-checklist-on-a-work-order-job) para a ordem de trabalho.
    1. Selecione uma linha da lista de verificação para ver a guia associada.

        ![Guia associada a uma linha da lista de verificação.](media/am-guides-integration-show-guide.png "Guia associado a uma linha da lista de verificação")

    1. Abrir a guia no HoloLens.

        ![Abrir a guia no HoloLens.](media/am-guides-integration-hololens-select.png "Abrir a guia no HoloLens")

> [!NOTE]
> Também é possível associar uma guia diretamente na lista de verificação de manutenção de uma ordem de trabalho ou de um tipo de trabalho.

> [!IMPORTANT]
> Há um problema conhecido em que, quando você associa um modelo de lista de verificação de manutenção a um tipo de trabalho de manutenção padrão, a guia vinculada ao modelo não aparece na Guia Rápida **Guias associadas** da página **Padrões de tipo de trabalho de manutenção**. No entanto, a guia será exibida depois que esse tipo de trabalho for aplicado a uma ordem de trabalho na Guia Rápida **Guias associadas**.

## <a name="see-also"></a>Consulte também

- [Visão geral da gravação dupla](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview.md)
- [Visão geral do gerenciamento de ativos](index.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]