---
title: Calcular uma BOM usando uma estrutura de nível único (Fevereiro de 2016)
description: Este procedimento mostra como calcular o custo de um produto finalizado usando detalhamento de nível único baseado na folha de custos.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 36f908e02c996c0d0a636fd9295b84fcc16b6b63
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011763"
---
# <a name="calculate-a-bom-by-using-a-single-level-structure-february-2016"></a>Calcular uma BOM usando uma estrutura de nível único (Fevereiro de 2016)

[!include [banner](../../includes/banner.md)]

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
    * Você pode clicar nas reticências (...) para ver essa opção no menu superior.    Esta é a composição do custo:  *    10 é derivado do ITEM_A, 10 do ITEM_B, 10 do BOM_2. Neste caso, não há detalhes para BOM_2 porque ele foi inserido como um custo padrão de 10, mas isso não foi feito por meio de cálculo.  *    7 é derivado do tempo de preparação, que é um custo constante, e o 7 adicional é derivado da operação de tempo de execução (Processo).  *    Também há outros valores que correspondem a custos indiretos.  
9. @SysTaskRecorder:_RequestClose

