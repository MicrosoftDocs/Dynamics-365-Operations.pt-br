--- 
title: " Criar dimensões financeiras para registros de PDV e configurar valores de dimensão em registros"
description: "Este procedimento mostra a criação de dimensões financeiras para registros de (POS) do ponto de venda e demonstra como configurar valores de dimensão financeira nos registros."
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d9b080ff46a0fbc73ed4f8fa3f03d71e9d758cc2
ms.openlocfilehash: d2dd2b2dfac44dc343a4b13738c68ccbb27b9e16
ms.contentlocale: pt-br
ms.lasthandoff: 01/17/2018

---
# <a name="create-financial-dimensions-for-pos-registers-and-configure-dimension-values-on-registers"></a><span data-ttu-id="5e92e-103"> Criar dimensões financeiras para registros de PDV e configurar valores de dimensão em registros</span><span class="sxs-lookup"><span data-stu-id="5e92e-103">Create financial dimensions for POS registers and configure dimension values on registers</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="5e92e-104">Este procedimento mostra a criação de dimensões financeiras para registros de (POS) do ponto de venda e demonstra como configurar valores de dimensão financeira nos registros.</span><span class="sxs-lookup"><span data-stu-id="5e92e-104">This procedure walks through creating financial dimensions for point of sale (POS) registers, and demonstrates how to configure financial dimension values on registers.</span></span> <span data-ttu-id="5e92e-105">Este procedimento não inclui outras etapas relacionadas, como a criação de conjuntos de dimensões e de estruturas de conta.</span><span class="sxs-lookup"><span data-stu-id="5e92e-105">This procedure doesn’t include other related steps, such as creating dimension sets and account structures.</span></span> <span data-ttu-id="5e92e-106">Essas tarefas podem ser encontradas em outros tópicos.</span><span class="sxs-lookup"><span data-stu-id="5e92e-106">Those tasks can be found in other topics.</span></span> <span data-ttu-id="5e92e-107">Este registro usa a empresa de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="5e92e-107">This recording uses USRT demo company.</span></span>

1. <span data-ttu-id="5e92e-108">Vá para Contabilidade > Plano de contas > Dimensões > Dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="5e92e-108">Go to General ledger > Chart of accounts > Dimensions > Financial dimensions.</span></span>
2. <span data-ttu-id="5e92e-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5e92e-109">Click New.</span></span>
3. <span data-ttu-id="5e92e-110">No campo Usar valores de, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="5e92e-110">In the Use values from field, select an option.</span></span>
4. <span data-ttu-id="5e92e-111">No campo Nome da dimensão, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="5e92e-111">In the Dimension name field, type a value.</span></span>
5. <span data-ttu-id="5e92e-112">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="5e92e-112">Click Activate.</span></span>
6. <span data-ttu-id="5e92e-113">Clique em Fechar.</span><span class="sxs-lookup"><span data-stu-id="5e92e-113">Click Close.</span></span>
7. <span data-ttu-id="5e92e-114">Clique em Ativar.</span><span class="sxs-lookup"><span data-stu-id="5e92e-114">Click Activate.</span></span>
8. <span data-ttu-id="5e92e-115">Clique em Valores de dimensão.</span><span class="sxs-lookup"><span data-stu-id="5e92e-115">Click Dimension values.</span></span>
9. <span data-ttu-id="5e92e-116">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="5e92e-116">Close the page.</span></span>
10. <span data-ttu-id="5e92e-117">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5e92e-117">Click Save.</span></span>
11. <span data-ttu-id="5e92e-118">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="5e92e-118">Close the page.</span></span>
12. <span data-ttu-id="5e92e-119">Vá para Varejo e comércio > Configuração do canal > Configuração do PDV > Registros.</span><span class="sxs-lookup"><span data-stu-id="5e92e-119">Go to Retail and commerce > Channel setup > POS setup > Registers.</span></span>
13. <span data-ttu-id="5e92e-120">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="5e92e-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="5e92e-121">Ative a expansão da seção Dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="5e92e-121">Toggle the expansion of the Financial dimensions section.</span></span>
15. <span data-ttu-id="5e92e-122">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="5e92e-122">Click Edit.</span></span>
16. <span data-ttu-id="5e92e-123">No campo Terminal, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="5e92e-123">In the Terminal field, click the drop-down button to open the lookup.</span></span>
17. <span data-ttu-id="5e92e-124">Na lista, localize e selecione o valor de dimensão para o registro que está sendo atualizado.</span><span class="sxs-lookup"><span data-stu-id="5e92e-124">In the list, find and select the dimension value for the register being updated.</span></span>
18. <span data-ttu-id="5e92e-125">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5e92e-125">Click Save.</span></span>


