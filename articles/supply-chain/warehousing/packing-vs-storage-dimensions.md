---
title: Definir dimensões diferentes para embalagem e armazenamento
description: Este tópico mostra como especificar para qual processo (embalagem, armazenamento ou embalagem aninhada) cada dimensão especificada é usada.
author: mirzaab
manager: tfehr
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPhysDimUOM
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 004d9b4522335b481b640ef0fe35f4db66e3c9f5
ms.sourcegitcommit: b7a7a14f8650913f6797ae1c4a82ad8adfe415fd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/28/2021
ms.locfileid: "5078234"
---
# <a name="set-different-dimensions-for-packing-and-storage"></a><span data-ttu-id="59fa9-103">Definir dimensões diferentes para embalagem e armazenamento</span><span class="sxs-lookup"><span data-stu-id="59fa9-103">Set different dimensions for packing and storage</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="59fa9-104">Alguns itens são embalados ou armazenados de forma que pode ser necessário rastrear dimensões físicas de forma diferente para cada processo.</span><span class="sxs-lookup"><span data-stu-id="59fa9-104">Some items are packed or stored in such a way that you may need to track physical dimensions differently for each of several different processes.</span></span> <span data-ttu-id="59fa9-105">O recurso *Dimensões de produtos de embalagem* permite configurar um ou mais tipos de dimensões para cada produto.</span><span class="sxs-lookup"><span data-stu-id="59fa9-105">The *Packaging product dimensions* feature lets you set up one or several types of dimensions for each product.</span></span> <span data-ttu-id="59fa9-106">Cada tipo de dimensão oferece um conjunto de medidas físicas (peso, largura, profundidade e altura) e estabelece o processo em que esses valores de medida física se aplicam.</span><span class="sxs-lookup"><span data-stu-id="59fa9-106">Each dimension type provides a set of physical measurements (weight, width, depth, and height), and establishes the process where those physical measurement values apply.</span></span> <span data-ttu-id="59fa9-107">Quando este recurso é habilitado, o sistema oferecerá suporte aos seguintes tipos de dimensões:</span><span class="sxs-lookup"><span data-stu-id="59fa9-107">When this feature is enabled, your system will support the following types of dimensions:</span></span>

- <span data-ttu-id="59fa9-108">*Armazenamento* – as dimensões de armazenamento são usadas com a volumetria da localização para determinar a quantidade de cada item que pode ser armazenada em diferentes localizações de depósito.</span><span class="sxs-lookup"><span data-stu-id="59fa9-108">*Storage* - Storage dimensions are used along with location volumetrics to determine how many of each item can be stored in various warehouse locations.</span></span>
- <span data-ttu-id="59fa9-109">*Embalagem* – as dimensões de embalagem são usadas durante o transporte em contêineres e o processo de embalagem manual para determinar a quantidade de cada item que caberá nos diferentes tipos de contêiner.</span><span class="sxs-lookup"><span data-stu-id="59fa9-109">*Packing* - Packing dimensions are used during containerization and the manual packing process to determine how many of each item will fit in various container types.</span></span>
- <span data-ttu-id="59fa9-110">*Embalagem aninhada* – as dimensões de embalagem aninhada são usadas quando o processo de embalagem contiver vários níveis.</span><span class="sxs-lookup"><span data-stu-id="59fa9-110">*Nested packing* - Nested packing dimensions are used when the packing process contains multiple levels.</span></span>

<span data-ttu-id="59fa9-111">As dimensões de *armazenamento* são compatíveis mesmo quando o recurso *Dimensões de produtos de embalagem* não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="59fa9-111">*Storage* dimensions are supported even when the *Packaging product dimensions* feature isn't enabled.</span></span> <span data-ttu-id="59fa9-112">Configure-as usando a página **Dimensão física** no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="59fa9-112">You set these up using the **Physical dimension** page in Supply Chain Management.</span></span> <span data-ttu-id="59fa9-113">Essas dimensões são usadas por todos os processos nos quais as dimensões de embalagem e embalagem aninhada não são especificadas.</span><span class="sxs-lookup"><span data-stu-id="59fa9-113">These dimensions are used by all processes where the packing and nested packing dimensions aren't specified.</span></span>

