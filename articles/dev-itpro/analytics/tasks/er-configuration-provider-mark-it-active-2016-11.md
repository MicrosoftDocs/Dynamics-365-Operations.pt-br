--- 
title: "Criar um provedor de configuração e marcá-lo como ativo para relatórios eletrônicos (ER)"
description: "As etapas a seguir explicam como um usuário atribuído ao Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de fornecedor para Relatório eletrônico (RE)."
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 8392e789f546e32a00736c02eccf47d00893cc8b
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-configuration-provider-and-mark-it-as-active-for-electronic-reporting-er"></a><span data-ttu-id="9f2e1-103">Criar um provedor de configuração e marcá-lo como ativo para relatórios eletrônicos (ER)</span><span class="sxs-lookup"><span data-stu-id="9f2e1-103">Create a configuration provider and mark it as active for electronic reporting (ER)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9f2e1-104">As etapas a seguir explicam como um usuário atribuído ao Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de fornecedor para Relatório eletrônico (RE).</span><span class="sxs-lookup"><span data-stu-id="9f2e1-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="9f2e1-105">Cada configuração RE será referida ao fornecedor como o autor da configuração.</span><span class="sxs-lookup"><span data-stu-id="9f2e1-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="9f2e1-106">Neste exemplo, será criado um provedor de configuração para a empresa de exemplo, Litware, Inc. Essas etapas podem ser executadas em toda a empresa, uma vez que prestadores de configuração de ER são compartilhados entre todas as empresas.</span><span class="sxs-lookup"><span data-stu-id="9f2e1-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>


## <a name="create-a-provider"></a><span data-ttu-id="9f2e1-107">Criar um fornecedor</span><span class="sxs-lookup"><span data-stu-id="9f2e1-107">Create a provider</span></span>
1. <span data-ttu-id="9f2e1-108">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="9f2e1-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="9f2e1-109">Clique em Provedores de configuração.</span><span class="sxs-lookup"><span data-stu-id="9f2e1-109">Click Configuration providers.</span></span>
3. <span data-ttu-id="9f2e1-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="9f2e1-110">Click New.</span></span>
    * <span data-ttu-id="9f2e1-111">Um registro de fornecedor tem nome e URL exclusivos.</span><span class="sxs-lookup"><span data-stu-id="9f2e1-111">A provider record has a unique name and URL.</span></span> <span data-ttu-id="9f2e1-112">Revise o conteúdo dessa página e ignore esse procedimento se um registro para Litware, Inc. (`http://www.litware.com`) já existir.</span><span class="sxs-lookup"><span data-stu-id="9f2e1-112">Review the content of this page and skip this procedure if a record for Litware, Inc. (`http://www.litware.com`) already exists.</span></span>  
4. <span data-ttu-id="9f2e1-113">No campo Nome, digite 'Litware, Inc.'.</span><span class="sxs-lookup"><span data-stu-id="9f2e1-113">In the Name field, type 'Litware, Inc.'.</span></span>
    * <span data-ttu-id="9f2e1-114">Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="9f2e1-114">Litware, Inc.</span></span>  
5. <span data-ttu-id="9f2e1-115">No campo Endereço na Internet, digite `http://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="9f2e1-115">In the Internet address field, type `http://www.litware.com`.</span></span>
6. <span data-ttu-id="9f2e1-116">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="9f2e1-116">Click Save.</span></span>
7. <span data-ttu-id="9f2e1-117">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="9f2e1-117">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="9f2e1-118">Selecione como um provedor ativo</span><span class="sxs-lookup"><span data-stu-id="9f2e1-118">Select as an active provider</span></span>
1. <span data-ttu-id="9f2e1-119">Selecione o fornecedor "Litware, Inc.".</span><span class="sxs-lookup"><span data-stu-id="9f2e1-119">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="9f2e1-120">Clique em Definir como ativo.</span><span class="sxs-lookup"><span data-stu-id="9f2e1-120">Click Set active.</span></span>


