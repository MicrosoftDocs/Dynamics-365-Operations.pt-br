---
title: Editor de fórmula avançado do Relatório eletrônico
description: Este tópico descreve como o editor de fórmula avançado pode ser usado para configurar expressões em componentes de formato e mapeamento de modelo do ER (Relatório eletrônico).
author: NickSelin
manager: AnnBe
ms.date: 04/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: d9911c858d6832aa70378d37e0fd5cf7d7831b1b
ms.sourcegitcommit: dce8c5d3b2fc4a752d676cf9ba91e0dea2fa80d8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/10/2020
ms.locfileid: "3257052"
---
# <a name="electronic-reporting-advanced-formula-editor"></a><span data-ttu-id="04e97-103">Editor de fórmula avançado do Relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="04e97-103">Electronic reporting advanced formula editor</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="04e97-104">Além do [editor de fórmula](general-electronic-reporting-formula-designer.md) do [Relatório eletrônico](general-electronic-reporting.md), você pode usar o editor de fórmula avançado do Relatório eletrônico para aprimorar a experiência de configuração das expressões de ER (Relatório eletrônico).</span><span class="sxs-lookup"><span data-stu-id="04e97-104">In addition to the [Electronic reporting](general-electronic-reporting.md) [formula editor](general-electronic-reporting-formula-designer.md), you can use the advanced Electronic reporting formula editor to improve the experience of configuring Electronic reporting (ER) expressions.</span></span> <span data-ttu-id="04e97-105">O editor avançado é baseado em navegador e conta com a tecnologia do [Monaco Editor](https://microsoft.github.io/monaco-editor).</span><span class="sxs-lookup"><span data-stu-id="04e97-105">The advanced editor is browser-based and powered by the [Monaco editor](https://microsoft.github.io/monaco-editor).</span></span> <span data-ttu-id="04e97-106">Os recursos do editor avançado usados com mais frequência são descritos neste tópico:</span><span class="sxs-lookup"><span data-stu-id="04e97-106">The most commonly used advanced editor features are described in this topic:</span></span>

