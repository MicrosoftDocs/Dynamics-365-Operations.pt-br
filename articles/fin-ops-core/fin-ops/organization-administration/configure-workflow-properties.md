---
title: Configurar propriedades do fluxo de trabalho
description: Este tópico explica como configurar as várias propriedades de um fluxo de trabalho.
author: ChrisGarty
manager: AnnBe
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 40118f329a676ffb30870eb882d127e3eb258599
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566958"
---
# <a name="configure-workflow-properties"></a><span data-ttu-id="07147-103">Configurar propriedades do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="07147-103">Configure workflow properties</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="07147-104">Este tópico explica como configurar as várias propriedades de um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="07147-104">This topic explains how to configure the various properties of a workflow.</span></span>

<span data-ttu-id="07147-105">Para configurar as propriedades de um fluxo de trabalho, abra o fluxo de trabalho no editor.</span><span class="sxs-lookup"><span data-stu-id="07147-105">To configure the properties of a workflow, open the workflow in the workflow editor.</span></span> <span data-ttu-id="07147-106">Clique na tela do editor de fluxo de trabalho e clique em **Propriedades** para abrir a página **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="07147-106">Click the canvas of the workflow editor, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="07147-107">Em seguida, use os procedimentos a seguir para configurar as várias propriedades do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="07147-107">You can then use the following procedures to configure the various properties of the workflow.</span></span>

## <a name="name-the-workflow"></a><span data-ttu-id="07147-108">Nomear o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="07147-108">Name the workflow</span></span>

<span data-ttu-id="07147-109">Siga as etapas abaixo para inserir um nome para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="07147-109">Follow these steps to enter a name for the workflow.</span></span>

1. <span data-ttu-id="07147-110">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="07147-110">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="07147-111">No campo **Nome**, insira um nome exclusivo para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="07147-111">In the **Name** field, enter a unique name for the workflow.</span></span> <span data-ttu-id="07147-112">Por exemplo, se você criar um fluxo de trabalho de requisição de compra para cada país/região onde opera, poderá nomear um fluxo de trabalho como **Requisições de Compra - Dinamarca** ou **Requisições de Compra - Espanha**.</span><span class="sxs-lookup"><span data-stu-id="07147-112">For example, if you create a purchase requisition workflow for each country/region that you operate in, you can name the purchase requisition workflow **Purchase Requisitions Denmark** or **Purchase Requisitions Spain**.</span></span>

## <a name="specify-the-workflow-owner"></a><span data-ttu-id="07147-113">Especificar o proprietário do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="07147-113">Specify the workflow owner</span></span>

<span data-ttu-id="07147-114">O proprietário do fluxo de trabalho é a pessoa que gerencia e mantém o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="07147-114">The workflow owner is the person who manages and maintains the workflow.</span></span> <span data-ttu-id="07147-115">Siga estas etapas para especificar o proprietário do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="07147-115">Follow these steps to specify the workflow owner.</span></span>

1. <span data-ttu-id="07147-116">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="07147-116">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="07147-117">Na lista **Proprietário**, selecione o nome da pessoa que gerenciará o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="07147-117">In the **Owner** list, select the name of the person who will manage the workflow.</span></span>

## <a name="select-an-email-template"></a><span data-ttu-id="07147-118">Selecionar um modelo de email</span><span class="sxs-lookup"><span data-stu-id="07147-118">Select an email template</span></span>

<span data-ttu-id="07147-119">Siga estas etapas para selecionar o modelo de email que será usado para gerar mensagens de notificação sobre o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="07147-119">Follow these steps to select the email template that is used to generate notification messages about the workflow.</span></span>

1. <span data-ttu-id="07147-120">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="07147-120">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="07147-121">Na lista **Modelo de email para notificações de fluxo de trabalho**, selecione o modelo.</span><span class="sxs-lookup"><span data-stu-id="07147-121">In the **Email template for workflow notifications** list, select the template.</span></span>

## <a name="enter-instructions-for-users"></a><span data-ttu-id="07147-122">Inserir instruções para os usuários</span><span class="sxs-lookup"><span data-stu-id="07147-122">Enter instructions for users</span></span>

