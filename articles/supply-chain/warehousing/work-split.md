---
title: Divisão do trabalho
description: Este tópico fornece informações sobre a funcionalidade de divisão do trabalho. Essa funcionalidade permite dividir grandes ordens de serviço em várias ordens de serviço menores que você pode atribuir a vários funcionários do depósito. Dessa forma, o mesmo trabalho pode ser separado simultaneamente por vários funcionários do depósito.
author: mirzaab
manager: tfehr
ms.date: 10/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: WHSWorkTableListPage
ms.author: mirzaab
ms.search.validFrom: 2020-10-15
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: e74b630e72d70829938f0f34efd624509b1ba7c3
ms.sourcegitcommit: 531be324bf706ca727d777720df899d6ddd3c2d7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "4422657"
---
# <a name="work-split"></a><span data-ttu-id="fa443-105">Divisão do trabalho</span><span class="sxs-lookup"><span data-stu-id="fa443-105">Work split</span></span>

<span data-ttu-id="fa443-106">A funcionalidade de divisão do trabalho permite dividir grandes IDs de trabalho (ou seja, ordens de serviço que têm várias linhas) em várias IDs de trabalho menores que você pode atribuir a vários funcionários do depósito.</span><span class="sxs-lookup"><span data-stu-id="fa443-106">Work split functionality lets you split large work IDs (that is, work orders that have several lines) into several smaller work IDs that you can then assign to multiple warehouse workers.</span></span> <span data-ttu-id="fa443-107">Dessa forma, o mesmo número de criação de trabalho pode ser selecionado simultaneamente por vários funcionários do depósito.</span><span class="sxs-lookup"><span data-stu-id="fa443-107">In this way, the same work creation number can be picked simultaneously by several warehouse workers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa443-108">Você pode dividir apenas as ordens de serviço que têm um status de *Aberto* ou *Em andamento*.</span><span class="sxs-lookup"><span data-stu-id="fa443-108">You can split only work orders that have a status of *Open* or *In-progress*.</span></span>

## <a name="turn-on-the-work-split-functionality"></a><span data-ttu-id="fa443-109">Ativar a funcionalidade de divisão do trabalho</span><span class="sxs-lookup"><span data-stu-id="fa443-109">Turn on the work split functionality</span></span>

<span data-ttu-id="fa443-110">Antes de usar a funcionalidade de divisão do trabalho, você deve ativar o recurso e seu recurso de pré-requisito em seu sistema.</span><span class="sxs-lookup"><span data-stu-id="fa443-110">Before you can use the work split functionality, you must turn on the feature and its prerequisite feature in your system.</span></span> <span data-ttu-id="fa443-111">Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status dos recursos e ativá-los se necessário.</span><span class="sxs-lookup"><span data-stu-id="fa443-111">Administrators can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the features and turn them on as required.</span></span>

<span data-ttu-id="fa443-112">Primeiro, ative o recurso de pré-requisito *Bloqueio de trabalho em toda a organização* se ainda não estiver ativado.</span><span class="sxs-lookup"><span data-stu-id="fa443-112">First, turn on the prerequisite *Organization-wide work blocking* feature if it isn't already turned on.</span></span> <span data-ttu-id="fa443-113">No espaço de trabalho **Gerenciamento de recursos**, este recurso está listado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="fa443-113">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="fa443-114">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="fa443-114">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="fa443-115">**Nome do recurso:** *Bloqueio de trabalho em toda a organização*</span><span class="sxs-lookup"><span data-stu-id="fa443-115">**Feature name:** *Organization-wide work blocking*</span></span>

> [!NOTE]
> <span data-ttu-id="fa443-116">Quando esse recurso é ativado, uma atualização de dados é aplicada automaticamente depois que o recurso é ativado em todas as entidades legais.</span><span class="sxs-lookup"><span data-stu-id="fa443-116">When this feature is activated, a data upgrade is automatically applied after the feature is turned on across all legal entities.</span></span>

<span data-ttu-id="fa443-117">Em seguida, ative o recurso *Divisão do trabalho*, que está listado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="fa443-117">Next, turn on the *Work split* feature, which is listed in the following way:</span></span>

