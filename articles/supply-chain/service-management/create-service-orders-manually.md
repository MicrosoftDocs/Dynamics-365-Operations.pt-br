---
title: "Criar ordens de serviço manualmente"
description: "Você pode criar ordens de serviço manualmente usando um contrato de serviço ou o formulário **Ordens de serviço**."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 9fbcdaa50a8f13247c13c1885cdb4ab7f5f39a47
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---

# <a name="create-service-orders-manually"></a><span data-ttu-id="3eb87-103">Criar ordens de serviço manualmente</span><span class="sxs-lookup"><span data-stu-id="3eb87-103">Create service orders manually</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="3eb87-104">Você pode criar ordens de serviço manualmente usando um contrato de serviço ou o formulário **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="3eb87-104">You can create service orders manually by using a service agreement or by using the **Service orders** form.</span></span> <span data-ttu-id="3eb87-105">Também é possível criar uma ordem de serviço a partir de um projeto.</span><span class="sxs-lookup"><span data-stu-id="3eb87-105">You can also create a service order from a project.</span></span>

> [!TIP]
> <P><span data-ttu-id="3eb87-106">Você pode usar processos automatizados para criar ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="3eb87-106">You can use automated processes to create service orders.</span></span> 

## <a name="create-a-service-order-manually-from-a-service-agreement"></a><span data-ttu-id="3eb87-107">Criar uma ordem de serviço manualmente a partir de um contrato de serviço</span><span class="sxs-lookup"><span data-stu-id="3eb87-107">Create a service order manually from a service agreement</span></span>

1.  <span data-ttu-id="3eb87-108">Clique em **Gerenciamento de serviços** \> **Comum** \> **Contratos de serviço** \> **Contratos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="3eb87-108">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="3eb87-109">Selecione um contrato de serviço ou crie um novo.</span><span class="sxs-lookup"><span data-stu-id="3eb87-109">Select a service agreement or create a new service agreement.</span></span>

3.  <span data-ttu-id="3eb87-110">Clique na guia **Entregar** e no grupo **Criar** clique em **Ordens de serviço planejadas** para abrir o formulário **Criar ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="3eb87-110">Click the **Deliver** tab and in the **Create** group click **Planned service orders** to open the **Create service orders** form.</span></span>

## <a name="create-a-service-order-manually-in-the-service-orders-form"></a><span data-ttu-id="3eb87-111">Criar uma ordem de serviço manualmente no formulário Ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="3eb87-111">Create a service order manually in the Service orders form</span></span>

1.  <span data-ttu-id="3eb87-112">Clique em **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="3eb87-112">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="3eb87-113">Pressione Ctrl+N para criar uma nova ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="3eb87-113">Press Ctrl+N to create a new service order.</span></span>

3.  <span data-ttu-id="3eb87-114">Criar as linhas de ordem de serviço para a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="3eb87-114">Create service order lines for the service order.</span></span>

> [!NOTE]
> <P><span data-ttu-id="3eb87-115">Se a caixa de seleção <STRONG>Permitir sem contrato de serviço</STRONG> do formulário <STRONG>Parâmetros de gerenciamento de serviços</STRONG> estiver marcada, você poderá lançar as transações a partir das linhas da ordem de serviço sem anexar a ordem de serviço ao contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="3eb87-115">If the <STRONG>Allow without service agreement</STRONG> check box in the <STRONG>Service management parameters</STRONG> form is selected, you can post the transactions from the service order lines without attaching the service order to a service agreement.</span></span> <span data-ttu-id="3eb87-116">Se a caixa de seleção estiver desmarcada, você deverá anexar a ordem de serviço criada manualmente a um projeto antes de lançar as linhas da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="3eb87-116">If the check box is cleared, you must attach the manually created service order to a project before posting the service order lines.</span></span></P>

## <a name="create-a-service-order-from-a-project"></a><span data-ttu-id="3eb87-117">Criar uma ordem de serviço a partir de um projeto</span><span class="sxs-lookup"><span data-stu-id="3eb87-117">Create a service order from a project</span></span>

1.  <span data-ttu-id="3eb87-118">Clique em **Gerenciamento e contabilidade de projeto** \> **Comum** \> **Projetos** \> **Todos os projetos**.</span><span class="sxs-lookup"><span data-stu-id="3eb87-118">Click **Project management and accounting** \> **Common** \> **Projects** \> **All projects**.</span></span>

2.  <span data-ttu-id="3eb87-119">No formulário **Projetos**, no **Painel de Ação**, clique na guia **Gerenciar** \> clique e **Serviço** \> **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="3eb87-119">In the **Projects** form, on the **Action pane**, click the **Manage** tab \> click **Service** \> **Service orders**.</span></span>

3.  <span data-ttu-id="3eb87-120">Siga o procedimento anterior para criar uma ordem de serviço manualmente no formulário **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="3eb87-120">Follow the previous procedure to create a service order manually in the **Service orders** form.</span></span> <span data-ttu-id="3eb87-121">O campo **ID de projeto** exibe a referência do projeto.</span><span class="sxs-lookup"><span data-stu-id="3eb87-121">The **Project ID** field displays the project reference.</span></span>

