---
title: Definir dimensões diferentes para embalagem e armazenamento
description: Este tópico mostra como especificar para qual processo (embalagem, armazenamento ou embalagem aninhada) cada dimensão especificada é usada.
author: mirzaab
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResPhysicalProductDimensions, WHSPhysDimUOM
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: e997f8bccde7856303d8b3c6407143598ccc6030
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818911"
---
# <a name="set-different-dimensions-for-packing-and-storage"></a><span data-ttu-id="95be0-103">Definir dimensões diferentes para embalagem e armazenamento</span><span class="sxs-lookup"><span data-stu-id="95be0-103">Set different dimensions for packing and storage</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="95be0-104">Alguns itens são embalados ou armazenados de forma que pode ser necessário rastrear dimensões físicas de forma diferente para cada processo.</span><span class="sxs-lookup"><span data-stu-id="95be0-104">Some items are packed or stored in such a way that you may need to track physical dimensions differently for each of several different processes.</span></span> <span data-ttu-id="95be0-105">O recurso *Dimensões de produtos de embalagem* permite configurar um ou mais tipos de dimensões para cada produto.</span><span class="sxs-lookup"><span data-stu-id="95be0-105">The *Packaging product dimensions* feature lets you set up one or several types of dimensions for each product.</span></span> <span data-ttu-id="95be0-106">Cada tipo de dimensão oferece um conjunto de medidas físicas (peso, largura, profundidade e altura) e estabelece o processo em que esses valores de medida física se aplicam.</span><span class="sxs-lookup"><span data-stu-id="95be0-106">Each dimension type provides a set of physical measurements (weight, width, depth, and height), and establishes the process where those physical measurement values apply.</span></span> <span data-ttu-id="95be0-107">Quando este recurso é habilitado, o sistema oferecerá suporte aos seguintes tipos de dimensões:</span><span class="sxs-lookup"><span data-stu-id="95be0-107">When this feature is enabled, your system will support the following types of dimensions:</span></span>

- <span data-ttu-id="95be0-108">*Armazenamento* – as dimensões de armazenamento são usadas com a volumetria da localização para determinar a quantidade de cada item que pode ser armazenada em diferentes localizações de depósito.</span><span class="sxs-lookup"><span data-stu-id="95be0-108">*Storage* - Storage dimensions are used along with location volumetrics to determine how many of each item can be stored in various warehouse locations.</span></span>
- <span data-ttu-id="95be0-109">*Embalagem* – as dimensões de embalagem são usadas durante o transporte em contêineres e o processo de embalagem manual para determinar a quantidade de cada item que caberá nos diferentes tipos de contêiner.</span><span class="sxs-lookup"><span data-stu-id="95be0-109">*Packing* - Packing dimensions are used during containerization and the manual packing process to determine how many of each item will fit in various container types.</span></span>
- <span data-ttu-id="95be0-110">*Embalagem aninhada* – as dimensões de embalagem aninhada são usadas quando o processo de embalagem contiver vários níveis.</span><span class="sxs-lookup"><span data-stu-id="95be0-110">*Nested packing* - Nested packing dimensions are used when the packing process contains multiple levels.</span></span>

<span data-ttu-id="95be0-111">As dimensões de *armazenamento* são compatíveis mesmo quando o recurso *Dimensões de produtos de embalagem* não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="95be0-111">*Storage* dimensions are supported even when the *Packaging product dimensions* feature isn't enabled.</span></span> <span data-ttu-id="95be0-112">Configure-as usando a página **Dimensão física** no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="95be0-112">You set these up using the **Physical dimension** page in Supply Chain Management.</span></span> <span data-ttu-id="95be0-113">Essas dimensões são usadas por todos os processos nos quais as dimensões de embalagem e embalagem aninhada não são especificadas.</span><span class="sxs-lookup"><span data-stu-id="95be0-113">These dimensions are used by all processes where the packing and nested packing dimensions aren't specified.</span></span>

