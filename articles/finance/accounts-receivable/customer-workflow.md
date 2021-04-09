---
title: Fluxo de trabalho de cliente
description: Este tópico fornece informações sobre o fluxo de trabalho de cliente. Você altera campos específicos de um cliente e envia essas alterações para aprovação usando o fluxo de trabalho antes que elas sejam adicionadas ao cliente.
author: mikefalkner
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: c769d225ee0f7b35719c37d9b9bc690a20060911
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817260"
---
# <a name="customer-workflow"></a><span data-ttu-id="1ddff-104">Fluxo de trabalho de cliente</span><span class="sxs-lookup"><span data-stu-id="1ddff-104">Customer workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1ddff-105">O fluxo de trabalho de cliente foi adicionado à versão 8.0.4.</span><span class="sxs-lookup"><span data-stu-id="1ddff-105">The customer workflow has been added to version 8.0.4.</span></span> <span data-ttu-id="1ddff-106">Você pode alterar campos específicos de um cliente e enviar essas alterações para aprovação usando o fluxo de trabalho antes que elas sejam adicionadas ao cliente.</span><span class="sxs-lookup"><span data-stu-id="1ddff-106">You can change specific fields for a customer and then send those changes for approval by using the workflow before they are added to the customer.</span></span>

## <a name="set-up-the-customer-workflow"></a><span data-ttu-id="1ddff-107">Configurar o fluxo de trabalho de cliente</span><span class="sxs-lookup"><span data-stu-id="1ddff-107">Set up the customer workflow</span></span>

<span data-ttu-id="1ddff-108">Antes de usar o recurso fluxo de trabalho de cliente, você deve habilitá-lo.</span><span class="sxs-lookup"><span data-stu-id="1ddff-108">Before you can use the customer workflow feature, you must enable it.</span></span>

1. <span data-ttu-id="1ddff-109">Vá para **Contas a receber \> Configuração \> Parâmetros de contas a receber**.</span><span class="sxs-lookup"><span data-stu-id="1ddff-109">Go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="1ddff-110">Na guia **Geral**, na FastTab **Aprovação de cliente**, defina a opção **Habilitar aprovações de cliente** como **Sim** para habilitar o recurso.</span><span class="sxs-lookup"><span data-stu-id="1ddff-110">On the **General** tab, on the **Customer approval** FastTab, set the **Enable customer approvals** option to **Yes** to enable the feature.</span></span>
3. <span data-ttu-id="1ddff-111">No campo **Comportamento de entidade de dados**, selecione o comportamento que as entidades de dados devem usar quando os dados forem importados:</span><span class="sxs-lookup"><span data-stu-id="1ddff-111">In the **Data entity behavior** field, select the behavior that the data entities should use when data is imported:</span></span>

    - <span data-ttu-id="1ddff-112">**Permitir alterações sem aprovação** – Uma entidade pode atualizar o registro do cliente sem processá-lo por meio do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1ddff-112">**Allow changes without approval** – An entity can update the customer record without processing it through the workflow.</span></span>
    - <span data-ttu-id="1ddff-113">**Rejeitar alterações** – As alterações não podem ser feitas no registro do cliente.</span><span class="sxs-lookup"><span data-stu-id="1ddff-113">**Reject changes** – Changes can't be made to the customer record.</span></span> <span data-ttu-id="1ddff-114">Ocorrerá falha na importação dos campos habilitados para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1ddff-114">The import will fail for the fields that are enabled for the workflow.</span></span>
    - <span data-ttu-id="1ddff-115">**Criar propostas de alteração** – Todos os campos serão alterados exceto os campos habilitados para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1ddff-115">**Create change proposals** – All fields will be changed except the fields that are enabled for the workflow.</span></span> <span data-ttu-id="1ddff-116">Os novos valores para esses campos serão adicionados ao cliente como alterações propostas, e o fluxo de trabalho será iniciado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1ddff-116">The new values for those fields will be added to the customer as proposed changes, and the workflow will be started automatically.</span></span>

4. <span data-ttu-id="1ddff-117">Na lista de campos de cliente, marque a caixa de seleção **Habilitar** para cada campo a ser aprovado antes que as alterações sejam feitas.</span><span class="sxs-lookup"><span data-stu-id="1ddff-117">In the list of customer fields, select then **Enable** check box for every field that must be approved before the changes can be made.</span></span>
5. <span data-ttu-id="1ddff-118">Vá para **Contas a receber \> Configuração \> Fluxos de trabalho de contas a receber**.</span><span class="sxs-lookup"><span data-stu-id="1ddff-118">Go to **Accounts receivable \> Setup \> Accounts receivable workflows**.</span></span>
6. <span data-ttu-id="1ddff-119">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="1ddff-119">Select **New**.</span></span>
7. <span data-ttu-id="1ddff-120">Selecione **Fluxo de trabalho da alteração proposta de cliente**.</span><span class="sxs-lookup"><span data-stu-id="1ddff-120">Select **Proposed customer change workflow**.</span></span> 
8. <span data-ttu-id="1ddff-121">Configurar o fluxo de trabalho para que corresponda ao processo de aprovação.</span><span class="sxs-lookup"><span data-stu-id="1ddff-121">Set up the workflow so that it matches your approval process.</span></span> <span data-ttu-id="1ddff-122">O elemento de aprovação do fluxo de trabalho **Aprovação de fluxo de trabalho para a alteração de cliente proposta** aplicará as alterações ao cliente.</span><span class="sxs-lookup"><span data-stu-id="1ddff-122">The **Workflow approval for proposed customer change** workflow approval element will apply the changes to the customer.</span></span>

