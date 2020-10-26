---
title: Submeter itens devolvidos à inspeção
description: Submeter itens devolvidos à inspeção.
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bdc42f9c5ece8e2c2570cadf623f52648b7b174e
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3985782"
---
# <a name="take-returned-items-through-inspection"></a>Submeter itens devolvidos à inspeção 

[!include [banner](../includes/banner.md)]


1.  Clique em **Gerenciamento de estoque** \> **Periódico** \> **Gerenciamento de qualidade** \> **Ordens de quarentena**.

2.  Localize a linha da ordem que corresponde ao item devolvido que está sendo inspecionado.

    > [!NOTE]
    > <P>Uma ordem de quarentena pode ser associada apenas a um único número de item. Se 10 itens com números de item diferentes forem devolvidos em uma única remessa e enviados para quarentena, 10 ordens de quarentena separadas serão criadas.</P>

3.  Depois de examinar o item, faça uma seleção no campo **Código de disposição** para indicar o que deve ser feito com o item e como tratar a transação financeira relacionada. Exemplos incluem devolver item ao estoque e o reembolsar o cliente, transformar o item em sucata e enviar uma substituição para o cliente, ou devolver o item ao cliente sem crédito.
    
    > [!NOTE]
    > <P>Se vários itens devolvidos em um único lote de número de itens não puderem receber o mesmo código de disposição, você deverá dividir a ordem de quarentena (<STRONG>Funções</STRONG> &gt; <STRONG>Dividir</STRONG>) para atribuir um código de disposição diferente para cada sub-lote.</P>


4.  Quando tiver terminado a inspeção, clique em **Relatório de conclusão** para liberar os itens devolvidos e criar uma entrada no diário de entrada de itens. A pessoa ou o departamento que receber os itens processará o diário para os itens a serem devolvidos para o estoque.
    
    –ou–
    
    Termine a ordem de quarentena e mova os itens diretamente para o estoque usando uma das funções de **Estoque**.

5.  Feche o formulário para salvar suas alterações.

## <a name="see-also"></a>Consulte também

[Especificar o destino dos itens devolvidos](specify-how-to-dispose-of-returned-items.md)

  


