---
title: Verificação de qualidade
description: Este tópico fornece informações sobre o recurso Verificação de qualidade. Este recurso permite que os trabalhadores de depósito​ façam verificações por amostragem para saber a qualidade ao receberem itens para a área de doca de entrada.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSQualityCheckTemplate, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSQualityCheckResult
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: dfb71f74732d65409003c4f6f74145442a1efa3f
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4422581"
---
# <a name="quality-check"></a><span data-ttu-id="9222c-104">Verificação de qualidade</span><span class="sxs-lookup"><span data-stu-id="9222c-104">Quality check</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9222c-105">O recurso *Verificação de qualidade* permite que os trabalhadores de depósito​ façam verificações por amostragem para saber a qualidade ao receberem itens para a área de doca de entrada.</span><span class="sxs-lookup"><span data-stu-id="9222c-105">The *Quality check* feature lets warehouse workers do quick spot checks for quality while they receive items to the inbound dock area.</span></span> <span data-ttu-id="9222c-106">Essas verificações de spot são benéficas quando os trabalhadores inspecionam a embalagem ou outras partes facilmente reconhecíveis de um item.</span><span class="sxs-lookup"><span data-stu-id="9222c-106">These spot checks are beneficial when workers inspect packaging or other easily recognizable parts of an item.</span></span> <span data-ttu-id="9222c-107">O recurso orienta os trabalhadores a verificar rapidamente se algo está obviamente com defeito ou danificado antes de colocar o estoque no local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="9222c-107">The feature guides workers to take a quick look to see whether anything is obviously faulty or damaged before they stock the inventory in its putaway location.</span></span>

<span data-ttu-id="9222c-108">Esse recurso é uma alternativa ao processo de verificação de qualidade padrão.</span><span class="sxs-lookup"><span data-stu-id="9222c-108">This feature is an alternative to the standard quality check process.</span></span> <span data-ttu-id="9222c-109">Ele oferece mais flexibilidade e processamento mais rápido.</span><span class="sxs-lookup"><span data-stu-id="9222c-109">It offers more flexibility and faster processing.</span></span>

<span data-ttu-id="9222c-110">Quando você usa esse recurso, a entrada e a verificação de qualidade ocorrem da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="9222c-110">When you use this feature, the arrival and quality check occur in the following way:</span></span>

1. <span data-ttu-id="9222c-111">Quando uma remessa chega, um trabalhador do depósito registra a entrada.</span><span class="sxs-lookup"><span data-stu-id="9222c-111">When a shipment arrives, a warehouse worker registers the arrival.</span></span> <span data-ttu-id="9222c-112">O trabalhador também examina uma placa de licença para registrar a localização.</span><span class="sxs-lookup"><span data-stu-id="9222c-112">The worker also scans a license plate to register the location.</span></span>
1. <span data-ttu-id="9222c-113">O trabalhador faz uma verificação de qualidade rápida e registra o resultado (aprovado ou reprovado) para essa placa de licença.</span><span class="sxs-lookup"><span data-stu-id="9222c-113">The worker does a quick quality check and records the result (pass or fail) for that license plate.</span></span>
1. <span data-ttu-id="9222c-114">Ocorre uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="9222c-114">One of the following actions occurs:</span></span>

    - <span data-ttu-id="9222c-115">Se a verificação de qualidade for aprovada, a placa de licença será aceita e dirigida a um local de recebimento, como de costume.</span><span class="sxs-lookup"><span data-stu-id="9222c-115">If the quality check is passed, the license plate is accepted and guided to a receiving location, as usual.</span></span>
    - <span data-ttu-id="9222c-116">Se a verificação de qualidade falhar, a placa de licença será rejeitada e o trabalho de armazenamento existente será redirecionado para um local alternativo para uma inspeção adicional.</span><span class="sxs-lookup"><span data-stu-id="9222c-116">If the quality check is failed, the license plate is rejected, and existing putaway work for it is redirected to an alternate location for further inspection.</span></span> <span data-ttu-id="9222c-117">Uma nova ordem de qualidade é criada.</span><span class="sxs-lookup"><span data-stu-id="9222c-117">A new quality order is created.</span></span> <span data-ttu-id="9222c-118">Para exibir a ordem de qualidade criada por meio da verificação de qualidade com falha, vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Ordens de qualidade**.</span><span class="sxs-lookup"><span data-stu-id="9222c-118">To view the quality order that is created from the failed quality check, go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>

<span data-ttu-id="9222c-119">Esse processo também pode ser configurado de forma que todas as placas de licença verificadas sejam imediatamente desviadas para o local da verificação de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9222c-119">This process can also be set up so that all scanned license plates are immediately diverted to the quality check location.</span></span>

## <a name="turn-on-the-quality-check-feature"></a><span data-ttu-id="9222c-120">Ativar o recurso Verificação de qualidade</span><span class="sxs-lookup"><span data-stu-id="9222c-120">Turn on the Quality check feature</span></span>

<span data-ttu-id="9222c-121">Para que você possa usar o recurso *Verificação de qualidade*, ele deve estar ativado no sistema.</span><span class="sxs-lookup"><span data-stu-id="9222c-121">Before you can use the *Quality check* feature, it must be turned on in your system.</span></span> <span data-ttu-id="9222c-122">Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo se necessário.</span><span class="sxs-lookup"><span data-stu-id="9222c-122">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="9222c-123">No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="9222c-123">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="9222c-124">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="9222c-124">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="9222c-125">**Nome do recurso:** *Verificação de qualidade*</span><span class="sxs-lookup"><span data-stu-id="9222c-125">**Feature name:** *Quality check*</span></span>

## <a name="set-up-the-feature-for-the-example-scenario"></a><span data-ttu-id="9222c-126">Configurar o recurso para o cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="9222c-126">Set up the feature for the example scenario</span></span>

<span data-ttu-id="9222c-127">Esta seção fornece diretrizes e um exemplo que mostra como configurar o recurso *Verificação de qualidade* e preparar dados de exemplo para o cenário de exemplo fornecido mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="9222c-127">This section provides guidelines and an example that shows how to set up the *Quality check* feature and prepare sample data for the example scenario that is provided later in this topic.</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="9222c-128">Disponibilizar dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="9222c-128">Make sample data available</span></span>

