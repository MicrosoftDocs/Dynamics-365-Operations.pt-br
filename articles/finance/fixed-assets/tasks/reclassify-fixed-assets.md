---
title: Reclassificar ativos fixos
description: Para reclassificar um ativo fixo, você deve transferi-lo para um novo grupo de ativos fixos ou atribuir a ele um novo número de ativo fixo no mesmo grupo.
author: saraschi2
manager: AnnBe
ms.date: 05/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 47d8cf2ff1e275df0466a7fe327a3180c0399e49
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186914"
---
# <a name="reclassify-fixed-assets"></a>Reclassificar ativos fixos

[!include [task guide banner](../../includes/task-guide-banner.md)]

Para reclassificar um ativo fixo, você deve transferi-lo para um novo grupo de ativos fixos ou atribuir a ele um novo número de ativo fixo no mesmo grupo. 

Quando um ativo fixo é reclassificado:

• Todos os livros do ativo fixo existente são criados para o novo ativo fixo. Todas as informações configuradas para o ativo fixo original são copiadas para o novo ativo fixo. O status dos livros para o ativo fixo original é Fechado. 

• Os novos livros do novo ativo fixo contêm a data da reclassificação no campo **Data de aquisição**. A data indicada no campo **Data de execução da depreciação** é copiada das informações originais de ativo. Caso a depreciação já tenha sido iniciada, o campo **Data da última depreciação exibirá** a data da reclassificação. 

• As transações de ativo fixo existentes para o ativo fixo original são canceladas e geradas novamente para o novo ativo fixo.

Siga essa etapas para reclassificar um ativo fixo:

1. Vá para **Ativos fixos > Tarefas periódicas > Reclassificação**.
2. No campo **Grupo de ativos fixos**, selecione o grupo a ser reclassificado.
3. No campo **Número do ativo fixo**, selecione o ativo fixo a ser reclassificado.
4. No campo **Novo grupo de ativos fixos**, selecione um grupo para o qual deseja transferir o ativo fixo.
    * Se o novo grupo de ativos fixos estiver associado a uma sequência numérica, o campo **Número do novo ativo fixo** será atualizado com o número da nova sequência numérica do grupo de ativos fixos. Caso contrário, o campo **Número do novo ativo fixo** será atualizado com o número da sequência numérica que está configurada na página **Parâmetros do ativo fixo**. Se uma sequência numérica não estiver configurada na página **Parâmetros do ativo fixo**, insira um número no campo **Número do novo ativo fixo**.  
5. No campo **Data de reclassificação**, insira uma data.
6. No campo **Série de comprovante**, insira ou selecione um valor.
7. Clique em **OK**.
