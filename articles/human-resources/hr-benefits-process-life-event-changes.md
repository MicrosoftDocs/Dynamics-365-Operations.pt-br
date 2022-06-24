---
title: Processar alterações de eventos de vida
description: Este artigo explica como processar alterações de eventos da vida no Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 38b36f2165c9794091321c193f10dd37cc92b866
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858175"
---
# <a name="process-life-event-changes"></a>Processar alterações de eventos de vida


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Processe alterações de eventos de vida no Microsoft Dynamics 365 Human Resources para duas alterações de eventos de vida:

- Alterações de aniversário
- A regra de qualificação substitui as alterações de expiração 

1. No espaço de trabalho **Gerenciamento de benefícios**, em **Processando**, selecione **Processamento da alteração de eventos de vida**.

2. No caixa de diálogo **Executar o processamento da alteração de eventos de vida**, especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | Período de inscrição | O período de inscrição para processar as alterações de eventos de vida. |
   | Pessoa jurídica em geral | A entidade legal para processar alterações de eventos de vida. |

3. Se você deseja executar o processo em segundo plano, selecione **Executar em segundo plano** e execute as seguintes tarefas:

   1. Insira informações para o processo.

   2. Para configurar um trabalho recorrente, selecione **Recorrência**, insira as informações de recorrência e selecione **OK**.

   3. Para configurar um alerta de trabalho, selecione **Alertas**, selecione os alertas a receber e, em seguida, selecione **OK**.

   4. Selecione **OK**. O processo será executado com os parâmetros definidos por você.

4. Selecione **OK**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
