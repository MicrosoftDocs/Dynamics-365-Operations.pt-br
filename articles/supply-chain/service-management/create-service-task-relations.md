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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9e5fd978c1e9db7e7ce3c06bbeb45b59854f1582
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974651"
---
# <a name="create-service-task-relations"></a><span data-ttu-id="9c586-103">Criar relações de tarefas de serviço</span><span class="sxs-lookup"><span data-stu-id="9c586-103">Create service task relations</span></span>    

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9c586-104">Você pode associar tarefas de serviço a contratos de serviço ou ordens de serviço para descrever a tarefa de serviço que deverá ser concluída para o contrato ou a ordem.</span><span class="sxs-lookup"><span data-stu-id="9c586-104">You can associate service tasks with service agreements or service orders in order to describe the service task to be completed for the agreement or order.</span></span> <span data-ttu-id="9c586-105">Essas informações estão disponíveis para técnicos de serviço e clientes.</span><span class="sxs-lookup"><span data-stu-id="9c586-105">This information is available to service technicians and customers.</span></span>

## <a name="create-a-relation-with-a-service-agreement"></a><span data-ttu-id="9c586-106">Criar uma relação com um contrato de serviço</span><span class="sxs-lookup"><span data-stu-id="9c586-106">Create a relation with a service agreement</span></span>

1.  <span data-ttu-id="9c586-107">Clique em **Gerenciamento de serviços** \> **Comum** \> **Contratos de serviço** \> **Contratos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="9c586-107">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="9c586-108">Selecione um contrato de serviço existente ou crie um novo.</span><span class="sxs-lookup"><span data-stu-id="9c586-108">Select an existing service agreement, or create a new service agreement.</span></span>

3.  <span data-ttu-id="9c586-109">No Painel de Ações, clique no botão **Tarefas de serviço**.</span><span class="sxs-lookup"><span data-stu-id="9c586-109">On the Action Pane, click the **Service tasks** button.</span></span>

4.  <span data-ttu-id="9c586-110">No formulário **Tarefas de serviço**, pressione CTRL+N para criar uma nova linha e selecione uma tarefa de serviço na lista **Tarefa de serviço** para anexar a tarefa de serviço ao contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="9c586-110">On the **Service tasks** form, press CTRL+N to create a new line, and then select a service task from the **Service task** list to attach the service task to the service agreement.</span></span>

5.  <span data-ttu-id="9c586-111">Na guia **Descrição**, insira todas as descrições de observações internas ou externas nos campos de texto livre.</span><span class="sxs-lookup"><span data-stu-id="9c586-111">On the **Description** tab, enter any internal or external note descriptions in the free text fields.</span></span>

6.  <span data-ttu-id="9c586-112">Feche o formulário para salvar o registro.</span><span class="sxs-lookup"><span data-stu-id="9c586-112">Close the form to save the record.</span></span>

<span data-ttu-id="9c586-113">Repita este procedimento até ter criado todas as relações de tarefas de serviço necessárias para o contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="9c586-113">Repeat this procedure until you have created all the necessary service task relations for the service agreement.</span></span> <span data-ttu-id="9c586-114">Agora, você pode especificar essas tarefas de serviço para qualquer linha do contrato de serviço em anexo.</span><span class="sxs-lookup"><span data-stu-id="9c586-114">You can now specify these service tasks for any attached agreement lines.</span></span>

<span data-ttu-id="9c586-115">Uma relação de tarefas de serviço que é criada em um contrato de serviço está disponível a partir de todas as ordens de serviço anexadas ao contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="9c586-115">A service tasks relation that is created on a service agreement is available from all service orders that are attached to the service agreement.</span></span>

## <a name="create-a-relation-with-a-service-order"></a><span data-ttu-id="9c586-116">Criar uma relação com uma ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="9c586-116">Create a relation with a service order</span></span>

1.  <span data-ttu-id="9c586-117">Clique em **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="9c586-117">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="9c586-118">Selecione uma ordem de serviço existente ou crie uma nova.</span><span class="sxs-lookup"><span data-stu-id="9c586-118">Select an existing service order, or create a new service order.</span></span>

3.  <span data-ttu-id="9c586-119">No Painel de Ações, clique no botão **Tarefas de serviço**.</span><span class="sxs-lookup"><span data-stu-id="9c586-119">On the Action Pane, click the **Service tasks** button.</span></span>

4.  <span data-ttu-id="9c586-120">No formulário **Tarefas de serviço**, pressione CTRL+N para criar uma nova linha e selecione uma tarefa de serviço na lista **Tarefa de serviço** para anexar as tarefas de serviço à ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="9c586-120">From the **Service tasks** form, press CTRL+N to create a new line, and then select a service task from the **Service task** list to attach the service tasks to the service order.</span></span>

5.  <span data-ttu-id="9c586-121">Na guia **Descrição**, insira todas as descrições de observações internas ou externas nos campos de texto livre.</span><span class="sxs-lookup"><span data-stu-id="9c586-121">On the **Description** tab, enter any internal or external note descriptions in the free text fields.</span></span>

6.  <span data-ttu-id="9c586-122">Feche o formulário para salvar o registro.</span><span class="sxs-lookup"><span data-stu-id="9c586-122">Close the form to save the record.</span></span>

<span data-ttu-id="9c586-123">Repita este procedimento até ter criado todas as relações de tarefas de serviço necessárias para a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="9c586-123">Repeat this procedure until you have created all the necessary service task relations for the service order.</span></span> <span data-ttu-id="9c586-124">Agora, você pode selecionar a tarefa de serviço para a qual você criou a relação ao criar linhas da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="9c586-124">You can now select the service task for which you have created the relation when you create service order lines.</span></span>

<span data-ttu-id="9c586-125">As relações de tarefas de serviço que são criadas em uma ordem de serviço estão disponíveis na ordem de serviço específica.</span><span class="sxs-lookup"><span data-stu-id="9c586-125">Service task relations that are created on a service order are available on the specific service order.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c586-126">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9c586-126">See also</span></span>

[<span data-ttu-id="9c586-127">Visão geral de tarefas de serviço</span><span class="sxs-lookup"><span data-stu-id="9c586-127">Service tasks overview</span></span>](service-tasks.md)


  


