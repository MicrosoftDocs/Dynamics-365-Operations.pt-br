---
title: Configurar recursos bancários e perfis de lançamento para cartas de garantia
description: Essa tarefa cria um Recurso bancário e um perfil de lançamento que são necessários para processar uma carta de garantia.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0f696f5aa809692a0cc2c4ff559945a301480d7e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566009"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letters-of-guarantee"></a><span data-ttu-id="6bb27-103">Configurar recursos bancários e perfis de lançamento para cartas de garantia</span><span class="sxs-lookup"><span data-stu-id="6bb27-103">Set up bank facilities and posting profiles for letters of guarantee</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6bb27-104">Essa tarefa cria um Recurso bancário e um perfil de lançamento que são necessários para processar uma carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="6bb27-104">This task creates a Bank facility and posting profile that is needed to process a letter of guarantee.</span></span>



<span data-ttu-id="6bb27-105">Esta tarefa usa a empresa de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="6bb27-105">This task uses the USMF demo company.</span></span> 




## <a name="general-ledger-parameter"></a><span data-ttu-id="6bb27-106">Parâmetro da contabilidade</span><span class="sxs-lookup"><span data-stu-id="6bb27-106">General ledger parameter</span></span>
1. <span data-ttu-id="6bb27-107">Vá para Gerenciamento de dinheiro e banco > Configuração > Parâmetros do gerenciamento de dinheiro e banco.</span><span class="sxs-lookup"><span data-stu-id="6bb27-107">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="6bb27-108">Expanda a seção Documento bancário.</span><span class="sxs-lookup"><span data-stu-id="6bb27-108">Expand the Bank document section.</span></span>
3. <span data-ttu-id="6bb27-109">Selecione a opção Habilitar carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="6bb27-109">Select the Enable letter of guarantee option.</span></span>
4. <span data-ttu-id="6bb27-110">No campo Diário de transação, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6bb27-110">In the Transaction journal field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="6bb27-111">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="6bb27-111">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="6bb27-112">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="6bb27-112">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="6bb27-113">Clique na aba Sequências numéricas.</span><span class="sxs-lookup"><span data-stu-id="6bb27-113">Click the Number sequences tab.</span></span>
    * <span data-ttu-id="6bb27-114">Definir código de sequência numérica para o número da Carta de garantia e referências de transação da Carta de garantia</span><span class="sxs-lookup"><span data-stu-id="6bb27-114">Define number sequence code for Letter of guarantee number and Letter of guarantee transaction references</span></span>  
8. <span data-ttu-id="6bb27-115">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="6bb27-115">Click Save.</span></span>
9. <span data-ttu-id="6bb27-116">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6bb27-116">Close the page.</span></span>

## <a name="create-bank-facility"></a><span data-ttu-id="6bb27-117">Criar Recursos bancários</span><span class="sxs-lookup"><span data-stu-id="6bb27-117">Create Bank facility</span></span>
1. <span data-ttu-id="6bb27-118">Vá para Gerenciamento de dinheiro e banco > Configuração > Recursos bancários.</span><span class="sxs-lookup"><span data-stu-id="6bb27-118">Go to Cash and bank management > Setup > Bank facilities.</span></span>
2. <span data-ttu-id="6bb27-119">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="6bb27-119">Click New.</span></span>
3. <span data-ttu-id="6bb27-120">No campo Grupo de recursos, insira o nome do grupo de recursos bancários para a transação da carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="6bb27-120">In the Facility group field, enter the bank facility group name for the letter of guarantee transaction.</span></span>
4. <span data-ttu-id="6bb27-121">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6bb27-121">In the Description field, type a value.</span></span>
5. <span data-ttu-id="6bb27-122">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="6bb27-122">Click Save.</span></span>
6. <span data-ttu-id="6bb27-123">Clique na aba Tipos de recursos.</span><span class="sxs-lookup"><span data-stu-id="6bb27-123">Click the Facility types tab.</span></span>
7. <span data-ttu-id="6bb27-124">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="6bb27-124">Click New.</span></span>
8. <span data-ttu-id="6bb27-125">No campo Tipo de recurso, insira o nome do tipo de recurso bancário que está relacionado ao contrato de recursos bancários.</span><span class="sxs-lookup"><span data-stu-id="6bb27-125">In the Facility type field, enter the name of the bank facility type that is related to the bank facility agreement.</span></span>
9. <span data-ttu-id="6bb27-126">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6bb27-126">In the Description field, type a value.</span></span>
10. <span data-ttu-id="6bb27-127">No campo Grupo de recursos, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6bb27-127">In the Facility group field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="6bb27-128">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="6bb27-128">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="6bb27-129">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="6bb27-129">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="6bb27-130">No campo Natureza dos recursos, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="6bb27-130">In the Facility nature field, select an option.</span></span>
14. <span data-ttu-id="6bb27-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="6bb27-131">Click Save.</span></span>
15. <span data-ttu-id="6bb27-132">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6bb27-132">Close the page.</span></span>

## <a name="bank-posting-profile"></a><span data-ttu-id="6bb27-133">Perfil de lançamento bancário</span><span class="sxs-lookup"><span data-stu-id="6bb27-133">Bank posting profile</span></span>
1. <span data-ttu-id="6bb27-134">Vá para Gerenciamento de dinheiro e banco > Configuração > Perfil de lançamento de documentos bancários.</span><span class="sxs-lookup"><span data-stu-id="6bb27-134">Go to Cash and bank management > Setup > Bank documents posting profile.</span></span>
2. <span data-ttu-id="6bb27-135">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="6bb27-135">Click New.</span></span>
3. <span data-ttu-id="6bb27-136">No campo Número de conta/grupo, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6bb27-136">In the Account/Group number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="6bb27-137">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="6bb27-137">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="6bb27-138">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="6bb27-138">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="6bb27-139">No campo Liquidar conta, selecione a conta principal para liquidação.</span><span class="sxs-lookup"><span data-stu-id="6bb27-139">In the Settle account field, select the main account for settlement.</span></span>
7. <span data-ttu-id="6bb27-140">No campo Conta de encargos, selecione a conta para transações de despesa.</span><span class="sxs-lookup"><span data-stu-id="6bb27-140">In the Charges account field, select the account for expense transactions.</span></span>
8. <span data-ttu-id="6bb27-141">No campo Conta de margem, selecione a conta para a transação de margem.</span><span class="sxs-lookup"><span data-stu-id="6bb27-141">In the Margin account field, select the account for the margin transaction.</span></span>
9. <span data-ttu-id="6bb27-142">No campo Conta de liquidação, selecione a conta de liquidação para a transação da carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="6bb27-142">In the Liquidation account field, select the liquidation account for the letter of guarantee transaction.</span></span> 
10. <span data-ttu-id="6bb27-143">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="6bb27-143">Click Save.</span></span>
11. <span data-ttu-id="6bb27-144">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6bb27-144">Close the page.</span></span>

