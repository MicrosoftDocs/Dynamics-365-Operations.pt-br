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
ms.openlocfilehash: 76d44c472989a73d71c2edd19f1187ecd09827ae
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190111"
---
# <a name="configure-workflow-properties"></a><span data-ttu-id="b280d-103">Configurar propriedades do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="b280d-103">Configure workflow properties</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b280d-104">Este tópico explica como configurar as várias propriedades de um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b280d-104">This topic explains how to configure the various properties of a workflow.</span></span>

<span data-ttu-id="b280d-105">Para configurar as propriedades de um fluxo de trabalho, abra o fluxo de trabalho no editor.</span><span class="sxs-lookup"><span data-stu-id="b280d-105">To configure the properties of a workflow, open the workflow in the workflow editor.</span></span> <span data-ttu-id="b280d-106">Clique na tela do editor de fluxo de trabalho e clique em **Propriedades** para abrir a página **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b280d-106">Click the canvas of the workflow editor, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="b280d-107">Em seguida, use os procedimentos a seguir para configurar as várias propriedades do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b280d-107">You can then use the following procedures to configure the various properties of the workflow.</span></span>

## <a name="name-the-workflow"></a><span data-ttu-id="b280d-108">Nomear o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="b280d-108">Name the workflow</span></span>

<span data-ttu-id="b280d-109">Siga as etapas abaixo para inserir um nome para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b280d-109">Follow these steps to enter a name for the workflow.</span></span>

1. <span data-ttu-id="b280d-110">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="b280d-110">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="b280d-111">No campo **Nome**, insira um nome exclusivo para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b280d-111">In the **Name** field, enter a unique name for the workflow.</span></span> <span data-ttu-id="b280d-112">Por exemplo, se você criar um fluxo de trabalho de requisição de compra para cada país/região onde opera, poderá nomear um fluxo de trabalho como **Requisições de Compra - Dinamarca** ou **Requisições de Compra - Espanha**.</span><span class="sxs-lookup"><span data-stu-id="b280d-112">For example, if you create a purchase requisition workflow for each country/region that you operate in, you can name the purchase requisition workflow **Purchase Requisitions Denmark** or **Purchase Requisitions Spain**.</span></span>

## <a name="specify-the-workflow-owner"></a><span data-ttu-id="b280d-113">Especificar o proprietário do fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="b280d-113">Specify the workflow owner</span></span>

<span data-ttu-id="b280d-114">O proprietário do fluxo de trabalho é a pessoa que gerencia e mantém o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b280d-114">The workflow owner is the person who manages and maintains the workflow.</span></span> <span data-ttu-id="b280d-115">Siga estas etapas para especificar o proprietário do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b280d-115">Follow these steps to specify the workflow owner.</span></span>

1. <span data-ttu-id="b280d-116">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="b280d-116">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="b280d-117">Na lista **Proprietário**, selecione o nome da pessoa que gerenciará o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b280d-117">In the **Owner** list, select the name of the person who will manage the workflow.</span></span>

## <a name="select-an-email-template"></a><span data-ttu-id="b280d-118">Selecionar um modelo de email</span><span class="sxs-lookup"><span data-stu-id="b280d-118">Select an email template</span></span>

<span data-ttu-id="b280d-119">Siga estas etapas para selecionar o modelo de email que será usado para gerar mensagens de notificação sobre o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b280d-119">Follow these steps to select the email template that is used to generate notification messages about the workflow.</span></span>

1. <span data-ttu-id="b280d-120">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="b280d-120">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="b280d-121">Na lista **Modelo de email para notificações de fluxo de trabalho**, selecione o modelo.</span><span class="sxs-lookup"><span data-stu-id="b280d-121">In the **Email template for workflow notifications** list, select the template.</span></span>

## <a name="enter-instructions-for-users"></a><span data-ttu-id="b280d-122">Inserir instruções para os usuários</span><span class="sxs-lookup"><span data-stu-id="b280d-122">Enter instructions for users</span></span>

