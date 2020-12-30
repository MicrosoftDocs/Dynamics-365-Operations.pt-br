---
title: Configurar propriedades do fluxo de trabalho
description: Este tópico explica como configurar as várias propriedades de um fluxo de trabalho.
author: ChrisGarty
manager: AnnBe
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8bd3c9bea010099f83d16dad70261bc2d46a1dac
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693273"
---
# <a name="configure-workflow-properties"></a><span data-ttu-id="21e53-103">Configurar propriedades do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="21e53-103">Configure workflow properties</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="21e53-104">Este tópico explica como configurar as várias propriedades de um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="21e53-104">This topic explains how to configure the various properties of a workflow.</span></span>

<span data-ttu-id="21e53-105">Para configurar as propriedades de um fluxo de trabalho, abra o fluxo de trabalho no editor.</span><span class="sxs-lookup"><span data-stu-id="21e53-105">To configure the properties of a workflow, open the workflow in the workflow editor.</span></span> <span data-ttu-id="21e53-106">Clique na tela do editor de fluxo de trabalho e clique em **Propriedades** para abrir a página **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="21e53-106">Click the canvas of the workflow editor, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="21e53-107">Em seguida, use os procedimentos a seguir para configurar as várias propriedades do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="21e53-107">You can then use the following procedures to configure the various properties of the workflow.</span></span>

## <a name="name-the-workflow"></a><span data-ttu-id="21e53-108">Nomear o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="21e53-108">Name the workflow</span></span>

<span data-ttu-id="21e53-109">Siga as etapas abaixo para inserir um nome para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="21e53-109">Follow these steps to enter a name for the workflow.</span></span>

1. <span data-ttu-id="21e53-110">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="21e53-110">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="21e53-111">No campo **Nome**, insira um nome exclusivo para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="21e53-111">In the **Name** field, enter a unique name for the workflow.</span></span> <span data-ttu-id="21e53-112">Por exemplo, se você criar um fluxo de trabalho de requisição de compra para cada país/região onde opera, poderá nomear um fluxo de trabalho como **Requisições de Compra - Dinamarca** ou **Requisições de Compra - Espanha**.</span><span class="sxs-lookup"><span data-stu-id="21e53-112">For example, if you create a purchase requisition workflow for each country/region that you operate in, you can name the purchase requisition workflow **Purchase Requisitions Denmark** or **Purchase Requisitions Spain**.</span></span>

## <a name="specify-the-workflow-owner"></a><span data-ttu-id="21e53-113">Especificar o proprietário do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="21e53-113">Specify the workflow owner</span></span>

<span data-ttu-id="21e53-114">O proprietário do fluxo de trabalho é a pessoa que gerencia e mantém o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="21e53-114">The workflow owner is the person who manages and maintains the workflow.</span></span> <span data-ttu-id="21e53-115">Siga estas etapas para especificar o proprietário do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="21e53-115">Follow these steps to specify the workflow owner.</span></span>

1. <span data-ttu-id="21e53-116">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="21e53-116">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="21e53-117">Na lista **Proprietário**, selecione o nome da pessoa que gerenciará o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="21e53-117">In the **Owner** list, select the name of the person who will manage the workflow.</span></span>

## <a name="select-an-email-template"></a><span data-ttu-id="21e53-118">Selecionar um modelo de email</span><span class="sxs-lookup"><span data-stu-id="21e53-118">Select an email template</span></span>

<span data-ttu-id="21e53-119">Siga estas etapas para selecionar o modelo de email que será usado para gerar mensagens de notificação sobre o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="21e53-119">Follow these steps to select the email template that is used to generate notification messages about the workflow.</span></span>

1. <span data-ttu-id="21e53-120">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="21e53-120">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="21e53-121">Na lista **Modelo de email para notificações de fluxo de trabalho**, selecione o modelo.</span><span class="sxs-lookup"><span data-stu-id="21e53-121">In the **Email template for workflow notifications** list, select the template.</span></span>

## <a name="enter-instructions-for-users"></a><span data-ttu-id="21e53-122">Inserir instruções para os usuários</span><span class="sxs-lookup"><span data-stu-id="21e53-122">Enter instructions for users</span></span>

