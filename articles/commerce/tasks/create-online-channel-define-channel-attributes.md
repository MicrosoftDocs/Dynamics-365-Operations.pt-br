---
title: Criar canal online e definir atributos do canal
description: Este procedimento orienta na criação de um novo canal online e sua adição à hierarquia da organização.
author: jashanno
manager: AnnBe
ms.date: 06/04/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailSPOnlineStoreDetailPage, SysLookupMultiSelectGrid, DimensionLookup, OMHierarchyManager, HierarchyDesigner, OMNodeSelection, HierarchyPublishAndCloseForm
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8f85a74e44be28452f5d892f1875d74261f9dbe3
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215427"
---
# <a name="create-online-channel-and-define-channel-attributes"></a><span data-ttu-id="97c65-103">Criar canal online e definir atributos do canal</span><span class="sxs-lookup"><span data-stu-id="97c65-103">Create online channel and define channel attributes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="97c65-104">Este procedimento orienta na criação de um novo canal online e sua adição à hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="97c65-104">This procedure walks through creating a new online channel and adding it to the organization hierarchy.</span></span> <span data-ttu-id="97c65-105">É necessário criar a hierarquia da organização antes que você possa criar um novo canal online.</span><span class="sxs-lookup"><span data-stu-id="97c65-105">You must create the organization hierarchy before you can create a new online channel.</span></span> <span data-ttu-id="97c65-106">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="97c65-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-new-online-channel"></a><span data-ttu-id="97c65-107">Criar um novo canal online</span><span class="sxs-lookup"><span data-stu-id="97c65-107">Create a new online channel</span></span>
1. <span data-ttu-id="97c65-108">Vá para Varejo e Comércio > Canais > Lojas online.</span><span class="sxs-lookup"><span data-stu-id="97c65-108">Go to Retail and Commerce > Channels > Online stores.</span></span>
2. <span data-ttu-id="97c65-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="97c65-109">Click New.</span></span>
3. <span data-ttu-id="97c65-110">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="97c65-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="97c65-111">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="97c65-111">In the Warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="97c65-112">No campo Fuso horário da loja, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="97c65-112">In the Store time zone field, select an option.</span></span>
6. <span data-ttu-id="97c65-113">No campo Cliente padrão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="97c65-113">In the Default customer field, enter or select a value.</span></span>
7. <span data-ttu-id="97c65-114">No campo Catálogo de endereços do cliente, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="97c65-114">In the Customer address book field, enter or select a value.</span></span>
8. <span data-ttu-id="97c65-115">No campo Condições de pagamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="97c65-115">In the Terms of payment field, enter or select a value.</span></span>
9. <span data-ttu-id="97c65-116">No campo Condições de pagamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="97c65-116">In the Method of payment field, enter or select a value.</span></span>
10. <span data-ttu-id="97c65-117">No campo Notificação por email, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="97c65-117">In the Email notification profile field, enter or select a value.</span></span>
11. <span data-ttu-id="97c65-118">Expanda a seção Dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="97c65-118">Expand the Financial dimensions section.</span></span>
12. <span data-ttu-id="97c65-119">No campo Unidade de negócios, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="97c65-119">In the BusinessUnit field, enter or select a value.</span></span>
    * <span data-ttu-id="97c65-120">De modo semelhante, defina o valor para todas as outras dimensões padrão.</span><span class="sxs-lookup"><span data-stu-id="97c65-120">Similarly set the value for all the other default dimensions.</span></span>  
13. <span data-ttu-id="97c65-121">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="97c65-121">Click Save.</span></span>

## <a name="add-the-online-channel-to-organization-hierarchy"></a><span data-ttu-id="97c65-122">Adicionar o canal online à hierarquia da organização</span><span class="sxs-lookup"><span data-stu-id="97c65-122">Add the online channel to organization hierarchy</span></span>
1. <span data-ttu-id="97c65-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="97c65-123">Close the page.</span></span>
2. <span data-ttu-id="97c65-124">Vá para Administração da organização > Organizações > Hierarquias da organização.</span><span class="sxs-lookup"><span data-stu-id="97c65-124">Go to Organization administration > Organizations > Organization hierarchies.</span></span>
3. <span data-ttu-id="97c65-125">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="97c65-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="97c65-126">Clique em Exibir.</span><span class="sxs-lookup"><span data-stu-id="97c65-126">Click View.</span></span>
5. <span data-ttu-id="97c65-127">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="97c65-127">Click Edit.</span></span>
    * <span data-ttu-id="97c65-128">Você pode selecionar qualquer nó da hierarquia no qual deseja inserir o novo canal.</span><span class="sxs-lookup"><span data-stu-id="97c65-128">You can select any hierarchy node under which you want to insert the new channel.</span></span>  
6. <span data-ttu-id="97c65-129">Clique em Inserir.</span><span class="sxs-lookup"><span data-stu-id="97c65-129">Click Insert.</span></span>
7. <span data-ttu-id="97c65-130">Clique em Canal de comércio.</span><span class="sxs-lookup"><span data-stu-id="97c65-130">Click Commerce channel.</span></span>
8. <span data-ttu-id="97c65-131">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="97c65-131">Click OK.</span></span>
9. <span data-ttu-id="97c65-132">Clique em Publicar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="97c65-132">Click Publish to open the drop dialog.</span></span>
10. <span data-ttu-id="97c65-133">No campo de data efetiva, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="97c65-133">In the Effective date field, enter a date and time.</span></span>
11. <span data-ttu-id="97c65-134">Clique em Publicar.</span><span class="sxs-lookup"><span data-stu-id="97c65-134">Click Publish.</span></span>

## <a name="configure-orders-for-near-real-time-notification"></a><span data-ttu-id="97c65-135">Configurar ordens para notificação quase em tempo real</span><span class="sxs-lookup"><span data-stu-id="97c65-135">Configure orders for near real-time notification</span></span>
1. <span data-ttu-id="97c65-136">Vá para Varejo e Comércio > Configuração da sede > Parâmetros > Parâmetros de comércio.</span><span class="sxs-lookup"><span data-stu-id="97c65-136">Go to Retail and Commerce  > Headquarters setup > Parameters > Commerce parameters.</span></span>
2. <span data-ttu-id="97c65-137">Definir Usar serviço em tempo real para criação de ordens de comércio eletrônico como "Sim".</span><span class="sxs-lookup"><span data-stu-id="97c65-137">Set Use realtime service for eCommerce order creation to "Yes".</span></span>
3. <span data-ttu-id="97c65-138">Execute a agenda de distribuição 1070 para sincronizar alterações no banco de dados do canal.</span><span class="sxs-lookup"><span data-stu-id="97c65-138">Run the 1070 distribution schedule to sync changes to the channel database.</span></span> 




[!INCLUDE[footer-include](../../includes/footer-banner.md)]