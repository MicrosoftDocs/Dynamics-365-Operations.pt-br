---
title: Espaço de trabalho de gerenciamento de benefícios
description: Este tópico descreve o espaço de trabalho Gerenciamento de benefícios no Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 02/24/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-24
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8f17685dab8159522ec88af0fa6ca9c99c346b7b
ms.sourcegitcommit: 105f65468b45799761c26e5d0ad9df4ff162c38d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "5488183"
---
# <a name="benefits-management-workspace"></a>Espaço de trabalho Gerenciamento de benefícios

[!include [applies to](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

Este tópico descreve o espaço de trabalho **Gerenciamento de benefícios** no Dynamics 365 Human Resources.

> [!NOTE]
> Para exibir o espaço de trabalho **Gerenciamento de benefícios**, você deve primeiro habilitar o recurso **(Versão preliminar) Espaço de trabalho de gerenciamento de benefícios** no Gerenciamento de recursos. Para obter mais informações sobre como habilitar os recursos de visualização, consulte [Gerenciar recursos](../hr-admin-manage-features.md).<br><br>![Habilitar espaço de trabalho Gerenciamento de benefícios](./media/hr-benefits-management-workspace-enable.png)

O espaço de trabalho **Gerenciamento de benefícios** fornece uma exibição rápida dos itens de benefícios que exigem sua atenção. Nesta página, você pode ver:

- Totais de itens aguardando ação
- Trabalhadores com seleções não confirmadas
- Trabalhadores recém-inscritos em benefícios
- Trabalhadores com eventos de vida futuros
- Novos contratados que não estão inscritos
- Trabalhadores com eventos de vida ativos
- Trabalhadores com inscrições abertas que não optaram por planos

![Espaço de trabalho de gerenciamento de benefícios](./media/hr-benefits-management-workspace.png)

## <a name="view-action-items"></a>Exibir itens de ação

Você pode exibir itens de ação selecionando um bloco ou uma guia. Se você selecionar uma guia, poderá exibir e selecionar trabalhadores na página do espaço de trabalho.

![Itens de ação](./media/hr-benefits-management-workspace-action-items.png)

Se você selecionar um bloco, vá para a página dessa área. Por exemplo, a seleção de um desses blocos exibe a página **Planos de benefícios do trabalhador**, filtrada para os funcionários nos quais você precisa executar uma ação:

- **Seleções não confirmadas**
- **Abrir inscrições com planos sem check-out**
- **Inscrito em benefícios**
- **Nova contratação não inscrita**

![Planos de benefícios para o trabalhador](./media/hr-benefits-management-workspace-plans.png)

A seleção do bloco **Eventos de vida ativos** ou **Eventos de vida futuros** leva você a uma lista de eventos de vida ativos ou futuros.

![Eventos de vida](./media/hr-benefits-management-workspace-life-events.png)

## <a name="processing"></a>Processando

Para processar a qualificação da inscrição, eventos de vida ou atualizações da alteração de taxa, selecione o item apropriado na barra de navegação.

![Processamento](./media/hr-benefits-management-workspace-processing.png)

Para exibir resultados do processo, selecione **Resultados do processo** na página.

![Resultados do processo](./media/hr-benefits-management-workspace-process-results.png)

Para obter mais informações sobre o processamento de benefícios, consulte:

- [Processar qualificação da inscrição](hr-benefits-process-enrollment-eligibility.md)
- [Processar alterações de eventos de vida](hr-benefits-process-life-event-changes.md)
- [Processar qualificação para eventos de vida](hr-benefits-process-life-event-eligibility.md)
- [Processar eventos de vida](hr-benefits-process-life-events.md)
- [Processar alterações de taxa](hr-benefits-process-rate-changes.md)

## <a name="change-period"></a>Alterar período

Para exibir um período de benefícios diferente, selecione-o no menu suspenso **Período**.

![Alterar período](./media/hr-benefits-management-workspace-period.png)

## <a name="view-more-options"></a>Exibir mais opções

Para exibir mais informações e ações que podem ser executadas, selecione **Links**.

![Links](./media/hr-benefits-management-workspace-links.png)

## <a name="see-also"></a>Consulte também

[Visão geral do gerenciamento de benefícios](hr-benefits-management-overview.md)