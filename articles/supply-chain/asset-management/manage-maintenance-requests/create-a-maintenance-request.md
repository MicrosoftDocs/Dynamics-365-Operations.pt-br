---
title: Crie solicitações de manutenção
description: Este tópico explica como criar uma solicitação de manutenção em Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetRequestTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 22d5e371c386abc71946bf64ed8792647f78cf1b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422245"
---
# <a name="create-maintenance-requests"></a><span data-ttu-id="e38c2-103">Crie solicitações de manutenção</span><span class="sxs-lookup"><span data-stu-id="e38c2-103">Create maintenance requests</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="e38c2-104">As solicitações de manutenção poderão ser usadas se os funcionários de manutenção ou os funcionários de produção descobrirem que o equipamento exige reparo, mas o reparo não puder ser feito imediatamente.</span><span class="sxs-lookup"><span data-stu-id="e38c2-104">Maintenance requests can be used if maintenance workers or production workers discover that equipment requires repair, but the repair job can't be done right away.</span></span>

<span data-ttu-id="e38c2-105">**Exemplo:** ao fazer um reparo, uma funcionária de manutenção descobre que outro ativo no mesmo local deve ser atendido.</span><span class="sxs-lookup"><span data-stu-id="e38c2-105">**Example:** While a maintenance worker is making a repair, she discovers that another asset at the same location must be serviced.</span></span> <span data-ttu-id="e38c2-106">Entretanto, a funcionária de manutenção não tem o tempo ou as peças sobressalentes necessárias para realizar o trabalho de reparo.</span><span class="sxs-lookup"><span data-stu-id="e38c2-106">However, the maintenance worker doesn't have the time or the required spare parts to do the repair job.</span></span> <span data-ttu-id="e38c2-107">Assim, ela cria uma uma solicitação de manutenção no ativo e insere uma breve descrição do problema.</span><span class="sxs-lookup"><span data-stu-id="e38c2-107">Therefore, she creates a maintenance request on the asset and enters a short description of the issue.</span></span>

<span data-ttu-id="e38c2-108">A seção **Solicitações de manutenção de ativos** do painel **Informações relacionadas** no lado direito da página **Todos os ativos** ou **Ativos ativos** (**Gerenciamento de ativos** \> **Comum** \> **Ativos** \> **Todos os ativos** ou **Ativos ativos**) mostra solicitações de manutenção de ativos anexadas ao ativo selecionado.</span><span class="sxs-lookup"><span data-stu-id="e38c2-108">The **Active maintenance requests** section of the **Related information** pane on the right side of the **All assets** or **Active assets** page (**Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**) shows the active maintenance requests that are attached to the selected asset.</span></span>

