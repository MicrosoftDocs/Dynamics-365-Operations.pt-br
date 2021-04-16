---
title: Suporte a chamadas parametrizadas de fontes de dados de ER do tipo Campo calculado
description: Este tópico fornece informações sobre como usar o tipo Campo calculado de fontes de dados de ER.
author: NickSelin
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 897133a27f9d3da2f576ce675c0949f824cde881
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749480"
---
# <a name="support-parameterized-calls-of-er-data-sources-of-the-calculated-field-type"></a><span data-ttu-id="264f7-103">Suporte a chamadas parametrizadas de fontes de dados de ER do tipo Campo calculado</span><span class="sxs-lookup"><span data-stu-id="264f7-103">Support parameterized calls of ER data sources of the Calculated field type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="264f7-104">Este tópico explica como você pode criar uma fonte de dados relatório eletrônico (ER) usando o tipo **Campo calculado**.</span><span class="sxs-lookup"><span data-stu-id="264f7-104">This topic explains how you can design an Electronic reporting (ER) data source by using the **Calculated field** type.</span></span> <span data-ttu-id="264f7-105">Essa fonte de dados pode conter uma expressão de ER que, quando executada, pode ser controlada pelos valores de argumentos do parâmetro configurados em uma associação que chama essa fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="264f7-105">This data source may contain an ER expression that, when executed, can be controlled by the values of the parameter arguments that are configured in a binding that calls this data source.</span></span> <span data-ttu-id="264f7-106">Ao configurar chamadas parametrizadas dessa fonte de dados, você pode reutilizar uma única fonte de dados em muitas associações, o que reduz o número total de fontes de dados que devem ser configuradas em mapeamentos de modelos de ER ou em formatos de ER.</span><span class="sxs-lookup"><span data-stu-id="264f7-106">By configuring parameterized calls of such a data source, you can reuse a single data source in many bindings, which reduces the total number of data sources that must be configured in ER model mappings or ER formats.</span></span> <span data-ttu-id="264f7-107">Isso também simplifica o componente de ER configurado, o que reduz os custos de manutenção e os custos de utilização por outros consumidores.</span><span class="sxs-lookup"><span data-stu-id="264f7-107">It also simplifies the configured ER component, which reduces the maintenance costs and the cost of use by other consumers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="264f7-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="264f7-108">Prerequisites</span></span>
<span data-ttu-id="264f7-109">Para concluir os exemplos neste tópico, você deve ter o seguinte acesso:</span><span class="sxs-lookup"><span data-stu-id="264f7-109">To complete the examples in this topic, you must have the following access:</span></span>

- <span data-ttu-id="264f7-110">Acesso a uma destas funções:</span><span class="sxs-lookup"><span data-stu-id="264f7-110">Access to one of these roles:</span></span>

    - <span data-ttu-id="264f7-111">Desenvolvedor de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="264f7-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="264f7-112">Consultor funcional de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="264f7-112">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="264f7-113">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="264f7-113">System administrator</span></span>

- <span data-ttu-id="264f7-114">Acesso ao Regulatory Configuration Services (RCS) que foi provisionado para o mesmo locatário como Finance and Operations para uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="264f7-114">Access to Regulatory Configuration Services (RCS) that have been provisioned for the same tenant as Finance and Operations for one of the following roles:</span></span>

    - <span data-ttu-id="264f7-115">Desenvolvedor de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="264f7-115">Electronic reporting developer</span></span>
    - <span data-ttu-id="264f7-116">Consultor funcional de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="264f7-116">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="264f7-117">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="264f7-117">System administrator</span></span>

<span data-ttu-id="264f7-118">Você também deve baixar e armazenar localmente os arquivos a seguir.</span><span class="sxs-lookup"><span data-stu-id="264f7-118">You must also download and locally store the following files.</span></span>

| <span data-ttu-id="264f7-119">**Conteúdo**</span><span class="sxs-lookup"><span data-stu-id="264f7-119">**Content**</span></span>                           | <span data-ttu-id="264f7-120">**Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="264f7-120">**File name**</span></span>                                        |
|---------------------------------------|------------------------------------------------------|
| <span data-ttu-id="264f7-121">Configuração do modelo de dados de ER de exemplo</span><span class="sxs-lookup"><span data-stu-id="264f7-121">Sample ER data model configuration</span></span>    | [<span data-ttu-id="264f7-122">Modelo para conhecer chamadas parametrizadas.versão.1.xml</span><span class="sxs-lookup"><span data-stu-id="264f7-122">Model to learn parameterized calls.version.1.xml</span></span>](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)     |
| <span data-ttu-id="264f7-123">Configuração de metadados de ER de exemplo</span><span class="sxs-lookup"><span data-stu-id="264f7-123">Sample ER metadata configuration</span></span>      | [<span data-ttu-id="264f7-124">Metadados para conhecer chamadas parametrizadas.versão.1.xml</span><span class="sxs-lookup"><span data-stu-id="264f7-124">Metadata to learn parameterized calls.version.1.xml</span></span>](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)  |
| <span data-ttu-id="264f7-125">Configuração do mapeamento do modelo de ER de exemplo</span><span class="sxs-lookup"><span data-stu-id="264f7-125">Sample ER model mapping configuration</span></span> | [<span data-ttu-id="264f7-126">Mapeamento para conhecer chamadas parametrizadas.versão.1.1.xml</span><span class="sxs-lookup"><span data-stu-id="264f7-126">Mapping to learn parameterized calls.version.1.1.xml</span></span>](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg) |
| <span data-ttu-id="264f7-127">Configuração de formato de ER de exemplo</span><span class="sxs-lookup"><span data-stu-id="264f7-127">Sample ER format configuration</span></span>        | [<span data-ttu-id="264f7-128">Formato para conhecer chamadas parametrizadas.versão.1.1.xml</span><span class="sxs-lookup"><span data-stu-id="264f7-128">Format to learn parameterized calls.version.1.1.xml</span></span>](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)  |