<span data-ttu-id="b280d-123">Você pode fornecer instruções aos usuários que enviarão documentos para processamento e aprovação.</span><span class="sxs-lookup"><span data-stu-id="b280d-123">You can provide instructions to users who submit documents for processing and approval.</span></span> <span data-ttu-id="b280d-124">Esses usuários também são conhecidos como *originadores*.</span><span class="sxs-lookup"><span data-stu-id="b280d-124">These users are also referred to as *originators*.</span></span> <span data-ttu-id="b280d-125">Por exemplo, suponha que você esteja criando um fluxo de trabalho de requisição de compra e insira instruções.</span><span class="sxs-lookup"><span data-stu-id="b280d-125">For example, you're creating a purchase requisition workflow, and you enter instructions.</span></span> <span data-ttu-id="b280d-126">Essas instruções fornecidas poderão ser exibidas pelos usuários que inserirem requisições de compra na página **Requisições de compra**.</span><span class="sxs-lookup"><span data-stu-id="b280d-126">Those instructions can then be viewed by users who enter purchase requisitions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="b280d-127">Para exibir instruções, o originador clica no ícone na barra de mensagens de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b280d-127">To view instructions, the originator clicks the icon in the workflow message bar.</span></span> <span data-ttu-id="b280d-128">Siga estas etapas para inserir instruções para os usuários.</span><span class="sxs-lookup"><span data-stu-id="b280d-128">Follow these steps to enter instructions for users.</span></span>

1. <span data-ttu-id="b280d-129">No painel esquerdo, clique em **Configurações Básicas**.</span><span class="sxs-lookup"><span data-stu-id="b280d-129">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="b280d-130">No campo **Enviar instruções**, insira as instruções.</span><span class="sxs-lookup"><span data-stu-id="b280d-130">In the **Submission instructions** field, enter the instructions.</span></span>
3. <span data-ttu-id="b280d-131">Para personalizar as instruções, você pode inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="b280d-131">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="b280d-132">Os espaços reservados são substituídos pelos dados adequados quando as instruções são exibidas para os usuários.</span><span class="sxs-lookup"><span data-stu-id="b280d-132">Placeholders are replaced with the appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="b280d-133">Para inserir um espaço reservado, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b280d-133">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="b280d-134">Clique no campo **Instruções de envio** para especificar onde o espaço reservado deve aparecer.</span><span class="sxs-lookup"><span data-stu-id="b280d-134">Click in the **Submission instructions** field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="b280d-135">Clique em **Inserir espaço reservado**.</span><span class="sxs-lookup"><span data-stu-id="b280d-135">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="b280d-136">Na lista exibida, selecione o espaço reservado a ser inserido.</span><span class="sxs-lookup"><span data-stu-id="b280d-136">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="b280d-137">Clique em **Inserir**.</span><span class="sxs-lookup"><span data-stu-id="b280d-137">Click **Insert**.</span></span>

4. <span data-ttu-id="b280d-138">Para adicionar traduções das instruções, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b280d-138">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="b280d-139">Clique em **Traduções**.</span><span class="sxs-lookup"><span data-stu-id="b280d-139">Click **Translations**.</span></span>
    2. <span data-ttu-id="b280d-140">Na página exibida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b280d-140">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="b280d-141">Na lista exibida, selecione o idioma do texto que você inserirá.</span><span class="sxs-lookup"><span data-stu-id="b280d-141">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="b280d-142">No campo **Texto traduzido**, insira o texto.</span><span class="sxs-lookup"><span data-stu-id="b280d-142">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="b280d-143">Para personalizar o texto, você poderá inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="b280d-143">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="b280d-144">Para obter instruções sobre como inserir um espaço reservado, consulte a etapa 3.</span><span class="sxs-lookup"><span data-stu-id="b280d-144">For instructions about how to enter a placeholder, see step 3.</span></span>
    6. <span data-ttu-id="b280d-145">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b280d-145">Click **Close**.</span></span>

## <a name="specify-when-this-workflow-is-used"></a><span data-ttu-id="b280d-146">Especificar quando esse fluxo de trabalho será usado</span><span class="sxs-lookup"><span data-stu-id="b280d-146">Specify when this workflow is used</span></span>

