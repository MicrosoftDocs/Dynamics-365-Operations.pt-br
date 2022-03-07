---
title: Atualizar status de kanban
description: Quando um kanban é esvaziado por engano ou um kanban recebido precisa ser esvaziado, você precisa atualizar o status dele.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Kanban, KanbanResetEmpty
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3fd19febe38d5d0a201d5a50bc57ddb541e12051
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7574344"
---
# <a name="update-kanban-status"></a>Atualizar status de kanban

[!include [banner](../../includes/banner.md)]

Quando um kanban é esvaziado por engano ou um kanban recebido precisa ser esvaziado, você precisa atualizar o status dele. A empresa de dados demo usada para criar este procedimento é USMF. Esse procedimento é criado para o supervisor de loja.


## <a name="find-the-kanban"></a>Encontre o kanban.
1. Acesse Controle de produção > Kanban > Kanbans.
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]