## <a name="sign-in-to-your-rcs-instance"></a><span data-ttu-id="264f7-129">Entrar em sua instância do RCS</span><span class="sxs-lookup"><span data-stu-id="264f7-129">Sign in to your RCS instance</span></span>
<span data-ttu-id="264f7-130">Neste exemplo, você criará uma configuração para a empresa de exemplo, Litware, Inc. Primeiro, no RCS, você deve concluir as etapas do procedimento [Criar provedores configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md):</span><span class="sxs-lookup"><span data-stu-id="264f7-130">In this example, you will create a configuration for the sample company, Litware, Inc. First, in RCS, you must complete the steps in the [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure:</span></span>

1. <span data-ttu-id="264f7-131">No painel padrão, selecione **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="264f7-131">On the default dashboard, select **Electronic reporting**.</span></span>
2. <span data-ttu-id="264f7-132">Selecione **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="264f7-132">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="264f7-133">Importe as configurações baixadas para o RCS nesta sequência: modelo de dados, metadados, mapeamento do modelo, formato.</span><span class="sxs-lookup"><span data-stu-id="264f7-133">Import the downloaded configurations to RCS in the following sequence: data model, metadata, model mapping, format.</span></span> <span data-ttu-id="264f7-134">Execute as seguintes etapas para cada configuração de ER:</span><span class="sxs-lookup"><span data-stu-id="264f7-134">Complete the following steps for each ER configuration:</span></span>

    1. <span data-ttu-id="264f7-135">Selecione **Troca**.</span><span class="sxs-lookup"><span data-stu-id="264f7-135">Select **Exchange.**</span></span>
    2. <span data-ttu-id="264f7-136">Selecione **Carregar do arquivo XML**.</span><span class="sxs-lookup"><span data-stu-id="264f7-136">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="264f7-137">Selecione **Procurar** e selecione a configuração de ER necessária em formato XML.</span><span class="sxs-lookup"><span data-stu-id="264f7-137">Select **Browse**, and then select the required ER configuration in XML format.</span></span>
    4. <span data-ttu-id="264f7-138">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="264f7-138">Select **OK.**</span></span>

## <a name="review-the-provided-er-solution"></a><span data-ttu-id="264f7-139">Revisar a solução de ER fornecida</span><span class="sxs-lookup"><span data-stu-id="264f7-139">Review the provided ER solution</span></span>

### <a name="review-model-mapping"></a><span data-ttu-id="264f7-140">Revisar o mapeamento de modelos</span><span class="sxs-lookup"><span data-stu-id="264f7-140">Review model mapping</span></span>

1. <span data-ttu-id="264f7-141">Na árvore de configuração, expanda o conteúdo do item **Modelo para conhecer chamadas parametrizadas**.</span><span class="sxs-lookup"><span data-stu-id="264f7-141">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="264f7-142">Selecione **Mapeamento para conhecer chamadas parametrizadas**.</span><span class="sxs-lookup"><span data-stu-id="264f7-142">Select **Mapping to learn parameterized calls**.</span></span>
3. <span data-ttu-id="264f7-143">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="264f7-143">Select **Designer**.</span></span>
4. <span data-ttu-id="264f7-144">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="264f7-144">Select **Designer**.</span></span>  
   
    <span data-ttu-id="264f7-145">Esse mapeamento de modelos de ER foi criado para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="264f7-145">This ER model mapping is designed to do the following:</span></span>

    - <span data-ttu-id="264f7-146">Obtenha a lista de códigos de imposto (fonte de dados **Imposto**) na tabela **TaxTable**.</span><span class="sxs-lookup"><span data-stu-id="264f7-146">Fetch the list of tax codes (**Tax** data source) residing in the **TaxTable** table.</span></span>
    - <span data-ttu-id="264f7-147">Obtenha a lista de transações de imposto (fonte de dados **Trans**) na tabela **TaxTrans**:</span><span class="sxs-lookup"><span data-stu-id="264f7-147">Fetch the list of tax transactions (**Trans** data source) residing in the **TaxTrans** table:</span></span>
    
        - <span data-ttu-id="264f7-148">Agrupar a lista de transações obtidas (fonte de dados **Gr**) por código de imposto.</span><span class="sxs-lookup"><span data-stu-id="264f7-148">Group the list of fetched transactions (**Gr** data source) by tax code.</span></span>
        - <span data-ttu-id="264f7-149">Calcular transações agrupadas seguindo os valores agregados de acordo com o código de imposto:</span><span class="sxs-lookup"><span data-stu-id="264f7-149">Calculate for grouped transactions following aggregated values per tax code:</span></span>

            - <span data-ttu-id="264f7-150">Soma dos valores de base do imposto.</span><span class="sxs-lookup"><span data-stu-id="264f7-150">Sum of tax base values.</span></span>
            - <span data-ttu-id="264f7-151">Soma dos valores do imposto.</span><span class="sxs-lookup"><span data-stu-id="264f7-151">Sum of tax values.</span></span>
            - <span data-ttu-id="264f7-152">Valor mínimo da taxas de impostos aplicada.</span><span class="sxs-lookup"><span data-stu-id="264f7-152">Minimum value of applied tax rate.</span></span>

    <span data-ttu-id="264f7-153">O mapeamento de modelos nesta configuração implementa o modelo de dados de base para qualquer formato de ER criado para esse modelo e executado no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="264f7-153">The model mapping in this configuration implements the base data model for any of the ER formats created for this model and executed in Finance and Operations.</span></span> <span data-ttu-id="264f7-154">Consequentemente, o conteúdo das fontes de dados **Imposto** e **Gr** é exposto para formatos de ER, como fontes de dados abstratos.</span><span class="sxs-lookup"><span data-stu-id="264f7-154">As a result, the content of the **Tax** and **Gr** data sources is exposed for ER formats such as abstract data sources.</span></span>

    ![Página do Designer de mapeamento de modelos mostrando as fontes de dados Imposto e Gr](media/er-calculated-field-type-01.png)

5.  <span data-ttu-id="264f7-156">Feche a página **Designer de mapeamento de modelo**.</span><span class="sxs-lookup"><span data-stu-id="264f7-156">Close the **Model mapping designer** page.</span></span>
6.  <span data-ttu-id="264f7-157">Feche a página **Mapeamento de modelos**.</span><span class="sxs-lookup"><span data-stu-id="264f7-157">Close the **Model mapping** page.</span></span>

### <a name="review-format"></a><span data-ttu-id="264f7-158">Revisar o formato</span><span class="sxs-lookup"><span data-stu-id="264f7-158">Review format</span></span>

1. <span data-ttu-id="264f7-159">Na árvore de configuração, expanda o conteúdo do item **Modelo para conhecer chamadas parametrizadas**.</span><span class="sxs-lookup"><span data-stu-id="264f7-159">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="264f7-160">Selecione **Formato para conhecer chamadas parametrizadas**.</span><span class="sxs-lookup"><span data-stu-id="264f7-160">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="264f7-161">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="264f7-161">Select **Designer**.</span></span> <span data-ttu-id="264f7-162">Esse formato de ER foi criado para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="264f7-162">This ER format is designed to do the following:</span></span>

    - <span data-ttu-id="264f7-163">Gerar um demonstrativo de imposto em formato XML.</span><span class="sxs-lookup"><span data-stu-id="264f7-163">Generate a tax statement in XML format.</span></span>
    - <span data-ttu-id="264f7-164">Apresentar os seguintes níveis de tributação no demonstrativo de imposto: normal, reduzido e nenhum.</span><span class="sxs-lookup"><span data-stu-id="264f7-164">Present the following levels of taxation in the tax statement: regular, reduced, and none.</span></span>
    - <span data-ttu-id="264f7-165">Apresentar vários detalhes em cada nível de tributação, com um número de detalhes diferente em cada nível.</span><span class="sxs-lookup"><span data-stu-id="264f7-165">Present multiple details at each taxation level, having a different number of details in each level.</span></span>

    ![Página do designer de formatos](media/er-calculated-field-type-02.png)

4. <span data-ttu-id="264f7-167">Selecione **Mapeamento**.</span><span class="sxs-lookup"><span data-stu-id="264f7-167">Select **Mapping**.</span></span>
5. <span data-ttu-id="264f7-168">Expanda os itens **Modelo**, **Dados** e **Resumo**.</span><span class="sxs-lookup"><span data-stu-id="264f7-168">Expand the **Model**, **Data,** and **Summary** items.</span></span> 

    <span data-ttu-id="264f7-169">O campo calculado **Model.Data.Summary.Level** contém a expressão que retorna o código do nível de tributação (**Normal**, **Reduzido**, **Nenhum** ou **Outro**) como um valor de texto para qualquer código de imposto que possa ser recuperado da fonte de dados **Model.Data.Summary** em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="264f7-169">The calculated field **Model.Data.Summary.Level** contains the expression that returns the code of the taxation level (**Regular**, **Reduced**, **None,** or **Other**) as a text value for any tax code that can be retrieved from the **Model.Data.Summary** data source at run time.</span></span>

    ![Página do designer de formatos mostrando detalhes do modelo de dados Modelo para conhecer chamadas parametrizadas](media/er-calculated-field-type-03.png)

6. <span data-ttu-id="264f7-171">Expanda o item **Model**.**Data2**.</span><span class="sxs-lookup"><span data-stu-id="264f7-171">Expand the **Model**.**Data2** item.</span></span>
7. <span data-ttu-id="264f7-172">Expanda o item **Model**.**Data2.Summary2**.</span><span class="sxs-lookup"><span data-stu-id="264f7-172">Expand the **Model**.**Data2.Summary2** item.</span></span>
   
    <span data-ttu-id="264f7-173">A fonte de dados **Model**.**Data2.Summary2** é configurada para agrupar os detalhes de transações da fonte de dados **Model.Data.Summary** por nível de tributação (retornado pelo campo calculado **Model.Data.Summary.Level**) e calcular as agregações.</span><span class="sxs-lookup"><span data-stu-id="264f7-173">The **Model**.**Data2.Summary2** data source is configured to group the **Model.Data.Summary** data source transaction details by taxation level (returned by the **Model.Data.Summary.Level** calculated field) and compute the aggregations.</span></span>

    ![Página do designer de formatos mostrando detalhes da fonte de dados Model.Data2.Summary2](media/er-calculated-field-type-04.png)

8. <span data-ttu-id="264f7-175">Examine os campos calculados **Model**.**Data2.Level1**, **Model**.**Data2.Level2** e **Model**.**Data2.Level3**.</span><span class="sxs-lookup"><span data-stu-id="264f7-175">Review the calculated fields **Model**.**Data2.Level1**, **Model**.**Data2.Level2**, and **Model**.**Data2.Level3.**</span></span> <span data-ttu-id="264f7-176">Esses campos calculados são usados para filtrar a lista de registros **Model**.**Data2.Summary2** e retornar apenas os registros que representam um nível de tributação específico.</span><span class="sxs-lookup"><span data-stu-id="264f7-176">These calculated fields are used to filter the **Model**.**Data2.Summary2** records list and return only records that represent a particular taxation level.</span></span>
9. <span data-ttu-id="264f7-177">Feche a página **Designer de formato**.</span><span class="sxs-lookup"><span data-stu-id="264f7-177">Close the **Format designer** page.</span></span>

## <a name="create-a-derived-format"></a><span data-ttu-id="264f7-178">Criar um formato derivado</span><span class="sxs-lookup"><span data-stu-id="264f7-178">Create a derived format</span></span>
<span data-ttu-id="264f7-179">Você pode aperfeiçoar o formato fornecido adicionando um campo calculado para filtrar o nível de tributação necessário em vez de usar os três campos existentes: **Model**.**Data2.Level1**, **Model**.**Data2.Level2** e **Model**.**Data2.Level3**.</span><span class="sxs-lookup"><span data-stu-id="264f7-179">You can improve the provided format by adding one calculated field to filter the required taxation level instead of using the existing three fields: **Model**.**Data2.Level1**, **Model**.**Data2.Level2,** and **Model**.**Data2.Level3**.</span></span> <span data-ttu-id="264f7-180">O nível de tributação necessário pode ser especificado no local em que esse novo campo calculado será chamado.</span><span class="sxs-lookup"><span data-stu-id="264f7-180">The required taxation level can be specified in the location where this new calculated field will be called.</span></span>

1. <span data-ttu-id="264f7-181">Na árvore de configuração, expanda o conteúdo do item **Modelo para conhecer chamadas parametrizadas**.</span><span class="sxs-lookup"><span data-stu-id="264f7-181">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="264f7-182">Selecione **Formato para conhecer chamadas parametrizadas**.</span><span class="sxs-lookup"><span data-stu-id="264f7-182">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="264f7-183">Selecione **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="264f7-183">Select **Create configuration**.</span></span>
4. <span data-ttu-id="264f7-184">Selecione **Derivar do Nome: Formato para conhecer chamadas parametrizadas, Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="264f7-184">Select **Derive from Name: Format to learn parameterized calls, Microsoft**.</span></span>
5. <span data-ttu-id="264f7-185">No campo **Nome**, insira **Formato para conhecer chamadas parametrizadas (personalizado)**.</span><span class="sxs-lookup"><span data-stu-id="264f7-185">In the **Name** field, enter **Format to learn parameterized calls (custom)**.</span></span>
6. <span data-ttu-id="264f7-186">Selecione **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="264f7-186">Select **Create configuration.**</span></span>

## <a name="configure-a-parameterized-calculated-field-that-returns-a-list-of-records"></a><span data-ttu-id="264f7-187">Configurar um campo calculado parametrizado que retorna uma lista de registros</span><span class="sxs-lookup"><span data-stu-id="264f7-187">Configure a parameterized calculated field that returns a list of records</span></span>

### <a name="start-adding-a-new-calculated-field"></a><span data-ttu-id="264f7-188">Começar a adicionar um novo campo calculado</span><span class="sxs-lookup"><span data-stu-id="264f7-188">Start adding a new calculated field</span></span>

1. <span data-ttu-id="264f7-189">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="264f7-189">Select **Designer**.</span></span>
2. <span data-ttu-id="264f7-190">Selecione **Expandir/recolher** para expandir todos os itens de formato.</span><span class="sxs-lookup"><span data-stu-id="264f7-190">Select **Expand/collapse** to expand all format items.</span></span>
3. <span data-ttu-id="264f7-191">Selecione **Mapeamento**.</span><span class="sxs-lookup"><span data-stu-id="264f7-191">Select **Mapping**.</span></span>
4. <span data-ttu-id="264f7-192">Expanda o item **Modelo**.</span><span class="sxs-lookup"><span data-stu-id="264f7-192">Expand the **Model** item.</span></span>
5. <span data-ttu-id="264f7-193">Selecione o item **Model.Data2**.</span><span class="sxs-lookup"><span data-stu-id="264f7-193">Select the **Model.Data2** item.</span></span>
6. <span data-ttu-id="264f7-194">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="264f7-194">Select **Add**.</span></span>
7. <span data-ttu-id="264f7-195">Selecione **Funções\\Campo calculado**.</span><span class="sxs-lookup"><span data-stu-id="264f7-195">Select **Functions\\Calculated field**.</span></span>
8. <span data-ttu-id="264f7-196">No campo **Nome**, insira **Níveis**.</span><span class="sxs-lookup"><span data-stu-id="264f7-196">In the **Name** field, enter **Levels**.</span></span>
9. <span data-ttu-id="264f7-197">Selecione **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="264f7-197">Select **Edit formula**.</span></span>

### <a name="define-a-parameter-for-adding-a-calculated-field"></a><span data-ttu-id="264f7-198">Definir um parâmetro para adicionar um campo calculado</span><span class="sxs-lookup"><span data-stu-id="264f7-198">Define a parameter for adding a calculated field</span></span>

1. <span data-ttu-id="264f7-199">Selecione **Parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="264f7-199">Select **Parameters**.</span></span>
2. <span data-ttu-id="264f7-200">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="264f7-200">Select **New**.</span></span>
3. <span data-ttu-id="264f7-201">No campo **Nome**, insira **Nível de Tributação**.</span><span class="sxs-lookup"><span data-stu-id="264f7-201">In the **Name** field, enter **Taxation Level**.</span></span>
4. <span data-ttu-id="264f7-202">No campo **Tipo**, selecione **Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="264f7-202">In the **Type** field, select **String**.</span></span>

    <span data-ttu-id="264f7-203">Somente os tipos de dados primitivos podem ser usados para especificar o tipo de argumento do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="264f7-203">Only primitive data types can be used to specify the type of the parameter’s argument.</span></span> <span data-ttu-id="264f7-204">Portanto, não é possível usar os tipos **Lista de registros**, **Registro** e **Enumeração** com essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="264f7-204">Therefore, **Record list**, **Record**, and **Enum** types cannot be used for this purpose.</span></span>

    <span data-ttu-id="264f7-205">O número máximo de parâmetros que podem ser especificados para um único campo calculado é 8.</span><span class="sxs-lookup"><span data-stu-id="264f7-205">The maximum number of parameters that can be specified for a single calculated field is 8.</span></span>

    ![Lista de fontes de dados do parâmetro](media/er-calculated-field-type-05.png)

5. <span data-ttu-id="264f7-207">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="264f7-207">Select **OK**.</span></span>

<span data-ttu-id="264f7-208">Ao adicionar esse parâmetro, você especifica a condição que deve estar em vigor para chamar esse campo calculado.</span><span class="sxs-lookup"><span data-stu-id="264f7-208">By adding this parameter, you specify the condition that must be in place to call this calculated field.</span></span> <span data-ttu-id="264f7-209">Quando você chama esse campo calculado, precisa especificar o argumento do parâmetro **Nível de Tributação** como um valor com o formato **Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="264f7-209">When you call this calculated field, you need to specify the argument of the **Taxation Level** parameter as a value with **String** format.</span></span>

   <span data-ttu-id="264f7-210">Verifique se você definiu parâmetros apenas para os campos calculados que residem em um contêiner (**Lista de registros**, **Registro** ou **Contêiner**).</span><span class="sxs-lookup"><span data-stu-id="264f7-210">Make sure that you define parameters only for those calculated fields that reside in a container (either **Record list**, **Record**, or **Container**).</span></span>

   <span data-ttu-id="264f7-211">O parâmetro configurado está disponível na lista de fontes de dados do campo calculado.</span><span class="sxs-lookup"><span data-stu-id="264f7-211">The configured parameter is available in the list of data sources for this calculated field.</span></span> <span data-ttu-id="264f7-212">Você pode adicionar o parâmetro à expressão configurada selecionando **Adicionar fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="264f7-212">You can add the parameter to the configured expression by selecting **Add data source**.</span></span>

   ![Campos da fonte de dados](media/er-calculated-field-type-06.png)

### <a name="define-an-expression-for-adding-a-calculated-field"></a><span data-ttu-id="264f7-214">Definir uma expressão para adicionar um campo calculado</span><span class="sxs-lookup"><span data-stu-id="264f7-214">Define an expression for adding a calculated field</span></span>

1. <span data-ttu-id="264f7-215">No campo **Fórmula**, insira:</span><span class="sxs-lookup"><span data-stu-id="264f7-215">In the **Formula** field, enter:</span></span> 

    <span data-ttu-id="264f7-216">**WHERE(\@.Summary2, \@.Summary2.grouped.Level =**</span><span class="sxs-lookup"><span data-stu-id="264f7-216">**WHERE(\@.Summary2, \@.Summary2.grouped.Level =**</span></span>
    
2. <span data-ttu-id="264f7-217">Selecione o parâmetro **Nível de Tributação** na lista de fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="264f7-217">Select the **Taxation Level** parameter in the list of data sources.</span></span>
3. <span data-ttu-id="264f7-218">Selecione **Adicionar fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="264f7-218">Select **Add data source**.</span></span>
4. <span data-ttu-id="264f7-219">No campo **Fórmula**, finalize a expressão como:</span><span class="sxs-lookup"><span data-stu-id="264f7-219">In the **Formula** field, finalize the expression as:</span></span>  

    <span data-ttu-id="264f7-220">**WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Nível de Tributação')**</span><span class="sxs-lookup"><span data-stu-id="264f7-220">**WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Taxation Level')**</span></span>

5. <span data-ttu-id="264f7-221">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="264f7-221">Select **Save**.</span></span>

    ![Informações do campo da fonte de dados](media/er-calculated-field-type-07.png)

6. <span data-ttu-id="264f7-223">Feche a página **Designer de fórmulas**.</span><span class="sxs-lookup"><span data-stu-id="264f7-223">Close the **Formula designer** page.</span></span>

### <a name="finish-adding-a-new-calculated-field"></a><span data-ttu-id="264f7-224">Concluir a adição de um novo campo calculado</span><span class="sxs-lookup"><span data-stu-id="264f7-224">Finish adding a new calculated field</span></span>

- <span data-ttu-id="264f7-225">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="264f7-225">Select **OK**.</span></span>

<span data-ttu-id="264f7-226">Na página **Designer de formato**, o campo calculado parametrizado configurado **Níveis** exige um argumento **Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="264f7-226">On the **Format designer** page, the configured parameterized calculated field **Levels** requires a **String** argument.</span></span>

![Lista expandida de níveis do campo calculado](media/er-calculated-field-type-08.png)

### <a name="use-the-configured-calculated-field-for-binding-format-elements&quot;></a><span data-ttu-id=&quot;264f7-228&quot;>Usar o campo calculado configurado para associar elementos de formato</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;264f7-228&quot;>Use the configured calculated field for binding format elements</span></span>

1. <span data-ttu-id=&quot;264f7-229&quot;>Selecione **Model.Data2.Levels** para selecionar o campo calculado configurado.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;264f7-229&quot;>Select **Model.Data2.Levels** to select the configured calculated field.</span></span>
2. <span data-ttu-id=&quot;264f7-230&quot;>Selecione o elemento de formato **Statement.Taxation.Regular**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;264f7-230&quot;>Select the **Statement.Taxation.Regular** format element.</span></span>
3. <span data-ttu-id=&quot;264f7-231&quot;>Selecione **Associar**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;264f7-231&quot;>Select **Bind**.</span></span>
4. <span data-ttu-id=&quot;264f7-232&quot;>Selecione **Sim** para confirmar a substituição da fonte de dados usada atualmente, **Level1**, pela nova fonte de dados, **Níveis**, em todos os elementos de formato aninhados do elemento de formato selecionado.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;264f7-232&quot;>Select **Yes** to confirm the replacement of the currently used data source, **Level1**, by the new data source, **Levels**, in all nested format elements of the selected format element.</span></span>

    <span data-ttu-id=&quot;264f7-233&quot;>A associação aplicada foi criada como uma chamada do campo calculado parametrizado.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;264f7-233&quot;>Applied binding has been built as a call of the parameterized calculated field.</span></span> <span data-ttu-id=&quot;264f7-234&quot;>Por padrão, o nome do elemento de formato associado é usado como argumento para o campo calculado parametrizado nas seguintes condições:</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;264f7-234&quot;>By default, the name of the bound format element is used as an argument for parameterized calculated field under the following conditions:</span></span>

      - <span data-ttu-id=&quot;264f7-235&quot;>O campo calculado é configurado para usar um único parâmetro.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;264f7-235&quot;>The calculated field is configured to use a single parameter.</span></span>
      - <span data-ttu-id=&quot;264f7-236&quot;>O tipo de dados deste parâmetro é definido como **Cadeia de caracteres**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;264f7-236&quot;>The data type of this parameter is defined as **String**.</span></span>

    <span data-ttu-id=&quot;264f7-237&quot;>Quando o nome do elemento de formato associado estiver em branco, o nome da fonte de dados do elemento será usada na associação aplicada.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;264f7-237&quot;>When the name of the bound format element is blank, the data source name of this element is used in applied binding.</span></span>

5. <span data-ttu-id=&quot;264f7-238&quot;>Selecione o elemento de formato **Statement.Taxation.Reduced**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;264f7-238&quot;>Select the **Statement.Taxation.Reduced** format element.</span></span>
6. <span data-ttu-id=&quot;264f7-239&quot;>Selecione **Associar**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;264f7-239&quot;>Select **Bind**.</span></span>
7. <span data-ttu-id=&quot;264f7-240&quot;>Selecione **Sim** para confirmar a substituição da fonte de dados usada atualmente, **Level2**, pela nova fonte de dados, **Níveis**, em todos os elementos de formato aninhados sob o elemento de formato selecionado.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;264f7-240&quot;>Select **Yes** to confirm the replacement of the currently used data source, **Level2**, by the new data source, **Levels**, in all nested format elements under the selected format element.</span></span>
8. <span data-ttu-id=&quot;264f7-241&quot;>Selecione o elemento de formato **Statement.Taxation.None**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;264f7-241&quot;>Select the **Statement.Taxation.None** format element.</span></span>
9. <span data-ttu-id=&quot;264f7-242&quot;>Selecione **Associar**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;264f7-242&quot;>Select **Bind**.</span></span>
10. <span data-ttu-id=&quot;264f7-243&quot;>Selecione **Sim** para confirmar a substituição da fonte de dados usada atualmente, **Level3**, pela nova fonte de dados, **Níveis**, em todos os elementos de formato aninhados sob o elemento de formato selecionado.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;264f7-243&quot;>Select **Yes** to confirm the replacement of the currently used data source, **Level3**, by the new data source, **Levels**, in all nested format elements under the selected format element.</span></span>

   <span data-ttu-id=&quot;264f7-244&quot;>Quando você especificar o argumento do campo calculado parametrizado do elemento XML que representa o nível de tributação (por exemplo, **Model.Data2.Levels(&quot;Reduzido")** como um valor de texto), não será necessário fazer o mesmo para atributos XML aninhados; suas associações herdarão automaticamente o valor do argumento definido no nível pai (**Model.Data2.Levels.aggregated.Base**, não **Model.Data2.Levels("Reduzido").aggregated.Base**).</span><span class="sxs-lookup"><span data-stu-id="264f7-244">When you specify the argument of the parameterized calculated field for the XML element representing taxation level (for example, **Model.Data2.Levels("Reduced")** as a text value), you don’t need to do the same for nested XML attributes—their bindings will automatically inherit the value of the argument defined on the parent level (**Model.Data2.Levels.aggregated.Base**, not **Model.Data2.Levels("Reduced").aggregated.Base**).</span></span>

<span data-ttu-id="264f7-245">Não há suporte para chamadas recorrentes de qualquer campo calculado parametrizado.</span><span class="sxs-lookup"><span data-stu-id="264f7-245">Recurrent calls of any parameterized calculated field are not supported.</span></span>

<span data-ttu-id="264f7-246">Você pode selecionar **Editar fórmula** e alterar o argumento aplicado por padrão do campo calculado parametrizado na associação selecionada.</span><span class="sxs-lookup"><span data-stu-id="264f7-246">You can select **Edit formula**, and change the applied-by-default argument of the parameterized calculated field in the selected binding.</span></span> <span data-ttu-id="264f7-247">Se esse argumento estiver ausente, poderão ocorrer erros em tempo de execução. Os usuários serão informados sobre essa situação quando o formato atual for validado.</span><span class="sxs-lookup"><span data-stu-id="264f7-247">If this argument is missing, it can cause errors at run time — users are informed about such a situation when the current format is validated.</span></span>

![Notificação de aviso de validação](media/er-calculated-field-type-10.png)

## <a name="configure-a-parameterized-calculated-field-to-return-a-record"></a><span data-ttu-id="264f7-249">Configurar um campo calculado parametrizado para retornar um registro</span><span class="sxs-lookup"><span data-stu-id="264f7-249">Configure a parameterized calculated field to return a record</span></span>
<span data-ttu-id="264f7-250">Quando um campo calculado parametrizado retorna um registro, você precisa dar suporte à associação de campos individuais desse registro para elementos de formato.</span><span class="sxs-lookup"><span data-stu-id="264f7-250">When a parameterized calculated field returns a record, you need to support binding of individual fields of this record to format elements.</span></span> <span data-ttu-id="264f7-251">Nesses casos, não haverá nenhuma associação pai que contém o valor de um argumento para chamar um campo calculado parametrizado. Esse valor deve ser definido na associação do campo de um único registro.</span><span class="sxs-lookup"><span data-stu-id="264f7-251">In such cases there will be no parent binding that contains the value of an argument to call a parameterized calculated field — this value must be defined in the binding of a single record’s field.</span></span>

### <a name="start-adding-a-new-calculated-field"></a><span data-ttu-id="264f7-252">Começar a adicionar um novo campo calculado</span><span class="sxs-lookup"><span data-stu-id="264f7-252">Start adding a new calculated field</span></span>

1. <span data-ttu-id="264f7-253">Selecione o item **Model.Data2**.</span><span class="sxs-lookup"><span data-stu-id="264f7-253">Select the **Model.Data2** item.</span></span>
2. <span data-ttu-id="264f7-254">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="264f7-254">Select **Add**.</span></span>
3. <span data-ttu-id="264f7-255">Selecione **Funções\\Campo calculado**.</span><span class="sxs-lookup"><span data-stu-id="264f7-255">Select **Functions\\Calculated field**.</span></span>
4. <span data-ttu-id="264f7-256">No campo **Nome**, insira **LevelRecord**.</span><span class="sxs-lookup"><span data-stu-id="264f7-256">In the **Name** field, enter **LevelRecord**.</span></span>
5. <span data-ttu-id="264f7-257">Selecione **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="264f7-257">Select **Edit formula**.</span></span>

### <a name="define-a-parameter-for-adding-a-calculated-field"></a><span data-ttu-id="264f7-258">Definir um parâmetro para adicionar um campo calculado</span><span class="sxs-lookup"><span data-stu-id="264f7-258">Define a parameter for adding a calculated field</span></span>

1. <span data-ttu-id="264f7-259">Selecione **Parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="264f7-259">Select **Parameters**.</span></span>
2. <span data-ttu-id="264f7-260">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="264f7-260">Select **New**.</span></span>
3. <span data-ttu-id="264f7-261">No campo **Nome**, insira **Nível de Tributação**.</span><span class="sxs-lookup"><span data-stu-id="264f7-261">In the **Name** field, enter **Taxation Level**.</span></span>
4. <span data-ttu-id="264f7-262">No campo **Tipo**, selecione **Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="264f7-262">In the **Type** field, select **String**.</span></span>
5. <span data-ttu-id="264f7-263">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="264f7-263">Select **OK**.</span></span>

### <a name="define-an-expression-for-adding-a-calculated-field"></a><span data-ttu-id="264f7-264">Definir uma expressão para adicionar um campo calculado</span><span class="sxs-lookup"><span data-stu-id="264f7-264">Define an expression for adding a calculated field</span></span>

1. <span data-ttu-id="264f7-265">No campo **Fórmula**, insira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="264f7-265">In the **Formula** field, enter the following:</span></span>  
    
    <span data-ttu-id="264f7-266">**FIRSTORNULL(\@.Levels(**</span><span class="sxs-lookup"><span data-stu-id="264f7-266">**FIRSTORNULL(\@.Levels(**</span></span>

2. <span data-ttu-id="264f7-267">Selecione o parâmetro **Nível de Tributação**.</span><span class="sxs-lookup"><span data-stu-id="264f7-267">Select the **Taxation Level** parameter.</span></span>
3. <span data-ttu-id="264f7-268">Selecione **Adicionar fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="264f7-268">Select **Add data source**.</span></span>
4. <span data-ttu-id="264f7-269">No campo **Fórmula**, acrescente **'Nível de Tributação'))** ao que você inseriu na Etapa 1 para finalizar a expressão como:</span><span class="sxs-lookup"><span data-stu-id="264f7-269">In the **Formula** field, append **'Taxation Level'))** to what you entered in Step 1 to finalize the expression to:</span></span>  
    
    <span data-ttu-id="264f7-270">**FIRSTORNULL(\@.Levels('Nível de Tributação'))**</span><span class="sxs-lookup"><span data-stu-id="264f7-270">**FIRSTORNULL(\@.Levels('Taxation Level'))**</span></span>

5. <span data-ttu-id="264f7-271">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="264f7-271">Select **Save**.</span></span>
6. <span data-ttu-id="264f7-272">Feche a página **Designer de fórmulas**.</span><span class="sxs-lookup"><span data-stu-id="264f7-272">Close **the Formula designer** page.</span></span>

### <a name="finish-adding-a-new-calculated-field"></a><span data-ttu-id="264f7-273">Concluir a adição de um novo campo calculado</span><span class="sxs-lookup"><span data-stu-id="264f7-273">Finish adding a new calculated field</span></span>

-   <span data-ttu-id="264f7-274">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="264f7-274">Select **OK**.</span></span>

### <a name="use-the-configured-calculated-field-to-bind-format-elements"></a><span data-ttu-id="264f7-275">Usar o campo calculado configurado para associar elementos de formato</span><span class="sxs-lookup"><span data-stu-id="264f7-275">Use the configured calculated field to bind format elements</span></span>

1. <span data-ttu-id="264f7-276">Expanda **Model.Data2.LevelRecord** para selecionar o campo calculado configurado.</span><span class="sxs-lookup"><span data-stu-id="264f7-276">Expand **Model.Data2.LevelRecord** to select the configured calculated field.</span></span>
2. <span data-ttu-id="264f7-277">Expanda o contêiner **Model.Data2.LevelRecord.aggregated** do campo calculado configurado.</span><span class="sxs-lookup"><span data-stu-id="264f7-277">Expand the **Model.Data2.LevelRecord.aggregated** container of the configured calculated field.</span></span>
3. <span data-ttu-id="264f7-278">Selecione o campo **Model.Data2.LevelRecord.aggregated.Base**.</span><span class="sxs-lookup"><span data-stu-id="264f7-278">Select the **Model.Data2.LevelRecord.aggregated.Base** field.</span></span>
4. <span data-ttu-id="264f7-279">Selecione o elemento de formato **Statement.Taxation.None**.</span><span class="sxs-lookup"><span data-stu-id="264f7-279">Select the **Statement.Taxation.None** format element.</span></span>
5. <span data-ttu-id="264f7-280">Selecione **Desassociar**.</span><span class="sxs-lookup"><span data-stu-id="264f7-280">Select **Unbind**.</span></span>
6. <span data-ttu-id="264f7-281">Selecione o elemento de formato **Statement.Taxation.None.Base**.</span><span class="sxs-lookup"><span data-stu-id="264f7-281">Select the **Statement.Taxation.None.Base** format element.</span></span>
7. <span data-ttu-id="264f7-282">Selecione **Associar**.</span><span class="sxs-lookup"><span data-stu-id="264f7-282">Select **Bind**.</span></span>
8. <span data-ttu-id="264f7-283">Selecione **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="264f7-283">Select **Edit formula**.</span></span>
9. <span data-ttu-id="264f7-284">Altere a expressão para **Model.Data2.LevelRecord("Nenhum").aggregated.Base**.</span><span class="sxs-lookup"><span data-stu-id="264f7-284">Change the expression to **Model.Data2.LevelRecord("None").aggregated.Base**.</span></span>

![Expressão atualizada](media/er-calculated-field-type-11.png)

## <a name="remove-calculated-fields-that-are-not-used"></a><span data-ttu-id="264f7-286">Remover campos calculados que não são usados</span><span class="sxs-lookup"><span data-stu-id="264f7-286">Remove calculated fields that are not used</span></span>

1. <span data-ttu-id="264f7-287">Selecione **Model.Data2.Level1**.</span><span class="sxs-lookup"><span data-stu-id="264f7-287">Select **Model.Data2.Level1**.</span></span>
2. <span data-ttu-id="264f7-288">Selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="264f7-288">Select **Delete**.</span></span>
3. <span data-ttu-id="264f7-289">Selecione **Model.Data2.Level2**.</span><span class="sxs-lookup"><span data-stu-id="264f7-289">Select **Model.Data2.Level2**.</span></span>
4. <span data-ttu-id="264f7-290">Selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="264f7-290">Select **Delete**.</span></span>
5. <span data-ttu-id="264f7-291">Selecione **Model.Data2.Level3**.</span><span class="sxs-lookup"><span data-stu-id="264f7-291">Select **Model.Data2.Level3**.</span></span>
6. <span data-ttu-id="264f7-292">Selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="264f7-292">Select **Delete**.</span></span>
7. <span data-ttu-id="264f7-293">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="264f7-293">Select **Save**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="264f7-294">Você reutilizou o mesmo campo calculado **Model.Data2.Levels** várias vezes em associações de formato.</span><span class="sxs-lookup"><span data-stu-id="264f7-294">You reused the same calculated field **Model.Data2.Levels** several times in format bindings.</span></span> <span data-ttu-id="264f7-295">É muito mais fácil usar e manter um único campo calculado em vez de fazer isso para vários campos semelhantes.</span><span class="sxs-lookup"><span data-stu-id="264f7-295">It is much easier to use and maintain a single calculated field instead of doing this for multiple similar fields.</span></span>

8. <span data-ttu-id="264f7-296">Feche a página **Designer de formato**.</span><span class="sxs-lookup"><span data-stu-id="264f7-296">Close the **Format designer** page.</span></span>

## <a name="complete-adjusted-version-of-a-derived-format"></a><span data-ttu-id="264f7-297">Concluir a versão ajustada de um formato de derivado</span><span class="sxs-lookup"><span data-stu-id="264f7-297">Complete adjusted version of a derived format</span></span>

1. <span data-ttu-id="264f7-298">Na Guia Rápida **Versões**, selecione **Alterar status**.</span><span class="sxs-lookup"><span data-stu-id="264f7-298">In the **Versions** FastTab, select **Change status**.</span></span>
2. <span data-ttu-id="264f7-299">Selecione **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="264f7-299">Select **Complete**.</span></span>

## <a name="export-completed-version-of-a-derived-format"></a><span data-ttu-id="264f7-300">Exportar a versão concluída de um formato de derivado</span><span class="sxs-lookup"><span data-stu-id="264f7-300">Export completed version of a derived format</span></span>

1. <span data-ttu-id="264f7-301">Selecione o formato **Formato para conhecer chamadas parametrizadas (personalizado)** na árvore de configurações.</span><span class="sxs-lookup"><span data-stu-id="264f7-301">Select **Format to learn parameterized calls (custom)** format in the configurations tree.</span></span>
2. <span data-ttu-id="264f7-302">Na Guia Rápida **Versões**, selecione a versão 1.1.1 concluída.</span><span class="sxs-lookup"><span data-stu-id="264f7-302">In the **Versions** FastTab, select the completed version 1.1.1.</span></span>
3. <span data-ttu-id="264f7-303">Selecione **Taxa de câmbio**.</span><span class="sxs-lookup"><span data-stu-id="264f7-303">Select **Exchange**.</span></span>
4. <span data-ttu-id="264f7-304">Selecione **Exportar como arquivo XML**.</span><span class="sxs-lookup"><span data-stu-id="264f7-304">Select **Export as XML file**.</span></span>
5. <span data-ttu-id="264f7-305">Armazene a configuração baixada localmente no formato XML.</span><span class="sxs-lookup"><span data-stu-id="264f7-305">Store the downloaded configuration locally, in XML format.</span></span>

## <a name="test-er-formats"></a><span data-ttu-id="264f7-306">Testar formatos de ER</span><span class="sxs-lookup"><span data-stu-id="264f7-306">Test ER formats</span></span> 
<span data-ttu-id="264f7-307">Você pode executar os formatos de ER inicial e aprimorados para garantir que os campos calculados parametrizados funcionam corretamente.</span><span class="sxs-lookup"><span data-stu-id="264f7-307">You can run the initial and improved ER formats to make sure that configured parameterized calculated fields work properly.</span></span>

### <a name="import-er-configurations"></a><span data-ttu-id="264f7-308">Importar configurações de ER</span><span class="sxs-lookup"><span data-stu-id="264f7-308">Import ER configurations</span></span>
<span data-ttu-id="264f7-309">Você pode importar configurações revisadas do RCS usando o repositório de ER do tipo **RCS**.</span><span class="sxs-lookup"><span data-stu-id="264f7-309">You can import reviewed configurations from RCS by using the ER repository of the **RCS** type.</span></span> <span data-ttu-id="264f7-310">Se você já passou pelas etapas do tópico [Importar configurações de ER (Relatórios eletrônicos) do RCS (Regulatory Configuration Service)](rcs-download-configurations.md), use o repositório de ER configurado para importar as configurações discutidas anteriormente neste tópico para o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="264f7-310">If you already went through the steps in the topic, [Import Electronic reporting (ER) configurations from Regulatory Configuration Services (RCS)](rcs-download-configurations.md), use the configured ER repository to import configurations discussed earlier in this topic to your environment.</span></span> <span data-ttu-id="264f7-311">Caso contrário, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="264f7-311">Otherwise, follow these steps:</span></span>

1. <span data-ttu-id="264f7-312">Selecione a empresa **DEMF** e, no painel padrão, selecione **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="264f7-312">Select the **DEMF** company and on the default dashboard, select **Electronic reporting**.</span></span>
2. <span data-ttu-id="264f7-313">Selecione **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="264f7-313">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="264f7-314">Importe as configurações do Centro de Download da Microsoft nesta sequência: modelo de dados, mapeamento do modelo, formato.</span><span class="sxs-lookup"><span data-stu-id="264f7-314">Import the configurations from Microsoft Download Center in the following sequence: data model, model mapping, format.</span></span> <span data-ttu-id="264f7-315">Execute as seguintes etapas para cada configuração de ER:</span><span class="sxs-lookup"><span data-stu-id="264f7-315">Complete the following steps for each ER configuration:</span></span>

    1. <span data-ttu-id="264f7-316">Selecione **Troca**.</span><span class="sxs-lookup"><span data-stu-id="264f7-316">Select **Exchange.**</span></span>
    2. <span data-ttu-id="264f7-317">Selecione **Carregar do arquivo XML**.</span><span class="sxs-lookup"><span data-stu-id="264f7-317">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="264f7-318">Selecione **Procurar** para selecionar a configuração de ER necessária em formato XML.</span><span class="sxs-lookup"><span data-stu-id="264f7-318">Select **Browse** to select the required ER configuration in XML format.</span></span>
    4. <span data-ttu-id="264f7-319">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="264f7-319">Select **OK**.</span></span>

4. <span data-ttu-id="264f7-320">Importe a exportação do RCS versão 1.1.1 concluída do formato **Formato para conhecer chamadas parametrizadas (personalizado)**:</span><span class="sxs-lookup"><span data-stu-id="264f7-320">Import the exported from RCS completed version 1.1.1 of the **Format to learn parameterized calls (custom)** format:</span></span>

    1. <span data-ttu-id="264f7-321">Selecione **Troca**.</span><span class="sxs-lookup"><span data-stu-id="264f7-321">Select **Exchange.**</span></span>
    2. <span data-ttu-id="264f7-322">Selecione **Carregar do arquivo XML**.</span><span class="sxs-lookup"><span data-stu-id="264f7-322">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="264f7-323">Selecione **Procurar** para selecionar o arquivo **Formato para conhecer chamadas parametrizadas (personalizado)** armazenado localmente em formato XML.</span><span class="sxs-lookup"><span data-stu-id="264f7-323">Select **Browse** to select the locally stored **Format to learn parameterized calls (custom)** file in XML format.</span></span>
    4. <span data-ttu-id="264f7-324">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="264f7-324">Select **OK**.</span></span>

### <a name="run-er-formats"></a><span data-ttu-id="264f7-325">Executar formatos de ER</span><span class="sxs-lookup"><span data-stu-id="264f7-325">Run ER formats</span></span>

1. <span data-ttu-id="264f7-326">Na árvore de configuração, expanda o conteúdo do item **Modelo para conhecer chamadas parametrizadas**.</span><span class="sxs-lookup"><span data-stu-id="264f7-326">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="264f7-327">Selecione **Formato para conhecer chamadas parametrizadas**.</span><span class="sxs-lookup"><span data-stu-id="264f7-327">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="264f7-328">Selecione **Executar** na faixa de opções mais superior.</span><span class="sxs-lookup"><span data-stu-id="264f7-328">Select **Run** on the top-most ribbon.</span></span>
4. <span data-ttu-id="264f7-329">Salve a saída gerada localmente.</span><span class="sxs-lookup"><span data-stu-id="264f7-329">Save the locally generated output.</span></span>
5. <span data-ttu-id="264f7-330">Selecione o item **Formato para conhecer chamadas parametrizadas (personalizado)**.</span><span class="sxs-lookup"><span data-stu-id="264f7-330">Select the **Format to learn parameterized calls (custom)** item.</span></span>
6. <span data-ttu-id="264f7-331">Selecione **Executar** na faixa de opções mais superior.</span><span class="sxs-lookup"><span data-stu-id="264f7-331">Select **Run** on the top-most ribbon.</span></span>
7. <span data-ttu-id="264f7-332">Salve a saída gerada localmente.</span><span class="sxs-lookup"><span data-stu-id="264f7-332">Save the generated output locally.</span></span> 
8. <span data-ttu-id="264f7-333">Compare o conteúdo das saídas geradas.</span><span class="sxs-lookup"><span data-stu-id="264f7-333">Compare the contents of the generated outputs.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="264f7-334">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="264f7-334">Additional resources</span></span>

- [<span data-ttu-id="264f7-335">Designer de fórmulas no relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="264f7-335">Formula designer in Electronic reporting (ER)</span></span>](general-electronic-reporting-formula-designer.md)
- [<span data-ttu-id="264f7-336">Melhorar o desempenho das soluções ER adicionando fontes de dados de CAMPOS CALCULADOS parametrizados</span><span class="sxs-lookup"><span data-stu-id="264f7-336">Improve performance of ER solutions by adding parameterized CALCULATED FIELD data sources</span></span>](er-calculated-field-ds-performance.md)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]