<span data-ttu-id="b280d-147">Você pode criar vários fluxos de trabalho baseados no mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="b280d-147">You can create multiple workflows that are based on the same type.</span></span> <span data-ttu-id="b280d-148">Por exemplo, você pode criar um fluxo de trabalho de requisição de compra para cada país/região onde opera, como Requisições de Compra - Dinamarca e Requisições de Compra - Espanha.</span><span class="sxs-lookup"><span data-stu-id="b280d-148">For example, you can create a purchase requisition workflow for each country/region that you operate in, such as Purchase Requisitions Denmark and Purchase Requisitions Spain.</span></span> <span data-ttu-id="b280d-149">Se houver vários fluxos de trabalho baseados no mesmo tipo, será necessário especificar quando cada um deles será usado.</span><span class="sxs-lookup"><span data-stu-id="b280d-149">When you have multiple workflows that are based on the same type, you must specify when each workflow is used.</span></span> <span data-ttu-id="b280d-150">No exemplo anterior, especifique as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="b280d-150">For the preceding example, you specify the following conditions:</span></span>

- <span data-ttu-id="b280d-151">As Requisições de Compra - Dinamarca são usadas quando: país/região = DK</span><span class="sxs-lookup"><span data-stu-id="b280d-151">Purchase Requisitions Denmark is used when: country/region = DK</span></span>
- <span data-ttu-id="b280d-152">As Requisições de Compra - Espanha são usadas quando: país/região = DK</span><span class="sxs-lookup"><span data-stu-id="b280d-152">Purchase Requisitions Spain is used when: country/region = ES</span></span>

<span data-ttu-id="b280d-153">Siga estas etapas para especificar quando o fluxo de trabalho que você está configurando será usado.</span><span class="sxs-lookup"><span data-stu-id="b280d-153">Follow these steps to specify when the workflow that you're configuring is used.</span></span>

1. <span data-ttu-id="b280d-154">No painel esquerdo, clique em **Ativação**.</span><span class="sxs-lookup"><span data-stu-id="b280d-154">In the left pane, click **Activation**.</span></span>
2. <span data-ttu-id="b280d-155">Marque a caixa de seleção **Definir as condições para executar este fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="b280d-155">Select the **Set the conditions for running this workflow** check box.</span></span>
3. <span data-ttu-id="b280d-156">Clique em **Adicionar condição**.</span><span class="sxs-lookup"><span data-stu-id="b280d-156">Click **Add condition**.</span></span>
4. <span data-ttu-id="b280d-157">Insira uma condição.</span><span class="sxs-lookup"><span data-stu-id="b280d-157">Enter a condition.</span></span>
5. <span data-ttu-id="b280d-158">Insira quaisquer condições adicionais necessárias.</span><span class="sxs-lookup"><span data-stu-id="b280d-158">Enter any additional conditions that are required.</span></span>
6. <span data-ttu-id="b280d-159">Para verificar se as condições inseridas foram definidas corretamente, execute estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b280d-159">To verify that the conditions that you entered are set correctly, follow these steps:</span></span>

    1. <span data-ttu-id="b280d-160">Clique em **Teste**.</span><span class="sxs-lookup"><span data-stu-id="b280d-160">Click **Test**.</span></span>
    2. <span data-ttu-id="b280d-161">Na página **Testar condição de fluxo de trabalho**, na área **Validar condição**, selecione um registro.</span><span class="sxs-lookup"><span data-stu-id="b280d-161">On the **Test workflow condition** page, in the **Validate condition** area, select a record.</span></span>
    3. <span data-ttu-id="b280d-162">Clique em **Teste**.</span><span class="sxs-lookup"><span data-stu-id="b280d-162">Click **Test**.</span></span> <span data-ttu-id="b280d-163">O sistema avaliará o registro para determinar se ele atende às condições especificadas.</span><span class="sxs-lookup"><span data-stu-id="b280d-163">The system evaluates the record to determine whether it meets the conditions that you specified.</span></span> <span data-ttu-id="b280d-164">Por exemplo, se você estiver criando um fluxo de trabalho de requisição de compra para a Espanha, a área **Validar condição** da página exibirá uma lista de requisições de compra.</span><span class="sxs-lookup"><span data-stu-id="b280d-164">For example, if you're creating a purchase requisition workflow for Spain, the **Validate condition** area of the page shows a list of purchase requisitions.</span></span> <span data-ttu-id="b280d-165">Quando você clicar em **Testar**, o sistema avaliará a requisição de compra selecionada para determinar se o país/região é ES.</span><span class="sxs-lookup"><span data-stu-id="b280d-165">When you click **Test**, the system evaluates the selected purchase requisition to determine whether the country/region is ES.</span></span>
    4. <span data-ttu-id="b280d-166">Clique em **OK** ou **Cancelar** para retornar à página **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b280d-166">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="b280d-167">Especificar quando enviar notificações</span><span class="sxs-lookup"><span data-stu-id="b280d-167">Specify when notifications are sent</span></span>

