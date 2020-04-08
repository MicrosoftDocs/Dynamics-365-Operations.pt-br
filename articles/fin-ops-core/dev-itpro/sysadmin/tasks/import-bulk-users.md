---
title: Importar usuários em massa
description: Este procedimento pode ser usado por administradores de sistema para importar um grande número de usuários do Azure Active Directory.
author: maertenm
manager: AnnBe
ms.date: 07/07/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7d8b55895c9dfaf1c69cd319697f1e0da5990daf
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144078"
---
# <a name="import-users-in-bulk"></a><span data-ttu-id="a37a0-103">Importar usuários em massa</span><span class="sxs-lookup"><span data-stu-id="a37a0-103">Import users in bulk</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a37a0-104">Este procedimento pode ser usado por administradores de sistema para importar um grande número de usuários do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a37a0-104">This procedure can be used by system administrators to import a large number of users from Azure Active Directory.</span></span>


## <a name="run-as-a-batch-job"></a><span data-ttu-id="a37a0-105">Executar como trabalho em lotes</span><span class="sxs-lookup"><span data-stu-id="a37a0-105">Run as a batch job</span></span>
1. <span data-ttu-id="a37a0-106">Vá para Administração do sistema > Usuários > Usuários.</span><span class="sxs-lookup"><span data-stu-id="a37a0-106">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="a37a0-107">Clique em Importação em lote.</span><span class="sxs-lookup"><span data-stu-id="a37a0-107">Click Batch import.</span></span>
3. <span data-ttu-id="a37a0-108">Expanda a seção Executar em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="a37a0-108">Expand the Run in the background section.</span></span>
4. <span data-ttu-id="a37a0-109">Selecione Sim no campo Processamento de lote.</span><span class="sxs-lookup"><span data-stu-id="a37a0-109">Select Yes in the Batch processing field.</span></span>
5. <span data-ttu-id="a37a0-110">No campo Descrição da tarefa, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a37a0-110">In the Task description field, type a value.</span></span>
6. <span data-ttu-id="a37a0-111">No campo Grupo de lotes, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a37a0-111">In the Batch group field, enter or select a value.</span></span>
    * <span data-ttu-id="a37a0-112">Essa etapa é opcional.</span><span class="sxs-lookup"><span data-stu-id="a37a0-112">This is an optional step.</span></span>  
7. <span data-ttu-id="a37a0-113">Selecione Sim no campo Particular.</span><span class="sxs-lookup"><span data-stu-id="a37a0-113">Select Yes in the Private field.</span></span>
    * <span data-ttu-id="a37a0-114">Essa etapa é opcional.</span><span class="sxs-lookup"><span data-stu-id="a37a0-114">This is an optional step.</span></span>  
8. <span data-ttu-id="a37a0-115">Selecione Sim no campo Trabalho crítico.</span><span class="sxs-lookup"><span data-stu-id="a37a0-115">Select Yes in the Critical Job field.</span></span>
    * <span data-ttu-id="a37a0-116">Essa etapa é opcional.</span><span class="sxs-lookup"><span data-stu-id="a37a0-116">This is an optional step.</span></span>  
9. <span data-ttu-id="a37a0-117">No campo Monitorando categoria, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="a37a0-117">In the Monitoring category field, select an option.</span></span>
10. <span data-ttu-id="a37a0-118">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a37a0-118">Click OK.</span></span>

## <a name="run-in-a-sandbox-environment"></a><span data-ttu-id="a37a0-119">Executar em um ambiente de área restrita</span><span class="sxs-lookup"><span data-stu-id="a37a0-119">Run in a sandbox environment</span></span>
1. <span data-ttu-id="a37a0-120">Clique em Importação em lote.</span><span class="sxs-lookup"><span data-stu-id="a37a0-120">Click Batch import.</span></span>
2. <span data-ttu-id="a37a0-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a37a0-121">Click OK.</span></span>

