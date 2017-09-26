--- 
title: "Configurar depreciação extra"
description: "Este procedimento mostra como criar uma provisão para depreciação especial e associá-la a um registro de ativos fixos."
author: saraschi2
manager: AnnBe
ms.date: 10/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 7af954eaae76a327313a80cb3014d837267ccf4d
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-bonus-depreciation"></a>Configurar depreciação extra

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como criar uma provisão para depreciação especial e associá-la a um registro de ativos fixos. Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.


## <a name="create-a-special-depreciation-allowance"></a>Criar uma provisão para depreciação especial
1. Vá para Ativos fixos > Configuração > Provisão para depreciação especial.
2. Clique em Novo.
3. No campo Provisão para depreciação especial, insira um valor.
4. No campo Descrição, digite um valor.
5. No campo Porcentagem, insira um número.
    * Se uma porcentagem não foi indicada, defina um valor.  

## <a name="associate-a-special-depreciation-allowance-with-a-fixed-asset-group-book"></a>Associar uma provisão para depreciação especial a um registro de grupo de ativos fixos
1. Vá para Ativos fixos > Configuração > Grupos de ativo fixo.
2. Na lista, selecione o grupo de ativos fixos a ser associado à provisão para depreciação especial.
3. Clique em Registros.
4. Na lista, selecione o registro associado à provisão para depreciação especial.
5. Clique em Provisão para depreciação especial.
6. Clique em Novo.
7. No campo Provisão para depreciação especial, insira ou selecione um valor.
    * O padrão para a porcentagem ou o valor vem da configuração de provisão para depreciação especial.  
8. No campo Prioridade, insira um número.


