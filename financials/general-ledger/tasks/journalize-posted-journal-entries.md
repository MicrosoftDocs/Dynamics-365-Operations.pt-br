--- 
title: "Lançar em diário entradas de diário"
description: "Este procedimento aborda como lançar em diário entradas de diário postadas."
author: aprilolson
manager: AnnBe
ms.date: 10/24/2016
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
ms.openlocfilehash: 450bb7fdcc866f45c2fd3357a5ee25e6c6f929c1
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="journalize-posted-journal-entries"></a>Lançar em diário entradas de diário

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento aborda como lançar em diário entradas de diário postadas. Este procedimento usa a empresa de dados de demonstração USMF.

1. Valide as configurações para o lançamento em diário em Contabilidade > Configuração do razão > Parâmetros da contabilidade.
2. O campo de diários estendidos de motivo pode ser definido como Sim ou Não. Se Sim, as versões de relatório serão diferentes.
3. Selecione se o período pode ser inserido se o processo se lançando em diário não foi executado.
    * Se esta opção é definida em Sim, o período não poderá ser fechado até o processo se lançando em diário foi preenchido para o período.  
4. Feche a página.
5. Vá para Contabilidade > Tarefas periódicas > Lançamento em diário.
6. Clique em Filtro.
7. Realce a linha com os critérios do filtro que você deseja definir.
8. No campo Critérios, insira ou selecione o critério de filtro.
9. Clique em OK para fechar a página de filtro.
10. Clique em OK para iniciar o processo de colocar em diário.
    * Um relatório será gerado depois que o processo foi concluído.  


