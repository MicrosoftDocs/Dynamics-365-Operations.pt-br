---
title: Contratos de garantia
description: Este tópico explica contratos de garantia no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e9cbb9068101f3004179f338da18af0369190807
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215369"
---
# <a name="warranty-agreements"></a><span data-ttu-id="bd720-103">Contratos de garantia</span><span class="sxs-lookup"><span data-stu-id="bd720-103">Warranty agreements</span></span>

[!include [banner](../../includes/banner.md)]

 


<span data-ttu-id="bd720-104">No Gerenciamento de Ativos, você pode definir termo de garantia que podem ser conectadas um ativo ou a um tipo de ativo.</span><span class="sxs-lookup"><span data-stu-id="bd720-104">In Asset Management, you can set up warranty terms that can be connected to an asset or an asset type.</span></span> <span data-ttu-id="bd720-105">Os termos de garantia são criados para um período específico.</span><span class="sxs-lookup"><span data-stu-id="bd720-105">Warranty terms are created for a specific period.</span></span> <span data-ttu-id="bd720-106">A garantia pode ser configurada para fornecer cobertura total ou parcial, e você pode configurar os termos que são relacionados a horas, despesas e itens.</span><span class="sxs-lookup"><span data-stu-id="bd720-106">Warranty can be set up to provide full coverage or partial coverage, and you can set up terms that are related to hours, expenses, and items.</span></span>

<span data-ttu-id="bd720-107">A primeira etapa é criar quaisquer contratos de garantia de fornecedor que tiver para o equipamento.</span><span class="sxs-lookup"><span data-stu-id="bd720-107">The first step is to create any vendor warranty agreements that you have for your equipment.</span></span> <span data-ttu-id="bd720-108">Em seguida, anexe os contratos de garantia para ativos ou tipos de ativos.</span><span class="sxs-lookup"><span data-stu-id="bd720-108">You then attach warranty agreements to assets or asset types.</span></span> <span data-ttu-id="bd720-109">Contratos de garantia de fornecedor são usados somente para fins informativos.</span><span class="sxs-lookup"><span data-stu-id="bd720-109">Vendor warranty agreements are used only for informational purposes.</span></span> <span data-ttu-id="bd720-110">A garantia do fornecedor é configurada em um ativo, você pode ver o período de cobertura da garantia no ativo.</span><span class="sxs-lookup"><span data-stu-id="bd720-110">If vendor warranty is set up on an asset, you can see the warranty coverage period on the asset.</span></span>

## <a name="create-a-warranty-agreement"></a><span data-ttu-id="bd720-111">Criar um contrato de garantia</span><span class="sxs-lookup"><span data-stu-id="bd720-111">Create a warranty agreement</span></span>

<span data-ttu-id="bd720-112">Um contrato da garantia pode incluir diversas linhas de contrato para cobrir a garantia de horas de trabalho, despesas e itens.</span><span class="sxs-lookup"><span data-stu-id="bd720-112">A warranty agreement can include several agreement lines to cover the warranty for work hours, expenses, and items.</span></span>

1. <span data-ttu-id="bd720-113">Selecione **Gerenciamento de ativos** \> **Configuração** \> **Ativos** \> **Garantia**.</span><span class="sxs-lookup"><span data-stu-id="bd720-113">Select **Asset management** \> **Setup** \> **Assets** \> **Warranty**.</span></span>
2. <span data-ttu-id="bd720-114">Selecione **Nova** para criar um produto.</span><span class="sxs-lookup"><span data-stu-id="bd720-114">Select **New** to create a product.</span></span>
3. <span data-ttu-id="bd720-115">No campo **Garantia**, insira um ID de garantia.</span><span class="sxs-lookup"><span data-stu-id="bd720-115">In the **Warranty** field, enter a warranty ID.</span></span>
4. <span data-ttu-id="bd720-116">No campo **Nome**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="bd720-116">In the **Name** field, enter a description.</span></span>

    <span data-ttu-id="bd720-117">Na Guia Rápida **Detalhes**, o campo **Ativos** exibe o número de ativos válidos que usam o contrato de garantia.</span><span class="sxs-lookup"><span data-stu-id="bd720-117">On the **Details** FastTab, the **Assets** field shows the number of active assets that use the warranty agreement.</span></span>

5. <span data-ttu-id="bd720-118">Nas Guias Rápidas **Garantia de hora** e **Garantia de item**, siga estas etapas para adicionar linhas que devem ser incluídas em um contrato de garantia que pertence a horas ou itens:</span><span class="sxs-lookup"><span data-stu-id="bd720-118">On the **Hour warranty** and **Item warranty** FastTabs, follow these steps to add lines that should be included in a warranty agreement that pertains to hours or items:</span></span>

    1. <span data-ttu-id="bd720-119">Selecione **Adicionar linha** para adicionar uma nova condição à garantia.</span><span class="sxs-lookup"><span data-stu-id="bd720-119">Select **Add line** to add a new condition to the warranty.</span></span> <span data-ttu-id="bd720-120">Um número de linha sequencial é inserido automaticamente no campo **Linha**.</span><span class="sxs-lookup"><span data-stu-id="bd720-120">A sequential line number is automatically entered in the **Line** field.</span></span>
    2. <span data-ttu-id="bd720-121">No campo **Período**, selecione o tipo de período de garantia.</span><span class="sxs-lookup"><span data-stu-id="bd720-121">In the **Period** field, select the type of warranty period.</span></span>
    3. <span data-ttu-id="bd720-122">No campo **Intervalo**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="bd720-122">In the **Interval** field, enter a number.</span></span> <span data-ttu-id="bd720-123">Este campo define o número de períodos para o qual a garantia deve ser válida.</span><span class="sxs-lookup"><span data-stu-id="bd720-123">This field defines the number of periods that the warranty should be valid for.</span></span>
    4. <span data-ttu-id="bd720-124">No campo **Porcentagem**, insira a porcentagem de cobertura para a linha de garantia.</span><span class="sxs-lookup"><span data-stu-id="bd720-124">In the **Percent** field, enter the coverage percentage for the warranty line.</span></span> <span data-ttu-id="bd720-125">O percentual indica quanto é coberto por sua empresa.</span><span class="sxs-lookup"><span data-stu-id="bd720-125">The percentage indicates how much is covered by your company.</span></span>

![Página de garantia](media/01-warranty.png)
