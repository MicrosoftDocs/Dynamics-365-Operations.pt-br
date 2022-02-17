---
title: Processar alterações de taxa
description: Este tópico explica como processar alterações da taxa de benefícios no Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitRate, BenefitEligibilityProcessResultViewer
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5e0dfbdde8ee950a0341fffb1e268fff05434953
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070366"
---
# <a name="process-rate-changes"></a>Processar alterações de taxa


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico explica como processar alterações da taxa de benefícios no Microsoft Dynamics 365 Human Resources quando um plano de benefícios novo ou existente tiver uma alteração nas configurações da regra de qualificação. Se uma nova regra de qualificação for criada e atribuída ao plano, isso fará com que o sistema execute novamente a qualificação do trabalhador de modo a verificar se agora ele pode estar qualificado para o plano com base nas novas opções de qualificação. 

1. No espaço de trabalho **Gerenciamento de benefícios**, em **Processando**, selecione **Processamento de atualização de alteração de taxa**.

2. No caixa de diálogo **Executar processo de atualização de taxa de benefício**, especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | **Período de inscrição** | O período de inscrição para processar alterações de taxa. |

3. Se você deseja executar o processo em segundo plano, selecione **Executar em segundo plano** e execute as seguintes tarefas:

   1. Insira informações para o processo.

   2. Para configurar um trabalho recorrente, selecione **Recorrência**, insira as informações de recorrência e selecione **OK**.

   3. Para configurar um alerta de trabalho, selecione **Alertas**, selecione os alertas a receber e, em seguida, selecione **OK**.

   4. Selecione **OK**. O processo será executado com os parâmetros definidos por você.

4. Selecione **OK**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
