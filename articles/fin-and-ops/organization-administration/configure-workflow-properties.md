---
title: Configurar propriedades do fluxo de trabalho
description: Este tópico explica como configurar as várias propriedades de um fluxo de trabalho.
author: sericks007
manager: AnnBe
ms.date: 07/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 576ce368b2a8672aa39116eb0cc6e3d3f2a06bb3
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "328461"
---
# <a name="configure-workflow-properties"></a><span data-ttu-id="2e44b-103">Configurar propriedades do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="2e44b-103">Configure workflow properties</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2e44b-104">Este tópico explica como configurar as várias propriedades de um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2e44b-104">This topic explains how to configure the various properties of a workflow.</span></span>

<span data-ttu-id="2e44b-105">Para configurar as propriedades de um fluxo de trabalho, abra o fluxo de trabalho no editor.</span><span class="sxs-lookup"><span data-stu-id="2e44b-105">To configure the properties of a workflow, open the workflow in the workflow editor.</span></span> <span data-ttu-id="2e44b-106">Clique na tela do editor de fluxo de trabalho e clique em **Propriedades** para abrir a página **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-106">Click the canvas of the workflow editor, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="2e44b-107">Em seguida, use os procedimentos a seguir para configurar as várias propriedades do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2e44b-107">You can then use the following procedures to configure the various properties of the workflow.</span></span>

## <a name="name-the-workflow"></a><span data-ttu-id="2e44b-108">Nomear o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="2e44b-108">Name the workflow</span></span>

<span data-ttu-id="2e44b-109">Siga as etapas abaixo para inserir um nome para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2e44b-109">Follow these steps to enter a name for the workflow.</span></span>

1. <span data-ttu-id="2e44b-110">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-110">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="2e44b-111">No campo **Nome**, insira um nome exclusivo para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2e44b-111">In the **Name** field, enter a unique name for the workflow.</span></span> <span data-ttu-id="2e44b-112">Por exemplo, se você criar um fluxo de trabalho de requisição de compra para cada país/região onde opera, poderá nomear um fluxo de trabalho como **Requisições de Compra - Dinamarca** ou **Requisições de Compra - Espanha**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-112">For example, if you create a purchase requisition workflow for each country/region that you operate in, you can name the purchase requisition workflow **Purchase Requisitions Denmark** or **Purchase Requisitions Spain**.</span></span>

## <a name="specify-the-workflow-owner"></a><span data-ttu-id="2e44b-113">Especificar o proprietário do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="2e44b-113">Specify the workflow owner</span></span>

<span data-ttu-id="2e44b-114">O proprietário do fluxo de trabalho é a pessoa que gerencia e mantém o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2e44b-114">The workflow owner is the person who manages and maintains the workflow.</span></span> <span data-ttu-id="2e44b-115">Siga estas etapas para especificar o proprietário do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2e44b-115">Follow these steps to specify the workflow owner.</span></span>

1. <span data-ttu-id="2e44b-116">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-116">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="2e44b-117">Na lista **Proprietário**, selecione o nome da pessoa que gerenciará o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2e44b-117">In the **Owner** list, select the name of the person who will manage the workflow.</span></span>

## <a name="select-an-email-template"></a><span data-ttu-id="2e44b-118">Selecionar um modelo de email</span><span class="sxs-lookup"><span data-stu-id="2e44b-118">Select an email template</span></span>

<span data-ttu-id="2e44b-119">Siga estas etapas para selecionar o modelo de email que será usado para gerar mensagens de notificação sobre o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2e44b-119">Follow these steps to select the email template that is used to generate notification messages about the workflow.</span></span>

1. <span data-ttu-id="2e44b-120">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-120">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="2e44b-121">Na lista **Modelo de email para notificações de fluxo de trabalho**, selecione o modelo.</span><span class="sxs-lookup"><span data-stu-id="2e44b-121">In the **Email template for workflow notifications** list, select the template.</span></span>

