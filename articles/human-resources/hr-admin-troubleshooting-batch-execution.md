---
title: Redefinir trabalhos em lotes presos
description: Este tópico explica como resolver problemas de trabalhos em lotes que estão presos.
author: andreabichsel
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: 01ef0bf8ccc486614eec42d3fb6f0b2941fc47c0
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794940"
---
# <a name="reset-stuck-batch-jobs"></a>Redefinir trabalhos em lotes presos

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a>Problema

O Microsoft Dynamics 365 Human Resources pode enfrentar problemas com trabalhos em lotes que estão presos em um estado **Executando** ou **Cancelando** e não são concluídos.

## <a name="resolution"></a>Resolução

Quando um trabalho em lotes está preso em um estado **Executando** ou **Cancelando**, é possível redefinir o status ao forçar o cancelamento do trabalho. Após cancelá-lo, você pode redefinir o trabalho em lotes ao defini-lo com um status **Aguardando**. Em seguida, ele será selecionado novamente para execução na próxima execução de lote agendada.

1. No espaço de trabalho **Administração do sistema**, selecione a página **Links** e selecione **Trabalhos em lote**.

2. Na página de lista **Trabalho em lotes**, selecione o trabalho que deve ser redefinido.

3. Na faixa de opções de ação, selecione **Forçar cancelamento** e confirme a ação.

   > [!NOTE]
   > A ação **Forçar cancelamento** está disponível somente quando o trabalho em lotes tem um status **Executando** ou **Cancelando** e não houver execução em lotes ou processos de cancelamento do trabalho em andamento.

4. Na faixa de opções de ação, selecione **Alterar status**.

5. Na página **Selecionar novo status**, selecione **Aguardando** e depois **OK**.

   ![Selecionar um novo status de trabalho em lotes](./media/hr-admin-reset-batch-job-status.png)

## <a name="see-also"></a>Consulte também

[Otimizar o desempenho ao agendar trabalhos em lotes após o expediente](hr-admin-troubleshooting-batch-jobs.md)<br>
[Otimizar o desempenho com tarefas de limpeza automática](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]