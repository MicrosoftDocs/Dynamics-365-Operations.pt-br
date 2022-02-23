---
title: Calcular uma BOM usando uma estrutura de vários níveis (Fevereiro de 2016)
description: Este procedimento mostra como calcular o custo de um produto finalizado usando detalhamento de vários níveis baseado na folha de custos.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog, BOMCalcTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0f0ec28a20d32fc38cd6e77a76a02fc9544db3ca
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422262"
---
# <a name="calculate-a-bom-by-using-a-multilevel-structure-february-2016"></a>Calcular uma BOM usando uma estrutura de vários níveis (Fevereiro de 2016)

[!include [banner](../../includes/banner.md)]

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

