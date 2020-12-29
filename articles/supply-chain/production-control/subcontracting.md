---
title: Subcontratação
description: Esse tópico o ajudará a criar um passo a passo da subcontratação na fabricação no Dynamics 365 Supply Chain Management.
author: christophernread
manager: tfehr
ms.date: 09/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2018-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1cc1040393d843f39ca8c741a7c51435c7169c00
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4421919"
---
# <a name="subcontracting"></a><span data-ttu-id="ddca3-103">Subcontratação</span><span class="sxs-lookup"><span data-stu-id="ddca3-103">Subcontracting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ddca3-104">Esse tópico o ajudará a criar um passo a passo da subcontratação de fabricação no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ddca3-104">This topic will help you build a walkthrough of subcontracting in manufacturing in Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="ddca3-105">A primeira parte desse tópico descreve a configuração dos dados.</span><span class="sxs-lookup"><span data-stu-id="ddca3-105">The first part of this topic describes the setup of the data.</span></span> <span data-ttu-id="ddca3-106">A segunda parte fornece orientações sobre as etapas do passo a passo.</span><span class="sxs-lookup"><span data-stu-id="ddca3-106">The second part takes you through the steps in the walkthrough.</span></span>

## <a name="target-audience"></a><span data-ttu-id="ddca3-107">Público-alvo</span><span class="sxs-lookup"><span data-stu-id="ddca3-107">Target audience</span></span>

<span data-ttu-id="ddca3-108">Neste tópico, você saberá como configurar a subcontratação de fabricação.</span><span class="sxs-lookup"><span data-stu-id="ddca3-108">In this topic, you will learn how to set up subcontracting in manufacturing.</span></span> <span data-ttu-id="ddca3-109">Você usará os dados existentes na entidade legal de HQUS para fazer a configuração básica de um fluxo de atividade a subcontratação.</span><span class="sxs-lookup"><span data-stu-id="ddca3-109">You will use existing data in the HQUS legal entity to do the basic setup of a subcontracting activity flow.</span></span> <span data-ttu-id="ddca3-110">Os dados de demonstração na entidade legal de HQUS incluem os parâmetros de configuração que foram predefinidos para oferecer suporte nas etapas do passo a passo.</span><span class="sxs-lookup"><span data-stu-id="ddca3-110">The demo data in the HQUS legal entity includes setup parameters that have been preset to support the steps in the walkthrough.</span></span> <span data-ttu-id="ddca3-111">Embora o passo a passo aborde problemas encontrados e desafios importantes para várias funções, ele podem ser concluído pelo administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="ddca3-111">Even though the walkthrough addresses key pain points and challenges for various roles, it can be completed by the system admin.</span></span>

## <a name="demo-scenario"></a><span data-ttu-id="ddca3-112">Cenário de demonstração</span><span class="sxs-lookup"><span data-stu-id="ddca3-112">Demo scenario</span></span>

<span data-ttu-id="ddca3-113">Na entidade legal de HQUS, fabrica-se alto-falantes.</span><span class="sxs-lookup"><span data-stu-id="ddca3-113">In the HQUS legal entity, high-end speakers are manufactured.</span></span> <span data-ttu-id="ddca3-114">Durante o processo de fabricação, os alto-falantes passam pelas três operações a seguir.</span><span class="sxs-lookup"><span data-stu-id="ddca3-114">During the manufacturing process, speakers go through the following three operations.</span></span>

- <span data-ttu-id="ddca3-115">**Pré-montagem** – O gabinete do alto-falante é montado.</span><span class="sxs-lookup"><span data-stu-id="ddca3-115">**Pre-assembly** – The speaker cabinet is assembled.</span></span> <span data-ttu-id="ddca3-116">O material para o gabinete é escolhido no depósito de material antes da operação ser iniciada.</span><span class="sxs-lookup"><span data-stu-id="ddca3-116">The material for the cabinet is picked in the material warehouse before the operation is started.</span></span>
- <span data-ttu-id="ddca3-117">**Revestimento** – Após o gabinete do alto-falante ser montado, ele deve ser revestido.</span><span class="sxs-lookup"><span data-stu-id="ddca3-117">**Coating** – After the speaker cabinet has been assembled, it must be coated.</span></span> <span data-ttu-id="ddca3-118">Essa operação é concluída por um fornecedor (subcontratado).</span><span class="sxs-lookup"><span data-stu-id="ddca3-118">This operation is completed by a vendor (subcontractor).</span></span> <span data-ttu-id="ddca3-119">O gabinete do alto-falante montado anteriormente é enviado para o subcontratado de revestimento com dois materiais.</span><span class="sxs-lookup"><span data-stu-id="ddca3-119">The pre-assembled speaker cabinet is shipped to the coating subcontractor together with two materials.</span></span>
- <span data-ttu-id="ddca3-120">**Conclusão** – Após o gabinete do alto-falante montado anteriormente ser revestido pelo subcontratado, ele retorna à entidade legal de HQUS para que a montagem final do alto-falante possa ser concluída.</span><span class="sxs-lookup"><span data-stu-id="ddca3-120">**Finish** – After the pre-assembled speaker cabinet has been coated by the subcontractor, it's returned to the HQUS legal entity so that final assembly of the speaker can be completed.</span></span>

<span data-ttu-id="ddca3-121">A ilustração a seguir mostra as três operações e os materiais que elas consomem.</span><span class="sxs-lookup"><span data-stu-id="ddca3-121">The following illustration shows the three operations and the materials that they consume.</span></span>

