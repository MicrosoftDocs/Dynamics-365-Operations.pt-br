--- 
title: "Calcular uma BOM usando uma estrutura de vários níveis (apenas fevereiro de 2016)"
description: "Este procedimento mostra como calcular o custo de um produto finalizado usando detalhamento de vários níveis baseado na folha de custos."
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
ms.openlocfilehash: 16c2cacaf70df5455c3ed49b8dcb5756e89f8cb8
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="calculate-a-bom-by-using-a-multilevel-structure-february-2016-only"></a>Calcular uma BOM usando uma estrutura de vários níveis (apenas fevereiro de 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como calcular o custo de um produto finalizado usando detalhamento de vários níveis baseado na folha de custos. Trata-se da sétima tarefa na série de cálculo BOM. A empresa de dados demo usada para criar esta tarefa é USMF.

1. Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.
2. Na lista, localize e selecione o PDV desejado.
    * Selecione o produto BOM_1.  
3. No Painel de Ação, clique em Gerenciar custos.
4. Clique em Preço de item.
5. Clique em Calcular custo do item.
    * Você pode clicar nas reticências (...) para ver essa opção no menu superior.  
6. No campo Versão do custo, insira ou selecione um valor.
    * Selecione Versão do custo 20, porque é um tipo Custo planejado e o Modo de detalhamento tem vários níveis.   O modo de detalhamento de vários níveis destina-se a custos planejados e simulações. Não é usado para custo padrão.  
7. Clique em OK.
8. Clique em Exibir detalhes do cálculo.
    * Você pode clicar nas reticências (...) para ver essa opção no menu superior.  Nesse caso, observe como o BOM_2 foi calculado levando em consideração a matéria-prima, o processo e os custos gerais indiretos com um total de 29,40 em vez do custo padrão de 10 que foi ativado na guia de tarefas inicial nesta série.  
9. Clique na guia Folha de custos.
    * Seguindo para a guia Folha de custos, os totais por grupo de custos são diferentes em comparação ao cálculo feito na guia de tarefas anterior.  
10. No campo Nível, selecione "Vários".
    * Ao selecionar Vários, os custos são classificados de acordo com a composição de BOM_2, na qual 10 é derivado do grupo de custos M1 (ITEM_C) e 15,60 é derivado de sua fabricação na qual o grupo de custos é L2. Os custos indiretos também variam.  
11. Feche a página.
12. Feche a página.


