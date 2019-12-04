---
title: Criar regras de alerta
description: Este tópico fornece informações sobre os alertas e explica como criar uma regra de alerta para que você seja notificado sobre eventos, como uma data do evento ou uma alteração específica que ocorra.
author: tjvass
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: c37ddc52ef576a15dd35cc155e99821c74631a46
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180705"
---
# <a name="create-alert-rules"></a><span data-ttu-id="52639-103">Criar regras de alerta</span><span class="sxs-lookup"><span data-stu-id="52639-103">Create alert rules</span></span>

[!include [banner](../includes/banner.md)]

## <a name="getting-started"></a><span data-ttu-id="52639-104">Introdução</span><span class="sxs-lookup"><span data-stu-id="52639-104">Getting started</span></span>

<span data-ttu-id="52639-105">Antes de configurar uma regra de alerta, decida quando ou em quais situações deseja receber alertas.</span><span class="sxs-lookup"><span data-stu-id="52639-105">Before you set up an alert rule, decide when or in what situations you want to receive alerts.</span></span> <span data-ttu-id="52639-106">Quando você souber sobre qual evento deseja ser notificado, localize a página onde aparecem os dados que causam o evento.</span><span class="sxs-lookup"><span data-stu-id="52639-106">When you know which event you want to be notified about, find the page where the data that causes that event appears.</span></span> <span data-ttu-id="52639-107">O evento pode ser uma data de ocorrência ou uma alteração específica que ocorra.</span><span class="sxs-lookup"><span data-stu-id="52639-107">The event can be a date that arrives or a specific change that occurs.</span></span> <span data-ttu-id="52639-108">Portanto, você deve encontrar a página na qual a data é especificada ou onde aparece o campo que é alterado ou o novo registro que é criado.</span><span class="sxs-lookup"><span data-stu-id="52639-108">Therefore, you must find the page where the date is specified, or where the field that changes or the new record that is created appears.</span></span> <span data-ttu-id="52639-109">Quando tiver estas informações, você poderá criar a regra de alerta.</span><span class="sxs-lookup"><span data-stu-id="52639-109">After you have this information, you can create the alert rule.</span></span>

<span data-ttu-id="52639-110">Quando cria uma regra de alerta, você define os critérios que o sistema deve atender para que um alerta seja acionado.</span><span class="sxs-lookup"><span data-stu-id="52639-110">When you create an alert rule, you define the criteria that must be met before an alert is triggered.</span></span> <span data-ttu-id="52639-111">Pense nos critérios como uma coincidência entre a ocorrência de um evento e o preenchimento de condições específicas.</span><span class="sxs-lookup"><span data-stu-id="52639-111">You can think of criteria as a match between the occurrence of an event and the fulfillment of specific conditions.</span></span> <span data-ttu-id="52639-112">Quando um evento ocorre, o sistema inicia a verificação de acordo com as condições configuradas.</span><span class="sxs-lookup"><span data-stu-id="52639-112">When an event occurs, the system starts to perform a check according to the conditions that are set up.</span></span>

## <a name="events"></a><span data-ttu-id="52639-113">Eventos</span><span class="sxs-lookup"><span data-stu-id="52639-113">Events</span></span>

<span data-ttu-id="52639-114">O evento que aciona uma regra de alerta pode ser uma data que se aproxima ou uma alteração específica que ocorre.</span><span class="sxs-lookup"><span data-stu-id="52639-114">The event that triggers an alert rule can be a date that arrives or a specific change that occurs.</span></span> <span data-ttu-id="52639-115">Os disparadores de eventos são definidos na Guia rápida **Alertar-me quando** da caixa de diálogo **Criar regra de alerta**.</span><span class="sxs-lookup"><span data-stu-id="52639-115">Triggers for events are defined on the **Alert me when** FastTab of the **Create alert rule** dialog box.</span></span> <span data-ttu-id="52639-116">Os eventos disponíveis para um determinado campo dependem do disparador que é selecionado.</span><span class="sxs-lookup"><span data-stu-id="52639-116">The events that are available for a particular field depend on the trigger that is selected.</span></span>