![As operações de pré-montagem, revestimento e conclusão e os materiais que elas consomem](./media/subcontract01_operations-materials.png)

## <a name="setup"></a><span data-ttu-id="ddca3-123">Configurar</span><span class="sxs-lookup"><span data-stu-id="ddca3-123">Setup</span></span>

<span data-ttu-id="ddca3-124">Antes de começar o passo a passo, é necessário configurar os dados.</span><span class="sxs-lookup"><span data-stu-id="ddca3-124">Before you start the walkthrough, you must set up the data.</span></span>

### <a name="set-up-the-finished-product"></a><span data-ttu-id="ddca3-125">Instalar o produto finalizado</span><span class="sxs-lookup"><span data-stu-id="ddca3-125">Set up the finished product</span></span>

<span data-ttu-id="ddca3-126">Esse procedimento fornece orientações sobre a instalação do produto lançado D8100, “Gabinete revestido”.</span><span class="sxs-lookup"><span data-stu-id="ddca3-126">This procedure takes you through the setup of released product D8100, "Coated Cabinet."</span></span>

1. <span data-ttu-id="ddca3-127">Selecione **Gerenciamento de informações do produto \> Produtos \> Produtos liberados** para abrir a página **Detalhes do produto liberado** .</span><span class="sxs-lookup"><span data-stu-id="ddca3-127">Select **Product information management \> Products \> Released products** to open the **Released product details** page.</span></span>
2. <span data-ttu-id="ddca3-128">No campo de filtro rápido, insira **D8100** para encontrar o produto liberado existente.</span><span class="sxs-lookup"><span data-stu-id="ddca3-128">In the quick filter field, enter **D8100** to find the existing released product.</span></span>

    ![Para filtrar o produto liberado D8100 na página Detalhes do produto liberado](./media/subcontract02_filtering-released-products.png)

3. <span data-ttu-id="ddca3-130">No Painel de Ações, na guia **Engenheiro** , selecione **Roteiro** para abrir a página **Roteiro** .</span><span class="sxs-lookup"><span data-stu-id="ddca3-130">On the Action Pane, on the **Engineer** tab, select **Route** to open the **Route** page.</span></span>

    <span data-ttu-id="ddca3-131">A página **Roteiro** mostra as oito versões de roteiro para o produto liberado D8100.</span><span class="sxs-lookup"><span data-stu-id="ddca3-131">The **Route** page shows the eight route versions for released product D8100.</span></span> <span data-ttu-id="ddca3-132">As oito versões de roteiro são divididas em quatro roteiros no site 1 e site 5.</span><span class="sxs-lookup"><span data-stu-id="ddca3-132">The eight route versions are divided among four routes on site 1 and site 5.</span></span> <span data-ttu-id="ddca3-133">O roteiro 000400 é usado para avaliação de custo, o roteiro 00041 é usado quando a operação de revestimento é interna e roteiro 00042 é usado quando a operação de revestimento é externa.</span><span class="sxs-lookup"><span data-stu-id="ddca3-133">Route 000400 is used for costing, route 00041 is used when the Coating operation is an internal operation, and route 00042 is used when the Coating operation is an external operation.</span></span>

    ![Oito versões de roteiro na página Roteiro](./media/subcontract03_route-page.png)

4. <span data-ttu-id="ddca3-135">No painel superior, na grade **Versões** , selecione a versão de roteiro **00042** do site **5**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-135">In the upper pane, in the **Versions** grid, select route version **00042** for site **5**.</span></span>
5. <span data-ttu-id="ddca3-136">No painel inferior, na guia **Visão geral**, selecione a operação **20** (**Cbnt CtSc**) na grade.</span><span class="sxs-lookup"><span data-stu-id="ddca3-136">In the lower pane, on the **Overview** tab, select operation **20** (**Cbnt CtSc**) in the grid.</span></span>

    ![Operação 20 da versão de roteiro 00042 do site 5 selecionada](./media/subcontract04_route-version-operation.png)

6. <span data-ttu-id="ddca3-138">Selecione a guia **Geral**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-138">Select the **General** tab.</span></span>

    <span data-ttu-id="ddca3-139">Observe que o campo **Tipo de roteiro** está definido como **Fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-139">Notice that the field **Route type** field is set to **Vendor**.</span></span> <span data-ttu-id="ddca3-140">Esse valor que indica que a operação 20 (Cbnt CtSc) é uma operação subcontratada.</span><span class="sxs-lookup"><span data-stu-id="ddca3-140">This value indicates that operation 20 (Cbnt CtSc) is a subcontracted operation.</span></span>

    ![Campo Tipo de roteiro definido como Fornecedor na guia Geral](./media/subcontract05_general-tab.png)

7. <span data-ttu-id="ddca3-142">Selecione a guia **Requisitos de recursos**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-142">Select the **Resource requirements** tab.</span></span>

    <span data-ttu-id="ddca3-143">Os recursos serão usados para encontrar um recurso aplicável durante o agendamento de produção.</span><span class="sxs-lookup"><span data-stu-id="ddca3-143">Capabilities will be used to find an applicable resource during production scheduling.</span></span> <span data-ttu-id="ddca3-144">Para a operação 20 (Cbnt CtSc), observe que é necessário um recurso que tenha dois recursos, **Revestimento** e **Gabinetes revestidos**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-144">For operation 20 (Cbnt CtSc), notice that a resource that has two capabilities, **Coating** and **Coated cabinets**, is required.</span></span>

    ![Recursos de revestimento e gabinetes revestidos na guia de requisitos de recursos](./media/subcontract06_resource-requirements-tab.png)