<span data-ttu-id="07147-123">Você pode fornecer instruções aos usuários que enviarão documentos para processamento e aprovação.</span><span class="sxs-lookup"><span data-stu-id="07147-123">You can provide instructions to users who submit documents for processing and approval.</span></span> <span data-ttu-id="07147-124">Esses usuários também são conhecidos como *originadores*.</span><span class="sxs-lookup"><span data-stu-id="07147-124">These users are also referred to as *originators*.</span></span> <span data-ttu-id="07147-125">Por exemplo, suponha que você esteja criando um fluxo de trabalho de requisição de compra e insira instruções.</span><span class="sxs-lookup"><span data-stu-id="07147-125">For example, you're creating a purchase requisition workflow, and you enter instructions.</span></span> <span data-ttu-id="07147-126">Essas instruções fornecidas poderão ser exibidas pelos usuários que inserirem requisições de compra na página **Requisições de compra**.</span><span class="sxs-lookup"><span data-stu-id="07147-126">Those instructions can then be viewed by users who enter purchase requisitions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="07147-127">Para exibir instruções, o originador clica no ícone na barra de mensagens de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="07147-127">To view instructions, the originator clicks the icon in the workflow message bar.</span></span> <span data-ttu-id="07147-128">Siga estas etapas para inserir instruções para os usuários.</span><span class="sxs-lookup"><span data-stu-id="07147-128">Follow these steps to enter instructions for users.</span></span>

1. <span data-ttu-id="07147-129">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="07147-129">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="07147-130">No campo **Enviar instruções**, insira as instruções.</span><span class="sxs-lookup"><span data-stu-id="07147-130">In the **Submission instructions** field, enter the instructions.</span></span>
3. <span data-ttu-id="07147-131">Para personalizar as instruções, você pode inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="07147-131">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="07147-132">Os espaços reservados são substituídos pelos dados adequados quando as instruções são exibidas para os usuários.</span><span class="sxs-lookup"><span data-stu-id="07147-132">Placeholders are replaced with the appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="07147-133">Para inserir um espaço reservado, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="07147-133">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="07147-134">Clique no campo **Instruções de envio** para especificar onde o espaço reservado deve aparecer.</span><span class="sxs-lookup"><span data-stu-id="07147-134">Click in the **Submission instructions** field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="07147-135">Clique em **Inserir espaço reservado**.</span><span class="sxs-lookup"><span data-stu-id="07147-135">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="07147-136">Na lista exibida, selecione o espaço reservado a ser inserido.</span><span class="sxs-lookup"><span data-stu-id="07147-136">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="07147-137">Clique em **Inserir**.</span><span class="sxs-lookup"><span data-stu-id="07147-137">Click **Insert**.</span></span>

4. <span data-ttu-id="07147-138">Para adicionar traduções das instruções, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="07147-138">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="07147-139">Clique em **Traduções**.</span><span class="sxs-lookup"><span data-stu-id="07147-139">Click **Translations**.</span></span>
    2. <span data-ttu-id="07147-140">Na página exibida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="07147-140">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="07147-141">Na lista exibida, selecione o idioma do texto que você inserirá.</span><span class="sxs-lookup"><span data-stu-id="07147-141">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="07147-142">No campo **Texto traduzido**, insira o texto.</span><span class="sxs-lookup"><span data-stu-id="07147-142">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="07147-143">Para personalizar o texto, você poderá inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="07147-143">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="07147-144">Para obter instruções sobre como inserir um espaço reservado, consulte a etapa 3.</span><span class="sxs-lookup"><span data-stu-id="07147-144">For instructions about how to enter a placeholder, see step 3.</span></span>
    6. <span data-ttu-id="07147-145">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="07147-145">Click **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="07147-146">Os espaços reservados não podem ser adicionados usando copiar e colar porque as informações de destino não são coladas corretamente.</span><span class="sxs-lookup"><span data-stu-id="07147-146">Placeholders cannot be added using copy and paste because the target information is not pasted in correctly.</span></span> <span data-ttu-id="07147-147">Use a interface para adicionar espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="07147-147">Use the interface to add placeholders.</span></span>

## <a name="specify-when-this-workflow-is-used-through-activation-conditions"></a><span data-ttu-id="07147-148">Especificar quando este fluxo de trabalho é usado por condições de ativação</span><span class="sxs-lookup"><span data-stu-id="07147-148">Specify when this workflow is used through activation conditions</span></span>

<span data-ttu-id="07147-149">Você pode criar vários fluxos de trabalho baseados no mesmo tipo de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="07147-149">You can create multiple workflows that are based on the same workflow type.</span></span> <span data-ttu-id="07147-150">Se houver vários fluxos de trabalho baseados no mesmo tipo, será necessário especificar quando cada um deles será usado usando condições de ativação.</span><span class="sxs-lookup"><span data-stu-id="07147-150">When you have multiple workflows that are based on the same type, you must specify when each workflow is used using activation conditions.</span></span> <span data-ttu-id="07147-151">Se as condições de ativação não forem atendidas, o fluxo de trabalho padrão será usado.</span><span class="sxs-lookup"><span data-stu-id="07147-151">If activation conditions are not met, then the default workflow is used.</span></span> <span data-ttu-id="07147-152">Da mesma forma, se houver apenas uma configuração de fluxo de trabalho definida para um tipo de fluxo de trabalho, a configuração do fluxo de trabalho será usada independentemente das condições de ativação.</span><span class="sxs-lookup"><span data-stu-id="07147-152">Similarly, if there is only one workflow configuration defined for a workflow type, then that workflow configuration will be used regardless of the activation conditions.</span></span>

