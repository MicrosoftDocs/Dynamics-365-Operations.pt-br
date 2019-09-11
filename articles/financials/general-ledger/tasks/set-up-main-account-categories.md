---
title: Configurar categorias de conta principal
description: Este tópico explica como configurar as categorias da conta principal no Dynamics 365 for Finance and Operations.
author: aprilolson
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MainAccountCategory, MainAccountCategoryLink
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4d37deb0bda225abb111375d8a00ae22d9e0c4fe
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916059"
---
# <a name="set-up-main-account-categories"></a><span data-ttu-id="38f5a-103">Configurar categorias de conta principal</span><span class="sxs-lookup"><span data-stu-id="38f5a-103">Set up main account categories</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="38f5a-104">Este tópico explica como configurar as categorias da conta principal no Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="38f5a-104">This topic explains how to set up main account categories in Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="38f5a-105">Categorias de conta principal são usadas para os relatórios padrão em relatórios financeiros e no Power BI.</span><span class="sxs-lookup"><span data-stu-id="38f5a-105">Main account categories are used for the default reports in financial reporting and in Power BI.</span></span> <span data-ttu-id="38f5a-106">Categorias de conta principal que são criadas por padrão podem ser renomeadas, mas não excluídas.</span><span class="sxs-lookup"><span data-stu-id="38f5a-106">Main account categories that are created by default can be renamed but not deleted.</span></span> <span data-ttu-id="38f5a-107">Categorias de conta adicional podem ser criadas e usadas para fins de relatório e análise.</span><span class="sxs-lookup"><span data-stu-id="38f5a-107">Additional account categories can be created and used for reporting and analysis purposes.</span></span> <span data-ttu-id="38f5a-108">Este tópico usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="38f5a-108">This topic uses the USMF demo company.</span></span>

## <a name="create-a-main-account-category"></a><span data-ttu-id="38f5a-109">Criar uma categoria de conta principal</span><span class="sxs-lookup"><span data-stu-id="38f5a-109">Create a main account category</span></span>
1. <span data-ttu-id="38f5a-110">No painel de navegação, acesse **Módulos > Contabilidade >Plano de contas > Contas > Categorias de conta principal**.</span><span class="sxs-lookup"><span data-stu-id="38f5a-110">In the navigation pane, go to **Modules > General Ledger > Chart of accounts > Accounts > Main account categories**.</span></span>
2. <span data-ttu-id="38f5a-111">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="38f5a-111">Select **New**.</span></span>
3. <span data-ttu-id="38f5a-112">No campo **Categoria de conta principal**, insira um nome exclusivo.</span><span class="sxs-lookup"><span data-stu-id="38f5a-112">In the **Main account category** field, enter a unique name.</span></span>
4. <span data-ttu-id="38f5a-113">No campo **Descrição**, insira uma descrição para a categoria de conta principal.</span><span class="sxs-lookup"><span data-stu-id="38f5a-113">In the **Description field**, enter a description for the main account category.</span></span>
5. <span data-ttu-id="38f5a-114">No campo **Tipo de conta principal**, selecione o tipo de conta principal que será vinculado à categoria.</span><span class="sxs-lookup"><span data-stu-id="38f5a-114">In the **Main account type** field, select the main account type that will be linked to the category.</span></span>

## <a name="link-main-accounts-to-account-category"></a><span data-ttu-id="38f5a-115">Vincular a conta principal à categoria de conta principal</span><span class="sxs-lookup"><span data-stu-id="38f5a-115">Link main accounts to account category</span></span>
1. <span data-ttu-id="38f5a-116">Clicar em **Vincular contas principais**.</span><span class="sxs-lookup"><span data-stu-id="38f5a-116">Click **Link main accounts**.</span></span>
2. <span data-ttu-id="38f5a-117">Na lista, selecione as contas principais para atribuir à categoria de conta principal marcando as caixas a coluna **Vinculado**.</span><span class="sxs-lookup"><span data-stu-id="38f5a-117">In the list, select the main accounts to assign to the main account category by checking the boxes in the **Linked** column.</span></span> <span data-ttu-id="38f5a-118">A atribuição de contas principais a uma categoria de conta principal agregará os saldos das contas quando essa categoria é usada para relatórios e análise financeiros.</span><span class="sxs-lookup"><span data-stu-id="38f5a-118">Assigning main accounts to a main account category will aggregate the balances of the accounts when that category is used for financial reporting and analysis.</span></span>  
3. <span data-ttu-id="38f5a-119">Marque ou desmarque a opção **Vinculada** para escolher as contas principais.</span><span class="sxs-lookup"><span data-stu-id="38f5a-119">Select or clear the **Linked** option to choose the main accounts.</span></span>
4. <span data-ttu-id="38f5a-120">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="38f5a-120">Select **OK**.</span></span>
5. <span data-ttu-id="38f5a-121">Selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="38f5a-121">Select **Yes**.</span></span>
