--- 
title: "Criar provedores de configuração e marcá-los como ativos"
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
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 37957f224cb57fd9f6c5014740bcea124a99a03a
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---
# <a name="create-configuration-providers-and-mark-them-as-active"></a><span data-ttu-id="85619-103">Criar provedores de configuração e marcá-los como ativos</span><span class="sxs-lookup"><span data-stu-id="85619-103">Create configuration providers and mark them as active</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="85619-104">As etapas a seguir explicam como um usuário atribuído ao Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de fornecedor para Relatório eletrônico (RE).</span><span class="sxs-lookup"><span data-stu-id="85619-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="85619-105">Cada configuração RE será referida ao fornecedor como o autor da configuração.</span><span class="sxs-lookup"><span data-stu-id="85619-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="85619-106">Neste exemplo, será criado um provedor de configuração para a empresa de exemplo, Litware, Inc. Essas etapas podem ser executadas em toda a empresa, uma vez que prestadores de configuração de ER são compartilhados entre todas as empresas.</span><span class="sxs-lookup"><span data-stu-id="85619-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>


## <a name="create-a-provider"></a><span data-ttu-id="85619-107">Criar um fornecedor</span><span class="sxs-lookup"><span data-stu-id="85619-107">Create a provider</span></span>
1. <span data-ttu-id="85619-108">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="85619-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="85619-109">Clique em Provedores de configuração.</span><span class="sxs-lookup"><span data-stu-id="85619-109">Click Configuration providers.</span></span>
3. <span data-ttu-id="85619-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="85619-110">Click New.</span></span>
    * <span data-ttu-id="85619-111">Um registro de fornecedor tem nome e URL exclusivos.</span><span class="sxs-lookup"><span data-stu-id="85619-111">A provider record has a unique name and URL.</span></span> <span data-ttu-id="85619-112">Revise o conteúdo dessa página e ignore esse procedimento se um registro para Litware, Inc. (`http://www.litware.com`) já existir.</span><span class="sxs-lookup"><span data-stu-id="85619-112">Review the content of this page and skip this procedure if a record for Litware, Inc. (`http://www.litware.com`) already exists.</span></span>  
4. <span data-ttu-id="85619-113">No campo Nome, digite 'Litware, Inc.'.</span><span class="sxs-lookup"><span data-stu-id="85619-113">In the Name field, type 'Litware, Inc.'.</span></span>
    * <span data-ttu-id="85619-114">Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="85619-114">Litware, Inc.</span></span>  
5. <span data-ttu-id="85619-115">No campo Endereço na Internet, digite `http://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="85619-115">In the Internet address field, type `http://www.litware.com`.</span></span>
6. <span data-ttu-id="85619-116">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="85619-116">Click Save.</span></span>
7. <span data-ttu-id="85619-117">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="85619-117">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="85619-118">Selecione como um provedor ativo</span><span class="sxs-lookup"><span data-stu-id="85619-118">Select as an active provider</span></span>
1. <span data-ttu-id="85619-119">Selecione o fornecedor "Litware, Inc.".</span><span class="sxs-lookup"><span data-stu-id="85619-119">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="85619-120">Clique em Definir como ativo.</span><span class="sxs-lookup"><span data-stu-id="85619-120">Click Set active.</span></span>


