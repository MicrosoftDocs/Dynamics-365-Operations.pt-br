---
title: Lançar em diário entradas de diário
description: Este procedimento aborda como lançar em diário entradas de diário postadas.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cbf7ee8063487303cd4c8d2b76a8b44bacc86193
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846382"
---
# <a name="journalize-posted-journal-entries"></a>Lançar em diário entradas de diário

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

