---
title: Notificações de execução do ciclo
description: Este tópico descreve as notificações de execução do ciclo e explica como configurá-las.
author: mirzaab
ms.date: 04/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WhsWaveNotificationPolicy, WHSParameters, WHSWaveTemplateTable, BusinessEventsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2022-04-01
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: fee112d3211f619b2146dd21c4f8a52ad33667d6
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019145"
---
# <a name="wave-execution-notifications"></a><span data-ttu-id="39c77-103">Notificações de execução do ciclo</span><span class="sxs-lookup"><span data-stu-id="39c77-103">Wave execution notifications</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="39c77-104">O recurso *Notificações de execução do ciclo* usa eventos comerciais e a Central de ações para entregar notificações relacionadas à execução do ciclo.</span><span class="sxs-lookup"><span data-stu-id="39c77-104">The *Wave execution notifications* feature uses business events and the Action center to deliver notifications that are related to wave execution.</span></span> <span data-ttu-id="39c77-105">Ele permite que você especifique os tipos de eventos que geram notificações, os depósitos que as geram e os usuários que as recebem.</span><span class="sxs-lookup"><span data-stu-id="39c77-105">It lets you specify the types of events that generate notifications, the warehouses that generate them, and the users who receive them.</span></span>

<span data-ttu-id="39c77-106">O botão **Mostrar mensagens** (símbolo de sino) no lado direito da barra de navegação indica quando uma mensagem da Central de ações está disponível para o usuário atual.</span><span class="sxs-lookup"><span data-stu-id="39c77-106">The **Show messages** button (bell symbol) on the right side of the navigation bar indicates when an Action center message is available for the current user.</span></span> <span data-ttu-id="39c77-107">O usuário pode selecionar o botão **Mostrar mensagens** para abrir a Central de ações e revisar as mensagens.</span><span class="sxs-lookup"><span data-stu-id="39c77-107">The user can select the **Show messages** button to open the Action center and review the messages.</span></span>

<span data-ttu-id="39c77-108">Os eventos comerciais ocorrem quando processos comerciais são executados.</span><span class="sxs-lookup"><span data-stu-id="39c77-108">Business events occur when business processes are run.</span></span> <span data-ttu-id="39c77-109">Os processos comerciais são compostos de tarefas.</span><span class="sxs-lookup"><span data-stu-id="39c77-109">Business processes are made up of tasks.</span></span> <span data-ttu-id="39c77-110">Durante um processo comercial, os usuários que participam dele executam ações comerciais para concluir essas tarefas.</span><span class="sxs-lookup"><span data-stu-id="39c77-110">During a business process, the users who participate in it perform business actions to complete those tasks.</span></span> <span data-ttu-id="39c77-111">Os eventos de negócios fornecem um mecanismo que permite que os sistemas externos recebam notificações de aplicativos do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="39c77-111">Business events provide a mechanism that lets external systems receive notifications from Finance and Operations applications.</span></span> <span data-ttu-id="39c77-112">Dessa forma, os sistemas podem executar ações comerciais em resposta aos eventos comerciais.</span><span class="sxs-lookup"><span data-stu-id="39c77-112">In this way, the systems can perform business actions in response to the business events.</span></span> <span data-ttu-id="39c77-113">Para obter mais informações, consulte [Visão geral de alertas comerciais](../../fin-ops-core/dev-itpro/business-events/home-page.md).</span><span class="sxs-lookup"><span data-stu-id="39c77-113">For more information, see [Business events overview](../../fin-ops-core/dev-itpro/business-events/home-page.md).</span></span>

## <a name="turn-on-the-wave-execution-notifications-feature"></a><span data-ttu-id="39c77-114">Ativar o recurso Notificações de execução do ciclo</span><span class="sxs-lookup"><span data-stu-id="39c77-114">Turn on the Wave execution notifications feature</span></span>

<span data-ttu-id="39c77-115">Antes de usar o recurso *Notificações de execução do ciclo*, ele deverá estar ativado no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="39c77-115">Before you can use the *Wave execution notifications* feature, it must be turned on in your system.</span></span> <span data-ttu-id="39c77-116">Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="39c77-116">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="39c77-117">Nesse caso, o recurso é listado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="39c77-117">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="39c77-118">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="39c77-118">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="39c77-119">**Nome do recurso:** *Notificações de execução do ciclo*</span><span class="sxs-lookup"><span data-stu-id="39c77-119">**Feature name:** *Wave execution notifications*</span></span>

