---
title: Visão geral dos alertas
description: Este tópico fornece informações gerais sobre alertas. Você pode usar alertas para manter-se informado sobre os eventos que deseja acompanhar durante o dia útil.
author: tjvass
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: a42e836c0b72798de3375c169e45b121debd55ec
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2191261"
---
# <a name="alerts-overview"></a><span data-ttu-id="e64c6-104">Visão geral dos alertas</span><span class="sxs-lookup"><span data-stu-id="e64c6-104">Alerts overview</span></span>

[!include [banner](../includes/banner.md)]

## <a name="about-alerts"></a><span data-ttu-id="e64c6-105">Sobre alertas</span><span class="sxs-lookup"><span data-stu-id="e64c6-105">About alerts</span></span>
<span data-ttu-id="e64c6-106">Os alertas formam um sistema de notificação de eventos críticos no sistema.</span><span class="sxs-lookup"><span data-stu-id="e64c6-106">Alerts form a notification system for critical events in the system.</span></span> <span data-ttu-id="e64c6-107">Você pode usar alertas para manter-se informado sobre os eventos que deseja acompanhar durante o dia útil.</span><span class="sxs-lookup"><span data-stu-id="e64c6-107">You can use alerts to stay informed about events that you want to track during the workday.</span></span> <span data-ttu-id="e64c6-108">Você pode criar facilmente seu próprio conjunto de regras de alerta para ser alertado sobre entregas atrasadas, ordens excluídas, preços alterados ou outros eventos pelos quais você deve ser o responsável.</span><span class="sxs-lookup"><span data-stu-id="e64c6-108">You can easily create your own set of alert rules so that you're alerted about deliveries that are overdue, orders that are deleted, prices that change, or other events that you must respond to.</span></span>

<span data-ttu-id="e64c6-109">No planejamento de recursos empresariais (ERP), há vários cenários típicos em que é possível usar o recurso de alertas.</span><span class="sxs-lookup"><span data-stu-id="e64c6-109">In enterprise resource planning (ERP), there are several typical scenarios where the alerts feature can be used.</span></span> <span data-ttu-id="e64c6-110">Aqui estão alguns exemplos.</span><span class="sxs-lookup"><span data-stu-id="e64c6-110">Here are some examples.</span></span>

### <a name="scenario-1-create-an-alert-rule-for-new-sales-orders"></a><span data-ttu-id="e64c6-111">Cenário 1: Criar uma regra de alerta para novas ordens de venda</span><span class="sxs-lookup"><span data-stu-id="e64c6-111">Scenario 1: Create an alert rule for new sales orders</span></span>

1. <span data-ttu-id="e64c6-112">Abra a página **Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="e64c6-112">Open the **All sales orders** page.</span></span>
2. <span data-ttu-id="e64c6-113">No Painel de Ação, na guia **Opções**, no grupo **Compartilhar**, selecione **Criar um alerta personalizado**.</span><span class="sxs-lookup"><span data-stu-id="e64c6-113">On the Action Pane, on the **Options** tab, in the **Share** group, select **Create a custom alert**.</span></span>
3. <span data-ttu-id="e64c6-114">Na caixa de diálogo **Criar regra de alerta**, na guia rápida **Alertar-me quando**, no campo **Evento**, selecione **O registro foi criado**.</span><span class="sxs-lookup"><span data-stu-id="e64c6-114">In the **Create alert rule** dialog box, on the **Alert me when** FastTab, in the **Event** field, select **Record has been created**.</span></span>

### <a name="scenario-2-create-an-alert-rule-for-postponement-of-a-delivery-date"></a><span data-ttu-id="e64c6-115">Cenário 2: Criar uma regra de alerta para o adiamento de uma data de entrega</span><span class="sxs-lookup"><span data-stu-id="e64c6-115">Scenario 2: Create an alert rule for postponement of a delivery date</span></span>

