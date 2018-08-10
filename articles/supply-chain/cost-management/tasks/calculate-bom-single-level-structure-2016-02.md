--- 
title: "Calcular uma BOM usando uma estrutura de um único nível (apenas fevereiro de 2016)"
description: "Este procedimento mostra como calcular o custo de um produto finalizado usando detalhamento de nível único baseado na folha de custos."
author: ShylaThompson
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0e6829238b244cc01b070fde6acdf37bdaeb9670
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="calculate-a-bom-by-using-a-single-level-structure-february-2016-only"></a>Calcular uma BOM usando uma estrutura de um único nível (apenas fevereiro de 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como calcular o custo de um produto finalizado usando detalhamento de nível único baseado na folha de custos. Trata-se da sexta tarefa na série de cálculo BOM. A empresa de dados demo usada para criar esta tarefa é USMF.

1. Vá para Produtos liberados.
2. Na lista, localize e selecione o PDV desejado.
    * Selecione o produto BOM_1.  
3. No Painel de Ação, clique em Gerenciar custos.
4. Clique em Preço de item.
5. Clique em Calcular custo do item.
    * Você pode clicar nas reticências (...) para ver essa opção no menu superior.  
6. No campo Versão do custo, clique no botão suspenso para abrir a pesquisa.
    * Nesta demonstração, selecione 10. Trata-se da mesma versão de custos usada para adicionar o preço de custo aos componentes.  
7. Clique em OK.
8. Clique em Exibir detalhes do cálculo.
    * Você pode clicar nas reticências (...) para ver essa opção no menu superior.    Esta é a composição do custo:  •    10 é derivado do ITEM_A, 10 do ITEM_B, 10 do BOM_2. Neste caso, não há detalhes para BOM_2 porque ele foi inserido como um custo padrão de 10, mas isso não foi feito por meio de cálculo.  •  7 é derivado do tempo de preparação, que é um custo constante, e o 7 adicional é derivado da operação de tempo de execução (Processo).  •   Também há outros valores que correspondem a custos indiretos.  
9. @SysTaskRecorder:_RequestClose