<span data-ttu-id="07147-153">Por exemplo, você pode criar um fluxo de trabalho de requisição de compra para cada país/região onde opera, como Requisições de Compra - Dinamarca e Requisições de Compra - Espanha, com as condições a seguir:</span><span class="sxs-lookup"><span data-stu-id="07147-153">For example, you can create a purchase requisition workflow for each country/region that you operate in, such as Purchase Requisitions Denmark and Purchase Requisitions Spain, with the following conditions:</span></span>

- <span data-ttu-id="07147-154">As Requisições de Compra - Dinamarca são usadas quando: país/região = DK</span><span class="sxs-lookup"><span data-stu-id="07147-154">Purchase Requisitions Denmark is used when: country/region = DK</span></span>
- <span data-ttu-id="07147-155">As Requisições de Compra - Espanha são usadas quando: país/região = DK</span><span class="sxs-lookup"><span data-stu-id="07147-155">Purchase Requisitions Spain is used when: country/region = ES</span></span>

<span data-ttu-id="07147-156">Siga estas etapas para especificar quando o fluxo de trabalho que você está configurando será usado.</span><span class="sxs-lookup"><span data-stu-id="07147-156">Follow these steps to specify when the workflow that you're configuring is used.</span></span>

1. <span data-ttu-id="07147-157">No painel esquerdo, clique em **Ativação**.</span><span class="sxs-lookup"><span data-stu-id="07147-157">In the left pane, click **Activation**.</span></span>
2. <span data-ttu-id="07147-158">Marque a caixa de seleção **Definir as condições para executar este fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="07147-158">Select the **Set the conditions for running this workflow** check box.</span></span>
3. <span data-ttu-id="07147-159">Clique em **Adicionar condição**.</span><span class="sxs-lookup"><span data-stu-id="07147-159">Click **Add condition**.</span></span>
4. <span data-ttu-id="07147-160">Insira uma condição.</span><span class="sxs-lookup"><span data-stu-id="07147-160">Enter a condition.</span></span>
5. <span data-ttu-id="07147-161">Insira quaisquer condições adicionais necessárias.</span><span class="sxs-lookup"><span data-stu-id="07147-161">Enter any additional conditions that are required.</span></span>
6. <span data-ttu-id="07147-162">Execute o fluxo de trabalho com alguns registros de destino para verificar se a condição inclui e exclui corretamente os registros.</span><span class="sxs-lookup"><span data-stu-id="07147-162">Run through the workflow with some target records to verify that the condition correctly includes and excludes records.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="07147-163">Especificar quando enviar notificações</span><span class="sxs-lookup"><span data-stu-id="07147-163">Specify when notifications are sent</span></span>

<span data-ttu-id="07147-164">Quando um documento é enviado para processamento, é criada uma instância do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="07147-164">When a document is submitted for processing, a workflow instance is created.</span></span> <span data-ttu-id="07147-165">Você poderá enviar notificações para os usuários quando instâncias baseadas nesse fluxo de trabalho forem iniciadas, concluídas, encerradas ou interrompidas devido a um erro.</span><span class="sxs-lookup"><span data-stu-id="07147-165">You can send notifications to users when workflow instances that are based on the workflow are started, completed, terminated, or stopped because of an error.</span></span> <span data-ttu-id="07147-166">Siga estas etapas para especificar quando as notificações serão enviadas.</span><span class="sxs-lookup"><span data-stu-id="07147-166">Follow these steps to specify when notifications are sent.</span></span>

