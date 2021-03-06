---
title: Otimizar o desempenho com tarefas de limpeza automática
description: Este artigo explica como resolver alguns problemas de desempenho com o Microsoft Dynamics 365 Human Resources limpando o histórico de trabalhos em lotes.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 6a9e94e282aa8f101b42c1378ef21c6c1fe0477e
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053482"
---
# <a name="optimize-performance-with-auto-cleanup-tasks"></a>Otimizar o desempenho com tarefas automáticas de limpeza

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Emissão**

O Microsoft Dynamics 365 Human Resources pode apresentar problemas de desempenho se o histórico de trabalhos em lotes se tornar muito grande.

**Causa**

Os trabalhos em lote que são executados com frequência geralmente podem levar ao crescimento insustentável do histórico de trabalhos em lotes. Isso pode causar problemas de desempenho. 

**Resolução**

Agende uma tarefa automática limpar o histórico de trabalhos em lotes. Recomendamos configurar a tarefa para ser executada semanalmente, mas pode ser necessário executar a limpeza com mais ou menos frequência, dependendo do seu ambiente. O procedimento a seguir contém nossas configurações recomendadas, mas você pode modificá-las de acordo com suas necessidades.

1. No Human Resources, selecione **Administração do sistema**.

2. Na barra **Pesquisa** , insira **Limpeza de histórico de trabalhos em lote**.

   ![Pesquisar limpeza de histórico de trabalhos em lotes](media/talent-batch-history-cleanup-search-bar.png)

3. No **Limite de histórico (dias)**, insira **30**.

   ![Defina o limite de histórico como 30](media/talent-batch-history-cleanup-history-limit.png)

4. Selecione **Executar em segundo plano** e **Recorrência**.

   ![Definir a recorrência](media/talent-batch-history-cleanup-recurrence.png)

5. Em **Definir a recorrência**, defina a **Data inicial** e a **Hora inicial** para ocorrer fora do horário comercial ou no final de semana e selecione **NENHUMA DATA DE TÉRMINO**. 

   ![Definir a data e a hora de início da recorrência](media/talent-batch-history-cleanup-define-recurrence.png)

6. Em **PADRÃO DE RECORRÊNCIA**, selecione **Dias** e **REPETIR APÓS O INTERVALO ESPECIFICADO** como **7**.

   ![Definir limpeza para ser repetida semanalmente](media/talent-batch-history-cleanup-recurrence-pattern.png)

7. Selecione **OK**.

8. Altere quaisquer outros parâmetros em **Executar em segundo plano** conforme necessário e selecione **OK**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]