1. <span data-ttu-id="e64c6-116">Abra a página **Todas as ordens de compra**.</span><span class="sxs-lookup"><span data-stu-id="e64c6-116">Open the **All purchase orders** page.</span></span>
2. <span data-ttu-id="e64c6-117">Selecione um ID da ordem de compra para acessar os detalhes da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="e64c6-117">Select a purchase order ID to access the purchase order details.</span></span>
3. <span data-ttu-id="e64c6-118">Expanda a guia rápida **cabeçalho da Ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="e64c6-118">Expand the **Purchase order header** FastTab.</span></span>
4. <span data-ttu-id="e64c6-119">No Painel de Ação, na guia **Opções**, no grupo **Compartilhar**, selecione **Criar um alerta personalizado**.</span><span class="sxs-lookup"><span data-stu-id="e64c6-119">On the Action Pane, on the **Options** tab, in the **Share** group, select **Create a custom alert**.</span></span>
5. <span data-ttu-id="e64c6-120">Na caixa de diálogo **Criar regra de alerta**, na guia rápida **Alertar-me quando**, no campo **Campo**, selecione **Data de entrega**.</span><span class="sxs-lookup"><span data-stu-id="e64c6-120">In the **Create alert rule** dialog box, on the **Alert me when** FastTab, in the **Field** field, select **Delivery date**.</span></span>
6. <span data-ttu-id="e64c6-121">No campo **Evento**, selecione **foi adiado**.</span><span class="sxs-lookup"><span data-stu-id="e64c6-121">In the **Event** field, select **has been postponed**.</span></span>
    
<span data-ttu-id="e64c6-122">Depois que você fechar a caixa de diálogo **Criar regra de alerta**, sua regra aparecerá na página **Gerenciar regras de alerta**.</span><span class="sxs-lookup"><span data-stu-id="e64c6-122">After you close the **Create alert rule** dialog box, your rule appears on the **Manage alert rules** page.</span></span> <span data-ttu-id="e64c6-123">Você pode usar a página **Gerenciar regras de alerta** para atualizar suas regras de alerta existentes.</span><span class="sxs-lookup"><span data-stu-id="e64c6-123">You can use the **Manage alert rules** page to update your existing alert rules.</span></span> <span data-ttu-id="e64c6-124">Por exemplo, você pode alterar os disparadores do evento, atualizar as notificações de eventos e atualizar as datas de vencimento.</span><span class="sxs-lookup"><span data-stu-id="e64c6-124">For example, you can modify event triggers, update event notifications, and update expiration dates.</span></span> <span data-ttu-id="e64c6-125">Para abrir a página **Gerenciar regras de alerta**, use o botão **Alertar-me** na guia **Opções** do Painel de Ação.</span><span class="sxs-lookup"><span data-stu-id="e64c6-125">To open the **Manage alert rules** page, use the **Alert me** button on the **Options** tab of the Action Pane.</span></span>

## <a name="what-occurs-when-an-alert-rule-is-created"></a><span data-ttu-id="e64c6-126">O que acontece quando uma regra de alerta é criada?</span><span class="sxs-lookup"><span data-stu-id="e64c6-126">What occurs when an alert rule is created?</span></span>

<span data-ttu-id="e64c6-127">Ao criar regras de alerta, é possível associar um evento predefinido com um campo específico.</span><span class="sxs-lookup"><span data-stu-id="e64c6-127">When you create alert rules, you can associate a predefined event with a specific field.</span></span> <span data-ttu-id="e64c6-128">Por exemplo, a data especificada no campo é atingida ou o conteúdo do campo é alterado.</span><span class="sxs-lookup"><span data-stu-id="e64c6-128">For example, the date that is specified in the field arrives, or the contents of the field change.</span></span> <span data-ttu-id="e64c6-129">Como alternativa, é possível associar um evento aos registros de uma página específica.</span><span class="sxs-lookup"><span data-stu-id="e64c6-129">Alternatively, you can associate an event with the records on a specific page.</span></span> <span data-ttu-id="e64c6-130">Por exemplo, um registro é criado ou um registro é excluído.</span><span class="sxs-lookup"><span data-stu-id="e64c6-130">For example, a record is created, or a record is deleted.</span></span>

<span data-ttu-id="e64c6-131">Quando o evento selecionado ocorre para o campo ou para um registro da página, um alerta é enviado a você.</span><span class="sxs-lookup"><span data-stu-id="e64c6-131">When the selected event occurs for the field or for a record on the page, an alert is sent to you.</span></span> <span data-ttu-id="e64c6-132">Por exemplo, você cria uma regra na qual associa o campo **Data de entrega** em uma linha específica da ordem de compra ao evento **venceu neste período**.</span><span class="sxs-lookup"><span data-stu-id="e64c6-132">For example, you create a rule where you associate the **Delivery date** field on a specific purchase order line with the **was due this amount of time ago** event.</span></span> <span data-ttu-id="e64c6-133">Você define o período como cinco dias.</span><span class="sxs-lookup"><span data-stu-id="e64c6-133">You set the time frame to five days.</span></span> <span data-ttu-id="e64c6-134">Neste caso, um alerta é enviado cinco dias após a data de entrega dessa linha de ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="e64c6-134">In this case, an alert is sent five days after the delivery date of that purchase order line.</span></span>

