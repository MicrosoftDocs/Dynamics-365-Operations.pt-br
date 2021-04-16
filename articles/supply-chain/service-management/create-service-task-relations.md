---
title: Criar relações de tarefas de serviço
description: Você pode associar tarefas de serviço a contratos de serviço ou ordens de serviço para descrever a tarefa de serviço que deverá ser concluída para o contrato ou a ordem.
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
ms.openlocfilehash: f9a7808357916ed80ddfa46e1e4f362e0dde1671
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819055"
---
# <a name="create-service-task-relations"></a><span data-ttu-id="45cab-103">Criar relações de tarefas de serviço</span><span class="sxs-lookup"><span data-stu-id="45cab-103">Create service task relations</span></span>    

[!include [banner](../includes/banner.md)]

<span data-ttu-id="45cab-104">Você pode associar tarefas de serviço a contratos de serviço ou ordens de serviço para descrever a tarefa de serviço que deverá ser concluída para o contrato ou a ordem.</span><span class="sxs-lookup"><span data-stu-id="45cab-104">You can associate service tasks with service agreements or service orders in order to describe the service task to be completed for the agreement or order.</span></span> <span data-ttu-id="45cab-105">Essas informações estão disponíveis para técnicos de serviço e clientes.</span><span class="sxs-lookup"><span data-stu-id="45cab-105">This information is available to service technicians and customers.</span></span>

## <a name="create-a-relation-with-a-service-agreement"></a><span data-ttu-id="45cab-106">Criar uma relação com um contrato de serviço</span><span class="sxs-lookup"><span data-stu-id="45cab-106">Create a relation with a service agreement</span></span>

1.  <span data-ttu-id="45cab-107">Acesse **Gerenciamento de serviços** \> **Comum** \> **Contratos de serviço** \> **Contratos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="45cab-107">Go to **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="45cab-108">Selecione um contrato de serviço existente ou crie um novo.</span><span class="sxs-lookup"><span data-stu-id="45cab-108">Select an existing service agreement, or create a new service agreement.</span></span>

3.  <span data-ttu-id="45cab-109">No Painel de Ações, selecione o botão **Tarefas de serviço**.</span><span class="sxs-lookup"><span data-stu-id="45cab-109">On the Action Pane, select the **Service tasks** button.</span></span>

4.  <span data-ttu-id="45cab-110">No formulário **Tarefas de serviço**, selecione **Novo** para criar uma nova linha e selecione uma tarefa de serviço na lista **Tarefa de serviço** para anexar a tarefa de serviço ao contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="45cab-110">On the **Service tasks** form, select **New** to create a new line, and then select a service task from the **Service task** list to attach the service task to the service agreement.</span></span>

5.  <span data-ttu-id="45cab-111">Na guia **Descrição**, insira todas as descrições de observações internas ou externas nos campos de texto livre.</span><span class="sxs-lookup"><span data-stu-id="45cab-111">On the **Description** tab, enter any internal or external note descriptions in the free text fields.</span></span>

6.  <span data-ttu-id="45cab-112">Feche o formulário para salvar o registro.</span><span class="sxs-lookup"><span data-stu-id="45cab-112">Close the form to save the record.</span></span>

<span data-ttu-id="45cab-113">Repita este procedimento até ter criado todas as relações de tarefas de serviço necessárias para o contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="45cab-113">Repeat this procedure until you have created all the necessary service task relations for the service agreement.</span></span> <span data-ttu-id="45cab-114">Agora, você pode especificar essas tarefas de serviço para qualquer linha do contrato de serviço em anexo.</span><span class="sxs-lookup"><span data-stu-id="45cab-114">You can now specify these service tasks for any attached agreement lines.</span></span>

<span data-ttu-id="45cab-115">Uma relação de tarefas de serviço que é criada em um contrato de serviço está disponível a partir de todas as ordens de serviço anexadas ao contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="45cab-115">A service tasks relation that is created on a service agreement is available from all service orders that are attached to the service agreement.</span></span>

## <a name="create-a-relation-with-a-service-order"></a><span data-ttu-id="45cab-116">Criar uma relação com uma ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="45cab-116">Create a relation with a service order</span></span>

1.  <span data-ttu-id="45cab-117">Acesse **Gerenciamento de serviços** \> **Comum** \> **Ordens de serviço** \> **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="45cab-117">Go to **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="45cab-118">Selecione uma ordem de serviço existente ou crie uma nova.</span><span class="sxs-lookup"><span data-stu-id="45cab-118">Select an existing service order, or create a new service order.</span></span>

3.  <span data-ttu-id="45cab-119">No Painel de Ações, selecione o botão **Tarefas de serviço**.</span><span class="sxs-lookup"><span data-stu-id="45cab-119">On the Action Pane, select the **Service tasks** button.</span></span>

4.  <span data-ttu-id="45cab-120">No formulário **Tarefas de serviço**, selecione **Novo** para criar uma nova linha e selecione uma tarefa de serviço na lista **Tarefa de serviço** para anexar as tarefas de serviço à ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="45cab-120">From the **Service tasks** form, select **New** to create a new line, and then select a service task from the **Service task** list to attach the service tasks to the service order.</span></span>

5.  <span data-ttu-id="45cab-121">Na guia **Descrição**, insira todas as descrições de observações internas ou externas nos campos de texto livre.</span><span class="sxs-lookup"><span data-stu-id="45cab-121">On the **Description** tab, enter any internal or external note descriptions in the free text fields.</span></span>

6.  <span data-ttu-id="45cab-122">Feche o formulário para salvar o registro.</span><span class="sxs-lookup"><span data-stu-id="45cab-122">Close the form to save the record.</span></span>

<span data-ttu-id="45cab-123">Repita este procedimento até ter criado todas as relações de tarefas de serviço necessárias para a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="45cab-123">Repeat this procedure until you have created all the necessary service task relations for the service order.</span></span> <span data-ttu-id="45cab-124">Agora, você pode selecionar a tarefa de serviço para a qual você criou a relação ao criar linhas da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="45cab-124">You can now select the service task for which you have created the relation when you create service order lines.</span></span>

<span data-ttu-id="45cab-125">As relações de tarefas de serviço que são criadas em uma ordem de serviço estão disponíveis na ordem de serviço específica.</span><span class="sxs-lookup"><span data-stu-id="45cab-125">Service task relations that are created on a service order are available on the specific service order.</span></span>

## <a name="see-also"></a><span data-ttu-id="45cab-126">Consulte também</span><span class="sxs-lookup"><span data-stu-id="45cab-126">See also</span></span>

[<span data-ttu-id="45cab-127">Visão geral de tarefas de serviço</span><span class="sxs-lookup"><span data-stu-id="45cab-127">Service tasks overview</span></span>](service-tasks.md)


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]