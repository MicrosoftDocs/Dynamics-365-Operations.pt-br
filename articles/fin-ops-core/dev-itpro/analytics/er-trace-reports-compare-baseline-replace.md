---
title: Melhorias no rastreamento dos resultados dos relatórios de ER gerados e na comparação deles com valores de linha de base
description: Este tópico descreve melhorias no recurso de linha de base ER no Microsoft Dynamics 365 for Finance and Operations versão 10.0.3 (junho de 2019).
author: NickSelin
manager: AnnBe
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 1579a0bb0dcf21ae16a54969e57ca88301041076
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568940"
---
# <a name="improvements-in-tracing-the-results-of-generated-er-reports-and-comparing-them-with-baseline-values"></a><span data-ttu-id="8f586-103">Melhorias no rastreamento dos resultados dos relatórios de ER gerados e na comparação deles com valores de linha de base</span><span class="sxs-lookup"><span data-stu-id="8f586-103">Improvements in tracing the results of generated ER reports and comparing them with baseline values</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="8f586-104">Este tópico descreve o primeiro conjunto de melhorias feitas no recurso de linha de base da estrutura ER (relatório eletrônico).</span><span class="sxs-lookup"><span data-stu-id="8f586-104">This topic describes the first set of improvements that have been made to the baseline feature of the Electronic reporting (ER) framework.</span></span> <span data-ttu-id="8f586-105">Essas melhorias estão disponíveis no Microsoft Dynamics 365 for Finance and Operations versão 10.0.3 (junho de 2019) e posterior.</span><span class="sxs-lookup"><span data-stu-id="8f586-105">These improvements are available in Microsoft Dynamics 365 for Finance and Operations version 10.0.3 (June 2019) and later.</span></span>

## <a name="automate-the-setting-of-baseline-rules"></a><span data-ttu-id="8f586-106">Automatize a configuração de regras de linha de base</span><span class="sxs-lookup"><span data-stu-id="8f586-106">Automate the setting of baseline rules</span></span>

