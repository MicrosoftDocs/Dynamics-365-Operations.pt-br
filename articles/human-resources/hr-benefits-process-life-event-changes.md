---
title: Processar alterações de eventos de vida
description: Processe alterações de eventos de vida no Microsoft Dynamics 365 Human Resources para alterações de eventos de vida.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes, BenefitEligibilityProcessResultViewer
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1bfbd7347581e57edcab39a675b17ef66e262582
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059007"
---
# <a name="process-life-event-changes"></a>Processar alterações de eventos de vida

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