> [!NOTE]
> <P><span data-ttu-id="3eb87-122">Se a caixa de seleção <STRONG>Permitir sem contrato de serviço</STRONG> do formulário <STRONG>Parâmetros de gerenciamento de serviços</STRONG> estiver marcada, você poderá lançar as transações a partir das linhas da ordem de serviço sem anexar a ordem de serviço ao contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="3eb87-122">If the <STRONG>Allow without service agreement</STRONG> check box in the <STRONG>Service management parameters</STRONG> form is selected, you can post the transactions from the service order lines without attaching the service order to a service agreement.</span></span> <span data-ttu-id="3eb87-123">Se a caixa de seleção estiver desmarcada, você deverá anexar a ordem de serviço criada manualmente a um projeto antes de lançar as linhas da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="3eb87-123">If the check box is cleared, you must attach the manually created service order to a project before posting the service order lines.</span></span></P>

## <a name="create-a-service-order-from-the-sales-order-form"></a><span data-ttu-id="3eb87-124">Criar uma ordem de serviço a partir de um formulário de ordem de Venda</span><span class="sxs-lookup"><span data-stu-id="3eb87-124">Create a service order from the Sales order form</span></span>

<span data-ttu-id="3eb87-125">Você pode criar uma ordem de serviço do formulário **Ordens de venda** usando o assistente **Criar uma nova ordem de serviço com base na ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="3eb87-125">You can create a service order from the **Sales orders** form by using the **Create a new service order based on the sales order** wizard.</span></span>

1.  <span data-ttu-id="3eb87-126">Clique em **Vendas e marketing** \> **Comum** \> **Ordens de venda** \> **Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="3eb87-126">Click **Sales and marketing** \> **Common** \> **Sales orders** \> **All sales orders**.</span></span>

2.  <span data-ttu-id="3eb87-127">Abra a ordem de venda relevante.</span><span class="sxs-lookup"><span data-stu-id="3eb87-127">Open the relevant sales order.</span></span>

3.  <span data-ttu-id="3eb87-128">Na guia **Ordem de venda**, clique em **Ordem de serviço** para iniciar o assistente **Criar uma nova ordem de serviço com base na ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="3eb87-128">On the **Sales order** tab, click **Service order** to start the **Create a new service order based on the sales order** wizard.</span></span>

4.  <span data-ttu-id="3eb87-129">Clique em **Avançar \>**, e conclua as seguintes etapas na página **Selecionar o contrato de ordem de serviço**:</span><span class="sxs-lookup"><span data-stu-id="3eb87-129">Click **Next \>**, and then complete the following steps on the **Select agreement for service order** page:</span></span>
    
      - <span data-ttu-id="3eb87-130">Use o campo **Contrato de serviço** para selecionar o contrato de serviço ao qual a nova ordem de serviço deve ser associada.</span><span class="sxs-lookup"><span data-stu-id="3eb87-130">Use the **Service agreement** field to select the service agreement with which the new service order should be associated.</span></span>
    
      - <span data-ttu-id="3eb87-131">Opcional: Use a lista **ID de projeto** para associar a ordem de serviço a um determinado projeto.</span><span class="sxs-lookup"><span data-stu-id="3eb87-131">Optional: Use the **Project ID** field to associate this service order with a particular project.</span></span>

5.  <span data-ttu-id="3eb87-132">Clique em **Avançar \>**, e conclua as seguintes etapas na página **Criar ordem de serviço**:</span><span class="sxs-lookup"><span data-stu-id="3eb87-132">Click **Next \>**, and then complete the following steps on the **Create service order** page:</span></span>
    
      - <span data-ttu-id="3eb87-133">Insira uma data e hora para que a chamada de serviço seja iniciada no campo **Hora de serviço preferencial**.</span><span class="sxs-lookup"><span data-stu-id="3eb87-133">Enter a date and time for the service call to begin in the **Preferred service time** field.</span></span>
    
      - <span data-ttu-id="3eb87-134">Opcional: Modifique o texto no campo **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="3eb87-134">Optional: Modify the text in the **Description** field.</span></span> <span data-ttu-id="3eb87-135">Por padrão, este campo contem a descrição do contrato de serviço selecionado na página anterior.</span><span class="sxs-lookup"><span data-stu-id="3eb87-135">By default, this field contains the description of the service agreement that you selected on the previous page.</span></span>
    
      - <span data-ttu-id="3eb87-136">No campo **Responsável**, selecione a ID do funcionário responsável pelo contrato e, se souber, a ID do técnico preferido do cliente para a chamada de serviço.</span><span class="sxs-lookup"><span data-stu-id="3eb87-136">In the **Responsible** field, select the ID of the employee who is responsible for the agreement, and if you know what it is, enter the ID of the customer's preferred technician for the service call.</span></span>
    
      - <span data-ttu-id="3eb87-137">No campo **ID de contato**, selecione a pessoa na empresa do cliente que deve ser contatada referente a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="3eb87-137">In the **Contact ID** field, select the person in the customer's company who should be contacted regarding this service order.</span></span>

6.  <span data-ttu-id="3eb87-138">Clique em **Avançar \>** e depois em **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="3eb87-138">Click **Next \>**, and then click **Finish**.</span></span>


## <a name="see-also"></a><span data-ttu-id="3eb87-139">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3eb87-139">See also</span></span>

[<span data-ttu-id="3eb87-140">Ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="3eb87-140">Service orders</span></span>](service-orders.md)

[<span data-ttu-id="3eb87-141">Criar ordens de serviço automaticamente</span><span class="sxs-lookup"><span data-stu-id="3eb87-141">Create service orders automatically</span></span>](create-service-orders-automatically.md)

<span data-ttu-id="3eb87-142">[Criar ordens de serviço (formulário de classe)](https://technet.microsoft.com/en-us/library/aa553901\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="3eb87-142">[Create service orders (class form)](https://technet.microsoft.com/en-us/library/aa553901\(v=ax.60\))</span></span> 