<span data-ttu-id="95be0-114">As dimensões de *embalagem* e *embalagem aninhada* são configuradas usando a página **Dimensões físicas do produto**, adicionada quando você habilita o recurso *Dimensões de produtos de embalagem*.</span><span class="sxs-lookup"><span data-stu-id="95be0-114">*Packing* and *nested packing* dimensions are set up using the **Physical product dimensions** page, which is added when you enable the *Packaging product dimensions* feature.</span></span>
<span data-ttu-id="95be0-115">Este tópico oferece um cenário que mostra como usar esse recurso.</span><span class="sxs-lookup"><span data-stu-id="95be0-115">This topic provides a scenario that illustrates how to use this feature.</span></span>

## <a name="turn-on-the-packaging-product-dimensions-feature"></a><span data-ttu-id="95be0-116">Ativar o recurso de dimensões de produtos de embalagem</span><span class="sxs-lookup"><span data-stu-id="95be0-116">Turn on the packaging product dimensions feature</span></span>

<span data-ttu-id="95be0-117">Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="95be0-117">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="95be0-118">Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="95be0-118">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="95be0-119">Nesse caso, o recurso é listado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="95be0-119">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="95be0-120">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="95be0-120">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="95be0-121">**Nome do recurso:** *Dimensões de produtos de embalagem*</span><span class="sxs-lookup"><span data-stu-id="95be0-121">**Feature name:** *Packaging product dimensions*</span></span>

## <a name="example-scenario"></a><span data-ttu-id="95be0-122">Cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="95be0-122">Example scenario</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="95be0-123">Configurar o cenário</span><span class="sxs-lookup"><span data-stu-id="95be0-123">Set up the scenario</span></span>

<span data-ttu-id="95be0-124">Antes de executar o cenário de exemplo, prepare o sistema conforme descrito nesta seção.</span><span class="sxs-lookup"><span data-stu-id="95be0-124">Before you can run the example scenario, you must prepare your system as described in this section.</span></span>

#### <a name="enable-demo-data"></a><span data-ttu-id="95be0-125">Habilitar dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="95be0-125">Enable demo data</span></span>

<span data-ttu-id="95be0-126">Para trabalhar nesse cenário usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados.</span><span class="sxs-lookup"><span data-stu-id="95be0-126">To work through this scenario using the demo records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="95be0-127">Além disso, você deve selecionar a entidade legal *USMF* antes de começar.</span><span class="sxs-lookup"><span data-stu-id="95be0-127">Additionally, you must select the *USMF* legal entity before you begin.</span></span>

#### <a name="add-a-new-physical-dimension-to-a-product"></a><span data-ttu-id="95be0-128">Adicionar nova dimensão física a um produto</span><span class="sxs-lookup"><span data-stu-id="95be0-128">Add a new physical dimension to a product</span></span>

<span data-ttu-id="95be0-129">Adicione uma nova dimensão física a um produto da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="95be0-129">Add a new physical dimension for a product by doing the following:</span></span>

