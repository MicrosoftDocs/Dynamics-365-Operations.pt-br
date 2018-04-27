--- 
title: Atualizar status de kanban
description: "Quando um kanban é esvaziado por engano ou um kanban recebido precisa ser esvaziado, você precisa atualizar o status dele."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3c2b5a5fbfc5bd83cc68ffafaa243dac9244c003
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="update-kanban-status"></a>Atualizar status de kanban

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Quando um kanban é esvaziado por engano ou um kanban recebido precisa ser esvaziado, você precisa atualizar o status dele. A empresa de dados demo usada para criar este procedimento é USMF. Esse procedimento é criado para o supervisor de loja.


## <a name="find-the-kanban"></a>Encontre o kanban.
1. Vá para Controle de produção > Kanban > Kanbans.
2. Abra o filtro na coluna do status da unidade de manuseio.
3. Clicar em Limpar.
    * Isso redefine os filtros.  
4. Use o Filtro Rápido para localizar registros. Por exemplo, filtre no campo Número do cartão com um valor de '000149'.

## <a name="change-emptied-status-to-received-status"></a>Alterar status de esvaziado para recebido
1. Clique em Reverter unidade de manuseio de material vazia.
2. Clique em OK.
    * Observe que o status da unidade de manuseio é Recebido.  

## <a name="change-received-status-to-emptied-status"></a>Alterar status de recebido para esvaziado
1. Clique em Kanban vazio.
2. Na lista, marque a linha selecionada.
    * Observe que o status da unidade de manuseio é esvaziado.  


