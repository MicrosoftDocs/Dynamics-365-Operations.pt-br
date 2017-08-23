--- 
title: "Processar diário de alocação do razão"
description: "Use a página Processar solicitação de alocação para criar um diário de alocação que possa ser revisto e aprovado antes do lançamento na Contabilidade ou que possa ser lançado diretamente na Contabilidade."
author: aprilolson
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 1189ffeae052c72542b3b403a6b7a6e415b005c4
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="process-ledger-allocation-journal"></a>Processar diário de alocação do razão

[!include[task guide banner](../../includes/task-guide-banner.md)]

Use a página Processar solicitação de alocação para criar um diário de alocação que possa ser revisto e aprovado antes do lançamento na Contabilidade ou que possa ser lançado diretamente na Contabilidade. Antes de criar um diário de alocações, deve haver pelo menos uma regra de alocação do razão ativa. Esta tarefa usa a empresa de demonstração USMF.

1. Vá para Contabilidade > Alocações > Processar solicitação de alocação.
2. No campo Regra, clique no botão suspenso para abrir a pesquisa.
3. Na lista, localize e selecione o registro desejado.
4. Na lista, clique no link na linha selecionada.
5. No campo A partir da data, insira uma data.
    * O campo A partir da data é muito importante quando o razão é a fonte de dados para a regra. Essa data controla quais saldos do razão serão incluídos na alocação.     No campo Fonte zero, selecione Parar. Isso interromperá o processo de alocação e exibirá uma mensagem informando que um valor de origem zero foi selecionado.  
6. No campo Opções de proposta, selecione 'Somente proposta'.
    * Selecione Proposta apenas para revisar e opcionalmente aprovar o resultado em Diários de alocação antes de lançar a alocação na Contabilidade.  
7. No campo Lançamento GL, insira uma data.
8. Clique em OK.
9. Vá para Contabilidade > Alocações > Diários de alocação.
10. Clique em Linhas.
11. Clique em Lançar.
12. Clique em Lançar.