1. <span data-ttu-id="95be0-130">Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="95be0-130">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="95be0-131">Selecione o produto com **Número do item** *A0001*.</span><span class="sxs-lookup"><span data-stu-id="95be0-131">Select the product with **Item number** *A0001*.</span></span>
1. <span data-ttu-id="95be0-132">No Painel de Ação, abra a guia **Gerenciar estoque** e, no grupo **Depósito**, selecione **Dimensões físicas do produto**.</span><span class="sxs-lookup"><span data-stu-id="95be0-132">On the Action Pane, open the **Manage inventory** tab and, from the **Warehouse** group, select **Physical product dimensions**.</span></span>
1. <span data-ttu-id="95be0-133">A página **Dimensões físicas do produto** é aberta.</span><span class="sxs-lookup"><span data-stu-id="95be0-133">The **Physical product dimensions** page opens.</span></span> <span data-ttu-id="95be0-134">No Painel de Ações, selecione **Novo** para adicionar uma nova dimensão à grade com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="95be0-134">On the Action Pane, select **New** to add a new dimension to the grid with the following settings:</span></span>
    - <span data-ttu-id="95be0-135">**Tipo de dimensão física** - *Embalagem*</span><span class="sxs-lookup"><span data-stu-id="95be0-135">**Physical dimension type** - *Packing*</span></span>
    - <span data-ttu-id="95be0-136">**Unidade física** - *pçs*</span><span class="sxs-lookup"><span data-stu-id="95be0-136">**Physical unit** - *pcs*</span></span>
    - <span data-ttu-id="95be0-137">**Peso** - *4*</span><span class="sxs-lookup"><span data-stu-id="95be0-137">**Weight** - *4*</span></span>
    - <span data-ttu-id="95be0-138">**Unidade de peso** - *kg*</span><span class="sxs-lookup"><span data-stu-id="95be0-138">**Weight unit** - *kg*</span></span>
    - <span data-ttu-id="95be0-139">**Profundidade** - *3*</span><span class="sxs-lookup"><span data-stu-id="95be0-139">**Depth** - *3*</span></span>
    - <span data-ttu-id="95be0-140">**Altura** - *4*</span><span class="sxs-lookup"><span data-stu-id="95be0-140">**Height** - *4*</span></span>
    - <span data-ttu-id="95be0-141">**Largura** - *3*</span><span class="sxs-lookup"><span data-stu-id="95be0-141">**Width** - *3*</span></span>
    - <span data-ttu-id="95be0-142">**Comprimento** - *cm*</span><span class="sxs-lookup"><span data-stu-id="95be0-142">**Length** - *cm*</span></span>
    - <span data-ttu-id="95be0-143">**Unidade de volume** - *cm3*</span><span class="sxs-lookup"><span data-stu-id="95be0-143">**Volume unit** - *cm3*</span></span>

<span data-ttu-id="95be0-144">O campo **Volume** é calculado automaticamente com base nas configurações de **Profundidade**, **Altura** e **Largura**.</span><span class="sxs-lookup"><span data-stu-id="95be0-144">The **Volume** field is automatically calculated based on your **Depth**, **Height**, and **Width** settings.</span></span>

#### <a name="create-a-new-container-type"></a><span data-ttu-id="95be0-145">Criar um novo tipo de contêiner</span><span class="sxs-lookup"><span data-stu-id="95be0-145">Create a new container type</span></span>

<span data-ttu-id="95be0-146">Acesse **Gerenciamento de depósito \> Configuração \> Contêineres \> Tipos de contêiner** e crie um registro com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="95be0-146">Go to **Warehouse management \> Setup \> Containers \> Container types** and create a new record with the following settings:</span></span>

- <span data-ttu-id="95be0-147">**Código do tipo de contêiner** - *Caixa Baixa*</span><span class="sxs-lookup"><span data-stu-id="95be0-147">**Container type code** - *Short Box*</span></span>
- <span data-ttu-id="95be0-148">**Descrição** - *Caixa Baixa*</span><span class="sxs-lookup"><span data-stu-id="95be0-148">**Description** - *Short Box*</span></span>
- <span data-ttu-id="95be0-149">**Peso líquido máximo** - *50*</span><span class="sxs-lookup"><span data-stu-id="95be0-149">**Maximum net weight** - *50*</span></span>
- <span data-ttu-id="95be0-150">**Volume** - *144*</span><span class="sxs-lookup"><span data-stu-id="95be0-150">**Volume** - *144*</span></span>
- <span data-ttu-id="95be0-151">**Extensão** - *6*</span><span class="sxs-lookup"><span data-stu-id="95be0-151">**Length** - *6*</span></span>
- <span data-ttu-id="95be0-152">**Largura** - *6*</span><span class="sxs-lookup"><span data-stu-id="95be0-152">**Width** - *6*</span></span>
- <span data-ttu-id="95be0-153">**Altura** - *4*</span><span class="sxs-lookup"><span data-stu-id="95be0-153">**Height** - *4*</span></span>

