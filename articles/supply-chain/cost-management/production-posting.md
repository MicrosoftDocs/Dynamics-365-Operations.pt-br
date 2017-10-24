---
title: "Lançamento de produção"
description: "Este artigo fornece informações sobre tipos diferentes de lançamento no processo de produção."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventItemGroup, ProjCategory, WrkCtrResourceGroup, WrkCtrTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 54591
ms.assetid: 0917fe64-f643-46ae-98ff-5013b266a067
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f965fd7fc4386665befedd89f33c6d32401c9132
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="production-posting"></a>Lançamento de produção

[!include[banner](../includes/banner.md)]


Este artigo fornece informações sobre tipos diferentes de lançamento no processo de produção.

As atividades de lançamento de produção acompanham os processos de produção descritos nas seções a seguir.

## <a name="material-consumption"></a>Consumo de materiais
Os materiais são registradas como consumidos durante a produção quando o diário de listas de separação de produção é lançado. Esse processo gera transações de saída que deduzem do estoque disponível. Nos parâmetros de produção, você pode especificar se os valores de matérias-prima que estão em andamento (trabalho em andamento \[WIP\]) devem ser lançados no razão. O valor de matérias-prima que estão em andamento (WIP) é lançado então em uma conta de Lista de separação dedicada e em uma contrapartida de Lita de separação dedicada.

## <a name="time-consumption"></a>Consumo de tempo
O tempo que os trabalhadores passam em trabalhos de produção são registrados no diário Cartão de roteiro ou no diário Ficha de trabalho. Quando esses diários são lançados, o lançamento contábil para uma conta dedicada para recursos que estão em andamento (WIP) é processado. Esse lançamento representa o valor do tempo gasto na ordem de produção. Depois que a ordem de produção é registrada como concluída, as contas WIP são liquidadas.

## <a name="reporting-finished-goods-and-error-quantities"></a>Relatar mercadorias concluídas e quantidades de erro
Quando uma ordem de produção é relatada como concluída, a quantidade de mercadorias concluídas é atualizada no Gerenciamento de estoque por meio do diário Relatar como concluído. Se você estiver usando a contabilidade WIP, que pode ser configurada nos parâmetros de produção, um diário do razão é criado para reduzir as contas WIP e aumentar o estoque das mercadorias concluídas. O diário usa o custo padrão definido para o produto.

## <a name="ending-the-production-order"></a>Terminar a ordem de produção
Antes de encerrar uma ordem de produção, os custos reais serão calculados para a quantidade que foi produzida. Todos os custos previstos de material, mão-de-obra e custos gerais indiretos são revertidos e substituídos por custos reais. O custo geral do item finalizado será debitado da conta Recebimento do estoque e creditado na conta Saídas do estoque. Se você marcar a caixa de seleção **Trabalho final** ao executar o cálculo de custos, o status da ordem de produção mudará para **Concluído**. Esse status evita que custos adicionais sejam lançados acidentalmente em uma ordem de produção concluída. Você pode especificar que o valor das quantidades de erro relatados durante o relatório concluído devem ser alocados com as quantidades de mercadoria relatadas como concluídas. Como alternativa, você pode especificar que o valor das quantidades de erros deve ser lançado em uma conta de sucata dedicada.

## <a name="controlling-the-level-of-ledger-posting"></a>Controle do nível de lançamento contábil
Em **Parâmetros de controle de produção**, você pode usar o campo **Lançamento contábil** para definir o nível de lançamento contábil para processos de produção. Os valores a seguir estão disponíveis:

-   **Item e recurso** – use as contas contábeis configuradas nos grupos de itens para matérias-primas e mercadorias concluídas. O WIP para o consumo de tempo é obtido do recurso ou do grupo de recursos das operações de roteiro.
-   **Item e categoria** – use as contas contábeis configuradas nos grupos de itens para matérias-primas e mercadorias concluídas. O WIP para o consumo de tempo é obtido das categorias de custo associadas às operações de roteiro.
-   **Grupos de produção** – use as contas contábeis configuradas nos grupos de produção para o consumo de materiais e de tempo. Os grupos de produção estão associados aos produtos liberados e copiados para as ordens de produção quando as ordens são criadas. O lançamento nas ordens de produção seguirão os grupos de produção associados à ordem de produção.

**Observação:** se o método padrão para calcular o custo do item finalizado tiver sido utilizado, as transações finais também refletirão esse fato. Se os custos reais e os custos calculados utilizando o método padrão forem diferentes, essa diferença será lançada na conta que mostra lucros ou perdas.