- <span data-ttu-id="fa443-118">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="fa443-118">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="fa443-119">**Nome do recurso:** *Divisão do trabalho*</span><span class="sxs-lookup"><span data-stu-id="fa443-119">**Feature name:** *Work split*</span></span>

## <a name="enhancements-to-the-work-details-and-all-work-pages"></a><span data-ttu-id="fa443-120">Aprimoramentos dos detalhes de trabalho e todas as páginas de trabalho</span><span class="sxs-lookup"><span data-stu-id="fa443-120">Enhancements to the Work details and All work pages</span></span>

<span data-ttu-id="fa443-121">O recurso *Divisão do trabalho* adiciona os dois botões a seguir à guia **Trabalho** no Painel de ações das páginas **Detalhes do trabalho** e **Todos os trabalhos**:</span><span class="sxs-lookup"><span data-stu-id="fa443-121">The *Work split* feature adds the following two buttons to the **Work** tab on the Action Pane of the **Work details** and **All work** pages:</span></span>

- <span data-ttu-id="fa443-122">**Divisão do trabalho** – Divida a ID de trabalho atual em várias IDs menores do trabalho que podem ser processadas por funcionários separados.</span><span class="sxs-lookup"><span data-stu-id="fa443-122">**Split work** – Split the current work ID into multiple smaller work IDs that can be processed by separate workers.</span></span>
- <span data-ttu-id="fa443-123">**Cancelar sessão de divisão do trabalho** – Cancele a sessão de divisão do trabalho e disponibilize o trabalho para processamento.</span><span class="sxs-lookup"><span data-stu-id="fa443-123">**Cancel work split session** – Cancel the work split session, and make the work available for processing.</span></span>

