---
title: Configurar decisões manuais em um fluxo de trabalho
description: Este tópico explica como configurar as propriedades de uma decisão manual.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 192101
ms.assetid: 0bccad77-1a44-4f08-967b-12c62c02afc7
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d09e99a5bf99593a8fa7682f9d4f29eaa4e7c836
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "341387"
---
# <a name="configure-manual-decisions-in-a-workflow"></a><span data-ttu-id="7a735-103">Configurar decisões manuais em um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="7a735-103">Configure manual decisions in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7a735-104">Este tópico explica como configurar as propriedades de uma decisão manual.</span><span class="sxs-lookup"><span data-stu-id="7a735-104">This topic explains how to configure the properties of a manual decision.</span></span>

<span data-ttu-id="7a735-105">Para configurar uma decisão manual no editor de fluxo de trabalho, clique com o botão direito do mouse na decisão manual e clique em **Propriedades** para abrir a página **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="7a735-105">To configure a manual decision in the workflow editor, right-click the manual decision, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="7a735-106">Em seguida, use os procedimentos a seguir para configurar as propriedades da decisão manual.</span><span class="sxs-lookup"><span data-stu-id="7a735-106">Then use the following procedures to configure the properties of the manual decision.</span></span>

## <a name="name-the-decision"></a><span data-ttu-id="7a735-107">Nomear a decisão</span><span class="sxs-lookup"><span data-stu-id="7a735-107">Name the decision</span></span>

<span data-ttu-id="7a735-108">Siga estas etapas para inserir um nome para a decisão manual.</span><span class="sxs-lookup"><span data-stu-id="7a735-108">Follow these steps to enter a name for the manual decision.</span></span>

1. <span data-ttu-id="7a735-109">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="7a735-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="7a735-110">No campo **Nome**, insira um nome exclusivo para a decisão manual.</span><span class="sxs-lookup"><span data-stu-id="7a735-110">In the **Name** field, enter a unique name for the manual decision.</span></span>

## <a name="enter-a-subject-line-and-instructions"></a><span data-ttu-id="7a735-111">Inserir uma linha de assunto e instruções</span><span class="sxs-lookup"><span data-stu-id="7a735-111">Enter a subject line and instructions</span></span>

<span data-ttu-id="7a735-112">Você deve fornecer uma linha de assunto e instruções para os usuários atribuídos à decisão manual.</span><span class="sxs-lookup"><span data-stu-id="7a735-112">You must provide a subject line and instructions to users who are assigned to the manual decision.</span></span> <span data-ttu-id="7a735-113">Por exemplo, se você estiver configurando uma decisão de requisições de compra, o usuário que foi atribuído à decisão verá a linha de assunto e as instruções na página **Requisições de compra**.</span><span class="sxs-lookup"><span data-stu-id="7a735-113">For example, if you're configuring a decision for purchase requisitions, the user who is assigned to the decision sees the subject line and instructions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="7a735-114">A linha de assunto aparece em uma barra de mensagens na página.</span><span class="sxs-lookup"><span data-stu-id="7a735-114">The subject line appears in a message bar on the page.</span></span> <span data-ttu-id="7a735-115">O usuário poderá clicar no ícone na barra de mensagens para exibir as instruções.</span><span class="sxs-lookup"><span data-stu-id="7a735-115">The user can then click the icon in the message bar to view the instructions.</span></span> <span data-ttu-id="7a735-116">Siga estas etapas para inserir uma linha de assunto e instruções.</span><span class="sxs-lookup"><span data-stu-id="7a735-116">Follow these steps to enter a subject line and instructions.</span></span>

1. <span data-ttu-id="7a735-117">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="7a735-117">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="7a735-118">Na guia **Instruções**, no campo **Assunto do item de trabalho**, insira a linha de assunto.</span><span class="sxs-lookup"><span data-stu-id="7a735-118">On the **Instructions** tab, in the **Work item subject** field, enter the subject line.</span></span>
3. <span data-ttu-id="7a735-119">Para personalizar a linha de assunto, você pode inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="7a735-119">To personalize the subject line, you can insert placeholders.</span></span> <span data-ttu-id="7a735-120">Esses espaços reservados são substituídos pelos dados adequados quando a linha de assunto for exibida para os usuários.</span><span class="sxs-lookup"><span data-stu-id="7a735-120">Placeholders are replaced with appropriate data when the subject line is shown to users.</span></span> <span data-ttu-id="7a735-121">Siga estas etapas para inserir um espaço reservado:</span><span class="sxs-lookup"><span data-stu-id="7a735-121">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="7a735-122">Na caixa de texto, clique no local onde o espaço reservado deve aparecer.</span><span class="sxs-lookup"><span data-stu-id="7a735-122">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="7a735-123">Clique em **Inserir espaço reservado**.</span><span class="sxs-lookup"><span data-stu-id="7a735-123">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="7a735-124">Na lista exibida, selecione o espaço reservado a ser inserido.</span><span class="sxs-lookup"><span data-stu-id="7a735-124">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="7a735-125">Clique em **Inserir**.</span><span class="sxs-lookup"><span data-stu-id="7a735-125">Click **Insert**.</span></span>

4. <span data-ttu-id="7a735-126">Para adicionar traduções da linha de assunto, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="7a735-126">To add translations of the subject line, follow these steps:</span></span>

    1. <span data-ttu-id="7a735-127">Clique em **Traduções**.</span><span class="sxs-lookup"><span data-stu-id="7a735-127">Click **Translations**.</span></span>
    2. <span data-ttu-id="7a735-128">Na página exibida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7a735-128">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="7a735-129">Na lista exibida, selecione o idioma do texto que você está inserindo.</span><span class="sxs-lookup"><span data-stu-id="7a735-129">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="7a735-130">No campo **Texto traduzido**, insira o texto.</span><span class="sxs-lookup"><span data-stu-id="7a735-130">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="7a735-131">Para personalizar o texto, insira os espaços reservados conforme descrito na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="7a735-131">To personalize the text, you can insert placeholders as described in step 3.</span></span>
    6. <span data-ttu-id="7a735-132">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="7a735-132">Click **Close**.</span></span>