<span data-ttu-id="52639-117">Por exemplo, se estiver configurando uma regra de alerta para o campo **Data de início**, os eventos da data de vencimento são apropriados.</span><span class="sxs-lookup"><span data-stu-id="52639-117">For example, if you're setting up an alert rule for the **Start date** field, due date events are appropriate.</span></span> <span data-ttu-id="52639-118">Portanto, o tipo de evento **vence em** fica disponível para aquele campo.</span><span class="sxs-lookup"><span data-stu-id="52639-118">Therefore, the **is due in** event type is available for that field.</span></span> <span data-ttu-id="52639-119">Porém, para um campo como **Centro de custo**, um evento de data de vencimento não é apropriado.</span><span class="sxs-lookup"><span data-stu-id="52639-119">However, for a field such as **Cost center**, a due date event isn't appropriate.</span></span> <span data-ttu-id="52639-120">Portanto, o tipo de evento **vence em** não fica disponível.</span><span class="sxs-lookup"><span data-stu-id="52639-120">Therefore, the **is due in** event type isn't available.</span></span> <span data-ttu-id="52639-121">Em vez disso, o tipo de evento **foi alterado** estará disponível.</span><span class="sxs-lookup"><span data-stu-id="52639-121">Instead, the **has changed** event type is available.</span></span>

## <a name="event-types"></a><span data-ttu-id="52639-122">Tipos de evento</span><span class="sxs-lookup"><span data-stu-id="52639-122">Event types</span></span>

<span data-ttu-id="52639-123">Três tipos de evento podem ocorrer:</span><span class="sxs-lookup"><span data-stu-id="52639-123">Three types of events can occur:</span></span>

- <span data-ttu-id="52639-124">**Eventos do tipo Criar ou excluir** – Esses eventos disparam um alerta quando um registro é criado ou excluído.</span><span class="sxs-lookup"><span data-stu-id="52639-124">**Create-type and delete-type events** – These events trigger an alert when a record is created or deleted.</span></span>
- <span data-ttu-id="52639-125">**Eventos do tipo Atualizar** – Esses eventos acionam um alerta quando os dados de um campo específico são alterados.</span><span class="sxs-lookup"><span data-stu-id="52639-125">**Update-type events** – These events trigger an alert when the data in a specific field changes.</span></span>
- <span data-ttu-id="52639-126">**Eventos do tipo Data de vencimento** – Esses eventos disparam um alerta quando chega uma data.</span><span class="sxs-lookup"><span data-stu-id="52639-126">**Due date-type events** – These events trigger an alert when a date arrives.</span></span>
    
<span data-ttu-id="52639-127">As alterações ocorridas podem ser iniciadas por um usuário.</span><span class="sxs-lookup"><span data-stu-id="52639-127">Changes that occur can be initiated by a user.</span></span> <span data-ttu-id="52639-128">Por exemplo, um usuário altera a data de entrega de uma ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="52639-128">For example, a user changes the delivery date of a purchase order.</span></span> <span data-ttu-id="52639-129">Como alternativa, as alterações podem ocorrer como parte de um processo.</span><span class="sxs-lookup"><span data-stu-id="52639-129">Alternatively, changes can occur as part of a process.</span></span> <span data-ttu-id="52639-130">Por exemplo, o campo **Status** em uma página é alterado para refletir o ciclo de vida de vários processos no sistema.</span><span class="sxs-lookup"><span data-stu-id="52639-130">For example, the **Status** field on a page changes to reflect the life cycle of various processes in the system.</span></span>

## <a name="conditions"></a><span data-ttu-id="52639-131">Condições</span><span class="sxs-lookup"><span data-stu-id="52639-131">Conditions</span></span>

<span data-ttu-id="52639-132">Na guia rápida **Alertar-me para** da caixa de diálogo **Criar regra de alerta**, você pode usar condições para controlar quando você será alertado sobre os eventos.</span><span class="sxs-lookup"><span data-stu-id="52639-132">On the **Alert me for** FastTab of the **Create alert rule** dialog box, you can use conditions to control when you're alerted about events.</span></span>

