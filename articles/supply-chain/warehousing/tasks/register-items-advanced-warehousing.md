--- 
title: "Registrar itens para um item avançado com armazenamento habilitado usando um diário de entrada de itens"
description: "Este procedimento mostra como registrar itens usando o diário de entrada de itens quando estiver usando processos de gerenciamento de depósito avançado."
author: BibiSp
manager: AnnBe
ms.date: 02/12/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 09d5d61a1950a5ab341d3bb3c814b6985d5e910e
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---
# <a name="register-items-for-an-advanced-warehousing-enabled-item-using-an-item-arrival-journal"></a><span data-ttu-id="ecd9f-103">Registrar itens para um item avançado com armazenamento habilitado usando um diário de entrada de itens</span><span class="sxs-lookup"><span data-stu-id="ecd9f-103">Register items for an advanced warehousing enabled item using an item arrival journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ecd9f-104">Este procedimento mostra como registrar itens usando o diário de entrada de itens quando estiver usando processos de gerenciamento de depósito avançado.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-104">This procedure shows you how to register items using the item arrival journal when you are using advanced warehouse management processes.</span></span> <span data-ttu-id="ecd9f-105">Normalmente isso é feito por um vendedor de remessa.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-105">This would usually be done by a receiving clerk.</span></span> 

<span data-ttu-id="ecd9f-106">Você pode executar esse procedimento na empresa de dados demonstrativos USMF, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-106">You can run this procedure in demo data company USMF, or on your own data.</span></span> <span data-ttu-id="ecd9f-107">Você precisa ter uma ordem de compra confirmada com uma linha de ordem de compra aberta antes de dar início a este guia.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-107">You need to have a confirmed purchase order with an open purchase order line before you start this guide.</span></span> <span data-ttu-id="ecd9f-108">O item da linha deve ser armazenado, e não deve usar grades de produto, e não deve ter dimensões de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-108">The item on the line must be stocked, and it must not use product variants, and must not have tracking dimensions.</span></span> <span data-ttu-id="ecd9f-109">E o item precisa estar associado a um grupo de dimensões de armazenamento habilitado para processo de gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-109">And the item needs to be associated with a warehouse management process enabled storage dimension group.</span></span> <span data-ttu-id="ecd9f-110">O depósito usado deve ser habilitado para processos de gerenciamento de depósito, e a localização usada para recebimento deve ser controlada por placa de licença.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-110">The warehouse that’s used must be enabled for warehouse management processes and the location that you use for receiving must be license plate controlled.</span></span> <span data-ttu-id="ecd9f-111">Se estiver utilizando USMF, você pode usar a conta da companhia 1001, depósito 51 e item M9200 para criar sua OC.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-111">If you’re using USMF, you can use company account 1001, Warehouse 51, and item M9200 to create your PO.</span></span> 

<span data-ttu-id="ecd9f-112">Juntamente com o número da ordem de compra criada, anote o número do item e o site que você usou para sua linha de ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-112">Make a note of the number of the purchase order that you create, and also note the item number and the site that you used for your purchase order line.</span></span>


## <a name="create-an-item-arrival-journal-header"></a><span data-ttu-id="ecd9f-113">Criar um cabeçalho de diário de entrada de itens.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-113">Create an item arrival journal header</span></span>
1. <span data-ttu-id="ecd9f-114">Vá para Entrada de item.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-114">Go to Item arrival.</span></span>
2. <span data-ttu-id="ecd9f-115">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-115">Click New.</span></span>
3. <span data-ttu-id="ecd9f-116">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-116">In the Name field, type a value.</span></span>
    * <span data-ttu-id="ecd9f-117">Se você estiver usando USMF, você pode digitar WHS.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-117">If you are using USMF, you can type WHS.</span></span> <span data-ttu-id="ecd9f-118">Se você estiver usando outros dados, o diário cujo nome que você escolheu precisa ter as seguintes propriedades: O local de separação de verificação deve ser definido como nenhum, e o gerenciamento de quarentena deve ser definido como não.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-118">If you’re using other data, the journal whose name you choose has to have the following properties: Check picking location must be set to No, and Quarantine management must be set to No.</span></span>  
4. <span data-ttu-id="ecd9f-119">No campo Número, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-119">In the Number field, type a value.</span></span>
5. <span data-ttu-id="ecd9f-120">No campo Local, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-120">In the Site field, type a value.</span></span>
    * <span data-ttu-id="ecd9f-121">Selecione o site que você usou para sua ordem de compra aqui.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-121">Select the site that you used for your purchase order line.</span></span> <span data-ttu-id="ecd9f-122">Isso servirá como um valor padrão para todas as linhas do diário.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-122">This will serve as a default value, which will default to all lines in the journal.</span></span> <span data-ttu-id="ecd9f-123">Se você usou o depósito 51 na USMF, selecione o site 5.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-123">If you used warehouse 51 in USMF, choose site 5.</span></span>  
6. <span data-ttu-id="ecd9f-124">No campo Depósito, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-124">In the Warehouse field, type a value.</span></span>
    * <span data-ttu-id="ecd9f-125">Selecione um depósito válido para o site que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-125">Select a valid warehouse for the site that you’ve selected.</span></span> <span data-ttu-id="ecd9f-126">Isso servirá como um valor padrão para todas as linhas do diário.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-126">This will serve as a default value, which will default to all lines in the journal.</span></span> <span data-ttu-id="ecd9f-127">Se você estiver usando os valores do exemplo na USMF, selecione 51.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-127">If you’re using the example values in USMF, select 51.</span></span>  
