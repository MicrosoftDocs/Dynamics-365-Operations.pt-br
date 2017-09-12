--- 
title: " Criar canais online e definir atributos de canal"
description: "Este procedimento orienta na criação de um novo canal online e sua adição à hierarquia da organização."
author: jashanno
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 748c536692043a4cfe7d8b087066e12b3e7ddadc
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="create-online-channels-and-define-channel-attributes"></a><span data-ttu-id="5573c-103"> Criar canais online e definir atributos de canal</span><span class="sxs-lookup"><span data-stu-id="5573c-103">Create online channels and define channel attributes</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="5573c-104">Este procedimento orienta na criação de um novo canal online e sua adição à hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="5573c-104">This procedure walks through creating a new online channel and adding it to the organization hierarchy.</span></span> <span data-ttu-id="5573c-105">É necessário criar a hierarquia da organização antes que você possa criar um novo canal online.</span><span class="sxs-lookup"><span data-stu-id="5573c-105">You must create the organization hierarchy before you can create a new online channel.</span></span> <span data-ttu-id="5573c-106">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="5573c-106">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-new-online-channel"></a><span data-ttu-id="5573c-107">Criar um novo canal online</span><span class="sxs-lookup"><span data-stu-id="5573c-107">Create a new online channel</span></span>
1. <span data-ttu-id="5573c-108">Vá para Varejo e comércio > Canais > Lojas online.</span><span class="sxs-lookup"><span data-stu-id="5573c-108">Go to Retail and commerce > Channels > Online stores.</span></span>
2. <span data-ttu-id="5573c-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5573c-109">Click New.</span></span>
3. <span data-ttu-id="5573c-110">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="5573c-110">In the Name field, type a value.</span></span>
4. <span data-ttu-id="5573c-111">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5573c-111">In the Warehouse field, enter or select a value.</span></span>
5. <span data-ttu-id="5573c-112">No campo Fuso horário da loja, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="5573c-112">In the Store time zone field, select an option.</span></span>
6. <span data-ttu-id="5573c-113">No campo Cliente padrão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5573c-113">In the Default customer field, enter or select a value.</span></span>
7. <span data-ttu-id="5573c-114">No campo Catálogo de endereços do cliente, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5573c-114">In the Customer address book field, enter or select a value.</span></span>
8. <span data-ttu-id="5573c-115">No campo Condições de pagamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5573c-115">In the Terms of payment field, enter or select a value.</span></span>
9. <span data-ttu-id="5573c-116">No campo Condições de pagamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5573c-116">In the Method of payment field, enter or select a value.</span></span>
10. <span data-ttu-id="5573c-117">No campo Notificação por email, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5573c-117">In the Email notification profile field, enter or select a value.</span></span>
11. <span data-ttu-id="5573c-118">Expanda a seção Dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="5573c-118">Expand the Financial dimensions section.</span></span>
12. <span data-ttu-id="5573c-119">No campo Unidade de negócios, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5573c-119">In the BusinessUnit field, enter or select a value.</span></span>
    * <span data-ttu-id="5573c-120">De modo semelhante, defina o valor para todas as outras dimensões padrão.</span><span class="sxs-lookup"><span data-stu-id="5573c-120">Similarly set the value for all the other default dimensions.</span></span>  
13. <span data-ttu-id="5573c-121">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5573c-121">Click Save.</span></span>

## <a name="add-the-online-channel-to-organization-hierarchy"></a><span data-ttu-id="5573c-122">Adicionar o canal online à hierarquia da organização</span><span class="sxs-lookup"><span data-stu-id="5573c-122">Add the online channel to organization hierarchy</span></span>
1. <span data-ttu-id="5573c-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="5573c-123">Close the page.</span></span>
2. <span data-ttu-id="5573c-124">Vá para Administração da organização > Organizações > Hierarquias da organização.</span><span class="sxs-lookup"><span data-stu-id="5573c-124">Go to Organization administration > Organizations > Organization hierarchies.</span></span>
3. <span data-ttu-id="5573c-125">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="5573c-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="5573c-126">Clique em Exibir.</span><span class="sxs-lookup"><span data-stu-id="5573c-126">Click View.</span></span>
5. <span data-ttu-id="5573c-127">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="5573c-127">Click Edit.</span></span>
    * <span data-ttu-id="5573c-128">Você pode selecionar qualquer nó da hierarquia no qual deseja inserir o novo canal.</span><span class="sxs-lookup"><span data-stu-id="5573c-128">You can select any hierarchy node under which you want to insert the new channel.</span></span>  
6. <span data-ttu-id="5573c-129">Clique em Inserir.</span><span class="sxs-lookup"><span data-stu-id="5573c-129">Click Insert.</span></span>
7. <span data-ttu-id="5573c-130">Clique em Canal de varejo.</span><span class="sxs-lookup"><span data-stu-id="5573c-130">Click Retail channel.</span></span>
8. <span data-ttu-id="5573c-131">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="5573c-131">Click OK.</span></span>
9. <span data-ttu-id="5573c-132">Clique em Publicar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="5573c-132">Click Publish to open the drop dialog.</span></span>
10. <span data-ttu-id="5573c-133">No campo de data efetiva, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="5573c-133">In the Effective date field, enter a date and time.</span></span>
11. <span data-ttu-id="5573c-134">Clique em Publicar.</span><span class="sxs-lookup"><span data-stu-id="5573c-134">Click Publish.</span></span>


