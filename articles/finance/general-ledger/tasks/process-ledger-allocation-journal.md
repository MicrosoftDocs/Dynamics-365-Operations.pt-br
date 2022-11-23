---
title: Processar diário de alocação do razão
description: Este artigo explica como processar uma solicitação de alocação no Dynamics 365 Finance.
author: aprilolson
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1f22b5042e0e3726afcb1061852fdbd8de770c61
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779383"
---
# <a name="process-ledger-allocation-journal"></a>Processar diário de alocação do razão

[!include [banner](../../includes/banner.md)]

Este artigo explica como processar uma solicitação de alocação. Use a página **Processar solicitação de alocação** para criar um diário de alocação que possa ser revisto e aprovado antes do lançamento na Contabilidade ou que possa ser lançado diretamente na Contabilidade. Antes de criar um diário de alocações, deve haver pelo menos uma regra de alocação do razão ativa. Esta tarefa usa a empresa de demonstração USMF.

1. No painel de navegação, Acesse **Contabilidade > Alocações > Processar solicitação de alocação**.
2. No campo **Regra**, selecione o registro desejado no menu suspenso.
3. No campo **A partir da data**, insira uma data.

    - O campo **A partir da data** é muito importante quando o razão é a fonte de dados para a regra. Essa data controla quais saldos do razão serão incluídos na alocação.  
    - No campo **Fonte zero**, selecione **Parar**. Isso interromperá o processo de alocação e exibirá uma mensagem informando que um valor de origem zero foi selecionado.  

4. No campo **Opções de proposta**, selecione **Somente proposta**. Selecione **Somente proposta** para revisar e opcionalmente aprovar o resultado em **Diários de alocação** antes de lançar a alocação na Contabilidade.  
5. No campo **Data do lançamento GL**, insira uma data.
6. Selecione **OK**.
7. No painel de navegação, Acesse **Módulos > Contabilidade > Alocações > Diários de alocação**.
8. Selecione **Linhas**.
9. Selecione **Lançar**.
10. Selecione **Lançar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