5. <span data-ttu-id="7a735-133">No campo **Instruções do item de trabalho**, insira as instruções.</span><span class="sxs-lookup"><span data-stu-id="7a735-133">In the **Work item instructions** field, enter the instructions.</span></span>
6. <span data-ttu-id="7a735-134">Para personalizar as instruções, você pode inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="7a735-134">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="7a735-135">Esses espaços reservados são substituídos pelos dados adequados quando as instruções são exibidas para os usuários.</span><span class="sxs-lookup"><span data-stu-id="7a735-135">Placeholders are replaced with appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="7a735-136">Siga estas etapas para inserir um espaço reservado:</span><span class="sxs-lookup"><span data-stu-id="7a735-136">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="7a735-137">Na caixa de texto, clique no local onde o espaço reservado deve aparecer.</span><span class="sxs-lookup"><span data-stu-id="7a735-137">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="7a735-138">Clique em **Inserir espaço reservado**.</span><span class="sxs-lookup"><span data-stu-id="7a735-138">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="7a735-139">Na lista exibida, selecione o espaço reservado a ser inserido.</span><span class="sxs-lookup"><span data-stu-id="7a735-139">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="7a735-140">Clique em **Inserir**.</span><span class="sxs-lookup"><span data-stu-id="7a735-140">Click **Insert**.</span></span>

7. <span data-ttu-id="7a735-141">Para adicionar traduções das instruções, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="7a735-141">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="7a735-142">Clique em **Traduções**.</span><span class="sxs-lookup"><span data-stu-id="7a735-142">Click **Translations**.</span></span>
    2. <span data-ttu-id="7a735-143">Na página exibida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7a735-143">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="7a735-144">Na lista exibida, selecione o idioma do texto que você está inserindo.</span><span class="sxs-lookup"><span data-stu-id="7a735-144">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="7a735-145">No campo **Texto traduzido**, insira o texto.</span><span class="sxs-lookup"><span data-stu-id="7a735-145">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="7a735-146">Para personalizar o texto, insira os espaços reservados conforme descrito na etapa 6.</span><span class="sxs-lookup"><span data-stu-id="7a735-146">To personalize the text, you can insert placeholders as described in step 6.</span></span>
    6. <span data-ttu-id="7a735-147">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="7a735-147">Click **Close**.</span></span>

## <a name="specify-the-possible-outcomes-of-a-decision"></a><span data-ttu-id="7a735-148">Especificar os possíveis resultados de uma decisão</span><span class="sxs-lookup"><span data-stu-id="7a735-148">Specify the possible outcomes of a decision</span></span>

<span data-ttu-id="7a735-149">Geralmente, quando um documento é atribuído a um tomador de decisão, uma pergunta é feita a ele.</span><span class="sxs-lookup"><span data-stu-id="7a735-149">Typically, when a document is assigned to a decision maker, the decision maker is asked a question.</span></span> <span data-ttu-id="7a735-150">A resposta para essa pergunta normalmente é **Sim** ou **Não**, ou **Verdadeiro** ou **Falso**.</span><span class="sxs-lookup"><span data-stu-id="7a735-150">The answer to this question is usually **Yes** or **No**, or **True** or **False**.</span></span> <span data-ttu-id="7a735-151">Siga estas etapas para especificar os possíveis resultados de decisão manual.</span><span class="sxs-lookup"><span data-stu-id="7a735-151">Follow these steps to specify the possible outcomes of the manual decision.</span></span>

1. <span data-ttu-id="7a735-152">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="7a735-152">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="7a735-153">Na guia **Resultados**, no campo **Resultado 1**, insira o nome do resultado ou a opção.</span><span class="sxs-lookup"><span data-stu-id="7a735-153">On the **Outcomes** tab, in the **Outcome 1** field, enter the name of the outcome, or the option.</span></span>
3. <span data-ttu-id="7a735-154">Para adicionar traduções do resultado, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="7a735-154">To add translations of the outcome, follow these steps:</span></span>

    1. <span data-ttu-id="7a735-155">Clique em **Traduções**.</span><span class="sxs-lookup"><span data-stu-id="7a735-155">Click **Translations**.</span></span>
    2. <span data-ttu-id="7a735-156">Na página exibida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7a735-156">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="7a735-157">Na lista exibida, selecione o idioma do texto que você está inserindo.</span><span class="sxs-lookup"><span data-stu-id="7a735-157">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="7a735-158">No campo **Texto traduzido**, insira o texto.</span><span class="sxs-lookup"><span data-stu-id="7a735-158">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="7a735-159">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="7a735-159">Click **Close**.</span></span>

4. <span data-ttu-id="7a735-160">No campo **Resultado 2**, insira o nome do resultado ou a opção.</span><span class="sxs-lookup"><span data-stu-id="7a735-160">In the **Outcome 2** field, enter the name of the outcome, or the option.</span></span>
5. <span data-ttu-id="7a735-161">Para adicionar traduções do resultado, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="7a735-161">To add translations of the outcome, follow these steps:</span></span>

    1. <span data-ttu-id="7a735-162">Clique em **Traduções**.</span><span class="sxs-lookup"><span data-stu-id="7a735-162">Click **Translations**.</span></span>
    2. <span data-ttu-id="7a735-163">Na página exibida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7a735-163">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="7a735-164">Na lista exibida, selecione o idioma do texto que você está inserindo.</span><span class="sxs-lookup"><span data-stu-id="7a735-164">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="7a735-165">No campo **Texto traduzido**, insira o texto.</span><span class="sxs-lookup"><span data-stu-id="7a735-165">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="7a735-166">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="7a735-166">Click **Close**.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="7a735-167">Especificar quando enviar notificações</span><span class="sxs-lookup"><span data-stu-id="7a735-167">Specify when notifications are sent</span></span>

<span data-ttu-id="7a735-168">Você pode enviar notificações às pessoas quando uma decisão é tomada, delegada ou escalonada.</span><span class="sxs-lookup"><span data-stu-id="7a735-168">You can send notifications to people when a decision has been made, delegated, or escalated.</span></span> <span data-ttu-id="7a735-169">Siga estas etapas para especificar quando enviar notificações e a quem elas devem ser enviadas.</span><span class="sxs-lookup"><span data-stu-id="7a735-169">Follow these steps to specify when notifications are sent, and who the notifications are sent to.</span></span>

