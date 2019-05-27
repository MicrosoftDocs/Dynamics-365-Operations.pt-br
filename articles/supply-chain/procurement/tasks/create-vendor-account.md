---
title: Criar uma conta de fornecedor
description: Este procedimento mostra como criar uma conta de fornecedor, e adicionar um endereço e as informações de contato.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddressGrid, DirPartyLookup, LogisticsPostalAddress, SysLookupMultiSelectGrid
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 22c7a1a2b7468f00aa25a67a2c5f62b088e2fe7c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1546170"
---
# <a name="create-a-vendor-account"></a><span data-ttu-id="81913-103">Criar uma conta de fornecedor</span><span class="sxs-lookup"><span data-stu-id="81913-103">Create a vendor account</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="81913-104">Este procedimento mostra como criar uma conta de fornecedor, e adicionar um endereço e as informações de contato.</span><span class="sxs-lookup"><span data-stu-id="81913-104">This procedure shows how to create a vendor account, and add an address and contact information.</span></span> <span data-ttu-id="81913-105">O procedimento não mostra como preencher todos os campos para fins financeiros e de compra.</span><span class="sxs-lookup"><span data-stu-id="81913-105">The procedure does not show how to populate all fields for purchasing and financial purposes.</span></span> <span data-ttu-id="81913-106">Para obter mais informações sobre esses campos, por favor leia as descrições dos campos.</span><span class="sxs-lookup"><span data-stu-id="81913-106">To learn more about those fields, please read the field descriptions.</span></span> <span data-ttu-id="81913-107">Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou nos seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="81913-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="81913-108">As contas de fornecedor são criadas tipicamente por um profissional de aquisição ou por equipes de contas a receber.</span><span class="sxs-lookup"><span data-stu-id="81913-108">Vendor accounts are typically created by a procurement professional or accounts receivable personnel.</span></span>


## <a name="create-a-vendor-account"></a><span data-ttu-id="81913-109">Criar uma conta de fornecedor</span><span class="sxs-lookup"><span data-stu-id="81913-109">Create a vendor account</span></span>
1. <span data-ttu-id="81913-110">Vá para Aquisição e fornecimento > Fornecedores > Todos os fornecedores.</span><span class="sxs-lookup"><span data-stu-id="81913-110">Go to Procurement and sourcing > Vendors > All vendors.</span></span>
2. <span data-ttu-id="81913-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="81913-111">Click New.</span></span>
3. <span data-ttu-id="81913-112">No campo Conta de fornecedor, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="81913-112">In the Vendor account field, type a value.</span></span>
    * <span data-ttu-id="81913-113">O valor pode ser preenchido automaticamente.</span><span class="sxs-lookup"><span data-stu-id="81913-113">The value may be populated automatically.</span></span> <span data-ttu-id="81913-114">Nesse caso, é possível ignorar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="81913-114">If so, you can skip this step.</span></span>  
    * <span data-ttu-id="81913-115">Você pode criar contas de fornecedor para uma pessoa ou uma organização.</span><span class="sxs-lookup"><span data-stu-id="81913-115">You can create vendor accounts for a person or organization.</span></span> <span data-ttu-id="81913-116">Isso irá afetar quais campos estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="81913-116">This will affect which fields are available.</span></span> <span data-ttu-id="81913-117">Neste exemplo, iremos criar uma conta de fornecedor para uma organização.</span><span class="sxs-lookup"><span data-stu-id="81913-117">In this example, we’ll create a vendor account for an organization.</span></span>   
4. <span data-ttu-id="81913-118">No campo Nome, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="81913-118">In the Name field, enter or select a value.</span></span>
    * <span data-ttu-id="81913-119">Se o seu fornecedor já é um participante registrado no seu sistema, você pode usar o botão suspenso e selecioná-los nesse campo e a nova conta de fornecedor herdará as informações de endereço e contato já registradas.</span><span class="sxs-lookup"><span data-stu-id="81913-119">If your vendor is an already a registered party in your system you can use drop down and select them in this field and the new vendor account will inherit the address and contact information that’s already registered.</span></span>  
