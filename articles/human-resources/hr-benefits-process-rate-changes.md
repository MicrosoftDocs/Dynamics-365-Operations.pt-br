---
title: Processar alterações de taxa
description: Processe alterações na taxa de benefícios no Microsoft Dynamics 365 Human Resources quando um plano de benefícios novo ou existente tiver uma alteração nas configurações da regra de qualificação.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9ebe5cfc2bdf7790770d27ece2dc67f7677db593
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008049"
---
# <a name="process-rate-changes"></a>Processar alterações de taxa

[!include [banner](includes/preview-feature.md)]

Processe alterações na taxa de benefícios no Microsoft Dynamics 365 Human Resources quando um plano de benefícios novo ou existente tiver uma alteração nas configurações da regra de qualificação. Se uma nova regra de qualificação for criada e atribuída ao plano, isso fará com que o sistema execute novamente a qualificação do trabalhador de modo a verificar se agora ele pode estar qualificado para o plano com base nas novas opções de qualificação. 

1. No espaço de trabalho **Gerenciamento de benefícios**, em **Processando**, selecione **Processamento de atualização de alteração de taxa**.

2. No caixa de diálogo **Executar processo de atualização de taxa de benefício**, especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | Período de inscrição | O período de inscrição para processar alterações de taxa. |

3. Se você deseja executar o processo em segundo plano, selecione **Executar em segundo plano** e execute as seguintes tarefas:

   1. Insira informações para o processo.

   2. Para configurar um trabalho recorrente, selecione **Recorrência**, insira as informações de recorrência e selecione **OK**.

   3. Para configurar um alerta de trabalho, selecione **Alertas**, selecione os alertas a receber e, em seguida, selecione **OK**.

   4. Selecione **OK**. O processo será executado com os parâmetros definidos por você.

4. Selecione **OK**.
