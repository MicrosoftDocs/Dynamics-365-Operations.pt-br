--- 
title: "Criar uma configuração de mapeamento de modelo (ER)"
description: "Use este procedimento para criar uma nova configuração de mapeamento de modelo de Relatório eletrônico (ER) e usar funções de ER internas para obter cálculos agregados eficientes."
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 74606b1378e94e8a6945a408520c8b68648970d8
ms.openlocfilehash: f7206126bfa6150078f1bfb4f7e07c1cf2819ce0
ms.contentlocale: pt-br
ms.lasthandoff: 02/07/2018

---
# <a name="create-a-model-mapping-configuration-er"></a><span data-ttu-id="15d16-103">Criar uma configuração de mapeamento de modelo (ER)</span><span class="sxs-lookup"><span data-stu-id="15d16-103">Create a model mapping configuration (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="15d16-104">Use este procedimento para criar uma nova configuração de mapeamento de modelo de Relatório eletrônico (ER) e usar funções de ER internas para obter cálculos agregados eficientes.</span><span class="sxs-lookup"><span data-stu-id="15d16-104">Use this procedure to design a new Electronic reporting (ER) model mapping configuration and use built-in ER functions for efficient aggregate calculations.</span></span> <span data-ttu-id="15d16-105">Neste procedimento, você criará uma configuração para a empresa de exemplo, Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="15d16-105">In this procedure, you will create a configuration for sample company, Litware, Inc.</span></span> 

<span data-ttu-id="15d16-106">Este procedimento é criado para usuários com a função atribuída de Administrador do sistema ou Desenvolvedor de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="15d16-106">This procedure is created for uses with the assigned role of System administrator or Electronic reporting developer.</span></span>

<span data-ttu-id="15d16-107">Estas etapas podem ser concluídas usando qualquer conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="15d16-107">These steps can be completed using any dataset.</span></span> <span data-ttu-id="15d16-108">Para concluir essas etapas, você deve primeiro concluir as etapas do procedimento “Criar um provedor de configuração e marcá-lo como ativo“.</span><span class="sxs-lookup"><span data-stu-id="15d16-108">To complete these steps, you must first complete the steps in the procedure, “Create a configuration provider and mark it as active.”</span></span>

1. <span data-ttu-id="15d16-109">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="15d16-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="15d16-110">Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como Ativo.</span><span class="sxs-lookup"><span data-stu-id="15d16-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="15d16-111">Se não visualizar esse provedor de configuração, conclua as etapas do procedimento “Criar um provedor de configuração e marcá-lo como ativo“.</span><span class="sxs-lookup"><span data-stu-id="15d16-111">If you don’t see this configuration provider, complete the steps in the procedure, “Create a configuration provider and mark it as active”.</span></span>  
2. <span data-ttu-id="15d16-112">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="15d16-112">Click Reporting configurations.</span></span>
3. <span data-ttu-id="15d16-113">Clique em Mostrar filtros.</span><span class="sxs-lookup"><span data-stu-id="15d16-113">Click Show filters.</span></span>
4. <span data-ttu-id="15d16-114">No campo "Nome", digite o valor de filtro "Intrastat" e use o operador de filtro "começa com".</span><span class="sxs-lookup"><span data-stu-id="15d16-114">In the "Name" field, enter the filter value, "Intrastat" and use the filter operator "begins with".</span></span>
    * <span data-ttu-id="15d16-115">Aplique este filtro para localizar a configuração do modelo de dados 'intrastat'.</span><span class="sxs-lookup"><span data-stu-id="15d16-115">Apply this filter to find the ‘Intrastat’ data model configuration.</span></span> <span data-ttu-id="15d16-116">Esse modelo pode já existir na árvore de configurações.</span><span class="sxs-lookup"><span data-stu-id="15d16-116">This model may already exist in the configurations tree.</span></span> <span data-ttu-id="15d16-117">Se existir, ignore a subtarefa a seguir.</span><span class="sxs-lookup"><span data-stu-id="15d16-117">If it does, skip the next sub-task.</span></span>   