#### <a name="create-a-container-group"></a><span data-ttu-id="95be0-154">Criar um grupo de contêineres</span><span class="sxs-lookup"><span data-stu-id="95be0-154">Create a container group</span></span>

<span data-ttu-id="95be0-155">Acesse **Gerenciamento de depósito \> Configuração \> Contêineres \> Grupos de contêineres** e crie um registro com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="95be0-155">Go to **Warehouse management \> Setup \> Containers \> Container groups** and create a new record with the following settings:</span></span>

- <span data-ttu-id="95be0-156">**ID do grupo de contêineres** - *Caixa Baixa*</span><span class="sxs-lookup"><span data-stu-id="95be0-156">**Container group ID** - *Short Box*</span></span>
- <span data-ttu-id="95be0-157">**Descrição** - *Caixa Baixa*</span><span class="sxs-lookup"><span data-stu-id="95be0-157">**Description** - *Short Box*</span></span>

<span data-ttu-id="95be0-158">Adicione uma nova linha à seção **Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="95be0-158">Add a new line to the **Details** section.</span></span> <span data-ttu-id="95be0-159">Defina o **Tipo de contêiner** como *Caixa Baixa*.</span><span class="sxs-lookup"><span data-stu-id="95be0-159">Set the **Container type** to *Short Box*.</span></span>

#### <a name="set-up-a-container-build-template"></a><span data-ttu-id="95be0-160">Configurar um modelo de criação de contêiner</span><span class="sxs-lookup"><span data-stu-id="95be0-160">Set up a container build template</span></span>

<span data-ttu-id="95be0-161">Acesse **Gerenciamento de depósito \> Configuração \> Contêineres \> Modelos de criação de contêiner** e selecione **Caixas**.</span><span class="sxs-lookup"><span data-stu-id="95be0-161">Go to **Warehouse management \> Setup \> Containers \> Container build templates** and select **Boxes**.</span></span> <span data-ttu-id="95be0-162">Altere a **ID do grupo de contêineres** como *Caixa Baixa*.</span><span class="sxs-lookup"><span data-stu-id="95be0-162">Change the **Container group ID** to *Short Box*.</span></span>

### <a name="run-the-scenario"></a><span data-ttu-id="95be0-163">Executar o cenário</span><span class="sxs-lookup"><span data-stu-id="95be0-163">Run the scenario</span></span>

<span data-ttu-id="95be0-164">Depois de preparar o sistema conforme descrito na seção anterior, você estará pronto para executar o cenário conforme descrito na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="95be0-164">After you have prepared your system as described in the previous section, you are ready to run the scenario as described in the next section.</span></span>

#### <a name="create-a-sales-order-and-create-a-shipment"></a><span data-ttu-id="95be0-165">Criar uma ordem de venda e uma remessa</span><span class="sxs-lookup"><span data-stu-id="95be0-165">Create a sales order and create a shipment</span></span>

<span data-ttu-id="95be0-166">Neste processo, você criará uma remessa com base nas dimensões de *embalagem* do item, para o qual a altura é inferior a 3.</span><span class="sxs-lookup"><span data-stu-id="95be0-166">In this process you will create a shipment based on the item *packing* dimensions, for which the height is less than 3.</span></span>

1. <span data-ttu-id="95be0-167">Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="95be0-167">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="95be0-168">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="95be0-168">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="95be0-169">Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="95be0-169">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="95be0-170">**Conta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="95be0-170">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="95be0-171">**Depósito:** *63*</span><span class="sxs-lookup"><span data-stu-id="95be0-171">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="95be0-172">Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="95be0-172">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="95be0-173">A nova ordem de venda é aberta.</span><span class="sxs-lookup"><span data-stu-id="95be0-173">The new sales order is opened.</span></span> <span data-ttu-id="95be0-174">Ele deve incluir uma nova linha vazia na grade da FastTab **Linhas de ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="95be0-174">It should include a new, empty line in the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="95be0-175">Nessa linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="95be0-175">On this line, set the following values:</span></span>

    - <span data-ttu-id="95be0-176">**Número de item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="95be0-176">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="95be0-177">**Quantidade:** *5*</span><span class="sxs-lookup"><span data-stu-id="95be0-177">**Quantity:** *5*</span></span>