<span data-ttu-id="fa443-124">![Botões Divisão do trabalho e Cancelar sessão de divisão do trabalho](media/Work_split_buttons.png "Botões Divisão do trabalho e Cancelar sessão de divisão do trabalho")</span><span class="sxs-lookup"><span data-stu-id="fa443-124">![Split work and Cancel work split session buttons](media/Work_split_buttons.png "Split work and Cancel work split session buttons")</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa443-125">O botão **Divisão do trabalho** não estará disponível se qualquer uma das seguintes condições for atendida:</span><span class="sxs-lookup"><span data-stu-id="fa443-125">The **Split work** button won't be available if any of the following conditions are met:</span></span>
>
> - <span data-ttu-id="fa443-126">O status do trabalho é diferente de *Aberto* ou *Em andamento*.</span><span class="sxs-lookup"><span data-stu-id="fa443-126">The work status is something other than *Open* or *In progress*.</span></span>
> - <span data-ttu-id="fa443-127">Uma ID de contêiner está associada à ID de trabalho.</span><span class="sxs-lookup"><span data-stu-id="fa443-127">A container ID is associated with the work ID.</span></span> <span data-ttu-id="fa443-128">(Um contêiner não pode ser sistematicamente dividido, porque requer ações físicas.)</span><span class="sxs-lookup"><span data-stu-id="fa443-128">(A container can't be systematically split, because it requires physical actions.)</span></span>
> - <span data-ttu-id="fa443-129">O trabalho está associado a um cluster.</span><span class="sxs-lookup"><span data-stu-id="fa443-129">The work is associated with a cluster.</span></span>
> - <span data-ttu-id="fa443-130">O tipo de ordem de serviço é diferente de um dos seguintes tipos:</span><span class="sxs-lookup"><span data-stu-id="fa443-130">The work order type is something other than one of the following types:</span></span>
>
>    - <span data-ttu-id="fa443-131">Ordens de Venda</span><span class="sxs-lookup"><span data-stu-id="fa443-131">Sales orders</span></span>
>    - <span data-ttu-id="fa443-132">Separação de matéria-prima</span><span class="sxs-lookup"><span data-stu-id="fa443-132">Raw material picking</span></span>
>    - <span data-ttu-id="fa443-133">Transferir saída</span><span class="sxs-lookup"><span data-stu-id="fa443-133">Transfer issue</span></span>
>
> - <span data-ttu-id="fa443-134">O trabalho está sendo dividido por outro usuário.</span><span class="sxs-lookup"><span data-stu-id="fa443-134">The work is currently being split by another user.</span></span> <span data-ttu-id="fa443-135">Se você tentar abrir a página de divisão de um trabalho que já está sendo dividido por outro usuário, receberá a seguinte mensagem de erro: "O trabalho com ID \#\#\#\# está sendo dividido no momento.</span><span class="sxs-lookup"><span data-stu-id="fa443-135">If you try to open the splitting page for work that is already being split by another user, you receive the following error message: "The work with ID \#\#\#\# is currently being split.</span></span> <span data-ttu-id="fa443-136">Tente novamente em alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="fa443-136">Retry in a few minutes.</span></span> <span data-ttu-id="fa443-137">Se continuar a receber esta mensagem, entre em contato com um supervisor."</span><span class="sxs-lookup"><span data-stu-id="fa443-137">If you continue to receive this message, contact a supervisor."</span></span>

<span data-ttu-id="fa443-138">Um novo motivo de bloqueio do trabalho, *Divisão do trabalho*, indica quando a ID de trabalho está em processo de divisão.</span><span class="sxs-lookup"><span data-stu-id="fa443-138">A new work blocking reason, *Split work*, indicates when the work ID is in the process of being split.</span></span> <span data-ttu-id="fa443-139">É mostrado na página **Divisão do trabalho** e no aplicativo do depósito se um usuário tentar executar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="fa443-139">It's shown both on the **Split work** page and in the warehouse app if a user tries to run the work.</span></span> <span data-ttu-id="fa443-140">Quando motivos de bloqueio são usados, o nome do campo **Ciclo bloqueado** da ID de trabalho é alterado para **Bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="fa443-140">When blocking reasons are used, the name of the **Blocked wave** field from the work ID is changed to **Blocked**.</span></span>

## <a name="initiate-a-work-split"></a><span data-ttu-id="fa443-141">Iniciar uma divisão de trabalho</span><span class="sxs-lookup"><span data-stu-id="fa443-141">Initiate a work split</span></span>

<span data-ttu-id="fa443-142">O recurso adiciona uma nova página **Divisão do trabalho** que permite aos usuários dividir as linhas de trabalho a partir da ID de trabalho.</span><span class="sxs-lookup"><span data-stu-id="fa443-142">The feature adds a new **Split work** page that lets users split work lines from the work ID.</span></span> <span data-ttu-id="fa443-143">Quando a página é aberta pela primeira vez, mostra as linhas que têm um status de trabalho de *Aberto* e que estão disponíveis para serem divididas.</span><span class="sxs-lookup"><span data-stu-id="fa443-143">When the page is first opened, it shows lines that have a work status of *Open* and that are available to be split.</span></span> <span data-ttu-id="fa443-144">No Painel de ações, selecione **Divisão do trabalho** para processar o trabalho selecionado.</span><span class="sxs-lookup"><span data-stu-id="fa443-144">On the Action Pane, select **Split work** to process the selected work.</span></span>

<span data-ttu-id="fa443-145">Para dividir o trabalho, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="fa443-145">To split work, follow these steps.</span></span>

1. <span data-ttu-id="fa443-146">Abra uma das seguintes páginas de trabalho:</span><span class="sxs-lookup"><span data-stu-id="fa443-146">Open one of the following work pages:</span></span>

    - <span data-ttu-id="fa443-147">**Detalhes do trabalho** (**Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho**)</span><span class="sxs-lookup"><span data-stu-id="fa443-147">**Work details** (**Warehouse management \> Work \> Work details**)</span></span>
    - <span data-ttu-id="fa443-148">**Todos os trabalhos** (**Gerenciamento de depósito \> Trabalho \> Todos os trabalhos**)</span><span class="sxs-lookup"><span data-stu-id="fa443-148">**All work** (**Warehouse management \> Work \> All work**)</span></span>

1. <span data-ttu-id="fa443-149">Na grade, selecione uma ID de trabalho a ser dividida.</span><span class="sxs-lookup"><span data-stu-id="fa443-149">In the grid, select a work ID to split.</span></span> <span data-ttu-id="fa443-150">O campo **Tipo de ordem de serviço** deve ser definido com um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fa443-150">The **Work order type** field must be set to one of the following values:</span></span>

    - <span data-ttu-id="fa443-151">Ordens de Venda</span><span class="sxs-lookup"><span data-stu-id="fa443-151">Sales orders</span></span>
    - <span data-ttu-id="fa443-152">Separação de matéria-prima</span><span class="sxs-lookup"><span data-stu-id="fa443-152">Raw material picking</span></span>
    - <span data-ttu-id="fa443-153">Transferir saída</span><span class="sxs-lookup"><span data-stu-id="fa443-153">Transfer issue</span></span>

1. <span data-ttu-id="fa443-154">No Painel de Ação, na guia **Trabalho**, no grupo **Trabalho**, selecione **Divisão do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="fa443-154">On the Action Pane, on the **Work** tab, in the **Work** group, select **Split work**.</span></span>

    <span data-ttu-id="fa443-155">A página **Divisão do trabalho** aparece e mostra as linhas de trabalho que estão abertas e disponíveis para serem divididas.</span><span class="sxs-lookup"><span data-stu-id="fa443-155">The **Split work** page appears and shows the work lines that are open and available to be split.</span></span> <span data-ttu-id="fa443-156">Por padrão, apenas as linhas de trabalho disponíveis são mostradas.</span><span class="sxs-lookup"><span data-stu-id="fa443-156">By default, only available work lines are shown.</span></span> <span data-ttu-id="fa443-157">Para exibir todas as linhas da ID de trabalho (por exemplo, linhas que têm um tipo de trabalho de *Colocar*), marque a caixa de seleção **Mostrar todas as linhas** acima da grade.</span><span class="sxs-lookup"><span data-stu-id="fa443-157">To view all lines for the work ID (for example, lines that have a work type of *Put*), select the **Show all lines** check box above the grid.</span></span>

    <span data-ttu-id="fa443-158">A seguinte mensagem é mostrada: "Os usuários não podem processar linhas de trabalho até que você termine a divisão e feche esta página."</span><span class="sxs-lookup"><span data-stu-id="fa443-158">The following message is shown: "Users can't process lines of the work until you finish splitting and close this page."</span></span>

    <span data-ttu-id="fa443-159">O campo **Motivo de bloqueio de trabalho** do trabalho atual será definido como *Divisão do trabalho* e o trabalho será bloqueado.</span><span class="sxs-lookup"><span data-stu-id="fa443-159">The **Work blocking reason** field for the current work will be set to *Split work*, and the work will be blocked.</span></span>

    <span data-ttu-id="fa443-160">![Motivo do bloqueio](media/Blocking_reason.png "Motivo do bloqueio")</span><span class="sxs-lookup"><span data-stu-id="fa443-160">![Blocking reason](media/Blocking_reason.png "Blocking reason")</span></span>

1. <span data-ttu-id="fa443-161">Selecione as linhas a serem removidas da ID de trabalho atual e adicionadas a uma nova ID de trabalho.</span><span class="sxs-lookup"><span data-stu-id="fa443-161">Select the lines to remove from the current work ID and add to a new work ID.</span></span> <span data-ttu-id="fa443-162">Os seguintes eventos ocorrem:</span><span class="sxs-lookup"><span data-stu-id="fa443-162">The following events occur:</span></span>

    - <span data-ttu-id="fa443-163">Quando você divide o trabalho, as linhas selecionadas da ID de trabalho original são canceladas e, depois, copiadas em uma nova ID de trabalho.</span><span class="sxs-lookup"><span data-stu-id="fa443-163">When you split the work, the selected line or lines from the original work ID are canceled and then copied to a new work ID.</span></span>
    - <span data-ttu-id="fa443-164">A estrutura do modelo de trabalho existente e a localização da opção Colocar (e também futuros pares de retirada/ colocação) são preservados.</span><span class="sxs-lookup"><span data-stu-id="fa443-164">The existing work template structure and the location of the put (and also future pick/put pairs) are preserved.</span></span> <span data-ttu-id="fa443-165">Os valores para os seguintes campos de ID de trabalho são copiados do trabalho original para o novo trabalho:</span><span class="sxs-lookup"><span data-stu-id="fa443-165">Values for the following work ID fields are copied from the original work to the new work:</span></span>

        - <span data-ttu-id="fa443-166">ID da Carga</span><span class="sxs-lookup"><span data-stu-id="fa443-166">Load ID</span></span>
        - <span data-ttu-id="fa443-167">ID da Remessa</span><span class="sxs-lookup"><span data-stu-id="fa443-167">Shipment ID</span></span>
        - <span data-ttu-id="fa443-168">Tipo de ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="fa443-168">Work order type</span></span>
        - <span data-ttu-id="fa443-169">Número da ordem</span><span class="sxs-lookup"><span data-stu-id="fa443-169">Order number</span></span>
        - <span data-ttu-id="fa443-170">Site</span><span class="sxs-lookup"><span data-stu-id="fa443-170">Site</span></span>
        - <span data-ttu-id="fa443-171">Depósito</span><span class="sxs-lookup"><span data-stu-id="fa443-171">Warehouse</span></span>
        - <span data-ttu-id="fa443-172">Prioridade de trabalho</span><span class="sxs-lookup"><span data-stu-id="fa443-172">Work priority</span></span>
        - <span data-ttu-id="fa443-173">ID do pool de trabalho</span><span class="sxs-lookup"><span data-stu-id="fa443-173">Work pool ID</span></span>
        - <span data-ttu-id="fa443-174">ID da Onda</span><span class="sxs-lookup"><span data-stu-id="fa443-174">Wave ID</span></span>
        - <span data-ttu-id="fa443-175">Número de criação do trabalho</span><span class="sxs-lookup"><span data-stu-id="fa443-175">Work creation number</span></span>

    - <span data-ttu-id="fa443-176">Os seguintes campos não são copiados para a nova ID de trabalho:</span><span class="sxs-lookup"><span data-stu-id="fa443-176">The following fields aren't copied to the new work ID:</span></span>

        - <span data-ttu-id="fa443-177">**ID de trabalho** – Uma nova ID de trabalho é gerada a partir da sequência numérica apropriada.</span><span class="sxs-lookup"><span data-stu-id="fa443-177">**Work ID** – A new work ID is generated from the appropriate number sequence.</span></span>
        - <span data-ttu-id="fa443-178">**Status do trabalho** – Este campo está definido como *Aberto*.</span><span class="sxs-lookup"><span data-stu-id="fa443-178">**Work status** – This field is set to *Open*.</span></span>
        - <span data-ttu-id="fa443-179">**Bloqueado por** – Este campo é inicialmente definido como em branco.</span><span class="sxs-lookup"><span data-stu-id="fa443-179">**Locked by** – This field is initially set to blank.</span></span>
        - <span data-ttu-id="fa443-180">**ID da placa de licença de destino** – Este campo é deixado em branco.</span><span class="sxs-lookup"><span data-stu-id="fa443-180">**Target license plate ID** – This field is left blank.</span></span>
        - <span data-ttu-id="fa443-181">**Data e hora de criação** – Este campo é definido para a data e hora atuais.</span><span class="sxs-lookup"><span data-stu-id="fa443-181">**Created date and time** – This field is set to the current date and time.</span></span>
        - <span data-ttu-id="fa443-182">**Ciclo bloqueado/congelado** – Este campo é recalculado para a ID do trabalho original e a nova ID do trabalho.</span><span class="sxs-lookup"><span data-stu-id="fa443-182">**Blocked wave/frozen** – This field is recomputed for the original work ID and the new work ID.</span></span>

1. <span data-ttu-id="fa443-183">No Painel de Ação, selecione **Divisão do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="fa443-183">On the Action Pane, select **Split work**.</span></span>

<span data-ttu-id="fa443-184">Enquanto o trabalho está sendo dividido, a seguinte mensagem é exibida: "Operação de processamento - Divisão do trabalho".</span><span class="sxs-lookup"><span data-stu-id="fa443-184">While the work is being split, the following message is shown: "Processing operation - Split work".</span></span> <span data-ttu-id="fa443-185">Enquanto essa mensagem estiver visível, você pode cancelar a operação selecionando **Cancelar** na caixa de mensagem.</span><span class="sxs-lookup"><span data-stu-id="fa443-185">While this message is visible, you can cancel the operation by selecting **Cancel** in the message box.</span></span>

<span data-ttu-id="fa443-186">Se a caixa de seleção **Mostrar todas as linhas** estiver desmarcada, a linha que foi dividida e cancelada não aparecerá mais na grade.</span><span class="sxs-lookup"><span data-stu-id="fa443-186">If the **Show all lines** check box is cleared, the line that was split off and canceled will no longer appear in the grid.</span></span> <span data-ttu-id="fa443-187">Se a caixa de seleção estiver selecionada, você verá que o valor do campo **Status do trabalho** dessa linha foi alterado para *Cancelado*.</span><span class="sxs-lookup"><span data-stu-id="fa443-187">If the check box is selected, you should see that the value of the **Work status** field for that line has changed to *Canceled*.</span></span>

<span data-ttu-id="fa443-188">A seguinte notificação é mostrada para indicar que a nova ID de trabalho foi criada: "O trabalho \#\#\#\# foi criado pela divisão do trabalho original \#\#\#\#."</span><span class="sxs-lookup"><span data-stu-id="fa443-188">The following notification is shown to indicate that the new work ID has been created: "Work \#\#\#\# has been created by splitting off from original work \#\#\#\#."</span></span>

<span data-ttu-id="fa443-189">Outras linhas de trabalho da ID de trabalho original (como *Colocar* linhas) serão ajustadas conforme necessário para refletir as linhas de trabalho que foram canceladas.</span><span class="sxs-lookup"><span data-stu-id="fa443-189">Other work lines from the original work ID (such as *Put* lines) will be adjusted as required to reflect the lines of work that have been canceled.</span></span> <span data-ttu-id="fa443-190">Por exemplo, se a ID do trabalho original tem uma linha *Colocar* para uma quantidade de 15 e as linhas *Separar* com uma quantidade total de 10 foram canceladas, a nova quantidade *Colocar* na ID de trabalho original agora será são 5.</span><span class="sxs-lookup"><span data-stu-id="fa443-190">For example, if the original work ID had a *Put* line for a quantity of 15, and *Pick* lines that have a total quantity of 10 were canceled, the new *Put* quantity on the original work ID will now be 5.</span></span>

<span data-ttu-id="fa443-191">O novo trabalho não será atribuído imediatamente a nenhum usuário.</span><span class="sxs-lookup"><span data-stu-id="fa443-191">The new work won't immediately be assigned to any user.</span></span> <span data-ttu-id="fa443-192">Contudo, você pode atribuí-lo a um usuário agora, conforme necessário, usando a funcionalidade padrão da página **Detalhes do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="fa443-192">However, you can assign it to a user now, as required, by using the standard functionality of the **Work details** page.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fa443-193">É possível dividir apenas IDs de trabalho que contenham duas ou mais linhas de trabalho disponíveis.</span><span class="sxs-lookup"><span data-stu-id="fa443-193">You can split only work IDs that contain two or more available work lines.</span></span> <span data-ttu-id="fa443-194">Se você selecionar **Divisão do trabalho** quando houver apenas uma linha de trabalho, receberá a seguinte mensagem de erro: "Pelo menos uma linha de trabalho deve permanecer no trabalho inicial."</span><span class="sxs-lookup"><span data-stu-id="fa443-194">If you select **Split work** when there is only one work line, you will receive the following error message: "At least one work line must remain on initial work."</span></span> <span data-ttu-id="fa443-195">Nesse caso, nenhuma divisão ocorrerá.</span><span class="sxs-lookup"><span data-stu-id="fa443-195">In this case, no splitting will occur.</span></span>

## <a name="finish-a-work-split"></a><span data-ttu-id="fa443-196">Concluir uma divisão de trabalho</span><span class="sxs-lookup"><span data-stu-id="fa443-196">Finish a work split</span></span>

<span data-ttu-id="fa443-197">Para terminar o trabalho de divisão, o motivo de bloqueio *Divisão do trabalho* deve ser removido.</span><span class="sxs-lookup"><span data-stu-id="fa443-197">To finish splitting work, the *Split work* blocking reason must be removed.</span></span> <span data-ttu-id="fa443-198">Existem duas maneiras de concluir esta etapa:</span><span class="sxs-lookup"><span data-stu-id="fa443-198">There are two ways to complete this step:</span></span>

- <span data-ttu-id="fa443-199">O usuário que está dividindo o trabalho fecha a página **Divisão do trabalho** selecionando o botão **Fechar** (**X**) no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="fa443-199">The user who is splitting the work closes the **Split work** page by selecting the **Close** button (**X**) in the upper-right corner.</span></span> <span data-ttu-id="fa443-200">Quando a página for fechada, o motivo de bloqueio *Divisão do trabalho* será removido.</span><span class="sxs-lookup"><span data-stu-id="fa443-200">When the page is closed, the *Split Work* blocking reason will be removed.</span></span> <span data-ttu-id="fa443-201">O estado *Bloqueado* do trabalho será recalculado e, se não houver motivos de bloqueio restantes, ele será desbloqueado.</span><span class="sxs-lookup"><span data-stu-id="fa443-201">The *Blocked* state of this work will be recomputed and, if there are no remaining blocking reasons for this work, the work will be unblocked.</span></span>
- <span data-ttu-id="fa443-202">Qualquer usuário abre a ID de trabalho e seleciona o botão **Cancelar sessão de divisão do trabalho** no Painel de ações.</span><span class="sxs-lookup"><span data-stu-id="fa443-202">Any user opens the work ID and selects the **Cancel work split session** button on the Action Pane.</span></span> <span data-ttu-id="fa443-203">O motivo de bloqueio *Divisão do trabalho* será removido e o estado *Bloqueado* desse trabalho será recalculado, assim como quando a página **Divisão do trabalho** for fechada.</span><span class="sxs-lookup"><span data-stu-id="fa443-203">The *Split work* blocking reason will be removed, and the *Blocked* state of this work will be recomputed, just as when the **Split work** page is closed.</span></span>

<span data-ttu-id="fa443-204">Após a remoção do motivo de bloqueio *Divisão do trabalho*, o trabalho pode ser executado no dispositivo móvel, desde que o estado **Bloqueado** seja definido como *Não* na ID de trabalho.</span><span class="sxs-lookup"><span data-stu-id="fa443-204">After the *Split work* blocking reason is removed, the work can be run on the mobile device, provided that the **Blocked** state is set to *No* on the work ID.</span></span>

## <a name="user-blocking-on-the-warehouse-app"></a><span data-ttu-id="fa443-205">Bloqueio de usuário no aplicativo do depósito</span><span class="sxs-lookup"><span data-stu-id="fa443-205">User blocking on the warehouse app</span></span>

<span data-ttu-id="fa443-206">Se você tentar usar o aplicativo do depósito para executar o trabalho de separação em uma ID de trabalho que está sendo dividida, receberá a seguinte mensagem de erro: "O trabalho com ID \#\#\#\# está sendo dividido no momento."</span><span class="sxs-lookup"><span data-stu-id="fa443-206">If you try to use the warehouse app to run picking work against a work ID that is being split, you will receive the following error message: "The work with ID \#\#\#\# is currently being split."</span></span> <span data-ttu-id="fa443-207">Se você receber essa mensagem, selecione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="fa443-207">If you receive this message, select **Cancel**.</span></span> <span data-ttu-id="fa443-208">É possível continuar a processar outro trabalho.</span><span class="sxs-lookup"><span data-stu-id="fa443-208">You can then continue to process other work.</span></span>

## <a name="other-blocked-operations"></a><span data-ttu-id="fa443-209">Outras operações bloqueadas</span><span class="sxs-lookup"><span data-stu-id="fa443-209">Other blocked operations</span></span>

<span data-ttu-id="fa443-210">Qualquer operação que modifique linhas de trabalho, transações de estoque de trabalho ou links de reabastecimento relacionados ao trabalho que está sendo dividido falhará e a seguinte mensagem de erro será exibida: "O trabalho com ID \#\#\#\# está sendo dividido."</span><span class="sxs-lookup"><span data-stu-id="fa443-210">Any operations that modify work lines, work inventory transactions, or replenishment links that are related to work that is being split will fail, and the following error message will be shown: "The work with ID \#\#\#\# is currently being split."</span></span>
