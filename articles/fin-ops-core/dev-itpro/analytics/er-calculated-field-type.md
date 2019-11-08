---
title: Suporte a chamadas parametrizadas de fontes de dados de ER do tipo Campo calculado
description: Este tópico fornece informações sobre como usar o tipo Campo calculado de fontes de dados de ER.
author: NickSelin
manager: AnnBe
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 20d48795b23628bbba2896bf48940936a25e0435
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550075"
---
# <a name="support-parameterized-calls-of-er-data-sources-of-the-calculated-field-type"></a><span data-ttu-id="80e3f-103">Suporte a chamadas parametrizadas de fontes de dados de ER do tipo Campo calculado</span><span class="sxs-lookup"><span data-stu-id="80e3f-103">Support parameterized calls of ER data sources of the Calculated field type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="80e3f-104">Este tópico explica como você pode criar uma fonte de dados relatório eletrônico (ER) usando o tipo **Campo calculado**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-104">This topic explains how you can design an Electronic reporting (ER) data source by using the **Calculated field** type.</span></span> <span data-ttu-id="80e3f-105">Essa fonte de dados pode conter uma expressão de ER que, quando executada, pode ser controlada pelos valores de argumentos do parâmetro configurados em uma associação que chama essa fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="80e3f-105">This data source may contain an ER expression that, when executed, can be controlled by the values of the parameter arguments that are configured in a binding that calls this data source.</span></span> <span data-ttu-id="80e3f-106">Ao configurar chamadas parametrizadas dessa fonte de dados, você pode reutilizar uma única fonte de dados em muitas associações, o que reduz o número total de fontes de dados que devem ser configuradas em mapeamentos de modelos de ER ou em formatos de ER.</span><span class="sxs-lookup"><span data-stu-id="80e3f-106">By configuring parameterized calls of such a data source, you can reuse a single data source in many bindings, which reduces the total number of data sources that must be configured in ER model mappings or ER formats.</span></span> <span data-ttu-id="80e3f-107">Isso também simplifica o componente de ER configurado, o que reduz os custos de manutenção e os custos de utilização por outros consumidores.</span><span class="sxs-lookup"><span data-stu-id="80e3f-107">It also simplifies the configured ER component, which reduces the maintenance costs and the cost of use by other consumers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="80e3f-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="80e3f-108">Prerequisites</span></span>
<span data-ttu-id="80e3f-109">Para concluir os exemplos neste tópico, você deve ter o seguinte acesso:</span><span class="sxs-lookup"><span data-stu-id="80e3f-109">To complete the examples in this topic, you must have the following access:</span></span>

- <span data-ttu-id="80e3f-110">Acesso a uma destas funções:</span><span class="sxs-lookup"><span data-stu-id="80e3f-110">Access to one of these roles:</span></span>

    - <span data-ttu-id="80e3f-111">Desenvolvedor de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="80e3f-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="80e3f-112">Consultor funcional de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="80e3f-112">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="80e3f-113">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="80e3f-113">System administrator</span></span>

- <span data-ttu-id="80e3f-114">Acesso ao Regulatory Configuration Services (RCS) que foi provisionado para o mesmo locatário como Finance and Operations para uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="80e3f-114">Access to Regulatory Configuration Services (RCS) that have been provisioned for the same tenant as Finance and Operations for one of the following roles:</span></span>

    - <span data-ttu-id="80e3f-115">Desenvolvedor de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="80e3f-115">Electronic reporting developer</span></span>
    - <span data-ttu-id="80e3f-116">Consultor funcional de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="80e3f-116">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="80e3f-117">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="80e3f-117">System administrator</span></span>

