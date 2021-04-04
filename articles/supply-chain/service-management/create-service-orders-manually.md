---
title: Criar ordens de serviço manualmente
description: Você pode criar ordens de serviço manualmente usando um contrato de serviço ou o formulário **Ordens de serviço**.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 72b600bc59119a6304fa043240a34051435f8691
ms.sourcegitcommit: 34b8f6f5c6134b7b97a9fb41d0b2e63215c67062
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5470944"
---
# <a name="create-service-orders-manually"></a><span data-ttu-id="24dbc-103">Criar ordens de serviço manualmente</span><span class="sxs-lookup"><span data-stu-id="24dbc-103">Create service orders manually</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="24dbc-104">Você pode criar ordens de serviço manualmente usando um contrato de serviço ou o formulário **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="24dbc-104">You can create service orders manually by using a service agreement or by using the **Service orders** form.</span></span> <span data-ttu-id="24dbc-105">Também é possível criar uma ordem de serviço a partir de um projeto.</span><span class="sxs-lookup"><span data-stu-id="24dbc-105">You can also create a service order from a project.</span></span>

> [!TIP]
> <P><span data-ttu-id="24dbc-106">Você pode usar processos automatizados para criar ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="24dbc-106">You can use automated processes to create service orders.</span></span> 

## <a name="create-a-service-order-manually-from-a-service-agreement"></a><span data-ttu-id="24dbc-107">Criar uma ordem de serviço manualmente a partir de um contrato de serviço</span><span class="sxs-lookup"><span data-stu-id="24dbc-107">Create a service order manually from a service agreement</span></span>

1.  <span data-ttu-id="24dbc-108">Selecione **Gerenciamento de serviços** \> **Comum** \> **Contratos de serviço** \> **Contratos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="24dbc-108">Select **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="24dbc-109">Selecione um contrato de serviço ou crie um novo.</span><span class="sxs-lookup"><span data-stu-id="24dbc-109">Select a service agreement or create a new service agreement.</span></span>

3.  <span data-ttu-id="24dbc-110">Selecione a guia **Entregar** e, no grupo **Criar**, selecione **Ordens de serviço planejadas** para abrir o formulário **Criar ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="24dbc-110">Select the **Deliver** tab and in the **Create** group select **Planned service orders** to open the **Create service orders** form.</span></span>

## <a name="create-a-service-order-manually-in-the-service-orders-form"></a><span data-ttu-id="24dbc-111">Criar uma ordem de serviço manualmente no formulário Ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="24dbc-111">Create a service order manually in the Service orders form</span></span>

1.  <span data-ttu-id="24dbc-112">Selecione **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="24dbc-112">Select **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="24dbc-113">Selecione **Novo** para criar uma nova ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="24dbc-113">Select **New** to create a new service order.</span></span>

3.  <span data-ttu-id="24dbc-114">Criar as linhas de ordem de serviço para a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="24dbc-114">Create service order lines for the service order.</span></span>

> [!NOTE]
> <P><span data-ttu-id="24dbc-115">Se a caixa de seleção <STRONG>Permitir sem contrato de serviço</STRONG> do formulário <STRONG>Parâmetros de gerenciamento de serviços</STRONG> estiver marcada, você poderá lançar as transações a partir das linhas da ordem de serviço sem anexar a ordem de serviço ao contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="24dbc-115">If the <STRONG>Allow without service agreement</STRONG> check box in the <STRONG>Service management parameters</STRONG> form is selected, you can post the transactions from the service order lines without attaching the service order to a service agreement.</span></span> <span data-ttu-id="24dbc-116">Se a caixa de seleção estiver desmarcada, você deverá anexar a ordem de serviço criada manualmente a um projeto antes de lançar as linhas da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="24dbc-116">If the check box is cleared, you must attach the manually created service order to a project before posting the service order lines.</span></span></P>

## <a name="create-a-service-order-from-a-project"></a><span data-ttu-id="24dbc-117">Criar uma ordem de serviço a partir de um projeto</span><span class="sxs-lookup"><span data-stu-id="24dbc-117">Create a service order from a project</span></span>

1.  <span data-ttu-id="24dbc-118">Acesse **Gerenciamento e contabilidade de projeto** \> **Comum** \> **Projetos** \> **Todos os projetos**.</span><span class="sxs-lookup"><span data-stu-id="24dbc-118">Go to **Project management and accounting** \> **Common** \> **Projects** \> **All projects**.</span></span>

2.  <span data-ttu-id="24dbc-119">No formulário **Projetos**, no **Painel de Ações**, selecione a guia **Gerenciar** \> selecione **Serviço** \> **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="24dbc-119">In the **Projects** form, on the **Action Pane**, select the **Manage** tab \> select **Service** \> **Service orders**.</span></span>

3.  <span data-ttu-id="24dbc-120">Siga o procedimento anterior para criar uma ordem de serviço manualmente no formulário **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="24dbc-120">Follow the previous procedure to create a service order manually in the **Service orders** form.</span></span> <span data-ttu-id="24dbc-121">O campo **ID de projeto** exibe a referência do projeto.</span><span class="sxs-lookup"><span data-stu-id="24dbc-121">The **Project ID** field displays the project reference.</span></span>

