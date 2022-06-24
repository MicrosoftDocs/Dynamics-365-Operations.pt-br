---
title: Redefinir trabalhos em lote presos
description: Este artigo explica como resolver problemas de trabalhos em lote que estão presos.
author: twheeloc
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: b56a16257a45dd093d10b7550b13d6a4a1ceb1f7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896008"
---
# <a name="reset-stuck-batch-jobs"></a>Redefinir trabalhos em lote presos


[!INCLUDE [PEAP](../includes/peap-2.md)]

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

   ![Selecionar um novo status de trabalho em lotes.](./media/hr-admin-reset-batch-job-status.png)

## <a name="see-also"></a>Consulte também

[Otimizar o desempenho ao agendar trabalhos em lote após o expediente](hr-admin-troubleshooting-batch-jobs.md)<br>
[Otimizar o desempenho com tarefas de limpeza automática](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
