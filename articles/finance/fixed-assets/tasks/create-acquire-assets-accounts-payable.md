---
title: Criar e adquirir ativos de contas a pagar
description: Esta guia mostrará a criação e a aquisição de um ativo fixo com o processo de compra.
author: saraschi2
manager: AnnBe
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, VendInvoiceWorkspace, VendEditInvoice, VendTableLookup, InventItemIdLookupSimple, AssetTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 025639e6e5bdc6b95e9c496f11f29ed8ec8d388c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176389"
---
# <a name="create-and-acquire-assets-from-accounts-payable"></a><span data-ttu-id="efd8a-103">Criar e adquirir ativos de contas a pagar</span><span class="sxs-lookup"><span data-stu-id="efd8a-103">Create and acquire assets from Accounts payable</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="efd8a-104">Esta guia mostrará a criação e a aquisição de um ativo fixo com o processo de compra.</span><span class="sxs-lookup"><span data-stu-id="efd8a-104">This task guide will walk through creation and acquisition of a fixed asset with the purchasing process.</span></span>  <span data-ttu-id="efd8a-105">Usa os caixeiros de contador e contas a pagar e a empresa USMF de demonstração.</span><span class="sxs-lookup"><span data-stu-id="efd8a-105">It uses the Accountant and Accounts payable clerks and the demo company USMF .</span></span>


## <a name="set-fixed-assets-parameters"></a><span data-ttu-id="efd8a-106">Definir parâmetros dos ativos fixos</span><span class="sxs-lookup"><span data-stu-id="efd8a-106">Set Fixed assets parameters</span></span>
1. <span data-ttu-id="efd8a-107">No **Painel de Navegação**, vá para **Módulos > Ativos fixos > Configuração > Parâmetros de ativos fixos**.</span><span class="sxs-lookup"><span data-stu-id="efd8a-107">In the **Navigation pane**, go to **Modules > Fixed assets > Setup > Fixed assets parameters**.</span></span>
2. <span data-ttu-id="efd8a-108">Expanda a Guia Rápida **Ordens de compra**.</span><span class="sxs-lookup"><span data-stu-id="efd8a-108">Expand the **Purchase orders** fastTab.</span></span>
3. <span data-ttu-id="efd8a-109">Marque a caixa de seleção **Permitir a aquisição de ativos de Compras**.</span><span class="sxs-lookup"><span data-stu-id="efd8a-109">Check the **Allow asset acquisition from Purchasing** checkbox.</span></span>
4. <span data-ttu-id="efd8a-110">Marque a caixa de seleção **Criar um ativo durante o recebimento de produtos ou o lançamento de fatura**.</span><span class="sxs-lookup"><span data-stu-id="efd8a-110">Check the **Create asset during product receipt or invoice posting** checkbox.</span></span>

## <a name="create-a-new-vendor-invoice"></a><span data-ttu-id="efd8a-111">Criar uma nova fatura de fornecedor</span><span class="sxs-lookup"><span data-stu-id="efd8a-111">Create a new vendor invoice</span></span>
1. <span data-ttu-id="efd8a-112">No **Painel de Navegação**, vá para **Módulos > Contas a pagar > Espaços de trabalho > Entrada de fatura de fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="efd8a-112">In the **Navigation pane**, go to **Modules > Accounts payable > Workspaces > Vendor invoice entry**.</span></span>
2. <span data-ttu-id="efd8a-113">Clique em **Nova fatura de fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="efd8a-113">Click **New vendor invoice**.</span></span>
3. <span data-ttu-id="efd8a-114">No campo **Conta de fatura**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="efd8a-114">In the **Invoice account** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="efd8a-115">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="efd8a-115">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="efd8a-116">No campo **Número**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="efd8a-116">In the **Number** field, type a value.</span></span>
6. <span data-ttu-id="efd8a-117">No campo **Data de lançamento**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="efd8a-117">In the **Posting date** field, enter a date.</span></span>
7. <span data-ttu-id="efd8a-118">Clique em **Adicionar linha**.</span><span class="sxs-lookup"><span data-stu-id="efd8a-118">Click **Add line**.</span></span>
8. <span data-ttu-id="efd8a-119">No campo **Número do item**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="efd8a-119">In the **Item number** field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="efd8a-120">Os itens não estocados ou as categorias de aquisição podem ser usados para aquisições de ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="efd8a-120">Either non-stocked items or procurement categories can be used for fixed asset acquisition.</span></span>  
9. <span data-ttu-id="efd8a-121">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="efd8a-121">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="efd8a-122">No campo **Quantidade.**, insira um número</span><span class="sxs-lookup"><span data-stu-id="efd8a-122">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="efd8a-123">Uma linha da nota fiscal criará somente um ativo fixo, independentemente da quantidade.</span><span class="sxs-lookup"><span data-stu-id="efd8a-123">One invoice line will only create one fixed asset, regardless of quantity.</span></span> <span data-ttu-id="efd8a-124">O valor do campo de quantidade da nota fiscal será transferido para a quantidade do ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="efd8a-124">The invoice quantity field value will be transferred to the fixed asset quantity.</span></span>  
11. <span data-ttu-id="efd8a-125">No campo **Preço unitário**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="efd8a-125">In the **Unit price** field, enter a number.</span></span>
12. <span data-ttu-id="efd8a-126">Expanda a Guia Rápida **Detalhes da linha**.</span><span class="sxs-lookup"><span data-stu-id="efd8a-126">Expand the **Line details** fastTab.</span></span>
13. <span data-ttu-id="efd8a-127">Clique na guia **Ativos fixos**.</span><span class="sxs-lookup"><span data-stu-id="efd8a-127">Click the **Fixed assets** tab.</span></span>
14. <span data-ttu-id="efd8a-128">Marque a caixa de seleção **Criar um novo ativo fixo**.</span><span class="sxs-lookup"><span data-stu-id="efd8a-128">Check the **Create a new fixed asset** checkbox.</span></span>
15. <span data-ttu-id="efd8a-129">No campo **Grupo de ativo fixo**, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="efd8a-129">In the **Fixed asset group** field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="efd8a-130">Na lista, selecione o grupo de ativos fixos a ser usado quando criar o novo ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="efd8a-130">In the list, select the fixed asset group to be used when creating the new fixed asset.</span></span>
17. <span data-ttu-id="efd8a-131">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="efd8a-131">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="efd8a-132">Clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="efd8a-132">Click **Post**.</span></span> <span data-ttu-id="efd8a-133">O ativo fixo será criado e adquirido quando a nota fiscal for lançada.</span><span class="sxs-lookup"><span data-stu-id="efd8a-133">The fixed asset will be created and acquired when the invoice is posted.</span></span>  

