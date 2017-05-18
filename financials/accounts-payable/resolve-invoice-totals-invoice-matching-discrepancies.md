---
title: "Resolver discrepâncias durante a conciliação de totais de faturas"
description: 
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 63413
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: c947f84e6510073d49045f93af703c16d0ebc1ba
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="resolve-discrepancies-during-invoice-totals-matching"></a>Resolver discrepâncias durante a conciliação de totais de faturas

[!include[banner](../includes/banner.md)]




Um tipo de validação de conciliação de faturas é a conciliação de totais de faturas. Para especificar que o sistema deve executar a conciliação de totais de faturas, na página **Parâmetros de contas a pagar**, na guia **Validação de fatura**, defina a opção **Conciliar totais de fatura** como **Sim**. 

Você pode usar a conciliação de totais de fatura para ajudar a garantir que os valores totais de fatura não desviem dos valores esperados por mais de uma variação aceitável. Seis totais são comparados na página **Detalhes de conciliação de totais de fatura**. Se um dos totais se desviar do total de ordem de compra correspondente esperado, uma discrepância de conciliação será sinalizada. 

Para revisar a fatura que contém os totais de discrepâncias correspondentes, no espaço de trabalho **Entrada de fatura de fornecedor**, clique no bloco **Faturas pendentes**. Depois, no Painel de Ação, na guia **Revisão**, clique em **Detalhes da conciliação**. Se as discrepâncias de conciliação foram detectadas, os ícones de aviso aparecerão ao lado do valor da fatura. Você pode ver mais detalhes sobre os totais exibindo os detalhes da conciliação de totais da fatura. 

Após identificar uma discrepância, talvez você precise contatar o fornecedor se achar que as informações na fatura estão incorretas. Dependendo do contrato resultante com o fornecedor, execute uma destas ações:

-   Aceitar a diferença de preço e lançar a fatura com discrepâncias de conciliação. O sistema pode ser configurado para exigir aprovação antes de lançar se há discrepâncias de conciliação. Nesse caso, você deve aprovar a discrepância da conciliação e pode inserir um comentário de aprovação. Você pode optar por lançar a fatura.
-   Revisar o valor da fatura para o valor esperado e lançar a fatura.
-   Solicitar um crédito completo de uma nova fatura corrigida do fornecedor.