<span data-ttu-id="e64c6-135">Além disso, é possível refinar as regras de alerta definindo as condições.</span><span class="sxs-lookup"><span data-stu-id="e64c6-135">Additionally, you can refine alert rules by setting conditions.</span></span> <span data-ttu-id="e64c6-136">Por exemplo, você pode ser alertado sobre novas ordens de compra criadas para contas de fornecedor específicas.</span><span class="sxs-lookup"><span data-stu-id="e64c6-136">For example, you can be alerted about new purchase orders that are created for specific vendor accounts.</span></span>

## <a name="preparing-for-an-alert"></a><span data-ttu-id="e64c6-137">Preparando um alerta</span><span class="sxs-lookup"><span data-stu-id="e64c6-137">Preparing for an alert</span></span>

<span data-ttu-id="e64c6-138">Antes de configurar uma regra de alerta, decida quando ou em quais situações deseja receber alertas.</span><span class="sxs-lookup"><span data-stu-id="e64c6-138">Before you set up an alert rule, decide when or in what situations you want to receive alerts.</span></span> <span data-ttu-id="e64c6-139">Quando você souber sobre qual evento deseja ser notificado, localize a página onde aparecem os dados que causam o evento.</span><span class="sxs-lookup"><span data-stu-id="e64c6-139">When you know which event you want to be notified about, find the page where the data that causes that event appears.</span></span> <span data-ttu-id="e64c6-140">O evento pode ser uma data de ocorrência ou uma alteração específica que ocorra.</span><span class="sxs-lookup"><span data-stu-id="e64c6-140">The event can be a date that arrives or a specific change that occurs.</span></span> <span data-ttu-id="e64c6-141">Portanto, você deve encontrar a página na qual a data é especificada ou onde aparece o campo que é alterado ou o novo registro que é criado.</span><span class="sxs-lookup"><span data-stu-id="e64c6-141">Therefore, you must find the page where the date is specified, or where the field that changes or the new record that is created appears.</span></span> <span data-ttu-id="e64c6-142">Quando tiver estas informações, você poderá criar a regra de alerta.</span><span class="sxs-lookup"><span data-stu-id="e64c6-142">After you have this information, you can create the alert rule.</span></span>

## <a name="components-of-an-alert-rule"></a><span data-ttu-id="e64c6-143">Componentes de uma regra de alerta</span><span class="sxs-lookup"><span data-stu-id="e64c6-143">Components of an alert rule</span></span>

<span data-ttu-id="e64c6-144">Uma regra de alerta tem cinco componentes:</span><span class="sxs-lookup"><span data-stu-id="e64c6-144">An alert rule has five components:</span></span>