## <a name="enter-instructions-for-users"></a><span data-ttu-id="2e44b-122">Inserir instruções para os usuários</span><span class="sxs-lookup"><span data-stu-id="2e44b-122">Enter instructions for users</span></span>

<span data-ttu-id="2e44b-123">Você pode fornecer instruções aos usuários que enviarão documentos para processamento e aprovação.</span><span class="sxs-lookup"><span data-stu-id="2e44b-123">You can provide instructions to users who submit documents for processing and approval.</span></span> <span data-ttu-id="2e44b-124">Esses usuários também são conhecidos como *originadores*.</span><span class="sxs-lookup"><span data-stu-id="2e44b-124">These users are also referred to as *originators*.</span></span> <span data-ttu-id="2e44b-125">Por exemplo, suponha que você esteja criando um fluxo de trabalho de requisição de compra e insira instruções.</span><span class="sxs-lookup"><span data-stu-id="2e44b-125">For example, you're creating a purchase requisition workflow, and you enter instructions.</span></span> <span data-ttu-id="2e44b-126">Essas instruções fornecidas poderão ser exibidas pelos usuários que inserirem requisições de compra na página **Requisições de compra**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-126">Those instructions can then be viewed by users who enter purchase requisitions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="2e44b-127">Para exibir instruções, o originador clica no ícone na barra de mensagens de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2e44b-127">To view instructions, the originator clicks the icon in the workflow message bar.</span></span> <span data-ttu-id="2e44b-128">Siga estas etapas para inserir instruções para os usuários.</span><span class="sxs-lookup"><span data-stu-id="2e44b-128">Follow these steps to enter instructions for users.</span></span>

1. <span data-ttu-id="2e44b-129">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-129">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="2e44b-130">No campo **Enviar instruções**, insira as instruções.</span><span class="sxs-lookup"><span data-stu-id="2e44b-130">In the **Submission instructions** field, enter the instructions.</span></span>
3. <span data-ttu-id="2e44b-131">Para personalizar as instruções, você pode inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="2e44b-131">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="2e44b-132">Os espaços reservados são substituídos pelos dados adequados quando as instruções são exibidas para os usuários.</span><span class="sxs-lookup"><span data-stu-id="2e44b-132">Placeholders are replaced with the appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="2e44b-133">Para inserir um espaço reservado, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2e44b-133">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="2e44b-134">Clique no campo **Instruções de envio** para especificar onde o espaço reservado deve aparecer.</span><span class="sxs-lookup"><span data-stu-id="2e44b-134">Click in the **Submission instructions** field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="2e44b-135">Clique em **Inserir espaço reservado**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-135">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="2e44b-136">Na lista exibida, selecione o espaço reservado a ser inserido.</span><span class="sxs-lookup"><span data-stu-id="2e44b-136">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="2e44b-137">Clique em **Inserir**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-137">Click **Insert**.</span></span>

4. <span data-ttu-id="2e44b-138">Para adicionar traduções das instruções, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2e44b-138">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="2e44b-139">Clique em **Traduções**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-139">Click **Translations**.</span></span>
    2. <span data-ttu-id="2e44b-140">Na página exibida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-140">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="2e44b-141">Na lista exibida, selecione o idioma do texto que você inserirá.</span><span class="sxs-lookup"><span data-stu-id="2e44b-141">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="2e44b-142">No campo **Texto traduzido**, insira o texto.</span><span class="sxs-lookup"><span data-stu-id="2e44b-142">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="2e44b-143">Para personalizar o texto, você poderá inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="2e44b-143">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="2e44b-144">Para obter instruções sobre como inserir um espaço reservado, consulte a etapa 3.</span><span class="sxs-lookup"><span data-stu-id="2e44b-144">For instructions about how to enter a placeholder, see step 3.</span></span>
    6. <span data-ttu-id="2e44b-145">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-145">Click **Close**.</span></span>

