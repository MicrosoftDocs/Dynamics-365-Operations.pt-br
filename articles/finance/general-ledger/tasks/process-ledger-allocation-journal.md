---
title: Processar diário de alocação do razão
description: Este tópico explica como processar uma solicitação de alocação no Dynamics 365 Finance.
author: aprilolson
manager: AnnBe
ms.date: 07/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 882362a03e4fc4e249b092caea374640813eef88
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186063"
---
# <a name="process-ledger-allocation-journal"></a>Processar diário de alocação do razão

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este tópico explica como processar uma solicitação de alocação. Use a página Processar solicitação de alocação para criar um diário de alocação que possa ser revisto e aprovado antes do lançamento na Contabilidade ou que possa ser lançado diretamente na Contabilidade. Antes de criar um diário de alocações, deve haver pelo menos uma regra de alocação do razão ativa. Esta tarefa usa a empresa de demonstração USMF.

1. No painel de navegação, vá para **Módulos > Contabilidade > Alocações > Processar solicitação de alocação**.
2. No campo **Regra**, selecione o registro desejado no menu suspenso.
3. No campo **A partir da data**, insira uma data.

    - O campo **A partir da data** é muito importante quando o razão é a fonte de dados para a regra. Essa data controla quais saldos do razão serão incluídos na alocação.  
    - No campo **Fonte zero**, selecione **Parar**. Isso interromperá o processo de alocação e exibirá uma mensagem informando que um valor de origem zero foi selecionado.  

4. No campo **Opções de proposta**, selecione **Somente proposta**. Selecione **Somente proposta** para revisar e opcionalmente aprovar o resultado em Diários de alocação antes de lançar a alocação na Contabilidade.  
5. No campo Lançamento GL, insira uma data.
6. Selecione **OK**.
7. No painel de navegação, vá para **Módulos > Contabilidade > Alocações > Diários de alocação**.
8. Selecione **Linhas**.
9. Selecione **Lançar**.
10. Selecione **Lançar**.