1. <span data-ttu-id="07147-167">No painel esquerdo, clique em **Notificações**.</span><span class="sxs-lookup"><span data-stu-id="07147-167">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="07147-168">Marque a caixa de seleção para cada evento que disparará notificações:</span><span class="sxs-lookup"><span data-stu-id="07147-168">Select the check box for each event that should trigger notifications:</span></span>

    - <span data-ttu-id="07147-169">**Iniciado**– Enviar notificações quando uma instância de fluxo de trabalho for iniciada.</span><span class="sxs-lookup"><span data-stu-id="07147-169">**Started** – Send notifications when a workflow instance is started.</span></span>
    - <span data-ttu-id="07147-170">**Parado** – Enviar notificações quando uma instância de fluxo de trabalho for interrompida devido a um erro.</span><span class="sxs-lookup"><span data-stu-id="07147-170">**Stopped** – Send notifications when a workflow instance is stopped because of an error.</span></span>
    - <span data-ttu-id="07147-171">**Concluído** – Enviar notificações quando uma instância de fluxo de trabalho for concluída.</span><span class="sxs-lookup"><span data-stu-id="07147-171">**Completed** – Send notifications when a workflow instance is completed.</span></span>
    - <span data-ttu-id="07147-172">**Irrecuperável** – Enviar notificações quando uma instância de fluxo de trabalho for interrompida devido a um erro irrecuperável.</span><span class="sxs-lookup"><span data-stu-id="07147-172">**Unrecoverable** – Send notifications when a workflow instance is stopped because of an unrecoverable error.</span></span>
    - <span data-ttu-id="07147-173">**Encerrado** – Enviar notificações quando uma instância de fluxo de trabalho for encerrada.</span><span class="sxs-lookup"><span data-stu-id="07147-173">**Terminated** – Send notifications when a workflow instance is terminated.</span></span>

3. <span data-ttu-id="07147-174">Selecione a linha de um evento que você selecionou na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="07147-174">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="07147-175">Na guia **Texto da notificação**, insira o texto da notificação.</span><span class="sxs-lookup"><span data-stu-id="07147-175">On the **Notification text** tab, enter the text of the notification.</span></span>
5. <span data-ttu-id="07147-176">Para personalizar o texto, você poderá inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="07147-176">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="07147-177">Esses espaços reservados são substituídos pelos dados adequados quando o texto é exibido para os usuários.</span><span class="sxs-lookup"><span data-stu-id="07147-177">Placeholders are replaced with the appropriate data when the text is shown to users.</span></span> <span data-ttu-id="07147-178">Para inserir um espaço reservado, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="07147-178">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="07147-179">Clique no campo para especificar onde o espaço reservado deve aparecer.</span><span class="sxs-lookup"><span data-stu-id="07147-179">Click in the field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="07147-180">Clique em **Inserir espaço reservado**.</span><span class="sxs-lookup"><span data-stu-id="07147-180">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="07147-181">Na lista exibida, selecione o espaço reservado a ser inserido.</span><span class="sxs-lookup"><span data-stu-id="07147-181">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="07147-182">Clique em **Inserir**.</span><span class="sxs-lookup"><span data-stu-id="07147-182">Click **Insert**.</span></span>
    5. <span data-ttu-id="07147-183">Um espaço reservado comum de **Texto de notificação** a ser incluído é "Last Notes: %Workflow.Last note%", que exibe os comentários da etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="07147-183">A common **Notification text** placeholder to include is "Last Notes: %Workflow.Last note%", which displays any comments from the previous step.</span></span>

6. <span data-ttu-id="07147-184">Para adicionar traduções do texto, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="07147-184">To add translations of the text, follow these steps:</span></span>

    1. <span data-ttu-id="07147-185">Clique em **Traduções**.</span><span class="sxs-lookup"><span data-stu-id="07147-185">Click **Translations**.</span></span>
    2. <span data-ttu-id="07147-186">Na página exibida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="07147-186">On the page that appears, Click **Add**.</span></span>
    3. <span data-ttu-id="07147-187">Na lista exibida, selecione o idioma do texto que você inserirá.</span><span class="sxs-lookup"><span data-stu-id="07147-187">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="07147-188">No campo **Texto traduzido**, insira o texto.</span><span class="sxs-lookup"><span data-stu-id="07147-188">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="07147-189">Para personalizar o texto, você poderá inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="07147-189">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="07147-190">Para obter instruções sobre como inserir um espaço reservado, consulte a etapa 5.</span><span class="sxs-lookup"><span data-stu-id="07147-190">For instructions about how to enter a placeholder, see step 5.</span></span>
    6. <span data-ttu-id="07147-191">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="07147-191">Click **Close**.</span></span>

