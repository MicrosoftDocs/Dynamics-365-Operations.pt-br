---
title: Relatar uma ordem de produção como concluída
description: Este procedimento mostra como relatar uma ordem de produção como concluída.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmReportFinished, ProdJournalTransProd, ProdSetupReportFinished
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aa27691942b27886e85c52b7b3a736a62db7b7bd
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580591"
---
# <a name="report-a-production-order-as-finished"></a>Relatar uma ordem de produção como concluída

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como relatar uma ordem de produção como concluída. A empresa de dados demo usada para criar este procedimento é USMF. Este é o sexto procedimento de sete que explica o ciclo de vida da ordem de produção.


## <a name="report-a-production-order-as-finished"></a>Relatar uma ordem de produção como concluída
1. Acesse Controle de produção > Ordens de produção > Todas as ordens de produção.
    * Selecione uma ordem de produção com o status Iniciada.  
2. No Painel de Ação, clique em Ordem de produção.
3. Clique em Relatar como concluído.
    * Nesta página, você pode confirmar a quantidade do produto finalizado a ser informada na conclusão.  
4. Clique na guia Geral.
5. Defina Quantidade de bens como '18'.
6. Defina Quantidade de erros como '2'.
7. No campo Causa do erro, selecione 'Material'.
8. Marque ou desmarque a caixa de seleção Trabalho final.
9. Marque ou desmarque a caixa de seleção Aceitar erro.
10. Clique em OK.

## <a name="verify-the-report-as-finished-journal"></a>Verificar o diário Relatório de conclusão
1. No Painel de Ação, clique em Exibir.
2. Clique em Informado como concluído.
3. Na lista, marque a linha selecionada.
4. Na lista, clique no link na linha selecionada.
    * O diário Relatório de conclusão é lançado. Se quiser fazer ajustes no diário, você pode criar manualmente um diário no qual é possível fazer alterações.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]