## <a name="specify-when-this-workflow-is-used"></a><span data-ttu-id="2e44b-146">Especificar quando esse fluxo de trabalho será usado</span><span class="sxs-lookup"><span data-stu-id="2e44b-146">Specify when this workflow is used</span></span>

<span data-ttu-id="2e44b-147">Você pode criar vários fluxos de trabalho baseados no mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="2e44b-147">You can create multiple workflows that are based on the same type.</span></span> <span data-ttu-id="2e44b-148">Por exemplo, você pode criar um fluxo de trabalho de requisição de compra para cada país/região onde opera, como Requisições de Compra - Dinamarca e Requisições de Compra - Espanha.</span><span class="sxs-lookup"><span data-stu-id="2e44b-148">For example, you can create a purchase requisition workflow for each country/region that you operate in, such as Purchase Requisitions Denmark and Purchase Requisitions Spain.</span></span> <span data-ttu-id="2e44b-149">Se houver vários fluxos de trabalho baseados no mesmo tipo, será necessário especificar quando cada um deles será usado.</span><span class="sxs-lookup"><span data-stu-id="2e44b-149">When you have multiple workflows that are based on the same type, you must specify when each workflow is used.</span></span> <span data-ttu-id="2e44b-150">No exemplo anterior, especifique as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="2e44b-150">For the preceding example, you specify the following conditions:</span></span>

- <span data-ttu-id="2e44b-151">As Requisições de Compra - Dinamarca são usadas quando: país/região = DK</span><span class="sxs-lookup"><span data-stu-id="2e44b-151">Purchase Requisitions Denmark is used when: country/region = DK</span></span>
- <span data-ttu-id="2e44b-152">As Requisições de Compra - Espanha são usadas quando: país/região = DK</span><span class="sxs-lookup"><span data-stu-id="2e44b-152">Purchase Requisitions Spain is used when: country/region = ES</span></span>

<span data-ttu-id="2e44b-153">Siga estas etapas para especificar quando o fluxo de trabalho que você está configurando será usado.</span><span class="sxs-lookup"><span data-stu-id="2e44b-153">Follow these steps to specify when the workflow that you're configuring is used.</span></span>

1. <span data-ttu-id="2e44b-154">No painel esquerdo, clique em **Ativação**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-154">In the left pane, click **Activation**.</span></span>
2. <span data-ttu-id="2e44b-155">Marque a caixa de seleção **Definir as condições para executar este fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-155">Select the **Set the conditions for running this workflow** check box.</span></span>
3. <span data-ttu-id="2e44b-156">Clique em **Adicionar condição**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-156">Click **Add condition**.</span></span>
4. <span data-ttu-id="2e44b-157">Insira uma condição.</span><span class="sxs-lookup"><span data-stu-id="2e44b-157">Enter a condition.</span></span>
5. <span data-ttu-id="2e44b-158">Insira quaisquer condições adicionais necessárias.</span><span class="sxs-lookup"><span data-stu-id="2e44b-158">Enter any additional conditions that are required.</span></span>
6. <span data-ttu-id="2e44b-159">Para verificar se as condições inseridas foram definidas corretamente, execute estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2e44b-159">To verify that the conditions that you entered are set correctly, follow these steps:</span></span>

    1. <span data-ttu-id="2e44b-160">Clique em **Teste**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-160">Click **Test**.</span></span>
    2. <span data-ttu-id="2e44b-161">Na página **Testar condição de fluxo de trabalho**, na área **Validar condição**, selecione um registro.</span><span class="sxs-lookup"><span data-stu-id="2e44b-161">On the **Test workflow condition** page, in the **Validate condition** area, select a record.</span></span>
    3. <span data-ttu-id="2e44b-162">Clique em **Teste**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-162">Click **Test**.</span></span> <span data-ttu-id="2e44b-163">O sistema avaliará o registro para determinar se ele atende às condições especificadas.</span><span class="sxs-lookup"><span data-stu-id="2e44b-163">The system evaluates the record to determine whether it meets the conditions that you specified.</span></span> <span data-ttu-id="2e44b-164">Por exemplo, se você estiver criando um fluxo de trabalho de requisição de compra para a Espanha, a área **Validar condição** da página exibirá uma lista de requisições de compra.</span><span class="sxs-lookup"><span data-stu-id="2e44b-164">For example, if you're creating a purchase requisition workflow for Spain, the **Validate condition** area of the page shows a list of purchase requisitions.</span></span> <span data-ttu-id="2e44b-165">Quando você clicar em **Testar**, o sistema avaliará a requisição de compra selecionada para determinar se o país/região é ES.</span><span class="sxs-lookup"><span data-stu-id="2e44b-165">When you click **Test**, the system evaluates the selected purchase requisition to determine whether the country/region is ES.</span></span>
    4. <span data-ttu-id="2e44b-166">Clique em **OK** ou **Cancelar** para retornar à página **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-166">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="2e44b-167">Especificar quando enviar notificações</span><span class="sxs-lookup"><span data-stu-id="2e44b-167">Specify when notifications are sent</span></span>

