---
title: Criar ordens de serviço manualmente
description: Você pode criar ordens de serviço manualmente usando um contrato de serviço ou o formulário **Ordens de serviço**.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 486b4a0291ca527e647c9b5a41ff2e65a7820291
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817572"
---
# <a name="create-service-orders-manually"></a><span data-ttu-id="19355-103">Criar ordens de serviço manualmente</span><span class="sxs-lookup"><span data-stu-id="19355-103">Create service orders manually</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="19355-104">Você pode criar ordens de serviço manualmente usando um contrato de serviço ou o formulário **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="19355-104">You can create service orders manually by using a service agreement or by using the **Service orders** form.</span></span> <span data-ttu-id="19355-105">Também é possível criar uma ordem de serviço a partir de um projeto.</span><span class="sxs-lookup"><span data-stu-id="19355-105">You can also create a service order from a project.</span></span>

> [!TIP]
> <P><span data-ttu-id="19355-106">Você pode usar processos automatizados para criar ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="19355-106">You can use automated processes to create service orders.</span></span> 

## <a name="create-a-service-order-manually-from-a-service-agreement"></a><span data-ttu-id="19355-107">Criar uma ordem de serviço manualmente a partir de um contrato de serviço</span><span class="sxs-lookup"><span data-stu-id="19355-107">Create a service order manually from a service agreement</span></span>

1.  <span data-ttu-id="19355-108">Selecione **Gerenciamento de serviços** \> **Comum** \> **Contratos de serviço** \> **Contratos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="19355-108">Select **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="19355-109">Selecione um contrato de serviço ou crie um novo.</span><span class="sxs-lookup"><span data-stu-id="19355-109">Select a service agreement or create a new service agreement.</span></span>

3.  <span data-ttu-id="19355-110">Selecione a guia **Entregar** e, no grupo **Criar**, selecione **Ordens de serviço planejadas** para abrir o formulário **Criar ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="19355-110">Select the **Deliver** tab and in the **Create** group select **Planned service orders** to open the **Create service orders** form.</span></span>

## <a name="create-a-service-order-manually-in-the-service-orders-form"></a><span data-ttu-id="19355-111">Criar uma ordem de serviço manualmente no formulário Ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="19355-111">Create a service order manually in the Service orders form</span></span>

1.  <span data-ttu-id="19355-112">Selecione **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="19355-112">Select **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="19355-113">Selecione **Novo** para criar uma nova ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="19355-113">Select **New** to create a new service order.</span></span>

3.  <span data-ttu-id="19355-114">Criar as linhas de ordem de serviço para a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="19355-114">Create service order lines for the service order.</span></span>

> [!NOTE]
> <P><span data-ttu-id="19355-115">Se a caixa de seleção <STRONG>Permitir sem contrato de serviço</STRONG> do formulário <STRONG>Parâmetros de gerenciamento de serviços</STRONG> estiver marcada, você poderá lançar as transações a partir das linhas da ordem de serviço sem anexar a ordem de serviço ao contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="19355-115">If the <STRONG>Allow without service agreement</STRONG> check box in the <STRONG>Service management parameters</STRONG> form is selected, you can post the transactions from the service order lines without attaching the service order to a service agreement.</span></span> <span data-ttu-id="19355-116">Se a caixa de seleção estiver desmarcada, você deverá anexar a ordem de serviço criada manualmente a um projeto antes de lançar as linhas da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="19355-116">If the check box is cleared, you must attach the manually created service order to a project before posting the service order lines.</span></span></P>

## <a name="create-a-service-order-from-a-project"></a><span data-ttu-id="19355-117">Criar uma ordem de serviço a partir de um projeto</span><span class="sxs-lookup"><span data-stu-id="19355-117">Create a service order from a project</span></span>

1.  <span data-ttu-id="19355-118">Acesse **Gerenciamento e contabilidade de projeto** \> **Comum** \> **Projetos** \> **Todos os projetos**.</span><span class="sxs-lookup"><span data-stu-id="19355-118">Go to **Project management and accounting** \> **Common** \> **Projects** \> **All projects**.</span></span>

2.  <span data-ttu-id="19355-119">No formulário **Projetos**, no **Painel de Ações**, selecione a guia **Gerenciar** \> selecione **Serviço** \> **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="19355-119">In the **Projects** form, on the **Action Pane**, select the **Manage** tab \> select **Service** \> **Service orders**.</span></span>

3.  <span data-ttu-id="19355-120">Siga o procedimento anterior para criar uma ordem de serviço manualmente no formulário **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="19355-120">Follow the previous procedure to create a service order manually in the **Service orders** form.</span></span> <span data-ttu-id="19355-121">O campo **ID de projeto** exibe a referência do projeto.</span><span class="sxs-lookup"><span data-stu-id="19355-121">The **Project ID** field displays the project reference.</span></span>

> [!NOTE]
> <P><span data-ttu-id="19355-122">Se a caixa de seleção <STRONG>Permitir sem contrato de serviço</STRONG> do formulário <STRONG>Parâmetros de gerenciamento de serviços</STRONG> estiver marcada, você poderá lançar as transações a partir das linhas da ordem de serviço sem anexar a ordem de serviço ao contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="19355-122">If the <STRONG>Allow without service agreement</STRONG> check box in the <STRONG>Service management parameters</STRONG> form is selected, you can post the transactions from the service order lines without attaching the service order to a service agreement.</span></span> <span data-ttu-id="19355-123">Se a caixa de seleção estiver desmarcada, você deverá anexar a ordem de serviço criada manualmente a um projeto antes de lançar as linhas da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="19355-123">If the check box is cleared, you must attach the manually created service order to a project before posting the service order lines.</span></span></P>