<span data-ttu-id="59fa9-114">As dimensões de *embalagem* e *embalagem aninhada* são configuradas usando a página **Dimensões físicas do produto**, adicionada quando você habilita o recurso *Dimensões de produtos de embalagem*.</span><span class="sxs-lookup"><span data-stu-id="59fa9-114">*Packing* and *nested packing* dimensions are set up using the **Physical product dimensions** page, which is added when you enable the *Packaging product dimensions* feature.</span></span>
<span data-ttu-id="59fa9-115">Este tópico oferece um cenário que mostra como usar esse recurso.</span><span class="sxs-lookup"><span data-stu-id="59fa9-115">This topic provides a scenario that illustrates how to use this feature.</span></span>

## <a name="turn-on-the-packaging-product-dimensions-feature"></a><span data-ttu-id="59fa9-116">Ativar o recurso de dimensões de produtos de embalagem</span><span class="sxs-lookup"><span data-stu-id="59fa9-116">Turn on the packaging product dimensions feature</span></span>

<span data-ttu-id="59fa9-117">Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="59fa9-117">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="59fa9-118">Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="59fa9-118">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="59fa9-119">Nesse caso, o recurso é listado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="59fa9-119">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="59fa9-120">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="59fa9-120">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="59fa9-121">**Nome do recurso:** *Dimensões de produtos de embalagem*</span><span class="sxs-lookup"><span data-stu-id="59fa9-121">**Feature name:** *Packaging product dimensions*</span></span>

## <a name="example-scenario"></a><span data-ttu-id="59fa9-122">Cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="59fa9-122">Example scenario</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="59fa9-123">Configurar o cenário</span><span class="sxs-lookup"><span data-stu-id="59fa9-123">Set up the scenario</span></span>

<span data-ttu-id="59fa9-124">Antes de executar o cenário de exemplo, prepare o sistema conforme descrito nesta seção.</span><span class="sxs-lookup"><span data-stu-id="59fa9-124">Before you can run the example scenario, you must prepare your system as described in this section.</span></span>

#### <a name="enable-demo-data"></a><span data-ttu-id="59fa9-125">Habilitar dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="59fa9-125">Enable demo data</span></span>

<span data-ttu-id="59fa9-126">Para trabalhar nesse cenário usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados.</span><span class="sxs-lookup"><span data-stu-id="59fa9-126">To work through this scenario using the demo records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="59fa9-127">Além disso, você deve selecionar a entidade legal *USMF* antes de começar.</span><span class="sxs-lookup"><span data-stu-id="59fa9-127">Additionally, you must select the *USMF* legal entity before you begin.</span></span>

#### <a name="add-a-new-physical-dimension-to-a-product"></a><span data-ttu-id="59fa9-128">Adicionar nova dimensão física a um produto</span><span class="sxs-lookup"><span data-stu-id="59fa9-128">Add a new physical dimension to a product</span></span>

<span data-ttu-id="59fa9-129">Adicione uma nova dimensão física a um produto da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="59fa9-129">Add a new physical dimension for a product by doing the following:</span></span>

