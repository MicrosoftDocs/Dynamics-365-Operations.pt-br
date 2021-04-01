---
title: Item onde é usado
description: Este tópico explica como obter uma visão geral de onde o item é usado no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetItemWhereUsed, EntAssetItemWhereUsedCalculate
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ef020c6a917f0a2c358f775991182e1e494d45d6
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253749"
---
# <a name="item-where-used"></a><span data-ttu-id="8792b-103">Item onde é usado</span><span class="sxs-lookup"><span data-stu-id="8792b-103">Item where used</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="8792b-104">Você pode criar um cálculo para que um item específico obtenha uma visão geral de onde o item foi usado no Gerenciamento de Ativos.</span><span class="sxs-lookup"><span data-stu-id="8792b-104">You can make a calculation for a specific item to get an overview of where in Asset Management the item has been used.</span></span> <span data-ttu-id="8792b-105">Os resultados mostram o contexto no qual o item foi usado durante seu tempo de vida.</span><span class="sxs-lookup"><span data-stu-id="8792b-105">The results show the context in which the item has been used during its lifetime.</span></span> <span data-ttu-id="8792b-106">A página **Item onde usado** pode ser aberta do menu principal do Gerenciamento de Ativos e também pode ser acessada das seguintes páginas:</span><span class="sxs-lookup"><span data-stu-id="8792b-106">The **Item where used** page can be opened from the main Asset Management menu, and it can also be accessed from the following pages:</span></span>

- [<span data-ttu-id="8792b-107">BOMs de Ativos</span><span class="sxs-lookup"><span data-stu-id="8792b-107">Asset BOMs</span></span>](../objects/object-BOM.md)

- [<span data-ttu-id="8792b-108">Peças sobressalentes nos padrões do tipo de ativo</span><span class="sxs-lookup"><span data-stu-id="8792b-108">Spare parts on asset type defaults</span></span>](../setup-for-objects/object-types.md#spare-parts-on-the-asset-type-setup)

- [<span data-ttu-id="8792b-109">Categorias do tipo de trabalho e tipos de trabalho de manutenção, grades do tipo de trabalho de manutenção, comércios de trabalho de manutenção e listas de verificação de manutenção</span><span class="sxs-lookup"><span data-stu-id="8792b-109">Maintenance job type categories and maintenance job types, maintenance job type variants, maintenance job trades, and maintenance checklists</span></span>](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md)

- [<span data-ttu-id="8792b-110">Previsão de manutenção</span><span class="sxs-lookup"><span data-stu-id="8792b-110">Maintenance forecast</span></span>](../work-orders/maintenance-forecasts.md)

- [<span data-ttu-id="8792b-111">Compras</span><span class="sxs-lookup"><span data-stu-id="8792b-111">Procurement</span></span>](../work-orders/procurement.md)

- [<span data-ttu-id="8792b-112">Compra da ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="8792b-112">Work order purchase</span></span>](../work-orders/procurement.md)

## <a name="make-an-item-where-used-calculation"></a><span data-ttu-id="8792b-113">Criar um cálculo de item onde usado</span><span class="sxs-lookup"><span data-stu-id="8792b-113">Make an item-where-used calculation</span></span>

1. <span data-ttu-id="8792b-114">Clique em **Gerenciamento de ativos** > **Consultas** > **Item onde usado** ou selecione o botão **Item onde usado** em uma das páginas mencionadas acima.</span><span class="sxs-lookup"><span data-stu-id="8792b-114">Click **Asset management** > **Inquiries** > **Item where used**, or select the **Item where used** button on one of the pages mentioned above.</span></span>

2. <span data-ttu-id="8792b-115">Na caixa de diálogo **Item onde usado**, selecione o item para o qual você deseja fazer o cálculo no campo **Número do item**.</span><span class="sxs-lookup"><span data-stu-id="8792b-115">In the **Item where used** dialog, select the item for which you want to make the calculation in the **Item number** field.</span></span>

3. <span data-ttu-id="8792b-116">Você pode usar o campo **Nível** para indicar o nível de detalhamento desejado das linhas de item em relação aos locais funcionais.</span><span class="sxs-lookup"><span data-stu-id="8792b-116">You can use the **Level** field to indicate how detailed you want the item lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="8792b-117">Por exemplo, se você inserir o número “1 "no campo e tiver uma estrutura de local funcional com vários níveis, todas as linhas do item de um local funcional serão mostrados em nível superior.</span><span class="sxs-lookup"><span data-stu-id="8792b-117">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all item lines for a functional location will be shown on the top level.</span></span> <span data-ttu-id="8792b-118">Portanto, relação/quantidade em uma linha podem ser adicionado de locais funcionais localizados em nível inferior.</span><span class="sxs-lookup"><span data-stu-id="8792b-118">Therefore, relation/quantity on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="8792b-119">Se você inserir o número "0" no campo **Nível**, verá um resultado detalhado mostrando todas as linhas de item em todos os níveis do local funcional ao qual elas estão relacionadas.</span><span class="sxs-lookup"><span data-stu-id="8792b-119">If you insert the number "0" in the **Level** field, you will see a detailed result showing all item lines on all the functional location levels to which they are related.</span></span>

4. <span data-ttu-id="8792b-120">Na seção **Incluir**, selecione "Sim" nos botões de alternância que você deseja incluir no cálculo.</span><span class="sxs-lookup"><span data-stu-id="8792b-120">In the **Include** section, select "Yes" on the toggle buttons that you want to include in the calculation.</span></span>

5. <span data-ttu-id="8792b-121">Clique em **OK** para iniciar o cálculo.</span><span class="sxs-lookup"><span data-stu-id="8792b-121">Click **OK** to start the calculation.</span></span>

6. <span data-ttu-id="8792b-122">Na guia **Item onde usado**, selecione os botões **Agrupar por** para mostrar o nível de detalhe necessário do cálculo.</span><span class="sxs-lookup"><span data-stu-id="8792b-122">On the **Item where used** tab, select the **Group by** buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="8792b-123">Os botões selecionados de **Agrupar por** são realçados.</span><span class="sxs-lookup"><span data-stu-id="8792b-123">The selected **Group by** buttons are highlighted.</span></span> <span data-ttu-id="8792b-124">Clique em um botão para ativá-los ou desativá-los.</span><span class="sxs-lookup"><span data-stu-id="8792b-124">Click on a button to activate or deactivate it.</span></span>

7. <span data-ttu-id="8792b-125">Se quiser mostrar as dimensões relacionadas ao item, clique em **Exibir dimensões** e selecione as dimensões a serem mostradas.</span><span class="sxs-lookup"><span data-stu-id="8792b-125">If you want to show dimensions related to the item, click **Display dimensions**, and select the dimensions to be shown.</span></span>

## <a name="example"></a><span data-ttu-id="8792b-126">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8792b-126">Example</span></span>

<span data-ttu-id="8792b-127">Na captura de tela abaixo, você verá um exemplo de um cálculo de item onde usado para o número do item "1000".</span><span class="sxs-lookup"><span data-stu-id="8792b-127">In the screenshot below, you see an example of an item-where-used calculation for item number "1000".</span></span>

![Exemplo de item onde cálculo usado](media/12-controlling-and-reporting.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]