## <a name="create-a-service-order-from-the-sales-order-form"></a><span data-ttu-id="19355-124">Criar uma ordem de serviço a partir de um formulário de ordem de Venda</span><span class="sxs-lookup"><span data-stu-id="19355-124">Create a service order from the Sales order form</span></span>

<span data-ttu-id="19355-125">Você pode criar uma ordem de serviço do formulário **Ordens de venda** usando o assistente **Criar uma nova ordem de serviço com base na ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="19355-125">You can create a service order from the **Sales orders** form by using the **Create a new service order based on the sales order** wizard.</span></span>

1.  <span data-ttu-id="19355-126">Acesse **Vendas e marketing** \> **Comum** \> **Ordens de venda** \> **Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="19355-126">Go to **Sales and marketing** \> **Common** \> **Sales orders** \> **All sales orders**.</span></span>

2.  <span data-ttu-id="19355-127">Abra a ordem de venda relevante.</span><span class="sxs-lookup"><span data-stu-id="19355-127">Open the relevant sales order.</span></span>

3.  <span data-ttu-id="19355-128">Na guia **Ordem de venda**, selecione **Ordem de serviço** para iniciar o assistente **Criar uma nova ordem de serviço com base na ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="19355-128">On the **Sales order** tab, select **Service order** to start the **Create a new service order based on the sales order** wizard.</span></span>

4.  <span data-ttu-id="19355-129">Selecione **Avançar \>** e conclua as seguintes etapas na página **Selecionar o contrato de ordem de serviço**:</span><span class="sxs-lookup"><span data-stu-id="19355-129">Select **Next \>**, and then complete the following steps on the **Select agreement for service order** page:</span></span>
    
      - <span data-ttu-id="19355-130">Use o campo **Contrato de serviço** para selecionar o contrato de serviço ao qual a nova ordem de serviço deve ser associada.</span><span class="sxs-lookup"><span data-stu-id="19355-130">Use the **Service agreement** field to select the service agreement with which the new service order should be associated.</span></span>
    
      - <span data-ttu-id="19355-131">Opcional: Use a lista **ID de projeto** para associar a ordem de serviço a um determinado projeto.</span><span class="sxs-lookup"><span data-stu-id="19355-131">Optional: Use the **Project ID** field to associate this service order with a particular project.</span></span>

5.  <span data-ttu-id="19355-132">Selecione **Avançar \>** e conclua as seguintes etapas na página **Criar ordem de serviço**:</span><span class="sxs-lookup"><span data-stu-id="19355-132">Select **Next \>**, and then complete the following steps on the **Create service order** page:</span></span>
    
      - <span data-ttu-id="19355-133">Insira uma data e hora para que a chamada de serviço seja iniciada no campo **Hora de serviço preferencial**.</span><span class="sxs-lookup"><span data-stu-id="19355-133">Enter a date and time for the service call to begin in the **Preferred service time** field.</span></span>
    
      - <span data-ttu-id="19355-134">Opcional: Modifique o texto no campo **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="19355-134">Optional: Modify the text in the **Description** field.</span></span> <span data-ttu-id="19355-135">Por padrão, este campo contem a descrição do contrato de serviço selecionado na página anterior.</span><span class="sxs-lookup"><span data-stu-id="19355-135">By default, this field contains the description of the service agreement that you selected on the previous page.</span></span>
    
      - <span data-ttu-id="19355-136">No campo **Responsável**, selecione a ID do funcionário responsável pelo contrato e, se souber, a ID do técnico preferido do cliente para a chamada de serviço.</span><span class="sxs-lookup"><span data-stu-id="19355-136">In the **Responsible** field, select the ID of the employee who is responsible for the agreement, and if you know what it is, enter the ID of the customer's preferred technician for the service call.</span></span>
    
      - <span data-ttu-id="19355-137">No campo **ID de contato**, selecione a pessoa na empresa do cliente que deve ser contatada referente a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="19355-137">In the **Contact ID** field, select the person in the customer's company who should be contacted regarding this service order.</span></span>

6.  <span data-ttu-id="19355-138">Selecione **Avançar \>** e, em seguida, **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="19355-138">Select **Next \>**, and then select **Finish**.</span></span>


## <a name="see-also"></a><span data-ttu-id="19355-139">Consulte também</span><span class="sxs-lookup"><span data-stu-id="19355-139">See also</span></span>

[<span data-ttu-id="19355-140">Ordens de Serviço</span><span class="sxs-lookup"><span data-stu-id="19355-140">Service orders</span></span>](service-orders.md)

[<span data-ttu-id="19355-141">Criar ordens de serviço automaticamente</span><span class="sxs-lookup"><span data-stu-id="19355-141">Create service orders automatically</span></span>](create-service-orders-automatically.md)

<span data-ttu-id="19355-142">[Criar ordens de serviço (formulário de classe)](https://technet.microsoft.com/library/aa553901\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="19355-142">[Create service orders (class form)](https://technet.microsoft.com/library/aa553901\(v=ax.60\))</span></span> 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]