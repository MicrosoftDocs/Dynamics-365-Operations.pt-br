---
title: Importar usuários do Azure Active Directory
description: Este procedimento pode ser usado por administradores de sistema para importar manualmente usuários selecionados ou um grande número de usuários do Azure Active Directory.
author: peakerbl
manager: AnnBe
ms.date: 07/07/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 56b6666310309817ff30ccb3902721880b829ee0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679805"
---
# <a name="import-users-from-azure-active-directory"></a><span data-ttu-id="1e239-103">Importar usuários do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="1e239-103">Import users from Azure Active Directory</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="import-select-users"></a><span data-ttu-id="1e239-104">Importar usuários selecionados</span><span class="sxs-lookup"><span data-stu-id="1e239-104">Import select users</span></span>

<span data-ttu-id="1e239-105">Este procedimento pode ser usado por administradores de sistema para importar usuários selecionados do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="1e239-105">This procedure can be used by system administrators to import select users from Azure Active Directory (Azure AD).</span></span>

1. <span data-ttu-id="1e239-106">O usuário será importado com a empresa da sessão atual como a empresa padrão.</span><span class="sxs-lookup"><span data-stu-id="1e239-106">User will be imported with the current session company as their default company.</span></span> <span data-ttu-id="1e239-107">Altere a empresa atual, se aplicável, antes de importar usuários.</span><span class="sxs-lookup"><span data-stu-id="1e239-107">Change current company if applicable before importing users.</span></span>
2. <span data-ttu-id="1e239-108">Vá para **Administração do sistema > Usuários > Usuários**.</span><span class="sxs-lookup"><span data-stu-id="1e239-108">Go to **System administration > Users > User** s.</span></span>
3. <span data-ttu-id="1e239-109">Clique em **Importar usuários**.</span><span class="sxs-lookup"><span data-stu-id="1e239-109">Click **Import users**.</span></span>
4. <span data-ttu-id="1e239-110">Selecione os usuários que devem ser importados e selecione **Importar usuários**.</span><span class="sxs-lookup"><span data-stu-id="1e239-110">Select the users that should be imported and select **Import users**.</span></span>

<span data-ttu-id="1e239-111">Depois que a importação for concluída, será necessário atribuir funções aos usuários.</span><span class="sxs-lookup"><span data-stu-id="1e239-111">After import is completed it will be required to assign roles to users.</span></span>

## <a name="import-users-in-bulk"></a><span data-ttu-id="1e239-112">Importar usuários em massa</span><span class="sxs-lookup"><span data-stu-id="1e239-112">Import users in bulk</span></span>

<span data-ttu-id="1e239-113">Este procedimento pode ser usado por administradores de sistema para importar um grande número de usuários do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1e239-113">This procedure can be used by system administrators to import a large number of users from Azure Active Directory.</span></span>
<span data-ttu-id="1e239-114">Observe que não será possível selecionar usuários ao usar a opção Importação em lote.</span><span class="sxs-lookup"><span data-stu-id="1e239-114">Note that it is not possible to select users when using the Batch import option.</span></span>

## <a name="run-the-import-as-a-batch-job"></a><span data-ttu-id="1e239-115">Execute a importação como um trabalho em lotes</span><span class="sxs-lookup"><span data-stu-id="1e239-115">Run the import as a batch job</span></span>
1. <span data-ttu-id="1e239-116">O usuário será importado com a empresa da sessão atual como a empresa padrão.</span><span class="sxs-lookup"><span data-stu-id="1e239-116">User will be imported with the current session company as their default company.</span></span> <span data-ttu-id="1e239-117">Altere a empresa atual, se aplicável, antes de importar usuários.</span><span class="sxs-lookup"><span data-stu-id="1e239-117">Change current company if applicable before importing users.</span></span>
2. <span data-ttu-id="1e239-118">Vá para **Administração do sistema > Usuários > Usuários**.</span><span class="sxs-lookup"><span data-stu-id="1e239-118">Go to **System administration > Users > Users**.</span></span>
3. <span data-ttu-id="1e239-119">Clique em **Importação em lote**.</span><span class="sxs-lookup"><span data-stu-id="1e239-119">Click **Batch import**.</span></span>
4. <span data-ttu-id="1e239-120">Expanda a seção **Executar em segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="1e239-120">Expand the **Run in the background** section.</span></span>
4. <span data-ttu-id="1e239-121">Selecione \*\*Sim no campo **Processamento em lotes**.</span><span class="sxs-lookup"><span data-stu-id="1e239-121">Select \*\*Yes in the **Batch processing** field.</span></span>
6. <span data-ttu-id="1e239-122">No campo **Grupo de lotes**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="1e239-122">In the **Batch group** field, enter or select a value.</span></span> <span data-ttu-id="1e239-123">Essa etapa é opcional.</span><span class="sxs-lookup"><span data-stu-id="1e239-123">This is an optional step.</span></span>  
7. <span data-ttu-id="1e239-124">Selecione **Sim** no campo **Particular**.</span><span class="sxs-lookup"><span data-stu-id="1e239-124">Select **Yes** in the **Private** field.</span></span> <span data-ttu-id="1e239-125">Essa etapa é opcional.</span><span class="sxs-lookup"><span data-stu-id="1e239-125">This is an optional step.</span></span>  
8. <span data-ttu-id="1e239-126">Selecione **Sim** no campo **Trabalho crítico**.</span><span class="sxs-lookup"><span data-stu-id="1e239-126">Select **Yes** in the **Critical job** field.</span></span> <span data-ttu-id="1e239-127">Esta etapa é opcional.</span><span class="sxs-lookup"><span data-stu-id="1e239-127">bThis is an optional step.</span></span>  
9. <span data-ttu-id="1e239-128">No campo \*\*Categoria de monitoramento, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="1e239-128">In the \*\*Monitoring category field, select an option.</span></span>
10. <span data-ttu-id="1e239-129">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e239-129">Click **OK**.</span></span>

<span data-ttu-id="1e239-130">Depois que a importação for concluída, será necessário atribuir funções aos usuários.</span><span class="sxs-lookup"><span data-stu-id="1e239-130">After import is completed, it will be required to assign roles to users.</span></span>

## <a name="run-in-a-sandbox-environment"></a><span data-ttu-id="1e239-131">Executar em um ambiente de área restrita</span><span class="sxs-lookup"><span data-stu-id="1e239-131">Run in a sandbox environment</span></span>
1. <span data-ttu-id="1e239-132">Selecione **Importação em lote**.</span><span class="sxs-lookup"><span data-stu-id="1e239-132">Select **Batch import**.</span></span>
2. <span data-ttu-id="1e239-133">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e239-133">Select **OK**.</span></span>