<span data-ttu-id="2e44b-168">Quando um documento é enviado para processamento, é criada uma instância do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2e44b-168">When a document is submitted for processing, a workflow instance is created.</span></span> <span data-ttu-id="2e44b-169">Você poderá enviar notificações para os usuários quando instâncias baseadas nesse fluxo de trabalho forem iniciadas, concluídas, encerradas ou interrompidas devido a um erro.</span><span class="sxs-lookup"><span data-stu-id="2e44b-169">You can send notifications to users when workflow instances that are based on the workflow are started, completed, terminated, or stopped because of an error.</span></span> <span data-ttu-id="2e44b-170">Siga estas etapas para especificar quando as notificações serão enviadas.</span><span class="sxs-lookup"><span data-stu-id="2e44b-170">Follow these steps to specify when notifications are sent.</span></span>

1. <span data-ttu-id="2e44b-171">No painel esquerdo, clique em **Notificações**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-171">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="2e44b-172">Marque a caixa de seleção para cada evento que disparará notificações:</span><span class="sxs-lookup"><span data-stu-id="2e44b-172">Select the check box for each event that should trigger notifications:</span></span>

    - <span data-ttu-id="2e44b-173">**Iniciado**– Enviar notificações quando uma instância de fluxo de trabalho for iniciada.</span><span class="sxs-lookup"><span data-stu-id="2e44b-173">**Started** – Send notifications when a workflow instance is started.</span></span>
    - <span data-ttu-id="2e44b-174">**Parado** – Enviar notificações quando uma instância de fluxo de trabalho for interrompida devido a um erro.</span><span class="sxs-lookup"><span data-stu-id="2e44b-174">**Stopped** – Send notifications when a workflow instance is stopped because of an error.</span></span>
    - <span data-ttu-id="2e44b-175">**Concluído** – Enviar notificações quando uma instância de fluxo de trabalho for concluída.</span><span class="sxs-lookup"><span data-stu-id="2e44b-175">**Completed** – Send notifications when a workflow instance is completed.</span></span>
    - <span data-ttu-id="2e44b-176">**Irrecuperável** – Enviar notificações quando uma instância de fluxo de trabalho for interrompida devido a um erro irrecuperável.</span><span class="sxs-lookup"><span data-stu-id="2e44b-176">**Unrecoverable** – Send notifications when a workflow instance is stopped because of an unrecoverable error.</span></span>
    - <span data-ttu-id="2e44b-177">**Encerrado** – Enviar notificações quando uma instância de fluxo de trabalho for encerrada.</span><span class="sxs-lookup"><span data-stu-id="2e44b-177">**Terminated** – Send notifications when a workflow instance is terminated.</span></span>