<span data-ttu-id="9222c-129">Para trabalhar com o [cenário de exemplo](#example-scenario) usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados.</span><span class="sxs-lookup"><span data-stu-id="9222c-129">To work through the [example scenario](#example-scenario) by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="9222c-130">Além disso, você deve selecionar a entidade legal **USMF** antes de começar.</span><span class="sxs-lookup"><span data-stu-id="9222c-130">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

### <a name="quality-check-template"></a><a name="quality-template"></a><span data-ttu-id="9222c-131">Modelo de verificação de qualidade</span><span class="sxs-lookup"><span data-stu-id="9222c-131">Quality check template</span></span>

<span data-ttu-id="9222c-132">O modelo de verificação de qualidade define as regras para fazer verificações por amostragem rápidas de qualidade no momento da recepção.</span><span class="sxs-lookup"><span data-stu-id="9222c-132">The quality check template defines the rules for doing quick spot checks for quality at the time of receiving.</span></span>

1. <span data-ttu-id="9222c-133">Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de verificação de qualidade**.</span><span class="sxs-lookup"><span data-stu-id="9222c-133">Go to **Warehouse management \> Setup \> Work \> Quality check template**.</span></span>
1. <span data-ttu-id="9222c-134">Selecione **Novo** para adicionar um modelo à grade.</span><span class="sxs-lookup"><span data-stu-id="9222c-134">Select **New** to add a template to the grid.</span></span>
1. <span data-ttu-id="9222c-135">Defina os seguintes valores para definir o novo modelo:</span><span class="sxs-lookup"><span data-stu-id="9222c-135">Set the following values to define the new template:</span></span>

    - <span data-ttu-id="9222c-136">**Nome do modelo de verificação de qualidade:** *Verificação integrada*</span><span class="sxs-lookup"><span data-stu-id="9222c-136">**Quality check template name:** *Dock check*</span></span>

        <span data-ttu-id="9222c-137">Insira um nome que identifique as políticas aplicadas a este modelo.</span><span class="sxs-lookup"><span data-stu-id="9222c-137">Enter a name that identifies the policies applied for this template.</span></span>

    - <span data-ttu-id="9222c-138">**Política de aceitação:** *Avisar usuário*</span><span class="sxs-lookup"><span data-stu-id="9222c-138">**Acceptance policy:** *Prompt user*</span></span>

        <span data-ttu-id="9222c-139">Especifique se os usuários devem ser solicitados a aceitar ou rejeitar a qualidade do estoque enquanto processam o trabalho, ou se a qualidade deve ser rejeitada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9222c-139">Specify whether users should be prompted to accept or reject the quality of the inventory while they process the work, or whether the quality should automatically be rejected.</span></span> <span data-ttu-id="9222c-140">As opções disponíveis são *Rejeitar automaticamente* e *Avisar usuário*.</span><span class="sxs-lookup"><span data-stu-id="9222c-140">The available options are *Auto reject* and *Prompt user*.</span></span>

    - <span data-ttu-id="9222c-141">**Política de processamento de qualidade:** *Criar ordem de qualidade*</span><span class="sxs-lookup"><span data-stu-id="9222c-141">**Quality processing policy:** *Create quality order*</span></span>

        <span data-ttu-id="9222c-142">Selecione a política que deve ser usada quando a qualidade do estoque é rejeitada.</span><span class="sxs-lookup"><span data-stu-id="9222c-142">Select the policy that should be used when the quality of the inventory is rejected.</span></span> <span data-ttu-id="9222c-143">As opções a seguir estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="9222c-143">The following options are available:</span></span>

        - <span data-ttu-id="9222c-144">*Criar somente trabalho* — basta criar trabalho para facilitar a movimentação de estoque.</span><span class="sxs-lookup"><span data-stu-id="9222c-144">*Create work only* – Just create work to facilitate inventory movement.</span></span>
        - <span data-ttu-id="9222c-145">*Criar ordem de qualidade* — criar uma ordem de qualidade para facilitar testes de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9222c-145">*Create quality order* – Create a quality order to facilitate quality tests.</span></span>

    - <span data-ttu-id="9222c-146">**Grupo de teste:** *Anexo*</span><span class="sxs-lookup"><span data-stu-id="9222c-146">**Test group:** *Enclosure*</span></span>

        <span data-ttu-id="9222c-147">Especifique o grupo de testes que deve ser usado na ordem de qualidade criada.</span><span class="sxs-lookup"><span data-stu-id="9222c-147">Specify the test group that should be used in the quality order that is created.</span></span> <span data-ttu-id="9222c-148">Os grupos de testes são configurados no módulo **Gerenciamento de estoque**.</span><span class="sxs-lookup"><span data-stu-id="9222c-148">Test groups are set up in the **Inventory management** module.</span></span>

        <span data-ttu-id="9222c-149">Deixe a opção **Texto destrutivo** desativada para o grupo de testes.</span><span class="sxs-lookup"><span data-stu-id="9222c-149">Leave the **Destructive text** option turned off for the test group.</span></span> <span data-ttu-id="9222c-150">Esta opção define se a amostra será destruída como parte dos testes no grupo de testes.</span><span class="sxs-lookup"><span data-stu-id="9222c-150">This option defines whether the sample will be destroyed as part of the tests in the test group.</span></span> <span data-ttu-id="9222c-151">Se um teste destrutivo for usado, o sistema gerará uma transação de estoque quando uma ordem de qualidade for criada para um item.</span><span class="sxs-lookup"><span data-stu-id="9222c-151">If a destructive test is used, the system generates an inventory transaction when a quality order is created for an item.</span></span> <span data-ttu-id="9222c-152">A nova transação de estoque prevê a redução de estoque para a quantidade de teste.</span><span class="sxs-lookup"><span data-stu-id="9222c-152">The new inventory transaction predicts the inventory reduction for the test quantity.</span></span> <span data-ttu-id="9222c-153">A redução de estoque ocorre quando a ordem de qualidade é concluída por meio da etapa de validação.</span><span class="sxs-lookup"><span data-stu-id="9222c-153">The inventory reduction occurs when the quality order is completed through the validation step.</span></span> <span data-ttu-id="9222c-154">A transação de estoque é identificada como uma ordem de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9222c-154">The inventory transaction is identified as a quality order.</span></span>

### <a name="work-class--quality-check"></a><a name="work-class"></a><span data-ttu-id="9222c-155">Classe de trabalho — verificação de qualidade</span><span class="sxs-lookup"><span data-stu-id="9222c-155">Work class – Quality check</span></span>

<span data-ttu-id="9222c-156">Classes de trabalho são usadas para direcionar e/ou limitar os tipos de linhas da ordem de serviço que trabalhadores de depósito podem processar em um dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="9222c-156">Work classes are used to direct and/or limit the type of work order lines that warehouse workers can process on a mobile device.</span></span>

1. <span data-ttu-id="9222c-157">Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Classes de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="9222c-157">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="9222c-158">Selecione **Novo** para criar uma classe de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9222c-158">Select **New** to create a work class.</span></span>
1. <span data-ttu-id="9222c-159">No cabeçalho, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="9222c-159">In the header, set the following values:</span></span>

    - <span data-ttu-id="9222c-160">**ID da classe de trabalho:** *Verificação de QC*</span><span class="sxs-lookup"><span data-stu-id="9222c-160">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="9222c-161">Insira um nome que identifique a classe de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9222c-161">Enter a name that identifies the work class.</span></span>

    - <span data-ttu-id="9222c-162">**Descrição:** *Verificação de QC*</span><span class="sxs-lookup"><span data-stu-id="9222c-162">**Description:** *QC Check*</span></span>

        <span data-ttu-id="9222c-163">Insira uma breve descrição que indique para que a classe de trabalho será usada.</span><span class="sxs-lookup"><span data-stu-id="9222c-163">Enter a short description that indicates what the work class is used for.</span></span>

    - <span data-ttu-id="9222c-164">**Tipo de ordem de serviço:** *Qualidade na verificação de qualidade*</span><span class="sxs-lookup"><span data-stu-id="9222c-164">**Work order type:** *Quality in quality check*</span></span>

        <span data-ttu-id="9222c-165">Selecione o tipo de ordem de serviço que é criado pela classe de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9222c-165">Select the type of work order that is created by the work class.</span></span> <span data-ttu-id="9222c-166">Ao configurar o trabalho de controle de qualidade, sempre selecione *Qualidade na verificação de qualidade*.</span><span class="sxs-lookup"><span data-stu-id="9222c-166">When you set up quality control work, always select *Quality in quality check*.</span></span>

1. <span data-ttu-id="9222c-167">Na FastTab **Tipos de local de colocação válidos**, deixe o campo **Tipo de local** em branco.</span><span class="sxs-lookup"><span data-stu-id="9222c-167">On the **Valid put location types** FastTab, leave the **Location type** field blank.</span></span>

    <span data-ttu-id="9222c-168">Se você selecionar um tipo de local, limite os locais em que os itens podem ser colocados após a separação.</span><span class="sxs-lookup"><span data-stu-id="9222c-168">If you select a location type, you limit the locations where items can be put after they are picked.</span></span> <span data-ttu-id="9222c-169">Essa campo é usado quando uma diretiva de localização tenta resolver a localização, ou quando um trabalhador do depósito especifica manualmente a localização do item de menu do dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="9222c-169">This field is used when a location directive tries to resolve the location, or when a warehouse worker manually specifies the location for the mobile device menu item.</span></span>

<span data-ttu-id="9222c-170">Para obter mais informações sobre classes de trabalho e sobre como criá-las, consulte [Criar uma classe de trabalho](tasks/create-work-class.md).</span><span class="sxs-lookup"><span data-stu-id="9222c-170">For more information about work classes and how to create them, see [Create a work class](tasks/create-work-class.md).</span></span>

### <a name="work-template"></a><span data-ttu-id="9222c-171">Modelo do trabalho</span><span class="sxs-lookup"><span data-stu-id="9222c-171">Work template</span></span>

<span data-ttu-id="9222c-172">Os modelos de trabalho permitem definir as operações de trabalho a serem executadas no depósito.</span><span class="sxs-lookup"><span data-stu-id="9222c-172">Work templates let you define the work operations that must be performed in the warehouse.</span></span> <span data-ttu-id="9222c-173">Normalmente, as operações de trabalho de depósito consistem em duas ações: um trabalhador do depósito retira o estoque disponível em um local e coloca o estoque coletado em outro local.</span><span class="sxs-lookup"><span data-stu-id="9222c-173">Typically, warehouse work operations consist of a pair of actions: a warehouse worker picks on-hand inventory up in one location and then puts the picked inventory down in another location.</span></span> <span data-ttu-id="9222c-174">Um modelo de trabalho para controle de qualidade define as operações de trabalho para fazer verificações de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9222c-174">A work template for quality control defines the work operations for doing quality checks.</span></span>

#### <a name="purchase-orders"></a><span data-ttu-id="9222c-175">Ordens de Compra</span><span class="sxs-lookup"><span data-stu-id="9222c-175">Purchase orders</span></span>

1. <span data-ttu-id="9222c-176">Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="9222c-176">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="9222c-177">No cabeçalho, defina o campo **Tipo de ordem de serviço** como *Ordens de compra*.</span><span class="sxs-lookup"><span data-stu-id="9222c-177">In the header, set the **Work order type** field to *Purchase orders*.</span></span>
1. <span data-ttu-id="9222c-178">No Painel de Ações, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9222c-178">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="9222c-179">Selecione um modelo de trabalho que deve incluir uma etapa de verificação de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9222c-179">Select a work template that should include a quality check step.</span></span> <span data-ttu-id="9222c-180">Na seção **Visão geral**, no campo **Modelo de trabalho**, selecione *Recibo de OC 51*.</span><span class="sxs-lookup"><span data-stu-id="9222c-180">In the **Overview** section, in the **Work template** field, select *51 PO Receipt*.</span></span>
1. <span data-ttu-id="9222c-181">Na seção **Detalhes do modelo de trabalho**, observe que a grade tem duas linhas existentes: uma para *Separar* e outra para *Colocar*.</span><span class="sxs-lookup"><span data-stu-id="9222c-181">In the **Work template details** section, notice that the grid has two existing lines: one for *Pick* and one for *Put*.</span></span>
1. <span data-ttu-id="9222c-182">Na seção **Detalhes do modelo de trabalho**, selecione **Novo** para adicionar uma linha para controle de qualidade na grade.</span><span class="sxs-lookup"><span data-stu-id="9222c-182">In the **Work template details** section, select **New** to add a row for quality control to the grid.</span></span> <span data-ttu-id="9222c-183">Observe que o campo **Número da linha** para a nova linha está definido como *3*.</span><span class="sxs-lookup"><span data-stu-id="9222c-183">Notice that the **Line number** field for the new line is set to *3*.</span></span>
1. <span data-ttu-id="9222c-184">Na nova linha, defina os valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="9222c-184">On the new line, set the following values.</span></span> <span data-ttu-id="9222c-185">Aceite os valores padrão para os campos restantes.</span><span class="sxs-lookup"><span data-stu-id="9222c-185">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="9222c-186">**Tipo de trabalho:** *Verificação de qualidade*</span><span class="sxs-lookup"><span data-stu-id="9222c-186">**Work type:** *Quality check*</span></span>
    - <span data-ttu-id="9222c-187">**ID da classe de trabalho:** *Compra*</span><span class="sxs-lookup"><span data-stu-id="9222c-187">**Work class ID:** *Purchase*</span></span>
    - <span data-ttu-id="9222c-188">**Nome do modelo de verificação de qualidade:** *Verificação integrada*</span><span class="sxs-lookup"><span data-stu-id="9222c-188">**Quality check template name:** *Dock check*</span></span>

        <span data-ttu-id="9222c-189">Selecione o ID exclusivo da classe de trabalho.</span><span class="sxs-lookup"><span data-stu-id="9222c-189">Select the unique ID for the work class.</span></span> <span data-ttu-id="9222c-190">Use este valor para configurar os itens de menu no dispositivo móvel e os tipos de trabalho que esses itens de menu podem processar.</span><span class="sxs-lookup"><span data-stu-id="9222c-190">You use this value to configure the menu items on the mobile device and the types of work that those menu items can process.</span></span>

1. <span data-ttu-id="9222c-191">No Painel de Ações, selecione **Salvar** para salvar o trabalho até o momento.</span><span class="sxs-lookup"><span data-stu-id="9222c-191">On the Action Pane, select **Save** to save your work so far.</span></span>

    <span data-ttu-id="9222c-192">Você receberá uma mensagem informativa indicando que "Inválida – Verificação de qualidade deve aparecer diretamente após uma separação".</span><span class="sxs-lookup"><span data-stu-id="9222c-192">You receive an informational message that states, "Invalid - Quality check must come directly after a pick."</span></span> <span data-ttu-id="9222c-193">Portanto, você deve alterar o valor **Número da linha** da linha recém-adicionada.</span><span class="sxs-lookup"><span data-stu-id="9222c-193">Therefore, you must change the **Line number** value for the line that you just added.</span></span>

1. <span data-ttu-id="9222c-194">Siga estas etapas para alterar o valor **Número da linha** da nova linha:</span><span class="sxs-lookup"><span data-stu-id="9222c-194">Follow these steps to change the **Line number** value for the new line:</span></span>

    1. <span data-ttu-id="9222c-195">Na seção **Detalhes do modelo de trabalho**, selecione a linha em que o campo **Tipo de trabalho** está definido como *Verificação de qualidade*.</span><span class="sxs-lookup"><span data-stu-id="9222c-195">In the **Work template details** section, select the line where the **Work type** field is set to *Quality check*.</span></span>
    2. <span data-ttu-id="9222c-196">Selecione o botão **Mover para cima** ou **Mover para baixo** para mover a linha *Verificação de qualidade* para que fique depois da linha *Separação*.</span><span class="sxs-lookup"><span data-stu-id="9222c-196">Select the **Move up** or **Move down** button to move the *Quality check* line so that it's after the *Pick* line.</span></span>

1. <span data-ttu-id="9222c-197">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9222c-197">On the Action Pane, select **Save**.</span></span>

#### <a name="quality-in-quality-check"></a><span data-ttu-id="9222c-198">Qualidade na verificação de qualidade</span><span class="sxs-lookup"><span data-stu-id="9222c-198">Quality in quality check</span></span>

<span data-ttu-id="9222c-199">Em seguida, crie um modelo de trabalho para a verificação de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9222c-199">Next, create a work template for the quality check.</span></span>

1. <span data-ttu-id="9222c-200">No cabeçalho da página **Modelos de trabalho**, altere o valor do campo **Tipo de ordem de trabalho** para *Qualidade na verificação de qualidade*.</span><span class="sxs-lookup"><span data-stu-id="9222c-200">In the header of the **Work templates** page, change the value of the **Work order type** field to *Quality in quality check*.</span></span>
1. <span data-ttu-id="9222c-201">No Painel de Ações, selecione **Novo** para adicionar uma linha à grade na seção **Visão geral**.</span><span class="sxs-lookup"><span data-stu-id="9222c-201">On the Action Pane, select **New** to add a row to the grid in the **Overview** section.</span></span>
1. <span data-ttu-id="9222c-202">Na nova linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="9222c-202">In the new row, set the following values:</span></span>

    - <span data-ttu-id="9222c-203">**Modelo de trabalho:** *Verificação de qualidade 51*</span><span class="sxs-lookup"><span data-stu-id="9222c-203">**Work template:** *51 Quality Check*</span></span>

        <span data-ttu-id="9222c-204">Insira um nome para o modelo.</span><span class="sxs-lookup"><span data-stu-id="9222c-204">Enter a name for the template.</span></span>

    - <span data-ttu-id="9222c-205">**Descrição do modelo de trabalho:** *Verificação de qualidade 51*</span><span class="sxs-lookup"><span data-stu-id="9222c-205">**Work template description:** *51 Quality Check*</span></span>

1. <span data-ttu-id="9222c-206">No Painel de Ações, selecione **Salvar** para disponibilizar a seção **Detalhes do modelo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="9222c-206">On the Action Pane, select **Save** to make the **Work template details** section available.</span></span>
1. <span data-ttu-id="9222c-207">Embora o novo modelo ainda esteja selecionado na seção **Visão geral**, selecione **Novo** na seção **Detalhes do modelo de trabalho** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="9222c-207">While the new template is still selected in the **Overview** section, select **New** in the **Work template details** section to add a row to the grid there.</span></span>
1. <span data-ttu-id="9222c-208">Na nova linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="9222c-208">In the new row, set the following values:</span></span>

    - <span data-ttu-id="9222c-209">**Tipo de trabalho:** *Separar*</span><span class="sxs-lookup"><span data-stu-id="9222c-209">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="9222c-210">**ID da classe de trabalho:** *Verificação de QC*</span><span class="sxs-lookup"><span data-stu-id="9222c-210">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="9222c-211">Selecione o nome da [classe de trabalho](#work-class) criada anteriormente para o trabalho de controle de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9222c-211">Select the name of the [work class](#work-class) that you created earlier for quality control work.</span></span>

1. <span data-ttu-id="9222c-212">Na seção **Detalhes do modelo de trabalho**, selecione **Novo** novamente para adicionar outra linha.</span><span class="sxs-lookup"><span data-stu-id="9222c-212">In the **Work template details** section, select **New** again to add another row.</span></span>
1. <span data-ttu-id="9222c-213">Na nova linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="9222c-213">In the new row, set the following values:</span></span>

    - <span data-ttu-id="9222c-214">**Tipo de trabalho:** *Colocar*</span><span class="sxs-lookup"><span data-stu-id="9222c-214">**Work type:** *Put*</span></span>
    - <span data-ttu-id="9222c-215">**ID da classe de trabalho:** *Verificação de QC*</span><span class="sxs-lookup"><span data-stu-id="9222c-215">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="9222c-216">Selecione o nome da [classe de trabalho](#work-class) criada anteriormente para o trabalho de controle de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9222c-216">Select the name of the [work class](#work-class) that you created earlier for quality control work.</span></span>

1. <span data-ttu-id="9222c-217">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9222c-217">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="9222c-218">Para obter mais informações sobre modelos de trabalho, consulte [Controlar o trabalho do depósito usando modelos de trabalho e diretivas de localização](control-warehouse-location-directives.md)</span><span class="sxs-lookup"><span data-stu-id="9222c-218">For more information about work templates, see [Control warehouse work by using work templates and location directives](control-warehouse-location-directives.md)</span></span>

### <a name="location-directive--quality-failures"></a><span data-ttu-id="9222c-219">Diretiva de localização – falhas de qualidade</span><span class="sxs-lookup"><span data-stu-id="9222c-219">Location directive – Quality failures</span></span>

<span data-ttu-id="9222c-220">As diretivas de localização são regras que ajudam a identificar locais de separação e armazenamento para a movimentação do estoque.</span><span class="sxs-lookup"><span data-stu-id="9222c-220">Location directives are rules that help identify pick and put locations for inventory movement.</span></span> <span data-ttu-id="9222c-221">Por exemplo, em uma transação de ordem de venda, uma diretiva de localização determina onde os itens serão separados e onde os itens separados serão colocados.</span><span class="sxs-lookup"><span data-stu-id="9222c-221">For example, in a sales order transaction, a location directive determines where the items will be picked and where the picked items will be put.</span></span> <span data-ttu-id="9222c-222">Você deve configurar uma regra de diretiva de localização para definir como as verificações de qualidade de falha serão tratadas.</span><span class="sxs-lookup"><span data-stu-id="9222c-222">You must configure a location directive rule to define how failed quality checks will be handled.</span></span>

1. <span data-ttu-id="9222c-223">Vá para **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.</span><span class="sxs-lookup"><span data-stu-id="9222c-223">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="9222c-224">No painel esquerdo, defina o campo **Tipo de ordem de trabalho** como *Ordens de compra* para trabalhar com diretivas de localização desse tipo.</span><span class="sxs-lookup"><span data-stu-id="9222c-224">In the left pane, set the **Work order type** field to *Purchase orders* to work with location directives of that type.</span></span>
1. <span data-ttu-id="9222c-225">No Painel de Ações, selecione **Novo** para criar uma diretiva de localização para verificações de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9222c-225">On the Action Pane, select **New** to create a location directive for quality checks.</span></span>
1. <span data-ttu-id="9222c-226">No cabeçalho, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="9222c-226">In the header, set the following values:</span></span>

    - <span data-ttu-id="9222c-227">**Número de sequência:** aceite o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="9222c-227">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="9222c-228">**Nome:** *51 para qualidade*</span><span class="sxs-lookup"><span data-stu-id="9222c-228">**Name:** *51 To Quality*</span></span>

1. <span data-ttu-id="9222c-229">Na FastTab **Diretivas de localização**, defina os valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="9222c-229">On the **Location directives** FastTab, set the following values.</span></span> <span data-ttu-id="9222c-230">Aceite os valores padrão para os campos restantes.</span><span class="sxs-lookup"><span data-stu-id="9222c-230">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="9222c-231">**Tipo de trabalho:** *Colocar*</span><span class="sxs-lookup"><span data-stu-id="9222c-231">**Work type:** *Put*</span></span>
    - <span data-ttu-id="9222c-232">**Local:** *5*</span><span class="sxs-lookup"><span data-stu-id="9222c-232">**Site:** *5*</span></span>
    - <span data-ttu-id="9222c-233">**Depósito:** *51*</span><span class="sxs-lookup"><span data-stu-id="9222c-233">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="9222c-234">No Painel de Ações, selecione **Salvar** para salvar a diretiva e disponibilizar a FastTab **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="9222c-234">On the Action Pane select **Save** to save your directive and make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="9222c-235">Na FastTab **Linhas**, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="9222c-235">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="9222c-236">Na nova linha, defina os valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="9222c-236">On the new line, set the following values.</span></span> <span data-ttu-id="9222c-237">Aceite os valores padrão para os campos restantes.</span><span class="sxs-lookup"><span data-stu-id="9222c-237">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="9222c-238">**Quantidade inicial:** *1*</span><span class="sxs-lookup"><span data-stu-id="9222c-238">**From quantity:** *1*</span></span>
    - <span data-ttu-id="9222c-239">**Quantidade final:** *1000000*</span><span class="sxs-lookup"><span data-stu-id="9222c-239">**To quantity:** *1000000*</span></span>

1. <span data-ttu-id="9222c-240">No Painel de Ações, selecione **Salvar** para salvar a nova linha e disponibilizar a FastTab **Ações de diretiva de localização**.</span><span class="sxs-lookup"><span data-stu-id="9222c-240">On the Action Pane, select **Save** to save the new line and make the **Location directive actions** FastTab available.</span></span>
1. <span data-ttu-id="9222c-241">Enquanto a nova linha ainda estiver selecionada na FastTab **Linhas**, selecione **Novo** na FastTab **Ações de diretiva de localização** para adicionar uma linha à grade, permitindo que você configure uma ação para a linha.</span><span class="sxs-lookup"><span data-stu-id="9222c-241">While the new line is still selected on the **Lines** FastTab, select **New** on the **Location directive actions** FastTab to add a row to the grid there, so that you can set up an action for the line.</span></span>
1. <span data-ttu-id="9222c-242">Na nova linha, defina o campo **Nome** como *Qualidade*.</span><span class="sxs-lookup"><span data-stu-id="9222c-242">In the new row, set the **Name** field to *Quality*.</span></span> <span data-ttu-id="9222c-243">Aceite os valores padrão para os campos restantes.</span><span class="sxs-lookup"><span data-stu-id="9222c-243">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="9222c-244">No Painel de Ações, selecione **Salvar** para disponibilizar o botão **Editar consulta** na FastTab **Ações de diretiva de localização**.</span><span class="sxs-lookup"><span data-stu-id="9222c-244">On the Action Pane, select **Save** to make the **Edit query** button on the **Location directive actions** FastTab available.</span></span>
1. <span data-ttu-id="9222c-245">Com a linha recém-adicionada ainda selecionada na FastTab **Ações de diretiva de localização**, selecione **Editar consulta** para abrir uma caixa de diálogo na qual você possa editar a consulta para a ação.</span><span class="sxs-lookup"><span data-stu-id="9222c-245">While the line that you just added is still selected on the **Location directive actions** FastTab, select **Edit query** to open a dialog box where you can edit the query for the action.</span></span>
1. <span data-ttu-id="9222c-246">Na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha à consulta.</span><span class="sxs-lookup"><span data-stu-id="9222c-246">On the **Range** tab, select **Add** to add a row to the query.</span></span>
1. <span data-ttu-id="9222c-247">Na nova linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="9222c-247">In the new row, set the following values:</span></span>

    - <span data-ttu-id="9222c-248">**Tabela:** *Localizações*</span><span class="sxs-lookup"><span data-stu-id="9222c-248">**Table:** *Locations*</span></span>
    - <span data-ttu-id="9222c-249">**Tabela derivada:** *Locais*</span><span class="sxs-lookup"><span data-stu-id="9222c-249">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="9222c-250">**Campo:** *Localização*</span><span class="sxs-lookup"><span data-stu-id="9222c-250">**Field:** *Location*</span></span>
    - <span data-ttu-id="9222c-251">**Critérios:** *QMS*</span><span class="sxs-lookup"><span data-stu-id="9222c-251">**Criteria:** *QMS*</span></span>

    <span data-ttu-id="9222c-252">A localização *QMS* é uma localização de depósito para qualidade.</span><span class="sxs-lookup"><span data-stu-id="9222c-252">The *QMS* location is a warehouse location for quality.</span></span>

1. <span data-ttu-id="9222c-253">Selecione **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9222c-253">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="9222c-254">Você deve alterar a sequência das diretivas de localização de ordens de compra para o depósito *51*.</span><span class="sxs-lookup"><span data-stu-id="9222c-254">You must now change the sequence of purchase order location directives for warehouse *51*.</span></span> <span data-ttu-id="9222c-255">Salve a nova diretiva de localização *51 para qualidade*, atualize a página e selecione a diretiva de localização na lista.</span><span class="sxs-lookup"><span data-stu-id="9222c-255">Save the new *51 To Quality* location directive, refresh the page, and select the location directive in the list.</span></span> <span data-ttu-id="9222c-256">Em seguida, use os botões **Mover para cima** e **Mover para baixo** no Painel de Ações para colocar a diretiva de localização para o depósito *51* na ordem a seguir.</span><span class="sxs-lookup"><span data-stu-id="9222c-256">Then use the **Move up** and **Move down** buttons on the Action Pane to put the location directive for warehouse *51* in the following order.</span></span> <span data-ttu-id="9222c-257">(Antes de selecionar **Mover para cima** ou **Mover para baixo**, você deve selecionar uma diretiva de localização na lista.)</span><span class="sxs-lookup"><span data-stu-id="9222c-257">(Before you select **Move up** or **Move down**, you must select a location directive in the list.)</span></span>

    1. <span data-ttu-id="9222c-258">51 para qualidade</span><span class="sxs-lookup"><span data-stu-id="9222c-258">51 To Quality</span></span>
    2. <span data-ttu-id="9222c-259">OC Direta 51</span><span class="sxs-lookup"><span data-stu-id="9222c-259">51 PO Direct</span></span>
    3. <span data-ttu-id="9222c-260">51 QMS</span><span class="sxs-lookup"><span data-stu-id="9222c-260">51 QMS</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="9222c-261">Itens de menu do dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="9222c-261">Mobile device menu items</span></span>

<span data-ttu-id="9222c-262">Configure um item de menu para que os dispositivos móveis possam executar a função **Verificação de Qualidade**.</span><span class="sxs-lookup"><span data-stu-id="9222c-262">Configure a menu item so that mobile devices can perform the **Quality Check** function.</span></span>

#### <a name="purchase-putaway"></a><span data-ttu-id="9222c-263">Armazenamento de compra</span><span class="sxs-lookup"><span data-stu-id="9222c-263">Purchase putaway</span></span>

1. <span data-ttu-id="9222c-264">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="9222c-264">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="9222c-265">Na lista, selecione o item de menu **Armazenamento de compra**.</span><span class="sxs-lookup"><span data-stu-id="9222c-265">In the list, select the **Purchase put-away** menu item.</span></span>
1. <span data-ttu-id="9222c-266">No Painel de Ações, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9222c-266">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="9222c-267">Na seção **Classes de trabalho**, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="9222c-267">In the **Work classes** section, select **New** to add a row to the grid.</span></span>
1. <span data-ttu-id="9222c-268">Na nova linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="9222c-268">In the new row, set the following values:</span></span>

    - <span data-ttu-id="9222c-269">**ID da classe de trabalho:** *Verificação de QC*</span><span class="sxs-lookup"><span data-stu-id="9222c-269">**Work class ID:** *QC Check*</span></span>

        <span data-ttu-id="9222c-270">Insira o nome da [classe de trabalho](#work-class) criada anteriormente para o trabalho de controle de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9222c-270">Enter the name of the [work class](#work-class) that you created earlier for quality control work.</span></span>

    - <span data-ttu-id="9222c-271">**Tipo de ordem de serviço:** *Qualidade na verificação de qualidade*</span><span class="sxs-lookup"><span data-stu-id="9222c-271">**Work order type:** *Quality in quality check*</span></span>

1. <span data-ttu-id="9222c-272">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9222c-272">On the Action Pane, select **Save**.</span></span>

#### <a name="purchase-order-line-receiving"></a><span data-ttu-id="9222c-273">Recebimento da linha da ordem de compra</span><span class="sxs-lookup"><span data-stu-id="9222c-273">Purchase order line receiving</span></span>

1. <span data-ttu-id="9222c-274">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="9222c-274">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="9222c-275">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9222c-275">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9222c-276">No cabeçalho, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="9222c-276">In the header, set the following values:</span></span>

    - <span data-ttu-id="9222c-277">**Nome do item de menu:** *Recebimento da linha da OC*</span><span class="sxs-lookup"><span data-stu-id="9222c-277">**Menu item name:** *PO line receiving*</span></span>
    - <span data-ttu-id="9222c-278">**Título:** *Recebimento da linha da OC*</span><span class="sxs-lookup"><span data-stu-id="9222c-278">**Title:** *PO line receiving*</span></span>
    - <span data-ttu-id="9222c-279">**Modo:** *Trabalho*</span><span class="sxs-lookup"><span data-stu-id="9222c-279">**Mode:** *Work*</span></span>
    - <span data-ttu-id="9222c-280">**Usar trabalho existente:** *Não*</span><span class="sxs-lookup"><span data-stu-id="9222c-280">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="9222c-281">Na FastTab **Geral**, defina os valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="9222c-281">On the **General** FastTab, set the following values.</span></span> <span data-ttu-id="9222c-282">Aceite os valores padrão para os campos restantes.</span><span class="sxs-lookup"><span data-stu-id="9222c-282">Accept the default values for the remaining fields.</span></span>

    - <span data-ttu-id="9222c-283">**Processo de criação de trabalho:** *Recebimento e armazenamento da linha da ordem de compra*</span><span class="sxs-lookup"><span data-stu-id="9222c-283">**Work creation process:** *Purchase order line receiving and put away*</span></span>
    - <span data-ttu-id="9222c-284">**Gerar placa de licença:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="9222c-284">**Generate license plate:** *Yes*</span></span>
    - <span data-ttu-id="9222c-285">**Modelo de trabalho:** *Recibo de OC 51*</span><span class="sxs-lookup"><span data-stu-id="9222c-285">**Work template:** *51 PO Receipt*</span></span>

1. <span data-ttu-id="9222c-286">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9222c-286">On the Action Pane, select **Save**.</span></span>

#### <a name="add-the-menu-item-to-a-mobile-device-menu"></a><span data-ttu-id="9222c-287">Adicionar o item de menu ao menu de um dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="9222c-287">Add the menu item to a mobile device menu</span></span>

1. <span data-ttu-id="9222c-288">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="9222c-288">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="9222c-289">No painel esquerdo, selecione o menu **Entrada**.</span><span class="sxs-lookup"><span data-stu-id="9222c-289">In the left pane, select the **Inbound** menu.</span></span>
1. <span data-ttu-id="9222c-290">No Painel de Ações, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9222c-290">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="9222c-291">Na coluna **Menus e itens de menu disponíveis**, selecione o novo item de menu **Recebimento da linha da OC**.</span><span class="sxs-lookup"><span data-stu-id="9222c-291">In the **Available menus and menu items** column, select the new **PO line receiving** menu item.</span></span>
1. <span data-ttu-id="9222c-292">Selecione o botão de seta para a direita para mover **Recebimento da linha da OC** para a coluna **Estrutura de menu**.</span><span class="sxs-lookup"><span data-stu-id="9222c-292">Select the right arrow button to move **PO line receiving** to the **Menu structure** column.</span></span>
1. <span data-ttu-id="9222c-293">Na coluna **Estrutura de menu**, selecione **Recebimento da linha da OC** e, depois, selecione o botão de seta para cima ou seta para baixo para mover o item de menu para a posição desejada no menu dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="9222c-293">In the **Menu structure** column, select **PO line receiving**, and then select the up arrow or down arrow button to move the menu item to the desired position on the mobile device menu.</span></span>
1. <span data-ttu-id="9222c-294">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9222c-294">On the Action Pane, select **Save**.</span></span>

## <a name="example-scenario"></a><a name="example-scenario"></a><span data-ttu-id="9222c-295">Cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="9222c-295">Example scenario</span></span>

<span data-ttu-id="9222c-296">Após disponibilizar todos os dados de exemplo descritos anteriormente e configurá-los, você poderá trabalhar neste cenário para testar o recurso *Verificação de qualidade*.</span><span class="sxs-lookup"><span data-stu-id="9222c-296">After you've made all the previously described sample data available and set it up, you can work through this scenario to try out the *Quality check* feature.</span></span> <span data-ttu-id="9222c-297">Os valores que são mostrados neste cenário pressupõem que você está trabalhando com os dados de demonstração padrão, que você selecionou a entidade legal **USMF** e preparou os registros de exemplo descritos anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="9222c-297">The values that are shown in this scenario assume that you're working with the standard demo data, that you selected the **USMF** legal entity, and that you prepared the sample records that are described earlier in this topic.</span></span> <span data-ttu-id="9222c-298">Esse cenário também serve como exemplo para mostrar como o recurso pode ser usado em uma configuração de produção.</span><span class="sxs-lookup"><span data-stu-id="9222c-298">This scenario also serves as an example that shows how the feature can be used in a production setting.</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="9222c-299">Criar uma ordem de compra</span><span class="sxs-lookup"><span data-stu-id="9222c-299">Create a purchase order</span></span>

1. <span data-ttu-id="9222c-300">Acesse **Compras \> Ordens de compra \> Todas ordens de compra**.</span><span class="sxs-lookup"><span data-stu-id="9222c-300">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="9222c-301">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9222c-301">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9222c-302">Na caixa de diálogo **Criar ordem de compra**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="9222c-302">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="9222c-303">**Conta do fornecedor:** *104*</span><span class="sxs-lookup"><span data-stu-id="9222c-303">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="9222c-304">**Depósito:** *51*</span><span class="sxs-lookup"><span data-stu-id="9222c-304">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="9222c-305">Selecione **OK** para fechar a caixa de diálogo e abrir a nova ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="9222c-305">Select **OK** to close the dialog box and open the new purchase order.</span></span>
1. <span data-ttu-id="9222c-306">Na FastTab **Linhas de ordem de compra**, a grade contém uma linha nova, em branco.</span><span class="sxs-lookup"><span data-stu-id="9222c-306">On the **Purchase order lines** FastTab, the grid contains a new, blank line.</span></span> <span data-ttu-id="9222c-307">Nessa linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="9222c-307">On this line, set the following values:</span></span>

    - <span data-ttu-id="9222c-308">**Número de item:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="9222c-308">**Item number:** *M9203*</span></span>
    - <span data-ttu-id="9222c-309">**Quantidade:** *3*</span><span class="sxs-lookup"><span data-stu-id="9222c-309">**Quantity:** *3*</span></span>
    - <span data-ttu-id="9222c-310">**Unidade:** *PL*</span><span class="sxs-lookup"><span data-stu-id="9222c-310">**Unit:** *PL*</span></span>

1. <span data-ttu-id="9222c-311">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9222c-311">On the Action Pane, select **Save**.</span></span>

### <a name="process-quality-check-receiving"></a><span data-ttu-id="9222c-312">Recebimento da verificação de qualidade do processo</span><span class="sxs-lookup"><span data-stu-id="9222c-312">Process quality check receiving</span></span>

<span data-ttu-id="9222c-313">Depois que a ordem de compra for criada, ela poderá ser recebida usando o item de menu **Recebimento da linha da OC** e a funcionalidade do recurso *Verificação de qualidade*.</span><span class="sxs-lookup"><span data-stu-id="9222c-313">After the purchase order has been created, it can be received by using the **PO line receiving** menu item and the functionality of the *Quality check* feature.</span></span>

#### <a name="receive-pallet-1"></a><span data-ttu-id="9222c-314">Receber palete 1</span><span class="sxs-lookup"><span data-stu-id="9222c-314">Receive pallet 1</span></span>

1. <span data-ttu-id="9222c-315">Entre no aplicativo do depósito como um usuário do depósito *51*.</span><span class="sxs-lookup"><span data-stu-id="9222c-315">Sign in to the warehouse app as a user for warehouse *51*.</span></span> <span data-ttu-id="9222c-316">(Insira *51* como a ID do usuário e *1* como a senha.)</span><span class="sxs-lookup"><span data-stu-id="9222c-316">(Enter *51* as the user ID and *1* as the password.)</span></span>
1. <span data-ttu-id="9222c-317">Vá para **Entrada \> Recebimento da linha da OC**.</span><span class="sxs-lookup"><span data-stu-id="9222c-317">Go to **Inbound \> PO line receiving**.</span></span>
1. <span data-ttu-id="9222c-318">No campo **PONUM**, insira o número da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="9222c-318">In the **PONUM** field, enter the purchase order number.</span></span>
1. <span data-ttu-id="9222c-319">Confirme o número da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="9222c-319">Confirm the purchase order number.</span></span>
1. <span data-ttu-id="9222c-320">No campo **LINENUM**, insira o número da linha da ordem de compra que está sendo recebida.</span><span class="sxs-lookup"><span data-stu-id="9222c-320">In the **LINENUM** field, enter the number of the purchase order line that is being received.</span></span> <span data-ttu-id="9222c-321">Como a ordem tem apenas uma linha neste cenário, você inserirá *1* no campo **LINENUM** para cada etapa de recebimento.</span><span class="sxs-lookup"><span data-stu-id="9222c-321">Because the order has only one line in this scenario, you will enter *1* in the **LINENUM** field for each receiving step.</span></span>
1. <span data-ttu-id="9222c-322">Confirme o número da linha.</span><span class="sxs-lookup"><span data-stu-id="9222c-322">Confirm the line number.</span></span>
1. <span data-ttu-id="9222c-323">No campo **QTD**, insira a quantidade a ser recebida.</span><span class="sxs-lookup"><span data-stu-id="9222c-323">In the **QTY** field, enter the quantity to receive.</span></span> <span data-ttu-id="9222c-324">Como a ordem de compra é para três paletes (*PL*) neste cenário e há três etapas de recebimento, você inserirá *1* no campo **QTD** para cada etapa de recebimento.</span><span class="sxs-lookup"><span data-stu-id="9222c-324">Because the purchase order is for three pallets (*PL*) in this scenario, and there are three receiving steps, you will enter *1* in the **QTY** field for each receiving step.</span></span>
1. <span data-ttu-id="9222c-325">Confirme a quantidade.</span><span class="sxs-lookup"><span data-stu-id="9222c-325">Confirm the quantity.</span></span>

    <span data-ttu-id="9222c-326">A página **Verificação de qualidade** que aparece não tem campos de entrada.</span><span class="sxs-lookup"><span data-stu-id="9222c-326">The **Quality check** page that appears has no entry fields.</span></span> <span data-ttu-id="9222c-327">Ela tem apenas o botão de confirmação (marca de seleção) na parte inferior e o botão de menu (**≡**) na parte superior.</span><span class="sxs-lookup"><span data-stu-id="9222c-327">It has only the confirmation (check mark) button at the bottom and the Menu button (**≡**) at the top.</span></span> <span data-ttu-id="9222c-328">(Às vezes, o botão de menu é referenciado como hambúrguer ou botão de hambúrguer.) Para agilizar o processo de verificação de qualidade, quando o palete passa pela verificação de qualidade, o usuário apenas confirma a página **Verificação de qualidade**.</span><span class="sxs-lookup"><span data-stu-id="9222c-328">(The Menu button is sometimes referred to as the hamburger or the hamburger button.) To expedite the quality check process, when the pallet passes the quality check, the user just confirms the **Quality check** page.</span></span>

    <span data-ttu-id="9222c-329">![Página Verificação de qualidade](media/quality-check.png "Página Verificação de qualidade")</span><span class="sxs-lookup"><span data-stu-id="9222c-329">![Quality check page](media/quality-check.png "Quality check page")</span></span>

1. <span data-ttu-id="9222c-330">Selecione o botão de confirmação para passar a verificação de qualidade para o palete 1 da linha 1.</span><span class="sxs-lookup"><span data-stu-id="9222c-330">Select the confirmation button to pass the quality check for pallet 1 from line 1.</span></span>

    <span data-ttu-id="9222c-331">A página **Ordens de compra: colocar** que aparece mostra detalhes do trabalho de colocação:</span><span class="sxs-lookup"><span data-stu-id="9222c-331">The **Purchase orders: Put** page that appears shows details of the put work:</span></span>

    - <span data-ttu-id="9222c-332">**LOC:** a localização determinada do sistema</span><span class="sxs-lookup"><span data-stu-id="9222c-332">**LOC:** The system determined location</span></span>

        <span data-ttu-id="9222c-333">Essa localização é o local de armazenamento designado para recebimento da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="9222c-333">This location is the designated putaway location for purchase order receiving.</span></span>

    - <span data-ttu-id="9222c-334">**LP:** a ID da placa de licença gerada pelo sistema</span><span class="sxs-lookup"><span data-stu-id="9222c-334">**LP:** The system-generated License plate ID</span></span>
    - <span data-ttu-id="9222c-335">**Item:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="9222c-335">**Item:** *M9203*</span></span>
    - <span data-ttu-id="9222c-336">**Qtd:** *1 PL: 100 cada*</span><span class="sxs-lookup"><span data-stu-id="9222c-336">**Qty:** *1 PL: 100 ea*</span></span>

    <span data-ttu-id="9222c-337">A descrição do item também é mostrada.</span><span class="sxs-lookup"><span data-stu-id="9222c-337">The item description is also shown.</span></span>

1. <span data-ttu-id="9222c-338">Confirme o trabalho de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="9222c-338">Confirm the putaway work.</span></span>

    <span data-ttu-id="9222c-339">Na página **Tarefa** para recebimento de linha da ordem de compra, você recebe uma mensagem "Trabalho Concluído".</span><span class="sxs-lookup"><span data-stu-id="9222c-339">On the **Task** page for purchase order line receiving, you receive a "Work Completed" message.</span></span> <span data-ttu-id="9222c-340">O campo **LINENUM** está disponível para que você comece a receber o próximo palete.</span><span class="sxs-lookup"><span data-stu-id="9222c-340">The **LINENUM** field is available so that you can start to receive the next pallet.</span></span>

#### <a name="receive-pallet-2"></a><span data-ttu-id="9222c-341">Receber palete 2</span><span class="sxs-lookup"><span data-stu-id="9222c-341">Receive pallet 2</span></span>

<span data-ttu-id="9222c-342">Neste cenário, o palete 2 será rejeitado.</span><span class="sxs-lookup"><span data-stu-id="9222c-342">For this scenario, pallet 2 will be rejected.</span></span>

1. <span data-ttu-id="9222c-343">No campo **LINENUM**, insira *1* e confirme o número da linha.</span><span class="sxs-lookup"><span data-stu-id="9222c-343">In the **LINENUM** field, enter *1*, and confirm the line number.</span></span>
1. <span data-ttu-id="9222c-344">O campo **QTD** agora está disponível.</span><span class="sxs-lookup"><span data-stu-id="9222c-344">The **QTY** field is now available.</span></span> <span data-ttu-id="9222c-345">Insira *1* e confirme a quantidade.</span><span class="sxs-lookup"><span data-stu-id="9222c-345">Enter *1*, and confirm the quantity.</span></span>

    <span data-ttu-id="9222c-346">A página **Verificação de qualidade** é exibida.</span><span class="sxs-lookup"><span data-stu-id="9222c-346">The **Quality check** page appears.</span></span> <span data-ttu-id="9222c-347">Para esse recebimento, o palete será rejeitado para qualidade e será colocado no local de qualidade *QMS*.</span><span class="sxs-lookup"><span data-stu-id="9222c-347">For this receipt, the pallet will be rejected for quality, and it will be put into the *QMS* quality location.</span></span>

1. <span data-ttu-id="9222c-348">Selecione o botão de menu (**≡**) na parte superior da página e, no menu, selecione **Rejeitar**.</span><span class="sxs-lookup"><span data-stu-id="9222c-348">Select the Menu button (**≡**) at the top of the page, and then, on the menu, select **Reject**.</span></span>
1. <span data-ttu-id="9222c-349">Na página **Tarefa**, insira **QMS** como o local *Colocar* para onde o palete será enviado para inspeção adicional.</span><span class="sxs-lookup"><span data-stu-id="9222c-349">On the **Task** page that appears, enter **QMS** as the *Put* location to send the pallet to for further inspection.</span></span>

    <span data-ttu-id="9222c-350">A página **Qualidade na verificação de qualidade: colocar** que aparece mostra detalhes do trabalho de colocação:</span><span class="sxs-lookup"><span data-stu-id="9222c-350">The **Quality in quality check: Put** page that appears shows details of the put work:</span></span>

    - <span data-ttu-id="9222c-351">**LOC:** *QMS*</span><span class="sxs-lookup"><span data-stu-id="9222c-351">**LOC:** *QMS*</span></span>

        <span data-ttu-id="9222c-352">Essa localização é o local de armazenamento designado para recebimento da qualidade rejeitada.</span><span class="sxs-lookup"><span data-stu-id="9222c-352">This location is the designated putaway location for rejected quality receiving.</span></span>

    - <span data-ttu-id="9222c-353">**LP:** a ID da placa de licença gerada pelo sistema</span><span class="sxs-lookup"><span data-stu-id="9222c-353">**LP:** The system-generated License plate ID</span></span>
    - <span data-ttu-id="9222c-354">**Item:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="9222c-354">**Item:** *M9203*</span></span>
    - <span data-ttu-id="9222c-355">**Qtd:** *1 PL: 100 cada*</span><span class="sxs-lookup"><span data-stu-id="9222c-355">**Qty:** *1 PL: 100 ea*</span></span>

    <span data-ttu-id="9222c-356">A descrição do item também é mostrada.</span><span class="sxs-lookup"><span data-stu-id="9222c-356">The item description is also shown.</span></span>

1. <span data-ttu-id="9222c-357">Confirme o trabalho de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="9222c-357">Confirm the putaway work.</span></span>

    <span data-ttu-id="9222c-358">Na página **Tarefa** para recebimento de linha da ordem de compra, você recebe uma mensagem "Trabalho Concluído".</span><span class="sxs-lookup"><span data-stu-id="9222c-358">On the **Task** page for purchase order line receiving, you receive a "Work Completed" message.</span></span> <span data-ttu-id="9222c-359">O campo **LINENUM** está disponível para que você comece a receber o próximo palete.</span><span class="sxs-lookup"><span data-stu-id="9222c-359">The **LINENUM** field is available so that you can start to receive the next pallet.</span></span>

<span data-ttu-id="9222c-360">Você acabou de concluir a verificação de qualidade e criou uma ordem de qualidade para o palete rejeitado.</span><span class="sxs-lookup"><span data-stu-id="9222c-360">You've now completed the quality check and created a quality order for the rejected pallet.</span></span> <span data-ttu-id="9222c-361">Para exibir a ordem que foi criada, vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Ordens de qualidade**.</span><span class="sxs-lookup"><span data-stu-id="9222c-361">To view the order that was created, go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>

<span data-ttu-id="9222c-362">O teste da ordem de qualidade pode ser processado agora.</span><span class="sxs-lookup"><span data-stu-id="9222c-362">Quality order testing can now be processed.</span></span> <span data-ttu-id="9222c-363">O teste de qualidade não é abordado neste tópico.</span><span class="sxs-lookup"><span data-stu-id="9222c-363">Quality testing isn't covered in this topic.</span></span>

<span data-ttu-id="9222c-364">Para obter mais informações sobre o gerenciamento de qualidade, consulte [Visão geral do gerenciamento de qualidade](../inventory/enable-quality-management.md)</span><span class="sxs-lookup"><span data-stu-id="9222c-364">For more information about quality management, see [Quality management overview](../inventory/enable-quality-management.md)</span></span>

#### <a name="receive-pallet-3"></a><span data-ttu-id="9222c-365">Receber palete 3</span><span class="sxs-lookup"><span data-stu-id="9222c-365">Receive pallet 3</span></span>

<span data-ttu-id="9222c-366">Neste cenário, o palete 3 será aceito.</span><span class="sxs-lookup"><span data-stu-id="9222c-366">For this scenario, pallet 3 will be accepted.</span></span>

1. <span data-ttu-id="9222c-367">No campo **LINENUM**, insira *1* e confirme o número da linha.</span><span class="sxs-lookup"><span data-stu-id="9222c-367">In the **LINENUM** field, enter *1*, and confirm the line number.</span></span>
1. <span data-ttu-id="9222c-368">O campo **QTD** agora está disponível.</span><span class="sxs-lookup"><span data-stu-id="9222c-368">The **QTY** field is now available.</span></span> <span data-ttu-id="9222c-369">Insira *1* e confirme a quantidade.</span><span class="sxs-lookup"><span data-stu-id="9222c-369">Enter *1*, and confirm the quantity.</span></span>

    <span data-ttu-id="9222c-370">A página **Verificação de qualidade** é exibida.</span><span class="sxs-lookup"><span data-stu-id="9222c-370">The **Quality check** page appears.</span></span> <span data-ttu-id="9222c-371">Para esse recebimento, o palete será aceito para qualidade e será colocado em um local de armazenamento em massa.</span><span class="sxs-lookup"><span data-stu-id="9222c-371">For this receipt, the pallet will be accepted for quality, and it will be put into a bulk putaway location.</span></span>

1. <span data-ttu-id="9222c-372">Selecione o botão de confirmação para passar a verificação de qualidade.</span><span class="sxs-lookup"><span data-stu-id="9222c-372">Select the confirmation button to pass the quality check.</span></span>

    <span data-ttu-id="9222c-373">A página **Ordens de compra: colocar** que aparece mostra detalhes do trabalho de colocação:</span><span class="sxs-lookup"><span data-stu-id="9222c-373">The **Purchase orders: Put** page that appears shows details of the put work:</span></span>

    - <span data-ttu-id="9222c-374">**LOC:** a localização determinada do sistema</span><span class="sxs-lookup"><span data-stu-id="9222c-374">**LOC:** The system determined location</span></span>

        <span data-ttu-id="9222c-375">Essa localização é o local de armazenamento designado para recebimento da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="9222c-375">This location is the designated putaway location for purchase order receiving.</span></span>

    - <span data-ttu-id="9222c-376">**LP:** a ID da placa de licença gerada pelo sistema</span><span class="sxs-lookup"><span data-stu-id="9222c-376">**LP:** The system-generated License plate ID</span></span>
    - <span data-ttu-id="9222c-377">**Item:** *M9203*</span><span class="sxs-lookup"><span data-stu-id="9222c-377">**Item:** *M9203*</span></span>
    - <span data-ttu-id="9222c-378">**Qtd:** *1 PL: 100 cada*</span><span class="sxs-lookup"><span data-stu-id="9222c-378">**Qty:** *1 PL: 100 ea*</span></span>

    <span data-ttu-id="9222c-379">A descrição do item também é mostrada.</span><span class="sxs-lookup"><span data-stu-id="9222c-379">The item description is also shown.</span></span>

1. <span data-ttu-id="9222c-380">Confirme o trabalho de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="9222c-380">Confirm the putaway work.</span></span>

    <span data-ttu-id="9222c-381">Na página **Tarefa** para recebimento de linha da ordem de compra, você recebe uma mensagem "Trabalho Concluído".</span><span class="sxs-lookup"><span data-stu-id="9222c-381">On the **Task** page for purchase order line receiving, you receive a "Work Completed" message.</span></span> <span data-ttu-id="9222c-382">O campo **LINENUM** está disponível para que você comece a receber o próximo palete.</span><span class="sxs-lookup"><span data-stu-id="9222c-382">The **LINENUM** field is available so that you can start to receive the next pallet.</span></span>

1. <span data-ttu-id="9222c-383">Selecione o botão de menu (**≡**) na parte superior da página e, no menu, selecione **Cancelar** para voltar ao menu.</span><span class="sxs-lookup"><span data-stu-id="9222c-383">Select the Menu button (**≡**) at the top of the page, and then, on the menu, select **Cancel** to return to the menu.</span></span>

<span data-ttu-id="9222c-384">Agora você pode fechar o aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="9222c-384">You can now close the mobile app.</span></span>
