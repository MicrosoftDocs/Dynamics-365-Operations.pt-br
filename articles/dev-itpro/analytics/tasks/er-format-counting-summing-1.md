--- 
title: "Criar formatos de relatórios eletrônicos para contagem e soma"
description: "As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para fazer a contagem e soma com base nos dados já gerados do texto de saída."
author: NickSelin
manager: AnnBe
ms.date: 11/02/2017
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 7261a2324b61cacfca8d69ad52762aa545b70220
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---
# <a name="create-electronic-reporting-er-formats-to-do-counting-and-summing"></a><span data-ttu-id="eaa7f-103">Criar formatos de relatórios eletrônicos (ER) para contagem e soma</span><span class="sxs-lookup"><span data-stu-id="eaa7f-103">Create Electronic reporting (ER) formats to do counting and summing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="eaa7f-104">As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para fazer a contagem e soma com base nos dados já gerados do texto de saída.</span><span class="sxs-lookup"><span data-stu-id="eaa7f-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="eaa7f-105">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="eaa7f-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="eaa7f-106">Para completar essas etapas, você deve primeiro completar as etapas do procedimento “Criar um provedor de configuração e marcá-lo como ativo“.</span><span class="sxs-lookup"><span data-stu-id="eaa7f-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

<span data-ttu-id="eaa7f-107">Este procedimento é para um recurso que foi adicionado à versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="eaa7f-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="eaa7f-108">Obter acesso à lista de configurações fornecidas pela Microsoft</span><span class="sxs-lookup"><span data-stu-id="eaa7f-108">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="eaa7f-109">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="eaa7f-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="eaa7f-110">Verifique se o provedor "Litware, Inc."</span><span class="sxs-lookup"><span data-stu-id="eaa7f-110">Make sure that the “Litware, Inc.”</span></span> <span data-ttu-id="eaa7f-111">está disponível e marcado como ativo.</span><span class="sxs-lookup"><span data-stu-id="eaa7f-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="eaa7f-112">Selecione o provedor</span><span class="sxs-lookup"><span data-stu-id="eaa7f-112">Select the “Litware, Inc.”</span></span> <span data-ttu-id="eaa7f-113">"Litware, Inc.".</span><span class="sxs-lookup"><span data-stu-id="eaa7f-113">provider.</span></span>
3. <span data-ttu-id="eaa7f-114">Clique em Repositórios.</span><span class="sxs-lookup"><span data-stu-id="eaa7f-114">Click Repositories.</span></span>
    * <span data-ttu-id="eaa7f-115">Se um repositório do tipo "Recursos de operações" já existir, ignore as etapas restantes da subtarefa atual.</span><span class="sxs-lookup"><span data-stu-id="eaa7f-115">If a repository of the "Operations resources" type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="eaa7f-116">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="eaa7f-116">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="eaa7f-117">No campo Tipo de repositório de configuração, insira 'Recursos de operações'.</span><span class="sxs-lookup"><span data-stu-id="eaa7f-117">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="eaa7f-118">Clique em Criar repositório.</span><span class="sxs-lookup"><span data-stu-id="eaa7f-118">Click Create repository.</span></span>
7. <span data-ttu-id="eaa7f-119">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="eaa7f-119">Click OK.</span></span>

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a><span data-ttu-id="eaa7f-120">Obter as configurações do intrastat fornecidas pela Microsoft</span><span class="sxs-lookup"><span data-stu-id="eaa7f-120">Get the Intrastat configurations provided by Microsoft</span></span>
1. <span data-ttu-id="eaa7f-121">Clique em Abrir.</span><span class="sxs-lookup"><span data-stu-id="eaa7f-121">Click Open.</span></span>
2. <span data-ttu-id="eaa7f-122">Na árvore, selecione 'Modelo intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="eaa7f-122">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
3. <span data-ttu-id="eaa7f-123">Clique em Importar.</span><span class="sxs-lookup"><span data-stu-id="eaa7f-123">Click Import.</span></span>
    * <span data-ttu-id="eaa7f-124">Clique em Importar para a versão 1.1 da configuração selecionada.</span><span class="sxs-lookup"><span data-stu-id="eaa7f-124">Click Import for version 1.1 of the selected configuration.</span></span>  
4. <span data-ttu-id="eaa7f-125">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="eaa7f-125">Click Yes.</span></span>
5. <span data-ttu-id="eaa7f-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="eaa7f-126">Close the page.</span></span>
6. <span data-ttu-id="eaa7f-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="eaa7f-127">Close the page.</span></span>
7. <span data-ttu-id="eaa7f-128">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="eaa7f-128">Click Reporting configurations.</span></span>
8. <span data-ttu-id="eaa7f-129">Na árvore, expanda 'Modelo intrastat'.</span><span class="sxs-lookup"><span data-stu-id="eaa7f-129">In the tree, expand 'Intrastat model'.</span></span>
9. <span data-ttu-id="eaa7f-130">Na árvore, selecione 'Modelo intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="eaa7f-130">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>


