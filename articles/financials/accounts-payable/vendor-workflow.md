---
title: Fluxo de trabalho do fornecedor
description: Modifique as informações do fornecedor e o fluxo de trabalho de uso de aprová-las.
author: mikefalkner
manager: annbe
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Vendor
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 950a1852acf9f3e4747ce2d55738c0eb3a646897
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1546769"
---
# <a name="vendor-workflow"></a><span data-ttu-id="f1749-103">Fluxo de trabalho do fornecedor</span><span class="sxs-lookup"><span data-stu-id="f1749-103">Vendor workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f1749-104">Quando o fluxo de trabalho do fornecedor é usado, as alterações feitas em campos específicos são enviadas para o fluxo de trabalho para aprovação antes que sejam adicionadas ao fornecedor.</span><span class="sxs-lookup"><span data-stu-id="f1749-104">When the vendor workflow is used, changes that are made to specific fields are sent to the workflow for approval before they are added to the vendor.</span></span>

## <a name="set-up-the-vendor-workflow"></a><span data-ttu-id="f1749-105">Configurar o fluxo de trabalho do fornecedor</span><span class="sxs-lookup"><span data-stu-id="f1749-105">Set up the vendor workflow</span></span>

<span data-ttu-id="f1749-106">Antes de usar o recurso fluxo de trabalho do fornecedor, você deve habilitá-lo.</span><span class="sxs-lookup"><span data-stu-id="f1749-106">Before you can use the workflow feature, you must enable it.</span></span>

1. <span data-ttu-id="f1749-107">Acesse **Contas a pagar \> Configuração \> Parâmetros de contas a pagar**.</span><span class="sxs-lookup"><span data-stu-id="f1749-107">Go to **Accounts payable \> Setup \> Accounts payable parameters**.</span></span>
2. <span data-ttu-id="f1749-108">Na guia **Geral**, na Guia Rápida **Aprovação do fornecedor** , defina a opção **Habilitar aprovações de fornecedor** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f1749-108">On the **General** tab, on the **Vendor approval** FastTab, set the **Enable vendor approvals** option to **Yes**.</span></span>
3. <span data-ttu-id="f1749-109">No campo **Comportamento de entidade de dados**, selecione o comportamento que deverá ser usado quando os dados forem importados:</span><span class="sxs-lookup"><span data-stu-id="f1749-109">In the **Data entity behavior** field, select the behavior that should be used when data is imported:</span></span>

    - <span data-ttu-id="f1749-110">**Permitir alterações sem aprovação** – a entidade de dados pode atualizar o registro do fornecedor sem processá-lo por meio do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f1749-110">**Allow changes without approval** – The data entity can update the vendor record without processing it through the workflow.</span></span>
    - <span data-ttu-id="f1749-111">**Rejeitar alterações** – as alterações não podem ser feitas no registro do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="f1749-111">**Reject changes** – Changes can't be made to the vendor record.</span></span> <span data-ttu-id="f1749-112">Ocorrerá falha na importação dos campos habilitados para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f1749-112">The import will fail for the fields that are enabled for the workflow.</span></span>
    - <span data-ttu-id="f1749-113">**Criar propostas de alteração** – todos os campos serão alterados exceto os campos habilitados para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f1749-113">**Create change proposals** – All fields will be changed except the fields that are enabled for the workflow.</span></span> <span data-ttu-id="f1749-114">Os novos valores para esses campos serão adicionados ao fornecedor como alterações propostas, e o fluxo de trabalho será iniciado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f1749-114">The new values for those fields will be added to the vendor as proposed changes, and the workflow will be started automatically.</span></span>

4. <span data-ttu-id="f1749-115">Na lista de campos de fornecedor, marque a caixa de seleção **Habilitar** para cada campo a ser aprovado antes que as alterações sejam feitas.</span><span class="sxs-lookup"><span data-stu-id="f1749-115">In the list of vendor fields, select the **Enable** check box for every field that must be approved before the changes can be made.</span></span>
5. <span data-ttu-id="f1749-116">Acesse **Contas a pagar \> Configuração \> Fluxos de trabalho de contas a pagar**.</span><span class="sxs-lookup"><span data-stu-id="f1749-116">Go to **Accounts payable \> Setup \> Accounts payable workflows**.</span></span>
6. <span data-ttu-id="f1749-117">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="f1749-117">Select **New**.</span></span>
7. <span data-ttu-id="f1749-118">Selecione **Fluxo de trabalho das alterações propostas de fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="f1749-118">Select **Proposed vendor changes workflow**.</span></span> 
8. <span data-ttu-id="f1749-119">Configure o fluxo de trabalho para que corresponda ao processo de aprovação.</span><span class="sxs-lookup"><span data-stu-id="f1749-119">Set up the workflow so that it matches your approval process.</span></span> <span data-ttu-id="f1749-120">O elemento de aprovação do fluxo de trabalho **Aprovação de fluxo de trabalho para a alteração proposta de fornecedor** aplicará as alterações ao fornecedor.</span><span class="sxs-lookup"><span data-stu-id="f1749-120">The **Workflow approval for proposed vendor change** workflow approval element will apply the changes to the vendor.</span></span>

