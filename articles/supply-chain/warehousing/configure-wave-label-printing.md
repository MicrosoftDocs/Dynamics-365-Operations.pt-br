---
title: Configurar e usar a impressão de etiquetas de onda
description: Este tópico descreve a impressão de etiquetas de onda e explica como configurá-la.
author: GarmMSFT
manager: PJacobse
ms.date: 05/01/2020
ms.topic: configure-wave-label-printing
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveLabel, WHSWaveLabelTemplate
audience: Application User
ms.reviewer: PJacobse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: v-olbara
ms.search.validFrom: yyyy-mm-dd
ms.dyn365.ops.version: 10.0.0
ms.openlocfilehash: 49e0ef1b3020cd1236203c0f243f145dd7a7c10d
ms.sourcegitcommit: 137e2bd30f0a85bd2e1baf1cf16b993edd2094f9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "3546408"
---
# <a name="set-up-and-use-wave-label-printing"></a><span data-ttu-id="02807-103">Configurar e usar a impressão de etiquetas de onda</span><span class="sxs-lookup"><span data-stu-id="02807-103">Set up and use wave label printing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="02807-104">A impressão de etiquetas de onda oferece uma abordagem alternativa para a impressão de etiquetas introduzindo um novo método de etapa da onda que permite criar e imprimir etiquetas diretamente do modelo de onda durante a execução de ondas.</span><span class="sxs-lookup"><span data-stu-id="02807-104">Wave label printing offers an alternative approach to label printing by introducing a new wave step method that lets you create and print labels directly from the wave template during wave execution.</span></span> <span data-ttu-id="02807-105">Portanto, as etiquetas estarão disponíveis antes que os trabalhadores executem a ordem de serviço em um dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="02807-105">Therefore, the labels will already be available before workers run the work order on a mobile device.</span></span> <span data-ttu-id="02807-106">Os trabalhadores poderão então anexar as etiquetas necessárias durante a separação, em vez de após a separação.</span><span class="sxs-lookup"><span data-stu-id="02807-106">Workers can then attach the required labels during picking instead of after picking.</span></span>

<span data-ttu-id="02807-107">A impressão de etiquetas de onda usa a Linguagem de Programação Zebra (ZPL) para criar layouts de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-107">Wave label printing uses Zebra Programming Language (ZPL) to create label layouts.</span></span> <span data-ttu-id="02807-108">Um layout de etiqueta é dividido em três seções (cabeçalho, corpo e rodapé) para permitir etiquetas que tenham estrutura repetitiva.</span><span class="sxs-lookup"><span data-stu-id="02807-108">A label layout is divided into three sections (header, body, and footer) to allow for labels that have repeating structure.</span></span> <span data-ttu-id="02807-109">Os modelos de etiqueta de onda informam ao sistema qual layout de etiqueta deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="02807-109">Wave label templates tell the system which label layout to use.</span></span> <span data-ttu-id="02807-110">Os usuários podem especificar a impressora a ser usada.</span><span class="sxs-lookup"><span data-stu-id="02807-110">Users can specify which printer is used.</span></span> <span data-ttu-id="02807-111">Eles também podem imprimir etiquetas em várias impressoras ao mesmo tempo, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="02807-111">They can also print labels on several printers at the same time, as they require.</span></span> <span data-ttu-id="02807-112">A página **Histórico de etiquetas de onda** mostra um registro de todas as etiquetas que foram criadas usando esta configuração.</span><span class="sxs-lookup"><span data-stu-id="02807-112">The **Wave label history** page shows a record of all labels that have been created by using this setup.</span></span>

<span data-ttu-id="02807-113">Você pode imprimir e agrupar etiquetas com base em cabeçalhos de trabalho, imprimir etiquetas de intervalo por cabeçalho de trabalho e imprimir etiquetas de conteúdo de contêiner, etiquetas de caso e outras etiquetas semelhantes.</span><span class="sxs-lookup"><span data-stu-id="02807-113">You can print and collate labels based on work headers, you can print break labels per work header, and you can print container content labels, case labels, and other similar labels.</span></span>

> [!NOTE]
> <span data-ttu-id="02807-114">Essa funcionalidade não substitui a funcionalidade de impressão de etiquetas existente que é baseada no roteamento de documentos.</span><span class="sxs-lookup"><span data-stu-id="02807-114">This functionality doesn't replace existing label printing functionality that is based on document routing.</span></span>

<span data-ttu-id="02807-115">A impressão de etiquetas de onda oferece os seguintes aprimoramentos:</span><span class="sxs-lookup"><span data-stu-id="02807-115">Wave label printing offers the following enhancements:</span></span>

- <span data-ttu-id="02807-116">Imprimir etiquetas de acordo com o número de caixas em uma única linha de trabalho, sem o transporte em contêineres.</span><span class="sxs-lookup"><span data-stu-id="02807-116">Print labels according to the number of cartons on a single work line, without using containerization.</span></span> <span data-ttu-id="02807-117">(A "caixa" é uma unidade designada em linhas do grupo de sequências de unidade.)</span><span class="sxs-lookup"><span data-stu-id="02807-117">(A "carton" is a unit that is designated on unit sequence group lines.)</span></span>
- <span data-ttu-id="02807-118">Imprimir várias sequências de etiquetas diferentes (por exemplo, etiquetas de caixa e de palete).</span><span class="sxs-lookup"><span data-stu-id="02807-118">Print several different label sequences (for example, carton and pallet labels).</span></span>
- <span data-ttu-id="02807-119">Incluir enumeração de etiquetas (por exemplo, 1/124, 2/124, ... 124/124) e definir o intervalo de enumeração (por exemplo, linha de trabalho, linha de carga ou remessa).</span><span class="sxs-lookup"><span data-stu-id="02807-119">Include label enumeration (for example, 1/124, 2/124, ... 124/124), and define the range of enumeration (for example, work line, load line, or shipment).</span></span>
- <span data-ttu-id="02807-120">Criar e imprimir uma ID de conhecimento de embarque nas etiquetas antes que o conhecimento de embarque seja gerado.</span><span class="sxs-lookup"><span data-stu-id="02807-120">Create and print a bill of lading ID on labels before the bill of lading is generated.</span></span>
- <span data-ttu-id="02807-121">Criar um código série do contêiner de remessa (SSCC) exclusivo para cada caixa e incluí-lo em cada etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-121">Create a unique serial shipping container code (SSCC) for each carton, and include it on each label.</span></span>
- <span data-ttu-id="02807-122">Criar sequências numéricas em conformidade com o GS1 para IDs de conhecimento de embarque e SSCCs.</span><span class="sxs-lookup"><span data-stu-id="02807-122">Create GS1-compliant number sequences for bill of lading IDs and SSCCs.</span></span>
- <span data-ttu-id="02807-123">Reimprimir etiquetas de dispositivos móveis e do cliente avançado.</span><span class="sxs-lookup"><span data-stu-id="02807-123">Reprint labels from both mobile devices and the rich client.</span></span>
- <span data-ttu-id="02807-124">Anular etiquetas (por exemplo, em cenários de separação insuficiente) e reimprimi-las.</span><span class="sxs-lookup"><span data-stu-id="02807-124">Void labels (for example, in short pick scenarios), and reprint them.</span></span>
- <span data-ttu-id="02807-125">Limpar o histórico de etiquetas de onda.</span><span class="sxs-lookup"><span data-stu-id="02807-125">Clean up the wave label history.</span></span>
- <span data-ttu-id="02807-126">Os aprimoramentos nos layouts de roteamento de documentos são compartilhados entre layouts de roteamento de documentos e layouts de etiqueta de onda.</span><span class="sxs-lookup"><span data-stu-id="02807-126">Improvements to document routing layouts are shared between document routing layouts and wave label layouts.</span></span> <span data-ttu-id="02807-127">(Para obter mais informações, consulte [Layout de roteamento de documentos para placas de licença](../warehousing/document-routing-layout-for-license-plates.md).)</span><span class="sxs-lookup"><span data-stu-id="02807-127">(For more information, see [Document routing layout for license plates](../warehousing/document-routing-layout-for-license-plates.md).)</span></span>

<span data-ttu-id="02807-128">Esses aprimoramentos tornam mais eficiente a etiquetagem de caixas antes da paletização.</span><span class="sxs-lookup"><span data-stu-id="02807-128">These enhancements make it more efficient to label cartons before palletization.</span></span> <span data-ttu-id="02807-129">Eles são especialmente benéficos para empresas que enviam para grandes varejistas que automaticamente confirmam os recebimentos de ordens digitalizando cada caixa de forma separada.</span><span class="sxs-lookup"><span data-stu-id="02807-129">They especially benefit companies that ship to large retailers that automatically confirm order receipts by scanning each carton separately.</span></span>

> [!NOTE]
> <span data-ttu-id="02807-130">Você pode implementar os cenários de configuração descritos neste tópico separadamente ou em combinação, dependendo dos seus requisitos comerciais.</span><span class="sxs-lookup"><span data-stu-id="02807-130">You can implement the configuration scenarios that are described in this topic either separately or in combination, depending on your business requirements.</span></span> <span data-ttu-id="02807-131">Você pode criar vários modelos de etiqueta de onda que funcionam em sequência (conforme ilustrado no cenário 3).</span><span class="sxs-lookup"><span data-stu-id="02807-131">You can design several wave label templates that work in sequence (as illustrated in scenario 3).</span></span> <span data-ttu-id="02807-132">Por exemplo, você pode usar o cenário 1 para imprimir etiquetas de caixa e o cenário 2 para imprimir etiquetas de palete (se os paletes no estoque variarem em tamanho e composição).</span><span class="sxs-lookup"><span data-stu-id="02807-132">For example, you can use scenario 1 to print carton labels and scenario 2 to print pallet labels (if pallets in stock vary in size and composition).</span></span>

## <a name="turn-on-the-wave-label-printing-feature"></a><span data-ttu-id="02807-133">Ativar o recurso Impressão de etiquetas de onda</span><span class="sxs-lookup"><span data-stu-id="02807-133">Turn on the Wave label printing feature</span></span>

<span data-ttu-id="02807-134">Para que você possa usar o recurso *Impressão de etiquetas de onda*, ele deve estar ativado no sistema.</span><span class="sxs-lookup"><span data-stu-id="02807-134">Before you can use the *Wave label printing* feature, it must be turned on in your system.</span></span> <span data-ttu-id="02807-135">Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="02807-135">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="02807-136">Nesse caso, o recurso é listado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="02807-136">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="02807-137">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="02807-137">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="02807-138">**Nome do recurso:** *Impressão de etiquetas de onda*</span><span class="sxs-lookup"><span data-stu-id="02807-138">**Feature name:** *Wave label printing*</span></span>

## <a name="scenario-1-wave-label-printing-where-a-single-wave-label-is-generated"></a><span data-ttu-id="02807-139">Cenário 1: Impressão de etiquetas de onda na qual uma única etiqueta de onda é gerada</span><span class="sxs-lookup"><span data-stu-id="02807-139">Scenario 1: Wave label printing where a single wave label is generated</span></span>

<span data-ttu-id="02807-140">Este cenário mostra como uma empresa pode imprimir etiquetas de remessa para um grande varejista que automaticamente confirma os recebimentos de ordens digitalizando cada caixa de forma separada.</span><span class="sxs-lookup"><span data-stu-id="02807-140">This scenario shows how a company can print shipping labels for a large retailer that automatically confirms order receipts by scanning each carton separately.</span></span>

<span data-ttu-id="02807-141">Ele mostra o fluxo de ponta a ponta.</span><span class="sxs-lookup"><span data-stu-id="02807-141">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="02807-142">Disponibilizar dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="02807-142">Make demo data available</span></span>

<span data-ttu-id="02807-143">Para seguir este cenário, você deve ter dados de demonstração instalados e deve selecionar a entidade legal **USMF**.</span><span class="sxs-lookup"><span data-stu-id="02807-143">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-the-wave-label-method-is-available"></a><span data-ttu-id="02807-144">Verificar se o método de etiqueta de onda está disponível</span><span class="sxs-lookup"><span data-stu-id="02807-144">Make sure that the wave label method is available</span></span>

<span data-ttu-id="02807-145">Pode ser necessário regenerar os métodos de processo de onda para tornar o método de impressão de etiquetas de onda disponível.</span><span class="sxs-lookup"><span data-stu-id="02807-145">You might have to regenerate the wave process methods to make the wave label printing method available.</span></span>

1. <span data-ttu-id="02807-146">Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Métodos de processo de onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-146">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="02807-147">Confirme se **waveLabelPrinting** está na lista.</span><span class="sxs-lookup"><span data-stu-id="02807-147">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="02807-148">Se não estiver, selecione **Regenerar métodos** no Painel de Ação para adicioná-lo.</span><span class="sxs-lookup"><span data-stu-id="02807-148">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>

### <a name="configure-a-wave-template"></a><span data-ttu-id="02807-149">Configurar um modelo de onda</span><span class="sxs-lookup"><span data-stu-id="02807-149">Configure a wave template</span></span>

<span data-ttu-id="02807-150">Os modelos de onda permitem vincular instâncias específicas de métodos de onda a um modelo de etiqueta de onda correspondente.</span><span class="sxs-lookup"><span data-stu-id="02807-150">Wave templates let you link specific instances of wave methods to a corresponding wave label template.</span></span>

