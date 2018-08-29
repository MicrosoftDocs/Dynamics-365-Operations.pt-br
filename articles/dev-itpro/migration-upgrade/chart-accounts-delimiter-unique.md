---
title: Tornar o delimitador do plano de contas exclusivo
description: "No Dynamics 365 for Finance and Operations, você não pode ter o mesmo delimitador para o plano de contas e para os valores de dimensão. Você deve alterar os valores do delimitador após a atualização."
author: ryansandness
manager: AnnBe
ms.date: 03/30/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: e197a1b44e038a97b8bf6db692dcc2eef2bc5f7b
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---

# <a name="make-the-chart-of-accounts-delimiter-unique"></a><span data-ttu-id="d160a-104">Tornar o delimitador do plano de contas exclusivo</span><span class="sxs-lookup"><span data-stu-id="d160a-104">Make the chart of accounts delimiter unique</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d160a-105">No Microsoft Dynamics AX 2012, é possível usar o mesmo delimitador para o plano de contas e para os valores de dimensão.</span><span class="sxs-lookup"><span data-stu-id="d160a-105">In Microsoft Dynamics AX 2012, you could use the same delimiter for your chart of accounts and dimension values.</span></span> <span data-ttu-id="d160a-106">No Dynamics 365 for Finance and Operations, você não pode ter o mesmo delimitador para o plano de contas e para os valores de dimensão.</span><span class="sxs-lookup"><span data-stu-id="d160a-106">In Dynamics 365 for Finance and Operations, you cannot have the same delimiter for the chart of accounts and dimension values.</span></span> <span data-ttu-id="d160a-107">Se houver um delimitador duplicado, você poderá alterá-lo após a atualização.</span><span class="sxs-lookup"><span data-stu-id="d160a-107">If there is a duplicate delimiter, you can change it after upgrade.</span></span> 

<span data-ttu-id="d160a-108">Este recurso não está disponível no:</span><span class="sxs-lookup"><span data-stu-id="d160a-108">This feature is available in:</span></span>
- <span data-ttu-id="d160a-109">Dynamics 365 for Finance and Operations, versão 8.0</span><span class="sxs-lookup"><span data-stu-id="d160a-109">Dynamics 365 for Finance and Operations version 8.0</span></span>
- <span data-ttu-id="d160a-110">Dynamics 365 for Finance and Operations, versão 7.1, KB 4094701 – não é possível inserir as dimensões financeiras quando os valores de dimensões contiverem o delimitador de plano de contas</span><span class="sxs-lookup"><span data-stu-id="d160a-110">Dynamics 365 for Finance and Operations version 7.1, KB 4094701 Cannot enter the financial dimensions when the dimension values contain the chart of accounts delimiter</span></span>
- <span data-ttu-id="d160a-111">Dynamics 365 for Finance and Operations, versão 7.2, KB 4094701 – não é possível optar por subprojeto como a dimensão quando o formato do subprojeto contiver o delimitador de dimensão</span><span class="sxs-lookup"><span data-stu-id="d160a-111">Dynamics 365 for Finance and Operations version 7.2, KB 4092967 Cannot choose sub-project as dimension when sub-project format contains the dimension delimiter</span></span>

## <a name="update-delimiter"></a><span data-ttu-id="d160a-112">Atualizar delimitador</span><span class="sxs-lookup"><span data-stu-id="d160a-112">Update delimiter</span></span>
<span data-ttu-id="d160a-113">Se houver um conflito com o Plano de contas, o delimitador do Plano de contas e o formato da ID de projeto/subprojeto poderá ser alterado.</span><span class="sxs-lookup"><span data-stu-id="d160a-113">If there is a conflict with the Chart of Accounts, the Chart of accounts delimiter and the project/subproject ID format can be changed.</span></span> <span data-ttu-id="d160a-114">Nenhum outro delimitador de dimensão pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="d160a-114">No other dimension delimiters can be changed.</span></span> 
- <span data-ttu-id="d160a-115">Você poderá alterar o delimitador do plano de contas depois que atualizar o Finance and Operations em **Parâmetros de contabilidade** > **Plano de contas e dimensões** > **Alterar delimitador**.</span><span class="sxs-lookup"><span data-stu-id="d160a-115">You can change the chart of accounts delimiter after upgrade to Finance and Operations in **General ledger parameters** > **Chart of accounts and dimensions** > **Change delimiter**.</span></span> 
- <span data-ttu-id="d160a-116">Se o único conflito for com o formato da ID do projeto/subprojeto, você poderá alterar esse valor em **Parâmetros de gerenciamento e contabilidade de projetos** > **Geral** > **Modificar o formato do subprojeto**.</span><span class="sxs-lookup"><span data-stu-id="d160a-116">If the only conflict is with the project/subproject ID format, you can change that value in **Project management and accounting parameters** > **General** > **Modify subproject format**.</span></span> 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a><span data-ttu-id="d160a-117">Como determinar se o ambiente requer delimitadores atualizados</span><span class="sxs-lookup"><span data-stu-id="d160a-117">How to determine if your environment requires updated delimiters</span></span> 
<span data-ttu-id="d160a-118">Se os delimitadores em seu ambiente atualizado estiverem em conflito, é possível que haja instabilidade ao inserir valores em um controle de entrada segmentada ou em um controle entrada de dimensão.</span><span class="sxs-lookup"><span data-stu-id="d160a-118">If delimiters in your upgraded environment are conflicting, you may experience instability when entering values in a segmented entry control or dimension entry control.</span></span> <span data-ttu-id="d160a-119">Isso significa que você sempre precisará usar pesquisas ou um menu suspenso ao inserir combinações de conta e dimensão.</span><span class="sxs-lookup"><span data-stu-id="d160a-119">This means that you will need to always use lookups or a flyout menu when entering account and dimension combinations.</span></span>