1. <span data-ttu-id="e38c2-109">Selecione **Gerenciamento de ativos** \> **Comum** \> **Solicitações de manutenção** \> **Todas as solicitações de manutenção** ou **Solicitações manutenção de ativos**.</span><span class="sxs-lookup"><span data-stu-id="e38c2-109">Select **Asset management** \> **Common** \> **Maintenance requests** \> **All maintenance requests** or **Active maintenance requests**.</span></span>
2. <span data-ttu-id="e38c2-110">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="e38c2-110">Select **New**.</span></span>
3. <span data-ttu-id="e38c2-111">Na caixa de diálogo **Criar solicitação**, no campo **Tipo de solicitação de manutenção**, selecione o tipo de solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="e38c2-111">In the **Create request** dialog box, in the **Maintenance request type** field, select the type of maintenance request.</span></span> <span data-ttu-id="e38c2-112">Um tipo padrão é sugerido.</span><span class="sxs-lookup"><span data-stu-id="e38c2-112">A default type is suggested.</span></span>
4. <span data-ttu-id="e38c2-113">No campo **Descrição**, insira um nome ou título que descreva resumidamente a solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="e38c2-113">In the **Description** field, enter a name or title that briefly describes the maintenance request.</span></span>
5. <span data-ttu-id="e38c2-114">Nos campos **Local funcional** e **Ativo**, selecione um local funcional ou ativo, ou uma combinação de um local funcional e um ativo, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="e38c2-114">In the **Functional location** and **Asset** fields, select a functional location or an asset, or a combination of a functional location and an asset, as you require.</span></span> <span data-ttu-id="e38c2-115">Crie uma solicitação de manutenção sem selecionar um ativo. O ativo poderá ser adicionado à solicitação de manutenção posteriormente.</span><span class="sxs-lookup"><span data-stu-id="e38c2-115">You can create a maintenance request without selecting an asset, and the asset can be added to the maintenance request later.</span></span> <span data-ttu-id="e38c2-116">Se o funcionário de manutenção que está conectado estiver relacionado a um recurso relativo a um ativo, o campo **Ativo** será definido automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e38c2-116">If the maintenance worker who is signed in is related to a resource that is related to an asset, the **Asset** field is automatically set.</span></span>

    <span data-ttu-id="e38c2-117">Se uma solicitação de manutenção já estiver anexada ao ativo selecionado, uma barra de mensagem aparecerá na parte superior da caixa de diálogo **Criar solicitação** para notificá-lo sobre a ID da solicitação de manutenção existente.</span><span class="sxs-lookup"><span data-stu-id="e38c2-117">If a maintenance request is already attached to the selected asset, a message bar appears at the top of the **Create request** dialog box to notify you about the ID of the existing maintenance request.</span></span> <span data-ttu-id="e38c2-118">Uma barra de mensagem notifica-o também se o ativo é coberto por um contrato de garantia.</span><span class="sxs-lookup"><span data-stu-id="e38c2-118">A message bar also notifies you if the asset is covered by a warranty agreement.</span></span>

6. <span data-ttu-id="e38c2-119">No campo **Nível de serviço**, selecione um nível de serviço que indique a urgência da solicitação.</span><span class="sxs-lookup"><span data-stu-id="e38c2-119">In the **Service level** field, select a service level that indicates the urgency of the request.</span></span>
7. <span data-ttu-id="e38c2-120">Se você selecionou um ativo na etapa 5, poderá usar os campos **Sintoma de falha**, **Área com falha** e **Tipo de falha** para criar um registro com falha.</span><span class="sxs-lookup"><span data-stu-id="e38c2-120">If you selected an asset in step 5, you can use the **Fault symptom**, **Fault area**, and **Fault type** fields to create a fault registration.</span></span>
8. <span data-ttu-id="e38c2-121">Se a solicitação de manutenção levou a um tempo de inatividade de manutenção, insira a data e a hora inicial do tempo de inatividade.</span><span class="sxs-lookup"><span data-stu-id="e38c2-121">If the maintenance request has caused maintenance downtime, enter the start date and time of the downtime.</span></span>

    <span data-ttu-id="e38c2-122">O campo **Iniciado por** é automaticamente definido com seu nome.</span><span class="sxs-lookup"><span data-stu-id="e38c2-122">The **Started by** field is automatically set to your name.</span></span>

10. <span data-ttu-id="e38c2-123">O campo **Início real** é automaticamente definido com a data e a hora atuais.</span><span class="sxs-lookup"><span data-stu-id="e38c2-123">The **Actual start** field is automatically set to the current date and time.</span></span> <span data-ttu-id="e38c2-124">No entanto, você pode alterar o valor conforme desejado.</span><span class="sxs-lookup"><span data-stu-id="e38c2-124">However, you can change the value as you require.</span></span>
11. <span data-ttu-id="e38c2-125">No campo **Notas**, insira notas adicionais necessárias.</span><span class="sxs-lookup"><span data-stu-id="e38c2-125">In the **Notes** field, enter any additional notes that are required.</span></span>
12. <span data-ttu-id="e38c2-126">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e38c2-126">Select **OK**.</span></span>

![Criar solicitação de manutenção](media/03-manage-maintenance-requests.png)

## <a name="subsequent-processing-of-maintenance-requests"></a><span data-ttu-id="e38c2-128">Processamento subsequente de solicitações de manutenção</span><span class="sxs-lookup"><span data-stu-id="e38c2-128">Subsequent processing of maintenance requests</span></span>

