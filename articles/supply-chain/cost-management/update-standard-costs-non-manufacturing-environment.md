---
title: "Atualizar custos padrão em um ambiente que não seja de manufatura"
description: "Este artigo oferece diretrizes para a atualização de custos padrão em um ambiente que não seja de fabricação."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 79723
ms.assetid: 7ba0c408-2450-4042-9542-6fdf83c12e6c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0386ca1e5e7bf6e578ba2abf1b2c9eefe4dd2a02
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="update-standard-costs-in-a-non-manufacturing-environment"></a><span data-ttu-id="2b5dd-103">Atualizar custos padrão em um ambiente que não seja de manufatura</span><span class="sxs-lookup"><span data-stu-id="2b5dd-103">Update standard costs in a non-manufacturing environment</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="2b5dd-104">Este artigo oferece diretrizes para a atualização de custos padrão em um ambiente que não seja de fabricação.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-104">This article provides guidance for updating standard costs in a non-manufacturing environment.</span></span>

<span data-ttu-id="2b5dd-105">As diretrizes a seguir pressupõem o uso de uma abordagem de duas versões para atualizar o custo padrão.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-105">The following guidelines assume that you use a two-version approach to update standard cost.</span></span> <span data-ttu-id="2b5dd-106">Nesta abordagem, uma versão de avaliação de custo contém os custos padrão definidos originalmente para o período de congelamento, e a segunda versão de avaliação de custo contém as atualizações incrementais.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-106">In this approach, one costing version contains the standard costs that were originally defined for the frozen period, and the second costing version contains the incremental updates.</span></span> <span data-ttu-id="2b5dd-107">Cada atualização é inserida como um registro de custo que é incluído na segunda versão de avaliação de custo, e ocasionalmente ela é habilitada.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-107">Each update is entered as a cost record that is enclosed in the second costing version, and eventually it's enabled.</span></span> <span data-ttu-id="2b5dd-108">Como alternativa, a abordagem de uma versão usa o conjunto de custos padrão originalmente definido.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-108">An alternative, one-version approach uses the set of standard costs that was originally defined.</span></span> <span data-ttu-id="2b5dd-109">A abordagem de duas versões requer que você defina uma segunda versão de custo.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-109">The two-version approach requires that you define a second costing version.</span></span> <span data-ttu-id="2b5dd-110">Veja as diretrizes para a definição desta versão de avaliação de custo:</span><span class="sxs-lookup"><span data-stu-id="2b5dd-110">Here are the guidelines for defining this costing version:</span></span>

-   <span data-ttu-id="2b5dd-111">Atribua um tipo de avaliação de custo de **Custos padrão**.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-111">Assign a costing type of **Standard costs**.</span></span>
-   <span data-ttu-id="2b5dd-112">Atribua um identificador significativo que indique o conteúdo da versão de avaliação de custo, como **ATUALIZAÇÕES-2016**.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-112">Assign a meaningful identifier that indicates the contents of the costing version, such as **2016-UPDATES**.</span></span>
-   <span data-ttu-id="2b5dd-113">Verifique se o conteúdo inclui registros de custo.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-113">Make sure that the content includes cost records.</span></span>
-   <span data-ttu-id="2b5dd-114">Permita que os registros de custo sejam inseridos para todos os sites.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-114">Allow cost records to be entered for all sites.</span></span> <span data-ttu-id="2b5dd-115">Se você especificar um site, os registros de custo poderão ser inseridos somente para esse site.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-115">If you specify a site, cost records can be entered only for that site.</span></span>
-   <span data-ttu-id="2b5dd-116">Indique o princípio de fallback como **Nenhum**.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-116">Indicate a fallback principle of **None**.</span></span> <span data-ttu-id="2b5dd-117">O princípio de fallback só se aplica a cálculos de custo de itens fabricados.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-117">The fallback principle applies only to cost calculations for manufactured items.</span></span>