<span data-ttu-id="52639-133">Por exemplo, você pode especificar que o sistema deve alertá-lo quando o status das ordens de compra for alterado, mas apenas se o status corresponder a um determinado conjunto de condições.</span><span class="sxs-lookup"><span data-stu-id="52639-133">For example, you can specify that the system should alert you when the status of purchase orders changes, but only if the status matches a specific set of conditions.</span></span> <span data-ttu-id="52639-134">Especificamente, você quer ser alertado quando o status de uma ordem de compra for alterado para **Recebido**.</span><span class="sxs-lookup"><span data-stu-id="52639-134">Specifically, you want to be alerted when the status of a purchase order is set to **Received**.</span></span> <span data-ttu-id="52639-135">Essa alteração no status é o evento que aciona o alerta.</span><span class="sxs-lookup"><span data-stu-id="52639-135">This change in status is the event that triggers the alert.</span></span>

<span data-ttu-id="52639-136">Em seguida, você deverá decidir sobre quais ordens de compra você deseja ser alertado.</span><span class="sxs-lookup"><span data-stu-id="52639-136">Next, you must decide which purchase orders you want to be alerted about.</span></span> <span data-ttu-id="52639-137">Por exemplo, você pode selecionar uma das opções a seguir.</span><span class="sxs-lookup"><span data-stu-id="52639-137">For example, you can select one of the following options.</span></span> <span data-ttu-id="52639-138">Essas opções definem as condições da regra do alerta.</span><span class="sxs-lookup"><span data-stu-id="52639-138">These options define the conditions for the alert rule.</span></span>

- <span data-ttu-id="52639-139">**Registro selecionado atual** – Você recebe um alerta quando o status de uma ordem de compra específica for alterado para **Recebido**.</span><span class="sxs-lookup"><span data-stu-id="52639-139">**Current selected record** – You receive an alert when the status of a specific purchase order changes to **Received**.</span></span>
- <span data-ttu-id="52639-140">**Todos os registros** – Você receberá um alerta quando o status de uma ordem de compra for alterado para um item na exibição da página ativa.</span><span class="sxs-lookup"><span data-stu-id="52639-140">**All records** – You receive an alert when the status of a purchase order is changed for an item in the active page view.</span></span> <span data-ttu-id="52639-141">Você pode usar a filtragem avançada disponível na página criar regras para criar regras para um conjunto específico de registros.</span><span class="sxs-lookup"><span data-stu-id="52639-141">You can use the advanced filtering that is available on the page to create rules for a specific set of records.</span></span> <span data-ttu-id="52639-142">Por exemplo, você pode criar um alerta que é disparado para todas as ordens de compra dos clientes em um grupo de clientes específico.</span><span class="sxs-lookup"><span data-stu-id="52639-142">For example, you can create an alert that is triggered for all purchase orders for the customers in a specific customer group.</span></span>
    
## <a name="expiry-of-rule"></a><span data-ttu-id="52639-143">Vencimento da regra</span><span class="sxs-lookup"><span data-stu-id="52639-143">Expiry of rule</span></span>

<span data-ttu-id="52639-144">Na guia rápida **Alertar-me até** da caixa de diálogo **Criar regra de alerta**, você pode especificar quanto tempo a regra de alerta deve ficar ativa.</span><span class="sxs-lookup"><span data-stu-id="52639-144">On the **Alert me until** FastTab of the **Create alert rule** dialog box, you can specify how long the alert rule should be active.</span></span>

## <a name="alert-contents"></a><span data-ttu-id="52639-145">Conteúdo do alerta</span><span class="sxs-lookup"><span data-stu-id="52639-145">Alert contents</span></span>

<span data-ttu-id="52639-146">Na guia rápida **Alertar-me com** da caixa de diálogo **Criar regra de alerta**, você pode especificar o texto do assunto e o texto da mensagem que as mensagens de alerta devem usar.</span><span class="sxs-lookup"><span data-stu-id="52639-146">On the **Alert me with** FastTab of the **Create alert rule** dialog box, you can specify the subject text and message text that the alert messages should use.</span></span>