<span data-ttu-id="21e53-123">Você pode fornecer instruções aos usuários que enviarão documentos para processamento e aprovação.</span><span class="sxs-lookup"><span data-stu-id="21e53-123">You can provide instructions to users who submit documents for processing and approval.</span></span> <span data-ttu-id="21e53-124">Esses usuários também são conhecidos como *originadores*.</span><span class="sxs-lookup"><span data-stu-id="21e53-124">These users are also referred to as *originators*.</span></span> <span data-ttu-id="21e53-125">Por exemplo, suponha que você esteja criando um fluxo de trabalho de requisição de compra e insira instruções.</span><span class="sxs-lookup"><span data-stu-id="21e53-125">For example, you're creating a purchase requisition workflow, and you enter instructions.</span></span> <span data-ttu-id="21e53-126">Essas instruções fornecidas poderão ser exibidas pelos usuários que inserirem requisições de compra na página **Requisições de compra**.</span><span class="sxs-lookup"><span data-stu-id="21e53-126">Those instructions can then be viewed by users who enter purchase requisitions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="21e53-127">Para exibir instruções, o originador clica no ícone na barra de mensagens de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="21e53-127">To view instructions, the originator clicks the icon in the workflow message bar.</span></span> <span data-ttu-id="21e53-128">Siga estas etapas para inserir instruções para os usuários.</span><span class="sxs-lookup"><span data-stu-id="21e53-128">Follow these steps to enter instructions for users.</span></span>

1. <span data-ttu-id="21e53-129">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="21e53-129">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="21e53-130">No campo **Enviar instruções**, insira as instruções.</span><span class="sxs-lookup"><span data-stu-id="21e53-130">In the **Submission instructions** field, enter the instructions.</span></span>
3. <span data-ttu-id="21e53-131">Para personalizar as instruções, você pode inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="21e53-131">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="21e53-132">Os espaços reservados são substituídos pelos dados adequados quando as instruções são exibidas para os usuários.</span><span class="sxs-lookup"><span data-stu-id="21e53-132">Placeholders are replaced with the appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="21e53-133">Para inserir um espaço reservado, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="21e53-133">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="21e53-134">Clique no campo **Instruções de envio** para especificar onde o espaço reservado deve aparecer.</span><span class="sxs-lookup"><span data-stu-id="21e53-134">Click in the **Submission instructions** field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="21e53-135">Clique em **Inserir espaço reservado**.</span><span class="sxs-lookup"><span data-stu-id="21e53-135">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="21e53-136">Na lista exibida, selecione o espaço reservado a ser inserido.</span><span class="sxs-lookup"><span data-stu-id="21e53-136">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="21e53-137">Clique em **Inserir**.</span><span class="sxs-lookup"><span data-stu-id="21e53-137">Click **Insert**.</span></span>

4. <span data-ttu-id="21e53-138">Para adicionar traduções das instruções, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="21e53-138">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="21e53-139">Clique em **Traduções**.</span><span class="sxs-lookup"><span data-stu-id="21e53-139">Click **Translations**.</span></span>
    2. <span data-ttu-id="21e53-140">Na página exibida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="21e53-140">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="21e53-141">Na lista exibida, selecione o idioma do texto que você inserirá.</span><span class="sxs-lookup"><span data-stu-id="21e53-141">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="21e53-142">No campo **Texto traduzido**, insira o texto.</span><span class="sxs-lookup"><span data-stu-id="21e53-142">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="21e53-143">Para personalizar o texto, você poderá inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="21e53-143">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="21e53-144">Para obter instruções sobre como inserir um espaço reservado, consulte a etapa 3.</span><span class="sxs-lookup"><span data-stu-id="21e53-144">For instructions about how to enter a placeholder, see step 3.</span></span>
    6. <span data-ttu-id="21e53-145">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="21e53-145">Click **Close**.</span></span>

## <a name="specify-when-this-workflow-is-used-through-activation-conditions"></a><span data-ttu-id="21e53-146">Especificar quando este fluxo de trabalho é usado por condições de ativação</span><span class="sxs-lookup"><span data-stu-id="21e53-146">Specify when this workflow is used through activation conditions</span></span>

<span data-ttu-id="21e53-147">Você pode criar vários fluxos de trabalho baseados no mesmo tipo de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="21e53-147">You can create multiple workflows that are based on the same workflow type.</span></span> <span data-ttu-id="21e53-148">Se houver vários fluxos de trabalho baseados no mesmo tipo, será necessário especificar quando cada um deles será usado usando condições de ativação.</span><span class="sxs-lookup"><span data-stu-id="21e53-148">When you have multiple workflows that are based on the same type, you must specify when each workflow is used using activation conditions.</span></span> <span data-ttu-id="21e53-149">Se as condições de ativação não forem atendidas, o fluxo de trabalho padrão será usado.</span><span class="sxs-lookup"><span data-stu-id="21e53-149">If activation conditions are not met, then the default workflow is used.</span></span> <span data-ttu-id="21e53-150">Da mesma forma, se houver apenas uma configuração de fluxo de trabalho definida para um tipo de fluxo de trabalho, a configuração do fluxo de trabalho será usada independentemente das condições de ativação.</span><span class="sxs-lookup"><span data-stu-id="21e53-150">Similarly, if there is only one workflow configuration defined for a workflow type, then that workflow configuration will be used regardless of the activation conditions.</span></span>