1. <span data-ttu-id="7a735-170">No painel esquerdo, clique em **Notificações**.</span><span class="sxs-lookup"><span data-stu-id="7a735-170">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="7a735-171">Marque a caixa de seleção ao lado dos eventos para os quais as notificações devem ser enviadas:</span><span class="sxs-lookup"><span data-stu-id="7a735-171">Select the check box next to the events that notifications should be sent for:</span></span>

    - <span data-ttu-id="7a735-172">**\[Opção 1\]** – O usuário atribuído selecionou **\[Opção 1\]**.</span><span class="sxs-lookup"><span data-stu-id="7a735-172">**\[Choice 1\]** – The assigned user has selected **\[Choice 1\]**.</span></span>
    - <span data-ttu-id="7a735-173">**\[Opção 2\]** – O usuário atribuído selecionou **\[Opção 2\]**.</span><span class="sxs-lookup"><span data-stu-id="7a735-173">**\[Choice 2\]** – The assigned user has selected **\[Choice 2\]**.</span></span>
    - <span data-ttu-id="7a735-174">**Delegar** – O usuário atribuído atribuiu a decisão a outro usuário.</span><span class="sxs-lookup"><span data-stu-id="7a735-174">**Delegate** – The assigned user has assigned the decision to another user.</span></span>
    - <span data-ttu-id="7a735-175">**Escalonar** – O usuário atribuído não tomou a decisão no tempo alocado.</span><span class="sxs-lookup"><span data-stu-id="7a735-175">**Escalate** – The assigned user hasn't made the decision in the allotted time.</span></span>

3. <span data-ttu-id="7a735-176">Selecione a linha de um evento que você selecionou na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="7a735-176">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="7a735-177">Na guia **Texto da notificação**, insira o texto da notificação na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="7a735-177">On the **Notification text** tab, in the text box, enter the text of the notification.</span></span>
5. <span data-ttu-id="7a735-178">Para personalizar a notificação, você poderá inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="7a735-178">To personalize the notification, you can insert placeholders.</span></span> <span data-ttu-id="7a735-179">Os espaços reservados são substituídos pelos dados adequados quando a notificação é exibida para os usuários.</span><span class="sxs-lookup"><span data-stu-id="7a735-179">Placeholders are replaced with appropriate data when the notification is show to users.</span></span> <span data-ttu-id="7a735-180">Siga estas etapas para inserir um espaço reservado:</span><span class="sxs-lookup"><span data-stu-id="7a735-180">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="7a735-181">Na caixa de texto, clique no local onde o espaço reservado deve aparecer.</span><span class="sxs-lookup"><span data-stu-id="7a735-181">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="7a735-182">Clique em **Inserir espaço reservado**.</span><span class="sxs-lookup"><span data-stu-id="7a735-182">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="7a735-183">Na lista exibida, selecione o espaço reservado a ser inserido.</span><span class="sxs-lookup"><span data-stu-id="7a735-183">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="7a735-184">Clique em **Inserir**.</span><span class="sxs-lookup"><span data-stu-id="7a735-184">Click **Insert**.</span></span>

6. <span data-ttu-id="7a735-185">Para adicionar traduções da notificação, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="7a735-185">To add translations of the notification, follow these steps:</span></span>

    1. <span data-ttu-id="7a735-186">Clique em **Traduções**.</span><span class="sxs-lookup"><span data-stu-id="7a735-186">Click **Translations**.</span></span>
    2. <span data-ttu-id="7a735-187">Na página exibida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7a735-187">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="7a735-188">Na lista exibida, selecione o idioma do texto que você está inserindo.</span><span class="sxs-lookup"><span data-stu-id="7a735-188">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="7a735-189">No campo **Texto traduzido**, insira o texto.</span><span class="sxs-lookup"><span data-stu-id="7a735-189">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="7a735-190">Para personalizar o texto, insira os espaços reservados conforme descrito na etapa 5.</span><span class="sxs-lookup"><span data-stu-id="7a735-190">To personalize the text, you can insert placeholders as described in step 5.</span></span>
    6. <span data-ttu-id="7a735-191">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="7a735-191">Click **Close**.</span></span>

7. <span data-ttu-id="7a735-192">Na guia **Destinatário**, especifique para quem as notificações serão enviadas.</span><span class="sxs-lookup"><span data-stu-id="7a735-192">On the **Recipient** tab, specify who the notifications are sent to.</span></span> <span data-ttu-id="7a735-193">Selecione uma das opções na tabela a seguir e execute as etapas adicionais dessa opção antes de passar para a etapa 8.</span><span class="sxs-lookup"><span data-stu-id="7a735-193">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 8.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="7a735-194">Opção</span><span class="sxs-lookup"><span data-stu-id="7a735-194">Option</span></span></th>
    <th><span data-ttu-id="7a735-195">Destinatários da notificação</span><span class="sxs-lookup"><span data-stu-id="7a735-195">Notification recipients</span></span></th>
    <th><span data-ttu-id="7a735-196">Etapas adicionais</span><span class="sxs-lookup"><span data-stu-id="7a735-196">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="7a735-197">Participante</span><span class="sxs-lookup"><span data-stu-id="7a735-197">Participant</span></span></td>
    <td><span data-ttu-id="7a735-198">Usuários que foram atribuídos a uma função ou um grupo específico</span><span class="sxs-lookup"><span data-stu-id="7a735-198">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="7a735-199">Depois que você selecionar <strong>Participante</strong>, na guia <strong>Baseado em função</strong>, na lista <strong>Tipo de participante</strong>, selecione o tipo de grupo ou de função ao qual enviar notificações.</span><span class="sxs-lookup"><span data-stu-id="7a735-199">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="7a735-200">Na lista <strong>Participante</strong>, selecione o grupo ao qual serão enviadas notificações.</span><span class="sxs-lookup"><span data-stu-id="7a735-200">In the <strong>Participant</strong> list, select the group or to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="7a735-201">Usuário de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="7a735-201">Workflow user</span></span></td>
    <td><span data-ttu-id="7a735-202">Usuários no fluxo de trabalho atual</span><span class="sxs-lookup"><span data-stu-id="7a735-202">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="7a735-203">Depois que você selecionar <strong>Usuário de fluxo de trabalho</strong> na guia <strong>Usuário de fluxo de trabalho</strong>, na lista <strong>Usuário de fluxo de trabalho</strong>, selecione um usuário que participa do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7a735-203">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="7a735-204">Usuário</span><span class="sxs-lookup"><span data-stu-id="7a735-204">User</span></span></td>
    <td><span data-ttu-id="7a735-205">Usuários específicos do Microsoft Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7a735-205">Specific Microsoft Dynamics 365 for Finance and Operations users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="7a735-206">Após selecionar <strong>Usuário</strong>, clique na guia <strong>Usuário</strong>.</span><span class="sxs-lookup"><span data-stu-id="7a735-206">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="7a735-207">A lista <strong>Usuários disponíveis</strong> tem todos os usuários do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7a735-207">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="7a735-208">Selecione os usuários aos quais enviar notificações e mova- os para a lista <strong>Usuários selecionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="7a735-208">Select the users to send notifications to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="7a735-209">Repita as etapas de 3 a 7 para cada evento selecionado na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="7a735-209">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="assign-a-decision"></a><span data-ttu-id="7a735-210">Atribuir uma decisão</span><span class="sxs-lookup"><span data-stu-id="7a735-210">Assign a decision</span></span>