## <a name="change-vendor-information-and-submit-the-changes-to-the-workflow"></a><span data-ttu-id="f1749-121">Alterar informações do fornecedor e enviar as alterações para o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="f1749-121">Change vendor information and submit the changes to the workflow</span></span>

<span data-ttu-id="f1749-122">Quando alterar um campo que está habilitado para o fluxo de trabalho, a página **Alterações propostas** será exibida.</span><span class="sxs-lookup"><span data-stu-id="f1749-122">When you change a field that is enabled for the workflow, the **Proposed changes** page appears.</span></span> <span data-ttu-id="f1749-123">Esta página mostra o valor original do campo e do novo valor inserido.</span><span class="sxs-lookup"><span data-stu-id="f1749-123">This page shows the original value of the field and the new value that you entered.</span></span> <span data-ttu-id="f1749-124">O campo que você alterou foi revertido para o valor original.</span><span class="sxs-lookup"><span data-stu-id="f1749-124">The field that you changed is reverted to its original value.</span></span> <span data-ttu-id="f1749-125">Uma mensagem de status também informa que as alterações não foram enviadas.</span><span class="sxs-lookup"><span data-stu-id="f1749-125">A status message also informs you that your changes haven't been submitted.</span></span> 

<span data-ttu-id="f1749-126">Cada vez que um campo que está habilitado para o fluxo de trabalho for alterado, o campo será adicionado à lista na página **Alterações propostas**.</span><span class="sxs-lookup"><span data-stu-id="f1749-126">Every time that you change a field that is enabled for the workflow, that field is added to the list on the **Proposed changes** page.</span></span> <span data-ttu-id="f1749-127">Para rejeitar o valor proposto para um campo, use o botão **Descartar** ao lado do campo na lista.</span><span class="sxs-lookup"><span data-stu-id="f1749-127">To discard the proposed value for a field, use the **Discard** button next to the field in the list.</span></span> <span data-ttu-id="f1749-128">Para descartar todas as alterações, use o botão **Descartar todas as alterações** na parte inferior da página.</span><span class="sxs-lookup"><span data-stu-id="f1749-128">To discard all changes, use the **Discard all changes** button at the bottom of the page.</span></span> <span data-ttu-id="f1749-129">Selecione **OK** para fechar a página.</span><span class="sxs-lookup"><span data-stu-id="f1749-129">Select **OK** to close the page.</span></span>

<span data-ttu-id="f1749-130">Após de ter pelo menos uma alteração proposta, duas guias adicionais aparecerão no painel de ações: **Alterações propostas** e **Fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="f1749-130">After you have at least one proposed change, two additional tabs appear on the action pane: **Proposed changes** and **Workflow**.</span></span>

1. <span data-ttu-id="f1749-131">Selecione **Alterações propostas** para abrir a página **Alterações propostas** e revisar as alterações.</span><span class="sxs-lookup"><span data-stu-id="f1749-131">Select **Proposed changes** to open the **Proposed changes** page and review your changes.</span></span>
2. <span data-ttu-id="f1749-132">Selecione **Fluxo de trabalho \> para enviar as alterações para o fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="f1749-132">Select **Workflow \> Submit to submit the changes to workflow**.</span></span>

    <span data-ttu-id="f1749-133">O status na página foi alterado para **Alterações com aprovação pendente**.</span><span class="sxs-lookup"><span data-stu-id="f1749-133">The status on the page is changed to **Changes pending approval**.</span></span>

<span data-ttu-id="f1749-134">O fluxo de trabalho segue o processo padrão de fluxo de trabalho no Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f1749-134">The workflow follows the standard workflow process in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="f1749-135">O aprovador é direcionado à página **Fornecedor**, na qual pode revisar as alterações na página **Alterações propostas** e selecionar **Fluxo de trabalho \> Aprovar** para aprovar o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f1749-135">The approver is directed to the **Vendor** page, where he or she can review the changes on the **Proposed changes** page and then select **Workflow \> Approve** to approve the workflow.</span></span> <span data-ttu-id="f1749-136">Depois que todas as aprovações forem concluídas, os campos serão atualizados com os valores que você propôs.</span><span class="sxs-lookup"><span data-stu-id="f1749-136">After all approvals are completed, the fields are updated with the values that you proposed.</span></span>
