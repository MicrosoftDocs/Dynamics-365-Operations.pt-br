---
title: Criar uma ordem de venda para um produto configurável
description: Esse procedimento aborda a aplicação de um modelo de configuração a um produto em uma ordem de venda.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 882198bf07233867b54579b986f93f5c1b46c1b6
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564192"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a><span data-ttu-id="8be1a-103">Criar uma ordem de venda para um produto configurável</span><span class="sxs-lookup"><span data-stu-id="8be1a-103">Create a sales order for a configurable product</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8be1a-104">Esse procedimento aborda a aplicação de um modelo de configuração a um produto em uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="8be1a-104">This procedure shows how to apply a configuration template to a product on a sales order.</span></span> <span data-ttu-id="8be1a-105">Este exemplo usa o modelo do Palestrante D0006 na empresa de dados demo USMF.</span><span class="sxs-lookup"><span data-stu-id="8be1a-105">This example uses the D0006 speaker model in the USMF demo data company.</span></span> <span data-ttu-id="8be1a-106">Normalmente, um processador de ordens de venda usa este procedimento.</span><span class="sxs-lookup"><span data-stu-id="8be1a-106">Typically, a sales order processor uses this procedure.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="8be1a-107">Criar uma ordem de venda</span><span class="sxs-lookup"><span data-stu-id="8be1a-107">Create a sales order</span></span>
1. <span data-ttu-id="8be1a-108">Clique em Consulta e processamento de ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="8be1a-108">Click Sales order processing and inquiry.</span></span>
2. <span data-ttu-id="8be1a-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="8be1a-109">Click New.</span></span>
3. <span data-ttu-id="8be1a-110">Clique Ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="8be1a-110">Click Sales order.</span></span>
4. <span data-ttu-id="8be1a-111">No campo da conta Cliente, selecione US-001.</span><span class="sxs-lookup"><span data-stu-id="8be1a-111">In the Customer account field, select US-001.</span></span> 
5. <span data-ttu-id="8be1a-112">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8be1a-112">Click OK.</span></span>
6. <span data-ttu-id="8be1a-113">No campo Número do item, selecione D0006.</span><span class="sxs-lookup"><span data-stu-id="8be1a-113">In the Item number field, select D0006.</span></span>
    * <span data-ttu-id="8be1a-114">Para essa tarefa, você deve selecionar um produto configurável.</span><span class="sxs-lookup"><span data-stu-id="8be1a-114">For this task, you must select a configurable product.</span></span>  
7. <span data-ttu-id="8be1a-115">Clique em Produtos e fornecimento.</span><span class="sxs-lookup"><span data-stu-id="8be1a-115">Click Product and supply.</span></span>
8. <span data-ttu-id="8be1a-116">Clique em Configurar linha.</span><span class="sxs-lookup"><span data-stu-id="8be1a-116">Click Configure line.</span></span>
    * <span data-ttu-id="8be1a-117">Observe que o preço foi alterado, com base na configuração selecionada, e ela inclui o campo de cabo agora definido como Verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="8be1a-117">Note that the price has changed, based on the configuration that was selected, and that the Include cable field is now set to True.</span></span>  
    * <span data-ttu-id="8be1a-118">Anote o preço padrão e as configurações que estão selecionadas para o período.</span><span class="sxs-lookup"><span data-stu-id="8be1a-118">Note the default price and the settings that are selected for the cable.</span></span>  
9. <span data-ttu-id="8be1a-119">Clique em Carregar modelo.</span><span class="sxs-lookup"><span data-stu-id="8be1a-119">Click Load template.</span></span>
    * <span data-ttu-id="8be1a-120">Esse exemplo mostra como é possível aplicar um modelo para selecionar uma configuração predefinida.</span><span class="sxs-lookup"><span data-stu-id="8be1a-120">This example shows how you can apply a template to select a predefined configuration.</span></span> <span data-ttu-id="8be1a-121">Se você estiver usando este procedimento como um guia de tarefas e deseja consultar outros valores de atributo que estão disponíveis, clique no botão Desbloquear.</span><span class="sxs-lookup"><span data-stu-id="8be1a-121">If you’re using this procedure as a task guide and want to see the other attribute values that are available, you must click the Unlock button.</span></span>  
10. <span data-ttu-id="8be1a-122">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8be1a-122">Click OK.</span></span>
11. <span data-ttu-id="8be1a-123">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8be1a-123">Click OK.</span></span>
12. <span data-ttu-id="8be1a-124">Expanda a seção Detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="8be1a-124">Expand the Line details section.</span></span>
13. <span data-ttu-id="8be1a-125">Clique na guia de Produto.</span><span class="sxs-lookup"><span data-stu-id="8be1a-125">Click the Product tab.</span></span>
    * <span data-ttu-id="8be1a-126">A configuração do item está listada agora nas dimensões do produto.</span><span class="sxs-lookup"><span data-stu-id="8be1a-126">The configuration of the item is now listed under the product dimensions.</span></span>  
14. <span data-ttu-id="8be1a-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8be1a-127">Close the page.</span></span>

## <a name="select-the-product-configuration"></a><span data-ttu-id="8be1a-128">Selecione a configuração do produto</span><span class="sxs-lookup"><span data-stu-id="8be1a-128">Select the product configuration</span></span>

