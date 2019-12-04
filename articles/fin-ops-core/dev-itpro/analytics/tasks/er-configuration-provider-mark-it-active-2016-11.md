---
title: Criar provedores de configuração e marcá-los como ativos
description: Este tópico explica como um usuário atribuído à função de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar um provedor de configuração para relatórios eletrônicos (ER).
author: NickSelin
manager: AnnBe
ms.date: 07/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d2c092414f058a27cde963b1e8befd41ab3d1e3c
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249195"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a><span data-ttu-id="bf16d-103">Criar provedores de configuração e marcá-los como ativos</span><span class="sxs-lookup"><span data-stu-id="bf16d-103">Create configuration providers and mark them as active</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bf16d-104">Este tópico explica como um usuário atribuído à função de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar um provedor de configuração para relatórios eletrônicos (ER).</span><span class="sxs-lookup"><span data-stu-id="bf16d-104">This topic explains how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="bf16d-105">Cada configuração RE será referida ao fornecedor como o autor da configuração.</span><span class="sxs-lookup"><span data-stu-id="bf16d-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="bf16d-106">Neste exemplo, será criado um provedor de configuração para a empresa de exemplo, Litware, Inc. Essas etapas podem ser executadas em toda a empresa, uma vez que prestadores de configuração de ER são compartilhados entre todas as empresas.</span><span class="sxs-lookup"><span data-stu-id="bf16d-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>

## <a name="create-a-provider"></a><span data-ttu-id="bf16d-107">Criar um fornecedor</span><span class="sxs-lookup"><span data-stu-id="bf16d-107">Create a provider</span></span>
1. <span data-ttu-id="bf16d-108">Vá para o **painel de navegação** no canto superior esquerdo e selecione **Administração da organização**.</span><span class="sxs-lookup"><span data-stu-id="bf16d-108">Go to the **navigation pane** in the upper left corner and select **Organization administration**.</span></span>
2. <span data-ttu-id="bf16d-109">Vá para **Espaços de trabalho > Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="bf16d-109">Go to **Workspaces > Electronic reporting**.</span></span>
3. <span data-ttu-id="bf16d-110">Vá para **Links relacionados > Provedores de configuração**.</span><span class="sxs-lookup"><span data-stu-id="bf16d-110">Go to **Related links > Configuration providers**.</span></span>
4. <span data-ttu-id="bf16d-111">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="bf16d-111">Select **New**.</span></span>
    - <span data-ttu-id="bf16d-112">Um registro de fornecedor tem nome e URL exclusivos.</span><span class="sxs-lookup"><span data-stu-id="bf16d-112">A provider record has a unique name and URL.</span></span> <span data-ttu-id="bf16d-113">Revise o conteúdo dessa página e ignore esse procedimento se um registro para Litware, Inc. (https://www.litware.com) já existir.</span><span class="sxs-lookup"><span data-stu-id="bf16d-113">Review the content of this page and skip this procedure if a record for Litware, Inc. (https://www.litware.com) already exists.</span></span>  
5. <span data-ttu-id="bf16d-114">No campo Nome, digite `Litware, Inc.`.</span><span class="sxs-lookup"><span data-stu-id="bf16d-114">In the Name field, type `Litware, Inc.`.</span></span>
6. <span data-ttu-id="bf16d-115">No campo Endereço na Internet, digite `https://www.litware.com`.</span><span class="sxs-lookup"><span data-stu-id="bf16d-115">In the Internet address field, type `https://www.litware.com`.</span></span>
7. <span data-ttu-id="bf16d-116">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="bf16d-116">Select **Save**.</span></span>
8. <span data-ttu-id="bf16d-117">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="bf16d-117">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="bf16d-118">Selecione como um provedor ativo</span><span class="sxs-lookup"><span data-stu-id="bf16d-118">Select as an active provider</span></span>
1. <span data-ttu-id="bf16d-119">Selecione o fornecedor "Litware, Inc.".</span><span class="sxs-lookup"><span data-stu-id="bf16d-119">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="bf16d-120">Selecione **Definir como ativo**.</span><span class="sxs-lookup"><span data-stu-id="bf16d-120">Select **Set active**.</span></span>

![Página de espaço de trabalho de relatório eletrônico](../media/GER-Task-ActiveProvider-1.png)