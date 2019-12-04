---
title: Configurar os parâmetros de um formato de ER por entidade legal
description: Este tópico explica como configurar os parâmetros de um formato de relatório eletrônico (ER) por entidade legal.
author: NickSelin
manager: AnnBe
ms.date: 10/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.openlocfilehash: 9c5884bba494d2dd44f9204667144402a88ddec8
ms.sourcegitcommit: d6196d83c7b9166ddb4fe43a91e6bd0ad9da2099
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/31/2019
ms.locfileid: "2694329"
---
# <a name="set-up-the-parameters-of-an-er-format-per-legal-entity"></a><span data-ttu-id="04eb3-103">Configurar os parâmetros de um formato de ER por entidade legal</span><span class="sxs-lookup"><span data-stu-id="04eb3-103">Set up the parameters of an ER format per legal entity</span></span>

[!include[banner](../includes/banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="04eb3-104">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="04eb3-104">Prerequisites</span></span>

<span data-ttu-id="04eb3-105">Para concluir essas etapas, primeiro você deve concluir as etapas no tópico [Configurar formatos de ER para usar parâmetros especificados por entidade legal](er-app-specific-parameters-configure-format.md) .</span><span class="sxs-lookup"><span data-stu-id="04eb3-105">To complete these steps, you must first complete the steps in the [Configure ER formats to use parameters that are specified per legal entity](er-app-specific-parameters-configure-format.md) topic.</span></span>

<span data-ttu-id="04eb3-106">Para concluir os exemplos deste tópico, você deve ter acesso ao Microsoft Dynamics 365 Finance (Finance) para uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="04eb3-106">To complete the examples in this topic, you must have access to Microsoft Dynamics 365 Finance (Finance) for one of the following roles:</span></span>

- <span data-ttu-id="04eb3-107">Desenvolvedor de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="04eb3-107">Electronic reporting developer</span></span>
- <span data-ttu-id="04eb3-108">Consultor funcional de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="04eb3-108">Electronic reporting functional consultant</span></span>
- <span data-ttu-id="04eb3-109">Administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="04eb3-109">System administrator</span></span>

## <a name="import-er-configurations"></a><span data-ttu-id="04eb3-110">Importar configurações de ER</span><span class="sxs-lookup"><span data-stu-id="04eb3-110">Import ER configurations</span></span>

1.  <span data-ttu-id="04eb3-111">Entre no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="04eb3-111">Sign in to your environment.</span></span>
2.  <span data-ttu-id="04eb3-112">No painel padrão, selecione **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-112">On the default dashboard, select **Electronic reporting**.</span></span>
3.  <span data-ttu-id="04eb3-113">Selecione **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-113">Select **Reporting configurations**.</span></span>
4.  <span data-ttu-id="04eb3-114">Importe para a instância atual do Finance as configurações que exportou do Regulatory Configuration Services (RCS) enquanto estava concluindo as etapas no tópico [Configurar formatos de ER usar parâmetros especificados por entidade legal](er-app-specific-parameters-configure-format.md).</span><span class="sxs-lookup"><span data-stu-id="04eb3-114">Import, into the current instance of Finance, the configurations that you exported from Regulatory Configuration Services (RCS) while you were completing the steps in the [Configure ER formats to use parameters that are specified per legal entity](er-app-specific-parameters-configure-format.md) topic.</span></span> <span data-ttu-id="04eb3-115">Siga estas etapas para cada configuração de relatório eletrônico (ER), nesta ordem: modelo de dados, mapeamento de modelos e formatos.</span><span class="sxs-lookup"><span data-stu-id="04eb3-115">Follow these steps for each Electronic reporting (ER) configuration, in the following order: data model, model mapping, and formats.</span></span>

    1. <span data-ttu-id="04eb3-116">Selecione **Troca \> Carregar de um arquivo XML**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-116">Select **Exchange \> Load from XML file**.</span></span>
    2. <span data-ttu-id="04eb3-117">Selecione **Procurar** para selecionar o arquivo para a configuração de ER necessária no formato XML.</span><span class="sxs-lookup"><span data-stu-id="04eb3-117">Select **Browse** to select the file for the required ER configuration in XML format.</span></span>
    3. <span data-ttu-id="04eb3-118">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-118">Select **OK**.</span></span>
    
    <span data-ttu-id="04eb3-119">A ilustração a seguir mostra as configurações que você deve ter quando terminar.</span><span class="sxs-lookup"><span data-stu-id="04eb3-119">The following illustration shows the configurations that you must have when you've finished.</span></span>

    ![Página de configurações de ER](./media/GER-AppSpecParms-ImportedConfigurations.PNG)

## <a name="set-up-parameters-for-the-demf-company"></a><span data-ttu-id="04eb3-121">Configurar parâmetros para a empresa DEMF</span><span class="sxs-lookup"><span data-stu-id="04eb3-121">Set up parameters for the DEMF company</span></span>

<span data-ttu-id="04eb3-122">Você pode usar a estrutura de ER para configurar parâmetros específicos do aplicativo para um formato de ER.</span><span class="sxs-lookup"><span data-stu-id="04eb3-122">You can use the ER framework to set up application-specific parameters for an ER format.</span></span>

1.  <span data-ttu-id="04eb3-123">Selecione a entidade legal **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-123">Select the **DEMF** legal entity.</span></span>
2.  <span data-ttu-id="04eb3-124">Na árvore de configurações, selecione o formato **Formato para saber como pesquisar dados de LE**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-124">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
3.  <span data-ttu-id="04eb3-125">No Painel de Ação, na guia **Configurações**, no grupo **Parâmetros específicos do aplicativo**, selecione **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-125">On the Action Pane, on the **Configurations** tab, in the **Application specific parameters** group, select **Setup**.</span></span>

    ![Página de parâmetros específicos do aplicativo do ER](./media/GER-AppSpecParms-LookupForm.PNG)
    
    <span data-ttu-id="04eb3-127">Na página **Parâmetros específicos do aplicativo**, você pode configurar as regras para a fonte de dados **Seletor** do formato **Formato para saber como pesquisar dados de LE**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-127">On the **Application specific parameters** page, you can configure the rules for the **Selector** data source of the **Format to learn how to lookup LE data** format.</span></span>
    
    <span data-ttu-id="04eb3-128">Se o formato de ER de base contiver várias fontes de dados do tipo **Pesquisa**, selecione a fonte de dados desejada na guia rápida **Pesquisas** antes de começar a configurar o conjunto de regras para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="04eb3-128">If the base ER format will contain several data sources of the **Lookup** type, you must select the desired data source on the **Lookups** FastTab before you can start to configure the set of rules for the data source.</span></span>
    
    <span data-ttu-id="04eb3-129">Para cada fonte de dados, você pode configurar regras separadas para cada versão do formato de ER selecionado.</span><span class="sxs-lookup"><span data-stu-id="04eb3-129">For each data source, you can configure separate rules for each version of the selected ER format.</span></span>
    
    <span data-ttu-id="04eb3-130">O conjunto de regras inteiro para todas as fontes de dados de pesquisa que estão disponíveis na versão selecionada do formato de ER de base compõe os parâmetros específicos do aplicativo para o formato de ER.</span><span class="sxs-lookup"><span data-stu-id="04eb3-130">The whole set of rules for all lookup data sources that are available in the selected version of the base ER format makes up the application-specific parameters for the ER format.</span></span>

4.  <span data-ttu-id="04eb3-131">Selecione a versão **1.1.1** do formato de ER.</span><span class="sxs-lookup"><span data-stu-id="04eb3-131">Select version **1.1.1** of the ER format.</span></span>
5.  <span data-ttu-id="04eb3-132">Na guia rápida **Condições**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-132">On the **Conditions** FastTab, select **Add**.</span></span>
6.  <span data-ttu-id="04eb3-133">No campo **Código** do novo registro, selecione a seta suspensa para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="04eb3-133">In the **Code** field of the new record, select the drop-down arrow to open the lookup.</span></span>

    <span data-ttu-id="04eb3-134">A pesquisa apresenta a lista de códigos de imposto para seleção.</span><span class="sxs-lookup"><span data-stu-id="04eb3-134">The lookup presents the list of tax codes for selection.</span></span> <span data-ttu-id="04eb3-135">Essa lista é retornada pela fonte de dados **Model.Data.Tax** configurada no formato de ER de base.</span><span class="sxs-lookup"><span data-stu-id="04eb3-135">This list is returned by the **Model.Data.Tax** data source that has been configured in the base ER format.</span></span> <span data-ttu-id="04eb3-136">Como essa fonte dados contém o campo **Nome**, o nome de cada código de imposto aparece na pesquisa.</span><span class="sxs-lookup"><span data-stu-id="04eb3-136">Because this data source contains the **Name** field, the name of each tax code appears in the lookup.</span></span>

    ![Página de parâmetros específicos do aplicativo do ER](./media/GER-AppSpecParms-LookupForm-CodeFldPicker.PNG)
    
7.  <span data-ttu-id="04eb3-138">Selecione o código de imposto **VAT19**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-138">Select the **VAT19** tax code.</span></span>
8.  <span data-ttu-id="04eb3-139">No campo **Resultado da pesquisa** do novo registro, selecione a seta suspensa para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="04eb3-139">In the **Lookup result** field of the new record, select the drop-down arrow to open the lookup.</span></span> <span data-ttu-id="04eb3-140">A pesquisa apresenta a lista de valores para a enumeração de formato TaxationLevel para seleção.</span><span class="sxs-lookup"><span data-stu-id="04eb3-140">The lookup presents the list of values for the TaxationLevel format enumeration for selection.</span></span>

    <span data-ttu-id="04eb3-141">Observe que, se alemão for selecionado como o idioma preferencial do usuário conectado, as etiquetas dos valores na pesquisa estarão em alemão, uma vez que foram traduzidos no formato de ER de base.</span><span class="sxs-lookup"><span data-stu-id="04eb3-141">Note that, if German is selected as the preferred language of the user that you're signed in as, the labels of the values in the lookup will be in German, provided that they have been translated in the base ER format.</span></span> <span data-ttu-id="04eb3-142">Além disso, se a etiqueta de uma fonte de dados da pesquisa foi traduzida, será exibida no idioma preferencial do usuário na guia **Pesquisas**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-142">Additionally, if the label of a lookup data source has been translated, that label will appear in the user's preferred language on the **Lookups** tab.</span></span>

    ![Página de parâmetros específicos do aplicativo do ER](./media/GER-AppSpecParms-LookupForm-LookupFldPicker.PNG)

9.  <span data-ttu-id="04eb3-144">Selecione o valor **Tributação normal**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-144">Select the **Regular taxation** value.</span></span>

    <span data-ttu-id="04eb3-145">Ao adicionar esse registro, você define a seguinte regra: sempre que a fonte de dados de pesquisa **Seletor** for solicitada e o código de imposto **VAT19** for passado como argumento, **Tributação normal** será retornado como o nível de tributação solicitado.</span><span class="sxs-lookup"><span data-stu-id="04eb3-145">By adding this record, you define the following rule: Whenever the **Selector** lookup data source is requested, and the **VAT19** tax code is passed as an argument, **Regular taxation** will be returned as the requested taxation level.</span></span>

10. <span data-ttu-id="04eb3-146">Selecione **Adicionar** e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="04eb3-146">Select **Add**, and then follow these steps:</span></span>

    1. <span data-ttu-id="04eb3-147">No campo **Código**, selecione o código de imposto **InVAT19**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-147">In the **Code** field, select the **InVAT19** tax code.</span></span>
    2. <span data-ttu-id="04eb3-148">No campo **Resultado da pesquisa**, selecione o valor **Tributação normal**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-148">In the **Lookup result** field, select the **Regular taxation** value.</span></span>
    
11. <span data-ttu-id="04eb3-149">Selecione **Adicionar** novamente e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="04eb3-149">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="04eb3-150">No campo **Código**, selecione o código de imposto **VAT7**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-150">In the **Code** field, select the **VAT7** tax code.</span></span>
    2. <span data-ttu-id="04eb3-151">No campo **Resultado da pesquisa**, selecione o valor **Tributação reduzida**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-151">In the **Lookup result** field, select the **Reduced taxation** value.</span></span>
    
12. <span data-ttu-id="04eb3-152">Selecione **Adicionar** novamente e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="04eb3-152">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="04eb3-153">No campo **Código**, selecione o código de imposto **InVAT7**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-153">In the **Code** field, select the **InVAT7** tax code.</span></span>
    2. <span data-ttu-id="04eb3-154">No campo **Resultado da pesquisa**, selecione o valor **Tributação reduzida**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-154">In the **Lookup result** field, select the **Reduced taxation** value.</span></span>
    
13. <span data-ttu-id="04eb3-155">Selecione **Adicionar** novamente e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="04eb3-155">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="04eb3-156">No campo **Código**, selecione o código de imposto **THIRD**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-156">In the **Code** field, select the **THIRD** tax code.</span></span>
    2. <span data-ttu-id="04eb3-157">No campo **Resultado da pesquisa**, selecione o valor **Sem tributação**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-157">In the **Lookup result** field, select the **No taxation** value.</span></span>
    
14. <span data-ttu-id="04eb3-158">Selecione **Adicionar** novamente e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="04eb3-158">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="04eb3-159">No campo **Código**, selecione o código de imposto **InVAT0**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-159">In the **Code** field, select the **InVAT0** tax code.</span></span>
    2. <span data-ttu-id="04eb3-160">No campo **Resultado da pesquisa**, selecione o valor **Sem tributação**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-160">In the **Lookup result** field, select the **No taxation** value.</span></span>
    
15. <span data-ttu-id="04eb3-161">Selecione **Adicionar** novamente e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="04eb3-161">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="04eb3-162">No campo **Código**, selecione a opção **\*Não vazio\***.</span><span class="sxs-lookup"><span data-stu-id="04eb3-162">In the **Code** field, select the **\*Not blank\*** option.</span></span>
    2. <span data-ttu-id="04eb3-163">No campo **Resultado da pesquisa**, selecione o valor **Outro**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-163">In the **Lookup result** field, select the **Other** value.</span></span>
    
    <span data-ttu-id="04eb3-164">Ao adicionar esse último registro, você define a seguinte regra: sempre que o código de imposto que é passado como argumento não atender a nenhuma das regras anteriores, a fonte de dados de pesquisa retornará **Outro** como o nível de tributação solicitado.</span><span class="sxs-lookup"><span data-stu-id="04eb3-164">By adding this last record, you define the following rule: Whenever the tax code that is passed as an argument doesn't satisfy any of the previous rules, the lookup data source will return **Other** as the requested taxation level.</span></span>

    ![Página de parâmetros específicos do aplicativo do ER](./media/GER-AppSpecParms-LookupForm-RulesSet.PNG)
    
16. <span data-ttu-id="04eb3-166">No campo **Estado**, selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-166">In the **State** field, select **Completed**.</span></span>

    <span data-ttu-id="04eb3-167">Quando você executa uma versão de formato de ER que tem o status **Concluído** ou **Compartilhado**, esse conjunto de regras deve estar no estado **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-167">When you run an ER format version that has a status of either **Completed** or **Shared**, this set of rules must be in the **Completed** state.</span></span> <span data-ttu-id="04eb3-168">Do contrário, a execução do formato de ER de base será interrompida quando o formato tentar carregar dados desse conjunto de regras enquanto a fonte de dados de pesquisa **Seletor** estiver sendo executada.</span><span class="sxs-lookup"><span data-stu-id="04eb3-168">Otherwise, execution of the base ER format will be interrupted when the format tries to load data from this set of rules while the **Selector** lookup data source is being run.</span></span>
    
    <span data-ttu-id="04eb3-169">Quando você executa uma versão do formato de ER com o status **Rascunho**, o formato de ER de base pode acessar esse conjunto de regras, independentemente do estado.</span><span class="sxs-lookup"><span data-stu-id="04eb3-169">When you run an ER format version that has a status of **Draft**, the base ER format can access this set of rules, regardless of its state.</span></span>
    
17. <span data-ttu-id="04eb3-170">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-170">Select **Save**.</span></span>
18. <span data-ttu-id="04eb3-171">Feche a página **Parâmetros específicos do aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-171">Close the **Application specific parameters** page.</span></span>

## <a name="run-the-er-format-in-the-demf-company"></a><span data-ttu-id="04eb3-172">Executar o formato de ER na empresa DEMF</span><span class="sxs-lookup"><span data-stu-id="04eb3-172">Run the ER format in the DEMF company</span></span>

1.  <span data-ttu-id="04eb3-173">Na árvore de configurações, selecione o formato **Formato para saber como pesquisar dados de LE**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-173">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
2.  <span data-ttu-id="04eb3-174">No Painel de Ação, selecione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-174">On the Action Pane, select **Run**.</span></span>
3.  <span data-ttu-id="04eb3-175">Na caixa de diálogo exibida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-175">In the dialog box that appears, select **OK**.</span></span>
4.  <span data-ttu-id="04eb3-176">Baixe a instrução que é gerada e armazene-a localmente.</span><span class="sxs-lookup"><span data-stu-id="04eb3-176">Download the statement that is generated and store it locally.</span></span>

    <span data-ttu-id="04eb3-177">Na instrução gerada, observe que o resumo do código de imposto **InVAT7** foi colocado no nível **Reduzido** e os resumos dos códigos de imposto **VAT19** e **InVA19** foram colocados no nível **Normal**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-177">In the generated statement, notice that the summary of the **InVAT7** tax code has been put on the **Reduced** level, and the summaries of the **VAT19** and **InVA19** tax codes have been put on the **Regular** level.</span></span> <span data-ttu-id="04eb3-178">Esse comportamento é determinado pela configuração no conjunto de regras dependente da entidade legal.</span><span class="sxs-lookup"><span data-stu-id="04eb3-178">This behavior is determined by the configuration in the legal entity–dependent set of rules.</span></span>
    
5.  <span data-ttu-id="04eb3-179">Vá para **Imposto \> Impostos indiretos \> Impostos \> Códigos de imposto**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-179">Go to **Tax \> Indirect taxes \> Sales tax \> Sales tax codes**.</span></span>
6.  <span data-ttu-id="04eb3-180">Selecione o código de imposto **InVAT7**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-180">Select the **InVAT7** tax code.</span></span>
7.  <span data-ttu-id="04eb3-181">No Painel de Ação, na guia **Código de imposto**, no grupo **Consultas**, selecione **Imposto lançado** para exibir informações sobre o valor de impostos e as taxas de impostos aplicadas por código de imposto.</span><span class="sxs-lookup"><span data-stu-id="04eb3-181">On the Action Pane, on the **Sales tax code** tab, in the **Inquiries** group, select **Posted sales tax** to view information about the tax value and applied tax rate per tax code.</span></span>

    ![Página Imposto lançado](./media/GER-AppSpecParms-Statement.PNG)

8.  <span data-ttu-id="04eb3-183">Feche a página Imposto lançado.</span><span class="sxs-lookup"><span data-stu-id="04eb3-183">Close the Posted sales tax page.</span></span>

## <a name="set-up-parameters-for-the-usmf-company"></a><span data-ttu-id="04eb3-184">Configurar parâmetros para a empresa USMF</span><span class="sxs-lookup"><span data-stu-id="04eb3-184">Set up parameters for the USMF company</span></span>

1.  <span data-ttu-id="04eb3-185">Selecione a entidade legal **USMF**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-185">Select the **USMF** legal entity.</span></span>
2.  <span data-ttu-id="04eb3-186">Vá para **Administração da organização \> Relatório eletrônico \> Configurações**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-186">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
3.  <span data-ttu-id="04eb3-187">Na árvore de configurações, expanda o item **Modelo para conhecer chamadas parametrizadas**, expanda o item **Formato para conhecer chamadas parametrizadas** e selecione o formato **Formato para saber como pesquisar dados de LE**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-187">In the configurations tree, expand the **Model to learn parameterized calls** item, expand the **Format to learn parameterized calls** item, and select the **Format to learn how to lookup LE data** format.</span></span>
4.  <span data-ttu-id="04eb3-188">No Painel de Ação, na guia **Configurações**, no grupo **Parâmetros específicos do aplicativo**, selecione **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-188">On the Action Pane, on the **Configurations** tab, in the **Application specific parameters** group, select **Setup**.</span></span>
5.  <span data-ttu-id="04eb3-189">Selecione a versão **1.1.1** do formato de ER selecionado.</span><span class="sxs-lookup"><span data-stu-id="04eb3-189">Select version **1.1.1** of the selected ER format.</span></span>
6.  <span data-ttu-id="04eb3-190">Na guia rápida **Condições**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-190">On the **Conditions** FastTab, select **Add**.</span></span>
7.  <span data-ttu-id="04eb3-191">No campo **Código** do novo registro, selecione a seta suspensa para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="04eb3-191">In the **Code** field of the new record, select the drop-down arrow to open the lookup.</span></span>

    <span data-ttu-id="04eb3-192">Agora a pesquisa apresenta a lista de códigos de imposto para o imposto da empresa **USMF** para seleção.</span><span class="sxs-lookup"><span data-stu-id="04eb3-192">The lookup now presents the list of tax codes for the **USMF** company tax for selection.</span></span>

    ![Página de parâmetros específicos do aplicativo do ER](./media/GER-AppSpecParms-LookupForm-CodeFldPicker2.PNG)
    
8.  <span data-ttu-id="04eb3-194">Selecione o código de imposto **ISENTO**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-194">Select the **EXEMPT** tax code.</span></span>
9.  <span data-ttu-id="04eb3-195">No campo **Resultado da pesquisa** do novo registro, selecione o valor **Sem tributação**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-195">In the **Lookup resul**t field of the new record, select the **No taxation** value.</span></span>
10. <span data-ttu-id="04eb3-196">Selecione **Adicionar** novamente.</span><span class="sxs-lookup"><span data-stu-id="04eb3-196">Select **Add** again.</span></span>
11. <span data-ttu-id="04eb3-197">No campo **Código** do novo registro, selecione a opção **\*Não vazio\***.</span><span class="sxs-lookup"><span data-stu-id="04eb3-197">In the **Code** field of the new record, select the **\*Not blank\*** option.</span></span>
12. <span data-ttu-id="04eb3-198">No campo **Resultado da pesquisa** do novo registro, selecione o valor **Tributação normal**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-198">In the **Lookup result** field of the new record, select the **Regular taxation** value.</span></span>
13. <span data-ttu-id="04eb3-199">No campo **Estado**, selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-199">In the **State** field, select **Completed**.</span></span>
14. <span data-ttu-id="04eb3-200">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-200">Select **Save**.</span></span>

    ![Página de parâmetros específicos do aplicativo do ER](./media/GER-AppSpecParms-LookupForm-RulesSet2.PNG)
    
15. <span data-ttu-id="04eb3-202">Feche a página **Parâmetros específicos do aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-202">Close the **Application specific parameters** page.</span></span>

## <a name="run-the-er-format-in-the-usmf-company"></a><span data-ttu-id="04eb3-203">Executar o formato de ER na empresa USMF</span><span class="sxs-lookup"><span data-stu-id="04eb3-203">Run the ER format in the USMF company</span></span>

1.  <span data-ttu-id="04eb3-204">Na árvore de configurações, selecione o formato **Formato para saber como pesquisar dados de LE**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-204">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
2.  <span data-ttu-id="04eb3-205">No Painel de Ação, selecione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-205">On the Action Pane, select **Run**.</span></span>
3.  <span data-ttu-id="04eb3-206">Na caixa de diálogo exibida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-206">In the dialog box that appears, select **OK**.</span></span>
4.  <span data-ttu-id="04eb3-207">Baixe a instrução que é gerada e armazene-a localmente.</span><span class="sxs-lookup"><span data-stu-id="04eb3-207">Download the statement that is generated and store it locally.</span></span>

    <span data-ttu-id="04eb3-208">Na instrução gerada, observe que agora você reutilizou o mesmo formato de ER para outra entidade legal, mas sem fazer quaisquer ajustes ao formato de ER.</span><span class="sxs-lookup"><span data-stu-id="04eb3-208">In the generated statement, notice that you've now reused the same ER format for a different legal entity, but without making any adjustments to the ER format.</span></span>

## <a name="reuse-legal-entitydependent-parameters"></a><span data-ttu-id="04eb3-209">Reutilizar parâmetros dependentes da entidade legal</span><span class="sxs-lookup"><span data-stu-id="04eb3-209">Reuse legal entity–dependent parameters</span></span>

### <a name="export-parameters"></a><span data-ttu-id="04eb3-210">Exportar parâmetros</span><span class="sxs-lookup"><span data-stu-id="04eb3-210">Export parameters</span></span>

1.  <span data-ttu-id="04eb3-211">Ir para **Administração da organização \> Espaços de trabalho \> Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-211">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>
2.  <span data-ttu-id="04eb3-212">Selecione **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-212">Select **Reporting configurations**.</span></span>
3.  <span data-ttu-id="04eb3-213">Na árvore de configurações, selecione o formato **Formato para saber como pesquisar dados de LE**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-213">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
4.  <span data-ttu-id="04eb3-214">No Painel de Ação, na guia **Configurações**, no grupo **Parâmetros específicos do aplicativo**, selecione **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-214">On the Action Pane, on the **Configurations** tab, in the **Application specific parameters** group, select **Setup**.</span></span>
5.  <span data-ttu-id="04eb3-215">Selecione a versão **1.1.1** do formato de ER.</span><span class="sxs-lookup"><span data-stu-id="04eb3-215">Select version **1.1.1** of the ER format.</span></span>
6.  <span data-ttu-id="04eb3-216">No Painel de Ações, selecione **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-216">On the Action Pane, select **Export**.</span></span>
7.  <span data-ttu-id="04eb3-217">Baixe o arquivo que é gerado e armazene-o localmente.</span><span class="sxs-lookup"><span data-stu-id="04eb3-217">Download the file that is generated and store it locally.</span></span>

    <span data-ttu-id="04eb3-218">Agora o conjunto configurado de parâmetros específicos do aplicativo foi exportado como arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="04eb3-218">The configured set of application-specific parameters has now been exported as an XML file.</span></span>

### <a name="import-parameters"></a><span data-ttu-id="04eb3-219">Importar parâmetros</span><span class="sxs-lookup"><span data-stu-id="04eb3-219">Import parameters</span></span>

1.  <span data-ttu-id="04eb3-220">Selecione a versão **1.1.2** do formato de ER.</span><span class="sxs-lookup"><span data-stu-id="04eb3-220">Select version **1.1.2** of the ER format.</span></span>
2.  <span data-ttu-id="04eb3-221">No Painel de Ações, selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-221">On the Action Pane, select **Import**.</span></span>
3.  <span data-ttu-id="04eb3-222">Selecione **Sim** para confirmar que você quer substituir os parâmetros específicos do aplicativo existentes para esta versão de formato.</span><span class="sxs-lookup"><span data-stu-id="04eb3-222">Select **Yes** to confirm that you want to override the existing application-specific parameters for this format version.</span></span>
4.  <span data-ttu-id="04eb3-223">Selecione **Procurar** para localizar o arquivo contendo os parâmetros específicos do aplicativo exportados da versão **1.1.1**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-223">Select **Browse** to find the file that contains the exported application-specific parameters for version **1.1.1**.</span></span>
5.  <span data-ttu-id="04eb3-224">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-224">Select **OK**.</span></span>

    <span data-ttu-id="04eb3-225">Agora a versão **1.1.2** do formato de ER tem os mesmos parâmetros específicos do aplicativo que você configurou originalmente para a versão **1.1.1**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-225">Version **1.1.2** of the ER format now has the same application-specific parameters that you originally configured for version **1.1.1**.</span></span>
    
    <span data-ttu-id="04eb3-226">Observe que os parâmetros específicos do aplicativo de um formato de ER são dependentes da entidade legal.</span><span class="sxs-lookup"><span data-stu-id="04eb3-226">Note that the application-specific parameters of an ER format are legal entity–dependent.</span></span> <span data-ttu-id="04eb3-227">Para reutilizar os parâmetros específicos do aplicativo que foram configurados para uma entidade legal em outra entidade legal, você deve exportá-los quando estiver conectado à primeira entidade legal e importá-los depois que se conectar à outra entidade legal.</span><span class="sxs-lookup"><span data-stu-id="04eb3-227">To reuse the application-specific parameters that were configured for one legal entity in a different legal entity, you must export them while you're signed in to the first legal entity and then import them after you sign in to the other legal entity.</span></span>

    <span data-ttu-id="04eb3-228">Você também pode usar esta abordagem para transferir parâmetros específicos do aplicativo relacionados a um formato de ER que foram configurados originalmente em uma instância do Finance para outra instância do Finance.</span><span class="sxs-lookup"><span data-stu-id="04eb3-228">You can also use this approach to transfer an ER format related application-specific parameters that were originally configured in one instance of Finance to another instance of Finance.</span></span>

    <span data-ttu-id="04eb3-229">Lembre-se de que, se você configurar parâmetros específicos do aplicativo para uma versão de um formato de ER e importar uma versão superior do mesmo formato para a instância atual do Finance, os parâmetros específicos do aplicativo existentes não serão aplicados para a versão importada.</span><span class="sxs-lookup"><span data-stu-id="04eb3-229">Be aware that if you configure application-specific parameters for one version of an ER format and import a higher version of the same format into the current Finance instance, the existing application-specific parameters won't be applied for the imported version.</span></span>
    
    <span data-ttu-id="04eb3-230">Lembre-se também que, quando você selecionar um arquivo para importação, a estrutura dos parâmetros específicos do aplicativo nesse arquivo é comparada com a estrutura da fonte de dados correspondente do tipo **Pesquisa** no formato de ER selecionado para importação.</span><span class="sxs-lookup"><span data-stu-id="04eb3-230">Also be aware that, when you select a file for import, the structure of the application-specific parameters in that file is compared with the structure of the corresponding data source of the **Lookup** type in the ER format that is selected for import.</span></span> <span data-ttu-id="04eb3-231">A importação é feita quando a estrutura de cada parâmetro específico do aplicativo corresponde à estrutura da fonte de dados correspondente no formato de ER selecionado para importação.</span><span class="sxs-lookup"><span data-stu-id="04eb3-231">The import is done when the structure of each application-specific parameter matches the structure of the corresponding data source in the ER format that is selected for import.</span></span> <span data-ttu-id="04eb3-232">Se as estruturas não corresponderem, você receberá uma mensagem de aviso informando que não é possível fazer a importação.</span><span class="sxs-lookup"><span data-stu-id="04eb3-232">If the structures don't match, you receive a warning message that states that the import can't be done.</span></span> <span data-ttu-id="04eb3-233">Se você forçar a importação, os parâmetros específicos do aplicativos existentes para o formato de ER selecionado serão eliminados e você deverá configurá-los desde o início.</span><span class="sxs-lookup"><span data-stu-id="04eb3-233">If you force the import to be done, the existing application-specific parameters for the selected ER format will be cleaned up, and you must set them up from the beginning.</span></span>

## <a name="relationship-between-application-specific-parameters-and-an-er-format"></a><span data-ttu-id="04eb3-234">Relacionamento entre parâmetros específicos do aplicativo e um formato de ER</span><span class="sxs-lookup"><span data-stu-id="04eb3-234">Relationship between application-specific parameters and an ER format</span></span>

<span data-ttu-id="04eb3-235">O relacionamento entre um formato de ER e seus parâmetros específicos do aplicativo é estabelecido pelo código de identificação exclusivo e independente da instância do formato de ER.</span><span class="sxs-lookup"><span data-stu-id="04eb3-235">The relationship between an ER format and its application-specific parameters is established by the ER format's instance-independent unique identification code.</span></span> <span data-ttu-id="04eb3-236">Portanto, quando você remove um formato de ER do Finance, os parâmetros específicos do aplicativo configurados para o formato de ER são mantidos na instância atual do Finance.</span><span class="sxs-lookup"><span data-stu-id="04eb3-236">Therefore, when you remove an ER format from Finance, the application-specific parameters that are configured for the ER format are kept in the current instance of Finance.</span></span> <span data-ttu-id="04eb3-237">Eles podem ser acessados sempre que o formato de ER de base for reimportado para esta instância do Finance.</span><span class="sxs-lookup"><span data-stu-id="04eb3-237">They can be accessed whenever the base ER format is reimported into this instance of Finance.</span></span>

## <a name="access-application-specific-parameters-by-using-the-er-framework"></a><span data-ttu-id="04eb3-238">Acessar parâmetros específicos do aplicativo usando a estrutura de ER</span><span class="sxs-lookup"><span data-stu-id="04eb3-238">Access application-specific parameters by using the ER framework</span></span>

<span data-ttu-id="04eb3-239">No exemplo anterior, você acessou parâmetros específicos do aplicativo de um formato de ER usando a estrutura de ER.</span><span class="sxs-lookup"><span data-stu-id="04eb3-239">In the preceding example, you have accessed application-specific parameters of an ER format by using the ER framework.</span></span> <span data-ttu-id="04eb3-240">Esta abordagem não permite restringir o acesso aos parâmetros específicos do aplicativo de um determinado formato de ER.</span><span class="sxs-lookup"><span data-stu-id="04eb3-240">This approach doesn't let you restrict access to the application-specific parameters of a specific ER format.</span></span> <span data-ttu-id="04eb3-241">Se você tiver que aplicar essas limitações, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="04eb3-241">If you must apply such restrictions, follow these steps.</span></span> 

1.  <span data-ttu-id="04eb3-242">Reutilize um item de menu **ERSolutionAppSpecificParametersDesigner** existente ou implemente seu próprio item de menu **ERSolutionAppSpecificParametersDesigner**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-242">Either reuse an existing **ERSolutionAppSpecificParametersDesigner** menu item, or implement your own **ERSolutionAppSpecificParametersDesigner** menu item.</span></span>

    ![Página do Visual Studio](./media/GER-AppSpecParms-LookupForm-Access1.PNG)
    
2.  <span data-ttu-id="04eb3-244">Siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="04eb3-244">Follow one of these steps:</span></span>

    1.  <span data-ttu-id="04eb3-245">Crie um novo botão de item de menu e vincule-o ao registro correspondente da tabela **ERSolutionTable** definindo a propriedade **Fonte de dados** como **ERSolutionTable**.</span><span class="sxs-lookup"><span data-stu-id="04eb3-245">Create a new menu item button, and link it to the corresponding record from the **ERSolutionTable** table by setting its **Data Source** property to **ERSolutionTable**.</span></span>
    
        ![Página do Visual Studio](./media/GER-AppSpecParms-LookupForm-Access2.PNG)
        
    2.  <span data-ttu-id="04eb3-247">Crie um botão simples e substitua o método **Clicked** conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="04eb3-247">Create a simple button, and override the **Clicked** method as shown in the following example.</span></span>
    
        <span data-ttu-id="04eb3-248">Usando esta abordagem, você pode especificar um ID de solução exclusivo (definido por meio do valor **GUID**) para permitir acesso aos parâmetros específicos do aplicativo de apenas um determinado formato de ER e às cópias descendentes que são derivadas dele.</span><span class="sxs-lookup"><span data-stu-id="04eb3-248">By using this approach, you can specify a unique solution ID (defined via the **GUID** value) to allow access to the application-specific parameters of only a specific ER format and descendant copies that have been derived from it.</span></span>
        
        ```
        public void clicked()
            {
                super();

                ERSolutionTable solutionTableRecord = ERSolutionTable::findByGUID(str2Guid('ADACCB2F-EFD1-4C90-877D-7E1E5D1AEE92'));

                Args args = new Args();
                args.record(solutionTableRecord);
                args.caller(this);

                new MenuFunction(menuItemDisplayStr(ERSolutionAppSpecificParametersDesigner), MenuItemType::Display)
                    .run(args);
            }
        ```

## <a name="additional-resources"></a><span data-ttu-id="04eb3-249">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="04eb3-249">Additional resources</span></span>

[<span data-ttu-id="04eb3-250">Designer de fórmulas no Relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="04eb3-250">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="04eb3-251">Configurar formatos de ER para usar parâmetros especificados por entidade legal</span><span class="sxs-lookup"><span data-stu-id="04eb3-251">Configure ER formats to use parameters that are specified per legal entity</span></span>](er-app-specific-parameters-configure-format.md)
