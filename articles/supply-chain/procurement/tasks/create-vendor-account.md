---
title: Criar uma conta de fornecedor
description: Este procedimento mostra como criar uma conta de fornecedor, e adicionar um endereço e as informações de contato.
author: RichardLuan
manager: tfehr
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddressGrid, DirPartyLookup, LogisticsPostalAddress, SysLookupMultiSelectGrid, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e7f5723fc2aa50fc66c825eb09a01e45833b817e
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5022122"
---
# <a name="create-a-vendor-account"></a><span data-ttu-id="de41e-103">Criar uma conta de fornecedor</span><span class="sxs-lookup"><span data-stu-id="de41e-103">Create a vendor account</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="de41e-104">Este procedimento mostra como criar uma conta de fornecedor, e adicionar um endereço e as informações de contato.</span><span class="sxs-lookup"><span data-stu-id="de41e-104">This procedure shows how to create a vendor account, and add an address and contact information.</span></span> <span data-ttu-id="de41e-105">O procedimento não mostra como preencher todos os campos para fins financeiros e de compra.</span><span class="sxs-lookup"><span data-stu-id="de41e-105">The procedure does not show how to populate all fields for purchasing and financial purposes.</span></span> <span data-ttu-id="de41e-106">Para obter mais informações sobre esses campos, por favor leia as descrições dos campos.</span><span class="sxs-lookup"><span data-stu-id="de41e-106">To learn more about those fields, please read the field descriptions.</span></span> <span data-ttu-id="de41e-107">Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou nos seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="de41e-107">You can use this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="de41e-108">As contas de fornecedor são criadas tipicamente por um profissional de aquisição ou por equipes de contas a receber.</span><span class="sxs-lookup"><span data-stu-id="de41e-108">Vendor accounts are typically created by a procurement professional or accounts receivable personnel.</span></span>


## <a name="create-a-vendor-account"></a><span data-ttu-id="de41e-109">Criar uma conta de fornecedor</span><span class="sxs-lookup"><span data-stu-id="de41e-109">Create a vendor account</span></span>
1. <span data-ttu-id="de41e-110">Vá para **Painel de Navegação > Módulos > Compras e fornecimento > Fornecedores > Todos os fornecedores**.</span><span class="sxs-lookup"><span data-stu-id="de41e-110">Go to **Navigation pane > Modules > Procurement and sourcing > Vendors > All vendors**.</span></span>
2. <span data-ttu-id="de41e-111">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="de41e-111">Click **New**.</span></span>
3. <span data-ttu-id="de41e-112">No campo **Conta de fornecedor**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="de41e-112">In the **Vendor account** field, type a value.</span></span>
    - <span data-ttu-id="de41e-113">O valor pode ser preenchido automaticamente.</span><span class="sxs-lookup"><span data-stu-id="de41e-113">The value may be populated automatically.</span></span> <span data-ttu-id="de41e-114">Nesse caso, é possível ignorar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="de41e-114">If so, you can skip this step.</span></span>  
    - <span data-ttu-id="de41e-115">Você pode criar contas de fornecedor para uma pessoa ou uma organização.</span><span class="sxs-lookup"><span data-stu-id="de41e-115">You can create vendor accounts for a person or organization.</span></span> <span data-ttu-id="de41e-116">Isso irá afetar quais campos estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="de41e-116">This will affect which fields are available.</span></span> <span data-ttu-id="de41e-117">Neste exemplo, iremos criar uma conta de fornecedor para uma organização.</span><span class="sxs-lookup"><span data-stu-id="de41e-117">In this example, we'll create a vendor account for an organization.</span></span>   
4. <span data-ttu-id="de41e-118">No campo **Nome**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="de41e-118">In the **Name** field, enter or select a value.</span></span> <span data-ttu-id="de41e-119">Se o seu fornecedor já é um participante registrado no seu sistema, você pode usar o botão suspenso e selecioná-los nesse campo e a nova conta de fornecedor herdará as informações de endereço e contato já registradas.</span><span class="sxs-lookup"><span data-stu-id="de41e-119">If your vendor is an already a registered party in your system you can use drop down and select them in this field and the new vendor account will inherit the address and contact information that's already registered.</span></span>
5. <span data-ttu-id="de41e-120">No campo **Grupo**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="de41e-120">In the **Group** field, enter or select a value.</span></span> <span data-ttu-id="de41e-121">O grupo de fornecedores é usado para agrupar fornecedores que têm qualquer dos seguintes parâmetros em comum: condições de pagamento; período de liquidação; contas contábeis de lançamento de estoque, incluindo o grupo de impostos; contas contábeis padrão; códigos de filtro de produto ou configuração de previsão de fornecimento.</span><span class="sxs-lookup"><span data-stu-id="de41e-121">The vendor group is used to group vendors that have any of the following parameters in common: Terms of payment, settle period, inventory posting ledger accounts – including the sales tax group, default ledger accounts, product filter codes, or supply forecast configuration.</span></span>
6. <span data-ttu-id="de41e-122">No campo **Número de funcionários**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="de41e-122">In the **Number of employees** field, enter a number.</span></span>
7. <span data-ttu-id="de41e-123">No campo **Número da organização**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="de41e-123">In the **Organization number** field, type a value.</span></span>