<span data-ttu-id="b280d-168">Quando um documento é enviado para processamento, é criada uma instância do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b280d-168">When a document is submitted for processing, a workflow instance is created.</span></span> <span data-ttu-id="b280d-169">Você poderá enviar notificações para os usuários quando instâncias baseadas nesse fluxo de trabalho forem iniciadas, concluídas, encerradas ou interrompidas devido a um erro.</span><span class="sxs-lookup"><span data-stu-id="b280d-169">You can send notifications to users when workflow instances that are based on the workflow are started, completed, terminated, or stopped because of an error.</span></span> <span data-ttu-id="b280d-170">Siga estas etapas para especificar quando as notificações serão enviadas.</span><span class="sxs-lookup"><span data-stu-id="b280d-170">Follow these steps to specify when notifications are sent.</span></span>

1. <span data-ttu-id="b280d-171">No painel esquerdo, clique em **Notificações**.</span><span class="sxs-lookup"><span data-stu-id="b280d-171">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="b280d-172">Marque a caixa de seleção para cada evento que disparará notificações:</span><span class="sxs-lookup"><span data-stu-id="b280d-172">Select the check box for each event that should trigger notifications:</span></span>

    - <span data-ttu-id="b280d-173">**Iniciado**– Enviar notificações quando uma instância de fluxo de trabalho for iniciada.</span><span class="sxs-lookup"><span data-stu-id="b280d-173">**Started** – Send notifications when a workflow instance is started.</span></span>
    - <span data-ttu-id="b280d-174">**Parado** – Enviar notificações quando uma instância de fluxo de trabalho for interrompida devido a um erro.</span><span class="sxs-lookup"><span data-stu-id="b280d-174">**Stopped** – Send notifications when a workflow instance is stopped because of an error.</span></span>
    - <span data-ttu-id="b280d-175">**Concluído** – Enviar notificações quando uma instância de fluxo de trabalho for concluída.</span><span class="sxs-lookup"><span data-stu-id="b280d-175">**Completed** – Send notifications when a workflow instance is completed.</span></span>
    - <span data-ttu-id="b280d-176">**Irrecuperável** – Enviar notificações quando uma instância de fluxo de trabalho for interrompida devido a um erro irrecuperável.</span><span class="sxs-lookup"><span data-stu-id="b280d-176">**Unrecoverable** – Send notifications when a workflow instance is stopped because of an unrecoverable error.</span></span>
    - <span data-ttu-id="b280d-177">**Encerrado** – Enviar notificações quando uma instância de fluxo de trabalho for encerrada.</span><span class="sxs-lookup"><span data-stu-id="b280d-177">**Terminated** – Send notifications when a workflow instance is terminated.</span></span>