## <a name="scenario-send-wave-batch-execution-notifications-to-the-action-center"></a><span data-ttu-id="39c77-120">Cenário: enviar notificações de execução em lotes do ciclo para a Central de ações</span><span class="sxs-lookup"><span data-stu-id="39c77-120">Scenario: Send wave batch execution notifications to the Action center</span></span>

<span data-ttu-id="39c77-121">Este cenário mostra o fluxo de ponta a ponta para enviar notificações sobre erros de execução em lotes de ciclos a uma função específica por meio da Central de ações.</span><span class="sxs-lookup"><span data-stu-id="39c77-121">This scenario shows the end-to-end flow for sending notifications about wave batch execution errors to a specific role via the Action center.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="39c77-122">Disponibilizar dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="39c77-122">Make demo data available</span></span>

<span data-ttu-id="39c77-123">Para seguir este cenário, você deve ter dados de demonstração instalados e deve selecionar a entidade legal **USMF**.</span><span class="sxs-lookup"><span data-stu-id="39c77-123">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-waves-are-run-in-batch-mode"></a><span data-ttu-id="39c77-124">Verificar se os ciclos são executados no modo de lote</span><span class="sxs-lookup"><span data-stu-id="39c77-124">Make sure that waves are run in batch mode</span></span>

1. <span data-ttu-id="39c77-125">Vá para **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**.</span><span class="sxs-lookup"><span data-stu-id="39c77-125">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="39c77-126">Na Guia Rápida **Processamento do ciclo**, defina a opção **Processar ciclos em lotes** como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="39c77-126">On the **Wave processing** FastTab, set the **Process waves in batch** option to *Yes*.</span></span>

> [!NOTE]
> <span data-ttu-id="39c77-127">Se você quiser desabilitar as notificações de execução em lotes do ciclo, defina a opção **Desabilitar notificações em lotes de processamento do ciclo** como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="39c77-127">If you want to disable wave batch execution notifications, set the **Disable wave processing batch notifications** option to *Yes*.</span></span>

### <a name="configure-a-wave-notification-policy"></a><span data-ttu-id="39c77-128">Configurar uma política de notificação do ciclo</span><span class="sxs-lookup"><span data-stu-id="39c77-128">Configure a wave notification policy</span></span>

<span data-ttu-id="39c77-129">As políticas de notificação do ciclo definem os tipos de notificação enviadas e os usuários notificados.</span><span class="sxs-lookup"><span data-stu-id="39c77-129">Wave notification policies define the types of notifications that are sent and the users who are notified.</span></span>

1. <span data-ttu-id="39c77-130">Vá para **Gerenciamento de depósito \> Configuração \> Ciclos \> Políticas de notificação do ciclo**.</span><span class="sxs-lookup"><span data-stu-id="39c77-130">Go to **Warehouse management \> Setup \> Waves \> Wave notification policies**.</span></span>
1. <span data-ttu-id="39c77-131">Crie um registro com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="39c77-131">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="39c77-132">**Política de notificação do ciclo:** *24BatchError*</span><span class="sxs-lookup"><span data-stu-id="39c77-132">**Wave notification policy:** *24BatchError*</span></span>
    - <span data-ttu-id="39c77-133">**Descrição:** *Erro de lote do ciclo do Depósito 24*</span><span class="sxs-lookup"><span data-stu-id="39c77-133">**Description:** *Warehouse 24 wave batch error*</span></span>
    - <span data-ttu-id="39c77-134">**Enviar notificação em:** *Somente erro*</span><span class="sxs-lookup"><span data-stu-id="39c77-134">**Send notification on:** *Error only*</span></span>
    - <span data-ttu-id="39c77-135">**Para a função:** *Administrador do sistema*</span><span class="sxs-lookup"><span data-stu-id="39c77-135">**To role:** *System administrator*</span></span>

        > [!NOTE]
        > <span data-ttu-id="39c77-136">Como esse cenário usa dados de demonstração, a função *Administrador do sistema* foi selecionada para simplificar.</span><span class="sxs-lookup"><span data-stu-id="39c77-136">Because this scenario uses demo data, the *System administrator* role is selected for the sake of simplicity.</span></span> <span data-ttu-id="39c77-137">Portanto, como você está conectado como um usuário administrador do sistema, receberá as notificações.</span><span class="sxs-lookup"><span data-stu-id="39c77-137">Therefore, because you're signed in as a system administrator user, you will receive the notifications.</span></span> <span data-ttu-id="39c77-138">No entanto, na prática, geralmente você deve selecionar uma função mais específica para notificar sobre erros de execução de lotes do ciclo, como *Gerente de depósito*.</span><span class="sxs-lookup"><span data-stu-id="39c77-138">However, in practice, you should usually select a more specific role to notify about wave batch execution errors, such as *Warehouse manager*.</span></span>