<span data-ttu-id="21e53-151">Por exemplo, você pode criar um fluxo de trabalho de requisição de compra para cada país/região onde opera, como Requisições de Compra - Dinamarca e Requisições de Compra - Espanha, com as condições a seguir:</span><span class="sxs-lookup"><span data-stu-id="21e53-151">For example, you can create a purchase requisition workflow for each country/region that you operate in, such as Purchase Requisitions Denmark and Purchase Requisitions Spain, with the following conditions:</span></span>

- <span data-ttu-id="21e53-152">As Requisições de Compra - Dinamarca são usadas quando: país/região = DK</span><span class="sxs-lookup"><span data-stu-id="21e53-152">Purchase Requisitions Denmark is used when: country/region = DK</span></span>
- <span data-ttu-id="21e53-153">As Requisições de Compra - Espanha são usadas quando: país/região = DK</span><span class="sxs-lookup"><span data-stu-id="21e53-153">Purchase Requisitions Spain is used when: country/region = ES</span></span>

<span data-ttu-id="21e53-154">Siga estas etapas para especificar quando o fluxo de trabalho que você está configurando será usado.</span><span class="sxs-lookup"><span data-stu-id="21e53-154">Follow these steps to specify when the workflow that you're configuring is used.</span></span>

1. <span data-ttu-id="21e53-155">No painel esquerdo, clique em **Ativação**.</span><span class="sxs-lookup"><span data-stu-id="21e53-155">In the left pane, click **Activation**.</span></span>
2. <span data-ttu-id="21e53-156">Marque a caixa de seleção **Definir as condições para executar este fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="21e53-156">Select the **Set the conditions for running this workflow** check box.</span></span>
3. <span data-ttu-id="21e53-157">Clique em **Adicionar condição**.</span><span class="sxs-lookup"><span data-stu-id="21e53-157">Click **Add condition**.</span></span>
4. <span data-ttu-id="21e53-158">Insira uma condição.</span><span class="sxs-lookup"><span data-stu-id="21e53-158">Enter a condition.</span></span>
5. <span data-ttu-id="21e53-159">Insira quaisquer condições adicionais necessárias.</span><span class="sxs-lookup"><span data-stu-id="21e53-159">Enter any additional conditions that are required.</span></span>
6. <span data-ttu-id="21e53-160">Execute o fluxo de trabalho com alguns registros de destino para verificar se a condição inclui e exclui corretamente os registros.</span><span class="sxs-lookup"><span data-stu-id="21e53-160">Run through the workflow with some target records to verify that the condition correctly includes and excludes records.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="21e53-161">Especificar quando enviar notificações</span><span class="sxs-lookup"><span data-stu-id="21e53-161">Specify when notifications are sent</span></span>

<span data-ttu-id="21e53-162">Quando um documento é enviado para processamento, é criada uma instância do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="21e53-162">When a document is submitted for processing, a workflow instance is created.</span></span> <span data-ttu-id="21e53-163">Você poderá enviar notificações para os usuários quando instâncias baseadas nesse fluxo de trabalho forem iniciadas, concluídas, encerradas ou interrompidas devido a um erro.</span><span class="sxs-lookup"><span data-stu-id="21e53-163">You can send notifications to users when workflow instances that are based on the workflow are started, completed, terminated, or stopped because of an error.</span></span> <span data-ttu-id="21e53-164">Siga estas etapas para especificar quando as notificações serão enviadas.</span><span class="sxs-lookup"><span data-stu-id="21e53-164">Follow these steps to specify when notifications are sent.</span></span>

