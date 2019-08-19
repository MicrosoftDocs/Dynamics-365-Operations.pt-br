---
title: Definições de linha no designer de relatório financeiro
description: Uma definição de linha é um componente de relatório ou bloco de construção que especifica o conteúdo de cada linha em um relatório financeiro. Uma definição de linha pode ser combinada com as definições de coluna, definições de árvore de relatórios e as definições de relatório para criar um grupo do bloco de construção que possa ser usado por várias empresas.
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 68873
ms.assetid: 2fd7b5da-700f-48cb-9003-90c0d82f818f
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5b0b7b715bc2b3b90bcd6620c3fe0ad751313c06
ms.sourcegitcommit: 9b4c3fff2f30006b7bb491ef6ffe89d41bcbfa11
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2019
ms.locfileid: "1863739"
---
# <a name="row-definitions-in-financial-report-designer"></a><span data-ttu-id="43c23-104">Definições de linha no designer de relatório financeiro</span><span class="sxs-lookup"><span data-stu-id="43c23-104">Row definitions in financial report designer</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="43c23-105">Uma definição de linha é um componente de relatório ou bloco de construção que especifica o conteúdo de cada linha em um relatório financeiro.</span><span class="sxs-lookup"><span data-stu-id="43c23-105">A row definition is a report component, or building block, that specifies the contents of each row on a financial report.</span></span> <span data-ttu-id="43c23-106">Uma definição de linha pode ser combinada com as definições de coluna, definições de árvore de relatórios e as definições de relatório para criar um grupo do bloco de construção que possa ser usado por várias empresas.</span><span class="sxs-lookup"><span data-stu-id="43c23-106">A row definition can be combined with column definitions, reporting tree definitions, and report definitions to create a building block group that can be used by multiple companies.</span></span>

## <a name="create-a-row-definition"></a><span data-ttu-id="43c23-107">Criar uma definição de linha</span><span class="sxs-lookup"><span data-stu-id="43c23-107">Create a row definition</span></span>

