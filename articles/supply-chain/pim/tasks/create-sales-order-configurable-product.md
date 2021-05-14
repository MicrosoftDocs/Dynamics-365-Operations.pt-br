---
title: Criar uma ordem de venda para um produto configurável
description: Esse procedimento aborda a aplicação de um modelo de configuração a um produto em uma ordem de venda.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8607de5705354aa58c985fb536f3e1d52acd1f37
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921280"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a><span data-ttu-id="8c4fb-103">Criar uma ordem de venda para um produto configurável</span><span class="sxs-lookup"><span data-stu-id="8c4fb-103">Create a sales order for a configurable product</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8c4fb-104">Esse procedimento aborda a aplicação de um modelo de configuração a um produto em uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="8c4fb-104">This procedure shows how to apply a configuration template to a product on a sales order.</span></span> <span data-ttu-id="8c4fb-105">Este exemplo usa o modelo do Palestrante D0006 na empresa de dados demo USMF.</span><span class="sxs-lookup"><span data-stu-id="8c4fb-105">This example uses the D0006 speaker model in the USMF demo data company.</span></span> <span data-ttu-id="8c4fb-106">Normalmente, um processador de ordens de venda usa este procedimento.</span><span class="sxs-lookup"><span data-stu-id="8c4fb-106">Typically, a sales order processor uses this procedure.</span></span>

## <a name="create-a-sales-order"></a><span data-ttu-id="8c4fb-107">Criar uma ordem de venda</span><span class="sxs-lookup"><span data-stu-id="8c4fb-107">Create a sales order</span></span>

1. <span data-ttu-id="8c4fb-108">Vá para **Vendas e marketing \> Espaços de trabalho \> Consulta e processamento de ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="8c4fb-108">Go to **Sales and marketing \> Workspaces \> Sales order processing and inquiry**.</span></span>
1. <span data-ttu-id="8c4fb-109">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8c4fb-109">Select **New**.</span></span>
1. <span data-ttu-id="8c4fb-110">Selecione **Ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="8c4fb-110">Select **Sales order**.</span></span>
1. <span data-ttu-id="8c4fb-111">No campo **Conta do cliente**, selecione *US-001*.</span><span class="sxs-lookup"><span data-stu-id="8c4fb-111">In the **Customer account** field, select *US-001*.</span></span> 
1. <span data-ttu-id="8c4fb-112">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c4fb-112">Select **OK**.</span></span>
1. <span data-ttu-id="8c4fb-113">No campo **Número de item**, selecione *D0006*.</span><span class="sxs-lookup"><span data-stu-id="8c4fb-113">In the **Item number** field, select *D0006*.</span></span>
    * <span data-ttu-id="8c4fb-114">Para essa tarefa, você deve selecionar um produto configurável.</span><span class="sxs-lookup"><span data-stu-id="8c4fb-114">For this task, you must select a configurable product.</span></span>  
1. <span data-ttu-id="8c4fb-115">Selecione **Produto e fornecimento**.</span><span class="sxs-lookup"><span data-stu-id="8c4fb-115">Select **Product and supply**.</span></span>
1. <span data-ttu-id="8c4fb-116">Selecione **Configurar linha**.</span><span class="sxs-lookup"><span data-stu-id="8c4fb-116">Select **Configure line**.</span></span>
    * <span data-ttu-id="8c4fb-117">Observe que o preço foi alterado, com base na configuração selecionada, e que o campo **Incluir cabo** agora foi configurado como *Verdadeiro*.</span><span class="sxs-lookup"><span data-stu-id="8c4fb-117">Note that the price has changed, based on the configuration that was selected, and that the **Include cable** field is now set to *True*.</span></span>  
    * <span data-ttu-id="8c4fb-118">Anote o preço padrão e as configurações que estão selecionadas para o período.</span><span class="sxs-lookup"><span data-stu-id="8c4fb-118">Note the default price and the settings that are selected for the cable.</span></span>  
1. <span data-ttu-id="8c4fb-119">Selecione **Carregar modelo**.</span><span class="sxs-lookup"><span data-stu-id="8c4fb-119">Select **Load template**.</span></span>
    * <span data-ttu-id="8c4fb-120">Esse exemplo mostra como é possível aplicar um modelo para selecionar uma configuração predefinida.</span><span class="sxs-lookup"><span data-stu-id="8c4fb-120">This example shows how you can apply a template to select a predefined configuration.</span></span> <span data-ttu-id="8c4fb-121">Se você estiver usando este procedimento como um guia de tarefas e deseja consultar outros valores de atributo que estão disponíveis, selecione o botão **Desbloquear**.</span><span class="sxs-lookup"><span data-stu-id="8c4fb-121">If you're using this procedure as a task guide and want to see the other attribute values that are available, you must select the **Unlock** button.</span></span>  
1. <span data-ttu-id="8c4fb-122">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c4fb-122">Select **OK**.</span></span>
1. <span data-ttu-id="8c4fb-123">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c4fb-123">Select **OK**.</span></span>
1. <span data-ttu-id="8c4fb-124">Expanda a seção **Detalhes da linha**.</span><span class="sxs-lookup"><span data-stu-id="8c4fb-124">Expand the **Line details** section.</span></span>
1. <span data-ttu-id="8c4fb-125">Selecione a guia **Produto**.</span><span class="sxs-lookup"><span data-stu-id="8c4fb-125">Select the **Product** tab.</span></span>
    * <span data-ttu-id="8c4fb-126">A configuração do item está listada agora nas dimensões do produto.</span><span class="sxs-lookup"><span data-stu-id="8c4fb-126">The configuration of the item is now listed under the product dimensions.</span></span>  
1. <span data-ttu-id="8c4fb-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8c4fb-127">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]