1. <span data-ttu-id="21e53-165">No painel esquerdo, clique em **Notificações**.</span><span class="sxs-lookup"><span data-stu-id="21e53-165">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="21e53-166">Marque a caixa de seleção para cada evento que disparará notificações:</span><span class="sxs-lookup"><span data-stu-id="21e53-166">Select the check box for each event that should trigger notifications:</span></span>

    - <span data-ttu-id="21e53-167">**Iniciado**– Enviar notificações quando uma instância de fluxo de trabalho for iniciada.</span><span class="sxs-lookup"><span data-stu-id="21e53-167">**Started** – Send notifications when a workflow instance is started.</span></span>
    - <span data-ttu-id="21e53-168">**Parado** – Enviar notificações quando uma instância de fluxo de trabalho for interrompida devido a um erro.</span><span class="sxs-lookup"><span data-stu-id="21e53-168">**Stopped** – Send notifications when a workflow instance is stopped because of an error.</span></span>
    - <span data-ttu-id="21e53-169">**Concluído** – Enviar notificações quando uma instância de fluxo de trabalho for concluída.</span><span class="sxs-lookup"><span data-stu-id="21e53-169">**Completed** – Send notifications when a workflow instance is completed.</span></span>
    - <span data-ttu-id="21e53-170">**Irrecuperável** – Enviar notificações quando uma instância de fluxo de trabalho for interrompida devido a um erro irrecuperável.</span><span class="sxs-lookup"><span data-stu-id="21e53-170">**Unrecoverable** – Send notifications when a workflow instance is stopped because of an unrecoverable error.</span></span>
    - <span data-ttu-id="21e53-171">**Encerrado** – Enviar notificações quando uma instância de fluxo de trabalho for encerrada.</span><span class="sxs-lookup"><span data-stu-id="21e53-171">**Terminated** – Send notifications when a workflow instance is terminated.</span></span>

3. <span data-ttu-id="21e53-172">Selecione a linha de um evento que você selecionou na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="21e53-172">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="21e53-173">Na guia **Texto da notificação**, insira o texto da notificação.</span><span class="sxs-lookup"><span data-stu-id="21e53-173">On the **Notification text** tab, enter the text of the notification.</span></span>
5. <span data-ttu-id="21e53-174">Para personalizar o texto, você poderá inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="21e53-174">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="21e53-175">Esses espaços reservados são substituídos pelos dados adequados quando o texto é exibido para os usuários.</span><span class="sxs-lookup"><span data-stu-id="21e53-175">Placeholders are replaced with the appropriate data when the text is shown to users.</span></span> <span data-ttu-id="21e53-176">Para inserir um espaço reservado, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="21e53-176">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="21e53-177">Clique no campo para especificar onde o espaço reservado deve aparecer.</span><span class="sxs-lookup"><span data-stu-id="21e53-177">Click in the field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="21e53-178">Clique em **Inserir espaço reservado**.</span><span class="sxs-lookup"><span data-stu-id="21e53-178">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="21e53-179">Na lista exibida, selecione o espaço reservado a ser inserido.</span><span class="sxs-lookup"><span data-stu-id="21e53-179">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="21e53-180">Clique em **Inserir**.</span><span class="sxs-lookup"><span data-stu-id="21e53-180">Click **Insert**.</span></span>
    5. <span data-ttu-id="21e53-181">Um espaço reservado comum de **Texto de notificação** a ser incluído é "Last Notes: %Workflow.Last note%", que exibe os comentários da etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="21e53-181">A common **Notification text** placeholder to include is "Last Notes: %Workflow.Last note%", which displays any comments from the previous step.</span></span>

6. <span data-ttu-id="21e53-182">Para adicionar traduções do texto, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="21e53-182">To add translations of the text, follow these steps:</span></span>

    1. <span data-ttu-id="21e53-183">Clique em **Traduções**.</span><span class="sxs-lookup"><span data-stu-id="21e53-183">Click **Translations**.</span></span>
    2. <span data-ttu-id="21e53-184">Na página exibida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="21e53-184">On the page that appears, Click **Add**.</span></span>
    3. <span data-ttu-id="21e53-185">Na lista exibida, selecione o idioma do texto que você inserirá.</span><span class="sxs-lookup"><span data-stu-id="21e53-185">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="21e53-186">No campo **Texto traduzido**, insira o texto.</span><span class="sxs-lookup"><span data-stu-id="21e53-186">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="21e53-187">Para personalizar o texto, você poderá inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="21e53-187">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="21e53-188">Para obter instruções sobre como inserir um espaço reservado, consulte a etapa 5.</span><span class="sxs-lookup"><span data-stu-id="21e53-188">For instructions about how to enter a placeholder, see step 5.</span></span>
    6. <span data-ttu-id="21e53-189">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="21e53-189">Click **Close**.</span></span>