7. <span data-ttu-id="ecd9f-128">No campo Localização, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-128">In the Location field, type a value.</span></span>
    * <span data-ttu-id="ecd9f-129">Selecione uma localização válida no depósito que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-129">Select a valid location in the warehouse that you’ve selected.</span></span> <span data-ttu-id="ecd9f-130">A localização precisa estar associada a um perfil de localização, o que é controlado por placa de licença.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-130">The location has to be associated with a location profile, which is license plate controlled.</span></span> <span data-ttu-id="ecd9f-131">Isso servirá como um valor padrão para todas as linhas do diário.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-131">This will serve as a default value, which will default to all lines in the journal.</span></span> <span data-ttu-id="ecd9f-132">Se você estiver usando os valores do exemplo na USMF, selecione Bulk-008.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-132">If you’re using the example values in USMF, select Bulk-008.</span></span>  
8. <span data-ttu-id="ecd9f-133">Clique com o botão direito do mouse na seta suspensa no campo Placa de licença e selecione Exibir detalhes.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-133">Right-click on the drop-down arrow in the License plate field and then select View details.</span></span>
9. <span data-ttu-id="ecd9f-134">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-134">Click New.</span></span>
10. <span data-ttu-id="ecd9f-135">No campo Placa de licença, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-135">In the License plate field, type a value.</span></span>
    * <span data-ttu-id="ecd9f-136">Anote o valor.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-136">Make a note of the value.</span></span>  
11. <span data-ttu-id="ecd9f-137">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-137">Click Save.</span></span>
12. <span data-ttu-id="ecd9f-138">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-138">Close the page.</span></span>
13. <span data-ttu-id="ecd9f-139">No campo Placa de licença, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-139">In the License plate field, type a value.</span></span>
    * <span data-ttu-id="ecd9f-140">Insira o valor da placa de licença que acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-140">Enter the value of the license plate that you just created.</span></span> <span data-ttu-id="ecd9f-141">Isso servirá como um valor padrão para todas as linhas do diário.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-141">This will serve as a default value, which will default to all lines in the journal.</span></span>  
14. <span data-ttu-id="ecd9f-142">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-142">Click OK.</span></span>

## <a name="add-a-line"></a><span data-ttu-id="ecd9f-143">Adicionar uma linha</span><span class="sxs-lookup"><span data-stu-id="ecd9f-143">Add a line</span></span>
1. <span data-ttu-id="ecd9f-144">Clique em Adicionar linha.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-144">Click Add line.</span></span>
2. <span data-ttu-id="ecd9f-145">No campo Número de item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-145">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="ecd9f-146">Insira o número do item que usou na linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-146">Enter the item number that you used on the purchase order line.</span></span>  
3. <span data-ttu-id="ecd9f-147">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-147">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="ecd9f-148">Insira a quantidade que deseja registrar.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-148">Enter the quantity that you want to register.</span></span>  
    * <span data-ttu-id="ecd9f-149">O campo Data determina a data na qual a quantidade disponível desse item será registrada no estoque.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-149">The Date field determines the date on which the on-hand quantity of this item will be registered in the inventory.</span></span>  
    * <span data-ttu-id="ecd9f-150">O ID do lote será preenchido pelo sistema se puder ser identificado somente nas informações fornecidas.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-150">The lot ID will be populated by the system if it can be uniquely identified from the information provided.</span></span> <span data-ttu-id="ecd9f-151">Caso contrário, você terá que adicioná-lo manualmente.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-151">Otherwise you will have to add this manually.</span></span> <span data-ttu-id="ecd9f-152">Trata-se de um campo obrigatório, que vincula esse registro a uma linha de documento de origem específica.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-152">This is a mandatory field, which links this registration to a specific source document line.</span></span>  

## <a name="complete-the-registration"></a><span data-ttu-id="ecd9f-153">Concluir o registro</span><span class="sxs-lookup"><span data-stu-id="ecd9f-153">Complete the registration</span></span>
1. <span data-ttu-id="ecd9f-154">Clique em Validar.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-154">Click Validate.</span></span>
    * <span data-ttu-id="ecd9f-155">Isso verifica se o diário está pronto para ser lançado.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-155">This checks that the journal is ready to be posted.</span></span> <span data-ttu-id="ecd9f-156">Se a validação falhar, você precisará corrigir os erros antes de poder lançar o diário.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-156">If the validation fails you will need to fix the errors before you can post the journal.</span></span>  
2. <span data-ttu-id="ecd9f-157">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-157">Click OK.</span></span>
    * <span data-ttu-id="ecd9f-158">Após clicar em OK, verifique a mensagem.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-158">After you clicked OK, check the message.</span></span> <span data-ttu-id="ecd9f-159">Deve haver uma mensagem informando que o diário está OK.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-159">There should be a message saying that the journal is OK.</span></span>  
3. <span data-ttu-id="ecd9f-160">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-160">Click Post.</span></span>
4. <span data-ttu-id="ecd9f-161">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-161">Click OK.</span></span>
    * <span data-ttu-id="ecd9f-162">Após clicar em OK, verifique a barra de mensagem.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-162">After you have clicked OK, check the message bar.</span></span> <span data-ttu-id="ecd9f-163">Deve haver uma mensagem informando que a operação foi concluída.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-163">There should be a message saying that the operation completed.</span></span>  
5. <span data-ttu-id="ecd9f-164">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ecd9f-164">Close the page.</span></span>


