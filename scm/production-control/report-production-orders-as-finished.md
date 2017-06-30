---
title: "Relatar ordens de produção como concluídas"
description: "Relatar como concluído é um estágio da produção. Nesta fase, um produto acabado é reportado e movido da ordem de produção para o inventário."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdJournalTransJob, ProdJournalTransProd, ProdJournalTransRoute, ProdParmReportFinished, ProdRouteOprOverview
audience: Application User
ms.reviewer: annbe
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 27061
ms.assetid: 1c2dfc54-a293-49f2-9b96-5a912ac5762c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 52607d645c6eaf4ff97d2c4bf8abc6ec1374fd7e
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="report-production-orders-as-finished"></a>Relatar ordens de produção como concluídas

[!include[banner](../includes/banner.md)]


Relatar como concluído é um estágio da produção. Nesta fase, um produto acabado é reportado e movido da ordem de produção para o inventário.

Quando uma quantidade das mercadorias acabadas é informada como concluída em uma ordem de produção, ela é atualizada como disponível no estoque. As quantidades parciais da quantidade da ordem originalmente planejada podem ser informadas como concluídas. Também é possível relatar as quantidades de erro com um motivo de erro associado ao relatar quantidades como concluídas. Quando a ordem de produção atingir o estágio Informado como concluído, isso indicará que nenhuma outra quantidade será informada na ordem de produção.
As características a seguir também estão associadas ao processo **Informar como concluído**:
-   É possível configurar o consumo de matéria-prima e de tempo que seja proporcional à quantidade informada (baixa de estoque)
-   O trabalho de armazenamento pode ser gerado para itens habilitados para os processos de depósito.
-   O valor do custo planejado ou padrão das mercadorias concluídas pode ser configurado para ser informado para as contas contábeis.
-   Uma ordem de qualidade pode ser criada para a quantidade informada com base na configuração de uma associação de qualidade.

A quantidade é informada no local de saída. O trabalho de depósito é então gerado para mover a quantidade do local de saída para seu destino final definido pela diretiva da localização do trabalho de armazenamento.

-   Uma ordem de qualidade pode ser criada quando uma ordem de produção é informada como concluída se uma associação de qualidade tiver sido configurada.

## <a name="set-a-production-order-to-reporting-as-finished"></a>Definir uma ordem de produção como Informada como concluída
Você pode definir uma ordem de produção como **Informar como concluída** por meio da função de atualização da ordem de produção padrão ou por meio dos diários de roteiros e dos diários de ficha de trabalho ou por meio do diário **Informar como concluído**. Você também pode atualizar o estágio para **Informar como concluído** por meio das páginas de terminal de ficha de trabalho e de dispositivo de ficha de trabalho quando informa no último trabalho da ordem de produção. Por fim, você pode habilitar a opção **Informar como concluído** como um processo para a solução de dispositivo portátil para depósito.  