7. <span data-ttu-id="21e53-190">Na guia **Destinatário**, use as seguintes opções para especificar quem deverá receber as notificações.</span><span class="sxs-lookup"><span data-stu-id="21e53-190">On the **Recipient** tab, use the following options to specify who should receive the notifications.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="21e53-191">Opção</span><span class="sxs-lookup"><span data-stu-id="21e53-191">Option</span></span></th>
    <th><span data-ttu-id="21e53-192">As notificações são enviadas a esses usuários</span><span class="sxs-lookup"><span data-stu-id="21e53-192">Notifications are sent to these users</span></span></th>
    <th><span data-ttu-id="21e53-193">Para enviar notificações, siga estas etapas</span><span class="sxs-lookup"><span data-stu-id="21e53-193">To send notifications, follow these steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="21e53-194">Participante</span><span class="sxs-lookup"><span data-stu-id="21e53-194">Participant</span></span></td>
    <td><span data-ttu-id="21e53-195">Usuários que foram atribuídos a uma função ou um grupo específico</span><span class="sxs-lookup"><span data-stu-id="21e53-195">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="21e53-196">Na guia <strong>Destinatário</strong>, clique em <strong>Participante</strong>.</span><span class="sxs-lookup"><span data-stu-id="21e53-196">On the <strong>Recipient</strong> tab, click <strong>Participant</strong>.</span></span></li>
    <li><span data-ttu-id="21e53-197">Na guia <strong>Baseado em função</strong>, na lista <strong>Tipo de participante</strong>, selecione o tipo de grupo ou de função ao qual serão enviadas notificações.</span><span class="sxs-lookup"><span data-stu-id="21e53-197">On the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="21e53-198">Na lista <strong>Participante</strong>, selecione o grupo ou a função ao qual serão enviadas notificações.</span><span class="sxs-lookup"><span data-stu-id="21e53-198">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="21e53-199">Usuário de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="21e53-199">Workflow user</span></span></td>
    <td><span data-ttu-id="21e53-200">Usuários participantes desse fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="21e53-200">Users who are participants in this workflow</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="21e53-201">Na guia <strong>Destinatário</strong>, clique em <strong>Usuário de fluxo de trabalho</strong>.</span><span class="sxs-lookup"><span data-stu-id="21e53-201">On the <strong>Recipient</strong> tab, click <strong>Workflow user</strong>.</span></span></li>
    <li><span data-ttu-id="21e53-202">Na guia <strong>Usuário de fluxo de trabalho</strong>, na lista <strong>Usuário de fluxo de trabalho</strong>, selecione um participante desse fluxo.</span><span class="sxs-lookup"><span data-stu-id="21e53-202">On the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a participant in this workflow.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="21e53-203">Usuário</span><span class="sxs-lookup"><span data-stu-id="21e53-203">User</span></span></td>
    <td><span data-ttu-id="21e53-204">Usuários específicos</span><span class="sxs-lookup"><span data-stu-id="21e53-204">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="21e53-205">Na guia <strong>Destinatário</strong>, clique em <strong>Usuário</strong>.</span><span class="sxs-lookup"><span data-stu-id="21e53-205">On the <strong>Recipient</strong> tab, click <strong>User</strong>.</span></span></li>
    <li><span data-ttu-id="21e53-206">Na guia <strong>Usuário</strong>, a lista <strong>Usuários disponíveis</strong> inclui todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="21e53-206">On the <strong>User</strong> tab, the <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="21e53-207">Selecione os usuários aos quais enviar notificações e mova- os para a lista <strong>Usuários selecionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="21e53-207">Select the users to send notifications to, and move those users into the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="21e53-208">Repita as etapas de 3 a 7 para cada evento selecionado na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="21e53-208">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a><span data-ttu-id="21e53-209">Insira comentários sobre as alterações feitas no fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="21e53-209">Enter comments about the changes that you made to the workflow</span></span>

<span data-ttu-id="21e53-210">Para inserir comentários sobre as alterações feitas no fluxo de trabalho, siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="21e53-210">To enter comments about the changes that you made to the workflow, follow these steps.</span></span>

1. <span data-ttu-id="21e53-211">No painel esquerdo, clique em **Observações**.</span><span class="sxs-lookup"><span data-stu-id="21e53-211">In the left pane, click **Notes**.</span></span>
2. <span data-ttu-id="21e53-212">No campo **Inserir comentários sobre o fluxo de trabalho**, insira seus comentários.</span><span class="sxs-lookup"><span data-stu-id="21e53-212">In the **Enter comments about the workflow** field, enter your comments.</span></span>
3. <span data-ttu-id="21e53-213">Revise seus comentários.</span><span class="sxs-lookup"><span data-stu-id="21e53-213">Review your comments.</span></span> <span data-ttu-id="21e53-214">Depois que você adicionar comentários, não poderá modificá-los.</span><span class="sxs-lookup"><span data-stu-id="21e53-214">After you add comments, you can't modify them.</span></span>
4. <span data-ttu-id="21e53-215">Clique em **Adicionar** para adicionar comentários à área **Histórico de comentários**.</span><span class="sxs-lookup"><span data-stu-id="21e53-215">Click **Add** to add your comments to the **Comment history** area.</span></span>