8. <span data-ttu-id="ddca3-146">Selecione **Recursos aplicáveis** para abrir a caixa de diálogo **Recursos aplicáveis**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-146">Select **Applicable resources** to open the **Applicable resources** dialog box.</span></span>

    <span data-ttu-id="ddca3-147">Foram encontrados três recursos que correspondem aos requisitos de recursos para a operação.</span><span class="sxs-lookup"><span data-stu-id="ddca3-147">Three resources are found that match the resource requirements for the operation.</span></span> <span data-ttu-id="ddca3-148">Observe que os recursos 8851 e 8852 são do tipo **Fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-148">Notice that resources 8851 and 8852 are of the **Vendor** type.</span></span>

    ![Três recursos adequados na caixa de diálogo Recursos aplicáveis](./media/subcontract07_applicable-resources-dialog.png)

9. <span data-ttu-id="ddca3-150">Selecione **OK** para fechar a caixa de diálogo **Recursos aplicáveis** e retornar à página **Roteiro**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-150">Select **OK** to close the **Applicable resources** dialog box and return to the **Route** page.</span></span>
10. <span data-ttu-id="ddca3-151">Fecha a página **Roteiro** para retornar à página **Detalhes do produto liberado** .</span><span class="sxs-lookup"><span data-stu-id="ddca3-151">Close the **Route** page to return to the **Released product details** page.</span></span>

    ![Página Detalhes do produto liberado](./media/subcontract08_released-product-details-page.png)

11. <span data-ttu-id="ddca3-153">No Painel de Ações, na guia **Engenheiro** , selecione **Versões de BOM** para abrir a página **Versões de BOM**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-153">On the Action Pane, on the **Engineer** tab, select **BOM versions** to open the **BOM versions** page.</span></span>

    <span data-ttu-id="ddca3-154">A página **Versões de BOM** mostra as quatro versões da lista de materiais (BOM) do produto liberado D8100.</span><span class="sxs-lookup"><span data-stu-id="ddca3-154">The **BOM versions** page shows the four bill of materials (BOM) versions for released product D8100.</span></span> <span data-ttu-id="ddca3-155">A BOM 000040 é usada para avaliação de custo e planejamento, a BOM 000041 é usada se a operação de revestimento é interna, e as BOMs 000042 e 000043 são usadas se a operação de revestimento é subcontratada.</span><span class="sxs-lookup"><span data-stu-id="ddca3-155">BOM 000040 is used for costing and planning, BOM 000041 is used if the Coating operation is done in-house, and BOMs 000042 and 000043 are used if the Coating operation is subcontracted.</span></span>

    <span data-ttu-id="ddca3-156">Observe que o item S8050 é um produto do tipo de item **Serviço**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-156">Notice that item S8050 is a product of the **Service** item type.</span></span> <span data-ttu-id="ddca3-157">Esse item representa o trabalho subcontratado.</span><span class="sxs-lookup"><span data-stu-id="ddca3-157">This item represents the subcontracted work.</span></span>

    ![Quatro versões de BOM na página Versões de BOM](./media/subcontract09_bom-versions-page.png)

12. <span data-ttu-id="ddca3-159">Na FastTab **Linhas da lista de materiais**, selecione **Editar** para abrir a caixa de diálogo **Editar linha de BOM**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-159">On the **Bill of materials lines** FastTab, select **Edit** to open the **Edit BOM line** dialog box.</span></span>

    <span data-ttu-id="ddca3-160">Quando uma ordem de produção for criada e estimada para o produto liberado D8100, ordem de compra será gerada automaticamente para o item S8050.</span><span class="sxs-lookup"><span data-stu-id="ddca3-160">When a production order is created and estimated for released product D8100, a purchase order will be automatically generated for item S8050.</span></span> <span data-ttu-id="ddca3-161">Essa ordem de compra será vinculada à ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="ddca3-161">This purchase order will be linked to the production order.</span></span> <span data-ttu-id="ddca3-162">Para que as ordens de compra sejam geradas automaticamente, o campo **Tipo de linha** deve ser definido como **Fornecedor**, e a conta do fornecedor para o subcontratado deve ser selecionada.</span><span class="sxs-lookup"><span data-stu-id="ddca3-162">For purchase orders to be automatically generated, the **Line type** field must be set to **Vendor**, and the vendor account for the subcontractor must be selected.</span></span> <span data-ttu-id="ddca3-163">Nesse caso, a conta do fornecedor é US-801.</span><span class="sxs-lookup"><span data-stu-id="ddca3-163">In this case, the vendor account is US-801.</span></span>

    <span data-ttu-id="ddca3-164">Observe que a linha de BOM está conectada à operação de revestimento por meio do número da operação (neste caso, 20).</span><span class="sxs-lookup"><span data-stu-id="ddca3-164">Notice that the BOM line is connected to the Coating operation through the operation number (in this case, 20).</span></span>

    ![Editar caixa de diálogo Linha de BOM](./media/subcontract10_edit-bom-line-dialog.png)

### <a name="create-a-password-for-warehouse-workers"></a><span data-ttu-id="ddca3-166">Criar uma senha para trabalhadores de depósito</span><span class="sxs-lookup"><span data-stu-id="ddca3-166">Create a password for warehouse workers</span></span>

<span data-ttu-id="ddca3-167">Você deve definir uma senha para os trabalhadores de depósito que usam o dispositivo portátil.</span><span class="sxs-lookup"><span data-stu-id="ddca3-167">You must define a password for the warehouse workers who use the hand-held device.</span></span>

