---
title: Otimizar o desempenho ao agendar trabalhos em lote após o expediente
description: Este artigo explica como resolver problemas de desempenho com o Microsoft Dynamics 365 Human Resources agendando para depois do expediente os trabalhos em lotes de execução demorada.
author: twheeloc
ms.date: 06/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 6efb0a906bb948a47f03665dd6e7a8dd43434083
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896066"
---
# <a name="optimize-performance-by-scheduling-batch-jobs-after-hours"></a>Otimizar o desempenho agendando trabalhos em lotes após o expediente


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



## <a name="issue"></a>Emitir

O Microsoft Dynamics 365 Human Resources poderá ter problemas de desempenho se os trabalhos em lotes demorados forem executados no horário comercial normal.

## <a name="resolution"></a>Resolução

Agende os trabalhos em lotes a seguir fora do horário comercial. Também é recomendável rever a frequência de trabalhos em lotes executados habitualmente. Se possível, reduza a recorrência do trabalho em lotes. Em muitos casos, a frequência padrão é suficiente.

Os trabalhos em lotes a seguir devem ser executados à noite ou depois do expediente. Verifique o fuso horário desses trabalhos em lotes recorrentes. Alguns trabalhos em lotes podem usar o Horário Padrão do Pacífico (PST).

| Trabalho em Lotes | Ocorrência padrão |
| --- | --- |
| Limpeza do histórico de trabalhos em lotes | 1 vez por mês |
| Limpeza de preparo de exportação | 1 vez por dia |
| Sincronização de solicitação perdida da integração do Common Data Service | 1 vez por dia |
| Trabalho do sistema de compactação de banco de dados que precisa ser executado regularmente fora do horário comercial | 1 vez por dia |
| Trabalho do sistema de recriação de índice de banco de dados que precisa ser executado regularmente fora do horário comercial | 1 vez por dia |

1. No Human Resources, selecione **Administração do sistema**.

2. Na barra **Pesquisa**, procure um dos trabalhos em lotes acima.

3. Selecione **Executar em segundo plano** e, depois, **Recorrência**.

   ![Definir a recorrência.](media/talent-batch-history-cleanup-recurrence.png)

4. Em **Definir a recorrência**, defina a **Data inicial** e a **Hora inicial** para ocorrer fora do horário comercial ou no final de semana. Selecione **Sem data de término**. 

   ![Definir a data e a hora de início da recorrência.](media/talent-batch-history-cleanup-define-recurrence.png)

5. Selecione **OK**.

6. Se necessário, altere quaisquer outros parâmetros em **Executar em segundo plano** e selecione **OK**.

## <a name="additional-resources"></a>Recursos adicionais

[Otimizar o desempenho com tarefas de limpeza automática](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
