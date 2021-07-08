---
title: Editor de fórmula avançado do Relatório eletrônico
description: Este tópico descreve como o editor de fórmula avançado pode ser usado para configurar expressões em componentes de formato e mapeamento de modelo do ER (Relatório eletrônico).
author: NickSelin
ms.date: 06/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: f7f80928e1d3f5d4892f72d4bd2fd09b70a26c1f
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270698"
---
# <a name="electronic-reporting-advanced-formula-editor"></a><span data-ttu-id="08147-103">Editor de fórmula avançado do Relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="08147-103">Electronic reporting advanced formula editor</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="08147-104">Além do [editor de fórmula](general-electronic-reporting-formula-designer.md) do [Relatório eletrônico](general-electronic-reporting.md), você pode usar o editor de fórmula avançado do Relatório eletrônico para aprimorar a experiência de configuração das expressões de ER (Relatório eletrônico).</span><span class="sxs-lookup"><span data-stu-id="08147-104">In addition to the [Electronic reporting](general-electronic-reporting.md) [formula editor](general-electronic-reporting-formula-designer.md), you can use the advanced Electronic reporting formula editor to improve the experience of configuring Electronic reporting (ER) expressions.</span></span> <span data-ttu-id="08147-105">O editor avançado é baseado em navegador e conta com a tecnologia do [Monaco Editor](https://microsoft.github.io/monaco-editor).</span><span class="sxs-lookup"><span data-stu-id="08147-105">The advanced editor is browser-based and powered by the [Monaco editor](https://microsoft.github.io/monaco-editor).</span></span> <span data-ttu-id="08147-106">Os recursos do editor avançado usados com mais frequência são descritos neste tópico:</span><span class="sxs-lookup"><span data-stu-id="08147-106">The most commonly used advanced editor features are described in this topic:</span></span>