1. <span data-ttu-id="39c77-139">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="39c77-139">On the Action Pane, select **Save**.</span></span>

### <a name="configure-a-wave-template"></a><span data-ttu-id="39c77-140">Configurar um modelo de onda</span><span class="sxs-lookup"><span data-stu-id="39c77-140">Configure a wave template</span></span>

<span data-ttu-id="39c77-141">Os modelos do ciclo permitem vincular instâncias específicas de métodos do ciclo a modelos de etiqueta do ciclo correspondentes.</span><span class="sxs-lookup"><span data-stu-id="39c77-141">Wave templates let you link specific instances of wave methods to corresponding wave label templates.</span></span>

1. <span data-ttu-id="39c77-142">Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos de onda**.</span><span class="sxs-lookup"><span data-stu-id="39c77-142">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="39c77-143">No painel de lista, defina o campo **Tipo de modelo do ciclo** como *Remessa* e selecione o modelo do ciclo *Remessa Padrão 24* para o depósito 24.</span><span class="sxs-lookup"><span data-stu-id="39c77-143">In the list pane, set the **Wave template type** field to *Shipping*, and then select the *24 Shipping Default* wave template for warehouse 24.</span></span>
1. <span data-ttu-id="39c77-144">Na Guia Rápida **Geral**, defina o campo **Política de notificação do ciclo** como *24BatchError*.</span><span class="sxs-lookup"><span data-stu-id="39c77-144">On the **General** FastTab, set the **Wave notification policy** field to *24BatchError*.</span></span>

### <a name="configure-a-work-template"></a><span data-ttu-id="39c77-145">Configurar um modelo de trabalho</span><span class="sxs-lookup"><span data-stu-id="39c77-145">Configure a work template</span></span>

<span data-ttu-id="39c77-146">Os modelos de trabalho são usados durante a execução do ciclo para gerar trabalho.</span><span class="sxs-lookup"><span data-stu-id="39c77-146">Work templates are used during wave execution to generate work.</span></span> <span data-ttu-id="39c77-147">Para este cenário, a execução do ciclo deve disparar um erro.</span><span class="sxs-lookup"><span data-stu-id="39c77-147">For this scenario, wave execution should trigger an error.</span></span> <span data-ttu-id="39c77-148">Ao configurar a consulta de modelo de trabalho para usar um depósito não existente, você garantirá que a execução do ciclo falhe e, dessa forma, envie uma notificação.</span><span class="sxs-lookup"><span data-stu-id="39c77-148">By setting the work template query to use a nonexistent warehouse, you will ensure that wave execution fails and therefore sends a notification.</span></span>

