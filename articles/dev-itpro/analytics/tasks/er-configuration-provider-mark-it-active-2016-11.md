--- 
title: "Criar um provedor de configuração e marcá-lo como ativo para relatório eletrônico (ER)"
description: "As etapas a seguir explicam como um usuário atribuído ao Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de fornecedor para Relatório eletrônico (RE)."
author: NickSelin
manager: AnnBe
ms.date: 10/18/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: bdb3a3857a7293828a7766b6988c123a43e0673c
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-configuration-providand-mark-it-as-active-for-electronic-reporting-er"></a><span data-ttu-id="c2649-103">Criar um provedor de configuração e marcá-lo como ativo para relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="c2649-103">Create a configuration providand mark it as active for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c2649-104">As etapas a seguir explicam como um usuário atribuído ao Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de fornecedor para Relatório eletrônico (RE).</span><span class="sxs-lookup"><span data-stu-id="c2649-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="c2649-105">Cada configuração RE será referida ao fornecedor como o autor da configuração.</span><span class="sxs-lookup"><span data-stu-id="c2649-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="c2649-106">Neste exemplo, será criado um provedor de configuração para a empresa de exemplo, Litware, Inc. Essas etapas podem ser executadas em toda a empresa, uma vez que prestadores de configuração de ER são compartilhados entre todas as empresas.</span><span class="sxs-lookup"><span data-stu-id="c2649-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>


## <a name="create-a-provider"></a><span data-ttu-id="c2649-107">Criar um fornecedor</span><span class="sxs-lookup"><span data-stu-id="c2649-107">Create a provider</span></span>
1. <span data-ttu-id="c2649-108">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="c2649-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="c2649-109">Clique em Provedores de configuração.</span><span class="sxs-lookup"><span data-stu-id="c2649-109">Click Configuration providers.</span></span>
3. <span data-ttu-id="c2649-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c2649-110">Click New.</span></span>
    * <span data-ttu-id="c2649-111">Um registro de fornecedor tem nome e URL exclusivos.</span><span class="sxs-lookup"><span data-stu-id="c2649-111">A provider record has a unique name and URL.</span></span> <span data-ttu-id="c2649-112">Revise o conteúdo desta página e ignore este procedimento se um registro para Litware, Inc. (http://www.litware.com) já existir.</span><span class="sxs-lookup"><span data-stu-id="c2649-112">Review the content of this page and skip this procedure if a record for Litware, Inc. (http://www.litware.com) already exists.</span></span>  
4. <span data-ttu-id="c2649-113">No campo Nome, digite 'Litware, Inc.'.</span><span class="sxs-lookup"><span data-stu-id="c2649-113">In the Name field, type 'Litware, Inc.'.</span></span>
    * <span data-ttu-id="c2649-114">Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="c2649-114">Litware, Inc.</span></span>  
5. <span data-ttu-id="c2649-115">No campo da internet, digite 'http://www.litware.com'.</span><span class="sxs-lookup"><span data-stu-id="c2649-115">In the Internet address field, type 'http://www.litware.com'.</span></span>
    * <span data-ttu-id="c2649-116">http://www.litware.com</span><span class="sxs-lookup"><span data-stu-id="c2649-116">http://www.litware.com</span></span>  
6. <span data-ttu-id="c2649-117">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c2649-117">Click Save.</span></span>
7. <span data-ttu-id="c2649-118">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c2649-118">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="c2649-119">Selecione como um provedor ativo</span><span class="sxs-lookup"><span data-stu-id="c2649-119">Select as an active provider</span></span>
1. <span data-ttu-id="c2649-120">Selecione o fornecedor "Litware, Inc.".</span><span class="sxs-lookup"><span data-stu-id="c2649-120">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="c2649-121">Clique em Definir como ativo.</span><span class="sxs-lookup"><span data-stu-id="c2649-121">Click Set active.</span></span>