- [<span data-ttu-id="04e97-107">Autoformatação de código</span><span class="sxs-lookup"><span data-stu-id="04e97-107">Code autoformatting</span></span>](#Autoformatting)
- [<span data-ttu-id="04e97-108">IntelliSense</span><span class="sxs-lookup"><span data-stu-id="04e97-108">IntelliSense</span></span>](#IntelliSense)
- [<span data-ttu-id="04e97-109">Preenchimento de código</span><span class="sxs-lookup"><span data-stu-id="04e97-109">Code completion</span></span>](#CodeCompletion)
- [<span data-ttu-id="04e97-110">Navegação de código</span><span class="sxs-lookup"><span data-stu-id="04e97-110">Code navigation</span></span>](#CodeNavigation)
- [<span data-ttu-id="04e97-111">Estruturação de código</span><span class="sxs-lookup"><span data-stu-id="04e97-111">Code structuring</span></span>](#CodeStructuring)
- [<span data-ttu-id="04e97-112">Localizar e substituir</span><span class="sxs-lookup"><span data-stu-id="04e97-112">Find and replace</span></span>](#FindAndReplace)
- [<span data-ttu-id="04e97-113">Colagem de dados</span><span class="sxs-lookup"><span data-stu-id="04e97-113">Data pasting</span></span>](#DataPasting)
- [<span data-ttu-id="04e97-114">Colorização da sintaxe</span><span class="sxs-lookup"><span data-stu-id="04e97-114">Syntax colorization</span></span>](#SyntaxColorization)

## <a name=""></a><span data-ttu-id="04e97-115"><a name="ActivateAdvEditor">Ativar o editor de fórmula avançado</a></span><span class="sxs-lookup"><span data-stu-id="04e97-115"><a name="ActivateAdvEditor">Activate the advanced formula editor</a></span></span>

<span data-ttu-id="04e97-116">Conclua as etapas a seguir para começar a usar o editor de fórmula avançado em sua instância do Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="04e97-116">Complete the following steps to start using the advanced formula editor in your instance of Microsoft Dynamics 365 Finance.</span></span>

1.  <span data-ttu-id="04e97-117">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="04e97-117">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2.  <span data-ttu-id="04e97-118">Na página **Configurações** , no Painel Ação, na guia **Configurações** , no grupo **Configurações avançadas** , selecione **Parâmetros de usuário**.</span><span class="sxs-lookup"><span data-stu-id="04e97-118">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3.  <span data-ttu-id="04e97-119">Na caixa de diálogo **Parâmetro de usuário** , na seção **Rastreamento de execução** , defina o parâmetro **Habilitar editor de fórmula avançado** para **Sim**.</span><span class="sxs-lookup"><span data-stu-id="04e97-119">In the **User parameters** dialog box, in the **Execution tracing** section, set the **Enable advanced formula editor** parameter to **Yes**.</span></span>

<span data-ttu-id="04e97-120">[![Página de configurações de ER](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)</span><span class="sxs-lookup"><span data-stu-id="04e97-120">[![ER configurations page](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)</span></span>

> [!NOTE]
> <span data-ttu-id="04e97-121">Lembre-se de que esse parâmetro é específico do usuário e da empresa.</span><span class="sxs-lookup"><span data-stu-id="04e97-121">Be aware that this parameter is user specific and company specific.</span></span>

## <a name=""></a><span data-ttu-id="04e97-122"><a name="Autoformatting">Autoformatação de código</a></span><span class="sxs-lookup"><span data-stu-id="04e97-122"><a name="Autoformatting">Code autoformatting</a></span></span>

<span data-ttu-id="04e97-123">Quando você escreve uma expressão complexa que consiste em várias linhas de código, o recuo de uma nova linha inserida será automático com base no recuo da linha anterior.</span><span class="sxs-lookup"><span data-stu-id="04e97-123">When you write a complex expression that consists of multiple rows of code, the indentation of a new entered line will be automatic based on the indentation of the previous row.</span></span> <span data-ttu-id="04e97-124">Você pode selecionar linhas e alterar o respectivo recuo digitando **Tab** ou **Shift+Tab**.</span><span class="sxs-lookup"><span data-stu-id="04e97-124">You can select lines and change their indentation by typing **Tab** or **Shift+Tab**.</span></span>

<span data-ttu-id="04e97-125">[![Editor de fórmula do ER](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)</span><span class="sxs-lookup"><span data-stu-id="04e97-125">[![ER formula editor](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)</span></span>

<span data-ttu-id="04e97-126">A Autoformatação permite manter toda a expressão formatada de modo a facilitar a manutenção adicional e simplificar a compreensão da lógica configurada.</span><span class="sxs-lookup"><span data-stu-id="04e97-126">Autoformatting allows you to keep the entire expression well formatted to make further maintenance easier and to simplify understanding of the configured logic.</span></span>

## <a name=""></a><span data-ttu-id="04e97-127"><a name="IntelliSense">IntelliSense</a></span><span class="sxs-lookup"><span data-stu-id="04e97-127"><a name="IntelliSense">IntelliSense</a></span></span>

<span data-ttu-id="04e97-128">O editor fornece o preenchimento de palavras, que ajuda você a escrever expressões mais rapidamente e a evitar erros de digitação.</span><span class="sxs-lookup"><span data-stu-id="04e97-128">The editor provides word completion to help you write expression faster and avoid typos.</span></span> <span data-ttu-id="04e97-129">Quando você começa a adicionar um novo texto, o editor oferece automaticamente uma lista de funções aceitas nas funções do ER que contêm os caracteres inseridos.</span><span class="sxs-lookup"><span data-stu-id="04e97-129">When you start adding new text, the editor automatically offers a list of functions supported in ER functions that contain the characters you have entered.</span></span> <span data-ttu-id="04e97-130">Também é possível disparar o IntelliSense em qualquer lugar de uma expressão configurada digitando **CTRL + espaço**.</span><span class="sxs-lookup"><span data-stu-id="04e97-130">You can also trigger IntelliSense in any place of a configured expression by typing **Ctrl+Space**.</span></span>

<span data-ttu-id="04e97-131">[![Editor de fórmula do ER](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)</span><span class="sxs-lookup"><span data-stu-id="04e97-131">[![ER formula editor](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)</span></span>

## <a name=""></a><span data-ttu-id="04e97-132"><a name="CodeCompletion">Preenchimento de código</a></span><span class="sxs-lookup"><span data-stu-id="04e97-132"><a name="CodeCompletion">Code completion</a></span></span>

<span data-ttu-id="04e97-133">O editor fornece automaticamente o preenchimento de código com a:</span><span class="sxs-lookup"><span data-stu-id="04e97-133">The editor automatically provides code completion by:</span></span>

- <span data-ttu-id="04e97-134">Inserção de um colchete de fechamento quando o colchete de abertura é inserido, mantendo o cursor dentro dos colchetes.</span><span class="sxs-lookup"><span data-stu-id="04e97-134">Inserting a closing bracket when an opening  bracket is entered, keeping the cursor inside the brackets.</span></span>
- <span data-ttu-id="04e97-135">Inserção do segundo símbolo de aspas quando o primeiro é inserido, mantendo o curso dentro das aspas.</span><span class="sxs-lookup"><span data-stu-id="04e97-135">Inserting the second quotation symbol when the first one is entered, keeping the cursor inside the quotations.</span></span>
- <span data-ttu-id="04e97-136">Inserção do segundo símbolo de aspas duplas quando o primeiro é inserido, mantendo o curso dentro das aspas.</span><span class="sxs-lookup"><span data-stu-id="04e97-136">Inserting the second double quotation symbol when the first one is entered, keeping the cursor inside the quotations.</span></span>

<span data-ttu-id="04e97-137">[![Editor de fórmula do ER](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)</span><span class="sxs-lookup"><span data-stu-id="04e97-137">[![ER formula editor](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)</span></span>

<span data-ttu-id="04e97-138">Quando você aponta para o colchete digitado, o segundo colchete deste par é realçado automaticamente para mostrar a construção permitida.</span><span class="sxs-lookup"><span data-stu-id="04e97-138">When you point to the typed bracket, the second bracket of this pair is automatically highlighted to show the construct that they support.</span></span>

## <a name=""></a><span data-ttu-id="04e97-139"><a name="CodeNavigation">Navegação de código</a></span><span class="sxs-lookup"><span data-stu-id="04e97-139"><a name="CodeNavigation">Code navigation</a></span></span>

<span data-ttu-id="04e97-140">Você pode localizar linhas ou símbolos necessários em sua expressão digitando o comando **Ir para** usando a paleta de comandos ou o menu de contexto.</span><span class="sxs-lookup"><span data-stu-id="04e97-140">You can locate required symbols or lines in your expression by typing the **Go to** command using the command palette or the context menu.</span></span>

<span data-ttu-id="04e97-141">Por exemplo, para pular para a linha **8**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="04e97-141">For example, to jump to line **8**, do the following:</span></span>

- <span data-ttu-id="04e97-142">Pressione **CTRL + G**, digite o valor **8** e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="04e97-142">Press **Ctrl+G**, enter the value **8**, and then press **Enter**.</span></span>

  <span data-ttu-id="04e97-143">- ou -</span><span class="sxs-lookup"><span data-stu-id="04e97-143">-or-</span></span>

- <span data-ttu-id="04e97-144">Pressione **F1**, digite **G**, selecione **Ir para a linha**, digite o valor **8** e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="04e97-144">Press **F1**, type **G**, select **Go to line**, enter the value **8**, and the press **Enter**.</span></span>

<span data-ttu-id="04e97-145">[![Editor de fórmula do ER](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)</span><span class="sxs-lookup"><span data-stu-id="04e97-145">[![ER formula editor](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)</span></span>

## <a name=""></a><span data-ttu-id="04e97-146"><a name="CodeStructuring">Estruturação de código</a></span><span class="sxs-lookup"><span data-stu-id="04e97-146"><a name="CodeStructuring">Code structuring</a></span></span>

<span data-ttu-id="04e97-147">O código para algumas funções, como [IF](er-functions-logical-if.md) ou [CASE](er-functions-logical-case.md), é estruturado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="04e97-147">The code for some functions, such as [IF](er-functions-logical-if.md) or [CASE](er-functions-logical-case.md), is automatically structured.</span></span> <span data-ttu-id="04e97-148">Você pode expandir e recolher qualquer uma das regiões de dobra deste código para reduzir a parte editável de uma expressão a fim de focar somente na parte do código que requer sua atenção.</span><span class="sxs-lookup"><span data-stu-id="04e97-148">You can expand and collapse any or all of the folding regions of this code to reduce the editable part of an expression in order to focus on only  thepiece of code that requires your attention.</span></span> <span data-ttu-id="04e97-149">Os comandos de alternância entre dobrar/desdobrar podem ser usados para isso.</span><span class="sxs-lookup"><span data-stu-id="04e97-149">The toggle fold/unfold commands can be used for that.</span></span>

<span data-ttu-id="04e97-150">Por exemplo, para dobrar todas as regiões, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="04e97-150">For example, to fold all regions, do the following:</span></span>

- <span data-ttu-id="04e97-151">Pressione **Ctrl + K**</span><span class="sxs-lookup"><span data-stu-id="04e97-151">Press **Ctrl+K**</span></span>

  <span data-ttu-id="04e97-152">- ou -</span><span class="sxs-lookup"><span data-stu-id="04e97-152">-or-</span></span>

- <span data-ttu-id="04e97-153">Pressione **F1**, pressione **FO**, selecione **Dobrar tudo** e pressione **Enter**</span><span class="sxs-lookup"><span data-stu-id="04e97-153">Press **F1**, press **FO**, select **Fold all**, and then press **Enter**</span></span>

<span data-ttu-id="04e97-154">Para desdobrar todas as regiões, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="04e97-154">To unfold all regions, do the following:</span></span>

- <span data-ttu-id="04e97-155">Pressione **Ctrl + J**</span><span class="sxs-lookup"><span data-stu-id="04e97-155">Press **Ctrl+J**</span></span>

  <span data-ttu-id="04e97-156">- ou -</span><span class="sxs-lookup"><span data-stu-id="04e97-156">-or-</span></span>
  
- <span data-ttu-id="04e97-157">Pressione **F1**, digite **UN**, selecione **Desdobrar tudo** e pressione **Enter**</span><span class="sxs-lookup"><span data-stu-id="04e97-157">Press **F1**, type **UN**, select **Unfold all**, and then press **Enter**</span></span>

<span data-ttu-id="04e97-158">[![Editor de fórmula do ER](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)</span><span class="sxs-lookup"><span data-stu-id="04e97-158">[![ER formula editor](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)</span></span>

## <a name=""></a><span data-ttu-id="04e97-159"><a name="FindAndReplace">Localizar e substituir</a></span><span class="sxs-lookup"><span data-stu-id="04e97-159"><a name="FindAndReplace">Find and replace</a></span></span>

<span data-ttu-id="04e97-160">Para encontrar ocorrências de determinado texto, selecione o texto na expressão e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="04e97-160">To find occurrences of certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="04e97-161">Pressione **Ctrl + F** e, em seguida, **F3** para encontrar a próxima ocorrência do texto selecionado, ou pressione **Shift + F3** para encontrar a ocorrência anterior.</span><span class="sxs-lookup"><span data-stu-id="04e97-161">Press **Ctrl+F** and then press **F3** to find the next occurrence of the selected text, or press **Shift+F3** to find the previous occurrence.</span></span>

  <span data-ttu-id="04e97-162">- ou -</span><span class="sxs-lookup"><span data-stu-id="04e97-162">-or-</span></span>
  
- <span data-ttu-id="04e97-163">Pressione **F1**, digite **F** e selecione a opção necessária para localizar o texto selecionado.</span><span class="sxs-lookup"><span data-stu-id="04e97-163">Press **F1**, type **F**, and then select the required option to find the selected text.</span></span>

<span data-ttu-id="04e97-164">Para substituir ocorrências de um determinado texto, selecione o texto na expressão e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="04e97-164">To replace occurrences of a certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="04e97-165">Pressione **Ctrl + H**.</span><span class="sxs-lookup"><span data-stu-id="04e97-165">Press **Ctrl+H**.</span></span> <span data-ttu-id="04e97-166">Insira o texto alternativo e selecione a opção de substituição para substituir o texto selecionado ou todas as ocorrências desse texto na expressão atual.</span><span class="sxs-lookup"><span data-stu-id="04e97-166">Enter the alternative text and select the replacement option to replace either the selected text or all occurrences of this text in the current expression.</span></span>

  <span data-ttu-id="04e97-167">- ou -</span><span class="sxs-lookup"><span data-stu-id="04e97-167">-or-</span></span>
  
- <span data-ttu-id="04e97-168">Pressione **F1**, digite **R** e selecione a opção necessária para substituir o texto selecionado.</span><span class="sxs-lookup"><span data-stu-id="04e97-168">Press **F1**, type **R**, and then select the required option to replace the selected text.</span></span> <span data-ttu-id="04e97-169">Insira o texto alternativo e selecione a opção de substituição para substituir o texto selecionado ou todas as ocorrências desse texto na expressão atual.</span><span class="sxs-lookup"><span data-stu-id="04e97-169">Enter the alternative text and select the replacement option to replace either the selected text or all occurrences of this text in the current expression.</span></span>

<span data-ttu-id="04e97-170">Para alterar todas as ocorrências de um determinado texto, selecione o texto na expressão e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="04e97-170">To change all occurrences of a certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="04e97-171">Pressione **Ctrl + F2** e insira o texto alternativo.</span><span class="sxs-lookup"><span data-stu-id="04e97-171">Press **Ctrl+F2** and then enter the alternative text.</span></span>

  <span data-ttu-id="04e97-172">- ou -</span><span class="sxs-lookup"><span data-stu-id="04e97-172">-or-</span></span>
  
- <span data-ttu-id="04e97-173">Pressione **F1**, digite **C** e selecione a opção necessária para alterar o texto selecionado.</span><span class="sxs-lookup"><span data-stu-id="04e97-173">Press **F1**, type **C**, and then select the required option to change the selected text.</span></span> <span data-ttu-id="04e97-174">Insira o texto alternativo.</span><span class="sxs-lookup"><span data-stu-id="04e97-174">Enter the alternative text.</span></span>

<span data-ttu-id="04e97-175">[![Editor de fórmula do ER](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)</span><span class="sxs-lookup"><span data-stu-id="04e97-175">[![ER formula editor](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)</span></span>

## <a name=""></a><span data-ttu-id="04e97-176"><a name="DataPasting">Colagem de funções e fontes de dados</a></span><span class="sxs-lookup"><span data-stu-id="04e97-176"><a name="DataPasting">Data sources and functions pasting</a></span></span>

<span data-ttu-id="04e97-177">Você pode selecionar **Adicionar fonte de dados**, que cola na expressão atual uma fonte de dados que está atualmente selecionada no painel esquerdo **Fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="04e97-177">You can select **Add data source**, which pastes to the current expression a data source that is currently selected on the **Data source** left panel.</span></span> <span data-ttu-id="04e97-178">Da mesma forma, é possível selecionar **Adicionar função**, que cola na expressão atual uma função que está atualmente selecionada no painel direito **Funções**.</span><span class="sxs-lookup"><span data-stu-id="04e97-178">Simlilarly, you can select **Add function**, which pastes to the current expression a function that is currently selected on the **Functions** right panel.</span></span> <span data-ttu-id="04e97-179">Se você usar o editor de fórmula do ER, uma função selecionada ou uma fonte de dados selecionada sempre será colada no final da expressão configurada.</span><span class="sxs-lookup"><span data-stu-id="04e97-179">If you use the ER formula editor, a selected function or a selected data source will always be pasted to the end of the configured expression.</span></span> <span data-ttu-id="04e97-180">Quando você usa o editor de fórmula avançado do ER, uma função selecionada ou uma fonte de dados selecionada pode ser colada em qualquer parte da expressão configurada.</span><span class="sxs-lookup"><span data-stu-id="04e97-180">When you use the advanced ER formula editor, a selected function or a selected data source can be pasted to any part of the configured expression.</span></span> <span data-ttu-id="04e97-181">Será necessário usar o cursor para especificar onde deseja colar os dados.</span><span class="sxs-lookup"><span data-stu-id="04e97-181">You will need to use the cursor to specify where you want to paste the data.</span></span>

<span data-ttu-id="04e97-182">[![Editor de fórmula do ER](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)</span><span class="sxs-lookup"><span data-stu-id="04e97-182">[![ER formula editor](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)</span></span>

## <a name=""></a><span data-ttu-id="04e97-183"><a name="SyntaxColorization">Colorização da sintaxe</a></span><span class="sxs-lookup"><span data-stu-id="04e97-183"><a name="SyntaxColorization">Syntax colorization</a></span></span>

<span data-ttu-id="04e97-184">Atualmente, diferentes cores são usadas para realçar as seguintes partes das expressões:</span><span class="sxs-lookup"><span data-stu-id="04e97-184">Currently, different colors are used to highlight the following parts of expressions:</span></span>

- <span data-ttu-id="04e97-185">O texto entre colchetes duplos que pode representar uma ID de etiqueta de uma constante de texto.</span><span class="sxs-lookup"><span data-stu-id="04e97-185">The text in double brackets that can represent a label ID of a text constant.</span></span>

<span data-ttu-id="04e97-186">[![Editor de fórmula do ER](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)</span><span class="sxs-lookup"><span data-stu-id="04e97-186">[![ER formula editor](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)</span></span>

## <a name="limitations"></a><span data-ttu-id="04e97-187">Limitações</span><span class="sxs-lookup"><span data-stu-id="04e97-187">Limitations</span></span>

<span data-ttu-id="04e97-188">No momento, o editor é compatível com os seguintes navegadores da Web:</span><span class="sxs-lookup"><span data-stu-id="04e97-188">The editor is currently supported in the following web browsers:</span></span>

- <span data-ttu-id="04e97-189">Chrome</span><span class="sxs-lookup"><span data-stu-id="04e97-189">Chrome</span></span>
- <span data-ttu-id="04e97-190">Borda</span><span class="sxs-lookup"><span data-stu-id="04e97-190">Edge</span></span>
- <span data-ttu-id="04e97-191">Firefox</span><span class="sxs-lookup"><span data-stu-id="04e97-191">Firefox</span></span>
- <span data-ttu-id="04e97-192">Opera</span><span class="sxs-lookup"><span data-stu-id="04e97-192">Opera</span></span>
- <span data-ttu-id="04e97-193">Safari</span><span class="sxs-lookup"><span data-stu-id="04e97-193">Safari</span></span>

## <a name="additional-resources"></a><span data-ttu-id="04e97-194">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="04e97-194">Additional resources</span></span>

- [<span data-ttu-id="04e97-195">Visão geral de Relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="04e97-195">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="04e97-196">Designer de fórmulas no Relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="04e97-196">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)
- [<span data-ttu-id="04e97-197">Monaco Editor</span><span class="sxs-lookup"><span data-stu-id="04e97-197">Monaco editor</span></span>](https://microsoft.github.io/monaco-editor)