<span data-ttu-id="8f586-107">O tópico [Rastrear resultados dos relatórios gerados e compará-los com os valores da linha de base](er-trace-reports-compare-baseline.md) explica como configurar a estrutura de ER para coletar informações sobre definições de formato de ER e avaliar os resultados dessas execuções.</span><span class="sxs-lookup"><span data-stu-id="8f586-107">The [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic explains how to configure the ER framework to collect information about ER format executions and evaluate the results of those executions.</span></span> <span data-ttu-id="8f586-108">O exemplo neste tópico mostra as etapas que devem ser concluídas.</span><span class="sxs-lookup"><span data-stu-id="8f586-108">The example in this topic shows the steps that must be completed.</span></span>

<span data-ttu-id="8f586-109">Estas são algumas das etapas:</span><span class="sxs-lookup"><span data-stu-id="8f586-109">Here are some of the steps:</span></span>

- <span data-ttu-id="8f586-110">Execute um formato de ER para gerar um arquivo de saída e armazenar o arquivo localmente.</span><span class="sxs-lookup"><span data-stu-id="8f586-110">Run an ER format to generate an outbound file, and store the file locally.</span></span>
- <span data-ttu-id="8f586-111">Adicione o arquivo armazenado localmente como um anexo da linha base que foi adicionada para um formato de ER.</span><span class="sxs-lookup"><span data-stu-id="8f586-111">Add the locally stored file as an attachment of the baseline that was added for an ER format.</span></span>
- <span data-ttu-id="8f586-112">Configure a regra de linha de base para a linha de base adicionada.</span><span class="sxs-lookup"><span data-stu-id="8f586-112">Configure the baseline rule for the added baseline.</span></span> <span data-ttu-id="8f586-113">Essa configuração inclui as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="8f586-113">This configuration includes the following steps:</span></span>

    - <span data-ttu-id="8f586-114">Especifique um elemento de formato de ER usado para gerar um arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="8f586-114">Specify an ER format element that is used to generate an outbound file.</span></span>
    - <span data-ttu-id="8f586-115">Selecione o anexo relativo ao arquivo de saída gerado.</span><span class="sxs-lookup"><span data-stu-id="8f586-115">Select the attachment that refers to the generated outbound file.</span></span>

> [!NOTE]
> <span data-ttu-id="8f586-116">Essas etapas devem ser executadas manualmente, mesmo que os novos recursos de ER permitam que sejam automatizadas.</span><span class="sxs-lookup"><span data-stu-id="8f586-116">These steps must be done manually, even though the new ER capabilities enable them to be automated.</span></span> <span data-ttu-id="8f586-117">Para saber mais sobre este recurso, conclua o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="8f586-117">To learn more about this feature, complete the following example.</span></span>

## <a name="example-automate-the-setting-of-baseline-rules"></a><span data-ttu-id="8f586-118">Exemplo: automatize a configuração de regras de linha de base</span><span class="sxs-lookup"><span data-stu-id="8f586-118">Example: Automate the setting of baseline rules</span></span>

<span data-ttu-id="8f586-119">Para concluir as etapas desse exemplo, primeiro você deve concluir as etapas do exemplo no tópico [Rastrear resultados dos relatórios gerados e compará-los com os valores da linha de base](er-trace-reports-compare-baseline.md) na seção "Adicione uma nova linha base para formato de ER criado".</span><span class="sxs-lookup"><span data-stu-id="8f586-119">To complete the steps in this example, you must first complete the steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic, up through the "Add a new baseline for a designed ER format" section.</span></span>

### <a name="review-added-baseline"></a><span data-ttu-id="8f586-120">Examine a linha de base adicionada</span><span class="sxs-lookup"><span data-stu-id="8f586-120">Review added baseline</span></span>

1. <span data-ttu-id="8f586-121">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="8f586-121">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="8f586-122">Selecione **Linhas de base**.</span><span class="sxs-lookup"><span data-stu-id="8f586-122">Select **Baselines**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8f586-123">O botão **Linhas de base** no Painel de Ações está disponível apenas quando o parâmetro de usuário ER **Executar em modo de depuração** está ativado para a empresa atual.</span><span class="sxs-lookup"><span data-stu-id="8f586-123">The **Baselines** button on the Action Pane is available only when the **Run in debug mode** ER user parameter is turned on for the current company.</span></span>

<span data-ttu-id="8f586-124">A linha de base foi adicionada para o formato selecionado **Formatar para aprender linhas de base de ER**, mas as regras de linha de base não foram adicionadas ainda para esta linha de base.</span><span class="sxs-lookup"><span data-stu-id="8f586-124">The baseline has been added for the selected **Format to learn ER baselines** format, but the baseline rules haven't yet been added for this baseline.</span></span>

<span data-ttu-id="8f586-125">![Página de linhas de base de formato de relatório eletrônico, ainda não há regras](media/GER-BaselineSample-AddBaseline2.PNG "Captura de tela da página Linhas de base do formato de relatório eletrônico")</span><span class="sxs-lookup"><span data-stu-id="8f586-125">![Electronic reporting format baselines page, no rules yet](media/GER-BaselineSample-AddBaseline2.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

### <a name="make-a-new-baseline-rule"></a><span data-ttu-id="8f586-126">Crie uma nova regra de linha de base</span><span class="sxs-lookup"><span data-stu-id="8f586-126">Make a new baseline rule</span></span>

1. <span data-ttu-id="8f586-127">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="8f586-127">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="8f586-128">Na árvore, expanda **Modelar para aprender linhas de base de ER**.</span><span class="sxs-lookup"><span data-stu-id="8f586-128">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="8f586-129">Na árvore, selecione **Modelar para aprender linhas de base de ER\\Formatar para aprender linhas de base de ER**.</span><span class="sxs-lookup"><span data-stu-id="8f586-129">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="8f586-130">Na Guia Rápida **Versões**, selecione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="8f586-130">On the **Versions** FastTab, select **Run**.</span></span>
5. <span data-ttu-id="8f586-131">No campo **Inserir Id**, digite **1**.</span><span class="sxs-lookup"><span data-stu-id="8f586-131">In the **Enter Id** field, enter **1**.</span></span>
6. <span data-ttu-id="8f586-132">Defina a opção **Criar arquivos de linha de base** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="8f586-132">Set the **Make baseline files** option to **Yes**.</span></span>
7. <span data-ttu-id="8f586-133">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f586-133">Select **OK**.</span></span>
8. <span data-ttu-id="8f586-134">Selecione **Linhas de base**.</span><span class="sxs-lookup"><span data-stu-id="8f586-134">Select **Baselines**.</span></span>

    <span data-ttu-id="8f586-135">![Página de linhas de base do formato de relatório eletrônico, linhas de base selecionadas](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Captura de tela da página Linhas de base do formato de relatório eletrônico")</span><span class="sxs-lookup"><span data-stu-id="8f586-135">![Electronic reporting format baselines page, baselines selected](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

    <span data-ttu-id="8f586-136">O arquivo de saída gerado foi automaticamente anexado à linha de base para do formato de ER executado.</span><span class="sxs-lookup"><span data-stu-id="8f586-136">The generated outbound file has been automatically attached to the baseline of the executed ER format.</span></span> <span data-ttu-id="8f586-137">A regra de linha base foi adicionada automaticamente a esta linha de base e também contém a referência ao arquivo anexado.</span><span class="sxs-lookup"><span data-stu-id="8f586-137">The baseline rule has been automatically added to this baseline and also contains the reference to the attached file.</span></span>

9. <span data-ttu-id="8f586-138">No campo **Nome**, digite **Linha de base 1**.</span><span class="sxs-lookup"><span data-stu-id="8f586-138">In the **Name** field, enter **Baseline 1**.</span></span>
10. <span data-ttu-id="8f586-139">No campo **Máscara de nome de arquivo**, insira **.xml**.</span><span class="sxs-lookup"><span data-stu-id="8f586-139">In the **File name mask** field, enter **.xml**.</span></span>
11. <span data-ttu-id="8f586-140">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8f586-140">Select **Save**.</span></span>

### <a name="run-the-format"></a><span data-ttu-id="8f586-141">Execute o formato</span><span class="sxs-lookup"><span data-stu-id="8f586-141">Run the format</span></span>

<span data-ttu-id="8f586-142">Agora você está pronto para concluir as etapas restantes no exemplo do tópico [Rastrear resultados dos relatórios gerados e compará-los com os valores da linha de base](er-trace-reports-compare-baseline.md), começando pela seção "Execute o formato de ER criado e verifique o log para analisar os resultados".</span><span class="sxs-lookup"><span data-stu-id="8f586-142">You're now ready to complete the remaining steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic, starting from the "Run the designed ER format and review the log to analyze the results" section.</span></span>

> [!NOTE]
> <span data-ttu-id="8f586-143">Quando você excluir a regra automaticamente adicionada na Guia Rápida **Linhas de base**, o anexo referenciado não será excluído automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8f586-143">When you delete the automatically added baseline rule on the **Baselines** FastTab, the referenced attachment isn't automatically deleted.</span></span>

## <a name="configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a><span data-ttu-id="8f586-144">Configure a linha de base de forma que ela constantemente ignore partes alteradas da saída de ER</span><span class="sxs-lookup"><span data-stu-id="8f586-144">Configure the baseline so that it ignores constantly changing parts of the ER output</span></span>

<span data-ttu-id="8f586-145">Quando um formato de ER foi criado para conter informações que são alteradas quando o formato é executado, deve-se exigir que o formato utilize o recurso de linha de base de ER para comparar os resultados gerados com os valores de linha de base.</span><span class="sxs-lookup"><span data-stu-id="8f586-145">When an ER format has been designed to contain information that is changed when the format is run, the format must be required to use the ER baseline feature to compare the generated results with baseline values.</span></span> <span data-ttu-id="8f586-146">Por exemplo, as informações podem ser a data e a hora de processamento ou o identificador exclusivo de um documento gerado em diferentes formatos (identificador global exclusivo \[GUID\] etc.).</span><span class="sxs-lookup"><span data-stu-id="8f586-146">For example, the information might be the processing date and time or the unique identifier of a generated document in different formats (globally unique identifier \[GUID\], and so on).</span></span> <span data-ttu-id="8f586-147">Novos recursos de ER permitem configurar a regra de linha base de forma que ela ignore os elementos variáveis de um formato de ER quando o formato for executado visando comparar valores de linha base com os resultados da execução do formato.</span><span class="sxs-lookup"><span data-stu-id="8f586-147">The new ER capabilities let you configure the baseline rule so that it ignores changeable elements of an ER format when the format is run with the purpose of comparing baseline values with the results of the format's execution.</span></span> <span data-ttu-id="8f586-148">Para saber mais sobre este recurso, conclua o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="8f586-148">To learn more about this feature, complete the following example.</span></span>

## <a name="example-configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a><span data-ttu-id="8f586-149">Exemplo: configure a linha de base de forma que ela constantemente ignore partes alteradas da saída de ER</span><span class="sxs-lookup"><span data-stu-id="8f586-149">Example: Configure the baseline so that it ignores constantly changing parts of the ER output</span></span>

<span data-ttu-id="8f586-150">Para concluir as etapas desse exemplo, primeiro você deve concluir as etapas no exemplo do tópico [Rastrear resultados dos relatórios gerados e compará-los com os valores da linha de base](er-trace-reports-compare-baseline.md).</span><span class="sxs-lookup"><span data-stu-id="8f586-150">To complete the steps in this example, you must first complete the steps in the example in the [Trace generated report results and compare them with baseline values](er-trace-reports-compare-baseline.md) topic.</span></span>

### <a name="modify-a-configured-er-format"></a><span data-ttu-id="8f586-151">Modifique o formato de um ER configurado</span><span class="sxs-lookup"><span data-stu-id="8f586-151">Modify a configured ER format</span></span>

1. <span data-ttu-id="8f586-152">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="8f586-152">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="8f586-153">Na árvore, expanda **Modelar para aprender linhas de base de ER**.</span><span class="sxs-lookup"><span data-stu-id="8f586-153">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="8f586-154">Na árvore, selecione **Modelar para aprender linhas de base de ER\\Formatar para aprender linhas de base de ER**.</span><span class="sxs-lookup"><span data-stu-id="8f586-154">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="8f586-155">Selecione **Designer**.</span><span class="sxs-lookup"><span data-stu-id="8f586-155">Select **Designer**.</span></span>
5. <span data-ttu-id="8f586-156">Na árvore, selecione **Saída\\Documento**.</span><span class="sxs-lookup"><span data-stu-id="8f586-156">In the tree, select **Output\\Document**.</span></span>
6. <span data-ttu-id="8f586-157">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8f586-157">Select **Add**.</span></span>
7. <span data-ttu-id="8f586-158">Na caixa de diálogo suspensa, na árvore, selecione **XML\\Atributo**.</span><span class="sxs-lookup"><span data-stu-id="8f586-158">In the drop-down dialog box, in the tree, select **XML\\Attribute**.</span></span>
8. <span data-ttu-id="8f586-159">No campo **Nome**, digite **ProcessamentoDataHora**.</span><span class="sxs-lookup"><span data-stu-id="8f586-159">In the **Name** field, enter **ProcessingDateTime**.</span></span>
9. <span data-ttu-id="8f586-160">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f586-160">Select **OK**.</span></span>
10. <span data-ttu-id="8f586-161">Na guia **Mapeamento**, na árvore, selecione **Saída\\Documento\\ProcessamentoDataHora**.</span><span class="sxs-lookup"><span data-stu-id="8f586-161">On the **Mapping** tab, in the tree, select **Output\\Document\\ProcessingDateTime**.</span></span>
11. <span data-ttu-id="8f586-162">Selecione **Editar fórmula**.</span><span class="sxs-lookup"><span data-stu-id="8f586-162">Select **Edit formula**.</span></span>
12. <span data-ttu-id="8f586-163">No campo **Fórmula**, insira a seguinte expressão: **DATETIMEFORMAT(NOW(), "O")**</span><span class="sxs-lookup"><span data-stu-id="8f586-163">In the **Formula** field, enter the following expression: **DATETIMEFORMAT(NOW(), "O")**</span></span>
13. <span data-ttu-id="8f586-164">Selecione **Salvar** e **Testar**.</span><span class="sxs-lookup"><span data-stu-id="8f586-164">Select **Save**, and then select **Test**.</span></span>
14. <span data-ttu-id="8f586-165">Selecione **Testar** novamente para repetir o teste da expressão configurada.</span><span class="sxs-lookup"><span data-stu-id="8f586-165">Select **Test** again to retest the configured expression.</span></span>

    <span data-ttu-id="8f586-166">![Página Designer de fórmulas](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Captura de tela de página Designer de fórmulas")</span><span class="sxs-lookup"><span data-stu-id="8f586-166">![Formula designer page](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Screenshot of the Formula designer page")</span></span>

    > [!NOTE]
    > <span data-ttu-id="8f586-167">A guia **Resultado de teste** mostra que a expressão configurada retorna uma data e um valor de tempo diferentes sempre que chamada.</span><span class="sxs-lookup"><span data-stu-id="8f586-167">The **Test result** tab shows that the configured expression returns a different date and time value whenever it's called.</span></span>

15. <span data-ttu-id="8f586-168">Feche a página **Designer de fórmulas** e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8f586-168">Close the **Formula designer** page, and then select **Save**.</span></span>

    <span data-ttu-id="8f586-169">![Página do designer de formatos](media/GER-BaselineSample-FormatMappingDesign2.PNG "Captura de tela da página Designer de formato")</span><span class="sxs-lookup"><span data-stu-id="8f586-169">![Format designer page](media/GER-BaselineSample-FormatMappingDesign2.PNG "Screenshot of the Format designer page")</span></span>

16. <span data-ttu-id="8f586-170">Feche a página **Designer de formato**.</span><span class="sxs-lookup"><span data-stu-id="8f586-170">Close the **Format designer** page.</span></span>

### <a name="remove-an-existing-baseline-rule"></a><span data-ttu-id="8f586-171">Remova uma regra da linha de base existente</span><span class="sxs-lookup"><span data-stu-id="8f586-171">Remove an existing baseline rule</span></span>

1. <span data-ttu-id="8f586-172">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="8f586-172">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="8f586-173">Selecione **Linhas de base**.</span><span class="sxs-lookup"><span data-stu-id="8f586-173">Select **Baselines**.</span></span>
3. <span data-ttu-id="8f586-174">Na lista de linhas de base, selecione a linha de base que está configurada no formato **Formato para aprender linhas de base de ER**.</span><span class="sxs-lookup"><span data-stu-id="8f586-174">In the list of baselines, select the baseline that is configured for the **Format to learn ER baselines** format.</span></span>
4. <span data-ttu-id="8f586-175">Na Guia Rápida **Linhas de base**, selecione **Excluir** para remover a regra de linha base que você configurou antes.</span><span class="sxs-lookup"><span data-stu-id="8f586-175">On the **Baselines** FastTab, select **Delete** to remove the baseline rule that you configured earlier.</span></span>

<span data-ttu-id="8f586-176">![Página de linhas de base de formato de relatório eletrônico, excluída](media/GER-BaselineSample-AddBaseline3.PNG "Captura de tela da página Linhas de base do formato de relatório eletrônico")</span><span class="sxs-lookup"><span data-stu-id="8f586-176">![Electronic reporting format baselines page, deleted](media/GER-BaselineSample-AddBaseline3.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

### <a name="define-replacements-for-bindings-of-designed-er-format"></a><span data-ttu-id="8f586-177">Defina substituições para associações de formato de ER criado</span><span class="sxs-lookup"><span data-stu-id="8f586-177">Define replacements for bindings of designed ER format</span></span>

1. <span data-ttu-id="8f586-178">Na página **Configurações**, na Guia Rápida **Substituições**, marque **Selecionar componentes**.</span><span class="sxs-lookup"><span data-stu-id="8f586-178">On the **Configurations** page, on the **Replacements** FastTab, select **Select components**.</span></span>
2. <span data-ttu-id="8f586-179">Na árvore de componentes de formato, expanda **Saída**, expanda **Saída\\Documento** e marque a caixa de seleção **Saída\\Documento\\ProcessamentoDataHora**.</span><span class="sxs-lookup"><span data-stu-id="8f586-179">In the format components tree, expand **Output**, expand **Output\\Document**, and then select the check box for **Output\\Document\\ProcessingDateTime**.</span></span>
3. <span data-ttu-id="8f586-180">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f586-180">Select **OK**.</span></span>

<span data-ttu-id="8f586-181">![Página de linhas de base de formato de relatório eletrônico, componentes](media/GER-BaselineSample-AddBaseline4.PNG "Captura de tela da página Linhas de base do formato de relatório eletrônico")</span><span class="sxs-lookup"><span data-stu-id="8f586-181">![Electronic reporting format baselines page, components](media/GER-BaselineSample-AddBaseline4.PNG "Screenshot of the Electronic reporting format baselines page")</span></span>

<span data-ttu-id="8f586-182">O componente de formato de ER selecionado foi adicionado à lista de componentes na Guia Rápida **Substituições**.</span><span class="sxs-lookup"><span data-stu-id="8f586-182">The selected ER format component has been added to the list of components on the **Replacements** FastTab.</span></span> <span data-ttu-id="8f586-183">Quando o formato de ER básico for executado no modo de depuração, a associação de formato para cada componentes será substituída pela associação que é exibida na coluna **Associação**.</span><span class="sxs-lookup"><span data-stu-id="8f586-183">When the base ER format is run in debug mode, the format's binding for each component will be replaced by the binding that is shown in the **Binding** column.</span></span> <span data-ttu-id="8f586-184">Para alterar a associação padrão de um componente listado na Guia Rápida **Substituições**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="8f586-184">To change the default binding for a component that is listed on the **Replacements** FastTab, select **Edit**.</span></span>

### <a name="make-a-new-baseline-rule"></a><span data-ttu-id="8f586-185">Crie uma nova regra de linha de base</span><span class="sxs-lookup"><span data-stu-id="8f586-185">Make a new baseline rule</span></span>

<span data-ttu-id="8f586-186">Siga as etapas da seção "Exemplo: automatize a configuração de regras de linha de base" apresentada antes neste tópico.</span><span class="sxs-lookup"><span data-stu-id="8f586-186">Follow the steps in the "Example: Automate the setting of baseline rules" section earlier in this topic.</span></span> <span data-ttu-id="8f586-187">Uma notificação avisa que o arquivo de saída foi gerado usando configurações de linha de base e que houve uma substituição forçada das associações de formato.</span><span class="sxs-lookup"><span data-stu-id="8f586-187">A notification warns you that the outbound file has been generated by using baseline settings, and that a forced replacement of the format bindings has occurred.</span></span>

<span data-ttu-id="8f586-188">![Notificação da página Configurações](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Captura de tela da notificação na página Configurações")</span><span class="sxs-lookup"><span data-stu-id="8f586-188">![Notification on the Configurations page](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Screenshot of the notification on the Configurations page")</span></span>

### <a name="suppress-warnings-about-the-replacement-of-format-bindings"></a><span data-ttu-id="8f586-189">Suprima avisos sobre a substituição de associações de formato</span><span class="sxs-lookup"><span data-stu-id="8f586-189">Suppress warnings about the replacement of format bindings</span></span>

<span data-ttu-id="8f586-190">Ao configurar parâmetros específicos de ER, você pode suprimir notificações que avisam sobre a substituição de associações de formato.</span><span class="sxs-lookup"><span data-stu-id="8f586-190">By setting specific ER parameters, you can suppress notifications that warn about the replacement of format bindings.</span></span> <span data-ttu-id="8f586-191">Essa supressão pode ser útil quando as associações de formato são substituídas de um modo autônomo usando a Regression Suite Automation Tool.</span><span class="sxs-lookup"><span data-stu-id="8f586-191">This suppression can be useful when format bindings are replaced in an unattended mode by using the Regression Suite Automation Tool.</span></span> <span data-ttu-id="8f586-192">Nesse caso, o aviso pode ser considerado uma falha do caso de teste que está em execução.</span><span class="sxs-lookup"><span data-stu-id="8f586-192">In this case, the warning can be considered a failure of the test case that is running.</span></span>

1. <span data-ttu-id="8f586-193">Na página **Configurações**, no Painel de Ações, na guia **Configurações**, selecione **Parâmetros de usuário**.</span><span class="sxs-lookup"><span data-stu-id="8f586-193">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, select **User parameters**.</span></span>
2. <span data-ttu-id="8f586-194">Defina a opção **Suprimir avisos de linha de base** como **Sim** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f586-194">Set the **Suppress baseline warnings** option to **Yes**, and then select **OK**.</span></span>

### <a name="review-the-generated-baseline-file"></a><span data-ttu-id="8f586-195">Revise o arquivo de linha de base gerado.</span><span class="sxs-lookup"><span data-stu-id="8f586-195">Review the generated baseline file</span></span>

1. <span data-ttu-id="8f586-196">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="8f586-196">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="8f586-197">Selecione **Linhas de base**.</span><span class="sxs-lookup"><span data-stu-id="8f586-197">Select **Baselines**.</span></span>
3. <span data-ttu-id="8f586-198">Selecione **Anexos**.</span><span class="sxs-lookup"><span data-stu-id="8f586-198">Select **Attachments**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="8f586-199">O arquivo gerado contém o texto de data e hora de processamento (**"#"**) da associação que foi configurada na regra de linha de base adicionada, não da associação de formato.</span><span class="sxs-lookup"><span data-stu-id="8f586-199">The generated file contains the processing date and time text (**"#"**) from the binding that was configured in the added baseline rule, not from the format's binding.</span></span>
    
4. <span data-ttu-id="8f586-200">Feche a página **Anexos**.</span><span class="sxs-lookup"><span data-stu-id="8f586-200">Close the **Attachments** page.</span></span>

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a><span data-ttu-id="8f586-201">Execute o formato de ER criado e verifique o log para analisar os resultados</span><span class="sxs-lookup"><span data-stu-id="8f586-201">Run the designed ER format and review the log to analyze the results</span></span>

1. <span data-ttu-id="8f586-202">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="8f586-202">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2. <span data-ttu-id="8f586-203">Na árvore, expanda **Modelar para aprender linhas de base de ER**.</span><span class="sxs-lookup"><span data-stu-id="8f586-203">In the tree, expand **Model to learn ER baselines**.</span></span>
3. <span data-ttu-id="8f586-204">Na árvore, selecione **Modelar para aprender linhas de base de ER\\Formatar para aprender linhas de base de ER**.</span><span class="sxs-lookup"><span data-stu-id="8f586-204">In the tree, select **Model to learn ER baselines\\Format to learn ER baselines**.</span></span>
4. <span data-ttu-id="8f586-205">Na Guia Rápida **Versões**, selecione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="8f586-205">On the **Versions** FastTab select **Run**.</span></span>
5. <span data-ttu-id="8f586-206">No campo **Inserir Id**, digite **1**.</span><span class="sxs-lookup"><span data-stu-id="8f586-206">In the **Enter Id** field, type **1**.</span></span>
6. <span data-ttu-id="8f586-207">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="8f586-207">Select **OK**.</span></span>
7. <span data-ttu-id="8f586-208">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Logs de depuração de configuração**.</span><span class="sxs-lookup"><span data-stu-id="8f586-208">Go to **Organization administration** \> **Electronic reporting** \> **Configuration debug logs**.</span></span>

<span data-ttu-id="8f586-209">O log de execução contém informações sobre os resultados da comparação do arquivo gerado com a linha de base configurada.</span><span class="sxs-lookup"><span data-stu-id="8f586-209">The execution log contains information about the results of the comparison of the generated file with the configured baseline.</span></span> <span data-ttu-id="8f586-210">O log indica que o arquivo gerado e a linha de base são iguais, mesmo que o formato executado contenha a associação para inserir uma data e um valor de tempo constantemente alterados no arquivo de saída.</span><span class="sxs-lookup"><span data-stu-id="8f586-210">The log indicates that the generated file and the baseline are equal, even though the executed format contains the binding to enter a constantly changing date and time value in the outbound file.</span></span>

> [!NOTE]
> <span data-ttu-id="8f586-211">Embora um arquivo de saída tenha sido gerado usando as configurações de linha base que forçam a substituição das associações de formato, você não receberá avisos sobre a substituição.</span><span class="sxs-lookup"><span data-stu-id="8f586-211">Although the outbound file has been generated by using baseline settings that force the replacement of the format's bindings, you don't receive any warnings about the replacement.</span></span>

## <a name="exchange-baseline-settings-between-environments"></a><span data-ttu-id="8f586-212">Configurações de linha base Cambial entre ambientes</span><span class="sxs-lookup"><span data-stu-id="8f586-212">Exchange baseline settings between environments</span></span>

### <a name="export-baseline-settings"></a><span data-ttu-id="8f586-213">Exporte configurações de linha de base</span><span class="sxs-lookup"><span data-stu-id="8f586-213">Export baseline settings</span></span>

<span data-ttu-id="8f586-214">Os novos recursos de ER permitem exportar configurações de linha de base para o formato selecionado de ER do ambiente atual e armazená-las como arquivos XML.</span><span class="sxs-lookup"><span data-stu-id="8f586-214">The new ER capabilities let you export baseline settings for the selected ER format from the current environment and store them as XML files.</span></span> 

<span data-ttu-id="8f586-215">Para exportar configurações de linha de base, na página **Linhas de base do formato de relatório eletrônico**, selecione **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="8f586-215">To export baseline settings, on the **Electronic reporting format baselines** page, select **Export**.</span></span>

### <a name="import-baseline-settings"></a><span data-ttu-id="8f586-216">Importar configurações de linha de base</span><span class="sxs-lookup"><span data-stu-id="8f586-216">Import baseline settings</span></span>

<span data-ttu-id="8f586-217">As configurações de linha base exportadas podem ser importadas em um ambiente diferente.</span><span class="sxs-lookup"><span data-stu-id="8f586-217">Exported baseline settings can be imported into a different environment.</span></span> <span data-ttu-id="8f586-218">O ambiente precisa primeiro ser importado com um formato de ER.</span><span class="sxs-lookup"><span data-stu-id="8f586-218">The environment must first be imported as an ER format.</span></span> <span data-ttu-id="8f586-219">Depois, você poderá importar as configurações de linha de base.</span><span class="sxs-lookup"><span data-stu-id="8f586-219">You can then import the baseline settings.</span></span>

<span data-ttu-id="8f586-220">Para importar configurações de linha base de um arquivo XML armazenado localmente, na página **Linhas de base de formato de relatório eletrônico**, selecione **Importar** e selecione **Procurar** para selecionar o arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="8f586-220">To import baseline settings from a locally stored XML file, on the **Electronic reporting format baselines** page, select **Import**, and then select **Browse** to select the XML file.</span></span>

<span data-ttu-id="8f586-221">![Caixa de diálogo Importar configurações de linha de base](media/GER-BaselineSample-ImportBaseline1.PNG "Captura de tela da caixa de diálogo Importar configurações de linha de base")</span><span class="sxs-lookup"><span data-stu-id="8f586-221">![Import baseline settings dialog box](media/GER-BaselineSample-ImportBaseline1.PNG "Screenshot of the Import baseline settings dialog box")</span></span>

<span data-ttu-id="8f586-222">Para importar configurações de linha base de um arquivo XML armazenado no Microsoft SharePoint Server, com base nas configurações atuais de gerenciamento de documentos e no tipo de documento selecionado, na página **Linhas de base do formato de relatório eletrônico**, selecione **Importar da origem**.</span><span class="sxs-lookup"><span data-stu-id="8f586-222">To import baseline settings from an XML file that is stored on the Microsoft SharePoint Server, based on the current Document management settings and the selected document type, on the **Electronic reporting format baselines** page, select **Import from source**.</span></span> <span data-ttu-id="8f586-223">Depois, selecione o tipo de documento e o arquivos XML.</span><span class="sxs-lookup"><span data-stu-id="8f586-223">Then select the document type and the XML file.</span></span> <span data-ttu-id="8f586-224">O tipo de documento necessário para acessar a pasta do SharePoint deve ser configurado com antecedência.</span><span class="sxs-lookup"><span data-stu-id="8f586-224">The required document type to access the SharePoint folder must be configured in advance.</span></span>

<span data-ttu-id="8f586-225">![Caixa de diálogo Importar da origem](media/GER-BaselineSample-ImportBaseline2.PNG "Captura de tela da caixa de diálogo Importar da origem")</span><span class="sxs-lookup"><span data-stu-id="8f586-225">![Import from source dialog box](media/GER-BaselineSample-ImportBaseline2.PNG "Screenshot of the Import from source dialog box")</span></span>

> [!NOTE]
> <span data-ttu-id="8f586-226">Você pode usar o gravador de tarefas para registrar as etapas para selecionar o tipo de documento necessário e o nome de arquivo na caixa de diálogo **Importar da origem**.</span><span class="sxs-lookup"><span data-stu-id="8f586-226">You can use Task recorder to record the steps for selecting the required document type and the file name in the **Import from source** dialog box.</span></span> <span data-ttu-id="8f586-227">Assim, você pode manter configurações necessárias de linha base no SharePoint Server e automaticamente importá-las, executando uma gravação de tarefas ao realizar testes automatizados usando a Regression Suite Automation Tool.</span><span class="sxs-lookup"><span data-stu-id="8f586-227">In this way, you can keep required baseline settings on SharePoint Server and then automatically import them by playing a task recording when you run automated tests by using the Regression Suite Automation Tool.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8f586-228">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="8f586-228">Additional resources</span></span>

- [<span data-ttu-id="8f586-229">Rastrear resultados dos relatórios gerados e compará-los com os valores da linha de base</span><span class="sxs-lookup"><span data-stu-id="8f586-229">Trace generated report results and compare them with baseline values</span></span>](er-trace-reports-compare-baseline.md)
- [<span data-ttu-id="8f586-230">Recursos do Gravador de tarefas</span><span class="sxs-lookup"><span data-stu-id="8f586-230">Task recorder resources</span></span>](../user-interface/task-recorder.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]