1. <span data-ttu-id="39c77-149">Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="39c77-149">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="39c77-150">No painel de lista, defina o campo **Tipo de modelo de trabalho** como *Ordens de venda* e selecione o modelo de trabalho *Preparo SO 24* para o depósito 24.</span><span class="sxs-lookup"><span data-stu-id="39c77-150">In the list pane, set the **Work template type** field to *Sales orders* and then select the *24 SO Stage* work template for warehouse 24.</span></span>
1. <span data-ttu-id="39c77-151">No Painel de Ações, selecione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="39c77-151">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="39c77-152">Na caixa de diálogo do editor de consultas, na guia **Intervalo**, edite a linha a seguir (ou adicione-a se ela não existir):</span><span class="sxs-lookup"><span data-stu-id="39c77-152">In the query editor dialog box, on the **Range** tab, edit the following row (or add it if it doesn't exist):</span></span>

    - <span data-ttu-id="39c77-153">**Tabela:** *Transações de trabalho temporário*</span><span class="sxs-lookup"><span data-stu-id="39c77-153">**Table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="39c77-154">**Tabela derivada:** *Transações de trabalho temporário*</span><span class="sxs-lookup"><span data-stu-id="39c77-154">**Derived table:** *Temporary work transactions*</span></span>
    - <span data-ttu-id="39c77-155">**Campo:** *Depósito*</span><span class="sxs-lookup"><span data-stu-id="39c77-155">**Field:** *Warehouse*</span></span>
    - <span data-ttu-id="39c77-156">**Critérios:** altere o valor de *24* para *Erro*.</span><span class="sxs-lookup"><span data-stu-id="39c77-156">**Criteria:** Change the value from *24* to *Error*.</span></span>

1. <span data-ttu-id="39c77-157">Selecione **OK** e confirme a alteração.</span><span class="sxs-lookup"><span data-stu-id="39c77-157">Select **OK**, and confirm the change.</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="39c77-158">Criar uma ordem de venda e liberá-la para o depósito</span><span class="sxs-lookup"><span data-stu-id="39c77-158">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="39c77-159">Vá para **Vendas e marketing \> Ordem de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="39c77-159">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="39c77-160">Crie uma ordem de venda com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="39c77-160">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="39c77-161">**Conta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="39c77-161">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="39c77-162">**Depósito:** *24*</span><span class="sxs-lookup"><span data-stu-id="39c77-162">**Warehouse:** *24*</span></span>

1. <span data-ttu-id="39c77-163">Na Guia Rápida **Linhas da ordem de venda**, adicione uma linha de ordem de venda que tenha as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="39c77-163">On the **Sales order lines** FastTab, add a sales order line that has the following settings:</span></span>

    - <span data-ttu-id="39c77-164">**Número de item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="39c77-164">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="39c77-165">**Quantidade:** *10*</span><span class="sxs-lookup"><span data-stu-id="39c77-165">**Quantity:** *10*</span></span>

    > [!NOTE]
    > <span data-ttu-id="39c77-166">Esses itens e quantidades são apenas exemplos.</span><span class="sxs-lookup"><span data-stu-id="39c77-166">These items and quantities are only examples.</span></span> <span data-ttu-id="39c77-167">O depósito especificado deve conter estoque suficiente.</span><span class="sxs-lookup"><span data-stu-id="39c77-167">The specified warehouse must contain enough stock.</span></span>

1. <span data-ttu-id="39c77-168">Com a nova linha de ordem ainda selecionada na Guia Rápida **Linhas de ordem de venda**, selecione **Estoque \> Reserva** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="39c77-168">While the new line is still selected on the **Sales order lines** FastTab, select **Inventory \> Reservation** on the toolbar.</span></span>
1. <span data-ttu-id="39c77-169">Na página **Reserva**, no Painel de Ação, selecione **Reservar lote**.</span><span class="sxs-lookup"><span data-stu-id="39c77-169">On the **Reservation** page, on the Action Pane, select **Reserve lot**.</span></span> <span data-ttu-id="39c77-170">Depois feche a página.</span><span class="sxs-lookup"><span data-stu-id="39c77-170">Then close the page.</span></span>
1. <span data-ttu-id="39c77-171">No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="39c77-171">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

### <a name="notifications-from-wave-batch-job-execution"></a><span data-ttu-id="39c77-172">Notificações da execução do trabalho em lotes do ciclo</span><span class="sxs-lookup"><span data-stu-id="39c77-172">Notifications from wave batch job execution</span></span>

<span data-ttu-id="39c77-173">Dependendo da configuração dos eventos comerciais, você receberá, eventualmente, uma notificação sobre a falha na execução do ciclo.</span><span class="sxs-lookup"><span data-stu-id="39c77-173">Depending on the setup of your business events, you will eventually receive a notification about wave execution failure.</span></span> <span data-ttu-id="39c77-174">A mensagem da Central de ações será semelhante ao exemplo a seguir e incluirá um link para o ciclo que falhou.</span><span class="sxs-lookup"><span data-stu-id="39c77-174">The Action center message will resemble the following example and will include a link to the wave that failed.</span></span>

> <span data-ttu-id="39c77-175">**Erro durante execução do ciclo**</span><span class="sxs-lookup"><span data-stu-id="39c77-175">**Error during wave execution**</span></span>  
> <span data-ttu-id="39c77-176">Ocorreu um erro ao executar o ciclo USMF -000000001.</span><span class="sxs-lookup"><span data-stu-id="39c77-176">An error occurred while executing wave USMF-000000001.</span></span>  
> <span data-ttu-id="39c77-177">Últimas mensagens: nenhum trabalho foi criado para o ciclo USMF-000000001.</span><span class="sxs-lookup"><span data-stu-id="39c77-177">Last messages: No Work was created for Wave USMF-000000001.</span></span>
>
> <span data-ttu-id="39c77-178">**STATUS**</span><span class="sxs-lookup"><span data-stu-id="39c77-178">**STATUS**</span></span>  
> <span data-ttu-id="39c77-179">Com Atividade</span><span class="sxs-lookup"><span data-stu-id="39c77-179">Active</span></span>
>
> <span data-ttu-id="39c77-180">Abrir detalhes do ciclo</span><span class="sxs-lookup"><span data-stu-id="39c77-180">Open wave details</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