1. <span data-ttu-id="ddca3-168">Selecione **Gerenciamento de depósito \> Configuração \> Trabalhador** para abrir a página **Usuários de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-168">Select **Warehouse management \> Setup \> Worker** to open the **Work users** page.</span></span>
2. <span data-ttu-id="ddca3-169">Na FastTab **Usuários**, selecione a linha do usuário **51**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-169">On the **Users** FastTab, select the row for user **51**.</span></span>

    ![Página Usuários de trabalho](./media/subcontract11_work-users-page.png)

3. <span data-ttu-id="ddca3-171">Selecione **Redefinir senha**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-171">Select **Reset password**.</span></span>
4. <span data-ttu-id="ddca3-172">Nos campos **Senha** e **Confirmar senha**, insira **1**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-172">In the **Password** and **Confirm password** fields, enter **1**.</span></span>
5. <span data-ttu-id="ddca3-173">Selecione **Definir senha**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-173">Select **Set password**.</span></span>

## <a name="step-by-step-walkthrough"></a><span data-ttu-id="ddca3-174">Orientação passo a passo</span><span class="sxs-lookup"><span data-stu-id="ddca3-174">Step-by-step walkthrough</span></span>

<span data-ttu-id="ddca3-175">**Cenário e plano de fundo**</span><span class="sxs-lookup"><span data-stu-id="ddca3-175">**Scenario and background**</span></span>

<span data-ttu-id="ddca3-176">Uma ordem de produção de 10 peças é criada para o produto D8100, “Gabinete revestido”.</span><span class="sxs-lookup"><span data-stu-id="ddca3-176">A production order of 10 pieces is created for product D8100, "Coated Cabinet."</span></span> <span data-ttu-id="ddca3-177">O revestimento dos gabinetes é uma operação subcontratada que é feita no fornecedor US-801, Perfect Coating Solutions.</span><span class="sxs-lookup"><span data-stu-id="ddca3-177">The coating of the cabinets is a sub-contracted operation that is done at vendor US-801, Perfect Coating Solutions.</span></span> <span data-ttu-id="ddca3-178">A ordem de produção consiste em três operações.</span><span class="sxs-lookup"><span data-stu-id="ddca3-178">The production order consists of three operations.</span></span> <span data-ttu-id="ddca3-179">Na primeira operação, o gabinete passa pela pré-montagem como uma operação interna.</span><span class="sxs-lookup"><span data-stu-id="ddca3-179">In the first operation, the cabinet is pre-assembled as an in-house operation.</span></span> <span data-ttu-id="ddca3-180">O material para a pré-montagem é liberado para coleta no depósito de matéria-prima.</span><span class="sxs-lookup"><span data-stu-id="ddca3-180">The material for the pre-assembly is released for picking in the raw material warehouse.</span></span> <span data-ttu-id="ddca3-181">Após a pré-montagem ser concluída, o gabinete pré-montado é enviado para a Perfect Coating Solutions com dois materiais necessários para a operação de revestimento.</span><span class="sxs-lookup"><span data-stu-id="ddca3-181">After the pre-assembly is completed, the pre-assembled cabinet is sent to Perfect Coating Solutions together with two materials that are required for the Coating operation.</span></span> <span data-ttu-id="ddca3-182">Quando o gabinete revestido é recebido de volta do fornecedor, ele passa pela montagem interna final para que possa ser relatado como finalizado.</span><span class="sxs-lookup"><span data-stu-id="ddca3-182">When the coated cabinet is received back from the vendor, it goes through a final in-house assembly operation before it's reported as finished.</span></span>

1. <span data-ttu-id="ddca3-183">Selecione **Controle de produção \> Ordens de produção \> Todas as ordens de produção** para abrir a página **Todas as ordens de produção**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-183">Select **Production control \> Production orders \> All production orders** to open the **All production orders** page.</span></span>
2. <span data-ttu-id="ddca3-184">No Painel de Ações, selecione **Nova ordem de produção** para abrir a caixa de diálogo **Criar ordem de produção**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-184">On the Action Pane, select **New production order** to open the **Create production order** dialog box.</span></span>

    ![Caixa de diálogo Criar ordem de produção](./media/subcontract12_create-production-order-dialog.png)

3. <span data-ttu-id="ddca3-186">No campo **Número de item**, selecione **D8100**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-186">In the **Item number** field, select **D8100**.</span></span>
4. <span data-ttu-id="ddca3-187">Depois que você selecionar o número do item, os campos das dimensões do estoque serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="ddca3-187">After you select the item number, fields for the inventory dimensions appear.</span></span> <span data-ttu-id="ddca3-188">No campo **Cor**, selecione **Cromado**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-188">In the **Color** field, select **Chrome**.</span></span>

    <span data-ttu-id="ddca3-189">Uma caixa de mensagem é exibida para perguntar se versões ativas da BOM e do roteiro devem ser inseridas.</span><span class="sxs-lookup"><span data-stu-id="ddca3-189">A message box appears that asks whether the active versions for the BOM and route should be inserted.</span></span>

    ![Caixa de mensagem](./media/subcontract13_message-box.png)