3. <span data-ttu-id="b280d-178">Selecione a linha de um evento que você selecionou na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="b280d-178">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="b280d-179">Na guia **Texto da notificação**, insira o texto da notificação.</span><span class="sxs-lookup"><span data-stu-id="b280d-179">On the **Notification text** tab, enter the text of the notification.</span></span>
5. <span data-ttu-id="b280d-180">Para personalizar o texto, você poderá inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="b280d-180">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="b280d-181">Esses espaços reservados são substituídos pelos dados adequados quando o texto é exibido para os usuários.</span><span class="sxs-lookup"><span data-stu-id="b280d-181">Placeholders are replaced with the appropriate data when the text is shown to users.</span></span> <span data-ttu-id="b280d-182">Para inserir um espaço reservado, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b280d-182">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="b280d-183">Clique no campo para especificar onde o espaço reservado deve aparecer.</span><span class="sxs-lookup"><span data-stu-id="b280d-183">Click in the field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="b280d-184">Clique em **Inserir espaço reservado**.</span><span class="sxs-lookup"><span data-stu-id="b280d-184">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="b280d-185">Na lista exibida, selecione o espaço reservado a ser inserido.</span><span class="sxs-lookup"><span data-stu-id="b280d-185">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="b280d-186">Clique em **Inserir**.</span><span class="sxs-lookup"><span data-stu-id="b280d-186">Click **Insert**.</span></span>
    5. <span data-ttu-id="b280d-187">Um espaço reservado comum de **Texto de notificação** a ser incluído é "Last Notes: %Workflow.Last note%", que exibe os comentários da etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="b280d-187">A common **Notification text** placeholder to include is "Last Notes: %Workflow.Last note%", which displays any comments from the previous step.</span></span>

6. <span data-ttu-id="b280d-188">Para adicionar traduções do texto, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b280d-188">To add translations of the text, follow these steps:</span></span>

    1. <span data-ttu-id="b280d-189">Clique em **Traduções**.</span><span class="sxs-lookup"><span data-stu-id="b280d-189">Click **Translations**.</span></span>
    2. <span data-ttu-id="b280d-190">Na página exibida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b280d-190">On the page that appears, Click **Add**.</span></span>
    3. <span data-ttu-id="b280d-191">Na lista exibida, selecione o idioma do texto que você inserirá.</span><span class="sxs-lookup"><span data-stu-id="b280d-191">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="b280d-192">No campo **Texto traduzido**, insira o texto.</span><span class="sxs-lookup"><span data-stu-id="b280d-192">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="b280d-193">Para personalizar o texto, você poderá inserir espaços reservados.</span><span class="sxs-lookup"><span data-stu-id="b280d-193">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="b280d-194">Para obter instruções sobre como inserir um espaço reservado, consulte a etapa 5.</span><span class="sxs-lookup"><span data-stu-id="b280d-194">For instructions about how to enter a placeholder, see step 5.</span></span>
    6. <span data-ttu-id="b280d-195">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b280d-195">Click **Close**.</span></span>