5. <span data-ttu-id="81913-120">No campo Grupo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="81913-120">In the Group field, enter or select a value.</span></span>
    * <span data-ttu-id="81913-121">O grupo de fornecedores é usado para agrupar fornecedores que têm qualquer um dos seguintes parâmetros em comum: Condições de pagamento; período de liquidação; contas contábeis de lançamento de estoque - incluindo o grupo de impostos sobre vendas; contas contábeis padrão; códigos de filtro de produto ou configuração de previsão de fornecimento.</span><span class="sxs-lookup"><span data-stu-id="81913-121">The vendor group is used to group vendors that have any of the following parameters in common: Terms of payment , settle period,  inventory posting ledger accounts – including the sales tax group, default ledger accounts, product filter codes, or supply forecast configuration.</span></span>  
6. <span data-ttu-id="81913-122">No campo Número de funcionários, insira um número.</span><span class="sxs-lookup"><span data-stu-id="81913-122">In the Number of employees field, enter a number.</span></span>
7. <span data-ttu-id="81913-123">No campo Número da organização, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="81913-123">In the Organization number field, type a value.</span></span>

## <a name="add-an-address"></a><span data-ttu-id="81913-124">Adicionar um endereço</span><span class="sxs-lookup"><span data-stu-id="81913-124">Add an address</span></span>
1. <span data-ttu-id="81913-125">Expanda a seção Endereços.</span><span class="sxs-lookup"><span data-stu-id="81913-125">Expand the Addresses section.</span></span>
2. <span data-ttu-id="81913-126">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="81913-126">Click Add.</span></span>
3. <span data-ttu-id="81913-127">No campo Motivo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="81913-127">In the Purpose field, enter or select a value.</span></span>
    * <span data-ttu-id="81913-128">Você pode selecionar um ou mais motivos.</span><span class="sxs-lookup"><span data-stu-id="81913-128">You can select one or more purposes.</span></span> <span data-ttu-id="81913-129">Esses são usados para selecionar o endereço correto para uma finalidade específica.</span><span class="sxs-lookup"><span data-stu-id="81913-129">These are used to select the correct address for a given purpose.</span></span> <span data-ttu-id="81913-130">Por exemplo, se a finalidade for "Nota fiscal", esse endereço será usado ao enviar notas fiscais.</span><span class="sxs-lookup"><span data-stu-id="81913-130">For example, if the purpose is “Invoice” that address will be used when you send invoices.</span></span>  
4. <span data-ttu-id="81913-131">No campo Nome ou Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="81913-131">In the Name or description field, type a value.</span></span>
5. <span data-ttu-id="81913-132">No campo País/região, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="81913-132">In the Country/region field, enter or select a value.</span></span>
    * <span data-ttu-id="81913-133">Insira os detalhes do endereço.</span><span class="sxs-lookup"><span data-stu-id="81913-133">Enter the address details.</span></span> <span data-ttu-id="81913-134">O país/região selecionado irá determinar os campos que serão apresentados, correspondente ao formato de endereço para o país/região.</span><span class="sxs-lookup"><span data-stu-id="81913-134">The country/region that you selected will determine the fields you are presented with, corresponding to the address format for the country/region.</span></span>   
6. <span data-ttu-id="81913-135">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="81913-135">Click OK.</span></span>

## <a name="add-contact-information"></a><span data-ttu-id="81913-136">Adicionar informações de contato</span><span class="sxs-lookup"><span data-stu-id="81913-136">Add contact information</span></span>
1. <span data-ttu-id="81913-137">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="81913-137">Click Add.</span></span>
2. <span data-ttu-id="81913-138">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="81913-138">In the Description field, type a value.</span></span>
3. <span data-ttu-id="81913-139">No campo Tipo, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="81913-139">In the Type field, select an option.</span></span>
4. <span data-ttu-id="81913-140">No campo Número/endereço de contato, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="81913-140">In the Contact number/address field, type a value.</span></span>
    * <span data-ttu-id="81913-141">Você pode selecionar a caixa de seleção Principal se este for o contato primário.</span><span class="sxs-lookup"><span data-stu-id="81913-141">You can select the Primary check box if this is the primary contact.</span></span>  
5. <span data-ttu-id="81913-142">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="81913-142">Click Save.</span></span>
6. <span data-ttu-id="81913-143">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="81913-143">Close the page.</span></span>
7. <span data-ttu-id="81913-144">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="81913-144">Close the page.</span></span>