5. <span data-ttu-id="ddca3-191">Selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-191">Select **Yes**.</span></span> 

    <span data-ttu-id="ddca3-192">Na caixa de diálogo **Criar ordem de produção**, as versões ativas da BOM e do roteiro para o produto D8100 são selecionadas automaticamente nos campos **Número de BOM** e **Número de roteiro**, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="ddca3-192">In the **Create production order** dialog box, the active versions of the BOM and route for product D8100 are automatically selected in the **BOM number** and **Route number** fields, respectively.</span></span> <span data-ttu-id="ddca3-193">Nesse caso, a BOM **000040** e o roteiro **000040** são selecionados.</span><span class="sxs-lookup"><span data-stu-id="ddca3-193">In this case, BOM **000040** and route **000040** are selected.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ddca3-194">Para a BOM e o roteiro, a versão 000040 é usada para avaliação de custo e planejamento.</span><span class="sxs-lookup"><span data-stu-id="ddca3-194">For both the BOM and the route, version 000040 is used for costing and planning.</span></span>

6. <span data-ttu-id="ddca3-195">No campo **Local**, selecione **5**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-195">In the **Site** field, select **5**.</span></span>
7. <span data-ttu-id="ddca3-196">No campo **Depósito**, selecione **51**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-196">In the **Warehouse** field, select **51**.</span></span>
8. <span data-ttu-id="ddca3-197">Nos campos **Número de BOM** e **Número de roteiro** , altere o valor selecionado automaticamente para **000042**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-197">In the **BOM number** and **Route number** fields, change the value that was automatically selected to **000042**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ddca3-198">Para a BOM e o roteiro, a versão 000042 é usada para subcontratar o revestimento do gabinete para o fornecedor US-801.</span><span class="sxs-lookup"><span data-stu-id="ddca3-198">For both the BOM and the route, version 000042 is used to subcontract the coating of the cabinet to vendor US-801.</span></span>

    ![Valores definidos na caixa de diálogo Criar ordem de produção](./media/subcontract14_create-production-order-dialog-set.png)

9. <span data-ttu-id="ddca3-200">Selecione **Criar** para criar a ordem de produção e retornar à página **Todas as ordens de produção**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-200">Select **Create** to create the production order and return to the **All production orders** page.</span></span>

    ![Nova ordem de produção na página Todas as ordens de produção](./media/subcontract15_new-production-order.png)

10. <span data-ttu-id="ddca3-202">No Painel de Ações, na guia **Ordem de produção**, selecione **Estimativa** para abrir a caixa de diálogo **Estimativa**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-202">On the Action Pane, on the **Production order** tab, select **Estimate** to open the **Estimate** dialog box.</span></span>

    ![Caixa de diálogo Estimativa](./media/subcontract16_estimate-dialog.png)

11. <span data-ttu-id="ddca3-204">Selecione **OK** para criar a estimativa e retornar à página **Todas as ordens de produção**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-204">Select **OK** to confirm the estimate and return to the **All production orders** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ddca3-205">Quando a ordem de produção é estimada, a ordem de compra para o item de serviço S8050 é gerada para o fornecedor US-801.</span><span class="sxs-lookup"><span data-stu-id="ddca3-205">When the production order is estimated, the purchase order for service item S8050 is generated for vendor US-801.</span></span>

12. <span data-ttu-id="ddca3-206">No Painel de Ações, na guia **Ordem de produção** , selecione **BOM** para abrir a página **BOM** , que exibe as linhas de BOM para a ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="ddca3-206">On the Action Pane, on the **Production order** tab, select **BOM** to open the **BOM** page, where you can view the BOM lines for the production order.</span></span>

    <span data-ttu-id="ddca3-207">Para o item de serviço S8050, observe há uma referência à ordem de compra que foi gerada quando a ordem de produção foi estimada.</span><span class="sxs-lookup"><span data-stu-id="ddca3-207">For service item S8050, notice that there is a reference to the purchase order that was generated when the production order was estimated.</span></span>

    ![Linhas de BOM da ordem de produção na página BOM](./media/subcontract17_production-order-bom-lines.png)

13. <span data-ttu-id="ddca3-209">Feche a página **BOM** para retornar à página **Todas as ordens de produção**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-209">Close the **BOM** page to return to the **All production orders** page.</span></span>
14. <span data-ttu-id="ddca3-210">No Painel de Ações, na guia **Agenda**, selecione **Agendar trabalhos** para abrir a caixa de diálogo **Agendamento de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-210">On the Action Pane, on the **Schedule** tab, select **Schedule jobs** to open the **Job scheduling** dialog box.</span></span>
15. <span data-ttu-id="ddca3-211">Especifique os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="ddca3-211">Specify the following values:</span></span>

    - <span data-ttu-id="ddca3-212">No campo **Direção do agendamento**, selecione **Avançar a partir de amanhã**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-212">In the **Scheduling direction** field, select **Forward from tomorrow**.</span></span>
    - <span data-ttu-id="ddca3-213">Defina a opção **Capacidade finita** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-213">Set the **Finite capacity** option to **Yes**.</span></span>

    ![Caixa de diálogo Agendamento de trabalho](./media/subcontract18_job-scheduling-dialog.png)