- <span data-ttu-id="e64c6-145">**Evento** – O evento que aciona uma regra de alerta pode ser uma data de ocorrência ou uma alteração específica que ocorre.</span><span class="sxs-lookup"><span data-stu-id="e64c6-145">**Event** – The event that triggers an alert rule can be a date that arrives or a specific change that occurs.</span></span> <span data-ttu-id="e64c6-146">Você define eventos na guia rápida **Enviar alertas de email para alterações do status do trabalho** da caixa de diálogo **Criar regra de alerta**.</span><span class="sxs-lookup"><span data-stu-id="e64c6-146">You define events on the **Send email alerts for job status changes** FastTab of the **Create alert rule** dialog box.</span></span>
- <span data-ttu-id="e64c6-147">**Condição** – Na guia rápida **Alertar-me para** da caixa de diálogo **Criar regra de alerta**, você pode selecionar o escopo da condição para controlar quando será alertado sobre os eventos.</span><span class="sxs-lookup"><span data-stu-id="e64c6-147">**Condition** – On the **Alert me for** FastTab of the **Create alert rule** dialog box, you can select the scope of the condition, to control when you're alerted about events.</span></span> <span data-ttu-id="e64c6-148">Você pode aplicar a regra no registro atual ou apenas em todos os registros visíveis da página.</span><span class="sxs-lookup"><span data-stu-id="e64c6-148">You can apply the rule either to the current record only or to all visible records on the page.</span></span> <span data-ttu-id="e64c6-149">Se a regra se aplicar em entidades legais, você pode definir a opção **Em toda a organização** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="e64c6-149">If the rule applies across legal entities, you can set the **Organization-wide** option to **Yes**.</span></span>
- <span data-ttu-id="e64c6-150">**Expiração da regra** – Na guia rápida **Alertar-me até** da caixa de diálogo **Criar regra de alerta**, você pode especificar por quanto tempo a regra de alerta deve ficar ativa.</span><span class="sxs-lookup"><span data-stu-id="e64c6-150">**Expiry of rule** – On the **Alert me until** FastTab of the **Create alert rule** dialog box, you can specify how long the alert rule should be active.</span></span>
- <span data-ttu-id="e64c6-151">**Conteúdo** – Na guia rápida **Alertar-me com** da caixa de diálogo **Criar regra de alerta** é possível especificar o texto do assunto e o texto da mensagem que as mensagens de alerta devem usar.</span><span class="sxs-lookup"><span data-stu-id="e64c6-151">**Contents** – On the **Alert me with** FastTab of the **Create alert rule** dialog box, you can specify the subject text and message text that the alert messages should use.</span></span>
- <span data-ttu-id="e64c6-152">**Usuário** – Na guia rápida **Quem alertar** da caixa de diálogo **Criar regra de alerta** é possível especificar qual usuário deve receber as mensagens de alerta.</span><span class="sxs-lookup"><span data-stu-id="e64c6-152">**User** – On the **Alert who** FastTab of the **Create alert rule** dialog box, you can specify which user should receive the alert messages.</span></span> <span data-ttu-id="e64c6-153">Por padrão, seu ID de usuário é selecionado.</span><span class="sxs-lookup"><span data-stu-id="e64c6-153">By default, your user ID is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e64c6-154">Esta opção está restrita a administradores da organização.</span><span class="sxs-lookup"><span data-stu-id="e64c6-154">This option is restricted to organization administrators.</span></span>

## <a name="email-notifications-from-alerts"></a><span data-ttu-id="e64c6-155">Notificações por email de alertas</span><span class="sxs-lookup"><span data-stu-id="e64c6-155">Email notifications from alerts</span></span>

<span data-ttu-id="e64c6-156">As notificações por email de alertas ainda não estão habilitadas.</span><span class="sxs-lookup"><span data-stu-id="e64c6-156">Email notifications from alerts are not yet enabled.</span></span> <span data-ttu-id="e64c6-157">Isso será habilitado em uma atualização futura.</span><span class="sxs-lookup"><span data-stu-id="e64c6-157">This will be enabled in a future update.</span></span>

## <a name="videos"></a><span data-ttu-id="e64c6-158">Vídeos</span><span class="sxs-lookup"><span data-stu-id="e64c6-158">Videos</span></span>

### <a name="how-to-use-alerts-to-monitor-filtered-data"></a><span data-ttu-id="e64c6-159">Como usar alertas para monitorar dados filtrados</span><span class="sxs-lookup"><span data-stu-id="e64c6-159">How to use alerts to monitor filtered data</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3DWZ3]

<span data-ttu-id="e64c6-160">O vídeo [Como usar alertas para monitorar dados filtrados](https://youtu.be/ZYKMcv6kl9s) (exibido acima) está incluído na [playlist Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponível no YouTube.</span><span class="sxs-lookup"><span data-stu-id="e64c6-160">The [How to use alerts to monitor filtered data](https://youtu.be/ZYKMcv6kl9s) video (shown above) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

### <a name="alert-rule-options"></a><span data-ttu-id="e64c6-161">Opções de regras de alerta</span><span class="sxs-lookup"><span data-stu-id="e64c6-161">Alert rule options</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3E4PV]

<span data-ttu-id="e64c6-162">O vídeo [Opções de regras de alerta](https://youtu.be/cpzimwOjicM) (mostrado acima) está incluído na [playlist Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponível no YouTube.</span><span class="sxs-lookup"><span data-stu-id="e64c6-162">The [Alert rule options](https://youtu.be/cpzimwOjicM) video (shown above) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>