## <a name="user-id"></a><span data-ttu-id="52639-147">ID do usuário</span><span class="sxs-lookup"><span data-stu-id="52639-147">User ID</span></span>

<span data-ttu-id="52639-148">Na guia rápida **Alertar-me com** da caixa de diálogo **Criar regra de alerta**, você pode especificar qual usuário deve receber as mensagens de alerta.</span><span class="sxs-lookup"><span data-stu-id="52639-148">On the **Alert me with** FastTab of the **Create alert rule** dialog box, you can specify which user should receive the alert messages.</span></span> <span data-ttu-id="52639-149">Por padrão, seu ID de usuário é selecionado.</span><span class="sxs-lookup"><span data-stu-id="52639-149">By default, your user ID is selected.</span></span> <span data-ttu-id="52639-150">Esta opção está restrita a administradores da organização.</span><span class="sxs-lookup"><span data-stu-id="52639-150">This option is restricted to organization administrators.</span></span>

## <a name="create-an-alert-rule"></a><span data-ttu-id="52639-151">Crie uma regra de alerta</span><span class="sxs-lookup"><span data-stu-id="52639-151">Create an alert rule</span></span>

1. <span data-ttu-id="52639-152">Abra a página que contém os dados a serem monitorados.</span><span class="sxs-lookup"><span data-stu-id="52639-152">Open the page that contains the data to monitor.</span></span>
2. <span data-ttu-id="52639-153">No Painel de Ação, na guia **Opções**, no grupo **Compartilhar**, selecione **Criar regra de alerta**.</span><span class="sxs-lookup"><span data-stu-id="52639-153">On the Action Pane, on the **Options** tab, in the **Share** group, select **Create alert rule**.</span></span>
3. <span data-ttu-id="52639-154">Na caixa de diálogo **Criar regra de alerta**, no campo **Campo**, selecione o campo a ser monitorado.</span><span class="sxs-lookup"><span data-stu-id="52639-154">In the **Create alert rule** dialog box, in the **Field** field, select the field to monitor.</span></span>
4. <span data-ttu-id="52639-155">No campo **Evento**, selecione o tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="52639-155">In the **Event** field, select the type of event.</span></span>
5. <span data-ttu-id="52639-156">Na guia rápida **Alertar-me para**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="52639-156">On the **Alert me for** FastTab, select an option.</span></span>
6. <span data-ttu-id="52639-157">Caso você queira que a regra de alerta se torne ativa em uma determinada data, na guia rápida **Alertar-me até**, selecione uma data final.</span><span class="sxs-lookup"><span data-stu-id="52639-157">If the alert rule should become inactive on a specific date, on the **Alert me until** FastTab, select an end date.</span></span>
7. <span data-ttu-id="52639-158">Na guia rápida **Alertar-me com**, no campo **Assunto**, aceite o cabeçalho padrão do assunto para a mensagem de e-mail ou insira um novo assunto.</span><span class="sxs-lookup"><span data-stu-id="52639-158">On the **Alert me with** FastTab, in the **Subject** field, accept the default subject heading for the email message, or enter a new subject.</span></span> <span data-ttu-id="52639-159">O texto é usado como o título do assunto da mensagem de email recebida quando um alerta é acionado.</span><span class="sxs-lookup"><span data-stu-id="52639-159">The text is used as the subject heading for the email message that you receive when an alert is triggered.</span></span>
8. <span data-ttu-id="52639-160">No campo **Mensagem**, digite uma mensagem opcional.</span><span class="sxs-lookup"><span data-stu-id="52639-160">In the **Message** field, enter an optional message.</span></span> <span data-ttu-id="52639-161">O texto é usado como a mensagem recebida quando um alerta é acionado.</span><span class="sxs-lookup"><span data-stu-id="52639-161">The text is used as the message that you receive when an alert is triggered.</span></span>
9. <span data-ttu-id="52639-162">Selecione **OK** para salvar as configurações e criar a regra de alerta.</span><span class="sxs-lookup"><span data-stu-id="52639-162">Select **OK** to save the settings and create the alert rule.</span></span>