## <a name="change-customer-information-and-submit-the-changes-to-the-workflow"></a><span data-ttu-id="1ddff-123">Altere as informações do cliente e envie as alterações para o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="1ddff-123">Change customer information and submit the changes to the workflow</span></span>

<span data-ttu-id="1ddff-124">Quando alterar um campo que está habilitado para o fluxo de trabalho, a página **Alterações propostas** será exibida.</span><span class="sxs-lookup"><span data-stu-id="1ddff-124">When you change a field that is enabled for the workflow, the **Proposed changes** page appears.</span></span> <span data-ttu-id="1ddff-125">Esta página mostra o valor original do campo e do novo valor inserido.</span><span class="sxs-lookup"><span data-stu-id="1ddff-125">This page shows the original value of the field and the new value that you entered.</span></span> <span data-ttu-id="1ddff-126">O campo que você alterou foi revertido para o valor original.</span><span class="sxs-lookup"><span data-stu-id="1ddff-126">The field that you changed is reverted to its original value.</span></span> <span data-ttu-id="1ddff-127">Uma mensagem de status na página informa que as alterações não foram enviadas.</span><span class="sxs-lookup"><span data-stu-id="1ddff-127">A status message on the page informs you that your changes haven't been submitted.</span></span>

<span data-ttu-id="1ddff-128">Cada vez que um campo que está habilitado para o fluxo de trabalho for alterado, o campo será adicionado à lista de alterações propostas.</span><span class="sxs-lookup"><span data-stu-id="1ddff-128">Every time that you change a field that is enabled for the workflow, that field is added to the list of proposed changes.</span></span> <span data-ttu-id="1ddff-129">Para rejeitar o valor proposto para um campo, use o botão **Descartar** ao lado do campo na lista.</span><span class="sxs-lookup"><span data-stu-id="1ddff-129">To discard the proposed value for a field, use the **Discard** button next to the field in the list.</span></span> <span data-ttu-id="1ddff-130">Para rejeitar todas as alterações, use o botão **Descartar todas as alterações** na parte inferior da página.</span><span class="sxs-lookup"><span data-stu-id="1ddff-130">To discard all changes, use the **Discard all change** button at the bottom of the page.</span></span> <span data-ttu-id="1ddff-131">Selecione **OK** para fechar a página.</span><span class="sxs-lookup"><span data-stu-id="1ddff-131">Select **OK** to close the page.</span></span>

<span data-ttu-id="1ddff-132">Após haver pelo menos uma alteração proposta, dois menus adicionais aparecerão no Painel de Ações: **Alterações propostas** e **Fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="1ddff-132">After you have at least one proposed change, two additional menus appear on the Action Pane: **Proposed changes** and **Workflow**.</span></span>

1. <span data-ttu-id="1ddff-133">Selecione **Alterações propostas** para abrir a página **Alterações propostas** e revisar as alterações.</span><span class="sxs-lookup"><span data-stu-id="1ddff-133">Select **Proposed changes** to open the **Proposed changes** page and review your changes.</span></span>
2. <span data-ttu-id="1ddff-134">Selecione **Fluxo de trabalho \> Enviar** para enviar as alterações para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1ddff-134">Select **Workflow \> Submit** to submit the changes to the workflow.</span></span>

    <span data-ttu-id="1ddff-135">O status na página foi alterado para **Alterações com aprovação pendente**.</span><span class="sxs-lookup"><span data-stu-id="1ddff-135">The status on the page is changed to **Changes pending approval**.</span></span>

<span data-ttu-id="1ddff-136">O fluxo de trabalho segue o processo de fluxo de trabalho padrão no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1ddff-136">The workflow follows the standard workflow process in the application.</span></span> <span data-ttu-id="1ddff-137">O aprovador é direcionado à página **Cliente**, na qual é possível revisar as alterações na página **Alterações propostas** e, em seguida, selecionar **Fluxo de trabalho \> Aprovar** para aprovar o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1ddff-137">The approver is directed to the **Customer** page where the changes can be reviewed on the **Proposed changes** page and then select **Workflow \> Approve** to approve the workflow.</span></span> <span data-ttu-id="1ddff-138">Depois que todas as aprovações forem concluídas, os campos serão atualizados com os valores que você propôs.</span><span class="sxs-lookup"><span data-stu-id="1ddff-138">After all approvals are completed, the fields are updated with the values that you proposed.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]