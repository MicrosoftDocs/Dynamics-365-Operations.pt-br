---
title: Criar configurações baseadas em dimensão
description: Este procedimento mostra como definir uma configuração para um produto baseado na dimensão.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, EcoResDimensionBasedConfiguration, ConfigChooseFromRoute, ConfigChooseFromGroup, ConfigChoiceApprove
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 584bb558ee0afeaffaeb003e9f1d1b0bca42d19d
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920672"
---
# <a name="create-dimension-based-configurations"></a><span data-ttu-id="afea0-103">Criar configurações baseadas em dimensão</span><span class="sxs-lookup"><span data-stu-id="afea0-103">Create dimension-based configurations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="afea0-104">Este procedimento mostra como definir uma configuração para um produto baseado na dimensão.</span><span class="sxs-lookup"><span data-stu-id="afea0-104">This procedure shows how to define a configuration for a dimension-based product.</span></span> <span data-ttu-id="afea0-105">Este é o último procedimento da série que explica como criar combinações para configuração baseada em dimensão.</span><span class="sxs-lookup"><span data-stu-id="afea0-105">This is the last procedure in the series that explains how to build combinations for dimension-based configuration.</span></span> <span data-ttu-id="afea0-106">A execução desse procedimento depende dos dados criados nos sete registros anteriores.</span><span class="sxs-lookup"><span data-stu-id="afea0-106">The execution of this procedure is dependent on the data created in the previous seven recordings.</span></span> <span data-ttu-id="afea0-107">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="afea0-107">The demo data company used to create this procedure is USMF.</span></span>

## <a name="find-the-dimension-based-product-master"></a><span data-ttu-id="afea0-108">Encontre o produto mestre baseado na dimensão</span><span class="sxs-lookup"><span data-stu-id="afea0-108">Find the dimension-based product master</span></span>

1. <span data-ttu-id="afea0-109">Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="afea0-109">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="afea0-110">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="afea0-110">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="afea0-111">Selecione o produto mestre baseado na dimensão que você criou no primeiro registro nesta sequência de 8 registros.</span><span class="sxs-lookup"><span data-stu-id="afea0-111">Select the dimension-based product master that you created in the first recording in this sequence of 8 recordings.</span></span>  

## <a name="create-configurations"></a><span data-ttu-id="afea0-112">Criar configurações</span><span class="sxs-lookup"><span data-stu-id="afea0-112">Create configurations</span></span>

1. <span data-ttu-id="afea0-113">No Painel de Ação **Engenharia**, selecione **Manter configurações**.</span><span class="sxs-lookup"><span data-stu-id="afea0-113">On the **Engineering** Action Pane, select **Maintain configurations**.</span></span>
1. <span data-ttu-id="afea0-114">Selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="afea0-114">Select **Configure**.</span></span>
1. <span data-ttu-id="afea0-115">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="afea0-115">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="afea0-116">No campo **Número do item**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="afea0-116">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="afea0-117">Selecione um dos itens no grupo de configuração.</span><span class="sxs-lookup"><span data-stu-id="afea0-117">Select any of the items in the first configuration group.</span></span>  
1. <span data-ttu-id="afea0-118">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="afea0-118">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="afea0-119">No campo **Número do item**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="afea0-119">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="afea0-120">Selecione qualquer item do segundo grupo de configuração.</span><span class="sxs-lookup"><span data-stu-id="afea0-120">Select any item from the second configuration group.</span></span>  
1. <span data-ttu-id="afea0-121">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="afea0-121">Select **OK**.</span></span>
1. <span data-ttu-id="afea0-122">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="afea0-122">In the list, mark the selected row.</span></span>
1. <span data-ttu-id="afea0-123">No campo **Configuração**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="afea0-123">In the **Configuration** field, type a value.</span></span>
    * <span data-ttu-id="afea0-124">Insira um nome de configuração que seja de fácil identificação da configuração.</span><span class="sxs-lookup"><span data-stu-id="afea0-124">Enter a configuration name that will make it easy to identify the configuration.</span></span>  
1. <span data-ttu-id="afea0-125">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="afea0-125">In the **Description** field, type a value.</span></span>
    * <span data-ttu-id="afea0-126">Insira uma descrição da configuração para explicar o que ela contém.</span><span class="sxs-lookup"><span data-stu-id="afea0-126">Enter a description of the configuration to explain what it contains.</span></span>  
1. <span data-ttu-id="afea0-127">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="afea0-127">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]