## <a name="get-the-intrastat-model-configuration-provided-by-microsoft"></a><span data-ttu-id="15d16-118">Obter a configuração de modelo intrastat fornecida pela Microsoft</span><span class="sxs-lookup"><span data-stu-id="15d16-118">Get the Intrastat model configuration provided by Microsoft</span></span>
1. <span data-ttu-id="15d16-119">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="15d16-119">Close the page.</span></span>
2. <span data-ttu-id="15d16-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="15d16-120">Close the page.</span></span>
3. <span data-ttu-id="15d16-121">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="15d16-121">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
4. <span data-ttu-id="15d16-122">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="15d16-122">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="15d16-123">Selecione o bloco do provedor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="15d16-123">Select the Microsoft provider tile.</span></span>  
5. <span data-ttu-id="15d16-124">Clique em Repositórios.</span><span class="sxs-lookup"><span data-stu-id="15d16-124">Click Repositories.</span></span>
    * <span data-ttu-id="15d16-125">Clique em Repositórios no bloco do provedor Microsoft.</span><span class="sxs-lookup"><span data-stu-id="15d16-125">Click Repositories in the Microsoft provider tile.</span></span>  
6. <span data-ttu-id="15d16-126">Clique em Mostrar filtros.</span><span class="sxs-lookup"><span data-stu-id="15d16-126">Click Show filters.</span></span>
7. <span data-ttu-id="15d16-127">No campo "Nome do tipo", digite o valor de filtro "recursos" e use o operador de filtro "contém".</span><span class="sxs-lookup"><span data-stu-id="15d16-127">In the "Type name" field, enter the filter value, “resources” and use the filter operator "contains".</span></span> 
8. <span data-ttu-id="15d16-128">Clique em Abrir.</span><span class="sxs-lookup"><span data-stu-id="15d16-128">Click Open.</span></span>
9. <span data-ttu-id="15d16-129">Na árvore, selecione 'Modelo intrastat'.</span><span class="sxs-lookup"><span data-stu-id="15d16-129">In the tree, select 'Intrastat model'.</span></span>
10. <span data-ttu-id="15d16-130">Clique em Importar.</span><span class="sxs-lookup"><span data-stu-id="15d16-130">Click Import.</span></span>
11. <span data-ttu-id="15d16-131">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="15d16-131">Click Yes.</span></span>
    * <span data-ttu-id="15d16-132">Você importou a configuração de modelo de ER que contém o modelo de dados que usará para explorar como a nova funcionalidade de ER pode ser usada.</span><span class="sxs-lookup"><span data-stu-id="15d16-132">You imported the ER model configuration that contains the data model that you will use to explore how the new ER functionality can be used.</span></span>  
12. <span data-ttu-id="15d16-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="15d16-133">Close the page.</span></span>
13. <span data-ttu-id="15d16-134">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="15d16-134">Close the page.</span></span>
14. <span data-ttu-id="15d16-135">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="15d16-135">Click Reporting configurations.</span></span>

## <a name="add-a-new-model-mapping-configuration"></a><span data-ttu-id="15d16-136">Adicionar uma nova configuração de mapeamento de modelo</span><span class="sxs-lookup"><span data-stu-id="15d16-136">Add a new model mapping configuration</span></span>
1. <span data-ttu-id="15d16-137">Na árvore, selecione 'Modelo intrastat'.</span><span class="sxs-lookup"><span data-stu-id="15d16-137">In the tree, select 'Intrastat model'.</span></span>
2. <span data-ttu-id="15d16-138">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="15d16-138">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="15d16-139">No campo Novo, digite 'Mapeamento de modelo baseado no modelo de dados intrastat'.</span><span class="sxs-lookup"><span data-stu-id="15d16-139">In the New field, enter 'Model Mapping based on data model Intrastat'.</span></span>
4. <span data-ttu-id="15d16-140">No campo Nome, digite 'Mapeamento de amostra de intrastat'.</span><span class="sxs-lookup"><span data-stu-id="15d16-140">In the Name field, type 'Intrastat sample mapping'.</span></span>
    * <span data-ttu-id="15d16-141">Mapeamento de amostra de intrastat</span><span class="sxs-lookup"><span data-stu-id="15d16-141">Intrastat sample mapping</span></span>  
5. <span data-ttu-id="15d16-142">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="15d16-142">Click Create configuration.</span></span>