<span data-ttu-id="e38c2-129">Após a criação de uma solicitação de manutenção, mas antes de convertê-la em uma ordem de serviço, várias informações devem ser atualizadas nela.</span><span class="sxs-lookup"><span data-stu-id="e38c2-129">After a maintenance request is created, but before it's converted to a work order, various information should be updated on it.</span></span> <span data-ttu-id="e38c2-130">Em geral, um planejador ou outro funcionário administrativo conclui essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="e38c2-130">Typically, a planner or another administrative employee completes this task.</span></span>

- <span data-ttu-id="e38c2-131">Na página **Todas as solicitações de serviço** ou **Solicitações de manutenção de ativos**, selecione a solicitação com a qual deseja trabalhar e **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e38c2-131">On the **All maintenance requests** or **Active maintenance requests** page, select the request to work with, and then select **Edit**.</span></span>

<span data-ttu-id="e38c2-132">Na exibição de detalhes, é possível atualizar várias informações.</span><span class="sxs-lookup"><span data-stu-id="e38c2-132">In the details view, you can update various information.</span></span> <span data-ttu-id="e38c2-133">Eis alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="e38c2-133">Here are some examples:</span></span>

- <span data-ttu-id="e38c2-134">Selecione e verifique o ativo.</span><span class="sxs-lookup"><span data-stu-id="e38c2-134">Select and verify the asset.</span></span> <span data-ttu-id="e38c2-135">Se precisar selecionar um ativo diferente depois, você poderá definir a opção **Ativo verificado** como **Não**.</span><span class="sxs-lookup"><span data-stu-id="e38c2-135">If you must select a different asset later, you can set the **Asset verified** option to **No**.</span></span>
- <span data-ttu-id="e38c2-136">Selecione um grupo de funcionários de manutenção responsáveis e/ou um funcionário de manutenção responsável.</span><span class="sxs-lookup"><span data-stu-id="e38c2-136">Select a responsible maintenance worker group and/or a responsible maintenance worker.</span></span> <span data-ttu-id="e38c2-137">Para obter mais informações sobre a configuração necessária, consulte [Funcionários de manutenção responsáveis](../setup-for-maintenance-requests/responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="e38c2-137">For more information about the required setup, see [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md).</span></span>
- <span data-ttu-id="e38c2-138">Selecione um tipo de trabalho de manutenção e, se essas informações forem relevantes, uma grade de trabalho de manutenção relacionada e um comércio de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e38c2-138">Select a maintenance job type and, if this information is relevant, a related maintenance job variant and a job trade.</span></span>
- <span data-ttu-id="e38c2-139">Nos campos **Latitude** e **Longitude**, insira coordenadas geográficas.</span><span class="sxs-lookup"><span data-stu-id="e38c2-139">In the **Latitude** and **Longitude** fields, enter geographic coordinates.</span></span> <span data-ttu-id="e38c2-140">Todas as coordenadas adicionadas a uma solicitação de manutenção são transferidas automaticamente a uma ordem de serviço relacionada.</span><span class="sxs-lookup"><span data-stu-id="e38c2-140">Any coordinates that are added to a maintenance request are automatically transferred to a related work order.</span></span> 

![Atualizar solicitação de manutenção](media/04-manage-maintenance-requests.png)

> [!NOTE]
> <span data-ttu-id="e38c2-142">Se você selecionar um ativo ao criar uma solicitação de manutenção, poderá adicionar uma falha no ativo.</span><span class="sxs-lookup"><span data-stu-id="e38c2-142">If you select an asset when you create a maintenance request, you can add one fault to the asset.</span></span> <span data-ttu-id="e38c2-143">Quando a solicitação de manutenção for criada, você poderá adicionar mais falhas, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="e38c2-143">After the maintenance request has been created, you can add more faults, as you require.</span></span> <span data-ttu-id="e38c2-144">Para adicionar falhas, selecione **Falha de ativo** na página **Todas as solicitações de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="e38c2-144">To add faults, select **Asset fault** on the **All maintenance requests** page.</span></span>
