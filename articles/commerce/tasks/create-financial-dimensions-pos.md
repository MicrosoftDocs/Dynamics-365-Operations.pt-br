---
title: Criar dimensões financeiras para registros de PDV e configurar valores de dimensão em registros
description: Este procedimento mostra a criação de dimensões financeiras para registros de (POS) do ponto de venda e demonstra como configurar valores de dimensão financeira nos registros.
author: jashanno
manager: AnnBe
ms.date: 11/14/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7be50eba098b7b28594c8e18c721579f4bb2e879
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140982"
---
# <a name="create-financial-dimensions-for-pos-registers-and-configure-dimension-values-on-registers"></a><span data-ttu-id="e3274-103">Criar dimensões financeiras para registros de PDV e configurar valores de dimensão em registros</span><span class="sxs-lookup"><span data-stu-id="e3274-103">Create financial dimensions for POS registers and configure dimension values on registers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e3274-104">Este procedimento mostra a criação de dimensões financeiras para registros de (POS) do ponto de venda e demonstra como configurar valores de dimensão financeira nos registros.</span><span class="sxs-lookup"><span data-stu-id="e3274-104">This procedure walks through creating financial dimensions for point of sale (POS) registers, and demonstrates how to configure financial dimension values on registers.</span></span> <span data-ttu-id="e3274-105">Este procedimento não inclui outras etapas relacionadas, como a criação de conjuntos de dimensões e de estruturas de conta.</span><span class="sxs-lookup"><span data-stu-id="e3274-105">This procedure doesn't include other related steps, such as creating dimension sets and account structures.</span></span> <span data-ttu-id="e3274-106">Essas tarefas podem ser encontradas em outros tópicos.</span><span class="sxs-lookup"><span data-stu-id="e3274-106">Those tasks can be found in other topics.</span></span> <span data-ttu-id="e3274-107">Este registro usa a empresa de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="e3274-107">This recording uses USRT demo company.</span></span>

1. <span data-ttu-id="e3274-108">Vá para Contabilidade > Plano de contas > Dimensões > Dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="e3274-108">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="e3274-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="e3274-109">Click New.</span></span>
3. <span data-ttu-id="e3274-110">No campo Usar valores de, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="e3274-110">In the Use values from field, select an option.</span></span>
4. <span data-ttu-id="e3274-111">No campo Nome da dimensão, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e3274-111">In the Dimension name field, type a value.</span></span>
5. <span data-ttu-id="e3274-112">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="e3274-112">Click Activate.</span></span>
6. <span data-ttu-id="e3274-113">Clique em Fechar.</span><span class="sxs-lookup"><span data-stu-id="e3274-113">Click Close.</span></span>
7. <span data-ttu-id="e3274-114">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="e3274-114">Click Activate.</span></span>
8. <span data-ttu-id="e3274-115">Clique em Valores de dimensão.</span><span class="sxs-lookup"><span data-stu-id="e3274-115">Click Dimension values.</span></span>
9. <span data-ttu-id="e3274-116">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e3274-116">Close the page.</span></span>
10. <span data-ttu-id="e3274-117">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="e3274-117">Click Save.</span></span>
11. <span data-ttu-id="e3274-118">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e3274-118">Close the page.</span></span>
12. <span data-ttu-id="e3274-119">Vá para Varejo e Comércio > Configuração de canal > Configuração do PDV > Terminais.</span><span class="sxs-lookup"><span data-stu-id="e3274-119">Go to Retail and Commerce > Channel setup > POS setup > Registers.</span></span>
13. <span data-ttu-id="e3274-120">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="e3274-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="e3274-121">Ative a expansão da seção Dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="e3274-121">Toggle the expansion of the Financial dimensions section.</span></span>
15. <span data-ttu-id="e3274-122">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="e3274-122">Click Edit.</span></span>
16. <span data-ttu-id="e3274-123">No campo Terminal, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e3274-123">In the Terminal field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="e3274-124">Na lista, localize e selecione o valor de dimensão para o registro que está sendo atualizado.</span><span class="sxs-lookup"><span data-stu-id="e3274-124">In the list, find and select the dimension value for the register being updated.</span></span>
18. <span data-ttu-id="e3274-125">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="e3274-125">Click Save.</span></span>
