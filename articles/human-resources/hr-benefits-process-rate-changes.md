---
title: Processar alterações de taxa
description: Este artigo explica como processar alterações da taxa de benefícios no Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitRate, BenefitEligibilityProcessResultViewer
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 09714c70cb00b1a1b5dbd4613bbd70ff11d35cb2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882943"
---
# <a name="process-rate-changes"></a>Processar alterações de taxa


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo explica como processar alterações da taxa de benefícios no Microsoft Dynamics 365 Human Resources quando um plano de benefícios novo ou existente tiver uma alteração nas configurações da regra de qualificação. Se uma nova regra de qualificação for criada e atribuída ao plano, isso fará com que o sistema execute novamente a qualificação do trabalhador de modo a verificar se agora ele pode estar qualificado para o plano com base nas novas opções de qualificação. 

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