- [<span data-ttu-id="08147-107">Autoformatação de código</span><span class="sxs-lookup"><span data-stu-id="08147-107">Code autoformatting</span></span>](#Autoformatting)
- [<span data-ttu-id="08147-108">IntelliSense</span><span class="sxs-lookup"><span data-stu-id="08147-108">IntelliSense</span></span>](#IntelliSense)
- [<span data-ttu-id="08147-109">Preenchimento de código</span><span class="sxs-lookup"><span data-stu-id="08147-109">Code completion</span></span>](#CodeCompletion)
- [<span data-ttu-id="08147-110">Navegação de código</span><span class="sxs-lookup"><span data-stu-id="08147-110">Code navigation</span></span>](#CodeNavigation)
- [<span data-ttu-id="08147-111">Estruturação de código</span><span class="sxs-lookup"><span data-stu-id="08147-111">Code structuring</span></span>](#CodeStructuring)
- [<span data-ttu-id="08147-112">Localizar e substituir</span><span class="sxs-lookup"><span data-stu-id="08147-112">Find and replace</span></span>](#FindAndReplace)
- [<span data-ttu-id="08147-113">Colagem de dados</span><span class="sxs-lookup"><span data-stu-id="08147-113">Data pasting</span></span>](#DataPasting)
- [<span data-ttu-id="08147-114">Colorização da sintaxe</span><span class="sxs-lookup"><span data-stu-id="08147-114">Syntax colorization</span></span>](#SyntaxColorization)

## <a name=""></a><span data-ttu-id="08147-115"><a name="ActivateAdvEditor">Ativar o editor de fórmula avançado</a></span><span class="sxs-lookup"><span data-stu-id="08147-115"><a name="ActivateAdvEditor">Activate the advanced formula editor</a></span></span>

<span data-ttu-id="08147-116">Conclua as etapas a seguir para começar a usar o editor de fórmula avançado em sua instância do Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="08147-116">Complete the following steps to start using the advanced formula editor in your instance of Microsoft Dynamics 365 Finance.</span></span>

1.  <span data-ttu-id="08147-117">Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="08147-117">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2.  <span data-ttu-id="08147-118">Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.</span><span class="sxs-lookup"><span data-stu-id="08147-118">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3.  <span data-ttu-id="08147-119">Na caixa de diálogo **Parâmetro de usuário**, na seção **Rastreamento de execução**, defina o parâmetro **Habilitar editor de fórmula avançado** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="08147-119">In the **User parameters** dialog box, in the **Execution tracing** section, set the **Enable advanced formula editor** parameter to **Yes**.</span></span>

<span data-ttu-id="08147-120">[![Caixa de diálogo de parâmetros do usuário, Ativar parâmetro avançado do editor de fórmulas destacado](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)</span><span class="sxs-lookup"><span data-stu-id="08147-120">[![User parameters dialog box, Enable advanced formula editor parameter highlighted](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)</span></span>

> [!NOTE]
> <span data-ttu-id="08147-121">Lembre-se de que esse parâmetro é específico do usuário e da empresa.</span><span class="sxs-lookup"><span data-stu-id="08147-121">Be aware that this parameter is user specific and company specific.</span></span>

<span data-ttu-id="08147-122">A partir da versão 10.0.19 do Microsoft Dynamics 365 Finance, você pode controlar qual editor de fórmulas de ER é oferecido por padrão.</span><span class="sxs-lookup"><span data-stu-id="08147-122">Starting in Microsoft Dynamics 365 Finance version 10.0.19, you can control what ER formula editor is offered by default.</span></span> <span data-ttu-id="08147-123">Complete as seguintes etapas para habilitar o editor de fórmulas avançado para todos os usuários e empresas da atual instância do Finance.</span><span class="sxs-lookup"><span data-stu-id="08147-123">Complete the following steps to enable the advanced formula editor for all users and companies of the current Finance instance.</span></span>

1.  <span data-ttu-id="08147-124">Abra o espaço de trabalho **Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="08147-124">Open the **Feature management** workspace.</span></span>
2.  <span data-ttu-id="08147-125">Encontre e selecione o recurso **Configurar o editor de fórmula avançado de ER como o padrão para todos os usuários** na lista e selecione **Ativar agora**.</span><span class="sxs-lookup"><span data-stu-id="08147-125">Find and select the feature **Set the ER advanced formula editor as the default one for all users** in the list, and then select **Enable now**.</span></span>
3.  <span data-ttu-id="08147-126">Vá para **Administração da organização** > **Relatório eletrônico** > **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="08147-126">Go to **Organization administration** > **Electronic reporting** > **Configurations**.</span></span>
4.  <span data-ttu-id="08147-127">Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.</span><span class="sxs-lookup"><span data-stu-id="08147-127">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
5.  <span data-ttu-id="08147-128">Na caixa de diálogo de **Parâmetros do usuário**, encontre o parâmetro **Desativar editor de fórmula avançado** e verifique se ele está definido como **Não**.</span><span class="sxs-lookup"><span data-stu-id="08147-128">In the **User parameters** dialog box, find the **Disable advanced formula editor** parameter and verify that it is set to **No**.</span></span>

<span data-ttu-id="08147-129">[![Caixa de diálogo de parâmetros do usuário, Desativar parâmetro avançado do editor de fórmulas destacado](./media/ER-AdvEditor-Activate2.png)](./media/ER-AdvEditor-Activate2.png)</span><span class="sxs-lookup"><span data-stu-id="08147-129">[![User parameters dialog box, Disable advanced formula editor parameter highlighted](./media/ER-AdvEditor-Activate2.png)](./media/ER-AdvEditor-Activate2.png)</span></span>

> [!NOTE]
> <span data-ttu-id="08147-130">Os valores dos parâmetros **Habilitar editor de fórmula avançado** e **Desabilitar editor de fórmula avançado** são mantidos separados para cada usuário e oferecidos na caixa de diálogo **Parâmetros de usuário** dependendo do status do recurso **Definir o editor de fórmula avançado do ER como o padrão para todos os usuários**.</span><span class="sxs-lookup"><span data-stu-id="08147-130">The values of the parameters **Enable advanced formula editor** and **Disable advanced formula editor** are kept separate for each user and offered on the **User parameters** dialog box depending on the status of the **Set the ER advanced formula editor as the default one for all users** feature.</span></span>

## <a name=""></a><span data-ttu-id="08147-131"><a name="Autoformatting">Autoformatação de código</a></span><span class="sxs-lookup"><span data-stu-id="08147-131"><a name="Autoformatting">Code autoformatting</a></span></span>

<span data-ttu-id="08147-132">Quando você escreve uma expressão complexa que consiste em várias linhas de código, o recuo de uma nova linha inserida será automático com base no recuo da linha anterior.</span><span class="sxs-lookup"><span data-stu-id="08147-132">When you write a complex expression that consists of multiple rows of code, the indentation of a new entered line will be automatic based on the indentation of the previous row.</span></span> <span data-ttu-id="08147-133">Você pode selecionar linhas e alterar o respectivo recuo digitando **Tab** ou **Shift+Tab**.</span><span class="sxs-lookup"><span data-stu-id="08147-133">You can select lines and change their indentation by typing **Tab** or **Shift+Tab**.</span></span>

<span data-ttu-id="08147-134">[![Gif do editor de fórmulas de ER mostrando linhas de seleção e alterando o recuo](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)</span><span class="sxs-lookup"><span data-stu-id="08147-134">[![ER formula editor gif showing selecting lines and changing the indentation](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)</span></span>

<span data-ttu-id="08147-135">A Autoformatação permite manter toda a expressão formatada de modo a facilitar a manutenção adicional e simplificar a compreensão da lógica configurada.</span><span class="sxs-lookup"><span data-stu-id="08147-135">Autoformatting allows you to keep the entire expression well formatted to make further maintenance easier and to simplify understanding of the configured logic.</span></span>

## <a name=""></a><span data-ttu-id="08147-136"><a name="IntelliSense">IntelliSense</a></span><span class="sxs-lookup"><span data-stu-id="08147-136"><a name="IntelliSense">IntelliSense</a></span></span>

<span data-ttu-id="08147-137">O editor fornece o preenchimento de palavras, que ajuda você a escrever expressões mais rapidamente e a evitar erros de digitação.</span><span class="sxs-lookup"><span data-stu-id="08147-137">The editor provides word completion to help you write expression faster and avoid typos.</span></span> <span data-ttu-id="08147-138">Quando você começa a adicionar um novo texto, o editor oferece automaticamente uma lista de funções aceitas nas funções do ER que contêm os caracteres inseridos.</span><span class="sxs-lookup"><span data-stu-id="08147-138">When you start adding new text, the editor automatically offers a list of functions supported in ER functions that contain the characters you have entered.</span></span> <span data-ttu-id="08147-139">Também é possível disparar o IntelliSense em qualquer lugar de uma expressão configurada digitando **CTRL + espaço**.</span><span class="sxs-lookup"><span data-stu-id="08147-139">You can also trigger IntelliSense in any place of a configured expression by typing **Ctrl+Space**.</span></span>

<span data-ttu-id="08147-140">[![Gif do editor de fórmula de ER mostrando acionamento do IntelliSense](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)</span><span class="sxs-lookup"><span data-stu-id="08147-140">[![ER formula editor gif showing triggering IntelliSense](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)</span></span>

## <a name=""></a><span data-ttu-id="08147-141"><a name="CodeCompletion">Preenchimento de código</a></span><span class="sxs-lookup"><span data-stu-id="08147-141"><a name="CodeCompletion">Code completion</a></span></span>

<span data-ttu-id="08147-142">O editor fornece automaticamente o preenchimento de código com a:</span><span class="sxs-lookup"><span data-stu-id="08147-142">The editor automatically provides code completion by:</span></span>

- <span data-ttu-id="08147-143">Inserção de um colchete de fechamento quando o colchete de abertura é inserido, mantendo o cursor dentro dos colchetes.</span><span class="sxs-lookup"><span data-stu-id="08147-143">Inserting a closing bracket when an opening  bracket is entered, keeping the cursor inside the brackets.</span></span>
- <span data-ttu-id="08147-144">Inserção do segundo símbolo de aspas quando o primeiro é inserido, mantendo o curso dentro das aspas.</span><span class="sxs-lookup"><span data-stu-id="08147-144">Inserting the second quotation symbol when the first one is entered, keeping the cursor inside the quotations.</span></span>
- <span data-ttu-id="08147-145">Inserção do segundo símbolo de aspas duplas quando o primeiro é inserido, mantendo o curso dentro das aspas.</span><span class="sxs-lookup"><span data-stu-id="08147-145">Inserting the second double quotation symbol when the first one is entered, keeping the cursor inside the quotations.</span></span>

<span data-ttu-id="08147-146">[![Gif do editor de fórmulas de ER mostrando o editor automaticamente fornecendo conclusão de código](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)</span><span class="sxs-lookup"><span data-stu-id="08147-146">[![ER formula editor gif showing the editor automatically providing code completion](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)</span></span>

<span data-ttu-id="08147-147">Quando você aponta para o colchete digitado, o segundo colchete deste par é realçado automaticamente para mostrar a construção permitida.</span><span class="sxs-lookup"><span data-stu-id="08147-147">When you point to the typed bracket, the second bracket of this pair is automatically highlighted to show the construct that they support.</span></span>

## <a name=""></a><span data-ttu-id="08147-148"><a name="CodeNavigation">Navegação de código</a></span><span class="sxs-lookup"><span data-stu-id="08147-148"><a name="CodeNavigation">Code navigation</a></span></span>

<span data-ttu-id="08147-149">Você pode localizar linhas ou símbolos necessários em sua expressão digitando o comando **Ir para** usando a paleta de comandos ou o menu de contexto.</span><span class="sxs-lookup"><span data-stu-id="08147-149">You can locate required symbols or lines in your expression by typing the **Go to** command using the command palette or the context menu.</span></span>

<span data-ttu-id="08147-150">Por exemplo, para pular para a linha **8**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="08147-150">For example, to jump to line **8**, do the following:</span></span>

- <span data-ttu-id="08147-151">Pressione **CTRL + G**, digite o valor **8** e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="08147-151">Press **Ctrl+G**, enter the value **8**, and then press **Enter**.</span></span>

  <span data-ttu-id="08147-152">- ou -</span><span class="sxs-lookup"><span data-stu-id="08147-152">-or-</span></span>

- <span data-ttu-id="08147-153">Pressione **F1**, digite **G**, selecione **Ir para a linha**, digite o valor **8** e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="08147-153">Press **F1**, type **G**, select **Go to line**, enter the value **8**, and the press **Enter**.</span></span>

<span data-ttu-id="08147-154">[![Gif do editor de fórmulas de ER mostrando como localizar partes de uma expressão usando a paleta de comando](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)</span><span class="sxs-lookup"><span data-stu-id="08147-154">[![ER formula editor gif showing how to locate parts of an expression using the command palette](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)</span></span>

## <a name=""></a><span data-ttu-id="08147-155"><a name="CodeStructuring">Estruturação de código</a></span><span class="sxs-lookup"><span data-stu-id="08147-155"><a name="CodeStructuring">Code structuring</a></span></span>

<span data-ttu-id="08147-156">O código para algumas funções, como [IF](er-functions-logical-if.md) ou [CASE](er-functions-logical-case.md), é estruturado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="08147-156">The code for some functions, such as [IF](er-functions-logical-if.md) or [CASE](er-functions-logical-case.md), is automatically structured.</span></span> <span data-ttu-id="08147-157">Você pode expandir e recolher qualquer uma das regiões de dobra deste código para reduzir a parte editável de uma expressão a fim de focar somente na parte do código que requer sua atenção.</span><span class="sxs-lookup"><span data-stu-id="08147-157">You can expand and collapse any or all of the folding regions of this code to reduce the editable part of an expression in order to focus on only  thepiece of code that requires your attention.</span></span> <span data-ttu-id="08147-158">Os comandos de alternância entre dobrar/desdobrar podem ser usados para isso.</span><span class="sxs-lookup"><span data-stu-id="08147-158">The toggle fold/unfold commands can be used for that.</span></span>

<span data-ttu-id="08147-159">Por exemplo, para dobrar todas as regiões, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="08147-159">For example, to fold all regions, do the following:</span></span>

- <span data-ttu-id="08147-160">Pressione **Ctrl + K**</span><span class="sxs-lookup"><span data-stu-id="08147-160">Press **Ctrl+K**</span></span>

  <span data-ttu-id="08147-161">- ou -</span><span class="sxs-lookup"><span data-stu-id="08147-161">-or-</span></span>

- <span data-ttu-id="08147-162">Pressione **F1**, pressione **FO**, selecione **Dobrar tudo** e pressione **Enter**</span><span class="sxs-lookup"><span data-stu-id="08147-162">Press **F1**, press **FO**, select **Fold all**, and then press **Enter**</span></span>

<span data-ttu-id="08147-163">Para desdobrar todas as regiões, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="08147-163">To unfold all regions, do the following:</span></span>

- <span data-ttu-id="08147-164">Pressione **Ctrl + J**</span><span class="sxs-lookup"><span data-stu-id="08147-164">Press **Ctrl+J**</span></span>

  <span data-ttu-id="08147-165">- ou -</span><span class="sxs-lookup"><span data-stu-id="08147-165">-or-</span></span>
  
- <span data-ttu-id="08147-166">Pressione **F1**, digite **UN**, selecione **Desdobrar tudo** e pressione **Enter**</span><span class="sxs-lookup"><span data-stu-id="08147-166">Press **F1**, type **UN**, select **Unfold all**, and then press **Enter**</span></span>

<span data-ttu-id="08147-167">[![Gif do editor de fórmula de ER mostrando o código sendo desdobrado](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)</span><span class="sxs-lookup"><span data-stu-id="08147-167">[![ER formula editor gif showing code being unfolded](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)</span></span>

## <a name=""></a><span data-ttu-id="08147-168"><a name="FindAndReplace">Localizar e substituir</a></span><span class="sxs-lookup"><span data-stu-id="08147-168"><a name="FindAndReplace">Find and replace</a></span></span>

<span data-ttu-id="08147-169">Para encontrar ocorrências de determinado texto, selecione o texto na expressão e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="08147-169">To find occurrences of certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="08147-170">Pressione **Ctrl + F** e, em seguida, **F3** para encontrar a próxima ocorrência do texto selecionado, ou pressione **Shift + F3** para encontrar a ocorrência anterior.</span><span class="sxs-lookup"><span data-stu-id="08147-170">Press **Ctrl+F** and then press **F3** to find the next occurrence of the selected text, or press **Shift+F3** to find the previous occurrence.</span></span>

  <span data-ttu-id="08147-171">- ou -</span><span class="sxs-lookup"><span data-stu-id="08147-171">-or-</span></span>
  
- <span data-ttu-id="08147-172">Pressione **F1**, digite **F** e selecione a opção necessária para localizar o texto selecionado.</span><span class="sxs-lookup"><span data-stu-id="08147-172">Press **F1**, type **F**, and then select the required option to find the selected text.</span></span>

<span data-ttu-id="08147-173">Para substituir ocorrências de um determinado texto, selecione o texto na expressão e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="08147-173">To replace occurrences of a certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="08147-174">Pressione **Ctrl + H**.</span><span class="sxs-lookup"><span data-stu-id="08147-174">Press **Ctrl+H**.</span></span> <span data-ttu-id="08147-175">Insira o texto alternativo e selecione a opção de substituição para substituir o texto selecionado ou todas as ocorrências desse texto na expressão atual.</span><span class="sxs-lookup"><span data-stu-id="08147-175">Enter the alternative text and select the replacement option to replace either the selected text or all occurrences of this text in the current expression.</span></span>

  <span data-ttu-id="08147-176">- ou -</span><span class="sxs-lookup"><span data-stu-id="08147-176">-or-</span></span>
  
- <span data-ttu-id="08147-177">Pressione **F1**, digite **R** e selecione a opção necessária para substituir o texto selecionado.</span><span class="sxs-lookup"><span data-stu-id="08147-177">Press **F1**, type **R**, and then select the required option to replace the selected text.</span></span> <span data-ttu-id="08147-178">Insira o texto alternativo e selecione a opção de substituição para substituir o texto selecionado ou todas as ocorrências desse texto na expressão atual.</span><span class="sxs-lookup"><span data-stu-id="08147-178">Enter the alternative text and select the replacement option to replace either the selected text or all occurrences of this text in the current expression.</span></span>

<span data-ttu-id="08147-179">Para alterar todas as ocorrências de um determinado texto, selecione o texto na expressão e faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="08147-179">To change all occurrences of a certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="08147-180">Pressione **Ctrl + F2** e insira o texto alternativo.</span><span class="sxs-lookup"><span data-stu-id="08147-180">Press **Ctrl+F2** and then enter the alternative text.</span></span>

  <span data-ttu-id="08147-181">- ou -</span><span class="sxs-lookup"><span data-stu-id="08147-181">-or-</span></span>
  
- <span data-ttu-id="08147-182">Pressione **F1**, digite **C** e selecione a opção necessária para alterar o texto selecionado.</span><span class="sxs-lookup"><span data-stu-id="08147-182">Press **F1**, type **C**, and then select the required option to change the selected text.</span></span> <span data-ttu-id="08147-183">Insira o texto alternativo.</span><span class="sxs-lookup"><span data-stu-id="08147-183">Enter the alternative text.</span></span>

<span data-ttu-id="08147-184">[![Gif do editor de fórmula de ER mostrando localizar e substituir](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)</span><span class="sxs-lookup"><span data-stu-id="08147-184">[![ER formula editor gif showing find and replace](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)</span></span>

## <a name=""></a><span data-ttu-id="08147-185"><a name="DataPasting">Colagem de funções e fontes de dados</a></span><span class="sxs-lookup"><span data-stu-id="08147-185"><a name="DataPasting">Data sources and functions pasting</a></span></span>

<span data-ttu-id="08147-186">Você pode selecionar **Adicionar fonte de dados**, que cola na expressão atual uma fonte de dados que está atualmente selecionada no painel esquerdo **Fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="08147-186">You can select **Add data source**, which pastes to the current expression a data source that is currently selected on the **Data source** left panel.</span></span> <span data-ttu-id="08147-187">Da mesma forma, é possível selecionar **Adicionar função**, que cola na expressão atual uma função que está atualmente selecionada no painel direito **Funções**.</span><span class="sxs-lookup"><span data-stu-id="08147-187">Simlilarly, you can select **Add function**, which pastes to the current expression a function that is currently selected on the **Functions** right panel.</span></span> <span data-ttu-id="08147-188">Se você usar o editor de fórmula do ER, uma função selecionada ou uma fonte de dados selecionada sempre será colada no final da expressão configurada.</span><span class="sxs-lookup"><span data-stu-id="08147-188">If you use the ER formula editor, a selected function or a selected data source will always be pasted to the end of the configured expression.</span></span> <span data-ttu-id="08147-189">Quando você usa o editor de fórmula avançado do ER, uma função selecionada ou uma fonte de dados selecionada pode ser colada em qualquer parte da expressão configurada.</span><span class="sxs-lookup"><span data-stu-id="08147-189">When you use the advanced ER formula editor, a selected function or a selected data source can be pasted to any part of the configured expression.</span></span> <span data-ttu-id="08147-190">Será necessário usar o cursor para especificar onde deseja colar os dados.</span><span class="sxs-lookup"><span data-stu-id="08147-190">You will need to use the cursor to specify where you want to paste the data.</span></span>

<span data-ttu-id="08147-191">[![Gif do editor de fórmulas de ER mostrando como adicionar uma fonte de dados e colar uma função](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)</span><span class="sxs-lookup"><span data-stu-id="08147-191">[![ER formula editor gif showing adding a data source and pasting a function](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)</span></span>

## <a name=""></a><span data-ttu-id="08147-192"><a name="SyntaxColorization">Colorização da sintaxe</a></span><span class="sxs-lookup"><span data-stu-id="08147-192"><a name="SyntaxColorization">Syntax colorization</a></span></span>

<span data-ttu-id="08147-193">Atualmente, diferentes cores são usadas para realçar as seguintes partes das expressões:</span><span class="sxs-lookup"><span data-stu-id="08147-193">Currently, different colors are used to highlight the following parts of expressions:</span></span>

- <span data-ttu-id="08147-194">O texto entre colchetes duplos que pode representar uma ID de etiqueta de uma constante de texto.</span><span class="sxs-lookup"><span data-stu-id="08147-194">The text in double brackets that can represent a label ID of a text constant.</span></span>

<span data-ttu-id="08147-195">[![Editor de fórmula do ER](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)</span><span class="sxs-lookup"><span data-stu-id="08147-195">[![ER formula editor](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)</span></span>

## <a name="limitations"></a><span data-ttu-id="08147-196">Limitações</span><span class="sxs-lookup"><span data-stu-id="08147-196">Limitations</span></span>

<span data-ttu-id="08147-197">No momento, o editor é compatível com os seguintes navegadores da Web:</span><span class="sxs-lookup"><span data-stu-id="08147-197">The editor is currently supported in the following web browsers:</span></span>

- <span data-ttu-id="08147-198">Chrome</span><span class="sxs-lookup"><span data-stu-id="08147-198">Chrome</span></span>
- <span data-ttu-id="08147-199">Borda</span><span class="sxs-lookup"><span data-stu-id="08147-199">Edge</span></span>
- <span data-ttu-id="08147-200">Firefox</span><span class="sxs-lookup"><span data-stu-id="08147-200">Firefox</span></span>
- <span data-ttu-id="08147-201">Opera</span><span class="sxs-lookup"><span data-stu-id="08147-201">Opera</span></span>
- <span data-ttu-id="08147-202">Safari</span><span class="sxs-lookup"><span data-stu-id="08147-202">Safari</span></span>

## <a name="additional-resources"></a><span data-ttu-id="08147-203">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="08147-203">Additional resources</span></span>

- [<span data-ttu-id="08147-204">Visão geral de Relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="08147-204">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="08147-205">Designer de fórmulas no Relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="08147-205">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)
- [<span data-ttu-id="08147-206">Monaco Editor</span><span class="sxs-lookup"><span data-stu-id="08147-206">Monaco editor</span></span>](https://microsoft.github.io/monaco-editor)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
