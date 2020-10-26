---
title: Criar relações de tarefas de serviço
description: Você pode associar tarefas de serviço a contratos de serviço ou ordens de serviço para descrever a tarefa de serviço que deverá ser concluída para o contrato ou a ordem.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e50b4322c65097ab4f8aba9c36e4d5e6cc4c01b
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3978596"
---
# <a name="create-service-task-relations"></a><span data-ttu-id="ade64-103">Criar relações de tarefas de serviço</span><span class="sxs-lookup"><span data-stu-id="ade64-103">Create service task relations</span></span>    

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ade64-104">Você pode associar tarefas de serviço a contratos de serviço ou ordens de serviço para descrever a tarefa de serviço que deverá ser concluída para o contrato ou a ordem.</span><span class="sxs-lookup"><span data-stu-id="ade64-104">You can associate service tasks with service agreements or service orders in order to describe the service task to be completed for the agreement or order.</span></span> <span data-ttu-id="ade64-105">Essas informações estão disponíveis para técnicos de serviço e clientes.</span><span class="sxs-lookup"><span data-stu-id="ade64-105">This information is available to service technicians and customers.</span></span>

## <a name="create-a-relation-with-a-service-agreement"></a><span data-ttu-id="ade64-106">Criar uma relação com um contrato de serviço</span><span class="sxs-lookup"><span data-stu-id="ade64-106">Create a relation with a service agreement</span></span>

1.  <span data-ttu-id="ade64-107">Clique em **Gerenciamento de serviços** \> **Comum** \> **Contratos de serviço** \> **Contratos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="ade64-107">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="ade64-108">Selecione um contrato de serviço existente ou crie um novo.</span><span class="sxs-lookup"><span data-stu-id="ade64-108">Select an existing service agreement, or create a new service agreement.</span></span>

3.  <span data-ttu-id="ade64-109">No Painel de Ações, clique no botão **Tarefas de serviço**.</span><span class="sxs-lookup"><span data-stu-id="ade64-109">On the Action Pane, click the **Service tasks** button.</span></span>

4.  <span data-ttu-id="ade64-110">No formulário **Tarefas de serviço**, pressione CTRL+N para criar uma nova linha e selecione uma tarefa de serviço na lista **Tarefa de serviço** para anexar a tarefa de serviço ao contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="ade64-110">On the **Service tasks** form, press CTRL+N to create a new line, and then select a service task from the **Service task** list to attach the service task to the service agreement.</span></span>

5.  <span data-ttu-id="ade64-111">Na guia **Descrição**, insira todas as descrições de observações internas ou externas nos campos de texto livre.</span><span class="sxs-lookup"><span data-stu-id="ade64-111">On the **Description** tab, enter any internal or external note descriptions in the free text fields.</span></span>

6.  <span data-ttu-id="ade64-112">Feche o formulário para salvar o registro.</span><span class="sxs-lookup"><span data-stu-id="ade64-112">Close the form to save the record.</span></span>

<span data-ttu-id="ade64-113">Repita este procedimento até ter criado todas as relações de tarefas de serviço necessárias para o contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="ade64-113">Repeat this procedure until you have created all the necessary service task relations for the service agreement.</span></span> <span data-ttu-id="ade64-114">Agora, você pode especificar essas tarefas de serviço para qualquer linha do contrato de serviço em anexo.</span><span class="sxs-lookup"><span data-stu-id="ade64-114">You can now specify these service tasks for any attached agreement lines.</span></span>

<span data-ttu-id="ade64-115">Uma relação de tarefas de serviço que é criada em um contrato de serviço está disponível a partir de todas as ordens de serviço anexadas ao contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="ade64-115">A service tasks relation that is created on a service agreement is available from all service orders that are attached to the service agreement.</span></span>

## <a name="create-a-relation-with-a-service-order"></a><span data-ttu-id="ade64-116">Criar uma relação com uma ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="ade64-116">Create a relation with a service order</span></span>

1.  <span data-ttu-id="ade64-117">Clique em **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="ade64-117">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="ade64-118">Selecione uma ordem de serviço existente ou crie uma nova.</span><span class="sxs-lookup"><span data-stu-id="ade64-118">Select an existing service order, or create a new service order.</span></span>

3.  <span data-ttu-id="ade64-119">No Painel de Ações, clique no botão **Tarefas de serviço**.</span><span class="sxs-lookup"><span data-stu-id="ade64-119">On the Action Pane, click the **Service tasks** button.</span></span>

4.  <span data-ttu-id="ade64-120">No formulário **Tarefas de serviço**, pressione CTRL+N para criar uma nova linha e selecione uma tarefa de serviço na lista **Tarefa de serviço** para anexar as tarefas de serviço à ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="ade64-120">From the **Service tasks** form, press CTRL+N to create a new line, and then select a service task from the **Service task** list to attach the service tasks to the service order.</span></span>

5.  <span data-ttu-id="ade64-121">Na guia **Descrição**, insira todas as descrições de observações internas ou externas nos campos de texto livre.</span><span class="sxs-lookup"><span data-stu-id="ade64-121">On the **Description** tab, enter any internal or external note descriptions in the free text fields.</span></span>

6.  <span data-ttu-id="ade64-122">Feche o formulário para salvar o registro.</span><span class="sxs-lookup"><span data-stu-id="ade64-122">Close the form to save the record.</span></span>

<span data-ttu-id="ade64-123">Repita este procedimento até ter criado todas as relações de tarefas de serviço necessárias para a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="ade64-123">Repeat this procedure until you have created all the necessary service task relations for the service order.</span></span> <span data-ttu-id="ade64-124">Agora, você pode selecionar a tarefa de serviço para a qual você criou a relação ao criar linhas da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="ade64-124">You can now select the service task for which you have created the relation when you create service order lines.</span></span>

<span data-ttu-id="ade64-125">As relações de tarefas de serviço que são criadas em uma ordem de serviço estão disponíveis na ordem de serviço específica.</span><span class="sxs-lookup"><span data-stu-id="ade64-125">Service task relations that are created on a service order are available on the specific service order.</span></span>

## <a name="see-also"></a><span data-ttu-id="ade64-126">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ade64-126">See also</span></span>

[<span data-ttu-id="ade64-127">Visão geral de tarefas de serviço</span><span class="sxs-lookup"><span data-stu-id="ade64-127">Service tasks overview</span></span>](service-tasks.md)


  