1. <span data-ttu-id="43c23-108">No Designer de Relatórios, no painel de navegação, clique em **Definições de linha**.</span><span class="sxs-lookup"><span data-stu-id="43c23-108">In Report Designer, in the navigation pane, click **Row Definitions**.</span></span>
2. <span data-ttu-id="43c23-109">No menu **Arquivo**, clique em **Novo** e clique em **Definição de Linha**.</span><span class="sxs-lookup"><span data-stu-id="43c23-109">On the **File** menu, click **New**, and then click **Row Definition**.</span></span> <span data-ttu-id="43c23-110">Para obter mais informações sobre o conteúdo de cada célula, consulte [Modifique células de definição de linha](modify-row-definition-cells-financial-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="43c23-110">For more information about the content of each cell, see [Modify row definition cells](modify-row-definition-cells-financial-reporting.md).</span></span>

## <a name="open-a-row-definition"></a><span data-ttu-id="43c23-111">Abrir uma definição de linha</span><span class="sxs-lookup"><span data-stu-id="43c23-111">Open a row definition</span></span>
1. <span data-ttu-id="43c23-112">No Designer de Relatórios, no painel de navegação, clique em **Definições de linha**.</span><span class="sxs-lookup"><span data-stu-id="43c23-112">In Report Designer, in the navigation pane, click **Row Definitions**.</span></span>
2. <span data-ttu-id="43c23-113">Clique duas vezes no nome da definição de linha a ser aberta.</span><span class="sxs-lookup"><span data-stu-id="43c23-113">Double-click the name of the row definition to open.</span></span>
3. <span data-ttu-id="43c23-114">Para exibir todos os blocos de construção que estejam associados à definição de linha, clique com o botão direito do mouse na definição de linha e selecione **Associações**.</span><span class="sxs-lookup"><span data-stu-id="43c23-114">To view any building blocks that are associated with the row definition, right-click the row definition, and then select **Associations**.</span></span>

## <a name="contents-of-a-row-definition"></a><span data-ttu-id="43c23-115"> Conteúdo de uma definição de linha</span><span class="sxs-lookup"><span data-stu-id="43c23-115">Contents of a row definition</span></span>
<span data-ttu-id="43c23-116">Uma definição de linha pode conter até 20.000 linhas de dimensão financeira e pode incluir as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="43c23-116">A row definition can contain up to 20,000 financial dimension rows and can include the following information:</span></span>

- <span data-ttu-id="43c23-117">O texto descritivo que confere significado ao relatório ao criar títulos, linhas e espaços na seção, como **Pagamento à vista** ou **Receita total**</span><span class="sxs-lookup"><span data-stu-id="43c23-117">Descriptive text that adds meaning to the report by creating section headings, lines, and spaces, such as **Cash** or **Total Revenue**</span></span>
- <span data-ttu-id="43c23-118">Links para dados financeiros, que podem incluir valores de dimensão no Microsoft Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="43c23-118">Links to financial data, which can include dimension values in the Microsoft Dynamics 365 for Finance and Operations</span></span>

    > [!NOTE]
    > <span data-ttu-id="43c23-119">Você pode configurar uma definição de linha para receber dados do sistema de dimensão financeira sempre que o relatório é gerado.</span><span class="sxs-lookup"><span data-stu-id="43c23-119">You can set up a row definition to pull data from the financial dimensions system every time that the report is generated.</span></span>

- <span data-ttu-id="43c23-120">Os totais de linhas e as fórmulas que se baseiam nos dados financeiros vinculados</span><span class="sxs-lookup"><span data-stu-id="43c23-120">Row totals and formulas that are based on the linked financial data</span></span>

<span data-ttu-id="43c23-121">Geralmente, cada linha em uma definição de linha contém um dos seguintes tipos de informações:</span><span class="sxs-lookup"><span data-stu-id="43c23-121">Usually, each row in a row definition contains one of the following types of information:</span></span>

- <span data-ttu-id="43c23-122">Referências ao sistema de dimensões financeiras</span><span class="sxs-lookup"><span data-stu-id="43c23-122">References to the financial dimensions system</span></span>
- <span data-ttu-id="43c23-123">Totais ou cálculos que são baseados nos dados</span><span class="sxs-lookup"><span data-stu-id="43c23-123">Totals or calculations that are based on the data</span></span>
- <span data-ttu-id="43c23-124">Formatação</span><span class="sxs-lookup"><span data-stu-id="43c23-124">Formatting</span></span>

<span data-ttu-id="43c23-125">Há dois métodos para a inserção de informações em uma definição de linha:</span><span class="sxs-lookup"><span data-stu-id="43c23-125">There are two methods for entering information in a row definition:</span></span>

- <span data-ttu-id="43c23-126">Insira informações de linha manualmente em uma nova definição de linha.</span><span class="sxs-lookup"><span data-stu-id="43c23-126">Manually enter row information in a new row definition.</span></span> <span data-ttu-id="43c23-127">Para obter mais informações, consulte [Modifique células de definição de linha](modify-row-definition-cells-financial-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="43c23-127">For more information, see [Modify row definition cells](modify-row-definition-cells-financial-reporting.md).</span></span>
- <span data-ttu-id="43c23-128">Use o designer de relatórios para extrair informações de linha diretamente das dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="43c23-128">Use report designer to pull row information directly from the financial dimensions.</span></span> <span data-ttu-id="43c23-129">Para obter mais informações, consulte a seção "Fórmulas relacionadas/linhas/unidades" em [Modificar células de definição de linha](modify-row-definition-cells-financial-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="43c23-129">For more information, see the "Related formulas/rows/units" section in [Modify row definition cells](modify-row-definition-cells-financial-reporting.md).</span></span>

## <a name="add-dimensions-in-a-row-definition"></a><span data-ttu-id="43c23-130"> Adicionar dimensões em uma definição de linha</span><span class="sxs-lookup"><span data-stu-id="43c23-130">Add dimensions in a row definition</span></span>
<span data-ttu-id="43c23-131">Uma dimensão é uma interseção de dados e valores.</span><span class="sxs-lookup"><span data-stu-id="43c23-131">A dimension is an intersection of data and values.</span></span> <span data-ttu-id="43c23-132">Você pode agrupar dados e valores no designer de relatórios.</span><span class="sxs-lookup"><span data-stu-id="43c23-132">You can group data and values in report designer.</span></span> <span data-ttu-id="43c23-133">Em seguida, você pode classificar e analisar transações mais detalhadamente.</span><span class="sxs-lookup"><span data-stu-id="43c23-133">You can then classify and analyze transactions in more detail.</span></span> <span data-ttu-id="43c23-134">É possível usar a caixa de diálogo **Inserir Linhas de Dimensões** para adicionar várias linhas ao mesmo tempo em uma definição de linha.</span><span class="sxs-lookup"><span data-stu-id="43c23-134">You can use the **Insert Rows from Dimensions** dialog box to add multiple rows to a row definition at the same time.</span></span> <span data-ttu-id="43c23-135">A caixa de diálogo exibe uma coluna para cada dimensão.</span><span class="sxs-lookup"><span data-stu-id="43c23-135">The dialog box displays one column for each dimension.</span></span> <span data-ttu-id="43c23-136">A tabela a seguir descreve as informações que você pode especificar para cada dimensão.</span><span class="sxs-lookup"><span data-stu-id="43c23-136">The following table describes the information that you can specify for each dimension.</span></span>

| <span data-ttu-id="43c23-137">Opção</span><span class="sxs-lookup"><span data-stu-id="43c23-137">Option</span></span>                | <span data-ttu-id="43c23-138">Descrição</span><span class="sxs-lookup"><span data-stu-id="43c23-138">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="43c23-139">Dimensão</span><span class="sxs-lookup"><span data-stu-id="43c23-139">Dimension</span></span>             | <span data-ttu-id="43c23-140">O padrão que identifica a dimensão a ser adicionada à definição de linha.</span><span class="sxs-lookup"><span data-stu-id="43c23-140">The pattern that identifies the dimension to add to the row definition.</span></span> <span data-ttu-id="43c23-141">Este padrão contém um E comercial (&) ou sinal numérico (\#) para cada posição nas dimensões.</span><span class="sxs-lookup"><span data-stu-id="43c23-141">This pattern contains one ampersand (&) or number sign (\#) for each position in the dimensions.</span></span> <span data-ttu-id="43c23-142">Em geral, use E comerciais para a dimensão Conta principal e sinais numéricos para outras dimensões.</span><span class="sxs-lookup"><span data-stu-id="43c23-142">Generally, use all ampersands for the Main Account dimension and all number signs for other dimensions.</span></span> |
| <span data-ttu-id="43c23-143">Início do Intervalo de Dimensões</span><span class="sxs-lookup"><span data-stu-id="43c23-143">Dimension Range Start</span></span> | <span data-ttu-id="43c23-144">O primeiro valor dessa dimensão para adicionar à definição de linha.</span><span class="sxs-lookup"><span data-stu-id="43c23-144">The first value for this dimension to add to the row definition.</span></span> |
| <span data-ttu-id="43c23-145">Fim do Intervalo de Dimensões</span><span class="sxs-lookup"><span data-stu-id="43c23-145">Dimension Range End</span></span>   | <span data-ttu-id="43c23-146">O último valor desta dimensão a ser adicionado à definição de linha.</span><span class="sxs-lookup"><span data-stu-id="43c23-146">The last value for this dimension to add to the row definition.</span></span> |

<span data-ttu-id="43c23-147">Para adicionar dimensões a uma definição de linha, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="43c23-147">To add dimensions to a row definition, follow these steps.</span></span>

1. <span data-ttu-id="43c23-148">No Designer de Relatórios, clique em **Definições de Linha** e abra a definição de linha para modificá-la.</span><span class="sxs-lookup"><span data-stu-id="43c23-148">In Report Designer, click **Row Definitions**, and then open the row definition to modify.</span></span>
2. <span data-ttu-id="43c23-149">No menu **Editar**, clique em **Inserir Linhas de Dimensões**.</span><span class="sxs-lookup"><span data-stu-id="43c23-149">On the **Edit** menu, click **Insert Rows from Dimensions**.</span></span>
3. <span data-ttu-id="43c23-150">Na caixa de diálogo **Inserir Linhas de Dimensões**, na linha **Dimensões**, selecione a célula da dimensão a ser transferida para a definição de linha e clique em **Todos &&&**.</span><span class="sxs-lookup"><span data-stu-id="43c23-150">In the **Insert Rows from Dimensions** dialog box, in the **Dimensions** row, select the cell for the dimension to transfer to the row definition, and then click **All &&&**.</span></span>
4. <span data-ttu-id="43c23-151">Para limitar a definição de linha a um intervalo específico de valores de dimensões, digite o valor de dimensão inicial na célula **Início do Intervalo de Dimensões**, e digite o valor de dimensão final na célula **Final do Intervalo de Dimensões**.</span><span class="sxs-lookup"><span data-stu-id="43c23-151">To limit the row definition to a specific range of dimension values, enter the starting dimension value in the **Dimension Range Start** cell, and then enter the ending dimension value in the **Dimension Range End** cell.</span></span> <span data-ttu-id="43c23-152">Para incluir todos os valores da dimensão selecionada, deixe essas células vazias.</span><span class="sxs-lookup"><span data-stu-id="43c23-152">To include all values for the selected dimension, leave these cells empty.</span></span>

    > [!NOTE]
    > <span data-ttu-id="43c23-153">Os caracteres curinga (\* ou ?) nos intervalos de dimensão não podem retornar todos os resultados que você deseja, dependendo de como o banco de dados de ERP agrupa os dados.</span><span class="sxs-lookup"><span data-stu-id="43c23-153">Wildcard characters (\* or ?) in dimension ranges might not return all the results that you want, depending on how the ERP database collates data.</span></span>

5. <span data-ttu-id="43c23-154">No campo **Código de linha inicial** para especificar o código de linha para o primeiro valor de dimensão a ser adicionado à definição de linha.</span><span class="sxs-lookup"><span data-stu-id="43c23-154">In the **Starting row code** field, specify the row code for the first dimension value to add to the row definition.</span></span>
6. <span data-ttu-id="43c23-155">No campo **Incrementar cada linha em** para especificar o intervalo entre os códigos de linha consecutivos.</span><span class="sxs-lookup"><span data-stu-id="43c23-155">In the **Increment each row by** field, specify the gap between consecutive row codes.</span></span> <span data-ttu-id="43c23-156">Por exemplo, se o primeiro código de linha é 100 e o valor de incremento é 30, as primeiras novas linhas têm os códigos 100, 130, 160, 190 e 220.</span><span class="sxs-lookup"><span data-stu-id="43c23-156">For example, if the first row code is 100, and the increment value is 30, the first new rows have the codes 100, 130, 160, 190, and 220.</span></span> <span data-ttu-id="43c23-157">Use um valor de incremento que forneça espaço suficiente para inserir novas linhas de formato e fórmula.</span><span class="sxs-lookup"><span data-stu-id="43c23-157">Use an increment value that provides enough space to insert new format and formula rows.</span></span>
7. <span data-ttu-id="43c23-158">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="43c23-158">Click **OK**.</span></span> <span data-ttu-id="43c23-159">Para cada uma dos valores de dimensão selecionados, uma linha é adicionada a definição da linha.</span><span class="sxs-lookup"><span data-stu-id="43c23-159">For each of the selected dimension values, one line is added to the row definition.</span></span>

## <a name="adjust-rounding-in-a-row-definition"></a><span data-ttu-id="43c23-160"> Ajustar arredondamento em uma definição de linha</span><span class="sxs-lookup"><span data-stu-id="43c23-160">Adjust rounding in a row definition</span></span>
<span data-ttu-id="43c23-161">Quando você tem um balanço em que os valores são arredondados, talvez os totais estejam sem saldo.</span><span class="sxs-lookup"><span data-stu-id="43c23-161">If you have a balance sheet where the amounts are rounded, the totals might not balance.</span></span> <span data-ttu-id="43c23-162">Esse problema pode ocorrer se, por exemplo, você usar a opção de arredondamento em um relatório de balancete e a definição de relatório também especificar o arredondamento.</span><span class="sxs-lookup"><span data-stu-id="43c23-162">This issue can occur if, for example, you use the rounding option on a balance sheet report and the report definition also specifies rounding.</span></span> <span data-ttu-id="43c23-163">Você pode usar a opção de **arredondamento de ajuste** na definição de linha para equilibrar os valores no balanço patrimonial.</span><span class="sxs-lookup"><span data-stu-id="43c23-163">You can use the **Rounding adjustment** option in the row definition to balance the amounts in the balance sheets.</span></span> <span data-ttu-id="43c23-164">Você pode desativar o arredondamento ou modificá-lo na guia **Configurações** da definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="43c23-164">You can turn rounding off or modify it on the **Settings** tab of the report definition.</span></span> <span data-ttu-id="43c23-165">A tabela a seguir mostra como os valores são arredondados.</span><span class="sxs-lookup"><span data-stu-id="43c23-165">The following table shows how amounts are rounded.</span></span> <span data-ttu-id="43c23-166">Nesta tabela, os totais das linhas 100 e 200 diferem quando o arredondamento está ativado.</span><span class="sxs-lookup"><span data-stu-id="43c23-166">In this table, the totals of rows 100 and 200 differ when rounding is turned on.</span></span>

| <span data-ttu-id="43c23-167">Código da linha</span><span class="sxs-lookup"><span data-stu-id="43c23-167">Row code</span></span> | <span data-ttu-id="43c23-168">Valores sem arredondamento</span><span class="sxs-lookup"><span data-stu-id="43c23-168">Amounts without rounding</span></span> | <span data-ttu-id="43c23-169">Valor com arredondamento para milhares</span><span class="sxs-lookup"><span data-stu-id="43c23-169">Amount with rounding to whole thousands</span></span> |
|----------|--------------------------|-----------------------------------------|
| <span data-ttu-id="43c23-170">100</span><span class="sxs-lookup"><span data-stu-id="43c23-170">100</span></span>      | <span data-ttu-id="43c23-171">3,600</span><span class="sxs-lookup"><span data-stu-id="43c23-171">3,600</span></span>                    | <span data-ttu-id="43c23-172">4</span><span class="sxs-lookup"><span data-stu-id="43c23-172">4</span></span>                                       |
| <span data-ttu-id="43c23-173">200</span><span class="sxs-lookup"><span data-stu-id="43c23-173">200</span></span>      | <span data-ttu-id="43c23-174">3,700</span><span class="sxs-lookup"><span data-stu-id="43c23-174">3,700</span></span>                    | <span data-ttu-id="43c23-175">4</span><span class="sxs-lookup"><span data-stu-id="43c23-175">4</span></span>                                       |
| <span data-ttu-id="43c23-176">Total</span><span class="sxs-lookup"><span data-stu-id="43c23-176">Total</span></span>    | <span data-ttu-id="43c23-177">7,300</span><span class="sxs-lookup"><span data-stu-id="43c23-177">7,300</span></span>                    | <span data-ttu-id="43c23-178">8</span><span class="sxs-lookup"><span data-stu-id="43c23-178">8</span></span>                                       |

<span data-ttu-id="43c23-179">Para ajustar o arredondamento em um balanço, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="43c23-179">To adjust rounding in a balance sheet, follow these steps.</span></span>

1. <span data-ttu-id="43c23-180">No Designer de Relatórios, clique em **Definições de Linha** e abra a definição de linha para modificá-la.</span><span class="sxs-lookup"><span data-stu-id="43c23-180">In Report Designer, click **Row Definitions**, and then open the row definition to modify.</span></span>
2. <span data-ttu-id="43c23-181">No menu **Editar**, clique em **Ajuste de arredondamento**.</span><span class="sxs-lookup"><span data-stu-id="43c23-181">On the **Edit** menu, click **Rounding Adjustment**.</span></span>
3. <span data-ttu-id="43c23-182">Na caixa de diálogo **Ajustes de Arredondamento**, insira os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="43c23-182">In the **Rounding Adjustments** dialog box, enter the following values:</span></span>

    - <span data-ttu-id="43c23-183">**Linha de ajuste de arredondamento** – O código de linha da linha que deverá ser ajustada para equilibrar o balanço.</span><span class="sxs-lookup"><span data-stu-id="43c23-183">**Rounding adjustment row** – The row code for the row that should be adjusted to balance the balance sheet.</span></span>
    - <span data-ttu-id="43c23-184">**Linha de total de ativos** – O código de linha da linha no balanço que contém os ativos totais.</span><span class="sxs-lookup"><span data-stu-id="43c23-184">**Total assets row** – The row code for the row in the balance sheet that contains the total assets.</span></span>
    - <span data-ttu-id="43c23-185">**Linha de total de passivos e capital próprio** – O código de linha da linha no balanço que contém o total de passivos e capital próprio.</span><span class="sxs-lookup"><span data-stu-id="43c23-185">**Total liabilities and equity row** – The row code for the row in the balance sheet that contains the total liabilities and equity.</span></span>
    - <span data-ttu-id="43c23-186">**Limite de valor de ajuste** – Um limite positivo que especifica o limite em ajustes automáticos.</span><span class="sxs-lookup"><span data-stu-id="43c23-186">**Adjustment amount limit** – A positive whole number that specifies the limit on automatic adjustments.</span></span> <span data-ttu-id="43c23-187">Esse valor é comparado com um valor absoluto da diferença de arredondamento.</span><span class="sxs-lookup"><span data-stu-id="43c23-187">This amount is compared with the absolute value of the actual rounding difference.</span></span>

    > [!NOTE]
    > <span data-ttu-id="43c23-188">Esses códigos de linha devem estar vinculados aos seus dados financeiros.</span><span class="sxs-lookup"><span data-stu-id="43c23-188">These row codes must be linked to your financial data.</span></span> <span data-ttu-id="43c23-189">Em outras palavras a linha deve ter um valor de dimensão na célula de **Vincular a dimensões financeiras**.</span><span class="sxs-lookup"><span data-stu-id="43c23-189">In other words, the row must have a dimension value in its **Link to Financial Dimensions** cell.</span></span> <span data-ttu-id="43c23-190">Não **referencie** uma linha de descrição (**DESC**), calculada (**CALC**) ou totalizada (**TOT**).</span><span class="sxs-lookup"><span data-stu-id="43c23-190">Do **not** reference a description (**DESC**), calculated (**CALC**), or totaled (**TOT**) row.</span></span>

<span data-ttu-id="43c23-191">Os valores no balanço serão equilibrados agora uniformemente quando o arredondamento estiver ativado.</span><span class="sxs-lookup"><span data-stu-id="43c23-191">The amounts in your balance sheet will now balance evenly when rounding is turned on.</span></span>

> [!NOTE]
> <span data-ttu-id="43c23-192">O limite de ajuste é aplicado com base na opção da **Precisão do arredondamento** que é especificado para a definição do relatório.</span><span class="sxs-lookup"><span data-stu-id="43c23-192">The adjustment limit is applied based on the **Rounding precision** option that is specified for the report definition.</span></span> <span data-ttu-id="43c23-193">Por exemplo, se você selecionar para arredondar o relatório em milhares e inserir **2** no campo **Limite de valor de ajuste**, será exibida uma mensagem de aviso quando o valor identificado no campo **Linha de ajuste de arredondamento** aumentar ou diminuir em mais de US$ 2.000.</span><span class="sxs-lookup"><span data-stu-id="43c23-193">For example, if you round your report to thousands and enter **2** in the **Adjustment amount limit** field, you receive a warning message when the value in the **Rounding adjustment row** field increases or decreases by more than 2,000.</span></span>

## <a name="format-row-and-column-text"></a><span data-ttu-id="43c23-194">Linha de formato e texto da coluna</span><span class="sxs-lookup"><span data-stu-id="43c23-194">Format row and column text</span></span>
<span data-ttu-id="43c23-195">Você pode personalizar a aparência dos relatórios alterando fontes e formatação de texto.</span><span class="sxs-lookup"><span data-stu-id="43c23-195">You can customize the appearance of your reports by changing fonts and formatting text.</span></span> <span data-ttu-id="43c23-196">As seções a seguir explicam como formatar a aparência de linhas e colunas em relatórios.</span><span class="sxs-lookup"><span data-stu-id="43c23-196">The following sections explain how to format the appearance of rows and columns on reports.</span></span>

### <a name="manage-font-styles"></a><span data-ttu-id="43c23-197">Gerenciar estilos de fontes</span><span class="sxs-lookup"><span data-stu-id="43c23-197">Manage font styles</span></span>

<span data-ttu-id="43c23-198">Você pode criar e modificar estilos de fonte para o relatório.</span><span class="sxs-lookup"><span data-stu-id="43c23-198">You can create and modify font styles for your report.</span></span> <span data-ttu-id="43c23-199">Em seguida, você pode aplicar esses estilos para o documento ou a uma linha específica ou uma coluna em um relatório.</span><span class="sxs-lookup"><span data-stu-id="43c23-199">You can then apply those styles to the document, or to a specific row or column on a report.</span></span>

<table>
<tbody>
<tr>
<td><span data-ttu-id="43c23-200"><strong>Criar um estilo de fonte</strong></span><span class="sxs-lookup"><span data-stu-id="43c23-200"><strong>Create a font style</strong></span></span></td>
<td>
<ol>
<li><span data-ttu-id="43c23-201">No Designer de Relatórios, no menu <strong>Formato </strong>, clique em <strong>Estilos e Formatação</strong>.</span><span class="sxs-lookup"><span data-stu-id="43c23-201">In Report Designer, on the <strong>Format</strong> menu, click <strong>Styles and Formatting</strong>.</span></span></li>
<li><span data-ttu-id="43c23-202">Na caixa de diálogo <strong>Estilos e formatação</strong>, clique em <strong>Novo</strong> e insira um nome exclusivo para o novo estilo.</span><span class="sxs-lookup"><span data-stu-id="43c23-202">In the <strong>Styles and Formatting</strong> dialog box, click <strong>New</strong>, and then enter a unique name for the new style.</span></span></li>
<li><span data-ttu-id="43c23-203">Faça as seleções de fonte e, em seguida, clique em <strong>OK</strong>.</span><span class="sxs-lookup"><span data-stu-id="43c23-203">Make your font selections, and then click <strong>OK</strong>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="43c23-204"><strong>Modificar um estilo de fonte</strong></span><span class="sxs-lookup"><span data-stu-id="43c23-204"><strong>Modify a font style</strong></span></span></td>
<td>
<ol>
<li><span data-ttu-id="43c23-205">No Designer de Relatórios, no menu <strong>Formato </strong>, clique em <strong>Estilos e Formatação</strong>.</span><span class="sxs-lookup"><span data-stu-id="43c23-205">In Report Designer, on the <strong>Format</strong> menu, click <strong>Styles and Formatting</strong>.</span></span></li>
<li><span data-ttu-id="43c23-206">Na caixa de diálogo <strong>Estilos e formatação</strong>, selecione um estilo para modificar e clique em <strong>Modificar</strong>.</span><span class="sxs-lookup"><span data-stu-id="43c23-206">In the <strong>Styles and Formatting</strong> dialog box, select a style to modify, and then click <strong>Modify</strong>.</span></span></li>
<li><span data-ttu-id="43c23-207">Faça as seleções de fonte e, em seguida, clique em <strong>OK</strong>.</span><span class="sxs-lookup"><span data-stu-id="43c23-207">Make your font selections, and then click <strong>OK</strong>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="43c23-208"><strong>Aplicar um estilo de fonte</strong></span><span class="sxs-lookup"><span data-stu-id="43c23-208"><strong>Apply a font style</strong></span></span></td>
<td>
<ol>
<li><span data-ttu-id="43c23-209">Em designer de relatório, uma definição ou definição de coluna, ou em cabeçalhos e rodapés, selecione uma ou mais células.</span><span class="sxs-lookup"><span data-stu-id="43c23-209">In Report Designer, in a definition or column definition, or in headers and footers, select one or more cells.</span></span></li>
<li><span data-ttu-id="43c23-210">Na lista <strong>Estilo</strong> na barra de ferramentas, selecione um estilo de fonte.</span><span class="sxs-lookup"><span data-stu-id="43c23-210">In the <strong>Style</strong> list on the toolbar, select a font style.</span></span></li>
</ol>
</td>
</tr>
</tbody>
</table>

### <a name="format-row-text"></a><span data-ttu-id="43c23-211">Formatar texto de linha</span><span class="sxs-lookup"><span data-stu-id="43c23-211">Format row text</span></span>

<span data-ttu-id="43c23-212">A formatação que é especificada na definição de coluna substitui a formatação que é especificada na definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="43c23-212">The formatting that is specified in the row definition overrides any formatting that is specified in the column definition and the report definition.</span></span> <span data-ttu-id="43c23-213">Você pode modificar o formato do texto usando os controles na barra de ferramentas Formatação.</span><span class="sxs-lookup"><span data-stu-id="43c23-213">You can modify the text format by using the controls on the formatting toolbar.</span></span> <span data-ttu-id="43c23-214">Esses controles são controles padrão do Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="43c23-214">These controls are standard Microsoft Windows controls.</span></span>

1. <span data-ttu-id="43c23-215">No Report Designer, abra a definição de linha a ser modificada.</span><span class="sxs-lookup"><span data-stu-id="43c23-215">In Report Designer, open the row definition to modify.</span></span>
2. <span data-ttu-id="43c23-216">Selecione as células para formatar.</span><span class="sxs-lookup"><span data-stu-id="43c23-216">Select the cells to format.</span></span> <span data-ttu-id="43c23-217">Para selecionar várias células, mantenha pressionada a tecla CTRL enquanto seleciona a célula.</span><span class="sxs-lookup"><span data-stu-id="43c23-217">To select multiple cells, hold down the Ctrl key while you select the cell.</span></span>
3. <span data-ttu-id="43c23-218">Clique no botão na barra de ferramentas do formato a ser aplicado.</span><span class="sxs-lookup"><span data-stu-id="43c23-218">Click the toolbar button of the format to apply.</span></span> <span data-ttu-id="43c23-219">Por exemplo, para recuar uma linha, selecione a linha e clique em **Aumentar recuo** ![Aumentar recuo](media/indent.gif "Aumentar recuo") na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="43c23-219">For example, to indent a row, select the row, and then click **Increase Indent** ![Increase Indent](media/indent.gif "Increase Indent") on the toolbar.</span></span>

### <a name="adjust-columns-while-you-design-reports"></a><span data-ttu-id="43c23-220">Ajuste colunas ao criar relatórios</span><span class="sxs-lookup"><span data-stu-id="43c23-220">Adjust columns while you design reports</span></span>

<span data-ttu-id="43c23-221">Para facilitar a exibição das colunas em que estiver trabalhando na definição de linha, você poderá ajustar a largura de uma coluna, e ocultar (minimizar) ou mostrar colunas no painel de exibição.</span><span class="sxs-lookup"><span data-stu-id="43c23-221">To make it easier to view the columns that you're working on in the row definition, you can adjust the width of a column, and can also hide (minimize) or show columns in the view pane.</span></span> <span data-ttu-id="43c23-222">As modificações que você fizer afetarão somente a tela aparente das colunas.</span><span class="sxs-lookup"><span data-stu-id="43c23-222">The modifications that you make affect only the on-screen appearance of the columns.</span></span> <span data-ttu-id="43c23-223">Elas não afetam a coluna de formatação nos relatórios.</span><span class="sxs-lookup"><span data-stu-id="43c23-223">They don't affect the column formatting on reports.</span></span>

### <a name="change-the-width-of-a-column-in-the-view-pane"></a><span data-ttu-id="43c23-224">Alterar a largura de uma coluna no painel de exibição</span><span class="sxs-lookup"><span data-stu-id="43c23-224">Change the width of a column in the view pane</span></span>

1. <span data-ttu-id="43c23-225">No Designer de Relatórios, abra a definição de linha a ser modificada.</span><span class="sxs-lookup"><span data-stu-id="43c23-225">In Report Designer, open the row definition to modify.</span></span>
2. <span data-ttu-id="43c23-226">No menu **Formato**, selecione **Largura da Coluna**.</span><span class="sxs-lookup"><span data-stu-id="43c23-226">On the **Format** menu, select **Column Width**.</span></span>
3. <span data-ttu-id="43c23-227">Na caixa de diálogo **Largura da coluna**, insira um valor, e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="43c23-227">In the **Column Width** dialog box, enter a value, and then click **OK**.</span></span> <span data-ttu-id="43c23-228">De forma alternativa, você também pode arrastar o limite direito de uma célula de título da coluna para alterar a largura da coluna.</span><span class="sxs-lookup"><span data-stu-id="43c23-228">Alternatively, you can drag the right boundary of a column heading cell to change the width of the column.</span></span>

### <a name="hide-columns-in-the-view-pane"></a><span data-ttu-id="43c23-229">Ocultar colunas no painel de exibição</span><span class="sxs-lookup"><span data-stu-id="43c23-229">Hide columns in the view pane</span></span>

1. <span data-ttu-id="43c23-230">No Designer de Relatórios, abra a definição de linha a ser modificada.</span><span class="sxs-lookup"><span data-stu-id="43c23-230">In Report Designer, open the row definition to modify.</span></span>
2. <span data-ttu-id="43c23-231">Selecione uma ou mais colunas para minimizar.</span><span class="sxs-lookup"><span data-stu-id="43c23-231">Select the column or columns to minimize.</span></span>
3. <span data-ttu-id="43c23-232">Clique no botão direito do mouse e clique em **Ocultar**.</span><span class="sxs-lookup"><span data-stu-id="43c23-232">Right-click, and then click **Hide**.</span></span>

### <a name="show-all-hidden-columns-in-the-view-pane"></a><span data-ttu-id="43c23-233">Mostrar todas as colunas ocultas no painel de exibição</span><span class="sxs-lookup"><span data-stu-id="43c23-233">Show all hidden columns in the view pane</span></span>

1. <span data-ttu-id="43c23-234">No Designer de Relatórios, abra a definição de linha a ser modificada.</span><span class="sxs-lookup"><span data-stu-id="43c23-234">In Report Designer, open the row definition to modify.</span></span>
2. <span data-ttu-id="43c23-235">Clique com o botão direito do mouse na coluna minimizada a ser exibida. Clique em **Reexibir**.</span><span class="sxs-lookup"><span data-stu-id="43c23-235">Right-click the minimized column to display, and then click **Unhide**.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="43c23-236">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="43c23-236">Additional resources</span></span>

[<span data-ttu-id="43c23-237">Relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="43c23-237">Financial reporting</span></span>](financial-reporting-intro.md)