<span data-ttu-id="7a735-211">Siga estas etapas para especificar a quem uma decisão manual deve ser atribuída.</span><span class="sxs-lookup"><span data-stu-id="7a735-211">Follow these steps to specify who a manual decision should be assigned to.</span></span>

1. <span data-ttu-id="7a735-212">No painel esquerdo, clique em **Atribuição**.</span><span class="sxs-lookup"><span data-stu-id="7a735-212">In the left pane, click **Assignment**.</span></span>
2. <span data-ttu-id="7a735-213">Na guia **Tipo de atribuição**, selecione uma das opções na tabela a seguir e execute as etapas adicionais dessa opção antes de passar para a etapa 3.</span><span class="sxs-lookup"><span data-stu-id="7a735-213">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 3.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="7a735-214">Opção</span><span class="sxs-lookup"><span data-stu-id="7a735-214">Option</span></span></th>
    <th><span data-ttu-id="7a735-215">Usuários aos quais a decisão é atribuída</span><span class="sxs-lookup"><span data-stu-id="7a735-215">Users that the decision is assigned to</span></span></th>
    <th><span data-ttu-id="7a735-216">Etapas adicionais</span><span class="sxs-lookup"><span data-stu-id="7a735-216">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="7a735-217">Participante</span><span class="sxs-lookup"><span data-stu-id="7a735-217">Participant</span></span></td>
    <td><span data-ttu-id="7a735-218">Usuários que foram atribuídos a uma função ou um grupo específico</span><span class="sxs-lookup"><span data-stu-id="7a735-218">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="7a735-219">Depois que você selecionar <strong>Participante</strong>, na guia <strong>Baseado em função</strong>, na lista <strong>Tipo de participante</strong>, selecione o tipo de grupo ou de função ao qual atribuir a decisão.</span><span class="sxs-lookup"><span data-stu-id="7a735-219">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to assign the decision to.</span></span></li>
    <li><span data-ttu-id="7a735-220">Na lista <strong>Participante</strong>, selecione o grupo ou a função ao qual atribuir a decisão.</span><span class="sxs-lookup"><span data-stu-id="7a735-220">In the <strong>Participant</strong> list, select the group or role to assign the decision to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="7a735-221">Hierarquia</span><span class="sxs-lookup"><span data-stu-id="7a735-221">Hierarchy</span></span></td>
    <td><span data-ttu-id="7a735-222">Usuários em uma hierarquia organizacional específica</span><span class="sxs-lookup"><span data-stu-id="7a735-222">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="7a735-223">Depois que você selecionar <strong>Hierarquia</strong>, na guia <strong>Seleção de hierarquia</strong>, na lista <strong>Tipo de hierarquia</strong>, selecione o tipo de hierarquia ao qual atribuir a decisão.</span><span class="sxs-lookup"><span data-stu-id="7a735-223">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to assign the decision to.</span></span></li>
    <li><span data-ttu-id="7a735-224">O sistema deve recuperar um intervalo de nomes de usuário da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="7a735-224">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="7a735-225">Esses nomes representam usuários aos quais a decisão pode ser atribuída.</span><span class="sxs-lookup"><span data-stu-id="7a735-225">These names represent users that the decision can be assigned to.</span></span> <span data-ttu-id="7a735-226">Siga estas etapas para especificar o ponto inicial e final do intervalo de nomes de usuário que o sistema recupera:</span><span class="sxs-lookup"><span data-stu-id="7a735-226">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="7a735-227">Para especificar o ponto de partida, selecione uma pessoa na lista <strong>Iniciar em</strong>.</span><span class="sxs-lookup"><span data-stu-id="7a735-227">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="7a735-228">Para especificar o ponto final, clique em <strong>Adicionar condição</strong>.</span><span class="sxs-lookup"><span data-stu-id="7a735-228">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="7a735-229">Em seguida, insira uma condição que determine em que ponto da hierarquia o sistema para de recuperar nomes.</span><span class="sxs-lookup"><span data-stu-id="7a735-229">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="7a735-230">Na guia <strong>Opções de hierarquia</strong>, especifique a quais usuários no intervalo a decisão deve ser atribuída:</span><span class="sxs-lookup"><span data-stu-id="7a735-230">On the <strong>Hierarchy options</strong> tab, specify which users in the range the decision should be assigned to:</span></span> <ul>
    <li><span data-ttu-id="7a735-231"><strong>Atribuir a todos os usuários recuperados</strong> – A decisão é atribuída a todos os usuários do intervalo.</span><span class="sxs-lookup"><span data-stu-id="7a735-231"><strong>Assign to all users retrieved</strong> – The decision is assigned to all users in the range.</span></span></li>
    <li><span data-ttu-id="7a735-232"><strong>Atribuir somente ao último usuário recuperado</strong> – A decisão é atribuída somente ao último usuário do intervalo.</span><span class="sxs-lookup"><span data-stu-id="7a735-232"><strong>Assign only to last user retrieved</strong> – The decision is assigned to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="7a735-233"><strong>Excluir usuários com a seguinte condição</strong> – A decisão não é atribuída aos usuários do intervalo que atenderem a determinada condição.</span><span class="sxs-lookup"><span data-stu-id="7a735-233"><strong>Exclude users with the following condition</strong> – The decision isn't assigned to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="7a735-234">Clique em <strong>Adicionar condição</strong> para especificar a condição.</span><span class="sxs-lookup"><span data-stu-id="7a735-234">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="7a735-235">Usuário de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="7a735-235">Workflow user</span></span></td>
    <td><span data-ttu-id="7a735-236">Usuários no fluxo de trabalho atual</span><span class="sxs-lookup"><span data-stu-id="7a735-236">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="7a735-237">Depois que você selecionar <strong>Usuário de fluxo de trabalho</strong> na guia <strong>Usuário de fluxo de trabalho</strong>, na lista <strong>Usuário de fluxo de trabalho</strong>, selecione um usuário que participa do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7a735-237">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="7a735-238">Usuário</span><span class="sxs-lookup"><span data-stu-id="7a735-238">User</span></span></td>
    <td><span data-ttu-id="7a735-239">Usuários específicos do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7a735-239">Specific Finance and Operations users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="7a735-240">Após selecionar <strong>Usuário</strong>, clique na guia <strong>Usuário</strong>.</span><span class="sxs-lookup"><span data-stu-id="7a735-240">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="7a735-241">A lista <strong>Usuários disponíveis</strong> tem todos os usuários do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7a735-241">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="7a735-242">Selecione os usuários aos quais deseja atribuir a decisão e mova-os para a lista <strong>Usuários selecionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="7a735-242">Select the users to assign the decision to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="7a735-243">Fila</span><span class="sxs-lookup"><span data-stu-id="7a735-243">Queue</span></span></td>
    <td><span data-ttu-id="7a735-244">Uma fila de itens de trabalho</span><span class="sxs-lookup"><span data-stu-id="7a735-244">A work item queue</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="7a735-245">Após selecionar <strong>Fila</strong>, clique na guia <strong>Fila baseada</strong>.</span><span class="sxs-lookup"><span data-stu-id="7a735-245">After you select <strong>Queue</strong>, click the <strong>Queue based</strong> tab.</span></span></li>
    <li><span data-ttu-id="7a735-246">Para atribuir a decisão a uma fila específica, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="7a735-246">To assign the decision to a specific queue, follow these steps:</span></span> <ol>
    <li><span data-ttu-id="7a735-247">Na lista <strong>Tipo de fila</strong>, selecione <strong>Fila de itens de trabalho</strong>.</span><span class="sxs-lookup"><span data-stu-id="7a735-247">In the <strong>Queue type</strong> list, select <strong>Work item queues</strong>.</span></span></li>
    <li><span data-ttu-id="7a735-248">Na lista <strong>Nome da fila</strong>, selecione a fila.</span><span class="sxs-lookup"><span data-stu-id="7a735-248">In the <strong>Queue name</strong> list, select the queue.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="7a735-249">Se uma condição específica tiver que determinar a qual fila atribuir a decisão, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="7a735-249">If a specific condition should determine which queue the decision is assigned to, follow these steps:</span></span> <ol>
    <li><span data-ttu-id="7a735-250">Na lista <strong>Tipo de fila</strong>, selecione <strong>Filas de itens de trabalho condicionais</strong>.</span><span class="sxs-lookup"><span data-stu-id="7a735-250">In the <strong>Queue type</strong> list, select <strong>Conditional work item queues</strong>.</span></span></li>
    <li><span data-ttu-id="7a735-251">Na lista <strong>Nome da fila</strong>, selecione <strong>Fila condicional</strong>.</span><span class="sxs-lookup"><span data-stu-id="7a735-251">In the <strong>Queue name</strong> list, select <strong>Conditional queue</strong>.</span></span></li>
    </ol>
    </li>
    </ol>
    <blockquote>[!NOTE] <span data-ttu-id="7a735-252">Esta opção é usada apenas para alguns fluxos de trabalho, como Gerenciamento de casos.</span><span class="sxs-lookup"><span data-stu-id="7a735-252">This option is used for only a few workflows, such as Case management.</span></span></blockquote>
    </td>
    </tr>
    </tbody>
    </table>