> [!NOTE]
> <P><span data-ttu-id="24dbc-122">Se a caixa de seleção <STRONG>Permitir sem contrato de serviço</STRONG> do formulário <STRONG>Parâmetros de gerenciamento de serviços</STRONG> estiver marcada, você poderá lançar as transações a partir das linhas da ordem de serviço sem anexar a ordem de serviço ao contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="24dbc-122">If the <STRONG>Allow without service agreement</STRONG> check box in the <STRONG>Service management parameters</STRONG> form is selected, you can post the transactions from the service order lines without attaching the service order to a service agreement.</span></span> <span data-ttu-id="24dbc-123">Se a caixa de seleção estiver desmarcada, você deverá anexar a ordem de serviço criada manualmente a um projeto antes de lançar as linhas da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="24dbc-123">If the check box is cleared, you must attach the manually created service order to a project before posting the service order lines.</span></span></P>

## <a name="create-a-service-order-from-the-sales-order-form"></a><span data-ttu-id="24dbc-124">Criar uma ordem de serviço a partir de um formulário de ordem de Venda</span><span class="sxs-lookup"><span data-stu-id="24dbc-124">Create a service order from the Sales order form</span></span>

<span data-ttu-id="24dbc-125">Você pode criar uma ordem de serviço do formulário **Ordens de venda** usando o assistente **Criar uma nova ordem de serviço com base na ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="24dbc-125">You can create a service order from the **Sales orders** form by using the **Create a new service order based on the sales order** wizard.</span></span>

1.  <span data-ttu-id="24dbc-126">Acesse **Vendas e marketing** \> **Comum** \> **Ordens de venda** \> **Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="24dbc-126">Go to **Sales and marketing** \> **Common** \> **Sales orders** \> **All sales orders**.</span></span>

2.  <span data-ttu-id="24dbc-127">Abra a ordem de venda relevante.</span><span class="sxs-lookup"><span data-stu-id="24dbc-127">Open the relevant sales order.</span></span>

3.  <span data-ttu-id="24dbc-128">Na guia **Ordem de venda**, selecione **Ordem de serviço** para iniciar o assistente **Criar uma nova ordem de serviço com base na ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="24dbc-128">On the **Sales order** tab, select **Service order** to start the **Create a new service order based on the sales order** wizard.</span></span>

4.  <span data-ttu-id="24dbc-129">Selecione **Avançar \>** e conclua as seguintes etapas na página **Selecionar o contrato de ordem de serviço**:</span><span class="sxs-lookup"><span data-stu-id="24dbc-129">Select **Next \>**, and then complete the following steps on the **Select agreement for service order** page:</span></span>
    
      - <span data-ttu-id="24dbc-130">Use o campo **Contrato de serviço** para selecionar o contrato de serviço ao qual a nova ordem de serviço deve ser associada.</span><span class="sxs-lookup"><span data-stu-id="24dbc-130">Use the **Service agreement** field to select the service agreement with which the new service order should be associated.</span></span>
    
      - <span data-ttu-id="24dbc-131">Opcional: Use a lista **ID de projeto** para associar a ordem de serviço a um determinado projeto.</span><span class="sxs-lookup"><span data-stu-id="24dbc-131">Optional: Use the **Project ID** field to associate this service order with a particular project.</span></span>

5.  <span data-ttu-id="24dbc-132">Selecione **Avançar \>** e conclua as seguintes etapas na página **Criar ordem de serviço**:</span><span class="sxs-lookup"><span data-stu-id="24dbc-132">Select **Next \>**, and then complete the following steps on the **Create service order** page:</span></span>
    
      - <span data-ttu-id="24dbc-133">Insira uma data e hora para que a chamada de serviço seja iniciada no campo **Hora de serviço preferencial**.</span><span class="sxs-lookup"><span data-stu-id="24dbc-133">Enter a date and time for the service call to begin in the **Preferred service time** field.</span></span>
    
      - <span data-ttu-id="24dbc-134">Opcional: Modifique o texto no campo **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="24dbc-134">Optional: Modify the text in the **Description** field.</span></span> <span data-ttu-id="24dbc-135">Por padrão, este campo contem a descrição do contrato de serviço selecionado na página anterior.</span><span class="sxs-lookup"><span data-stu-id="24dbc-135">By default, this field contains the description of the service agreement that you selected on the previous page.</span></span>
    
      - <span data-ttu-id="24dbc-136">No campo **Responsável**, selecione a ID do funcionário responsável pelo contrato e, se souber, a ID do técnico preferido do cliente para a chamada de serviço.</span><span class="sxs-lookup"><span data-stu-id="24dbc-136">In the **Responsible** field, select the ID of the employee who is responsible for the agreement, and if you know what it is, enter the ID of the customer's preferred technician for the service call.</span></span>
    
      - <span data-ttu-id="24dbc-137">No campo **ID de contato**, selecione a pessoa na empresa do cliente que deve ser contatada referente a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="24dbc-137">In the **Contact ID** field, select the person in the customer's company who should be contacted regarding this service order.</span></span>

6.  <span data-ttu-id="24dbc-138">Selecione **Avançar \>** e, em seguida, **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="24dbc-138">Select **Next \>**, and then select **Finish**.</span></span>


## <a name="see-also"></a><span data-ttu-id="24dbc-139">Consulte também</span><span class="sxs-lookup"><span data-stu-id="24dbc-139">See also</span></span>

[<span data-ttu-id="24dbc-140">Ordens de Serviço</span><span class="sxs-lookup"><span data-stu-id="24dbc-140">Service orders</span></span>](service-orders.md)

[<span data-ttu-id="24dbc-141">Criar ordens de serviço automaticamente</span><span class="sxs-lookup"><span data-stu-id="24dbc-141">Create service orders automatically</span></span>](create-service-orders-automatically.md)

<span data-ttu-id="24dbc-142">[Criar ordens de serviço (formulário de classe)](https://technet.microsoft.com/library/aa553901\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="24dbc-142">[Create service orders (class form)](https://technet.microsoft.com/library/aa553901\(v=ax.60\))</span></span> 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]