16. <span data-ttu-id="ddca3-215">Selecione **OK** para fechar a caixa de diálogo **Agendamento de trabalho** e retornar à página **Todas as ordens de produção**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-215">Select **OK** to close the **Job scheduling** dialog box and return to the **All production orders** page.</span></span>
17. <span data-ttu-id="ddca3-216">No Painel de Ações, na guia **Agendar** , selecione **Gantt** para abrir a página **Gráfico de Gantt - visão de recurso**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-216">On the Action Pane, on the **Schedule** tab, select **Gantt** to open the **Gantt chart - Resource view** page.</span></span>

    <span data-ttu-id="ddca3-217">O gráfico de Gantt fornece uma visão geral de como os trabalhos de produção estão agendados nos recursos.</span><span class="sxs-lookup"><span data-stu-id="ddca3-217">The Gantt chart provides a visual overview of how the production jobs are scheduled on the resources.</span></span> <span data-ttu-id="ddca3-218">Observe que a operação externa de revestimento consiste em três trabalhos: um trabalho de processo, o trabalho de transporte e um trabalho de tempo de espera.</span><span class="sxs-lookup"><span data-stu-id="ddca3-218">Notice that the external Coating operation consists of three jobs: a process job, a transport job, and a queue time job.</span></span>

    ![Gráfico de Gantt na página Gráfico de Gantt - visão de recurso](./media/subcontract19_gantt-chart.png)

18. <span data-ttu-id="ddca3-220">Feche a página **Gráfico de Gantt - visão de recurso** para retornar à página **Todas as ordens de produção**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-220">Close the **Gantt chart - Resource view** page to return to the **All production orders** page.</span></span>
19. <span data-ttu-id="ddca3-221">No Painel de Ações, na guia **Ordem de produção**, selecione **Liberação** para abrir a caixa de diálogo **Liberação**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-221">On the Action Pane, on the **Production order** tab, select **Release** to open the **Release** dialog box.</span></span>

    ![Caixa de diálogo Liberação](./media/subcontract20_release-dialog.png)

20. <span data-ttu-id="ddca3-223">Selecione **OK** para fechar a caixa de diálogo **Liberação**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-223">Select **OK** to close the **Release** dialog box.</span></span>
21. <span data-ttu-id="ddca3-224">Selecione **Controle de produção \> Tarefas periódicas \> Liberar para depósito \> Liberação automática de linhas de BOM e fórmula** para abrir a caixa de diálogo **Liberação automática de linhas de BOM e fórmula** .</span><span class="sxs-lookup"><span data-stu-id="ddca3-224">Select **Production control \> Periodic tasks \> Release to warehouse \> Automatic release of BOM and formula lines** to open the **Automatic release of BOM and formula lines** dialog box.</span></span>

    ![Caixa de diálogo Liberação automática de linhas de BOM e fórmula](./media/subcontract21_auto-release-bom-formula-lines-dialog.png)

22. <span data-ttu-id="ddca3-226">Selecione **OK** para executar a liberação automática do trabalho das linhas BOM e fórmula.</span><span class="sxs-lookup"><span data-stu-id="ddca3-226">Select **OK** to run the Automatic release of BOM and formula lines job.</span></span>

    <span data-ttu-id="ddca3-227">Esse trabalho libera o trabalho de separação de matérias-primas para o depósito.</span><span class="sxs-lookup"><span data-stu-id="ddca3-227">This job releases pick work for raw materials to the warehouse.</span></span>

23. <span data-ttu-id="ddca3-228">Selecione **Controle de produção \> Ordens de produção \> Todas as ordens de produção** para abrir a página **Todas as ordens de produção**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-228">Select **Production control \> Production orders \> All production orders** to open the **All production orders** page.</span></span>
24. <span data-ttu-id="ddca3-229">Use o campo de filtro rápido para selecionar a ordem de produção em que você trabalhou.</span><span class="sxs-lookup"><span data-stu-id="ddca3-229">Use the quick filter field to select the production order that you've been working on.</span></span>
25. <span data-ttu-id="ddca3-230">No Painel de Ações, na guia **Depósito** , selecione **Detalhes do trabalho** para abrir a página **Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-230">On the Action Pane, on the **Warehouse** tab, select **Work details** to open the **Work** page.</span></span>

    <span data-ttu-id="ddca3-231">Observe que a página mostra dois conjuntos de trabalho para a separação de matéria-prima.</span><span class="sxs-lookup"><span data-stu-id="ddca3-231">Notice that the page shows two sets of work for raw material picking.</span></span> <span data-ttu-id="ddca3-232">O primeiro trabalho é para os materiais M8100 e M8101.</span><span class="sxs-lookup"><span data-stu-id="ddca3-232">The first work is for materials M8100 and M8101.</span></span> <span data-ttu-id="ddca3-233">Esses materiais são consumidos pela operação 10.</span><span class="sxs-lookup"><span data-stu-id="ddca3-233">These materials are consumed by operation 10.</span></span> <span data-ttu-id="ddca3-234">O segundo trabalho é para os materiais M8202 e M8250.</span><span class="sxs-lookup"><span data-stu-id="ddca3-234">The second work is for materials M8202 and M8250.</span></span> <span data-ttu-id="ddca3-235">Esses materiais são consumidos pela operação 20, que é subcontratada.</span><span class="sxs-lookup"><span data-stu-id="ddca3-235">These materials are consumed by operation 20, which is the subcontracted operation.</span></span>

    ![Dois conjuntos de trabalho para a separação de matéria-prima na página Trabalho.](./media/subcontract22_work-page.png)

26. <span data-ttu-id="ddca3-237">Inicie o aplicativo de depósito para processar o trabalho de depósito para a operação 10.</span><span class="sxs-lookup"><span data-stu-id="ddca3-237">Start the warehouse app to process the warehouse work for operation 10.</span></span>

    <!-- TBD – screen shots for processing pick work for the materials. -->