3. <span data-ttu-id="7a735-253">Na guia **Limite de tempo**, no campo **Duração**, especifique quanto tempo o usuário tem para tomar a decisão.</span><span class="sxs-lookup"><span data-stu-id="7a735-253">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to make the decision.</span></span> <span data-ttu-id="7a735-254">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="7a735-254">Select one of the following options:</span></span>

    - <span data-ttu-id="7a735-255">**Horas** – Insira o número de horas que o usuário tem para tomar a decisão.</span><span class="sxs-lookup"><span data-stu-id="7a735-255">**Hours** – Enter the number of hours that the user has to make the decision.</span></span> <span data-ttu-id="7a735-256">Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.</span><span class="sxs-lookup"><span data-stu-id="7a735-256">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="7a735-257">**Dias** – Insira o número de dias que o usuário tem para tomar a decisão.</span><span class="sxs-lookup"><span data-stu-id="7a735-257">**Days** – Enter the number of days that the user has to make the decision.</span></span> <span data-ttu-id="7a735-258">Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.</span><span class="sxs-lookup"><span data-stu-id="7a735-258">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="7a735-259">**Semanas** – Insira o número de semanas que o usuário tem para tomar a decisão.</span><span class="sxs-lookup"><span data-stu-id="7a735-259">**Weeks** – Enter the number of weeks that the user has to make the decision.</span></span>
    - <span data-ttu-id="7a735-260">**Meses** – Selecione o dia e a semana até quando o usuário deve tomar a decisão.</span><span class="sxs-lookup"><span data-stu-id="7a735-260">**Months** – Select the day and week that the user must make the decision by.</span></span> <span data-ttu-id="7a735-261">Por exemplo, talvez você queira que o usuário tome a decisão até sexta-feira da terceira semana do mês.</span><span class="sxs-lookup"><span data-stu-id="7a735-261">For example, you might want the user to make the decision by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="7a735-262">**Anos** – Selecione o dia, a semana e o mês até quando o usuário deve tomar a decisão.</span><span class="sxs-lookup"><span data-stu-id="7a735-262">**Years** – Select the day, week, and month that the user must make the decision by.</span></span> <span data-ttu-id="7a735-263">Por exemplo, talvez você queira que o usuário tome a decisão até a sexta-feira da terceira semana de dezembro.</span><span class="sxs-lookup"><span data-stu-id="7a735-263">For example, you might want the user to make the decision by Friday of the third week of December.</span></span>

    <span data-ttu-id="7a735-264">Se o usuário não tomar a decisão no tempo alocado, a decisão vencerá.</span><span class="sxs-lookup"><span data-stu-id="7a735-264">If the user doesn't make the decision in the allotted time, the decision is overdue.</span></span> <span data-ttu-id="7a735-265">Uma decisão vencida será escalonado, com base nas opções selecionadas na área **Escalonamento** da página.</span><span class="sxs-lookup"><span data-stu-id="7a735-265">A decision that is overdue is escalated, based on the options that you select in the **Escalation** area of the page.</span></span>