1. <span data-ttu-id="95be0-178">Na FastTab **Linhas da ordem de venda**, selecione **Estoque \> Reserva**.</span><span class="sxs-lookup"><span data-stu-id="95be0-178">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="95be0-179">Na página **Reserva**, no Painel de Ação, selecione **Reservar lote** para reservar o estoque.</span><span class="sxs-lookup"><span data-stu-id="95be0-179">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="95be0-180">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="95be0-180">Close the page.</span></span>
1. <span data-ttu-id="95be0-181">No Painel de Ações, abra a guia **Depósito** e selecione **Liberar para depósito** para criar trabalho para o depósito.</span><span class="sxs-lookup"><span data-stu-id="95be0-181">On the Action Pane, open the **Warehouse** tab and select **Release to warehouse** to create work for the warehouse.</span></span>
1. <span data-ttu-id="95be0-182">Na FastTab **Linhas de ordem de venda**, selecione **Depósito \> Detalhes da remessa**.</span><span class="sxs-lookup"><span data-stu-id="95be0-182">On the **Sales order lines** FastTab, select **Warehouse \> Shipment details**.</span></span>
1. <span data-ttu-id="95be0-183">No painel de ações, abra a guia **Transporte** e selecione **Exibir contêineres**.</span><span class="sxs-lookup"><span data-stu-id="95be0-183">On the Action Pane, open the **Transportation** tab and select **View containers**.</span></span> <span data-ttu-id="95be0-184">Confirme se o item foi incluído nos dois contêineres *Caixa Baixa*.</span><span class="sxs-lookup"><span data-stu-id="95be0-184">Confirm that the item was containerized into the two *Short Box* containers.</span></span>

#### <a name="place-an-item-into-storage"></a><span data-ttu-id="95be0-185">Colocar um item no armazenamento</span><span class="sxs-lookup"><span data-stu-id="95be0-185">Place an item into storage</span></span>

1. <span data-ttu-id="95be0-186">Abra o dispositivo móvel para entrar no depósito 63 e acesse **Estoque \> Ajustar em**.</span><span class="sxs-lookup"><span data-stu-id="95be0-186">Open the mobile device, sign in to warehouse 63 and go to **Inventory \> Adjust In**.</span></span>
1. <span data-ttu-id="95be0-187">Insira **Loc** = *SHORT-01*.</span><span class="sxs-lookup"><span data-stu-id="95be0-187">Enter **Loc** = *SHORT-01*.</span></span> <span data-ttu-id="95be0-188">Crie uma placa de licença com **Item** = *A0001* e **Quantidade** = *1 pçs*.</span><span class="sxs-lookup"><span data-stu-id="95be0-188">Make a new license plate with **Item** = *A0001* and **Quantity** = *1 pcs*.</span></span>
1. <span data-ttu-id="95be0-189">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="95be0-189">Select **OK**.</span></span> <span data-ttu-id="95be0-190">Você receberá o erro "Falha no local SHORT-01 porque o item A0001 não cabe nas dimensões especificadas do local".</span><span class="sxs-lookup"><span data-stu-id="95be0-190">You will receive the error "Location SHORT-01 failed because item A0001 does not fit in location's specified dimensions."</span></span> <span data-ttu-id="95be0-191">Isso ocorre porque as dimensões do tipo de *Armazenamento* do produto são maiores que as dimensões especificadas no perfil de localização.</span><span class="sxs-lookup"><span data-stu-id="95be0-191">This is because the *Storage* type dimensions of the product are larger than the dimensions specified on the location profile.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]