1. <span data-ttu-id="02807-151">Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos de onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-151">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="02807-152">Selecione um modelo, como **Padrão de Remessa 62**.</span><span class="sxs-lookup"><span data-stu-id="02807-152">Select a template, such as **62 Shipping Default**.</span></span>
1. <span data-ttu-id="02807-153">Na FastTab **Métodos**, mova o método \***Impressão de etiquetas de onda** para a coluna **Métodos selecionados**.</span><span class="sxs-lookup"><span data-stu-id="02807-153">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
1. <span data-ttu-id="02807-154">Na coluna **Métodos selecionados**, selecione o método **Impressão de etiquetas de onda** e defina seu campo **Código da etapa da onda** como *PrintLabel*.</span><span class="sxs-lookup"><span data-stu-id="02807-154">In the **Selected methods** column, select the **Wave label printing** method, and set its **Wave step code** field to *PrintLabel*.</span></span> <span data-ttu-id="02807-155">Para obter mais informações sobre códigos da etapa da onda, consulte [Códigos da etapa da onda](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="02807-155">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-a-wave-label-layout"></a><span data-ttu-id="02807-156">Criar um layout de etiqueta de onda</span><span class="sxs-lookup"><span data-stu-id="02807-156">Create a wave label layout</span></span>

<span data-ttu-id="02807-157">O layout de etiqueta controla quais informações são impressas na etiqueta e como são apresentadas. Aqui, insira o código ZPL enviado à impressora.</span><span class="sxs-lookup"><span data-stu-id="02807-157">The label layout controls what information is printed on the label and how it's laid out. Here, you enter the ZPL code that is sent to the printer.</span></span>

1. <span data-ttu-id="02807-158">Vá para **Gerenciamento de depósito \> Configuração \> Roteamento de documentos \> Layouts de etiqueta de onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-158">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="02807-159">Crie um registro com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-159">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="02807-160">**ID do layout da etiqueta:** *Caixa*</span><span class="sxs-lookup"><span data-stu-id="02807-160">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="02807-161">**Descrição:** *Caixa (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="02807-161">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="02807-162">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="02807-162">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="02807-163">No Painel de Ação, selecione **Configurações da linha da etiqueta da onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-163">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="02807-164">A página **Configurações da linha da etiqueta da onda** será exibida.</span><span class="sxs-lookup"><span data-stu-id="02807-164">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="02807-165">Aqui, você pode configurar a parte dinâmica da etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-165">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="02807-166">Adicione uma linha com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-166">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="02807-167">**ID da linha:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="02807-167">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="02807-168">**Nome da tabela de linhas:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="02807-168">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="02807-169">**Posição inicial da linha:** *0*</span><span class="sxs-lookup"><span data-stu-id="02807-169">**Row start position:** *0*</span></span>

        <span data-ttu-id="02807-170">Este campo define a posição vertical na qual a linha será iniciada na etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-170">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="02807-171">**Altura da linha:** *0*</span><span class="sxs-lookup"><span data-stu-id="02807-171">**Row height:** *0*</span></span>

        <span data-ttu-id="02807-172">Este campo define a altura de cada linha (em pontos), de acordo com o padrão ZPL.</span><span class="sxs-lookup"><span data-stu-id="02807-172">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="02807-173">A altura da linha é positiva para etiquetas horizontais e negativa para etiquetas verticais.</span><span class="sxs-lookup"><span data-stu-id="02807-173">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="02807-174">Como há apenas uma linha neste exemplo, você pode definir o valor como *0* (zero).</span><span class="sxs-lookup"><span data-stu-id="02807-174">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="02807-175">**Linhas por página:** *1*</span><span class="sxs-lookup"><span data-stu-id="02807-175">**Rows per page:** *1*</span></span>

        <span data-ttu-id="02807-176">Este campo define o número de linhas que podem ser impressas em cada etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-176">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="02807-177">Esta configuração fará com que uma etiqueta ZPL separada seja impressa para cada registro na tabela de etiquetas de onda.</span><span class="sxs-lookup"><span data-stu-id="02807-177">This setup will cause a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="02807-178">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="02807-178">Close the page.</span></span>
1. <span data-ttu-id="02807-179">No Painel de Ações, selecione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="02807-179">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="02807-180">Na caixa de diálogo do editor de consultas, na guia **Intervalo**, adicione uma linha com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-180">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="02807-181">**Tabela:** *Linhas de trabalho*</span><span class="sxs-lookup"><span data-stu-id="02807-181">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="02807-182">**Tabela derivada:** *Linhas de trabalho*</span><span class="sxs-lookup"><span data-stu-id="02807-182">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="02807-183">**Campo:** *Tipo de trabalho*</span><span class="sxs-lookup"><span data-stu-id="02807-183">**Field:** *Work type*</span></span>
    - <span data-ttu-id="02807-184">**Critérios:** *Separação*</span><span class="sxs-lookup"><span data-stu-id="02807-184">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="02807-185">Esta consulta garante que somente as linhas de trabalho de separação serão impressas na etiqueta, não as linhas de trabalho de colocação.</span><span class="sxs-lookup"><span data-stu-id="02807-185">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="02807-186">Se você quiser imprimir a ID do conhecimento de embarque, na guia **Junções**, selecione a tabela **Linhas de trabalho** e junte a tabela **Remessas** a ela.</span><span class="sxs-lookup"><span data-stu-id="02807-186">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="02807-187">Feche a caixa de diálogo do editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="02807-187">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="02807-188">A FastTab **Layout do texto da impressora** tem três seções nas quais é possível escrever código da impressora: **Seção do cabeçalho**, **Seção do corpo** e **Seção do rodapé**.</span><span class="sxs-lookup"><span data-stu-id="02807-188">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="02807-189">Na **Seção do cabeçalho**, no campo **Cabeçalho da etiqueta**, insira o código para o cabeçalho obrigatório.</span><span class="sxs-lookup"><span data-stu-id="02807-189">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="02807-190">Por exemplo, se você estiver usando impressoras Zebra, poderá usar o código a seguir.</span><span class="sxs-lookup"><span data-stu-id="02807-190">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. <span data-ttu-id="02807-191">Na **Seção do corpo**, no campo **Corpo da etiqueta**, insira o código ZPL para o corpo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="02807-191">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="02807-192">Veja aqui um exemplo.</span><span class="sxs-lookup"><span data-stu-id="02807-192">Here is an example.</span></span>

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. <span data-ttu-id="02807-193">Na **Seção do corpo**, no campo **Rodapé da etiqueta**, insira o código ZPL para o rodapé obrigatório.</span><span class="sxs-lookup"><span data-stu-id="02807-193">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="02807-194">Veja aqui um exemplo.</span><span class="sxs-lookup"><span data-stu-id="02807-194">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="02807-195">Esta configuração imprimirá uma cópia de cada etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-195">This setup will print one copy of each label.</span></span> <span data-ttu-id="02807-196">Se você precisar de mais cópias (por exemplo, uma cópia para cada lado do palete), defina o valor **n** para a seção **\^PQn** no rodapé como o número de cópias necessário.</span><span class="sxs-lookup"><span data-stu-id="02807-196">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="02807-197">Por exemplo, para imprimir quatro cópias de cada etiqueta, especifique **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="02807-197">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

<span data-ttu-id="02807-198">Sua etiqueta agora está pronta para uso.</span><span class="sxs-lookup"><span data-stu-id="02807-198">Your label is now ready to use.</span></span>

### <a name="create-a-wave-label-type"></a><span data-ttu-id="02807-199">Criar um tipo de etiqueta de onda</span><span class="sxs-lookup"><span data-stu-id="02807-199">Create a wave label type</span></span>

<span data-ttu-id="02807-200">Os tipos de etiqueta de onda são usados para vincular modelos de etiqueta de onda a uma unidade em linhas de grupo de sequências de unidade.</span><span class="sxs-lookup"><span data-stu-id="02807-200">Wave label types are used to link wave label templates to a unit on unit sequence group lines.</span></span>

1. <span data-ttu-id="02807-201">Vá para **Gerenciamento de depósito \> Configuração \> Roteamento de documentos \> Tipos de etiqueta de onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-201">Go to **Warehouse management \> Setup \> Document routing \> Wave label types**.</span></span>
1. <span data-ttu-id="02807-202">Adicione um tipo de etiqueta de onda com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-202">Add a wave label type that has the following settings:</span></span>

    - <span data-ttu-id="02807-203">**Tipo de etiqueta:** *Caixa*</span><span class="sxs-lookup"><span data-stu-id="02807-203">**Label type:** *Carton*</span></span>
    - <span data-ttu-id="02807-204">**Descrição:** *Caixa*</span><span class="sxs-lookup"><span data-stu-id="02807-204">**Description:** *Carton*</span></span>

### <a name="set-up-unit-sequence-groups"></a><span data-ttu-id="02807-205">Configurar grupos de sequências de unidade</span><span class="sxs-lookup"><span data-stu-id="02807-205">Set up unit sequence groups</span></span>

<span data-ttu-id="02807-206">Em seguida, configure o grupo de sequências de unidade para o tipo de etiqueta de onda.</span><span class="sxs-lookup"><span data-stu-id="02807-206">Next, set up the unit sequence group for the wave label type.</span></span>

1. <span data-ttu-id="02807-207">Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Grupos de sequências de unidade**.</span><span class="sxs-lookup"><span data-stu-id="02807-207">Go to **Warehouse management \> Setup \> Warehouse \> Unit sequence groups**.</span></span>
1. <span data-ttu-id="02807-208">Selecione o grupo **Ea Caixa PL**.</span><span class="sxs-lookup"><span data-stu-id="02807-208">Select the **Ea Box PL** group.</span></span>
1. <span data-ttu-id="02807-209">Para a linha **Caixa**, defina o campo **Tipo de nível de onda** como *Caixa*.</span><span class="sxs-lookup"><span data-stu-id="02807-209">For the **Box** line, set the **Wave level type** field to *Carton*.</span></span>

### <a name="create-a-wave-label-template"></a><span data-ttu-id="02807-210">Criar um modelo de etiqueta de onda</span><span class="sxs-lookup"><span data-stu-id="02807-210">Create a wave label template</span></span>

<span data-ttu-id="02807-211">Em seguida, crie o modelo de etiqueta de onda para o tipo de etiqueta de onda.</span><span class="sxs-lookup"><span data-stu-id="02807-211">Next, create the wave label template for the wave label type.</span></span>

1. <span data-ttu-id="02807-212">Vá para **Gerenciamento de depósito \> Configuração \> Roteamento de documentos \> Modelos de etiqueta de onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-212">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="02807-213">Adicione um modelo de nível de onda e defina os seguintes valores no cabeçalho:</span><span class="sxs-lookup"><span data-stu-id="02807-213">Add a wave level template, and set the following values in the header:</span></span>

    - <span data-ttu-id="02807-214">**Nome do modelo de etiqueta:** *Etiquetas de caixa*</span><span class="sxs-lookup"><span data-stu-id="02807-214">**Label template name:** *Carton labels*</span></span>
    - <span data-ttu-id="02807-215">**Descrição:** *Etiquetas de caixa*</span><span class="sxs-lookup"><span data-stu-id="02807-215">**Description:** *Carton labels*</span></span>
    - <span data-ttu-id="02807-216">**Código da etapa da onda:** *PrintLabel*</span><span class="sxs-lookup"><span data-stu-id="02807-216">**Wave step code:** *PrintLabel*</span></span>
    - <span data-ttu-id="02807-217">**Depósito:** *62*</span><span class="sxs-lookup"><span data-stu-id="02807-217">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="02807-218">Na FastTab **Geral**, defina o campo **Tipo de etiqueta de onda** como *Caixa*.</span><span class="sxs-lookup"><span data-stu-id="02807-218">On the **General** FastTab, set the **Wave label type** field to *Carton*.</span></span>
1. <span data-ttu-id="02807-219">Na FastTab **Detalhes do modelo de etiqueta de onda**, adicione uma nova linha com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-219">On the **Wave label template details** FastTab, add a new row that has the following settings:</span></span>

    - <span data-ttu-id="02807-220">**ID do layout da etiqueta:** *Caixa*</span><span class="sxs-lookup"><span data-stu-id="02807-220">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="02807-221">**Nome da impressora:** Selecione uma impressora ZPL apropriada.</span><span class="sxs-lookup"><span data-stu-id="02807-221">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="02807-222">**Executar consulta:** *Sim* (esta configuração é opcional, mas recomendável para um desempenho ideal.)</span><span class="sxs-lookup"><span data-stu-id="02807-222">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="02807-223">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="02807-223">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="02807-224">Opcional: se estiver configurando um design de etiqueta específico do cliente, você deve criar uma consulta para localizar a conta do cliente.</span><span class="sxs-lookup"><span data-stu-id="02807-224">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="02807-225">Na FastTab **Detalhes do modelo de etiqueta de onda**, selecione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="02807-225">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="02807-226">Em seguida, na caixa de diálogo do editor de consultas, na guia **Intervalo**, adicione uma linha com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-226">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="02807-227">**Tabela:** *Remessas*</span><span class="sxs-lookup"><span data-stu-id="02807-227">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="02807-228">**Tabela derivada:** *Remessas*</span><span class="sxs-lookup"><span data-stu-id="02807-228">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="02807-229">**Campo:** *Número da conta*</span><span class="sxs-lookup"><span data-stu-id="02807-229">**Field:** *Account number*</span></span>
    - <span data-ttu-id="02807-230">**Critérios:** Insira o número da conta do cliente relevante.</span><span class="sxs-lookup"><span data-stu-id="02807-230">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="02807-231">Quando terminar, selecione **OK** para fechar a caixa de diálogo do editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="02807-231">When you've finished, select **OK** to close the query editor dialog box.</span></span>

1. <span data-ttu-id="02807-232">No Painel de Ação, selecione **Editar consulta** para abrir a caixa de diálogo do editor de consultas para todo o modelo de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-232">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="02807-233">Na caixa de diálogo do editor de consultas, na guia **Classificação**, adicione uma linha com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-233">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="02807-234">**Tabela:** *Linhas de trabalho*</span><span class="sxs-lookup"><span data-stu-id="02807-234">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="02807-235">**Tabela derivada:** *Linhas de trabalho*</span><span class="sxs-lookup"><span data-stu-id="02807-235">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="02807-236">**Campo:** *ID da linha de carga de referência (ID do Registro)*</span><span class="sxs-lookup"><span data-stu-id="02807-236">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="02807-237">**Direção da pesquisa:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="02807-237">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="02807-238">Selecione **OK** para fechar a caixa de diálogo do editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="02807-238">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="02807-239">Uma caixa de mensagem solicitará que você confirme a operação de redefinição do agrupamento.</span><span class="sxs-lookup"><span data-stu-id="02807-239">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="02807-240">Selecione **Sim** para continuar.</span><span class="sxs-lookup"><span data-stu-id="02807-240">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="02807-241">No Painel de Ação, selecione **Grupo de modelos de etiqueta de onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-241">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="02807-242">Na caixa de diálogo **Grupo de modelos de etiqueta de onda**, selecione a linha na qual o campo **Nome do campo de referência** está definido como *ID da linha de carga de referência* e, em seguida, marque a caixa de seleção **ID de criação da etiqueta** para essa linha.</span><span class="sxs-lookup"><span data-stu-id="02807-242">In the **Wave label template group** dialog box, select the row where the **Reference field name** field is set to *Reference load line id*, and then select the **Label build ID** check box for this row.</span></span>

    > [!NOTE]
    > <span data-ttu-id="02807-243">Essa configuração criará uma sequência de etiquetas ("Caixa 1 de X") por linha de carga ao longo da onda, independentemente da configuração do agrupamento de trabalho.</span><span class="sxs-lookup"><span data-stu-id="02807-243">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="02807-244">Essa sequência de etiquetas pode ser impressa no layout de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-244">This label sequence can be printed on the label layout.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="02807-245">Configurar extensões de sequência numérica</span><span class="sxs-lookup"><span data-stu-id="02807-245">Configure number sequence extensions</span></span>

<span data-ttu-id="02807-246">As extensões de sequência numérica controlam a conformidade com o GS1 de sequências numéricas específicas.</span><span class="sxs-lookup"><span data-stu-id="02807-246">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="02807-247">Esta configuração é opcional para o cenário atual.</span><span class="sxs-lookup"><span data-stu-id="02807-247">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="02807-248">Para obter mais informações e instruções de configuração, consulte [Configurar extensões de sequência numérica](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="02807-248">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="02807-249">Criar uma ordem de venda e liberá-la para o depósito</span><span class="sxs-lookup"><span data-stu-id="02807-249">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="02807-250">Vá para **Vendas e marketing \> Ordem de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="02807-250">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="02807-251">Crie uma ordem de venda com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-251">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="02807-252">**Conta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="02807-252">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="02807-253">**Depósito:** *62*</span><span class="sxs-lookup"><span data-stu-id="02807-253">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="02807-254">Adicione duas linhas da ordem de venda com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-254">Add two sales order lines that have the following settings:</span></span>

    - <span data-ttu-id="02807-255">Linha 1 da ordem de venda:</span><span class="sxs-lookup"><span data-stu-id="02807-255">Sales order line 1:</span></span>

        - <span data-ttu-id="02807-256">**Número de item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="02807-256">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="02807-257">**Quantidade:** *9024*</span><span class="sxs-lookup"><span data-stu-id="02807-257">**Quantity:** *9024*</span></span>
        - <span data-ttu-id="02807-258">**Unidade:** *ea* (9024 ea = 376 Caixa = 47 PL)</span><span class="sxs-lookup"><span data-stu-id="02807-258">**Unit:** *ea* (9024 ea = 376 Box = 47 PL)</span></span>

    - <span data-ttu-id="02807-259">Linha 2 da ordem de venda:</span><span class="sxs-lookup"><span data-stu-id="02807-259">Sales order line 2:</span></span>

        - <span data-ttu-id="02807-260">**Número de item:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="02807-260">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="02807-261">**Quantidade:** *9016*</span><span class="sxs-lookup"><span data-stu-id="02807-261">**Quantity:** *9016*</span></span>
        - <span data-ttu-id="02807-262">**Unidade:** *ea* (9016 ea = 322 Caixa = 46 PL)</span><span class="sxs-lookup"><span data-stu-id="02807-262">**Unit:** *ea* (9016 ea = 322 Box = 46 PL)</span></span>

    > [!NOTE]
    > <span data-ttu-id="02807-263">Os itens e as quantidades fornecidos aqui são apenas exemplos.</span><span class="sxs-lookup"><span data-stu-id="02807-263">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="02807-264">Eles devem usar o grupo de sequências de unidade definido anteriormente, conversões de unidade apropriadas de *ea* para *Caixa* para *PL* devem ser definidas para eles, e eles devem ter estoque no depósito *62*.</span><span class="sxs-lookup"><span data-stu-id="02807-264">They must use the unit sequence group that you defined earlier, appropriate unit conversions from *ea* to *Box* to *PL* must be defined for them, and they must have stock in warehouse *62*.</span></span> <span data-ttu-id="02807-265">Para obter mais informações, consulte [Políticas de unidade de medida e estoque](unit-measure-stocking-policies.md).</span><span class="sxs-lookup"><span data-stu-id="02807-265">For more information, see [Unit of measure and stocking policies](unit-measure-stocking-policies.md).</span></span>

1. <span data-ttu-id="02807-266">Selecione a linha 1 da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="02807-266">Select sales order line 1.</span></span> <span data-ttu-id="02807-267">Em seguida, na seção **Linha da ordem de venda**, no menu **Estoque**, selecione **Reservas**.</span><span class="sxs-lookup"><span data-stu-id="02807-267">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="02807-268">Na página **Reserva**, no Painel de Ação, selecione **Reservar lote** e, em seguida, feche a página.</span><span class="sxs-lookup"><span data-stu-id="02807-268">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="02807-269">Repita as etapas 4 e 5 para a linha 2 da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="02807-269">Repeat steps 4 and 5 for sales order line 2.</span></span>
1. <span data-ttu-id="02807-270">No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="02807-270">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="02807-271">Os seguintes eventos ocorrem:</span><span class="sxs-lookup"><span data-stu-id="02807-271">The following events occur:</span></span>

    - <span data-ttu-id="02807-272">O sistema processa a remessa criada usando o modelo que inclui a etapa de impressão de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="02807-272">The system processes the created shipment by using the template that includes the label printing step.</span></span> <span data-ttu-id="02807-273">O layout da etiqueta será usado para definir o formato da etiqueta, e o resultado será uma etiqueta impressa na impressora selecionada no modelo de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-273">The label layout will be used to define the format of the label, and the result will be a label that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="02807-274">Etiquetas de onda são geradas e impressas.</span><span class="sxs-lookup"><span data-stu-id="02807-274">Wave labels are generated and printed.</span></span> <span data-ttu-id="02807-275">O número de etiquetas será igual ao número de caixas (neste exemplo, 376 etiquetas Caixa para a linha 1 e 322 etiquetas Caixa para a linha 2).</span><span class="sxs-lookup"><span data-stu-id="02807-275">The number of labels will equal the number of cartons (in this example, 376 Box labels for line 1 and 322 Box labels for line 2).</span></span>
    - <span data-ttu-id="02807-276">Uma nova ID de conhecimento de embarque é gerada para as remessas.</span><span class="sxs-lookup"><span data-stu-id="02807-276">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="02807-277">Se você configurou as extensões de sequência numérica, as IDs de etiqueta de onda seguirão o formato numérico de **SSCC-18**.</span><span class="sxs-lookup"><span data-stu-id="02807-277">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="02807-278">Você pode exibir e reimprimir etiquetas de onda nas páginas a seguir.</span><span class="sxs-lookup"><span data-stu-id="02807-278">You can view and reprint wave labels from the following pages.</span></span> <span data-ttu-id="02807-279">No Painel de Ações de cada página, na guia **Remessas**, no grupo **Informações relacionadas**, selecione **Etiquetas de onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-279">On the Action Pane of each page, on the **Shipments** tab, in the **Related information** group, select **Wave labels**.</span></span>

- <span data-ttu-id="02807-280">Todas as remessas \> Detalhes da remessa</span><span class="sxs-lookup"><span data-stu-id="02807-280">All shipments \> Shipment details</span></span>
- <span data-ttu-id="02807-281">Todas as cargas \> Detalhes da carga</span><span class="sxs-lookup"><span data-stu-id="02807-281">All loads \> Load details</span></span>
- <span data-ttu-id="02807-282">Todas as ondas</span><span class="sxs-lookup"><span data-stu-id="02807-282">All waves</span></span>
- <span data-ttu-id="02807-283">Etiquetas de onda</span><span class="sxs-lookup"><span data-stu-id="02807-283">Wave labels</span></span>
- <span data-ttu-id="02807-284">Histórico da etiqueta de onda</span><span class="sxs-lookup"><span data-stu-id="02807-284">Wave label history</span></span>

## <a name="scenario-2-wave-label-printing-for-containerization-without-wave-label-records"></a><span data-ttu-id="02807-285">Cenário 2: Impressão de etiquetas de onda para transporte em contêineres (sem registros de etiqueta de onda)</span><span class="sxs-lookup"><span data-stu-id="02807-285">Scenario 2: Wave label printing for containerization (without wave label records)</span></span>

<span data-ttu-id="02807-286">Este cenário permite imprimir etiquetas de onda ao usar o transporte em contêineres para dividir itens automaticamente em caixas e, portanto, não requer um registro de etiqueta de onda.</span><span class="sxs-lookup"><span data-stu-id="02807-286">This scenario lets you print wave labels when you use containerization to automatically split items into cartons and therefore don't require a wave label record.</span></span> <span data-ttu-id="02807-287">Nesse caso, a ID do contêiner atua como um espaço reservado para o SSCC.</span><span class="sxs-lookup"><span data-stu-id="02807-287">In this case, the container ID acts as a placeholder for the SSCC.</span></span>

<span data-ttu-id="02807-288">Estas são as principais diferenças entre este cenário e o cenário 1:</span><span class="sxs-lookup"><span data-stu-id="02807-288">Here are the main differences between this scenario and scenario 1:</span></span>

- <span data-ttu-id="02807-289">**Modelos de etiqueta de onda:** você não selecionará um tipo de etiqueta de onda no modelo de etiqueta de onda e não precisará de um agrupamento de criações de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="02807-289">**Wave label templates:** You won't select a wave label type on the wave label template, and you won't require a label build grouping.</span></span> <span data-ttu-id="02807-290">Caso contrário, você configurará o modelo de etiqueta de onda e se vinculará ao modelo de onda da mesma forma que é descrita no cenário 1.</span><span class="sxs-lookup"><span data-stu-id="02807-290">Otherwise, you will configure the wave label template and link to the wave template in the same way that is described in scenario 1.</span></span> <span data-ttu-id="02807-291">Você deve deixar o tipo de etiqueta de onda em branco para evitar que etiquetas de onda sejam geradas.</span><span class="sxs-lookup"><span data-stu-id="02807-291">You must leave the wave label type blank to prevent wave labels from being generated.</span></span>
- <span data-ttu-id="02807-292">**Layouts de etiqueta de onda:** você definirá as configurações de linha do layout de etiqueta de onda para linhas de trabalho em vez de registros de etiqueta de onda.</span><span class="sxs-lookup"><span data-stu-id="02807-292">**Wave label layouts:** You will configure the wave label layout row settings for work lines instead of wave label records.</span></span> <span data-ttu-id="02807-293">Você deve definir a configuração de linha para o layout de etiqueta usando a tabela **WHSWorkLine** em vez da tabela **WHSWaveLabel**.</span><span class="sxs-lookup"><span data-stu-id="02807-293">You must configure the row setting for the label layout by using the **WHSWorkLine** table instead of the **WHSWaveLabel** table.</span></span> <span data-ttu-id="02807-294">A configuração **Linhas por página** controla o número de linhas que a seção do corpo terá.</span><span class="sxs-lookup"><span data-stu-id="02807-294">The **Rows per page** setting controls the number of rows that the body section will have.</span></span> 

<span data-ttu-id="02807-295">Essa configuração também é adequada para cenários comerciais nos quais vários itens diferentes são embalados em uma caixa etiquetada ou em um palete, e esse processo de embalagem pode ser definido pela criação do trabalho (por exemplo, trabalho agrupado por remessa).</span><span class="sxs-lookup"><span data-stu-id="02807-295">This configuration is also suitable for business scenarios where multiple different items are packed into one labeled box or into a pallet, and this packing process can be defined by work creation (for example, work that is grouped by shipment).</span></span>

<span data-ttu-id="02807-296">Ele mostra o fluxo de ponta a ponta.</span><span class="sxs-lookup"><span data-stu-id="02807-296">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="02807-297">Disponibilizar dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="02807-297">Make demo data available</span></span>

<span data-ttu-id="02807-298">Para seguir este cenário, você deve ter dados de demonstração instalados e deve selecionar a entidade legal **USMF**.</span><span class="sxs-lookup"><span data-stu-id="02807-298">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="make-sure-that-the-wave-label-method-is-available"></a><span data-ttu-id="02807-299">Verificar se o método de etiqueta de onda está disponível</span><span class="sxs-lookup"><span data-stu-id="02807-299">Make sure that the wave label method is available</span></span>

<span data-ttu-id="02807-300">Pode ser necessário regenerar os métodos de processo de onda para tornar o método de impressão de etiquetas de onda disponível.</span><span class="sxs-lookup"><span data-stu-id="02807-300">You might have to regenerate the wave process methods to make the wave label printing method available.</span></span>

1. <span data-ttu-id="02807-301">Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Métodos de processo de onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-301">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="02807-302">Confirme se **waveLabelPrinting** está na lista.</span><span class="sxs-lookup"><span data-stu-id="02807-302">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="02807-303">Se não estiver, selecione **Regenerar métodos** no Painel de Ação para adicioná-lo.</span><span class="sxs-lookup"><span data-stu-id="02807-303">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="02807-304">Configurar um modelo de onda</span><span class="sxs-lookup"><span data-stu-id="02807-304">Set up a wave template</span></span>

<span data-ttu-id="02807-305">Os modelos de onda permitem vincular instâncias específicas de métodos de onda a um modelo de etiqueta de onda correspondente.</span><span class="sxs-lookup"><span data-stu-id="02807-305">Wave templates let you link specific instances of wave methods to a corresponding wave label template.</span></span>

1. <span data-ttu-id="02807-306">Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos de onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-306">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="02807-307">Selecione um modelo, como **Transporte em Contêineres 63**.</span><span class="sxs-lookup"><span data-stu-id="02807-307">Select a template, such as **63 Containerization**.</span></span>
1. <span data-ttu-id="02807-308">Na FastTab **Métodos**, mova o método \***Impressão de etiquetas de onda** para a coluna **Métodos selecionados**.</span><span class="sxs-lookup"><span data-stu-id="02807-308">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
1. <span data-ttu-id="02807-309">Na coluna **Métodos selecionados**, selecione o método **Impressão de etiquetas de onda** e defina seu campo **Código da etapa da onda** como *PrintLabel*.</span><span class="sxs-lookup"><span data-stu-id="02807-309">In the **Selected methods** column, select the **Wave label printing** method, and set its **Wave step code** field to *PrintLabel*.</span></span> <span data-ttu-id="02807-310">Para obter mais informações sobre códigos da etapa da onda, consulte [Códigos da etapa da onda](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="02807-310">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-a-wave-label-layout"></a><span data-ttu-id="02807-311">Criar um layout de etiqueta de onda</span><span class="sxs-lookup"><span data-stu-id="02807-311">Create a wave label layout</span></span>

1. <span data-ttu-id="02807-312">Vá para **Gerenciamento de depósito \> Configuração \> Roteamento de documentos \> Layouts de etiqueta de onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-312">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="02807-313">Crie um registro com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-313">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="02807-314">**ID do layout da etiqueta:** *Caixa*</span><span class="sxs-lookup"><span data-stu-id="02807-314">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="02807-315">**Descrição:** *Caixa (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="02807-315">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="02807-316">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="02807-316">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="02807-317">No Painel de Ação, selecione **Configurações da linha da etiqueta da onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-317">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="02807-318">A página **Configurações da linha da etiqueta da onda** será exibida.</span><span class="sxs-lookup"><span data-stu-id="02807-318">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="02807-319">Aqui, você pode configurar a parte dinâmica da etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-319">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="02807-320">Adicione uma linha com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-320">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="02807-321">**ID da linha:** *WorkLine*</span><span class="sxs-lookup"><span data-stu-id="02807-321">**Row Id:** *WorkLine*</span></span>
    - <span data-ttu-id="02807-322">**Nome da tabela de linhas:** *WHSWorkLine*</span><span class="sxs-lookup"><span data-stu-id="02807-322">**Row table name:** *WHSWorkLine*</span></span>
    - <span data-ttu-id="02807-323">**Posição inicial da linha:** *500*</span><span class="sxs-lookup"><span data-stu-id="02807-323">**Row start position:** *500*</span></span>

        <span data-ttu-id="02807-324">Este campo define a posição vertical na qual a linha será iniciada na etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-324">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="02807-325">**Altura da linha:** *-50*</span><span class="sxs-lookup"><span data-stu-id="02807-325">**Row height:** *-50*</span></span>

        <span data-ttu-id="02807-326">Este campo define a altura de cada linha.</span><span class="sxs-lookup"><span data-stu-id="02807-326">This field defines the height of each row.</span></span> <span data-ttu-id="02807-327">A altura da linha é positiva para etiquetas horizontais e negativa para etiquetas verticais.</span><span class="sxs-lookup"><span data-stu-id="02807-327">The row height is positive for horizontal labels and negative for vertical labels.</span></span>

    - <span data-ttu-id="02807-328">**Linhas por página:** *5*</span><span class="sxs-lookup"><span data-stu-id="02807-328">**Rows per page:** *5*</span></span>

        <span data-ttu-id="02807-329">Este campo define o número de linhas que podem ser impressas em cada etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-329">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="02807-330">Esta configuração imprimirá várias etiquetas ZPL por trabalho, em que cada página pode conter até cinco linhas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="02807-330">This setup will print several ZPL labels per work, where each page can hold up to five work lines.</span></span> <span data-ttu-id="02807-331">Por exemplo, se uma etiqueta for impressa para um contêiner que tem 12 linhas, três etiquetas serão impressas.</span><span class="sxs-lookup"><span data-stu-id="02807-331">For example, if a label is printed for a container that has 12 lines, three labels will be printed.</span></span> <span data-ttu-id="02807-332">Se quiser imprimir uma etiqueta separada para cada linha de separação, defina este valor como *1*.</span><span class="sxs-lookup"><span data-stu-id="02807-332">If you want to print a separate label for each pick line, set this value to *1*.</span></span>

1. <span data-ttu-id="02807-333">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="02807-333">Close the page.</span></span>
1. <span data-ttu-id="02807-334">No Painel de Ações, selecione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="02807-334">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="02807-335">Na caixa de diálogo do editor de consultas, na guia **Intervalo**, adicione uma linha com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-335">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="02807-336">**Tabela:** *Linhas de trabalho*</span><span class="sxs-lookup"><span data-stu-id="02807-336">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="02807-337">**Tabela derivada:** *Linhas de trabalho*</span><span class="sxs-lookup"><span data-stu-id="02807-337">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="02807-338">**Campo:** *Tipo de trabalho*</span><span class="sxs-lookup"><span data-stu-id="02807-338">**Field:** *Work type*</span></span>
    - <span data-ttu-id="02807-339">**Critérios:** *Separação*</span><span class="sxs-lookup"><span data-stu-id="02807-339">**Criteria:** *Pick*</span></span>

1. <span data-ttu-id="02807-340">Se você quiser imprimir a ID do conhecimento de embarque, na guia **Junções**, selecione a tabela **Linhas de trabalho** e junte a tabela **Remessas** a ela.</span><span class="sxs-lookup"><span data-stu-id="02807-340">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="02807-341">Feche a caixa de diálogo do editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="02807-341">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="02807-342">A FastTab **Layout do texto da impressora** tem três seções nas quais é possível escrever código da impressora: **Seção do cabeçalho**, **Seção do corpo** e **Seção do rodapé**.</span><span class="sxs-lookup"><span data-stu-id="02807-342">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="02807-343">Na **Seção do cabeçalho**, no campo **Cabeçalho da etiqueta**, insira o código para o cabeçalho obrigatório.</span><span class="sxs-lookup"><span data-stu-id="02807-343">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="02807-344">Por exemplo, se você estiver usando impressoras Zebra, poderá usar o código a seguir.</span><span class="sxs-lookup"><span data-stu-id="02807-344">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkTable.ContainerId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. <span data-ttu-id="02807-345">Na **Seção do corpo**, no campo **Corpo da etiqueta**, insira o código ZPL para o corpo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="02807-345">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="02807-346">Veja aqui um exemplo.</span><span class="sxs-lookup"><span data-stu-id="02807-346">Here is an example.</span></span>

    ```plaintext
    <Row name="WorkLine">
    <Heading>
    //Optional heading for section of rows
    </Heading>
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWorkLine.ItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWorkLine.QtyWork$ ^FS
    </Row>
    ```

1. <span data-ttu-id="02807-347">Na **Seção do corpo**, no campo **Rodapé da etiqueta**, insira o código ZPL para o rodapé obrigatório.</span><span class="sxs-lookup"><span data-stu-id="02807-347">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="02807-348">Veja aqui um exemplo.</span><span class="sxs-lookup"><span data-stu-id="02807-348">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="02807-349">Esta configuração imprimirá uma cópia de cada etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-349">This setup will print one copy of each label.</span></span> <span data-ttu-id="02807-350">Se você precisar de mais cópias (por exemplo, uma cópia para cada lado do palete), defina o valor **n** para a seção **\^PQn** no rodapé como o número de cópias necessário.</span><span class="sxs-lookup"><span data-stu-id="02807-350">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="02807-351">Por exemplo, para imprimir quatro cópias de cada etiqueta, especifique **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="02807-351">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

<span data-ttu-id="02807-352">Sua etiqueta agora está pronta para uso.</span><span class="sxs-lookup"><span data-stu-id="02807-352">Your label is now ready to use.</span></span>

### <a name="create-a-wave-label-template"></a><span data-ttu-id="02807-353">Criar um modelo de etiqueta de onda</span><span class="sxs-lookup"><span data-stu-id="02807-353">Create a wave label template</span></span>

1. <span data-ttu-id="02807-354">Vá para **Gerenciamento de depósito \> Configuração \> Roteamento de documentos \> Modelos de etiqueta de onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-354">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="02807-355">Adicione um modelo de nível de onda e defina os seguintes valores no cabeçalho:</span><span class="sxs-lookup"><span data-stu-id="02807-355">Add a wave level template, and set the following values in the header:</span></span>

    - <span data-ttu-id="02807-356">**Nome do modelo de etiqueta:** *Etiquetas de contêiner*</span><span class="sxs-lookup"><span data-stu-id="02807-356">**Label template name:** *Container labels*</span></span>
    - <span data-ttu-id="02807-357">**Descrição:** *Etiquetas de contêiner*</span><span class="sxs-lookup"><span data-stu-id="02807-357">**Description:** *Container labels*</span></span>
    - <span data-ttu-id="02807-358">**Código da etapa da onda:** *PrintLabel*</span><span class="sxs-lookup"><span data-stu-id="02807-358">**Wave step code:** *PrintLabel*</span></span>
    - <span data-ttu-id="02807-359">**Depósito:** *63*</span><span class="sxs-lookup"><span data-stu-id="02807-359">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="02807-360">Na FastTab **Detalhes do modelo de etiqueta de onda**, adicione uma linha com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-360">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="02807-361">**ID do layout da etiqueta:** *Contêiner*</span><span class="sxs-lookup"><span data-stu-id="02807-361">**Label layout ID:** *Container*</span></span>
    - <span data-ttu-id="02807-362">**Nome da impressora:** Selecione uma impressora ZPL apropriada.</span><span class="sxs-lookup"><span data-stu-id="02807-362">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="02807-363">**Executar consulta:** *Sim* (esta configuração é opcional, mas recomendável para um desempenho ideal.)</span><span class="sxs-lookup"><span data-stu-id="02807-363">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="02807-364">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="02807-364">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="02807-365">Opcional: se estiver configurando um design de etiqueta específico do cliente, você deve criar uma consulta para localizar a conta do cliente.</span><span class="sxs-lookup"><span data-stu-id="02807-365">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="02807-366">Na FastTab **Detalhes do modelo de etiqueta de onda**, selecione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="02807-366">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="02807-367">Em seguida, na caixa de diálogo do editor de consultas, na guia **Intervalo**, adicione uma linha com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-367">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="02807-368">**Tabela:** *Remessas*</span><span class="sxs-lookup"><span data-stu-id="02807-368">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="02807-369">**Tabela derivada:** *Remessas*</span><span class="sxs-lookup"><span data-stu-id="02807-369">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="02807-370">**Campo:** *Número da conta*</span><span class="sxs-lookup"><span data-stu-id="02807-370">**Field:** *Account number*</span></span>
    - <span data-ttu-id="02807-371">**Critérios:** Insira o número da conta do cliente relevante.</span><span class="sxs-lookup"><span data-stu-id="02807-371">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="02807-372">Quando terminar, selecione **OK** para fechar a caixa de diálogo do editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="02807-372">When you've finished, select **OK** to close the query editor dialog box.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="02807-373">Configurar extensões de sequência numérica</span><span class="sxs-lookup"><span data-stu-id="02807-373">Configure number sequence extensions</span></span>

<span data-ttu-id="02807-374">As extensões de sequência numérica controlam a conformidade com o GS1 de sequências numéricas específicas.</span><span class="sxs-lookup"><span data-stu-id="02807-374">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="02807-375">Esta configuração é opcional para o cenário atual.</span><span class="sxs-lookup"><span data-stu-id="02807-375">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="02807-376">Para obter mais informações e instruções de configuração, consulte [Configurar extensões de sequência numérica](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="02807-376">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="02807-377">Criar uma ordem de venda e liberá-la para o depósito</span><span class="sxs-lookup"><span data-stu-id="02807-377">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="02807-378">Vá para **Vendas e marketing \> Ordem de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="02807-378">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="02807-379">Crie uma ordem de venda com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-379">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="02807-380">**Conta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="02807-380">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="02807-381">**Depósito:** *63*</span><span class="sxs-lookup"><span data-stu-id="02807-381">**Warehouse:** *63*</span></span>

1. <span data-ttu-id="02807-382">Adicione cinco linhas da ordem de venda:</span><span class="sxs-lookup"><span data-stu-id="02807-382">Add five sales order lines:</span></span>

    - <span data-ttu-id="02807-383">Linha 1 da ordem de venda:</span><span class="sxs-lookup"><span data-stu-id="02807-383">Sales order line 1:</span></span>

        - <span data-ttu-id="02807-384">**Número de item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="02807-384">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="02807-385">**Quantidade:** *10*</span><span class="sxs-lookup"><span data-stu-id="02807-385">**Quantity:** *10*</span></span>

    - <span data-ttu-id="02807-386">Linha 2 da ordem de venda:</span><span class="sxs-lookup"><span data-stu-id="02807-386">Sales order line 2:</span></span>

        - <span data-ttu-id="02807-387">**Número de item:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="02807-387">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="02807-388">**Quantidade:** *20*</span><span class="sxs-lookup"><span data-stu-id="02807-388">**Quantity:** *20*</span></span>

    - <span data-ttu-id="02807-389">Linha 3 da ordem de venda:</span><span class="sxs-lookup"><span data-stu-id="02807-389">Sales order line 3:</span></span>

        - <span data-ttu-id="02807-390">**Número de item:** *L0006*</span><span class="sxs-lookup"><span data-stu-id="02807-390">**Item number:** *L0006*</span></span>
        - <span data-ttu-id="02807-391">**Quantidade:** *20*</span><span class="sxs-lookup"><span data-stu-id="02807-391">**Quantity:** *20*</span></span>

    - <span data-ttu-id="02807-392">Linha 4 da ordem de venda:</span><span class="sxs-lookup"><span data-stu-id="02807-392">Sales order line 4:</span></span>

        - <span data-ttu-id="02807-393">**Número de item:** *L0100*</span><span class="sxs-lookup"><span data-stu-id="02807-393">**Item number:** *L0100*</span></span>
        - <span data-ttu-id="02807-394">**Quantidade:** *40*</span><span class="sxs-lookup"><span data-stu-id="02807-394">**Quantity:** *40*</span></span>

    - <span data-ttu-id="02807-395">Linha 5 da ordem de venda:</span><span class="sxs-lookup"><span data-stu-id="02807-395">Sales order line 5:</span></span>

        - <span data-ttu-id="02807-396">**Número de item:** *L0101*</span><span class="sxs-lookup"><span data-stu-id="02807-396">**Item number:** *L0101*</span></span>
        - <span data-ttu-id="02807-397">**Quantidade:** *50*</span><span class="sxs-lookup"><span data-stu-id="02807-397">**Quantity:** *50*</span></span>

    > [!NOTE]
    > <span data-ttu-id="02807-398">Os itens e as quantidades fornecidos aqui são apenas exemplos.</span><span class="sxs-lookup"><span data-stu-id="02807-398">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="02807-399">Eles devem ter estoque no depósito especificado.</span><span class="sxs-lookup"><span data-stu-id="02807-399">They must have stock in the specified warehouse.</span></span>

1. <span data-ttu-id="02807-400">Selecione a linha 1 da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="02807-400">Select sales order line 1.</span></span> <span data-ttu-id="02807-401">Em seguida, na seção **Linha da ordem de venda**, no menu **Estoque**, selecione **Reservas**.</span><span class="sxs-lookup"><span data-stu-id="02807-401">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="02807-402">Na página **Reserva**, no Painel de Ação, selecione **Reservar lote** e, em seguida, feche a página.</span><span class="sxs-lookup"><span data-stu-id="02807-402">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="02807-403">Repita as etapas 4 e 5 para cada linha da ordem de venda adicional.</span><span class="sxs-lookup"><span data-stu-id="02807-403">Repeat steps 4 and 5 for each additional sales order line.</span></span>
1. <span data-ttu-id="02807-404">No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="02807-404">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="02807-405">Os seguintes eventos ocorrem:</span><span class="sxs-lookup"><span data-stu-id="02807-405">The following events occur:</span></span>

    - <span data-ttu-id="02807-406">O sistema processa a remessa criada usando o modelo que inclui a etapa de impressão de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="02807-406">The system processes the created shipment using the template that includes the label printing step.</span></span> <span data-ttu-id="02807-407">O layout da etiqueta será usado para definir o formato da etiqueta, e o resultado final será uma etiqueta com cinco linhas impressa na impressora selecionada no modelo de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-407">The label layout will be used to define the format of the label, and the end result will be a label that has five lines and that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="02807-408">Uma nova ID de conhecimento de embarque é gerada para as remessas.</span><span class="sxs-lookup"><span data-stu-id="02807-408">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="02807-409">Se você configurou as extensões de sequência numérica, as IDs de etiqueta de onda seguirão o formato numérico de **SSCC-18**.</span><span class="sxs-lookup"><span data-stu-id="02807-409">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="02807-410">Você pode reimprimir essas etiquetas de onda indo para **Gerenciamento de depósito \> Consultas e relatórios \> Histórico de etiquetas de onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-410">You can reprint these wave labels by going to **Warehouse management \> Inquiries and reports \> Wave label history**.</span></span>

## <a name="scenario-3-wave-label-printing-for-multi-tiered-labels"></a><span data-ttu-id="02807-411">Cenário 3: Impressão de etiquetas de onda para etiquetas de várias camadas</span><span class="sxs-lookup"><span data-stu-id="02807-411">Scenario 3: Wave label printing for multi-tiered labels</span></span>

<span data-ttu-id="02807-412">Este cenário mostra como usar a funcionalidade de impressão de etiquetas de onda quando os processos de depósito exigem várias camadas de etiquetas de remessa.</span><span class="sxs-lookup"><span data-stu-id="02807-412">This scenario shows how to use the wave label printing functionality when the warehousing processes require several tiers of shipping labels.</span></span> <span data-ttu-id="02807-413">Por exemplo, pode ser necessário imprimir etiquetas separadas para caixas e paletes e uma etiqueta de intervalo para uma remessa inteira.</span><span class="sxs-lookup"><span data-stu-id="02807-413">For example, separate labels might have to be printed for cartons and pallets, and a break label might have to be printed for a whole shipment.</span></span> <span data-ttu-id="02807-414">As etiquetas de intervalo são um tipo separado de etiqueta que pode ser usado como divisor entre rolos e contêineres, como etiquetas para a ID de remessa e um código de barras, de forma que as etiquetas possam ser classificadas facilmente após serem impressas.</span><span class="sxs-lookup"><span data-stu-id="02807-414">Break labels are a separate type of label that can be used as a divider between rolls and containers, such as labels for the shipment ID and a barcode, so that the labels can easily be sorted after they are printed.</span></span>

<span data-ttu-id="02807-415">A principal diferença entre a configuração deste cenário e a configuração do cenário 1, além do fato de as etiquetas de intervalo estarem habilitadas, é que vários tipos de etiqueta de onda devem ser associados a modelos de etiqueta de onda e linhas de grupo de sequências de unidade.</span><span class="sxs-lookup"><span data-stu-id="02807-415">The main difference between the configuration of this scenario and the configuration of scenario 1, besides the fact that break labels are enabled, is that multiple wave label types must be associated with wave label templates and unit sequence group lines.</span></span> <span data-ttu-id="02807-416">Para realizar essa configuração, defina os seguintes elementos para este cenário:</span><span class="sxs-lookup"><span data-stu-id="02807-416">To accomplish this configuration, you set up the following elements for this scenario:</span></span>

- <span data-ttu-id="02807-417">**Métodos de processamento de ondas:** você vai marcar o método de etiqueta de onda como "repetível", adicioná-lo duas (ou mais) vezes ao modelo de onda e definir códigos de etapa de onda diferentes.</span><span class="sxs-lookup"><span data-stu-id="02807-417">**Wave processing methods:** You will mark the wave label method as "repeatable," add it two (or more) times to the wave template, and set different wave step codes.</span></span>
- <span data-ttu-id="02807-418">**Modelos de etiqueta de onda:** você configurará os modelos de etiqueta de onda e os vinculará ao modelo de onda.</span><span class="sxs-lookup"><span data-stu-id="02807-418">**Wave label templates:** You will configure the wave label templates and link them to the wave template.</span></span> <span data-ttu-id="02807-419">Cada modelo de etiqueta de onda tem seu próprio tipo de etiqueta de onda.</span><span class="sxs-lookup"><span data-stu-id="02807-419">Each wave label template has its own wave label type.</span></span>
- <span data-ttu-id="02807-420">**Layouts de etiqueta de onda:** você criará vários layouts de etiqueta de onda.</span><span class="sxs-lookup"><span data-stu-id="02807-420">**Wave label layouts:** You will create multiple wave label layouts.</span></span> <span data-ttu-id="02807-421">Haverá um layout de etiqueta separado para cada "camada" de etiquetas e também haverá um layout de etiqueta de intervalo.</span><span class="sxs-lookup"><span data-stu-id="02807-421">There will be a separate label layout for each "tier" of labels, and there will also be a break label layout.</span></span>

<span data-ttu-id="02807-422">Ele mostra o fluxo de ponta a ponta.</span><span class="sxs-lookup"><span data-stu-id="02807-422">This scenario shows the end-to-end flow.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="02807-423">Disponibilizar dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="02807-423">Make demo data available</span></span>

<span data-ttu-id="02807-424">Para seguir este cenário, você deve ter dados de demonstração instalados e deve selecionar a entidade legal **USMF**.</span><span class="sxs-lookup"><span data-stu-id="02807-424">To follow this scenario, you must have demo data installed, and you must select the **USMF** legal entity.</span></span>

### <a name="set-up-a-wave-process-method"></a><span data-ttu-id="02807-425">Configurar um método de processo de onda</span><span class="sxs-lookup"><span data-stu-id="02807-425">Set up a wave process method</span></span>

1. <span data-ttu-id="02807-426">Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Métodos de processo de onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-426">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="02807-427">Confirme se **waveLabelPrinting** está na lista.</span><span class="sxs-lookup"><span data-stu-id="02807-427">Confirm that **waveLabelPrinting** is in the list.</span></span> <span data-ttu-id="02807-428">Se não estiver, selecione **Regenerar métodos** no Painel de Ação para adicioná-lo.</span><span class="sxs-lookup"><span data-stu-id="02807-428">If it isn't, select **Regenerate methods** on the Action Pane to add it.</span></span>
1. <span data-ttu-id="02807-429">Para o método **waveLabelPrinting**, marque a caixa de seleção **Tornar o método repetível**.</span><span class="sxs-lookup"><span data-stu-id="02807-429">For the **waveLabelPrinting** method, select the **Make method repeatable** check box.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="02807-430">Configurar um modelo de onda</span><span class="sxs-lookup"><span data-stu-id="02807-430">Set up a wave template</span></span>

1. <span data-ttu-id="02807-431">Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos de onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-431">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
2. <span data-ttu-id="02807-432">Selecione um modelo, como **Padrão de Remessa 62**.</span><span class="sxs-lookup"><span data-stu-id="02807-432">Select a template, such as **62 Shipping Default**.</span></span>
3. <span data-ttu-id="02807-433">Na FastTab **Métodos**, mova o método \***Impressão de etiquetas de onda** para a coluna **Métodos selecionados**.</span><span class="sxs-lookup"><span data-stu-id="02807-433">On the **Methods** FastTab, move the **Wave label printing** method to the **Selected methods** column.</span></span>
4. <span data-ttu-id="02807-434">Na coluna **Métodos selecionados**, atribua um valor de **Código da etapa da onda**, como *Caixa*, ao método **Impressão de etiquetas de onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-434">In the **Selected methods** column, assign a **Wave step code** value, such as *Carton*, to the **Wave label printing** method.</span></span> <span data-ttu-id="02807-435">Para obter mais informações sobre códigos da etapa da onda, consulte [Códigos da etapa da onda](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="02807-435">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>
5. <span data-ttu-id="02807-436">Mova o método **Impressão de etiquetas de onda** para a coluna **Métodos selecionados** novamente.</span><span class="sxs-lookup"><span data-stu-id="02807-436">Move the **Wave label printing** method to the **Selected methods** column a second time.</span></span>
6. <span data-ttu-id="02807-437">Na coluna **Métodos selecionados**, atribua um valor diferente de **Código da etapa da onda**, como *Palete*, ao segundo método **Impressão de etiquetas de onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-437">In the **Selected methods** column, assign a different **Wave step code** value, such as *Pallet*, to the second **Wave label printing** method.</span></span> <span data-ttu-id="02807-438">Para obter mais informações sobre códigos da etapa da onda, consulte [Códigos da etapa da onda](wave-step-codes.md).</span><span class="sxs-lookup"><span data-stu-id="02807-438">For more information about wave step codes, see [Wave step codes](wave-step-codes.md).</span></span>

### <a name="create-three-wave-label-layouts"></a><span data-ttu-id="02807-439">Criar três layouts de etiqueta de onda</span><span class="sxs-lookup"><span data-stu-id="02807-439">Create three wave label layouts</span></span>

1. <span data-ttu-id="02807-440">Vá para **Gerenciamento de depósito \> Configuração \> Roteamento de documentos \> Layouts de etiqueta de onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-440">Go to **Warehouse management \> Setup \> Document routing \> Wave label layouts**.</span></span>
1. <span data-ttu-id="02807-441">Crie um registro com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-441">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="02807-442">**ID do layout da etiqueta:** *Caixa*</span><span class="sxs-lookup"><span data-stu-id="02807-442">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="02807-443">**Descrição:** *Caixa (SSCC)*</span><span class="sxs-lookup"><span data-stu-id="02807-443">**Description:** *Carton (SSCC)*</span></span>

1. <span data-ttu-id="02807-444">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="02807-444">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="02807-445">No Painel de Ação, selecione **Configurações da linha da etiqueta da onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-445">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="02807-446">A página **Configurações da linha da etiqueta da onda** será exibida.</span><span class="sxs-lookup"><span data-stu-id="02807-446">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="02807-447">Aqui, você pode configurar a parte dinâmica da etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-447">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="02807-448">Adicione uma linha com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-448">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="02807-449">**ID da linha:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="02807-449">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="02807-450">**Nome da tabela de linhas:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="02807-450">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="02807-451">**Posição inicial da linha:** *0*</span><span class="sxs-lookup"><span data-stu-id="02807-451">**Row start position:** *0*</span></span>

        <span data-ttu-id="02807-452">Este campo define a posição vertical na qual a linha será iniciada na etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-452">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="02807-453">**Altura da linha:** *0*</span><span class="sxs-lookup"><span data-stu-id="02807-453">**Row height:** *0*</span></span>

        <span data-ttu-id="02807-454">Este campo define a altura de cada linha (em pontos), de acordo com o padrão ZPL.</span><span class="sxs-lookup"><span data-stu-id="02807-454">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="02807-455">A altura da linha é positiva para etiquetas horizontais e negativa para etiquetas verticais.</span><span class="sxs-lookup"><span data-stu-id="02807-455">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="02807-456">Como há apenas uma linha neste exemplo, você pode definir o valor como *0* (zero).</span><span class="sxs-lookup"><span data-stu-id="02807-456">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="02807-457">**Linhas por página:** *1*</span><span class="sxs-lookup"><span data-stu-id="02807-457">**Rows per page:** *1*</span></span>

        <span data-ttu-id="02807-458">Este campo define o número de linhas que podem ser impressas em cada etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-458">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="02807-459">Esta configuração fará com que uma etiqueta ZPL separada seja impressa para cada registro na tabela de etiquetas de onda.</span><span class="sxs-lookup"><span data-stu-id="02807-459">This setup will cause a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="02807-460">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="02807-460">Close the page.</span></span>
1. <span data-ttu-id="02807-461">No Painel de Ações, selecione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="02807-461">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="02807-462">Na caixa de diálogo do editor de consultas, na guia **Intervalo**, adicione uma linha com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-462">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="02807-463">**Tabela:** *Linhas de trabalho*</span><span class="sxs-lookup"><span data-stu-id="02807-463">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="02807-464">**Tabela derivada:** *Linhas de trabalho*</span><span class="sxs-lookup"><span data-stu-id="02807-464">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="02807-465">**Campo:** *Tipo de trabalho*</span><span class="sxs-lookup"><span data-stu-id="02807-465">**Field:** *Work type*</span></span>
    - <span data-ttu-id="02807-466">**Critérios:** *Separação*</span><span class="sxs-lookup"><span data-stu-id="02807-466">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="02807-467">Esta consulta garante que somente as linhas de trabalho de separação serão impressas na etiqueta, não as linhas de trabalho de colocação.</span><span class="sxs-lookup"><span data-stu-id="02807-467">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="02807-468">Se você quiser imprimir a ID do conhecimento de embarque, na guia **Junções**, selecione a tabela **Linhas de trabalho** e junte a tabela **Remessas** a ela.</span><span class="sxs-lookup"><span data-stu-id="02807-468">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span> 
1. <span data-ttu-id="02807-469">Feche a caixa de diálogo do editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="02807-469">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="02807-470">A FastTab **Layout do texto da impressora** tem três seções nas quais é possível escrever código da impressora: **Seção do cabeçalho**, **Seção do corpo** e **Seção do rodapé**.</span><span class="sxs-lookup"><span data-stu-id="02807-470">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="02807-471">Na **Seção do cabeçalho**, no campo **Cabeçalho da etiqueta**, insira o código para o cabeçalho obrigatório.</span><span class="sxs-lookup"><span data-stu-id="02807-471">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="02807-472">Por exemplo, se você estiver usando impressoras Zebra, poderá usar o código a seguir.</span><span class="sxs-lookup"><span data-stu-id="02807-472">For example, if you're using Zebra printers, you can use the following code.</span></span>


    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA~TA000~JSN^LT0^MNW^MTT^PON^PMN^LH0,0^JMA^PR8,8~SD15^JUS^LRN^CI0^XZ
    ^XA
    ^MMT
    ^PW812
    ^LL1218
    ^LS0
    ^FT85,505^A0N,28,28^FH\^FD$WHSShipmentTable.CustomerReq$^FS
    ^FO1,173^GB809,0,1^FS
    ^FO0,391^GB809,0,1^FS
    ^FO3,599^GB809,0,2^FS
    ^FO420,176^GB0,216,1^FS
    ^FO313,3^GB0,169,1^FS
    ^FO0,807^GB809,0,1^FS
    ^FT529,370^A0N,28,26^FH\^FD$WHSShipmentTable.BillOfLadingId$^FS
    ^BY2,3,132^FT25,344^BCN,,N,N
    ^FD>:(420)>38102>63^FS
    ^FT526,315^A0N,28,28^FH\^FD ^FS
    ^FT437,248^A0N,28,28^FH\^FDCARR: $WHSShipmentTable.SCAC$^FS
    ^FT425,201^A0N,23,24^FH\^FDCARRIER:^FS
    ^FT17,68^A0N,20,19^FH\^FDIntershipping, Inc.^FS
    ^FT15,99^A0N,20,19^FH\^FD1000 Shipping Lane^FS
    ^FT16,158^A0N,20,19^FH\^FD ^FS
    ^FT438,368^A0N,28,28^FH\^FDB/L#^FS
    ^FT15,128^A0N,20,19^FH\^FDShelbyville TN 38102^FS
    ^FT19,203^A0N,23,24^FH\^FD(420) SHIP TO POSTAL CODE^FS
    ^FT331,39^A0N,28,28^FH\^FDShip To:^FS
    ^FT14,39^A0N,28,28^FH\^FDShip From:^FS
    ^FT331,67^A0N,23,24^FH\^FDWAL-MART DC 1111A-ABC DIS^FS
    ^FT330,98^A0N,23,24^FH\^FDDEPT 10^FS
    ^FT329,166^A0N,23,24^FH\^FDSpringfield TN 39021^FS
    ^FT330,134^A0N,23,24^FH\^FD100 Main Street^FS
    ^FT19,504^A0N,28,28^FH\^FDPO#:^FS
    ^FT437,316^A0N,28,28^FH\^FDPRO#^FS
    ^FT105,371^A0N,28,28^FB130,1,0,C^FH\^FD(420)39021^FS
    ```

1. <span data-ttu-id="02807-473">Na **Seção do corpo**, no campo **Corpo da etiqueta**, insira o código ZPL para o corpo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="02807-473">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="02807-474">Veja aqui um exemplo.</span><span class="sxs-lookup"><span data-stu-id="02807-474">Here is an example.</span></span>

    ```plaintext
    <Row name="WaveLabel">
    ^FT127,439^A0N,28,28^FH\^FD$WHSWaveLabel.SeqNum$^FS
    ^FT256,439^A0N,28,28^FH\^FD$WHSWaveLabel.NumberOfLabels$^FS
    ^FT17,439^A0N,28,28^FH\^FDCARTON^FS
    ^FT522,422^A0N,23,24^FH\^FDVPN:^FS
    ^FT74,1156^A0N,28,28^FH\^FDSSCC-18^FS
    ^FT21,579^A0N,28,28^FH\^FDItem name:^FS
    ^FT107,580^A0N,28,28^FH\^FD$WHSWaveLabel.LabelItemName$^FS
    ^FT576,423^A0N,23,21^FH\^FD$WHSWaveLabel.LabelItemId$^FS
    ^FT252,1155^A0N,32,31^FH\^FD(00)$WHSWaveLabel.WaveLabelId$^FS
    ^BY4,3,283^FT66,1115^BCN,,N,N
    ^FD>;>800$WHSWaveLabel.WaveLabelId$^FS
    ^FT194,439^A0N,28,28^FH\^FDof^FS
    </Row>
    ```

1. <span data-ttu-id="02807-475">Na **Seção do corpo**, no campo **Rodapé da etiqueta**, insira o código ZPL para o rodapé obrigatório.</span><span class="sxs-lookup"><span data-stu-id="02807-475">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="02807-476">Veja aqui um exemplo.</span><span class="sxs-lookup"><span data-stu-id="02807-476">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="02807-477">Esta configuração imprimirá uma cópia de cada etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-477">This setup will print one copy of each label.</span></span> <span data-ttu-id="02807-478">Se você precisar de mais cópias (por exemplo, uma cópia para cada lado do palete), defina o valor **n** para a seção **\^PQn** no rodapé como o número de cópias necessário.</span><span class="sxs-lookup"><span data-stu-id="02807-478">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="02807-479">Por exemplo, para imprimir quatro cópias de cada etiqueta, especifique **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="02807-479">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

1. <span data-ttu-id="02807-480">A primeira etiqueta agora está pronta para uso.</span><span class="sxs-lookup"><span data-stu-id="02807-480">The first label is now ready to use.</span></span>
1. <span data-ttu-id="02807-481">Crie um segundo registro de layout com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-481">Create a second layout record that has the following settings:</span></span>

    - <span data-ttu-id="02807-482">**ID do layout da etiqueta:** *Palete*</span><span class="sxs-lookup"><span data-stu-id="02807-482">**Label layout ID:** *Pallet*</span></span>
    - <span data-ttu-id="02807-483">**Descrição:** *Palete*</span><span class="sxs-lookup"><span data-stu-id="02807-483">**Description:** *Pallet*</span></span>

1. <span data-ttu-id="02807-484">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="02807-484">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="02807-485">No Painel de Ação, selecione **Configurações da linha da etiqueta da onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-485">On the Action Pane, select **Wave label row settings**.</span></span>

    <span data-ttu-id="02807-486">A página **Configurações da linha da etiqueta da onda** será exibida.</span><span class="sxs-lookup"><span data-stu-id="02807-486">The **Wave label row settings** page appears.</span></span> <span data-ttu-id="02807-487">Aqui, você pode configurar a parte dinâmica da etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-487">Here, you can configure the dynamic part of the label.</span></span>

1. <span data-ttu-id="02807-488">Adicione uma linha com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-488">Add a row that has the following settings:</span></span>

    - <span data-ttu-id="02807-489">**ID da linha:** *WaveLabel*</span><span class="sxs-lookup"><span data-stu-id="02807-489">**Row Id:** *WaveLabel*</span></span>
    - <span data-ttu-id="02807-490">**Nome da tabela de linhas:** *WHSWaveLabel*</span><span class="sxs-lookup"><span data-stu-id="02807-490">**Row table name:** *WHSWaveLabel*</span></span>
    - <span data-ttu-id="02807-491">**Posição inicial da linha:** *0*</span><span class="sxs-lookup"><span data-stu-id="02807-491">**Row start position:** *0*</span></span>

        <span data-ttu-id="02807-492">Este campo define a posição vertical na qual a linha será iniciada na etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-492">This field defines the vertical position where the row will begin on the label.</span></span>

    - <span data-ttu-id="02807-493">**Altura da linha:** *0*</span><span class="sxs-lookup"><span data-stu-id="02807-493">**Row height:** *0*</span></span>

        <span data-ttu-id="02807-494">Este campo define a altura de cada linha (em pontos), de acordo com o padrão ZPL.</span><span class="sxs-lookup"><span data-stu-id="02807-494">This field defines the height of each row (in points), according to the ZPL standard.</span></span> <span data-ttu-id="02807-495">A altura da linha é positiva para etiquetas horizontais e negativa para etiquetas verticais.</span><span class="sxs-lookup"><span data-stu-id="02807-495">The row height is positive for horizontal labels and negative for vertical labels.</span></span> <span data-ttu-id="02807-496">Como há apenas uma linha neste exemplo, você pode definir o valor como *0* (zero).</span><span class="sxs-lookup"><span data-stu-id="02807-496">Because there is just one row in this example, you can set the value to *0* (zero).</span></span>

    - <span data-ttu-id="02807-497">**Linhas por página:** *1*</span><span class="sxs-lookup"><span data-stu-id="02807-497">**Rows per page:** *1*</span></span>

        <span data-ttu-id="02807-498">Este campo define o número de linhas que podem ser impressas em cada etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-498">This field defines the number of rows that can be printed on each label.</span></span>

        > [!NOTE]
        > <span data-ttu-id="02807-499">Esta configuração faz com que uma etiqueta ZPL separada seja impressa para cada registro na tabela de etiquetas de onda.</span><span class="sxs-lookup"><span data-stu-id="02807-499">This setup causes a separate ZPL label to be printed for each record in the wave labels table.</span></span>

1. <span data-ttu-id="02807-500">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="02807-500">Close the page.</span></span>
1. <span data-ttu-id="02807-501">No Painel de Ações, selecione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="02807-501">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="02807-502">Na caixa de diálogo do editor de consultas, na guia **Intervalo**, adicione uma linha com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-502">In the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="02807-503">**Tabela:** *Linhas de trabalho*</span><span class="sxs-lookup"><span data-stu-id="02807-503">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="02807-504">**Tabela derivada:** *Linhas de trabalho*</span><span class="sxs-lookup"><span data-stu-id="02807-504">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="02807-505">**Campo:** *Tipo de trabalho*</span><span class="sxs-lookup"><span data-stu-id="02807-505">**Field:** *Work type*</span></span>
    - <span data-ttu-id="02807-506">**Critérios:** *Separação*</span><span class="sxs-lookup"><span data-stu-id="02807-506">**Criteria:** *Pick*</span></span>

    <span data-ttu-id="02807-507">Esta consulta garante que somente as linhas de trabalho de separação serão impressas na etiqueta, não as linhas de trabalho de colocação.</span><span class="sxs-lookup"><span data-stu-id="02807-507">This query ensures that only pick-type work lines will be printed on the label, not put-type work lines.</span></span>

1. <span data-ttu-id="02807-508">Se você quiser imprimir a ID do conhecimento de embarque, na guia **Junções**, selecione a tabela **Linhas de trabalho** e junte a tabela **Remessas** a ela.</span><span class="sxs-lookup"><span data-stu-id="02807-508">If you want to be able to print the bill of lading ID, on the **Joins** tab, select the **Work lines** table, and join the **Shipments** table to it.</span></span>
1. <span data-ttu-id="02807-509">Feche a caixa de diálogo do editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="02807-509">Close the query editor dialog box.</span></span>
1. <span data-ttu-id="02807-510">A FastTab **Layout do texto da impressora** tem três seções nas quais é possível escrever código da impressora: **Seção do cabeçalho**, **Seção do corpo** e **Seção do rodapé**.</span><span class="sxs-lookup"><span data-stu-id="02807-510">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="02807-511">Na **Seção do cabeçalho**, no campo **Cabeçalho da etiqueta**, insira o código para o cabeçalho obrigatório.</span><span class="sxs-lookup"><span data-stu-id="02807-511">In the **Header section** section, in the **Label header** field, enter code for the required header.</span></span> <span data-ttu-id="02807-512">Por exemplo, se você estiver usando impressoras Zebra, poderá usar o código a seguir.</span><span class="sxs-lookup"><span data-stu-id="02807-512">For example, if you're using Zebra printers, you can use the following code.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWaveLabel.WaveLabelId$ ^FS
    ^FO0,75 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ^FO0,150 ^AT ^FD$WHSShipmentTable.BillOfLadingId$ ^FS
    ```

1. <span data-ttu-id="02807-513">Na **Seção do corpo**, no campo **Corpo da etiqueta**, insira o código ZPL para o corpo obrigatório.</span><span class="sxs-lookup"><span data-stu-id="02807-513">In the **Body section** section, in the **Label body** field, enter ZPL code for the required body.</span></span> <span data-ttu-id="02807-514">Veja aqui um exemplo.</span><span class="sxs-lookup"><span data-stu-id="02807-514">Here is an example.</span></span>

    ```plaintext
    <Row name="WaveLabel">
    ^FO0,450 ^AT ^FDItem ^FS
    ^FO200,450 ^AT ^FDQuantity ^FS
    ^FO0,[[YPos]] ^AT ^FD$WHSWaveLabel.LabelItemId$ ^FS
    ^FO200,[[YPos]] ^AT ^FD$WHSWaveLabel.QtyWork$ ^FS
    </Row>
    ```

1. <span data-ttu-id="02807-515">Na **Seção do corpo**, no campo **Rodapé da etiqueta**, insira o código ZPL para o rodapé obrigatório.</span><span class="sxs-lookup"><span data-stu-id="02807-515">In the **Body section** section, in the **Label footer** field, enter ZPL code for the required footer.</span></span> <span data-ttu-id="02807-516">Veja aqui um exemplo.</span><span class="sxs-lookup"><span data-stu-id="02807-516">Here is an example.</span></span>

    ```plaintext
    ^PQ1^XZ
    ```

    > [!NOTE]
    > <span data-ttu-id="02807-517">Esta configuração imprimirá uma cópia de cada etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-517">This setup will print one copy of each label.</span></span> <span data-ttu-id="02807-518">Se você precisar de mais cópias (por exemplo, uma cópia para cada lado do palete), defina o valor **n** para a seção **\^PQn** no rodapé como o número de cópias necessário.</span><span class="sxs-lookup"><span data-stu-id="02807-518">If you require more copies (for example, one copy for each side of the pallet), set the **n** value for the **\^PQn** section in the footer to the required number of copies.</span></span> <span data-ttu-id="02807-519">Por exemplo, para imprimir quatro cópias de cada etiqueta, especifique **\^PQ4**.</span><span class="sxs-lookup"><span data-stu-id="02807-519">For example, to print four copies of each label, specify **\^PQ4**.</span></span>

1. <span data-ttu-id="02807-520">A segunda etiqueta agora está pronta para uso.</span><span class="sxs-lookup"><span data-stu-id="02807-520">The second label is now ready to use.</span></span>
1. <span data-ttu-id="02807-521">Crie um terceiro registro de layout com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-521">Create a third layout record that has the following settings:</span></span>

    - <span data-ttu-id="02807-522">**ID do layout da etiqueta:** *Intervalo*</span><span class="sxs-lookup"><span data-stu-id="02807-522">**Label layout ID:** *Break*</span></span>
    - <span data-ttu-id="02807-523">**Descrição:** *Etiqueta de intervalo*</span><span class="sxs-lookup"><span data-stu-id="02807-523">**Description:** *Break label*</span></span>

1. <span data-ttu-id="02807-524">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="02807-524">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="02807-525">A FastTab **Layout do texto da impressora** tem três seções nas quais é possível escrever código da impressora: **Seção do cabeçalho**, **Seção do corpo** e **Seção do rodapé**.</span><span class="sxs-lookup"><span data-stu-id="02807-525">The **Printer text Layout** FastTab has three sections where you can write printer code: **Header section**, **Body section**, and **Footer section**.</span></span> <span data-ttu-id="02807-526">Na **Seção do cabeçalho**, no campo **Cabeçalho da etiqueta**, insira o código ZPL para o cabeçalho obrigatório.</span><span class="sxs-lookup"><span data-stu-id="02807-526">In the **Header section** section, in the **Label header** field, enter ZPL code for the required header.</span></span> <span data-ttu-id="02807-527">Veja aqui um exemplo.</span><span class="sxs-lookup"><span data-stu-id="02807-527">Here is an example.</span></span>

    ```plaintext
    CT~~CD,~CC^~CT~
    ^XA
    ^LH10,10
    ^FO0,0 ^AT ^FD$WHSWorkLine.ShipmentId$ ^FS
    ```

1. <span data-ttu-id="02807-528">Desta vez, o corpo não é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="02807-528">This time, no body is required.</span></span> <span data-ttu-id="02807-529">Portanto, basta inserir o texto obrigatório na **Seção de rodapé**.</span><span class="sxs-lookup"><span data-stu-id="02807-529">Therefore, just enter the required text in the **Footer section** section.</span></span> <span data-ttu-id="02807-530">Veja aqui um exemplo.</span><span class="sxs-lookup"><span data-stu-id="02807-530">Here is an example.</span></span>

    ```plaintext
    ^XZ
    ```

    <span data-ttu-id="02807-531">A terceira etiqueta agora está pronta para uso.</span><span class="sxs-lookup"><span data-stu-id="02807-531">The third label is now ready to use.</span></span>

    > [!NOTE]
    > <span data-ttu-id="02807-532">Essa terceira etiqueta é uma etiqueta de intervalo que será usada como um divisor entre os rolos de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="02807-532">This third label is a break label that will be used as a divider between label rolls.</span></span>

### <a name="create-two-wave-label-types"></a><span data-ttu-id="02807-533">Criar dois tipos de etiqueta de onda</span><span class="sxs-lookup"><span data-stu-id="02807-533">Create two wave label types</span></span>

1. <span data-ttu-id="02807-534">Vá para **Gerenciamento de depósito \> Configuração \> Roteamento de documentos \> Tipos de etiqueta de onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-534">Go to **Warehouse management \> Setup \> Document routing \> Wave label types**.</span></span>
1. <span data-ttu-id="02807-535">Crie um registro com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-535">Create a record that has the following settings:</span></span>

    - <span data-ttu-id="02807-536">**Tipo de etiqueta:** *Caixa*</span><span class="sxs-lookup"><span data-stu-id="02807-536">**Label type:** *Carton*</span></span>
    - <span data-ttu-id="02807-537">**Descrição:** *Caixa*</span><span class="sxs-lookup"><span data-stu-id="02807-537">**Description:** *Carton*</span></span>

1. <span data-ttu-id="02807-538">Crie um segundo registro com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-538">Create a second record that has the following settings:</span></span>

    - <span data-ttu-id="02807-539">**Tipo de etiqueta:** *Palete*</span><span class="sxs-lookup"><span data-stu-id="02807-539">**Label type:** *Pallet*</span></span>
    - <span data-ttu-id="02807-540">**Descrição:** *Palete*</span><span class="sxs-lookup"><span data-stu-id="02807-540">**Description:** *Pallet*</span></span>

### <a name="set-up-unit-sequence-groups"></a><span data-ttu-id="02807-541">Configurar grupos de sequências de unidade</span><span class="sxs-lookup"><span data-stu-id="02807-541">Set up unit sequence groups</span></span>

1. <span data-ttu-id="02807-542">Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Grupos de sequências de unidade**.</span><span class="sxs-lookup"><span data-stu-id="02807-542">Go to **Warehouse management \> Setup \> Warehouse \> Unit sequence groups**.</span></span>
1. <span data-ttu-id="02807-543">Selecione ou crie um grupo **Ea Caixa PL**.</span><span class="sxs-lookup"><span data-stu-id="02807-543">Select or create an **Ea Box PL** group.</span></span>
1. <span data-ttu-id="02807-544">Para a linha **Caixa**, defina o campo **Tipo de nível de onda** como *Caixa*.</span><span class="sxs-lookup"><span data-stu-id="02807-544">For the **Box** line, set the **Wave level type** field to *Carton*.</span></span>
1. <span data-ttu-id="02807-545">Para a linha **PL**, defina o campo **Tipo de nível de onda** como *Palete*.</span><span class="sxs-lookup"><span data-stu-id="02807-545">For the **PL** line, set the **Wave level type** field to *Pallet*.</span></span>

### <a name="create-wave-label-templates"></a><span data-ttu-id="02807-546">Criar modelos de etiqueta de onda</span><span class="sxs-lookup"><span data-stu-id="02807-546">Create wave label templates</span></span>

1. <span data-ttu-id="02807-547">Vá para **Gerenciamento de depósito \> Configuração \> Roteamento de documentos \> Modelos de etiqueta de onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-547">Go to **Warehouse management \> Setup \> Document routing \> Wave label templates**.</span></span>
1. <span data-ttu-id="02807-548">Crie um modelo de etiqueta com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-548">Create a label template that has the following settings:</span></span>

    - <span data-ttu-id="02807-549">**Nome do modelo de etiqueta:** *Etiquetas de caixa*</span><span class="sxs-lookup"><span data-stu-id="02807-549">**Label template name:** *Carton labels*</span></span>
    - <span data-ttu-id="02807-550">**Descrição:** *Etiquetas de caixa*</span><span class="sxs-lookup"><span data-stu-id="02807-550">**Description:** *Carton labels*</span></span>
    - <span data-ttu-id="02807-551">**Código da etapa da onda:** *Caixa*</span><span class="sxs-lookup"><span data-stu-id="02807-551">**Wave step code:** *Carton*</span></span>
    - <span data-ttu-id="02807-552">**Depósito:** *62*</span><span class="sxs-lookup"><span data-stu-id="02807-552">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="02807-553">Na FastTab **Geral**, no campo **Tipo de etiqueta de onda**, selecione um valor, como *Caixa*.</span><span class="sxs-lookup"><span data-stu-id="02807-553">On the **General** FastTab, in the **Wave label type** field, select a value, such as *Carton*.</span></span>
1. <span data-ttu-id="02807-554">Na FastTab **Detalhes do modelo de etiqueta de onda**, adicione uma linha com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-554">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="02807-555">**ID do layout da etiqueta:** *Caixa*</span><span class="sxs-lookup"><span data-stu-id="02807-555">**Label layout ID:** *Carton*</span></span>
    - <span data-ttu-id="02807-556">**Nome da impressora:** Selecione uma impressora ZPL apropriada.</span><span class="sxs-lookup"><span data-stu-id="02807-556">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="02807-557">**Executar consulta:** *Sim* (esta configuração é opcional, mas recomendável para um desempenho ideal.)</span><span class="sxs-lookup"><span data-stu-id="02807-557">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="02807-558">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="02807-558">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="02807-559">Opcional: se estiver configurando um design de etiqueta específico do cliente, você deve criar uma consulta para localizar a conta do cliente.</span><span class="sxs-lookup"><span data-stu-id="02807-559">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="02807-560">Na FastTab **Detalhes do modelo de etiqueta de onda**, selecione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="02807-560">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="02807-561">Em seguida, na caixa de diálogo do editor de consultas, na guia **Intervalo**, adicione uma linha com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-561">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="02807-562">**Tabela:** *Remessas*</span><span class="sxs-lookup"><span data-stu-id="02807-562">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="02807-563">**Tabela derivada:** *Remessas*</span><span class="sxs-lookup"><span data-stu-id="02807-563">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="02807-564">**Campo:** *Número da conta*</span><span class="sxs-lookup"><span data-stu-id="02807-564">**Field:** *Account number*</span></span>
    - <span data-ttu-id="02807-565">**Critérios:** Insira o número da conta do cliente relevante.</span><span class="sxs-lookup"><span data-stu-id="02807-565">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="02807-566">Quando terminar, selecione **OK** para fechar a caixa de diálogo do editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="02807-566">When you've finished, select **OK** to close the query editor dialog box.</span></span>

1. <span data-ttu-id="02807-567">No Painel de Ação, selecione **Editar consulta** para abrir a caixa de diálogo do editor de consultas para todo o modelo de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-567">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="02807-568">Na caixa de diálogo do editor de consultas, na guia **Classificação**, adicione uma linha com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-568">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="02807-569">**Tabela:** *Linhas de trabalho*</span><span class="sxs-lookup"><span data-stu-id="02807-569">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="02807-570">**Tabela derivada:** *Linhas de trabalho*</span><span class="sxs-lookup"><span data-stu-id="02807-570">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="02807-571">**Campo:** *ID da linha de carga de referência (ID do Registro)*</span><span class="sxs-lookup"><span data-stu-id="02807-571">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="02807-572">**Direção da pesquisa:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="02807-572">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="02807-573">Adicione uma segunda linha com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-573">Add a second row that has the following settings:</span></span>

    - <span data-ttu-id="02807-574">**Tabela:** *Linhas de trabalho*</span><span class="sxs-lookup"><span data-stu-id="02807-574">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="02807-575">**Tabela derivada:** *Linhas de trabalho*</span><span class="sxs-lookup"><span data-stu-id="02807-575">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="02807-576">**Campo:** *ID da Remessa*</span><span class="sxs-lookup"><span data-stu-id="02807-576">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="02807-577">**Direção da pesquisa:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="02807-577">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="02807-578">Selecione **OK** para fechar a caixa de diálogo do editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="02807-578">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="02807-579">Uma caixa de mensagem solicitará que você confirme a operação de redefinição do agrupamento.</span><span class="sxs-lookup"><span data-stu-id="02807-579">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="02807-580">Selecione **Sim** para continuar.</span><span class="sxs-lookup"><span data-stu-id="02807-580">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="02807-581">No Painel de Ação, selecione **Grupo de modelos de etiqueta de onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-581">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="02807-582">Na caixa de diálogo **Grupo de modelos de etiqueta de onda**, para a linha na qual o campo **Nome do campo de referência** está definido como *ID da Remessa*, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="02807-582">In the **Wave label template group** dialog box, for the row where the **Reference field name** field is set to *Shipment ID*, set the following values:</span></span>

    - <span data-ttu-id="02807-583">**Imprimir etiqueta de intervalo:** Marque esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="02807-583">**Print break label:** Select this check box.</span></span>
    - <span data-ttu-id="02807-584">**ID do layout da etiqueta:** Selecione uma etiqueta de intervalo.</span><span class="sxs-lookup"><span data-stu-id="02807-584">**Label layout ID:** Select a break label.</span></span> <span data-ttu-id="02807-585">(Por exemplo, selecione o layout da etiqueta *Intervalo* criado anteriormente neste cenário.)</span><span class="sxs-lookup"><span data-stu-id="02807-585">(For example, select the *Break* label layout that you created earlier in this scenario.)</span></span>
    - <span data-ttu-id="02807-586">**Nome da impressora:** Selecione a impressora para a etiqueta de intervalo.</span><span class="sxs-lookup"><span data-stu-id="02807-586">**Printer name:** Select the printer for the break label.</span></span> <span data-ttu-id="02807-587">(Normalmente, para dividir os rolos de etiquetas, você deve selecionar a mesma impressora selecionada na FastTab **Detalhes do modelo de etiqueta de onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-587">(Typically, for the purpose of splitting label rolls, you should select the same printer that is selected on the **Wave label template details** FastTab.</span></span> <span data-ttu-id="02807-588">No entanto, outros cenários são possíveis.)</span><span class="sxs-lookup"><span data-stu-id="02807-588">However, other scenarios are possible.)</span></span>

1. <span data-ttu-id="02807-589">Para a linha na qual o campo **Nome do campo de referência** está definido como *ID da linha de carga de referência*, marque a caixa de seleção **ID de criação da etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="02807-589">For the row where the **Reference field name** field is set to *Reference load line id*, select the **Label build ID** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="02807-590">Essa configuração criará uma sequência de etiquetas ("Caixa 1 de X") por linha de carga ao longo da onda, independentemente da configuração do agrupamento de trabalho.</span><span class="sxs-lookup"><span data-stu-id="02807-590">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="02807-591">Essa sequência de etiquetas pode ser impressa em um layout de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-591">This label sequence can be printed on a label layout.</span></span> <span data-ttu-id="02807-592">Além disso, etiquetas de remessas diferentes serão separadas pela etiqueta de intervalo selecionada.</span><span class="sxs-lookup"><span data-stu-id="02807-592">Additionally, labels for different shipments will be separated by the selected break label.</span></span>

1. <span data-ttu-id="02807-593">Selecione **OK** para fechar a caixa de diálogo **Grupo de modelos de etiqueta de onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-593">Select **OK** to close the **Wave label template group** dialog box.</span></span>
1. <span data-ttu-id="02807-594">Crie um segundo modelo de etiqueta com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-594">Create a second label template that has the following settings:</span></span>

    - <span data-ttu-id="02807-595">**Nome do modelo de etiqueta:** *Etiquetas de palete*</span><span class="sxs-lookup"><span data-stu-id="02807-595">**Label template name:** *Pallet labels*</span></span>
    - <span data-ttu-id="02807-596">**Descrição:** *Etiquetas de palete*</span><span class="sxs-lookup"><span data-stu-id="02807-596">**Description:** *Pallet labels*</span></span>
    - <span data-ttu-id="02807-597">**Código da etapa da onda:** *Palete*</span><span class="sxs-lookup"><span data-stu-id="02807-597">**Wave step code:** *Pallet*</span></span>
    - <span data-ttu-id="02807-598">**Depósito:** *62*</span><span class="sxs-lookup"><span data-stu-id="02807-598">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="02807-599">Na FastTab **Geral**, no campo **Tipo de etiqueta de onda**, selecione um valor, como *Palete*.</span><span class="sxs-lookup"><span data-stu-id="02807-599">On the **General** FastTab, in the **Wave label type** field, select a value, such as *Pallet*.</span></span>
1. <span data-ttu-id="02807-600">Na FastTab **Detalhes do modelo de etiqueta de onda**, adicione uma linha com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-600">On the **Wave label template details** FastTab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="02807-601">**ID do layout da etiqueta:** *Palete*</span><span class="sxs-lookup"><span data-stu-id="02807-601">**Label layout ID:** *Pallet*</span></span>
    - <span data-ttu-id="02807-602">**Nome da impressora:** Selecione uma impressora ZPL apropriada.</span><span class="sxs-lookup"><span data-stu-id="02807-602">**Printer name:** Select an appropriate ZPL printer.</span></span>
    - <span data-ttu-id="02807-603">**Executar consulta:** *Sim* (esta configuração é opcional, mas recomendável para um desempenho ideal.)</span><span class="sxs-lookup"><span data-stu-id="02807-603">**Run query:** *Yes* (This setting is optional, but it's recommended for optimal performance.)</span></span>

1. <span data-ttu-id="02807-604">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="02807-604">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="02807-605">Opcional: se estiver configurando um design de etiqueta específico do cliente, você deve criar uma consulta para localizar a conta do cliente.</span><span class="sxs-lookup"><span data-stu-id="02807-605">Optional: If you're setting up a customer-specific label design, you must create a query to find the customer's account.</span></span> <span data-ttu-id="02807-606">Na FastTab **Detalhes do modelo de etiqueta de onda**, selecione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="02807-606">On the **Wave label template details** FastTab, select **Edit query**.</span></span> <span data-ttu-id="02807-607">Em seguida, na caixa de diálogo do editor de consultas, na guia **Intervalo**, adicione uma linha com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-607">Then, in the query editor dialog box, on the **Range** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="02807-608">**Tabela:** *Remessas*</span><span class="sxs-lookup"><span data-stu-id="02807-608">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="02807-609">**Tabela derivada:** *Remessas*</span><span class="sxs-lookup"><span data-stu-id="02807-609">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="02807-610">**Campo:** *Número da conta*</span><span class="sxs-lookup"><span data-stu-id="02807-610">**Field:** *Account number*</span></span>
    - <span data-ttu-id="02807-611">**Critérios:** Insira o número da conta do cliente relevante.</span><span class="sxs-lookup"><span data-stu-id="02807-611">**Criteria:** Enter the relevant customer account number.</span></span>

    <span data-ttu-id="02807-612">Quando terminar, selecione **OK** para fechar a caixa de diálogo do editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="02807-612">When you've finished, select **OK** to close the query editor dialog box.</span></span> 

1. <span data-ttu-id="02807-613">No Painel de Ação, selecione **Editar consulta** para abrir a caixa de diálogo do editor de consultas para todo o modelo de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-613">On the Action Pane, select **Edit query** to open the query editor dialog box for the whole label template.</span></span>
1. <span data-ttu-id="02807-614">Na caixa de diálogo do editor de consultas, na guia **Classificação**, adicione uma linha com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-614">In the query editor dialog box, on the **Sorting** tab, add a row that has the following settings:</span></span>

    - <span data-ttu-id="02807-615">**Tabela:** *Linhas de trabalho*</span><span class="sxs-lookup"><span data-stu-id="02807-615">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="02807-616">**Tabela derivada:** *Linhas de trabalho*</span><span class="sxs-lookup"><span data-stu-id="02807-616">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="02807-617">**Campo:** *ID da linha de carga de referência (ID do Registro)*</span><span class="sxs-lookup"><span data-stu-id="02807-617">**Field:** *Reference load line id (Record-ID)*</span></span>
    - <span data-ttu-id="02807-618">**Direção da pesquisa:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="02807-618">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="02807-619">Adicione uma segunda linha com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-619">Add a second row that has the following settings:</span></span>

    - <span data-ttu-id="02807-620">**Tabela:** *Linhas de trabalho*</span><span class="sxs-lookup"><span data-stu-id="02807-620">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="02807-621">**Tabela derivada:** *Linhas de trabalho*</span><span class="sxs-lookup"><span data-stu-id="02807-621">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="02807-622">**Campo:** *ID da Remessa*</span><span class="sxs-lookup"><span data-stu-id="02807-622">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="02807-623">**Direção da pesquisa:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="02807-623">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="02807-624">Selecione **OK** para fechar a caixa de diálogo do editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="02807-624">Select **OK** to close the query editor dialog box.</span></span>
1. <span data-ttu-id="02807-625">Uma caixa de mensagem solicitará que você confirme a operação de redefinição do agrupamento.</span><span class="sxs-lookup"><span data-stu-id="02807-625">A message box prompts you to confirm the grouping reset operation.</span></span> <span data-ttu-id="02807-626">Selecione **Sim** para continuar.</span><span class="sxs-lookup"><span data-stu-id="02807-626">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="02807-627">No Painel de Ação, selecione **Grupo de modelos de etiqueta de onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-627">On the Action Pane, select **Wave label template group**.</span></span>
1. <span data-ttu-id="02807-628">Na caixa de diálogo **Grupo de modelos de etiqueta de onda**, para a linha na qual o campo **Nome do campo de referência** está definido como *ID da Remessa*, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="02807-628">In the **Wave label template group** dialog box, for the row where the **Reference field name** field is set to *Shipment ID*, set the following values:</span></span>

    - <span data-ttu-id="02807-629">**Imprimir etiqueta de intervalo:** Marque esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="02807-629">**Print break label:** Select this check box.</span></span>
    - <span data-ttu-id="02807-630">**ID do layout da etiqueta:** Selecione uma etiqueta de intervalo.</span><span class="sxs-lookup"><span data-stu-id="02807-630">**Label layout ID:** Select a break label.</span></span> <span data-ttu-id="02807-631">(Por exemplo, selecione o layout da etiqueta *Intervalo* criado anteriormente neste cenário.)</span><span class="sxs-lookup"><span data-stu-id="02807-631">(For example, select the *Break* label layout that you created earlier in this scenario.)</span></span>
    - <span data-ttu-id="02807-632">**Nome da impressora:** Selecione a impressora para a etiqueta de intervalo.</span><span class="sxs-lookup"><span data-stu-id="02807-632">**Printer name:** Select the printer for the break label.</span></span> <span data-ttu-id="02807-633">(Normalmente, para dividir os rolos de etiquetas, você deve selecionar a mesma impressora selecionada na FastTab **Detalhes do modelo de etiqueta de onda**.</span><span class="sxs-lookup"><span data-stu-id="02807-633">(Typically, for the purpose of splitting label rolls, you should select the same printer that is selected on the **Wave label template details** FastTab.</span></span> <span data-ttu-id="02807-634">No entanto, outros cenários são possíveis.)</span><span class="sxs-lookup"><span data-stu-id="02807-634">However, other scenarios are possible.)</span></span>

1. <span data-ttu-id="02807-635">Para a linha na qual o campo **Nome do campo de referência** está definido como *ID da linha de carga de referência*, marque a caixa de seleção **ID de criação da etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="02807-635">For the row where the **Reference field name** field is set to *Reference load line id*, select the **Label build ID** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="02807-636">Essa configuração criará uma sequência de etiquetas ("Caixa 1 de X") por linha de carga ao longo da onda, independentemente da configuração do agrupamento de trabalho.</span><span class="sxs-lookup"><span data-stu-id="02807-636">This setup will create one label sequence ("Carton 1 of X") per load line throughout the wave, regardless of the work grouping setup.</span></span> <span data-ttu-id="02807-637">Essa sequência de etiquetas pode ser impressa em um layout de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-637">This label sequence can be printed on a label layout.</span></span> <span data-ttu-id="02807-638">Além disso, etiquetas de remessas diferentes serão separadas pela etiqueta de intervalo selecionada.</span><span class="sxs-lookup"><span data-stu-id="02807-638">Additionally, labels for different shipments will be separated by the selected break label.</span></span>

### <a name="configure-number-sequence-extensions"></a><span data-ttu-id="02807-639">Configurar extensões de sequência numérica</span><span class="sxs-lookup"><span data-stu-id="02807-639">Configure number sequence extensions</span></span>

<span data-ttu-id="02807-640">As extensões de sequência numérica controlam a conformidade com o GS1 de sequências numéricas específicas.</span><span class="sxs-lookup"><span data-stu-id="02807-640">Number sequence extensions control the GS1 compliance of specific number sequences.</span></span> <span data-ttu-id="02807-641">Esta configuração é opcional para o cenário atual.</span><span class="sxs-lookup"><span data-stu-id="02807-641">This configuration is optional for the current scenario.</span></span> <span data-ttu-id="02807-642">Para obter mais informações e instruções de configuração, consulte [Configurar extensões de sequência numérica](../warehousing/configure-number-sequence-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="02807-642">For more information and configuration instructions, see [Configure number sequence extensions](../warehousing/configure-number-sequence-extensions.md).</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="02807-643">Criar uma ordem de venda e liberá-la para o depósito</span><span class="sxs-lookup"><span data-stu-id="02807-643">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="02807-644">Vá para **Vendas e marketing \> Ordem de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="02807-644">Go to **Sales and marketing \> Sales order \> All sales orders**.</span></span>
1. <span data-ttu-id="02807-645">Crie uma ordem de venda com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="02807-645">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="02807-646">**Conta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="02807-646">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="02807-647">**Depósito:** *62*</span><span class="sxs-lookup"><span data-stu-id="02807-647">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="02807-648">Adicione duas linhas da ordem de venda:</span><span class="sxs-lookup"><span data-stu-id="02807-648">Add two sales order lines:</span></span>

    - <span data-ttu-id="02807-649">Linha 1 da ordem de venda:</span><span class="sxs-lookup"><span data-stu-id="02807-649">Sales order line 1:</span></span>

        - <span data-ttu-id="02807-650">**Número de item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="02807-650">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="02807-651">**Quantidade:** *9024*</span><span class="sxs-lookup"><span data-stu-id="02807-651">**Quantity:** *9024*</span></span>
        - <span data-ttu-id="02807-652">**Unidade:** *ea* (9024 ea = 376 Caixa = 47 PL)</span><span class="sxs-lookup"><span data-stu-id="02807-652">**Unit:** *ea* (9024 ea = 376 Box = 47 PL)</span></span>

    - <span data-ttu-id="02807-653">Linha 2 da ordem de venda:</span><span class="sxs-lookup"><span data-stu-id="02807-653">Sales order line 2:</span></span>

        - <span data-ttu-id="02807-654">**Número de item:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="02807-654">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="02807-655">**Quantidade:** *9016*</span><span class="sxs-lookup"><span data-stu-id="02807-655">**Quantity:** *9016*</span></span>
        - <span data-ttu-id="02807-656">**Unidade:** *ea* (9016 ea = 322 Caixa = 46 PL)</span><span class="sxs-lookup"><span data-stu-id="02807-656">**Unit:** *ea* (9016 ea = 322 Box = 46 PL)</span></span>

    > [!NOTE]
    > <span data-ttu-id="02807-657">Os itens e as quantidades fornecidos aqui são apenas exemplos.</span><span class="sxs-lookup"><span data-stu-id="02807-657">The items and quantities that are provided here are only examples.</span></span> <span data-ttu-id="02807-658">Eles devem usar o grupo de sequências de unidade definido anteriormente, conversões de unidade apropriadas de *ea* para *Caixa* para *PL* devem ser definidas para eles, e eles devem ter estoque no depósito *62*.</span><span class="sxs-lookup"><span data-stu-id="02807-658">They must use the unit sequence group that you defined earlier, appropriate unit conversions from *ea* to *Box* to *PL* must be defined for them, and they must have stock in warehouse *62*.</span></span> <span data-ttu-id="02807-659">Para obter mais informações, consulte [Políticas de unidade de medida e estoque](unit-measure-stocking-policies.md).</span><span class="sxs-lookup"><span data-stu-id="02807-659">For more information, see [Unit of measure and stocking policies](unit-measure-stocking-policies.md).</span></span>

1. <span data-ttu-id="02807-660">Selecione a linha 1 da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="02807-660">Select sales order line 1.</span></span> <span data-ttu-id="02807-661">Em seguida, na seção **Linha da ordem de venda**, no menu **Estoque**, selecione **Reservas**.</span><span class="sxs-lookup"><span data-stu-id="02807-661">Then, in the **Sales order line** section, on the **Inventory** menu, select **Reservations**.</span></span>
1. <span data-ttu-id="02807-662">Na página **Reserva**, no Painel de Ação, selecione **Reservar lote** e, em seguida, feche a página.</span><span class="sxs-lookup"><span data-stu-id="02807-662">On the **Reservation** page, on the Action Pane, select **Reserve lot**, and then close the page.</span></span>
1. <span data-ttu-id="02807-663">Repita as etapas 4 e 5 para a linha 2 da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="02807-663">Repeat steps 4 and 5 for sales order line 2.</span></span>
1. <span data-ttu-id="02807-664">No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="02807-664">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="02807-665">Os seguintes eventos ocorrem:</span><span class="sxs-lookup"><span data-stu-id="02807-665">The following events occur:</span></span> 

    - <span data-ttu-id="02807-666">O sistema processa a remessa criada usando o modelo que inclui a etapa de impressão de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="02807-666">The system processes the created shipment by using the template that includes the label printing step.</span></span> <span data-ttu-id="02807-667">O layout da etiqueta será usado para definir o formato da etiqueta, e o resultado será uma etiqueta impressa na impressora selecionada no modelo de etiqueta.</span><span class="sxs-lookup"><span data-stu-id="02807-667">The label layout will be used to define the format of the label, and the result will be a label that is printed on the printer that is selected in the label template.</span></span>
    - <span data-ttu-id="02807-668">Etiquetas de onda são geradas e impressas.</span><span class="sxs-lookup"><span data-stu-id="02807-668">Wave labels are generated and printed.</span></span> <span data-ttu-id="02807-669">O número de etiquetas será igual ao número de caixas (neste exemplo, 376 etiquetas Caixa para a linha 1, 322 etiquetas Caixa para a linha 2, 47 etiquetas PL para a linha 1, 47 etiquetas PL para a linha 2 e duas etiquetas de intervalo com a ID de remessa).</span><span class="sxs-lookup"><span data-stu-id="02807-669">The number of labels will equal the number of cartons (in this example, 376 Box labels for line 1, 322 Box labels for line 2, 47 PL labels for line 1, 47 PL labels for line 2, and two break labels that have the shipment ID).</span></span>
    - <span data-ttu-id="02807-670">Uma nova ID de conhecimento de embarque é gerada para as remessas.</span><span class="sxs-lookup"><span data-stu-id="02807-670">A new bill of lading ID is generated for the shipments.</span></span> <span data-ttu-id="02807-671">Se você configurou as extensões de sequência numérica, as IDs de etiqueta de onda seguirão o formato numérico de **SSCC-18**.</span><span class="sxs-lookup"><span data-stu-id="02807-671">If you configured the number sequence extensions, the wave label IDs will follow the **SSCC-18** number format.</span></span> 

<span data-ttu-id="02807-672">Você pode exibir e reimprimir etiquetas de onda nas páginas a seguir:</span><span class="sxs-lookup"><span data-stu-id="02807-672">You can view and reprint wave labels from the following pages:</span></span>

- <span data-ttu-id="02807-673">Todas as remessas \> Detalhes da remessa</span><span class="sxs-lookup"><span data-stu-id="02807-673">All shipments \> Shipment details</span></span>
- <span data-ttu-id="02807-674">Todas as cargas \> Detalhes da carga</span><span class="sxs-lookup"><span data-stu-id="02807-674">All loads \> Load details</span></span>
- <span data-ttu-id="02807-675">Todas as ondas</span><span class="sxs-lookup"><span data-stu-id="02807-675">All waves</span></span>
- <span data-ttu-id="02807-676">Etiquetas de onda</span><span class="sxs-lookup"><span data-stu-id="02807-676">Wave labels</span></span>
- <span data-ttu-id="02807-677">Histórico da etiqueta de onda</span><span class="sxs-lookup"><span data-stu-id="02807-677">Wave label history</span></span>

<span data-ttu-id="02807-678">Para a maioria dessas páginas, você pode encontrar a função relevante selecionando **Etiquetas de onda** no grupo **Informações relacionadas** na guia **Remessas** do Painel de Ação.</span><span class="sxs-lookup"><span data-stu-id="02807-678">For most of these pages, you can find the relevant function by selecting **Wave labels** in the **Related information** group on the **Shipments** tab of the Action Pane.</span></span>