27. <span data-ttu-id="ddca3-238">Selecione **Controle de produção \> Ordens de produção \> Todas as ordens de produção** para abrir a página **Todas as ordens de produção**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-238">Select **Production control \> Production orders \> All production orders** to open the **All production orders** page.</span></span>
28. <span data-ttu-id="ddca3-239">Use o campo de filtro rápido para selecionar a ordem de produção em que você trabalhou.</span><span class="sxs-lookup"><span data-stu-id="ddca3-239">Use the quick filter field to select the production order that you've been working on.</span></span>
29. <span data-ttu-id="ddca3-240">No Painel de Ações, na guia **Ordem de produção**, selecione **Início** para abrir a caixa de diálogo **Início**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-240">On the Action Pane, on the **Production order** tab, select **Start** to open the **Start** dialog box.</span></span>
30. <span data-ttu-id="ddca3-241">Na guia **Geral**, especifique os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="ddca3-241">On the **General** tab, specify the following values:</span></span>

    - <span data-ttu-id="ddca3-242">No campo **Da Oper. N°**,</span><span class="sxs-lookup"><span data-stu-id="ddca3-242">In the **From Oper. No.**</span></span> <span data-ttu-id="ddca3-243">selecione **10**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-243">field, select **10**.</span></span>
    - <span data-ttu-id="ddca3-244">No campo **Para Oper. N°**,</span><span class="sxs-lookup"><span data-stu-id="ddca3-244">In the **To Oper. No.**</span></span> <span data-ttu-id="ddca3-245">selecione **10**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-245">field, select **10**.</span></span>

    ![Valores definidos na guia Geral](./media/subcontract23_start-dialog.png)

31. <span data-ttu-id="ddca3-247">Selecione **OK** para fechar a caixa de diálogo **Início** e retornar à página **Todas as ordens de produção**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-247">Select **OK** to close the **Start** dialog box and return to the **All production orders** page.</span></span>

    <span data-ttu-id="ddca3-248">Observe que o status da ordem de produção agora é **Iniciado**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-248">Notice that the status of the production order is now **Started**.</span></span> <span data-ttu-id="ddca3-249">Os materiais para a operação 10 são consumidos por um lançamento automático do diário de listas de separação.</span><span class="sxs-lookup"><span data-stu-id="ddca3-249">The materials for operation 10 are consumed by an automatic posting of the picking list journal.</span></span> <span data-ttu-id="ddca3-250">O consumo de tempo para a operação 10 é contabilizado por um lançamento automático de um diário de cartão de roteiro.</span><span class="sxs-lookup"><span data-stu-id="ddca3-250">Time consumption for operation 10 is accounted for by an automatic posting of a route card journal.</span></span>

32. <span data-ttu-id="ddca3-251">Inicie o aplicativo de depósito para processar o trabalho de depósito para a operação 20.</span><span class="sxs-lookup"><span data-stu-id="ddca3-251">Start the warehouse app to process the warehouse work for operation 20.</span></span>

    <!-- TBD – screen shots for processing pick work for the materials. -->

33. <span data-ttu-id="ddca3-252">No Painel de Ações, na guia **Ordem de produção**, selecione **Início** para abrir a caixa de diálogo **Início**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-252">On the Action Pane, on the **Production order** tab, select **Start** to open the **Start** dialog box.</span></span>
34. <span data-ttu-id="ddca3-253">Na guia **Geral**, especifique os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="ddca3-253">On the **General** tab, specify the following values:</span></span>

    - <span data-ttu-id="ddca3-254">No campo **Da Oper. N°**,</span><span class="sxs-lookup"><span data-stu-id="ddca3-254">In the **From Oper. No.**</span></span> <span data-ttu-id="ddca3-255">selecione **20**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-255">field, select **20**.</span></span>
    - <span data-ttu-id="ddca3-256">No campo **Para Oper. N°**,</span><span class="sxs-lookup"><span data-stu-id="ddca3-256">In the **To Oper. No.**</span></span> <span data-ttu-id="ddca3-257">selecione **20**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-257">field, select **20**.</span></span>
    - <span data-ttu-id="ddca3-258">No campo **Quantidade**, insira **10**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-258">In the **Quantity** field, enter **10**.</span></span>
    - <span data-ttu-id="ddca3-259">Defina a opção **Lançar lista de separação agora** como **Não**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-259">Set the **Post picking list now** option to **No**.</span></span>

    ![Valores definidos na guia Geral](./media/subcontract24_general-tab.png)

35. <span data-ttu-id="ddca3-261">Selecione **OK** para fechar a caixa de diálogo **Início** e retornar à página **Todas as ordens de produção**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-261">Select **OK** to close the **Start** dialog box and return to the **All production orders** page.</span></span>

    <span data-ttu-id="ddca3-262">Uma lista de separação é criada para os materiais usados para a operação de revestimento e para o item de serviço.</span><span class="sxs-lookup"><span data-stu-id="ddca3-262">A picking list is created for the materials that are used for the Coating operation, and for the service item.</span></span> <span data-ttu-id="ddca3-263">O item de serviço representa o custo da operação subcontratada.</span><span class="sxs-lookup"><span data-stu-id="ddca3-263">The service item represents the cost of the subcontracted operation.</span></span>

36. <span data-ttu-id="ddca3-264">No Painel de Ações, na guia **Exibir** , selecione **Lista de separação** para abrir a página **Lista de separação**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-264">On the Action Pane, on the **View** tab, select **Picking list** to open the **Picking list** page.</span></span>
37. <span data-ttu-id="ddca3-265">Selecione a lista de separação que não foi lançada e, em seguida, selecione o número do diário para exibir as linhas do diário.</span><span class="sxs-lookup"><span data-stu-id="ddca3-265">Select the picking list that isn't posted, and then select the journal number to view the journal lines.</span></span>

    ![Linhas do diário na página Lista de separação](./media/subcontract25_picking-list.png)