7. <span data-ttu-id="b280d-196">Na guia **Destinatário**, use as seguintes opções para especificar quem deverá receber as notificações.</span><span class="sxs-lookup"><span data-stu-id="b280d-196">On the **Recipient** tab, use the following options to specify who should receive the notifications.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="b280d-197">Opção</span><span class="sxs-lookup"><span data-stu-id="b280d-197">Option</span></span></th>
    <th><span data-ttu-id="b280d-198">As notificações são enviadas a esses usuários</span><span class="sxs-lookup"><span data-stu-id="b280d-198">Notifications are sent to these users</span></span></th>
    <th><span data-ttu-id="b280d-199">Para enviar notificações, siga estas etapas</span><span class="sxs-lookup"><span data-stu-id="b280d-199">To send notifications, follow these steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="b280d-200">Participante</span><span class="sxs-lookup"><span data-stu-id="b280d-200">Participant</span></span></td>
    <td><span data-ttu-id="b280d-201">Usuários que foram atribuídos a uma função ou um grupo específico</span><span class="sxs-lookup"><span data-stu-id="b280d-201">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="b280d-202">Na guia <strong>Destinatário</strong>, clique em <strong>Participante</strong>.</span><span class="sxs-lookup"><span data-stu-id="b280d-202">On the <strong>Recipient</strong> tab, click <strong>Participant</strong>.</span></span></li>
    <li><span data-ttu-id="b280d-203">Na guia <strong>Baseado em função</strong>, na lista <strong>Tipo de participante</strong>, selecione o tipo de grupo ou de função ao qual serão enviadas notificações.</span><span class="sxs-lookup"><span data-stu-id="b280d-203">On the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="b280d-204">Na lista <strong>Participante</strong>, selecione o grupo ou a função ao qual serão enviadas notificações.</span><span class="sxs-lookup"><span data-stu-id="b280d-204">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="b280d-205">Usuário de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="b280d-205">Workflow user</span></span></td>
    <td><span data-ttu-id="b280d-206">Usuários participantes desse fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="b280d-206">Users who are participants in this workflow</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="b280d-207">Na guia <strong>Destinatário</strong>, clique em <strong>Usuário de fluxo de trabalho</strong>.</span><span class="sxs-lookup"><span data-stu-id="b280d-207">On the <strong>Recipient</strong> tab, click <strong>Workflow user</strong>.</span></span></li>
    <li><span data-ttu-id="b280d-208">Na guia <strong>Usuário de fluxo de trabalho</strong>, na lista <strong>Usuário de fluxo de trabalho</strong>, selecione um participante desse fluxo.</span><span class="sxs-lookup"><span data-stu-id="b280d-208">On the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a participant in this workflow.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="b280d-209">Usuário</span><span class="sxs-lookup"><span data-stu-id="b280d-209">User</span></span></td>
    <td><span data-ttu-id="b280d-210">Usuários específicos</span><span class="sxs-lookup"><span data-stu-id="b280d-210">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="b280d-211">Na guia <strong>Destinatário</strong>, clique em <strong>Usuário</strong>.</span><span class="sxs-lookup"><span data-stu-id="b280d-211">On the <strong>Recipient</strong> tab, click <strong>User</strong>.</span></span></li>
    <li><span data-ttu-id="b280d-212">Na guia <strong>Usuário</strong>, a lista <strong>Usuários disponíveis</strong> inclui todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="b280d-212">On the <strong>User</strong> tab, the <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="b280d-213">Selecione os usuários aos quais enviar notificações e mova- os para a lista <strong>Usuários selecionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="b280d-213">Select the users to send notifications to, and move those users into the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="b280d-214">Repita as etapas de 3 a 7 para cada evento selecionado na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="b280d-214">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a><span data-ttu-id="b280d-215">Insira comentários sobre as alterações feitas no fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="b280d-215">Enter comments about the changes that you made to the workflow</span></span>

<span data-ttu-id="b280d-216">Para inserir comentários sobre as alterações feitas no fluxo de trabalho, siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="b280d-216">To enter comments about the changes that you made to the workflow, follow these steps.</span></span>

1. <span data-ttu-id="b280d-217">No painel esquerdo, clique em **Observações**.</span><span class="sxs-lookup"><span data-stu-id="b280d-217">In the left pane, click **Notes**.</span></span>
2. <span data-ttu-id="b280d-218">No campo **Inserir comentários sobre o fluxo de trabalho**, insira seus comentários.</span><span class="sxs-lookup"><span data-stu-id="b280d-218">In the **Enter comments about the workflow** field, enter your comments.</span></span>
3. <span data-ttu-id="b280d-219">Revise seus comentários.</span><span class="sxs-lookup"><span data-stu-id="b280d-219">Review your comments.</span></span> <span data-ttu-id="b280d-220">Depois que você adicionar comentários, não poderá modificá-los.</span><span class="sxs-lookup"><span data-stu-id="b280d-220">After you add comments, you can't modify them.</span></span>
4. <span data-ttu-id="b280d-221">Clique em **Adicionar** para adicionar comentários à área **Histórico de comentários**.</span><span class="sxs-lookup"><span data-stu-id="b280d-221">Click **Add** to add your comments to the **Comment history** area.</span></span>