1. <span data-ttu-id="59fa9-130">Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="59fa9-130">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="59fa9-131">Selecione o produto com **Número do item** *A0001*.</span><span class="sxs-lookup"><span data-stu-id="59fa9-131">Select the product with **Item number** *A0001*.</span></span>
1. <span data-ttu-id="59fa9-132">No Painel de Ação, abra a guia **Gerenciar estoque** e, no grupo **Depósito**, selecione **Dimensões físicas do produto**.</span><span class="sxs-lookup"><span data-stu-id="59fa9-132">On the Action Pane, open the **Manage inventory** tab and, from the **Warehouse** group, select **Physical product dimensions**.</span></span>
1. <span data-ttu-id="59fa9-133">A página **Dimensões físicas do produto** é aberta.</span><span class="sxs-lookup"><span data-stu-id="59fa9-133">The **Physical product dimensions** page opens.</span></span> <span data-ttu-id="59fa9-134">No Painel de Ações, selecione **Novo** para adicionar uma nova dimensão à grade com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="59fa9-134">On the Action Pane, select **New** to add a new dimension to the grid with the following settings:</span></span>
    - <span data-ttu-id="59fa9-135">**Tipo de dimensão física** - *Embalagem*</span><span class="sxs-lookup"><span data-stu-id="59fa9-135">**Physical dimension type** - *Packing*</span></span>
    - <span data-ttu-id="59fa9-136">**Unidade física** - *pçs*</span><span class="sxs-lookup"><span data-stu-id="59fa9-136">**Physical unit** - *pcs*</span></span>
    - <span data-ttu-id="59fa9-137">**Peso** - *4*</span><span class="sxs-lookup"><span data-stu-id="59fa9-137">**Weight** - *4*</span></span>
    - <span data-ttu-id="59fa9-138">**Unidade de peso** - *kg*</span><span class="sxs-lookup"><span data-stu-id="59fa9-138">**Weight unit** - *kg*</span></span>
    - <span data-ttu-id="59fa9-139">**Profundidade** - *3*</span><span class="sxs-lookup"><span data-stu-id="59fa9-139">**Depth** - *3*</span></span>
    - <span data-ttu-id="59fa9-140">**Altura** - *4*</span><span class="sxs-lookup"><span data-stu-id="59fa9-140">**Height** - *4*</span></span>
    - <span data-ttu-id="59fa9-141">**Largura** - *3*</span><span class="sxs-lookup"><span data-stu-id="59fa9-141">**Width** - *3*</span></span>
    - <span data-ttu-id="59fa9-142">**Comprimento** - *cm*</span><span class="sxs-lookup"><span data-stu-id="59fa9-142">**Length** - *cm*</span></span>
    - <span data-ttu-id="59fa9-143">**Unidade de volume** - *cm3*</span><span class="sxs-lookup"><span data-stu-id="59fa9-143">**Volume unit** - *cm3*</span></span>

<span data-ttu-id="59fa9-144">O campo **Volume** é calculado automaticamente com base nas configurações de **Profundidade**, **Altura** e **Largura**.</span><span class="sxs-lookup"><span data-stu-id="59fa9-144">The **Volume** field is automatically calculated based on your **Depth**, **Height**, and **Width** settings.</span></span>

#### <a name="create-a-new-container-type"></a><span data-ttu-id="59fa9-145">Criar um novo tipo de contêiner</span><span class="sxs-lookup"><span data-stu-id="59fa9-145">Create a new container type</span></span>

<span data-ttu-id="59fa9-146">Acesse **Gerenciamento de depósito \> Configuração \> Contêineres \> Tipos de contêiner** e crie um registro com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="59fa9-146">Go to **Warehouse management \> Setup \> Containers \> Container types** and create a new record with the following settings:</span></span>

- <span data-ttu-id="59fa9-147">**Código do tipo de contêiner** - *Caixa Baixa*</span><span class="sxs-lookup"><span data-stu-id="59fa9-147">**Container type code** - *Short Box*</span></span>
- <span data-ttu-id="59fa9-148">**Descrição** - *Caixa Baixa*</span><span class="sxs-lookup"><span data-stu-id="59fa9-148">**Description** - *Short Box*</span></span>
- <span data-ttu-id="59fa9-149">**Peso líquido máximo** - *50*</span><span class="sxs-lookup"><span data-stu-id="59fa9-149">**Maximum net weight** - *50*</span></span>
- <span data-ttu-id="59fa9-150">**Volume** - *144*</span><span class="sxs-lookup"><span data-stu-id="59fa9-150">**Volume** - *144*</span></span>
- <span data-ttu-id="59fa9-151">**Extensão** - *6*</span><span class="sxs-lookup"><span data-stu-id="59fa9-151">**Length** - *6*</span></span>
- <span data-ttu-id="59fa9-152">**Largura** - *6*</span><span class="sxs-lookup"><span data-stu-id="59fa9-152">**Width** - *6*</span></span>
- <span data-ttu-id="59fa9-153">**Altura** - *4*</span><span class="sxs-lookup"><span data-stu-id="59fa9-153">**Height** - *4*</span></span>