3. <span data-ttu-id="2e44b-178">Selecione a linha de um evento que você selecionou na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="2e44b-178">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="2e44b-179">Na guia **Texto da notificação**, insira o texto da notificação.</span><span class="sxs-lookup"><span data-stu-id="2e44b-179">On the **Notification text** tab, enter the text of the notification.</span></span>
5. <span data-ttu-id="2e44b-180">Para personalizar o texto, você poderá inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="2e44b-180">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="2e44b-181">Esses espaços reservados são substituídos pelos dados adequados quando o texto é exibido para os usuários.</span><span class="sxs-lookup"><span data-stu-id="2e44b-181">Placeholders are replaced with the appropriate data when the text is shown to users.</span></span> <span data-ttu-id="2e44b-182">Para inserir um espaço reservado, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2e44b-182">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="2e44b-183">Clique no campo para especificar onde o espaço reservado deve aparecer.</span><span class="sxs-lookup"><span data-stu-id="2e44b-183">Click in the field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="2e44b-184">Clique em **Inserir espaço reservado**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-184">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="2e44b-185">Na lista exibida, selecione o espaço reservado a ser inserido.</span><span class="sxs-lookup"><span data-stu-id="2e44b-185">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="2e44b-186">Clique em **Inserir**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-186">Click **Insert**.</span></span>
    5. <span data-ttu-id="2e44b-187">Um espaço reservado comum de **Texto de notificação** a ser incluído é "Last Notes: %Workflow.Last note%", que exibe os comentários da etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="2e44b-187">A common **Notification text** placeholder to include is "Last Notes: %Workflow.Last note%", which displays any comments from the previous step.</span></span>

6. <span data-ttu-id="2e44b-188">Para adicionar traduções do texto, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2e44b-188">To add translations of the text, follow these steps:</span></span>

    1. <span data-ttu-id="2e44b-189">Clique em **Traduções**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-189">Click **Translations**.</span></span>
    2. <span data-ttu-id="2e44b-190">Na página exibida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-190">On the page that appears, Click **Add**.</span></span>
    3. <span data-ttu-id="2e44b-191">Na lista exibida, selecione o idioma do texto que você inserirá.</span><span class="sxs-lookup"><span data-stu-id="2e44b-191">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="2e44b-192">No campo **Texto traduzido**, insira o texto.</span><span class="sxs-lookup"><span data-stu-id="2e44b-192">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="2e44b-193">Para personalizar o texto, você poderá inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="2e44b-193">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="2e44b-194">Para obter instruções sobre como inserir um espaço reservado, consulte a etapa 5.</span><span class="sxs-lookup"><span data-stu-id="2e44b-194">For instructions about how to enter a placeholder, see step 5.</span></span>
    6. <span data-ttu-id="2e44b-195">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-195">Click **Close**.</span></span>