## <a name="specify-what-happens-when-a-decision-is-overdue"></a><span data-ttu-id="7a735-266">Especificar o que acontece quando uma decisão vence</span><span class="sxs-lookup"><span data-stu-id="7a735-266">Specify what happens when a decision is overdue</span></span>

<span data-ttu-id="7a735-267">Se um usuário não tomar a decisão no tempo alocado, a decisão vencerá.</span><span class="sxs-lookup"><span data-stu-id="7a735-267">If a user doesn't make the decision in the allotted time, the decision is overdue.</span></span> <span data-ttu-id="7a735-268">Uma decisão vencida pode ser escalonada ou atribuída automaticamente a outro usuário.</span><span class="sxs-lookup"><span data-stu-id="7a735-268">A decision that is overdue can be escalated, or automatically assigned to another user.</span></span> <span data-ttu-id="7a735-269">Siga estas etapas para escalonar a decisão se ela estiver vencida.</span><span class="sxs-lookup"><span data-stu-id="7a735-269">Follow these steps to escalate the decision if it's overdue.</span></span>

1. <span data-ttu-id="7a735-270">No painel esquerdo, clique em **Escalonamento**.</span><span class="sxs-lookup"><span data-stu-id="7a735-270">In the left pane, click **Escalation**.</span></span>
2. <span data-ttu-id="7a735-271">Marque a caixa de seleção **Usar caminho de escalonamento** para criar um caminho de escalonamento.</span><span class="sxs-lookup"><span data-stu-id="7a735-271">Select the **Use escalation path** check box to create an escalation path.</span></span> <span data-ttu-id="7a735-272">O sistema atribuirá automaticamente a decisão aos usuários listados no caminho de escalonamento.</span><span class="sxs-lookup"><span data-stu-id="7a735-272">The system automatically assigns the decision to the users who are listed in the escalation path.</span></span> <span data-ttu-id="7a735-273">Por exemplo, a tabela a seguir representa um caminho de escalonamento.</span><span class="sxs-lookup"><span data-stu-id="7a735-273">For example, the following table represents an escalation path.</span></span>

    | <span data-ttu-id="7a735-274">Sequência</span><span class="sxs-lookup"><span data-stu-id="7a735-274">Sequence</span></span> | <span data-ttu-id="7a735-275">Caminho de escalonamento</span><span class="sxs-lookup"><span data-stu-id="7a735-275">Escalation path</span></span>            |
    |----------|----------------------------|
    | <span data-ttu-id="7a735-276">1</span><span class="sxs-lookup"><span data-stu-id="7a735-276">1</span></span>        | <span data-ttu-id="7a735-277">Atribuir a: Denise</span><span class="sxs-lookup"><span data-stu-id="7a735-277">Assign to: Donna</span></span>           |
    | <span data-ttu-id="7a735-278">2</span><span class="sxs-lookup"><span data-stu-id="7a735-278">2</span></span>        | <span data-ttu-id="7a735-279">Atribuir a: Eduardo</span><span class="sxs-lookup"><span data-stu-id="7a735-279">Assign to: Erin</span></span>            |
    | <span data-ttu-id="7a735-280">3</span><span class="sxs-lookup"><span data-stu-id="7a735-280">3</span></span>        | <span data-ttu-id="7a735-281">Ação final: \[Opção 1\]</span><span class="sxs-lookup"><span data-stu-id="7a735-281">Final action: \[Choice 1\]</span></span> |

    <span data-ttu-id="7a735-282">Neste exemplo, o sistema atribui a decisão vencida à Denise.</span><span class="sxs-lookup"><span data-stu-id="7a735-282">In this example, the system assigns the overdue decision to Donna.</span></span> <span data-ttu-id="7a735-283">Se a Denise não tomar a decisão no tempo alocado, o sistema a atribuirá a Eduardo.</span><span class="sxs-lookup"><span data-stu-id="7a735-283">If Donna doesn't make the decision in the allotted time, the system assigns the decision to Erin.</span></span> <span data-ttu-id="7a735-284">Se Eduardo não tomar a decisão no tempo alocado, o sistema selecionará **\[Opção 1\]** como decisão.</span><span class="sxs-lookup"><span data-stu-id="7a735-284">If Erin doesn't make the decision in the allotted time, the system selects **\[Choice 1\]** as the decision.</span></span>