7. <span data-ttu-id="07147-192">Na guia **Destinatário**, use as seguintes opções para especificar quem deverá receber as notificações.</span><span class="sxs-lookup"><span data-stu-id="07147-192">On the **Recipient** tab, use the following options to specify who should receive the notifications.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="07147-193">Opção</span><span class="sxs-lookup"><span data-stu-id="07147-193">Option</span></span></th>
    <th><span data-ttu-id="07147-194">As notificações são enviadas a esses usuários</span><span class="sxs-lookup"><span data-stu-id="07147-194">Notifications are sent to these users</span></span></th>
    <th><span data-ttu-id="07147-195">Para enviar notificações, siga estas etapas</span><span class="sxs-lookup"><span data-stu-id="07147-195">To send notifications, follow these steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="07147-196">Participante</span><span class="sxs-lookup"><span data-stu-id="07147-196">Participant</span></span></td>
    <td><span data-ttu-id="07147-197">Usuários que foram atribuídos a uma função ou um grupo específico</span><span class="sxs-lookup"><span data-stu-id="07147-197">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="07147-198">Na guia <strong>Destinatário</strong>, clique em <strong>Participante</strong>.</span><span class="sxs-lookup"><span data-stu-id="07147-198">On the <strong>Recipient</strong> tab, click <strong>Participant</strong>.</span></span></li>
    <li><span data-ttu-id="07147-199">Na guia <strong>Baseado em função</strong>, na lista <strong>Tipo de participante</strong>, selecione o tipo de grupo ou de função ao qual serão enviadas notificações.</span><span class="sxs-lookup"><span data-stu-id="07147-199">On the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="07147-200">Na lista <strong>Participante</strong>, selecione o grupo ou a função ao qual serão enviadas notificações.</span><span class="sxs-lookup"><span data-stu-id="07147-200">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="07147-201">Usuário de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="07147-201">Workflow user</span></span></td>
    <td><span data-ttu-id="07147-202">Usuários participantes desse fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="07147-202">Users who are participants in this workflow</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="07147-203">Na guia <strong>Destinatário</strong>, clique em <strong>Usuário de fluxo de trabalho</strong>.</span><span class="sxs-lookup"><span data-stu-id="07147-203">On the <strong>Recipient</strong> tab, click <strong>Workflow user</strong>.</span></span></li>
    <li><span data-ttu-id="07147-204">Na guia <strong>Usuário de fluxo de trabalho</strong>, na lista <strong>Usuário de fluxo de trabalho</strong>, selecione um participante desse fluxo.</span><span class="sxs-lookup"><span data-stu-id="07147-204">On the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a participant in this workflow.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="07147-205">Usuário</span><span class="sxs-lookup"><span data-stu-id="07147-205">User</span></span></td>
    <td><span data-ttu-id="07147-206">Usuários específicos</span><span class="sxs-lookup"><span data-stu-id="07147-206">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="07147-207">Na guia <strong>Destinatário</strong>, clique em <strong>Usuário</strong>.</span><span class="sxs-lookup"><span data-stu-id="07147-207">On the <strong>Recipient</strong> tab, click <strong>User</strong>.</span></span></li>
    <li><span data-ttu-id="07147-208">Na guia <strong>Usuário</strong>, a lista <strong>Usuários disponíveis</strong> inclui todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="07147-208">On the <strong>User</strong> tab, the <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="07147-209">Selecione os usuários aos quais enviar notificações e mova- os para a lista <strong>Usuários selecionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="07147-209">Select the users to send notifications to, and move those users into the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="07147-210">Repita as etapas de 3 a 7 para cada evento selecionado na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="07147-210">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a><span data-ttu-id="07147-211">Insira comentários sobre as alterações feitas no fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="07147-211">Enter comments about the changes that you made to the workflow</span></span>

<span data-ttu-id="07147-212">Para inserir comentários sobre as alterações feitas no fluxo de trabalho, siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="07147-212">To enter comments about the changes that you made to the workflow, follow these steps.</span></span>

1. <span data-ttu-id="07147-213">No painel esquerdo, clique em **Observações**.</span><span class="sxs-lookup"><span data-stu-id="07147-213">In the left pane, click **Notes**.</span></span>
2. <span data-ttu-id="07147-214">No campo **Inserir comentários sobre o fluxo de trabalho**, insira seus comentários.</span><span class="sxs-lookup"><span data-stu-id="07147-214">In the **Enter comments about the workflow** field, enter your comments.</span></span>
3. <span data-ttu-id="07147-215">Revise seus comentários.</span><span class="sxs-lookup"><span data-stu-id="07147-215">Review your comments.</span></span> <span data-ttu-id="07147-216">Depois que você adicionar comentários, não poderá modificá-los.</span><span class="sxs-lookup"><span data-stu-id="07147-216">After you add comments, you can't modify them.</span></span>
4. <span data-ttu-id="07147-217">Clique em **Adicionar** para adicionar comentários à área **Histórico de comentários**.</span><span class="sxs-lookup"><span data-stu-id="07147-217">Click **Add** to add your comments to the **Comment history** area.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]