#### <a name="create-a-container-group"></a><span data-ttu-id="59fa9-154">Criar um grupo de contêineres</span><span class="sxs-lookup"><span data-stu-id="59fa9-154">Create a container group</span></span>

<span data-ttu-id="59fa9-155">Acesse **Gerenciamento de depósito \> Configuração \> Contêineres \> Grupos de contêineres** e crie um registro com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="59fa9-155">Go to **Warehouse management \> Setup \> Containers \> Container groups** and create a new record with the following settings:</span></span>

- <span data-ttu-id="59fa9-156">**ID do grupo de contêineres** - *Caixa Baixa*</span><span class="sxs-lookup"><span data-stu-id="59fa9-156">**Container group ID** - *Short Box*</span></span>
- <span data-ttu-id="59fa9-157">**Descrição** - *Caixa Baixa*</span><span class="sxs-lookup"><span data-stu-id="59fa9-157">**Description** - *Short Box*</span></span>

<span data-ttu-id="59fa9-158">Adicione uma nova linha à seção **Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="59fa9-158">Add a new line to the **Details** section.</span></span> <span data-ttu-id="59fa9-159">Defina o **Tipo de contêiner** como *Caixa Baixa*.</span><span class="sxs-lookup"><span data-stu-id="59fa9-159">Set the **Container type** to *Short Box*.</span></span>

#### <a name="set-up-a-container-build-template"></a><span data-ttu-id="59fa9-160">Configurar um modelo de criação de contêiner</span><span class="sxs-lookup"><span data-stu-id="59fa9-160">Set up a container build template</span></span>

<span data-ttu-id="59fa9-161">Acesse **Gerenciamento de depósito \> Configuração \> Contêineres \> Modelos de criação de contêiner** e selecione **Caixas**.</span><span class="sxs-lookup"><span data-stu-id="59fa9-161">Go to **Warehouse management \> Setup \> Containers \> Container build templates** and select **Boxes**.</span></span> <span data-ttu-id="59fa9-162">Altere a **ID do grupo de contêineres** como *Caixa Baixa*.</span><span class="sxs-lookup"><span data-stu-id="59fa9-162">Change the **Container group ID** to *Short Box*.</span></span>

### <a name="run-the-scenario"></a><span data-ttu-id="59fa9-163">Executar o cenário</span><span class="sxs-lookup"><span data-stu-id="59fa9-163">Run the scenario</span></span>

<span data-ttu-id="59fa9-164">Depois de preparar o sistema conforme descrito na seção anterior, você estará pronto para executar o cenário conforme descrito na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="59fa9-164">After you have prepared your system as described in the previous section, you are ready to run the scenario as described in the next section.</span></span>

#### <a name="create-a-sales-order-and-create-a-shipment"></a><span data-ttu-id="59fa9-165">Criar uma ordem de venda e uma remessa</span><span class="sxs-lookup"><span data-stu-id="59fa9-165">Create a sales order and create a shipment</span></span>

<span data-ttu-id="59fa9-166">Neste processo, você criará uma remessa com base nas dimensões de *embalagem* do item, para o qual a altura é inferior a 3.</span><span class="sxs-lookup"><span data-stu-id="59fa9-166">In this process you will create a shipment based on the item *packing* dimensions, for which the height is less than 3.</span></span>

1. <span data-ttu-id="59fa9-167">Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="59fa9-167">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="59fa9-168">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="59fa9-168">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="59fa9-169">Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="59fa9-169">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="59fa9-170">**Conta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="59fa9-170">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="59fa9-171">**Depósito:** *63*</span><span class="sxs-lookup"><span data-stu-id="59fa9-171">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="59fa9-172">Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="59fa9-172">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="59fa9-173">A nova ordem de venda é aberta.</span><span class="sxs-lookup"><span data-stu-id="59fa9-173">The new sales order is opened.</span></span> <span data-ttu-id="59fa9-174">Ele deve incluir uma nova linha vazia na grade da FastTab **Linhas de ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="59fa9-174">It should include a new, empty line in the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="59fa9-175">Nessa linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="59fa9-175">On this line, set the following values:</span></span>

    - <span data-ttu-id="59fa9-176">**Número de item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="59fa9-176">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="59fa9-177">**Quantidade:** *5*</span><span class="sxs-lookup"><span data-stu-id="59fa9-177">**Quantity:** *5*</span></span>