3. <span data-ttu-id="7a735-285">Para adicionar um usuário ao caminho de escalonamento, clique em **Adicionar escalonamento**.</span><span class="sxs-lookup"><span data-stu-id="7a735-285">To add a user to the escalation path, click **Add escalation**.</span></span> <span data-ttu-id="7a735-286">Selecione uma das opções na tabela a seguir e execute as etapas adicionais dessa opção antes de passar para a etapa 4.</span><span class="sxs-lookup"><span data-stu-id="7a735-286">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 4.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="7a735-287">Opção</span><span class="sxs-lookup"><span data-stu-id="7a735-287">Option</span></span></th>
    <th><span data-ttu-id="7a735-288">Usuários para os quais a decisão será escalonada</span><span class="sxs-lookup"><span data-stu-id="7a735-288">Users that the decision is escalated to</span></span></th>
    <th><span data-ttu-id="7a735-289">Etapas adicionais</span><span class="sxs-lookup"><span data-stu-id="7a735-289">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="7a735-290">Hierarquia</span><span class="sxs-lookup"><span data-stu-id="7a735-290">Hierarchy</span></span></td>
    <td><span data-ttu-id="7a735-291">Usuários em uma hierarquia organizacional específica</span><span class="sxs-lookup"><span data-stu-id="7a735-291">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="7a735-292">Depois que você selecionar <strong>Hierarquia</strong>, na guia <strong>Seleção de hierarquia</strong>, na lista <strong>Tipo de hierarquia</strong>, selecione o tipo de hierarquia ao qual a decisão será escalonada.</span><span class="sxs-lookup"><span data-stu-id="7a735-292">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to escalate the decision to.</span></span></li>
    <li><span data-ttu-id="7a735-293">O sistema deve recuperar um intervalo de nomes de usuário da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="7a735-293">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="7a735-294">Esses nomes representam os usuários aos quais a decisão pode ser escalonada.</span><span class="sxs-lookup"><span data-stu-id="7a735-294">These names represent users that the decision can be escalated to.</span></span> <span data-ttu-id="7a735-295">Siga estas etapas para especificar o ponto inicial e final do intervalo de nomes de usuário que o sistema recupera:</span><span class="sxs-lookup"><span data-stu-id="7a735-295">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="7a735-296">Para especificar o ponto de partida, selecione uma pessoa na lista <strong>Iniciar em</strong>.</span><span class="sxs-lookup"><span data-stu-id="7a735-296">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="7a735-297">Para especificar o ponto final, clique em <strong>Adicionar condição</strong>.</span><span class="sxs-lookup"><span data-stu-id="7a735-297">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="7a735-298">Em seguida, insira uma condição que determine em que ponto da hierarquia o sistema para de recuperar nomes.</span><span class="sxs-lookup"><span data-stu-id="7a735-298">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="7a735-299">Na guia <strong>Opções de hierarquia</strong>, especifique a quais usuários no intervalo a decisão deve ser escalonada:</span><span class="sxs-lookup"><span data-stu-id="7a735-299">On the <strong>Hierarchy options</strong> tab, specify which users in the range the decision should be escalated to:</span></span> <ul>
    <li><span data-ttu-id="7a735-300"><strong>Atribuir a todos os usuários recuperados</strong> – A decisão é escalonada a todos os usuários do intervalo.</span><span class="sxs-lookup"><span data-stu-id="7a735-300"><strong>Assign to all users retrieved</strong> – The decision is escalated to all users in the range.</span></span></li>
    <li><span data-ttu-id="7a735-301"><strong>Atribuir somente ao último usuário recuperado</strong> – A decisão é escalonada somente ao último usuário do intervalo.</span><span class="sxs-lookup"><span data-stu-id="7a735-301"><strong>Assign only to last user retrieved</strong> – The decision is escalated to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="7a735-302"><strong>Excluir usuários com a seguinte condição:</strong> – A decisão não é escalonada aos usuários do intervalo que atenderem a determinada condição.</span><span class="sxs-lookup"><span data-stu-id="7a735-302"><strong>Exclude users with the following condition:</strong> – The decision isn't escalated to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="7a735-303">Clique em <strong>Adicionar condição</strong> para especificar a condição.</span><span class="sxs-lookup"><span data-stu-id="7a735-303">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="7a735-304">Usuário de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="7a735-304">Workflow user</span></span></td>
    <td><span data-ttu-id="7a735-305">Usuários no fluxo de trabalho atual</span><span class="sxs-lookup"><span data-stu-id="7a735-305">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="7a735-306">Depois que você selecionar <strong>Usuário de fluxo de trabalho</strong> na guia <strong>Usuário de fluxo de trabalho</strong>, na lista <strong>Usuário de fluxo de trabalho</strong>, selecione um usuário que participa do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7a735-306">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="7a735-307">Usuário</span><span class="sxs-lookup"><span data-stu-id="7a735-307">User</span></span></td>
    <td><span data-ttu-id="7a735-308">Usuários específicos do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="7a735-308">Specific Finance and Operations users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="7a735-309">Após selecionar <strong>Usuário</strong>, clique na guia <strong>Usuário</strong>.</span><span class="sxs-lookup"><span data-stu-id="7a735-309">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="7a735-310">A lista <strong>Usuários disponíveis</strong> tem todos os usuários do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7a735-310">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="7a735-311">Selecione os usuários aos quais a decisão será escalonada e mova-os para a lista <strong>Usuários selecionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="7a735-311">Select the users to escalate the decision to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. <span data-ttu-id="7a735-312">Na guia **Limite de tempo**, no campo **Duração**, especifique quanto tempo o usuário tem para tomar a decisão.</span><span class="sxs-lookup"><span data-stu-id="7a735-312">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to make the decision.</span></span> <span data-ttu-id="7a735-313">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="7a735-313">Select one of the following options:</span></span>

    - <span data-ttu-id="7a735-314">**Horas** – Insira o número de horas que o usuário tem para tomar a decisão.</span><span class="sxs-lookup"><span data-stu-id="7a735-314">**Hours** – Enter the number of hours that the user has to make the decision.</span></span> <span data-ttu-id="7a735-315">Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.</span><span class="sxs-lookup"><span data-stu-id="7a735-315">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="7a735-316">**Dias** – Insira o número de dias que o usuário tem para tomar a decisão.</span><span class="sxs-lookup"><span data-stu-id="7a735-316">**Days** – Enter the number of days that the user has to make the decision.</span></span> <span data-ttu-id="7a735-317">Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.</span><span class="sxs-lookup"><span data-stu-id="7a735-317">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="7a735-318">**Semanas** – Insira o número de semanas que o usuário tem para tomar a decisão.</span><span class="sxs-lookup"><span data-stu-id="7a735-318">**Weeks** – Enter the number of weeks that the user has to make the decision.</span></span>
    - <span data-ttu-id="7a735-319">**Meses** – Selecione o dia e a semana até quando o usuário deve tomar a decisão.</span><span class="sxs-lookup"><span data-stu-id="7a735-319">**Months** – Select the day and week that the user must make the decision by.</span></span> <span data-ttu-id="7a735-320">Por exemplo, talvez você queira que o usuário tome a decisão até sexta-feira da terceira semana do mês.</span><span class="sxs-lookup"><span data-stu-id="7a735-320">For example, you might want the user to make the decision by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="7a735-321">**Anos** – Selecione o dia, a semana e o mês até quando o usuário deve tomar a decisão.</span><span class="sxs-lookup"><span data-stu-id="7a735-321">**Years** – Select the day, week, and month that the user must make the decision by.</span></span> <span data-ttu-id="7a735-322">Por exemplo, talvez você queira que o usuário tome a decisão até a sexta-feira da terceira semana de dezembro.</span><span class="sxs-lookup"><span data-stu-id="7a735-322">For example, you might want the user to make the decision by Friday of the third week of December.</span></span>