## <a name="add-an-address"></a><span data-ttu-id="de41e-124">Adicionar um endereço</span><span class="sxs-lookup"><span data-stu-id="de41e-124">Add an address</span></span>
1. <span data-ttu-id="de41e-125">Expanda a seção **Endereços**.</span><span class="sxs-lookup"><span data-stu-id="de41e-125">Expand the **Addresses** section.</span></span>
2. <span data-ttu-id="de41e-126">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="de41e-126">Click **Add**.</span></span>
3. <span data-ttu-id="de41e-127">No campo **Finalidade**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="de41e-127">In the **Purpose** field, enter or select a value.</span></span> <span data-ttu-id="de41e-128">Você pode selecionar um ou mais motivos.</span><span class="sxs-lookup"><span data-stu-id="de41e-128">You can select one or more purposes.</span></span> <span data-ttu-id="de41e-129">Esses são usados para selecionar o endereço correto para uma finalidade específica.</span><span class="sxs-lookup"><span data-stu-id="de41e-129">These are used to select the correct address for a given purpose.</span></span> <span data-ttu-id="de41e-130">Por exemplo, se a finalidade for "Nota fiscal", esse endereço será usado ao enviar notas fiscais.</span><span class="sxs-lookup"><span data-stu-id="de41e-130">For example, if the purpose is "Invoice" that address will be used when you send invoices.</span></span>
4. <span data-ttu-id="de41e-131">No campo **Nome ou Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="de41e-131">In the **Name or description** field, type a value.</span></span>
5. <span data-ttu-id="de41e-132">No campo **País/região**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="de41e-132">In the **Country/region** field, enter or select a value.</span></span> <span data-ttu-id="de41e-133">Insira os detalhes do endereço.</span><span class="sxs-lookup"><span data-stu-id="de41e-133">Enter the address details.</span></span> <span data-ttu-id="de41e-134">O país/região selecionado irá determinar os campos que serão apresentados, correspondente ao formato de endereço para o país/região.</span><span class="sxs-lookup"><span data-stu-id="de41e-134">The country/region that you selected will determine the fields you are presented with, corresponding to the address format for the country/region.</span></span> 
6. <span data-ttu-id="de41e-135">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="de41e-135">Click **OK**.</span></span>

## <a name="add-contact-information"></a><span data-ttu-id="de41e-136">Adicionar informações de contato</span><span class="sxs-lookup"><span data-stu-id="de41e-136">Add contact information</span></span>
1. <span data-ttu-id="de41e-137">Expanda a seção **Informações do contato**.</span><span class="sxs-lookup"><span data-stu-id="de41e-137">Expand the **Contact information** section.</span></span>
2. <span data-ttu-id="de41e-138">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="de41e-138">Click **Add**.</span></span>
3. <span data-ttu-id="de41e-139">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="de41e-139">In the **Description** field, type a value.</span></span>
4. <span data-ttu-id="de41e-140">No campo **Tipo**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="de41e-140">In the **Type** field, select an option.</span></span>
5. <span data-ttu-id="de41e-141">No campo **Número/endereço do contato**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="de41e-141">In the **Contact number/address** field, type a value.</span></span> <span data-ttu-id="de41e-142">Você pode selecionar a caixa de seleção Principal se este for o contato primário.</span><span class="sxs-lookup"><span data-stu-id="de41e-142">You can select the Primary check box if this is the primary contact.</span></span>  
6. <span data-ttu-id="de41e-143">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="de41e-143">Click **Save**.</span></span>
7. <span data-ttu-id="de41e-144">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="de41e-144">Close the page.</span></span>
8. <span data-ttu-id="de41e-145">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="de41e-145">Close the page.</span></span>