1. <span data-ttu-id="59fa9-178">Na FastTab **Linhas da ordem de venda**, selecione **Estoque \> Reserva**.</span><span class="sxs-lookup"><span data-stu-id="59fa9-178">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="59fa9-179">Na página **Reserva**, no Painel de Ação, selecione **Reservar lote** para reservar o estoque.</span><span class="sxs-lookup"><span data-stu-id="59fa9-179">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="59fa9-180">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="59fa9-180">Close the page.</span></span>
1. <span data-ttu-id="59fa9-181">No Painel de Ações, abra a guia **Depósito** e selecione **Liberar para depósito** para criar trabalho para o depósito.</span><span class="sxs-lookup"><span data-stu-id="59fa9-181">On the Action Pane, open the **Warehouse** tab and select **Release to warehouse** to create work for the warehouse.</span></span>
1. <span data-ttu-id="59fa9-182">Na FastTab **Linhas de ordem de venda**, selecione **Depósito \> Detalhes da remessa**.</span><span class="sxs-lookup"><span data-stu-id="59fa9-182">On the **Sales order lines** FastTab, select **Warehouse \> Shipment details**.</span></span>
1. <span data-ttu-id="59fa9-183">No painel de ações, abra a guia **Transporte** e selecione **Exibir contêineres**.</span><span class="sxs-lookup"><span data-stu-id="59fa9-183">On the Action Pane, open the **Transportation** tab and select **View containers**.</span></span> <span data-ttu-id="59fa9-184">Confirme se o item foi incluído nos dois contêineres *Caixa Baixa*.</span><span class="sxs-lookup"><span data-stu-id="59fa9-184">Confirm that the item was containerized into the two *Short Box* containers.</span></span>

#### <a name="place-an-item-into-storage"></a><span data-ttu-id="59fa9-185">Colocar um item no armazenamento</span><span class="sxs-lookup"><span data-stu-id="59fa9-185">Place an item into storage</span></span>

1. <span data-ttu-id="59fa9-186">Abra o dispositivo móvel para entrar no depósito 63 e acesse **Estoque \> Ajustar em**.</span><span class="sxs-lookup"><span data-stu-id="59fa9-186">Open the mobile device, sign in to warehouse 63 and go to **Inventory \> Adjust In**.</span></span>
1. <span data-ttu-id="59fa9-187">Insira **Loc** = *SHORT-01*.</span><span class="sxs-lookup"><span data-stu-id="59fa9-187">Enter **Loc** = *SHORT-01*.</span></span> <span data-ttu-id="59fa9-188">Crie uma placa de licença com **Item** = *A0001* e **Quantidade** = *1 pçs*.</span><span class="sxs-lookup"><span data-stu-id="59fa9-188">Make a new license plate with **Item** = *A0001* and **Quantity** = *1 pcs*.</span></span>
1. <span data-ttu-id="59fa9-189">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="59fa9-189">Select **OK**.</span></span> <span data-ttu-id="59fa9-190">Você receberá o erro "Falha no local SHORT-01 porque o item A0001 não cabe nas dimensões especificadas do local".</span><span class="sxs-lookup"><span data-stu-id="59fa9-190">You will receive the error "Location SHORT-01 failed because item A0001 does not fit in location's specified dimensions."</span></span> <span data-ttu-id="59fa9-191">Isso ocorre porque as dimensões do tipo de *Armazenamento* do produto são maiores que as dimensões especificadas no perfil de localização.</span><span class="sxs-lookup"><span data-stu-id="59fa9-191">This is because the *Storage* type dimensions of the product are larger than the dimensions specified on the location profile.</span></span>
