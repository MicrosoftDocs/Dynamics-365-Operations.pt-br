---
title: ​Contagem de etiquetas do estoque​
description: Este tópico fornece informações sobre a contagem de etiquetas, que pode você usa para comparar o conteúdo real de um depósito com o estoque disponível.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCountTag
audience: Application User
ms.reviewer: kamaybac
ms.custom: 11594
ms.assetid: 03772d0e-5c37-454c-ab85-82bc8b60a76d
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 78402840ad86a0f43d30b3c80307b4646fffbaeb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5216120"
---
# <a name="inventory-tag-counting"></a><span data-ttu-id="39168-103">​Contagem de etiquetas do estoque​</span><span class="sxs-lookup"><span data-stu-id="39168-103">Inventory tag counting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="39168-104">Este tópico fornece informações sobre a contagem de etiquetas, que pode você usa para comparar o conteúdo real de um depósito com o estoque disponível.</span><span class="sxs-lookup"><span data-stu-id="39168-104">This topic provides information about tag counting, which you use to compare the actual contents of a warehouse with the on-hand inventory.</span></span>

<span data-ttu-id="39168-105">Ao criar linhas na página **Contagem de etiquetas**, você coloca um número de etiqueta em cada item de estoque, como um número de 1 a 500.</span><span class="sxs-lookup"><span data-stu-id="39168-105">By creating lines on the **Tag counting** page, you place a tag number on each inventory item, such as a number from 1 to 500.</span></span> <span data-ttu-id="39168-106">Durante a contagem, você digita o número e a quantidade do item na respectiva etiqueta.</span><span class="sxs-lookup"><span data-stu-id="39168-106">During the count, you enter the item number and the quantity on a corresponding tag.</span></span> <span data-ttu-id="39168-107">Esta etiqueta pode ser usada como base para entrada no diário de contagem de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="39168-107">This tag can then be used as the basis for input in the tag counting journal.</span></span> <span data-ttu-id="39168-108">Após você lançar o diário de contagem de etiquetas, um novo diário de contagem é criado na página **Contagem**.</span><span class="sxs-lookup"><span data-stu-id="39168-108">After you post the tag counting journal, a new counting journal is created on the **Counting** page.</span></span> <span data-ttu-id="39168-109">O novo diário se baseia nas linhas do diário de contagem de etiquetas que você criou.</span><span class="sxs-lookup"><span data-stu-id="39168-109">The new journal is based on the tag counting journal lines that you created.</span></span> <span data-ttu-id="39168-110">Para contar as etiquetas de itens por uma dimensão de estoque específica, selecione a dimensão na página **Dimensão de exibição** exibida quando você cria o diário de contagem de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="39168-110">To tag-count items by a specific inventory dimension, select the dimension on the **Display dimension** page that is displayed when you create the tag counting journal.</span></span> <span data-ttu-id="39168-111">Por exemplo, para contar itens em um depósito específico, marque a caixa de seleção **Depósito**.</span><span class="sxs-lookup"><span data-stu-id="39168-111">For example, to count items in a specific warehouse, select the **Warehouse** check box.</span></span> <span data-ttu-id="39168-112">Se o controle deslizante **Bloquear itens durante a contagem** na página **Parâmetros de gerenciamento de depósito e estoque** estiver selecionado, os itens não poderão ser atualizados fisicamente durante a contagem.</span><span class="sxs-lookup"><span data-stu-id="39168-112">If the **Lock items during count** slider on the **Inventory and warehouse management parameters** page is selected, items can't be physically updated during counting.</span></span> <span data-ttu-id="39168-113">No entanto, os itens em diários de contagem de etiquetas não são bloqueados durante a contagem.</span><span class="sxs-lookup"><span data-stu-id="39168-113">However, items in tag counting journals aren't locked during counting.</span></span> <span data-ttu-id="39168-114">As transações de estoque não são criadas até que as linhas de contagem sejam lançadas e transferidas para um diário de contagem.</span><span class="sxs-lookup"><span data-stu-id="39168-114">Inventory transactions aren't created until the tag counting lines are posted and transferred to a counting journal.</span></span> <span data-ttu-id="39168-115">Se as etiquetas forem inseridas aleatoriamente e você quiser identificar etiquetas ausentes, clique no cabeçalho da coluna **Etiqueta** para classificar as linhas por etiqueta.</span><span class="sxs-lookup"><span data-stu-id="39168-115">If tags are entered randomly, and you want to identify missing tags, click the **Tag** column header to sort the lines by tag.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="39168-116">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="39168-116">Additional resources</span></span>

[<span data-ttu-id="39168-117">Contagem cíclica</span><span class="sxs-lookup"><span data-stu-id="39168-117">Cycle counting</span></span>](../warehousing/cycle-counting.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]