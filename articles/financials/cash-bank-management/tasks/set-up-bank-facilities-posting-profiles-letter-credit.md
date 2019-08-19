---
title: Configurar recursos bancários e perfis de lançamento para carta de crédito
description: Este procedimento apresenta as etapas da criação de um Recurso bancário e perfil de lançamento necessários para processar Cartas de crédito.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankParameters, DefaultDashboard, BankDocumentSetup, BankDocumentPosting
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0d3d35bd265ad31da083d2437fae886569766085
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841888"
---
# <a name="set-up-bank-facilities-and-posting-profiles-for-letter-of-credit"></a><span data-ttu-id="22bfe-103">Configurar recursos bancários e perfis de lançamento para carta de crédito</span><span class="sxs-lookup"><span data-stu-id="22bfe-103">Set up bank facilities and posting profiles for letter of credit</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="22bfe-104">Este procedimento apresenta as etapas da criação de um Recurso bancário e perfil de lançamento necessários para processar Cartas de crédito.</span><span class="sxs-lookup"><span data-stu-id="22bfe-104">This procedure walks through creating a Bank facility and posting profile required to process Letters of credit.</span></span> 

<span data-ttu-id="22bfe-105">Essas tarefas usam a empresa de demonstração 'USMF'.</span><span class="sxs-lookup"><span data-stu-id="22bfe-105">This tasks uses the demo company 'USMF'.</span></span>






## <a name="general-ledger-parameter"></a><span data-ttu-id="22bfe-106">Parâmetro da contabilidade</span><span class="sxs-lookup"><span data-stu-id="22bfe-106">General ledger parameter</span></span>
1. <span data-ttu-id="22bfe-107">Vá para Gerenciamento de dinheiro e banco > Configuração > Parâmetros do gerenciamento de dinheiro e banco.</span><span class="sxs-lookup"><span data-stu-id="22bfe-107">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="22bfe-108">Expanda a seção Documento bancário.</span><span class="sxs-lookup"><span data-stu-id="22bfe-108">Expand the Bank document section.</span></span>
3. <span data-ttu-id="22bfe-109">Selecione a opção Habilitar importação de carta de crédito.</span><span class="sxs-lookup"><span data-stu-id="22bfe-109">Select the Enable import letter of credit option.</span></span>
4. <span data-ttu-id="22bfe-110">Selecione a opção Habilitar exportação de carta de crédito.</span><span class="sxs-lookup"><span data-stu-id="22bfe-110">Select the Enable export letter of credit option.</span></span>
5. <span data-ttu-id="22bfe-111">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="22bfe-111">Click Save.</span></span>
6. <span data-ttu-id="22bfe-112">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="22bfe-112">Close the page.</span></span>

## <a name="create-bank-facility"></a><span data-ttu-id="22bfe-113">Criar Recursos bancários</span><span class="sxs-lookup"><span data-stu-id="22bfe-113">Create Bank facility</span></span>
1. <span data-ttu-id="22bfe-114">Vá para Gerenciamento de dinheiro e banco > Configuração > Recursos bancários.</span><span class="sxs-lookup"><span data-stu-id="22bfe-114">Go to Cash and bank management > Setup > Bank facilities.</span></span>
2. <span data-ttu-id="22bfe-115">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="22bfe-115">Click New.</span></span>
3. <span data-ttu-id="22bfe-116">No campo Grupo de recursos, insira o nome do grupo de recursos bancários.</span><span class="sxs-lookup"><span data-stu-id="22bfe-116">In the Facility group field, enter the bank facility group name.</span></span>
4. <span data-ttu-id="22bfe-117">No campo Descrição, insira a descrição do grupo de recursos bancários.</span><span class="sxs-lookup"><span data-stu-id="22bfe-117">In the Description field, enter the bank facility group description.</span></span>
5. <span data-ttu-id="22bfe-118">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="22bfe-118">Click Save.</span></span>
6. <span data-ttu-id="22bfe-119">Clique na aba Tipos de recursos.</span><span class="sxs-lookup"><span data-stu-id="22bfe-119">Click the Facility types tab.</span></span>
7. <span data-ttu-id="22bfe-120">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="22bfe-120">Click New.</span></span>
8. <span data-ttu-id="22bfe-121">No campo Tipo de recurso, insira um código exclusivo.</span><span class="sxs-lookup"><span data-stu-id="22bfe-121">In the Facility type field, enter a unique code.</span></span>
9. <span data-ttu-id="22bfe-122">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="22bfe-122">In the Description field, type a value.</span></span>
10. <span data-ttu-id="22bfe-123">No campo Grupo de recursos, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="22bfe-123">In the Facility group field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="22bfe-124">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="22bfe-124">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="22bfe-125">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="22bfe-125">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="22bfe-126">No campo Natureza dos recursos, selecione a natureza dos recursos bancários.</span><span class="sxs-lookup"><span data-stu-id="22bfe-126">In the Facility nature field, select the nature of the bank facility.</span></span>
14. <span data-ttu-id="22bfe-127">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="22bfe-127">Click Save.</span></span>
15. <span data-ttu-id="22bfe-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="22bfe-128">Close the page.</span></span>

## <a name="bank-posting-profile"></a><span data-ttu-id="22bfe-129">Perfil de lançamento bancário</span><span class="sxs-lookup"><span data-stu-id="22bfe-129">Bank posting profile</span></span>
1. <span data-ttu-id="22bfe-130">Vá para Gerenciamento de dinheiro e banco > Configuração > Perfil de lançamento de documentos bancários.</span><span class="sxs-lookup"><span data-stu-id="22bfe-130">Go to Cash and bank management > Setup > Bank documents posting profile.</span></span>
2. <span data-ttu-id="22bfe-131">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="22bfe-131">Click New.</span></span>
3. <span data-ttu-id="22bfe-132">No campo Número de conta/grupo, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="22bfe-132">In the Account/Group number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="22bfe-133">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="22bfe-133">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="22bfe-134">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="22bfe-134">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="22bfe-135">Selecione a conta principal para liquidação.</span><span class="sxs-lookup"><span data-stu-id="22bfe-135">Select the main account for settlement.</span></span>
    * <span data-ttu-id="22bfe-136">Essa conta é usada para calcular a previsão do fluxo de caixa.</span><span class="sxs-lookup"><span data-stu-id="22bfe-136">This account is used when calculating cash flow forecast.</span></span>  
7. <span data-ttu-id="22bfe-137">No campo Conta de encargos, selecione a conta para transações de despesa.</span><span class="sxs-lookup"><span data-stu-id="22bfe-137">In the Charges account field, select the account for expense transactions.</span></span>
8. <span data-ttu-id="22bfe-138">No campo Conta de margem, selecione a conta para transações de margem.</span><span class="sxs-lookup"><span data-stu-id="22bfe-138">In the Margin account field, select the account for margin transactions.</span></span>
    * <span data-ttu-id="22bfe-139">Esta conta é debitada quando a margem de abertura é lançada e creditada quando o pagamento é lançado.</span><span class="sxs-lookup"><span data-stu-id="22bfe-139">This account is debited when the opening margin is posted and credited when the payment is posted.</span></span>  
9. <span data-ttu-id="22bfe-140">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="22bfe-140">Click Save.</span></span>

