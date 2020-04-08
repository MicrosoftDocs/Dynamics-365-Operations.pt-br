---
title: Relatar uma ordem de produção como concluída
description: Este procedimento mostra como relatar uma ordem de produção como concluída.
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmReportFinished, ProdJournalTransProd
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 78ba9a876edc9948d19180bcea9e68f15b72fec6
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148874"
---
# <a name="report-a-production-order-as-finished"></a>Relatar uma ordem de produção como concluída

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como relatar uma ordem de produção como concluída. A empresa de dados demo usada para criar este procedimento é USMF. Este é o sexto procedimento de sete que explica o ciclo de vida da ordem de produção.


## <a name="report-a-production-order-as-finished"></a>Relatar uma ordem de produção como concluída
1. Vá para Controle de produção > Ordens de produção > Todas as ordens de produção.
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