7. <span data-ttu-id="2e44b-196">Na guia **Destinatário**, use as seguintes opções para especificar quem deverá receber as notificações.</span><span class="sxs-lookup"><span data-stu-id="2e44b-196">On the **Recipient** tab, use the following options to specify who should receive the notifications.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="2e44b-197">Opção</span><span class="sxs-lookup"><span data-stu-id="2e44b-197">Option</span></span></th>
    <th><span data-ttu-id="2e44b-198">As notificações são enviadas a esses usuários</span><span class="sxs-lookup"><span data-stu-id="2e44b-198">Notifications are sent to these users</span></span></th>
    <th><span data-ttu-id="2e44b-199">Para enviar notificações, siga estas etapas</span><span class="sxs-lookup"><span data-stu-id="2e44b-199">To send notifications, follow these steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="2e44b-200">Participante</span><span class="sxs-lookup"><span data-stu-id="2e44b-200">Participant</span></span></td>
    <td><span data-ttu-id="2e44b-201">Usuários que foram atribuídos a uma função ou um grupo específico</span><span class="sxs-lookup"><span data-stu-id="2e44b-201">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="2e44b-202">Na guia <strong>Destinatário</strong>, clique em <strong>Participante</strong>.</span><span class="sxs-lookup"><span data-stu-id="2e44b-202">On the <strong>Recipient</strong> tab, click <strong>Participant</strong>.</span></span></li>
    <li><span data-ttu-id="2e44b-203">Na guia <strong>Baseado em função</strong>, na lista <strong>Tipo de participante</strong>, selecione o tipo de grupo ou de função ao qual serão enviadas notificações.</span><span class="sxs-lookup"><span data-stu-id="2e44b-203">On the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="2e44b-204">Na lista <strong>Participante</strong>, selecione o grupo ou a função ao qual serão enviadas notificações.</span><span class="sxs-lookup"><span data-stu-id="2e44b-204">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="2e44b-205">Usuário de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="2e44b-205">Workflow user</span></span></td>
    <td><span data-ttu-id="2e44b-206">Usuários participantes desse fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="2e44b-206">Users who are participants in this workflow</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="2e44b-207">Na guia <strong>Destinatário</strong>, clique em <strong>Usuário de fluxo de trabalho</strong>.</span><span class="sxs-lookup"><span data-stu-id="2e44b-207">On the <strong>Recipient</strong> tab, click <strong>Workflow user</strong>.</span></span></li>
    <li><span data-ttu-id="2e44b-208">Na guia <strong>Usuário de fluxo de trabalho</strong>, na lista <strong>Usuário de fluxo de trabalho</strong>, selecione um participante desse fluxo.</span><span class="sxs-lookup"><span data-stu-id="2e44b-208">On the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a participant in this workflow.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="2e44b-209">Usuário</span><span class="sxs-lookup"><span data-stu-id="2e44b-209">User</span></span></td>
    <td><span data-ttu-id="2e44b-210">Usuários específicos do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2e44b-210">Specific Finance and Operations users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="2e44b-211">Na guia <strong>Destinatário</strong>, clique em <strong>Usuário</strong>.</span><span class="sxs-lookup"><span data-stu-id="2e44b-211">On the <strong>Recipient</strong> tab, click <strong>User</strong>.</span></span></li>
    <li><span data-ttu-id="2e44b-212">Na guia <strong>Usuário</strong>, a lista <strong>Usuários disponíveis</strong> inclui todos os usuários do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2e44b-212">On the <strong>User</strong> tab, the <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="2e44b-213">Selecione os usuários aos quais enviar notificações e mova- os para a lista <strong>Usuários selecionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="2e44b-213">Select the users to send notifications to, and move those users into the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="2e44b-214">Repita as etapas de 3 a 7 para cada evento selecionado na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="2e44b-214">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a><span data-ttu-id="2e44b-215">Insira comentários sobre as alterações feitas no fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="2e44b-215">Enter comments about the changes that you made to the workflow</span></span>

<span data-ttu-id="2e44b-216">Para inserir comentários sobre as alterações feitas no fluxo de trabalho, siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="2e44b-216">To enter comments about the changes that you made to the workflow, follow these steps.</span></span>

1. <span data-ttu-id="2e44b-217">No painel esquerdo, clique em **Observações**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-217">In the left pane, click **Notes**.</span></span>
2. <span data-ttu-id="2e44b-218">No campo **Inserir comentários sobre o fluxo de trabalho**, insira seus comentários.</span><span class="sxs-lookup"><span data-stu-id="2e44b-218">In the **Enter comments about the workflow** field, enter your comments.</span></span>
3. <span data-ttu-id="2e44b-219">Revise seus comentários.</span><span class="sxs-lookup"><span data-stu-id="2e44b-219">Review your comments.</span></span> <span data-ttu-id="2e44b-220">Depois que você adicionar comentários, não poderá modificá-los.</span><span class="sxs-lookup"><span data-stu-id="2e44b-220">After you add comments, you can't modify them.</span></span>
4. <span data-ttu-id="2e44b-221">Clique em **Adicionar** para adicionar comentários à área **Histórico de comentários**.</span><span class="sxs-lookup"><span data-stu-id="2e44b-221">Click **Add** to add your comments to the **Comment history** area.</span></span>