<span data-ttu-id="80e3f-118">No [Centro de Download da Microsoft](https://go.microsoft.com/fwlink/?linkid=874684), baixe o arquivo compactado **Suporte a chamadas parametrizadas de fontes de dados de ER do tipo Campo calculado**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-118">From the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684), download the zipped (compressed) file **Support parameterized calls of ER data sources of Calculated field type**.</span></span> <span data-ttu-id="80e3f-119">Ele contém as configurações de ER a seguir que devem ser extraídas e armazenadas localmente.</span><span class="sxs-lookup"><span data-stu-id="80e3f-119">It contains the following ER configurations that must be extracted and stored locally.</span></span>

| <span data-ttu-id="80e3f-120">**Conteúdo**</span><span class="sxs-lookup"><span data-stu-id="80e3f-120">**Content**</span></span>                           | <span data-ttu-id="80e3f-121">**Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="80e3f-121">**File name**</span></span>                                        |
|---------------------------------------|------------------------------------------------------|
| <span data-ttu-id="80e3f-122">Configuração do modelo de dados de ER de exemplo</span><span class="sxs-lookup"><span data-stu-id="80e3f-122">Sample ER data model configuration</span></span>    | <span data-ttu-id="80e3f-123">Modelo para conhecer chamadas parametrizadas.versão.1.xml</span><span class="sxs-lookup"><span data-stu-id="80e3f-123">Model to learn parameterized calls.version.1.xml</span></span>     |
| <span data-ttu-id="80e3f-124">Configuração de metadados de ER de exemplo</span><span class="sxs-lookup"><span data-stu-id="80e3f-124">Sample ER metadata configuration</span></span>      | <span data-ttu-id="80e3f-125">Metadados para conhecer chamadas parametrizadas.versão.1.xml</span><span class="sxs-lookup"><span data-stu-id="80e3f-125">Metadata to learn parameterized calls.version.1.xml</span></span>  |
| <span data-ttu-id="80e3f-126">Configuração do mapeamento do modelo de ER de exemplo</span><span class="sxs-lookup"><span data-stu-id="80e3f-126">Sample ER model mapping configuration</span></span> | <span data-ttu-id="80e3f-127">Mapeamento para conhecer chamadas parametrizadas.versão.1.1.xml</span><span class="sxs-lookup"><span data-stu-id="80e3f-127">Mapping to learn parameterized calls.version.1.1.xml</span></span> |
| <span data-ttu-id="80e3f-128">Configuração de formato de ER de exemplo</span><span class="sxs-lookup"><span data-stu-id="80e3f-128">Sample ER format configuration</span></span>        | <span data-ttu-id="80e3f-129">Formato para conhecer chamadas parametrizadas.versão.1.1.xml</span><span class="sxs-lookup"><span data-stu-id="80e3f-129">Format to learn parameterized calls.version.1.1.xml</span></span>  |

## <a name="sign-in-to-your-rcs-instance"></a><span data-ttu-id="80e3f-130">Entrar em sua instância do RCS</span><span class="sxs-lookup"><span data-stu-id="80e3f-130">Sign in to your RCS instance</span></span>
<span data-ttu-id="80e3f-131">Neste exemplo, você criará uma configuração para a empresa de exemplo, Litware, Inc. Primeiro, no RCS, você deve concluir as etapas do procedimento [Criar um provedor configuração e marcá-lo como ativo](tasks/er-configuration-provider-mark-it-active-2016-11.md):</span><span class="sxs-lookup"><span data-stu-id="80e3f-131">In this example, you will create a configuration for the sample company, Litware, Inc. First, in RCS, you must complete the steps in the [Create a configuration provider and mark it as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure:</span></span>

1. <span data-ttu-id="80e3f-132">No painel padrão, selecione **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-132">On the default dashboard, select **Electronic reporting**.</span></span>
2. <span data-ttu-id="80e3f-133">Selecione **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-133">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="80e3f-134">Importe as configurações baixadas para o RCS nesta sequência: modelo de dados, metadados, mapeamento do modelo, formato.</span><span class="sxs-lookup"><span data-stu-id="80e3f-134">Import the downloaded configurations to RCS in the following sequence: data model, metadata, model mapping, format.</span></span> <span data-ttu-id="80e3f-135">Execute as seguintes etapas para cada configuração de ER:</span><span class="sxs-lookup"><span data-stu-id="80e3f-135">Complete the following steps for each ER configuration:</span></span>

    1. <span data-ttu-id="80e3f-136">Selecione **Troca**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-136">Select **Exchange.**</span></span>
    2. <span data-ttu-id="80e3f-137">Selecione **Carregar do arquivo XML**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-137">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="80e3f-138">Selecione **Procurar** e selecione a configuração de ER necessária em formato XML.</span><span class="sxs-lookup"><span data-stu-id="80e3f-138">Select **Browse**, and then select the required ER configuration in XML format.</span></span>
    4. <span data-ttu-id="80e3f-139">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-139">Select **OK.**</span></span>

## <a name="review-the-provided-er-solution"></a><span data-ttu-id="80e3f-140">Revisar a solução de ER fornecida</span><span class="sxs-lookup"><span data-stu-id="80e3f-140">Review the provided ER solution</span></span>

### <a name="review-model-mapping"></a><span data-ttu-id="80e3f-141">Revisar o mapeamento de modelos</span><span class="sxs-lookup"><span data-stu-id="80e3f-141">Review model mapping</span></span>

1. <span data-ttu-id="80e3f-142">Na árvore de configuração, expanda o conteúdo do item **Modelo para conhecer chamadas parametrizadas**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-142">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="80e3f-143">Selecione **Mapeamento para conhecer chamadas parametrizadas**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-143">Select **Mapping to learn parameterized calls**.</span></span>
3. <span data-ttu-id="80e3f-144">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-144">Select **Designer**.</span></span>
4. <span data-ttu-id="80e3f-145">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-145">Select **Designer**.</span></span>  
   
<span data-ttu-id="80e3f-146">Esse mapeamento de modelos de ER foi criado para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="80e3f-146">This ER model mapping is designed to do the following:</span></span>

- <span data-ttu-id="80e3f-147">Obter a lista de códigos de imposto (fontes dados **Imposto**) na tabela **TaxTable**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-147">Fetch the list of tax codes (**Tax** data source) residing in the   **TaxTable** table.</span></span>
- <span data-ttu-id="80e3f-148">Obter a lista de transações de imposto (fonte de dados **Trans**) na tabela **TaxTrans**:</span><span class="sxs-lookup"><span data-stu-id="80e3f-148">Fetch the list of tax transactions (**Trans** data source) residing in the   **TaxTrans** table:</span></span>
    
    - <span data-ttu-id="80e3f-149">Agrupar a lista de transações obtidas (fonte de dados **Gr**) por código de imposto.</span><span class="sxs-lookup"><span data-stu-id="80e3f-149">Group the list of fetched transactions (**Gr** data source) by tax code.</span></span>
    - <span data-ttu-id="80e3f-150">Calcular transações agrupadas seguindo os valores agregados de acordo com o código de imposto:</span><span class="sxs-lookup"><span data-stu-id="80e3f-150">Calculate for grouped transactions following aggregated values per   tax code:</span></span>

        - <span data-ttu-id="80e3f-151">Soma dos valores de base do imposto.</span><span class="sxs-lookup"><span data-stu-id="80e3f-151">Sum of tax base values.</span></span>
        - <span data-ttu-id="80e3f-152">Soma dos valores do imposto.</span><span class="sxs-lookup"><span data-stu-id="80e3f-152">Sum of tax values.</span></span>
        - <span data-ttu-id="80e3f-153">Valor mínimo da taxas de impostos aplicada.</span><span class="sxs-lookup"><span data-stu-id="80e3f-153">Minimum value of applied tax rate.</span></span>

<span data-ttu-id="80e3f-154">O mapeamento de modelos nesta configuração implementa o modelo de dados de base para qualquer dos formatos de ER criados para esse modelo e executados no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="80e3f-154">The model mapping in this configuration implements the base data model for any of the ER formats created for this model and executed in Finance and Operations.</span></span> <span data-ttu-id="80e3f-155">Consequentemente, o conteúdo das fontes de dados **Imposto** e **Gr** é exposto para formatos de ER, como fontes de dados abstratos.</span><span class="sxs-lookup"><span data-stu-id="80e3f-155">As a result, the content of the **Tax** and **Gr** data sources is exposed for ER formats such as abstract data sources.</span></span>

  ![Página do Designer de mapeamento de modelos mostrando as fontes de dados Imposto e Gr](media/er-calculated-field-type-01.png)

5.  <span data-ttu-id="80e3f-157">Feche a página **Designer de mapeamento de modelo**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-157">Close the **Model mapping designer** page.</span></span>
6.  <span data-ttu-id="80e3f-158">Feche a página **Mapeamento de modelos**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-158">Close the **Model mapping** page.</span></span>

### <a name="review-format"></a><span data-ttu-id="80e3f-159">Revisar o formato</span><span class="sxs-lookup"><span data-stu-id="80e3f-159">Review format</span></span>

1. <span data-ttu-id="80e3f-160">Na árvore de configuração, expanda o conteúdo do item **Modelo para conhecer chamadas parametrizadas**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-160">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="80e3f-161">Selecione **Formato para conhecer chamadas parametrizadas**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-161">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="80e3f-162">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-162">Select **Designer**.</span></span> <span data-ttu-id="80e3f-163">Esse formato de ER foi criado para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="80e3f-163">This ER format is designed to do the following:</span></span>

  - <span data-ttu-id="80e3f-164">Gerar um demonstrativo de imposto em formato XML.</span><span class="sxs-lookup"><span data-stu-id="80e3f-164">Generate a tax statement in XML format.</span></span>
  - <span data-ttu-id="80e3f-165">Apresentar os seguintes níveis de tributação no demonstrativo de imposto: normal, reduzido e nenhum.</span><span class="sxs-lookup"><span data-stu-id="80e3f-165">Present the following levels of taxation in the tax statement: regular, reduced, and none.</span></span>
  - <span data-ttu-id="80e3f-166">Apresentar vários detalhes em cada nível de tributação, com um número de detalhes diferente em cada nível.</span><span class="sxs-lookup"><span data-stu-id="80e3f-166">Present multiple details at each taxation level, having a different number of details in each level.</span></span>

  ![Página do designer de formatos](media/er-calculated-field-type-02.png)

4. <span data-ttu-id="80e3f-168">Selecione **Mapeamento**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-168">Select **Mapping**.</span></span>
5. <span data-ttu-id="80e3f-169">Expanda os itens **Modelo**, **Dados** e **Resumo**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-169">Expand the **Model**, **Data,** and **Summary** items.</span></span> 

   <span data-ttu-id="80e3f-170">O campo calculado **Model.Data.Summary.Level** contém a expressão que retorna o código do nível de tributação (**Normal**, **Reduzido**, **Nenhum** ou **Outro**) como um valor de texto para qualquer código de imposto que possa ser recuperado da fonte de dados **Model.Data.Summary** em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="80e3f-170">The calculated field **Model.Data.Summary.Level** contains the expression that returns the code of the taxation level (**Regular**, **Reduced**, **None,** or **Other**) as a text value for any tax code that can be retrieved from the **Model.Data.Summary** data source at run time.</span></span>

  ![Página do designer de formatos mostrando detalhes do modelo de dados Modelo para conhecer chamadas parametrizadas](media/er-calculated-field-type-03.png)

6. <span data-ttu-id="80e3f-172">Expanda o item **Model**.**Data2**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-172">Expand the **Model**.**Data2** item.</span></span>
7. <span data-ttu-id="80e3f-173">Expanda o item **Model**.**Data2.Summary2**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-173">Expand the **Model**.**Data2.Summary2** item.</span></span>
   
   <span data-ttu-id="80e3f-174">A fonte de dados **Model**.**Data2.Summary2** é configurada para agrupar os detalhes de transações da fonte de dados **Model.Data.Summary** por nível de tributação (retornado pelo campo calculado **Model.Data.Summary.Level**) e calcular as agregações.</span><span class="sxs-lookup"><span data-stu-id="80e3f-174">The **Model**.**Data2.Summary2** data source is configured to group the **Model.Data.Summary** data source transaction details by taxation level (returned by the **Model.Data.Summary.Level** calculated field) and compute the aggregations.</span></span>

  ![Página do designer de formatos mostrando detalhes da fonte de dados Model.Data2.Summary2](media/er-calculated-field-type-04.png)

8. <span data-ttu-id="80e3f-176">Examine os campos calculados **Model**.**Data2.Level1**, **Model**.**Data2.Level2** e **Model**.**Data2.Level3**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-176">Review the calculated fields **Model**.**Data2.Level1**, **Model**.**Data2.Level2**, and **Model**.**Data2.Level3.**</span></span> <span data-ttu-id="80e3f-177">Esses campos calculados são usados para filtrar a lista de registros **Model**.**Data2.Summary2** e retornar apenas os registros que representam um nível de tributação específico.</span><span class="sxs-lookup"><span data-stu-id="80e3f-177">These calculated fields are used to filter the **Model**.**Data2.Summary2** records list and return only records that represent a particular taxation level.</span></span>
9. <span data-ttu-id="80e3f-178">Feche a página **Designer de formato**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-178">Close the **Format designer** page.</span></span>

## <a name="create-a-derived-format"></a><span data-ttu-id="80e3f-179">Criar um formato derivado</span><span class="sxs-lookup"><span data-stu-id="80e3f-179">Create a derived format</span></span>
<span data-ttu-id="80e3f-180">Você pode aperfeiçoar o formato fornecido adicionando um campo calculado para filtrar o nível de tributação necessário em vez de usar os três campos existentes: **Model**.**Data2.Level1**, **Model**.**Data2.Level2** e **Model**.**Data2.Level3**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-180">You can improve the provided format by adding one calculated field to filter the required taxation level instead of using the existing three fields: **Model**.**Data2.Level1**, **Model**.**Data2.Level2,** and **Model**.**Data2.Level3**.</span></span> <span data-ttu-id="80e3f-181">O nível de tributação necessário pode ser especificado no local em que esse novo campo calculado será chamado.</span><span class="sxs-lookup"><span data-stu-id="80e3f-181">The required taxation level can be specified in the location where this new calculated field will be called.</span></span>

1. <span data-ttu-id="80e3f-182">Na árvore de configuração, expanda o conteúdo do item **Modelo para conhecer chamadas parametrizadas**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-182">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="80e3f-183">Selecione **Formato para conhecer chamadas parametrizadas**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-183">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="80e3f-184">Selecione **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-184">Select **Create configuration**.</span></span>
4. <span data-ttu-id="80e3f-185">Selecione **Derivar do Nome: Formato para conhecer chamadas parametrizadas, Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-185">Select **Derive from Name: Format to learn parameterized calls, Microsoft**.</span></span>
5. <span data-ttu-id="80e3f-186">No campo **Nome**, insira **Formato para conhecer chamadas parametrizadas (personalizado)**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-186">In the **Name** field, enter **Format to learn parameterized calls (custom)**.</span></span>
6. <span data-ttu-id="80e3f-187">Selecione **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-187">Select **Create configuration.**</span></span>

## <a name="configure-a-parameterized-calculated-field-that-returns-a-list-of-records"></a><span data-ttu-id="80e3f-188">Configurar um campo calculado parametrizado que retorna uma lista de registros</span><span class="sxs-lookup"><span data-stu-id="80e3f-188">Configure a parameterized calculated field that returns a list of records</span></span>

### <a name="start-adding-a-new-calculated-field"></a><span data-ttu-id="80e3f-189">Começar a adicionar um novo campo calculado</span><span class="sxs-lookup"><span data-stu-id="80e3f-189">Start adding a new calculated field</span></span>

1. <span data-ttu-id="80e3f-190">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-190">Select **Designer**.</span></span>
2. <span data-ttu-id="80e3f-191">Selecione **Expandir/recolher** para expandir todos os itens de formato.</span><span class="sxs-lookup"><span data-stu-id="80e3f-191">Select **Expand/collapse** to expand all format items.</span></span>
3. <span data-ttu-id="80e3f-192">Selecione **Mapeamento**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-192">Select **Mapping**.</span></span>
4. <span data-ttu-id="80e3f-193">Expanda o item **Modelo**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-193">Expand the **Model** item.</span></span>
5. <span data-ttu-id="80e3f-194">Selecione o item **Model.Data2**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-194">Select the **Model.Data2** item.</span></span>
6. <span data-ttu-id="80e3f-195">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-195">Select **Add**.</span></span>
7. <span data-ttu-id="80e3f-196">Selecione **Funções\\Campo calculado**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-196">Select **Functions\\Calculated field**.</span></span>
8. <span data-ttu-id="80e3f-197">No campo **Nome**, insira **Níveis**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-197">In the **Name** field, enter **Levels**.</span></span>
9. <span data-ttu-id="80e3f-198">Selecione **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-198">Select **Edit formula**.</span></span>

### <a name="define-a-parameter-for-adding-a-calculated-field"></a><span data-ttu-id="80e3f-199">Definir um parâmetro para adicionar um campo calculado</span><span class="sxs-lookup"><span data-stu-id="80e3f-199">Define a parameter for adding a calculated field</span></span>

1. <span data-ttu-id="80e3f-200">Selecione **Parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-200">Select **Parameters**.</span></span>
2. <span data-ttu-id="80e3f-201">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-201">Select **New**.</span></span>
3. <span data-ttu-id="80e3f-202">No campo **Nome**, insira **Nível de Tributação**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-202">In the **Name** field, enter **Taxation Level**.</span></span>
4. <span data-ttu-id="80e3f-203">No campo **Tipo**, selecione **Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-203">In the **Type** field, select **String**.</span></span>

    <span data-ttu-id="80e3f-204">Somente os tipos de dados primitivos podem ser usados para especificar o tipo de argumento do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="80e3f-204">Only primitive data types can be used to specify the type of the parameter’s argument.</span></span> <span data-ttu-id="80e3f-205">Portanto, não é possível usar os tipos **Lista de registros**, **Registro** e **Enumeração** com essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="80e3f-205">Therefore, **Record list**, **Record**, and **Enum** types cannot be used for this purpose.</span></span>

    <span data-ttu-id="80e3f-206">O número máximo de parâmetros que podem ser especificados para um único campo calculado é 8.</span><span class="sxs-lookup"><span data-stu-id="80e3f-206">The maximum number of parameters that can be specified for a single calculated field is 8.</span></span>

    ![Lista de fontes de dados do parâmetro](media/er-calculated-field-type-05.png)

5. <span data-ttu-id="80e3f-208">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-208">Select **OK**.</span></span>

<span data-ttu-id="80e3f-209">Ao adicionar esse parâmetro, você especifica a condição que deve estar em vigor para chamar esse campo calculado.</span><span class="sxs-lookup"><span data-stu-id="80e3f-209">By adding this parameter, you specify the condition that must be in place to call this calculated field.</span></span> <span data-ttu-id="80e3f-210">Quando você chama esse campo calculado, precisa especificar o argumento do parâmetro **Nível de Tributação** como um valor com o formato **Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-210">When you call this calculated field, you need to specify the argument of the **Taxation Level** parameter as a value with **String** format.</span></span>

   <span data-ttu-id="80e3f-211">Verifique se você definiu parâmetros apenas para os campos calculados que residem em um contêiner (**Lista de registros**, **Registro** ou **Contêiner**).</span><span class="sxs-lookup"><span data-stu-id="80e3f-211">Make sure that you define parameters only for those calculated fields that reside in a container (either **Record list**, **Record**, or **Container**).</span></span>

   <span data-ttu-id="80e3f-212">O parâmetro configurado está disponível na lista de fontes de dados do campo calculado.</span><span class="sxs-lookup"><span data-stu-id="80e3f-212">The configured parameter is available in the list of data sources for this calculated field.</span></span> <span data-ttu-id="80e3f-213">Você pode adicionar o parâmetro à expressão configurada selecionando **Adicionar fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-213">You can add the parameter to the configured expression by selecting **Add data source**.</span></span>

   ![Campos da fonte de dados](media/er-calculated-field-type-06.png)

### <a name="define-an-expression-for-adding-a-calculated-field"></a><span data-ttu-id="80e3f-215">Definir uma expressão para adicionar um campo calculado</span><span class="sxs-lookup"><span data-stu-id="80e3f-215">Define an expression for adding a calculated field</span></span>

1. <span data-ttu-id="80e3f-216">No campo **Fórmula**, insira:</span><span class="sxs-lookup"><span data-stu-id="80e3f-216">In the **Formula** field, enter:</span></span> 

    <span data-ttu-id="80e3f-217">**WHERE(\@.Summary2, \@.Summary2.grouped.Level =**</span><span class="sxs-lookup"><span data-stu-id="80e3f-217">**WHERE(\@.Summary2, \@.Summary2.grouped.Level =**</span></span>
    
2. <span data-ttu-id="80e3f-218">Selecione o parâmetro **Nível de Tributação** na lista de fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="80e3f-218">Select the **Taxation Level** parameter in the list of data sources.</span></span>
3. <span data-ttu-id="80e3f-219">Selecione **Adicionar fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-219">Select **Add data source**.</span></span>
4. <span data-ttu-id="80e3f-220">No campo **Fórmula**, finalize a expressão como:</span><span class="sxs-lookup"><span data-stu-id="80e3f-220">In the **Formula** field, finalize the expression as:</span></span>  

    <span data-ttu-id="80e3f-221">**WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Nível de Tributação')**</span><span class="sxs-lookup"><span data-stu-id="80e3f-221">**WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Taxation Level')**</span></span>

5. <span data-ttu-id="80e3f-222">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-222">Select **Save**.</span></span>

    ![Informações do campo da fonte de dados](media/er-calculated-field-type-07.png)

6. <span data-ttu-id="80e3f-224">Feche a página **Designer de fórmulas**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-224">Close the **Formula designer** page.</span></span>

### <a name="finish-adding-a-new-calculated-field"></a><span data-ttu-id="80e3f-225">Concluir a adição de um novo campo calculado</span><span class="sxs-lookup"><span data-stu-id="80e3f-225">Finish adding a new calculated field</span></span>

- <span data-ttu-id="80e3f-226">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-226">Select **OK**.</span></span>

<span data-ttu-id="80e3f-227">Na página **Designer de formato**, o campo calculado parametrizado configurado **Níveis** exige um argumento **Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-227">On the **Format designer** page, the configured parameterized calculated field **Levels** requires a **String** argument.</span></span>

![Lista expandida de níveis do campo calculado](media/er-calculated-field-type-08.png)

### <a name="use-the-configured-calculated-field-for-binding-format-elements"></a><span data-ttu-id="80e3f-229">Usar o campo calculado configurado para associar elementos de formato</span><span class="sxs-lookup"><span data-stu-id="80e3f-229">Use the configured calculated field for binding format elements</span></span>

1. <span data-ttu-id="80e3f-230">Selecione **Model.Data2.Levels** para selecionar o campo calculado configurado.</span><span class="sxs-lookup"><span data-stu-id="80e3f-230">Select **Model.Data2.Levels** to select the configured calculated field.</span></span>
2. <span data-ttu-id="80e3f-231">Selecione o elemento de formato **Statement.Taxation.Regular**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-231">Select the **Statement.Taxation.Regular** format element.</span></span>
3. <span data-ttu-id="80e3f-232">Selecione **Associar**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-232">Select **Bind**.</span></span>
4. <span data-ttu-id="80e3f-233">Selecione **Sim** para confirmar a substituição da fonte de dados usada atualmente, **Level1**, pela nova fonte de dados, **Níveis**, em todos os elementos de formato aninhados do elemento de formato selecionado.</span><span class="sxs-lookup"><span data-stu-id="80e3f-233">Select **Yes** to confirm the replacement of the currently used data source, **Level1**, by the new data source, **Levels**, in all nested format elements of the selected format element.</span></span>

    <span data-ttu-id="80e3f-234">A associação aplicada foi criada como uma chamada do campo calculado parametrizado.</span><span class="sxs-lookup"><span data-stu-id="80e3f-234">Applied binding has been built as a call of the parameterized calculated field.</span></span> <span data-ttu-id="80e3f-235">Por padrão, o nome do elemento de formato associado é usado como argumento para o campo calculado parametrizado nas seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="80e3f-235">By default, the name of the bound format element is used as an argument for parameterized calculated field under the following conditions:</span></span>

      - <span data-ttu-id="80e3f-236">O campo calculado é configurado para usar um único parâmetro.</span><span class="sxs-lookup"><span data-stu-id="80e3f-236">The calculated field is configured to use a single parameter.</span></span>
      - <span data-ttu-id="80e3f-237">O tipo de dados deste parâmetro é definido como **Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-237">The data type of this parameter is defined as **String**.</span></span>

    <span data-ttu-id="80e3f-238">Quando o nome do elemento de formato associado estiver em branco, o nome da fonte de dados do elemento será usada na associação aplicada.</span><span class="sxs-lookup"><span data-stu-id="80e3f-238">When the name of the bound format element is blank, the data source name of this element is used in applied binding.</span></span>

5. <span data-ttu-id="80e3f-239">Selecione o elemento de formato **Statement.Taxation.Reduced**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-239">Select the **Statement.Taxation.Reduced** format element.</span></span>
6. <span data-ttu-id="80e3f-240">Selecione **Associar**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-240">Select **Bind**.</span></span>
7. <span data-ttu-id="80e3f-241">Selecione **Sim** para confirmar a substituição da fonte de dados usada atualmente, **Level2**, pela nova fonte de dados, **Níveis**, em todos os elementos de formato aninhados sob o elemento de formato selecionado.</span><span class="sxs-lookup"><span data-stu-id="80e3f-241">Select **Yes** to confirm the replacement of the currently used data source, **Level2**, by the new data source, **Levels**, in all nested format elements under the selected format element.</span></span>
8. <span data-ttu-id="80e3f-242">Selecione o elemento de formato **Statement.Taxation.None**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-242">Select the **Statement.Taxation.None** format element.</span></span>
9. <span data-ttu-id="80e3f-243">Selecione **Associar**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-243">Select **Bind**.</span></span>
10. <span data-ttu-id="80e3f-244">Selecione **Sim** para confirmar a substituição da fonte de dados usada atualmente, **Level3**, pela nova fonte de dados, **Níveis**, em todos os elementos de formato aninhados sob o elemento de formato selecionado.</span><span class="sxs-lookup"><span data-stu-id="80e3f-244">Select **Yes** to confirm the replacement of the currently used data source, **Level3**, by the new data source, **Levels**, in all nested format elements under the selected format element.</span></span>

   <span data-ttu-id="80e3f-245">Quando você especificar o argumento do campo calculado parametrizado do elemento XML que representa o nível de tributação (por exemplo, **Model.Data2.Levels("Reduzido")** como um valor de texto), não será necessário fazer o mesmo para atributos XML aninhados; suas associações herdarão automaticamente o valor do argumento definido no nível pai (**Model.Data2.Levels.aggregated.Base**, não **Model.Data2.Levels("Reduzido").aggregated.Base**).</span><span class="sxs-lookup"><span data-stu-id="80e3f-245">When you specify the argument of the parameterized calculated field for the XML element representing taxation level (for example, **Model.Data2.Levels("Reduced")** as a text value), you don’t need to do the same for nested XML attributes—their bindings will automatically inherit the value of the argument defined on the parent level (**Model.Data2.Levels.aggregated.Base**, not **Model.Data2.Levels("Reduced").aggregated.Base**).</span></span>

<span data-ttu-id="80e3f-246">Não há suporte para chamadas recorrentes de qualquer campo calculado parametrizado.</span><span class="sxs-lookup"><span data-stu-id="80e3f-246">Recurrent calls of any parameterized calculated field are not supported.</span></span>

<span data-ttu-id="80e3f-247">Você pode selecionar **Editar fórmula** e alterar o argumento aplicado por padrão do campo calculado parametrizado na associação selecionada.</span><span class="sxs-lookup"><span data-stu-id="80e3f-247">You can select **Edit formula**, and change the applied-by-default argument of the parameterized calculated field in the selected binding.</span></span> <span data-ttu-id="80e3f-248">Se esse argumento estiver ausente, poderão ocorrer erros em tempo de execução. Os usuários serão informados sobre essa situação quando o formato atual for validado.</span><span class="sxs-lookup"><span data-stu-id="80e3f-248">If this argument is missing, it can cause errors at run time — users are informed about such a situation when the current format is validated.</span></span>

![Notificação de aviso de validação](media/er-calculated-field-type-10.png)

## <a name="configure-a-parameterized-calculated-field-to-return-a-record"></a><span data-ttu-id="80e3f-250">Configurar um campo calculado parametrizado para retornar um registro</span><span class="sxs-lookup"><span data-stu-id="80e3f-250">Configure a parameterized calculated field to return a record</span></span>
<span data-ttu-id="80e3f-251">Quando um campo calculado parametrizado retorna um registro, você precisa dar suporte à associação de campos individuais desse registro para elementos de formato.</span><span class="sxs-lookup"><span data-stu-id="80e3f-251">When a parameterized calculated field returns a record, you need to support binding of individual fields of this record to format elements.</span></span> <span data-ttu-id="80e3f-252">Nesses casos, não haverá nenhuma associação pai que contém o valor de um argumento para chamar um campo calculado parametrizado. Esse valor deve ser definido na associação do campo de um único registro.</span><span class="sxs-lookup"><span data-stu-id="80e3f-252">In such cases there will be no parent binding that contains the value of an argument to call a parameterized calculated field — this value must be defined in the binding of a single record’s field.</span></span>

### <a name="start-adding-a-new-calculated-field"></a><span data-ttu-id="80e3f-253">Começar a adicionar um novo campo calculado</span><span class="sxs-lookup"><span data-stu-id="80e3f-253">Start adding a new calculated field</span></span>

1. <span data-ttu-id="80e3f-254">Selecione o item **Model.Data2**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-254">Select the **Model.Data2** item.</span></span>
2. <span data-ttu-id="80e3f-255">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-255">Select **Add**.</span></span>
3. <span data-ttu-id="80e3f-256">Selecione **Funções\\Campo calculado**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-256">Select **Functions\\Calculated field**.</span></span>
4. <span data-ttu-id="80e3f-257">No campo **Nome**, insira **LevelRecord**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-257">In the **Name** field, enter **LevelRecord**.</span></span>
5. <span data-ttu-id="80e3f-258">Selecione **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-258">Select **Edit formula**.</span></span>

### <a name="define-a-parameter-for-adding-a-calculated-field"></a><span data-ttu-id="80e3f-259">Definir um parâmetro para adicionar um campo calculado</span><span class="sxs-lookup"><span data-stu-id="80e3f-259">Define a parameter for adding a calculated field</span></span>

1. <span data-ttu-id="80e3f-260">Selecione **Parâmetros**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-260">Select **Parameters**.</span></span>
2. <span data-ttu-id="80e3f-261">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-261">Select **New**.</span></span>
3. <span data-ttu-id="80e3f-262">No campo **Nome**, insira **Nível de Tributação**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-262">In the **Name** field, enter **Taxation Level**.</span></span>
4. <span data-ttu-id="80e3f-263">No campo **Tipo**, selecione **Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-263">In the **Type** field, select **String**.</span></span>
5. <span data-ttu-id="80e3f-264">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-264">Select **OK**.</span></span>

### <a name="define-an-expression-for-adding-a-calculated-field"></a><span data-ttu-id="80e3f-265">Definir uma expressão para adicionar um campo calculado</span><span class="sxs-lookup"><span data-stu-id="80e3f-265">Define an expression for adding a calculated field</span></span>

1. <span data-ttu-id="80e3f-266">No campo **Fórmula**, insira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="80e3f-266">In the **Formula** field, enter the following:</span></span>  
    
    <span data-ttu-id="80e3f-267">**FIRSTORNULL(\@.Levels(**</span><span class="sxs-lookup"><span data-stu-id="80e3f-267">**FIRSTORNULL(\@.Levels(**</span></span>

2. <span data-ttu-id="80e3f-268">Selecione o parâmetro **Nível de Tributação**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-268">Select the **Taxation Level** parameter.</span></span>
3. <span data-ttu-id="80e3f-269">Selecione **Adicionar fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-269">Select **Add data source**.</span></span>
4. <span data-ttu-id="80e3f-270">No campo **Fórmula**, acrescente **'Nível de Tributação'))** ao que você inseriu na Etapa 1 para finalizar a expressão como:</span><span class="sxs-lookup"><span data-stu-id="80e3f-270">In the **Formula** field, append **'Taxation Level'))** to what you entered in Step 1 to finalize the expression to:</span></span>  
    
    <span data-ttu-id="80e3f-271">**FIRSTORNULL(\@.Levels('Nível de Tributação'))**</span><span class="sxs-lookup"><span data-stu-id="80e3f-271">**FIRSTORNULL(\@.Levels('Taxation Level'))**</span></span>

5. <span data-ttu-id="80e3f-272">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-272">Select **Save**.</span></span>
6. <span data-ttu-id="80e3f-273">Feche a página **Designer de fórmulas**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-273">Close **the Formula designer** page.</span></span>

### <a name="finish-adding-a-new-calculated-field"></a><span data-ttu-id="80e3f-274">Concluir a adição de um novo campo calculado</span><span class="sxs-lookup"><span data-stu-id="80e3f-274">Finish adding a new calculated field</span></span>

-   <span data-ttu-id="80e3f-275">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-275">Select **OK**.</span></span>

### <a name="use-the-configured-calculated-field-to-bind-format-elements"></a><span data-ttu-id="80e3f-276">Usar o campo calculado configurado para associar elementos de formato</span><span class="sxs-lookup"><span data-stu-id="80e3f-276">Use the configured calculated field to bind format elements</span></span>

1. <span data-ttu-id="80e3f-277">Expanda **Model.Data2.LevelRecord** para selecionar o campo calculado configurado.</span><span class="sxs-lookup"><span data-stu-id="80e3f-277">Expand **Model.Data2.LevelRecord** to select the configured calculated field.</span></span>
2. <span data-ttu-id="80e3f-278">Expanda o contêiner **Model.Data2.LevelRecord.aggregated** do campo calculado configurado.</span><span class="sxs-lookup"><span data-stu-id="80e3f-278">Expand the **Model.Data2.LevelRecord.aggregated** container of the configured calculated field.</span></span>
3. <span data-ttu-id="80e3f-279">Selecione o campo **Model.Data2.LevelRecord.aggregated.Base**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-279">Select the **Model.Data2.LevelRecord.aggregated.Base** field.</span></span>
4. <span data-ttu-id="80e3f-280">Selecione o elemento de formato **Statement.Taxation.None**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-280">Select the **Statement.Taxation.None** format element.</span></span>
5. <span data-ttu-id="80e3f-281">Selecione **Desassociar**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-281">Select **Unbind**.</span></span>
6. <span data-ttu-id="80e3f-282">Selecione o elemento de formato **Statement.Taxation.None.Base**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-282">Select the **Statement.Taxation.None.Base** format element.</span></span>
7. <span data-ttu-id="80e3f-283">Selecione **Associar**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-283">Select **Bind**.</span></span>
8. <span data-ttu-id="80e3f-284">Selecione **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-284">Select **Edit formula**.</span></span>
9. <span data-ttu-id="80e3f-285">Altere a expressão para **Model.Data2.LevelRecord("Nenhum").aggregated.Base**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-285">Change the expression to **Model.Data2.LevelRecord("None").aggregated.Base**.</span></span>

![Expressão atualizada](media/er-calculated-field-type-11.png)

## <a name="remove-calculated-fields-that-are-not-used"></a><span data-ttu-id="80e3f-287">Remover campos calculados que não são usados</span><span class="sxs-lookup"><span data-stu-id="80e3f-287">Remove calculated fields that are not used</span></span>

1. <span data-ttu-id="80e3f-288">Selecione **Model.Data2.Level1**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-288">Select **Model.Data2.Level1**.</span></span>
2. <span data-ttu-id="80e3f-289">Selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-289">Select **Delete**.</span></span>
3. <span data-ttu-id="80e3f-290">Selecione **Model.Data2.Level2**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-290">Select **Model.Data2.Level2**.</span></span>
4. <span data-ttu-id="80e3f-291">Selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-291">Select **Delete**.</span></span>
5. <span data-ttu-id="80e3f-292">Selecione **Model.Data2.Level3**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-292">Select **Model.Data2.Level3**.</span></span>
6. <span data-ttu-id="80e3f-293">Selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-293">Select **Delete**.</span></span>
7. <span data-ttu-id="80e3f-294">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-294">Select **Save**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="80e3f-295">Você reutilizou o mesmo campo calculado **Model.Data2.Levels** várias vezes em associações de formato.</span><span class="sxs-lookup"><span data-stu-id="80e3f-295">You reused the same calculated field **Model.Data2.Levels** several times in format bindings.</span></span> <span data-ttu-id="80e3f-296">É muito mais fácil usar e manter um único campo calculado em vez de fazer isso para vários campos semelhantes.</span><span class="sxs-lookup"><span data-stu-id="80e3f-296">It is much easier to use and maintain a single calculated field instead of doing this for multiple similar fields.</span></span>

8. <span data-ttu-id="80e3f-297">Feche a página **Designer de formato**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-297">Close the **Format designer** page.</span></span>

## <a name="complete-adjusted-version-of-a-derived-format"></a><span data-ttu-id="80e3f-298">Concluir a versão ajustada de um formato de derivado</span><span class="sxs-lookup"><span data-stu-id="80e3f-298">Complete adjusted version of a derived format</span></span>

1. <span data-ttu-id="80e3f-299">Na Guia Rápida **Versões**, selecione **Alterar status**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-299">In the **Versions** FastTab, select **Change status**.</span></span>
2. <span data-ttu-id="80e3f-300">Selecione **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-300">Select **Complete**.</span></span>

## <a name="export-completed-version-of-a-derived-format"></a><span data-ttu-id="80e3f-301">Exportar a versão concluída de um formato de derivado</span><span class="sxs-lookup"><span data-stu-id="80e3f-301">Export completed version of a derived format</span></span>

1. <span data-ttu-id="80e3f-302">Selecione o formato **Formato para conhecer chamadas parametrizadas (personalizado)** na árvore de configurações.</span><span class="sxs-lookup"><span data-stu-id="80e3f-302">Select **Format to learn parameterized calls (custom)** format in the configurations tree.</span></span>
2. <span data-ttu-id="80e3f-303">Na Guia Rápida **Versões**, selecione a versão 1.1.1 concluída.</span><span class="sxs-lookup"><span data-stu-id="80e3f-303">In the **Versions** FastTab, select the completed version 1.1.1.</span></span>
3. <span data-ttu-id="80e3f-304">Selecione **Taxa de câmbio**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-304">Select **Exchange**.</span></span>
4. <span data-ttu-id="80e3f-305">Selecione **Exportar como arquivo XML**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-305">Select **Export as XML file**.</span></span>
5. <span data-ttu-id="80e3f-306">Armazene a configuração baixada localmente no formato XML.</span><span class="sxs-lookup"><span data-stu-id="80e3f-306">Store the downloaded configuration locally, in XML format.</span></span>

## <a name="test-er-formats"></a><span data-ttu-id="80e3f-307">Testar formatos de ER</span><span class="sxs-lookup"><span data-stu-id="80e3f-307">Test ER formats</span></span> 
<span data-ttu-id="80e3f-308">Você pode executar os formatos de ER inicial e aprimorados para garantir que os campos calculados parametrizados funcionam corretamente.</span><span class="sxs-lookup"><span data-stu-id="80e3f-308">You can run the initial and improved ER formats to make sure that configured parameterized calculated fields work properly.</span></span>

### <a name="import-er-configurations"></a><span data-ttu-id="80e3f-309">Importar configurações de ER</span><span class="sxs-lookup"><span data-stu-id="80e3f-309">Import ER configurations</span></span>
<span data-ttu-id="80e3f-310">Você pode importar configurações revisadas do RCS usando o repositório de ER do tipo **RCS**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-310">You can import reviewed configurations from RCS by using the ER repository of the **RCS** type.</span></span> <span data-ttu-id="80e3f-311">Se você já passou pelas etapas do tópico [Importar configurações do relatório eletrônico do Regulatory Configuration Service](rcs-download-configurations.md), use o repositório de ER configurado para importar as configurações discutidas anteriormente neste tópico para o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="80e3f-311">If you already went through the steps in the topic, [Import Electronic reporting configurations from Regulatory Configuration Services](rcs-download-configurations.md), use the configured ER repository to import configurations discussed earlier in this topic to your environment.</span></span> <span data-ttu-id="80e3f-312">Caso contrário, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="80e3f-312">Otherwise, follow these steps:</span></span>

1. <span data-ttu-id="80e3f-313">Selecione a empresa **DEMF** e, no painel padrão, selecione **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-313">Select the **DEMF** company and on the default dashboard, select **Electronic reporting**.</span></span>
2. <span data-ttu-id="80e3f-314">Selecione **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-314">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="80e3f-315">Importe as configurações do Centro de Download da Microsoft nesta sequência: modelo de dados, mapeamento do modelo, formato.</span><span class="sxs-lookup"><span data-stu-id="80e3f-315">Import the configurations from Microsoft Download Center in the following sequence: data model, model mapping, format.</span></span> <span data-ttu-id="80e3f-316">Execute as seguintes etapas para cada configuração de ER:</span><span class="sxs-lookup"><span data-stu-id="80e3f-316">Complete the following steps for each ER configuration:</span></span>

    1. <span data-ttu-id="80e3f-317">Selecione **Troca**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-317">Select **Exchange.**</span></span>
    2. <span data-ttu-id="80e3f-318">Selecione **Carregar do arquivo XML**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-318">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="80e3f-319">Selecione **Procurar** para selecionar a configuração de ER necessária em formato XML.</span><span class="sxs-lookup"><span data-stu-id="80e3f-319">Select **Browse** to select the required ER configuration in XML format.</span></span>
    4. <span data-ttu-id="80e3f-320">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-320">Select **OK**.</span></span>

4. <span data-ttu-id="80e3f-321">Importe a exportação do RCS versão 1.1.1 concluída do formato **Formato para conhecer chamadas parametrizadas (personalizado)**:</span><span class="sxs-lookup"><span data-stu-id="80e3f-321">Import the exported from RCS completed version 1.1.1 of the **Format to learn parameterized calls (custom)** format:</span></span>

    1. <span data-ttu-id="80e3f-322">Selecione **Troca**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-322">Select **Exchange.**</span></span>
    2. <span data-ttu-id="80e3f-323">Selecione **Carregar do arquivo XML**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-323">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="80e3f-324">Selecione **Procurar** para selecionar o arquivo **Formato para conhecer chamadas parametrizadas (personalizado)** armazenado localmente em formato XML.</span><span class="sxs-lookup"><span data-stu-id="80e3f-324">Select **Browse** to select the locally stored **Format to learn parameterized calls (custom)** file in XML format.</span></span>
    4. <span data-ttu-id="80e3f-325">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-325">Select **OK**.</span></span>

### <a name="run-er-formats"></a><span data-ttu-id="80e3f-326">Executar formatos de ER</span><span class="sxs-lookup"><span data-stu-id="80e3f-326">Run ER formats</span></span>

1. <span data-ttu-id="80e3f-327">Na árvore de configuração, expanda o conteúdo do item **Modelo para conhecer chamadas parametrizadas**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-327">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="80e3f-328">Selecione **Formato para conhecer chamadas parametrizadas**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-328">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="80e3f-329">Selecione **Executar** na faixa de opções mais superior.</span><span class="sxs-lookup"><span data-stu-id="80e3f-329">Select **Run** on the top-most ribbon.</span></span>
4. <span data-ttu-id="80e3f-330">Salve a saída gerada localmente.</span><span class="sxs-lookup"><span data-stu-id="80e3f-330">Save the locally generated output.</span></span>
5. <span data-ttu-id="80e3f-331">Selecione o item **Formato para conhecer chamadas parametrizadas (personalizado)**.</span><span class="sxs-lookup"><span data-stu-id="80e3f-331">Select the **Format to learn parameterized calls (custom)** item.</span></span>
6. <span data-ttu-id="80e3f-332">Selecione **Executar** na faixa de opções mais superior.</span><span class="sxs-lookup"><span data-stu-id="80e3f-332">Select **Run** on the top-most ribbon.</span></span>
7. <span data-ttu-id="80e3f-333">Salve a saída gerada localmente.</span><span class="sxs-lookup"><span data-stu-id="80e3f-333">Save the generated output locally.</span></span> 
8. <span data-ttu-id="80e3f-334">Compare o conteúdo das saídas geradas.</span><span class="sxs-lookup"><span data-stu-id="80e3f-334">Compare the contents of the generated outputs.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="80e3f-335">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="80e3f-335">Additional resources</span></span>
[<span data-ttu-id="80e3f-336">Designer de fórmulas no Relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="80e3f-336">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)