5. <span data-ttu-id="7a735-323">Repita as etapas de 3 a 4 para cada usuário que deve ser adicionado ao caminho de escalonamento.</span><span class="sxs-lookup"><span data-stu-id="7a735-323">Repeat steps 3 through 4 for each user that should be added to the escalation path.</span></span> <span data-ttu-id="7a735-324">Você pode alterar a ordem dos usuários.</span><span class="sxs-lookup"><span data-stu-id="7a735-324">You can change the order of the users.</span></span>
6. <span data-ttu-id="7a735-325">Se os usuários listados no caminho de escalonamento não tomarem a decisão no tempo alocado, o sistema tomará a decisão.</span><span class="sxs-lookup"><span data-stu-id="7a735-325">If the users in the escalation path don't make the decision in the allotted time, the system makes the decision.</span></span> <span data-ttu-id="7a735-326">Para especificar a opção que o sistema selecionará, selecione a linha **Ação** e, na guia **Encerrar ação**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="7a735-326">To specify the option that the system selects, select the **Action** row, and then, on the **End action** tab, select an option.</span></span>

## <a name="set-a-time-limit"></a><span data-ttu-id="7a735-327">Definir um limite de tempo</span><span class="sxs-lookup"><span data-stu-id="7a735-327">Set a time limit</span></span>

<span data-ttu-id="7a735-328">Siga estas etapas caso a decisão deva ser tomada em um horário específico.</span><span class="sxs-lookup"><span data-stu-id="7a735-328">Follow these steps if the decision must be made in a specific time.</span></span>

> [!NOTE]
> <span data-ttu-id="7a735-329">As opções selecionadas neste procedimento substituirão as que você selecionou nas áreas **Atribuição** e **Escalonamento** da página.</span><span class="sxs-lookup"><span data-stu-id="7a735-329">The options that you select in this procedure override the options that you selected in the **Assignment** and **Escalation** areas of the page.</span></span>

1. <span data-ttu-id="7a735-330">No painel esquerdo, clique em **Configurações avançadas**.</span><span class="sxs-lookup"><span data-stu-id="7a735-330">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="7a735-331">Marque a caixa de seleção **Definir um limite de tempo para o elemento de fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="7a735-331">Select the **Set a time limit for the workflow element** check box.</span></span>
3. <span data-ttu-id="7a735-332">No campo **Duração**, especifique quando a decisão deve ser tomada.</span><span class="sxs-lookup"><span data-stu-id="7a735-332">In the **Duration** field, specify when the decision must be made.</span></span> <span data-ttu-id="7a735-333">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="7a735-333">Select one of the following options:</span></span>

    - <span data-ttu-id="7a735-334">**Horas** - Insira o número de horas.</span><span class="sxs-lookup"><span data-stu-id="7a735-334">**Hours** – Enter the number of hours.</span></span> <span data-ttu-id="7a735-335">Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.</span><span class="sxs-lookup"><span data-stu-id="7a735-335">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="7a735-336">**Dias** – Insira o número de dias.</span><span class="sxs-lookup"><span data-stu-id="7a735-336">**Days** – Enter the number of days.</span></span> <span data-ttu-id="7a735-337">Selecione o calendário usado pela sua organização e insira informações sobre a semana de trabalho da organização.</span><span class="sxs-lookup"><span data-stu-id="7a735-337">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="7a735-338">**Semanas** – Insira o número de semanas.</span><span class="sxs-lookup"><span data-stu-id="7a735-338">**Weeks** – Enter the number of weeks.</span></span>
    - <span data-ttu-id="7a735-339">**Meses** – Selecione o dia e a semana até quando a decisão deve ser tomada.</span><span class="sxs-lookup"><span data-stu-id="7a735-339">**Months** – Select the day and week that the decision must be made by.</span></span> <span data-ttu-id="7a735-340">Por exemplo, você talvez queira que a decisão seja tomada até a sexta-feira da terceira semana do mês.</span><span class="sxs-lookup"><span data-stu-id="7a735-340">For example, you might want the decision to be made by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="7a735-341">**Anos** – Selecione o dia, a semana e o mês até quando a decisão deve ser tomada.</span><span class="sxs-lookup"><span data-stu-id="7a735-341">**Years** – Select the day, week, and month that the decision must be made by.</span></span> <span data-ttu-id="7a735-342">Por exemplo, você talvez queira que a decisão seja tomada até a sexta-feira da terceira semana de dezembro.</span><span class="sxs-lookup"><span data-stu-id="7a735-342">For example, you might want the decision to be made by Friday of the third week of December.</span></span>

4. <span data-ttu-id="7a735-343">Se o limite de tempo for excedido, o sistema tomará a decisão.</span><span class="sxs-lookup"><span data-stu-id="7a735-343">If the time limit is exceeded, the system makes the decision.</span></span> <span data-ttu-id="7a735-344">Na lista **Ação**, selecione a opção que o sistema deve selecionar.</span><span class="sxs-lookup"><span data-stu-id="7a735-344">In the **Action** list, select the option that the system should select.</span></span>