<span data-ttu-id="2b5dd-118">Para corrigir, ajustar ou atualizar os custos padrão para novos itens, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-118">To correct, adjust, or update standard costs for new items, follow these steps.</span></span>

1.  <span data-ttu-id="2b5dd-119">Use a página **Configuração da versão** **de avaliação de custo** para habilitar os dados de custo a serem inseridos na segunda versão de avaliação de custo.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-119">Use the **Costing version** **setup** page to enable cost data to be entered into the second costing version.</span></span> <span data-ttu-id="2b5dd-120">Opcionalmente impeça a ativação de custos pendentes, de forma que a ativação seja permitida depois que os custos pendentes tiverem sido definidos com exatidão e por completo.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-120">Optionally, prevent the activation of pending costs, so that activation will be allowed after pending costs have been completely and accurately defined.</span></span> <span data-ttu-id="2b5dd-121">Opcionalmente, você também pode inserir uma data no campo **Data inicial**.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-121">You can also optionally enter a date in the **From date** field.</span></span> <span data-ttu-id="2b5dd-122">Como diretriz geral, use a data quando você planeja habilitar as atualizações incrementais.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-122">As a general guideline, use the date when you intend to enable the incremental updates.</span></span> <span data-ttu-id="2b5dd-123">Como alternativa, deixe o campo **Data inicial** em branco para a versão de avaliação de custos e insira uma data no campo **Data inicial** para cada registro de custo.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-123">Alternatively, leave the **From date** field blank for the costing version, and then enter a date in the **From date** field for each cost record.</span></span>
2.  <span data-ttu-id="2b5dd-124">Use a página **Preço de item** para inserir atualizações como os registros de custo do item que são incluídos na segunda versão de avaliação de custo.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-124">Use the **Item price** page to enter updates as item cost records that are enclosed in the second costing version.</span></span>
3.  <span data-ttu-id="2b5dd-125">Use o relatório **Preços de item** para verificar a integridade e a precisão dos registros de custo de item que são incluídos na segunda versão de custo.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-125">Use the **Item prices** report to verify the completeness and accuracy of the item cost records that are enclosed in the second costing version.</span></span>
4.  <span data-ttu-id="2b5dd-126">Use a página **Manutenção de versão de avaliação de custo** para alterar o sinalizador de bloqueio para permitir a ativação dos registros de custos pendentes incluídos na segunda versão de avaliação de custo.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-126">Use the **Costing version maintenance** page to change the blocking flag to allow activation of the pending cost records that are enclosed in the second costing version.</span></span>
5.  <span data-ttu-id="2b5dd-127">Use a página **Preços ativos** (aberta da página **Manutenção de versão de avaliação de custo**) para ativar todos os registros de custos pendentes incluídos na segunda versão de avaliação de custo.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-127">Use the **Activate prices** page (which you open from the **Costing version maintenance** page) to activate all pending item cost records that are enclosed in the second costing version.</span></span> <span data-ttu-id="2b5dd-128">Você também pode ativar os registros de custo pendente para itens individuais clicando no botão **Ativar preço pendente** na página **Preço de item**.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-128">You can also activate the pending cost records for individual items by clicking the **Activate pending price** button on the **Item price** page.</span></span>
6.  <span data-ttu-id="2b5dd-129">Use a página **Configuração de versão de avaliação de custo** para alterar os sinalizadores de bloqueio incluídos na segunda versão de avaliação de custo para impedir a manutenção adicional de dados.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-129">To prevent additional data maintenance, use the **Costing version setup** page to change the blocking flags that are enclosed in the second costing version.</span></span> <span data-ttu-id="2b5dd-130">As diretivas de bloqueio impedem a entrada de novos custos pendentes e a ativação de custos pendentes.</span><span class="sxs-lookup"><span data-stu-id="2b5dd-130">The blocking policies will prevent the entry of new pending costs and the activation of pending costs.</span></span>





