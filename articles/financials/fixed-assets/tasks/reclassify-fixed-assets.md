--- 
title: Reclassificar ativos fixos
description: "Para reclassificar um ativo fixo, você deve transferi-lo para um novo grupo de ativos fixos ou atribuir a ele um novo número de ativo fixo no mesmo grupo."
author: saraschi2
manager: AnnBe
ms.date: 10/30/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: cafd499e849570cae7b7f58bf2d487a7ac0093e6
ms.openlocfilehash: 6bce294329c7ec6dc436c3d3baf6597e0283c9bd
ms.contentlocale: pt-br
ms.lasthandoff: 10/30/2017

---
# <a name="reclassify-fixed-assets"></a>Reclassificar ativos fixos

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Para reclassificar um ativo fixo, você deve transferi-lo para um novo grupo de ativos fixos ou atribuir a ele um novo número de ativo fixo no mesmo grupo. 

Quando um ativo fixo é reclassificado:

• Todos os métodos de depreciação do ativo fixo existente são criados para o novo ativo fixo. Todas as informações configuradas para o ativo fixo original são copiadas para o novo ativo fixo. O status dos métodos de depreciação para o ativo fixo original é Fechado. 

• Os novos modelos de valor do novo ativo fixo contêm a data da reclassificação no campo Data de aquisição. A data indicada no campo Data de execução da depreciação é copiada das informações originais de ativo. Caso a depreciação já tenha sido iniciada, o campo Data da última depreciação exibirá a data da reclassificação. 

• As transações de ativo fixo existentes para o ativo fixo original são canceladas e geradas novamente para o novo ativo fixo.

1. Vá para Ativos fixos > Tarefas periódicas > Reclassificação.
2. No campo Grupo de ativos fixos, selecione o grupo a ser reclassificado.
3. No campo Número do ativo fixo, selecione o ativo fixo a ser reclassificado.
4. No campo Novo grupo de ativos fixos, selecione um grupo para o qual deseja transferir o ativo fixo.
    * Se o novo grupo de ativos fixos estiver associado a uma sequência numérica, o campo Número do novo ativo fixo será atualizado com o número da nova sequência numérica do grupo de ativos fixos. Caso contrário, o campo Número do novo ativo fixo será atualizado com o número da sequência numérica que está configurada na página Parâmetros do ativo fixo. Se uma sequência numérica não estiver configurada na página Parâmetros do ativo fixo, insira um número no campo Número do novo ativo fixo.  
5. No campo Data de reclassificação, insira uma data.
6. No campo Série de comprovante, insira ou selecione um valor.
7. Clique em OK.