38. <span data-ttu-id="ddca3-267">No Painel de Ações, selecione **Imprimir** \> **Relatório de lista de separação** para abrir a caixa de diálogo **Relatório de lista de separação** .</span><span class="sxs-lookup"><span data-stu-id="ddca3-267">On the Action Pane, select **Print** \> **Picking list report** to open the **Picking list report** dialog box.</span></span>
39. <span data-ttu-id="ddca3-268">Defina a opção **Usar layout da nota de entrega** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-268">Set the **Use delivery note layout** option to **Yes**.</span></span>

    ![Caixa de diálogo Relatório de lista de separação](./media/subcontract26_picking-list-report-dialog.png)

40. <span data-ttu-id="ddca3-270">Selecione **OK** para gerar um relatório de **Lista de separação**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-270">Select **OK** to generate a **Picking list** report.</span></span>

    <span data-ttu-id="ddca3-271">Nesse caso, uma nota de entrega do fornecedor será impressa do diário de listas de separação de produção.</span><span class="sxs-lookup"><span data-stu-id="ddca3-271">In this case, a vendor delivery note is printed from the production picking list journal.</span></span> <span data-ttu-id="ddca3-272">A nota de entrega especifica os materiais enviados para fornecedor que realizará a operação de revestimento.</span><span class="sxs-lookup"><span data-stu-id="ddca3-272">The delivery note specifies the materials that are shipped to the vendor who will do the Coating operation.</span></span>

    ![Relatório de lista de separação](./media/subcontract27_picking-list-report.png)

41. <span data-ttu-id="ddca3-274">Feche o relatório de **Lista de separação** para retornar à **Lista de separação**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-274">Close the **Picking list** report to return to the **Picking list** page.</span></span>
42. <span data-ttu-id="ddca3-275">No Painel de Ações, selecione **Lançar** para abrir a caixa de diálogo **Diário de lançamentos**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-275">On the Action Pane, select **Post** to open the **Post journal** dialog box.</span></span>

    ![Caixa de diálogo Diário de lançamentos](./media/subcontract28_post-journal-dialog.png)

43. <span data-ttu-id="ddca3-277">Selecione **OK** para fechar a caixa de diálogo **Diário de lançamentos**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-277">Select **OK** to close the **Post journal** dialog box.</span></span>
44. <span data-ttu-id="ddca3-278">Abra a ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="ddca3-278">Open the purchase order.</span></span>

    ![Página Ordem de compra](./media/subcontract29_purchase-order-page.png)

45. <span data-ttu-id="ddca3-280">No Painel de Ações, na guia **Compra**, selecione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-280">On the Action Pane, on the **Purchase** tab, select **Confirm**.</span></span>
46. <span data-ttu-id="ddca3-281">Selecione **Lançar** para abrir a caixa de diálogo **Diário de lançamentos**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-281">Select **Post** to open the **Post journal** dialog box.</span></span>
47. <span data-ttu-id="ddca3-282">Selecione **OK** para fechar a caixa de diálogo **Diário de lançamentos** e retornar à página **Ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-282">Select **OK** to close the **Post journal** dialog box and return to the **Purchase order** page.</span></span>
48. <span data-ttu-id="ddca3-283">Altere o preço unitário de **33** para **40**.</span><span class="sxs-lookup"><span data-stu-id="ddca3-283">Change the unit price from **33** to **40**.</span></span>

    ![Preço unitário alterado na página Ordem de compra](./media/subcontract30_unit-price.png)

49. <span data-ttu-id="ddca3-285">Confirme a ordem de compra novamente.</span><span class="sxs-lookup"><span data-stu-id="ddca3-285">Confirm the purchase order again.</span></span>
50. <span data-ttu-id="ddca3-286">Recebimento de produtos.</span><span class="sxs-lookup"><span data-stu-id="ddca3-286">Product receipt.</span></span>

    ![Caixa de diálogo Lançamento de recebimento de produtos](./media/subcontract31_posting-product-receipt-dialog.png)

51. <span data-ttu-id="ddca3-288">Fatura de compra.</span><span class="sxs-lookup"><span data-stu-id="ddca3-288">Purchase invoice.</span></span>
52. <span data-ttu-id="ddca3-289">Atualizar o status de conciliação.</span><span class="sxs-lookup"><span data-stu-id="ddca3-289">Update the match status.</span></span>

    ![Página Fatura de fornecedor](./media/subcontract32_vendor-invoice-page.png)

53. <span data-ttu-id="ddca3-291">Relatar como concluído.</span><span class="sxs-lookup"><span data-stu-id="ddca3-291">Report as finished.</span></span>

    ![Caixa de diálogo Relatar como concluído](./media/subcontract33_report-as-finished-dialog.png)

54. <span data-ttu-id="ddca3-293">Finalizar.</span><span class="sxs-lookup"><span data-stu-id="ddca3-293">End.</span></span>

    ![Caixa de diálogo Finalizar](./media/subcontract34_end-dialog.png)

55. <span data-ttu-id="ddca3-295">Comparação de custo.</span><span class="sxs-lookup"><span data-stu-id="ddca3-295">Cost comparison.</span></span>

    ![Gráficos de comparação de custo](./media/subcontract35_cost-comparison-charts.png)

<span data-ttu-id="ddca3-297">Não há configuração nos dados.</span><span class="sxs-lookup"><span data-stu-id="ddca3-297">Missing setup in data.</span></span>
