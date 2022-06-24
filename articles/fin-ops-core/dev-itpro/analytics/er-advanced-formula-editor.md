---
title: Editor de fórmula avançado do Relatório eletrônico
description: Este artigo descreve como o editor de fórmula avançado pode ser usado para configurar expressões em componentes de formato e mapeamento de modelo do ER (Relatório eletrônico).
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
ms.openlocfilehash: f54ab248e38d87b0a9fb7a73143f56fa704a3f67
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869089"
---
# <a name="electronic-reporting-advanced-formula-editor"></a>Editor de fórmula avançado do Relatório eletrônico

[!include [banner](../includes/banner.md)]

Além do [editor de fórmula](general-electronic-reporting-formula-designer.md) do [Relatório eletrônico](general-electronic-reporting.md), você pode usar o editor de fórmula avançado do Relatório eletrônico para aprimorar a experiência de configuração das expressões de ER (Relatório eletrônico). O editor avançado é baseado em navegador e conta com a tecnologia do [Monaco Editor](https://microsoft.github.io/monaco-editor). Os recursos do editor avançado usados com mais frequência são descritos neste artigo:

- [Autoformatação de código](#Autoformatting)
- [IntelliSense](#IntelliSense)
- [Preenchimento de código](#CodeCompletion)
- [Navegação de código](#CodeNavigation)
- [Estruturação de código](#CodeStructuring)
- [Localizar e substituir](#FindAndReplace)
- [Colagem de dados](#DataPasting)
- [Colorização da sintaxe](#SyntaxColorization)

## <a name=""></a><a name="ActivateAdvEditor">Ativar o editor de fórmula avançado</a>

Conclua as etapas a seguir para começar a usar o editor de fórmula avançado em sua instância do Microsoft Dynamics 365 Finance.

1.  Acesse **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2.  Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.
3.  Na caixa de diálogo **Parâmetro de usuário**, na seção **Rastreamento de execução**, defina o parâmetro **Habilitar editor de fórmula avançado** como **Sim**.

[![Caixa de diálogo de parâmetros do usuário, Ativar parâmetro avançado do editor de fórmulas destacado.](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)

> [!NOTE]
> Lembre-se de que esse parâmetro é específico do usuário e da empresa.

A partir da versão 10.0.19 do Microsoft Dynamics 365 Finance, você pode controlar qual editor de fórmulas de ER é oferecido por padrão. Complete as seguintes etapas para habilitar o editor de fórmulas avançado para todos os usuários e empresas da atual instância do Finance.

1.  Abra o espaço de trabalho **Gerenciamento de recursos**.
2.  Encontre e selecione o recurso **Configurar o editor de fórmula avançado de ER como o padrão para todos os usuários** na lista e selecione **Ativar agora**.
3.  Acesse **Administração da organização** > **Relatório eletrônico** > **Configurações**.
4.  Na página **Configurações**, no Painel Ação, na guia **Configurações**, no grupo **Configurações avançadas**, selecione **Parâmetros de usuário**.
5.  Na caixa de diálogo de **Parâmetros do usuário**, encontre o parâmetro **Desativar editor de fórmula avançado** e verifique se ele está definido como **Não**.

[![Caixa de diálogo de parâmetros do usuário, Desativar parâmetro avançado do editor de fórmulas destacado.](./media/ER-AdvEditor-Activate2.png)](./media/ER-AdvEditor-Activate2.png)

> [!NOTE]
> Os valores dos parâmetros **Habilitar editor de fórmula avançado** e **Desabilitar editor de fórmula avançado** são mantidos separados para cada usuário e oferecidos na caixa de diálogo **Parâmetros de usuário** dependendo do status do recurso **Definir o editor de fórmula avançado do ER como o padrão para todos os usuários**.

## <a name=""></a><a name="Autoformatting">Autoformatação de código</a>

Quando você escreve uma expressão complexa que consiste em várias linhas de código, o recuo de uma nova linha inserida será automático com base no recuo da linha anterior. Você pode selecionar linhas e alterar o respectivo recuo digitando **Tab** ou **Shift+Tab**.

[![Gif do editor de fórmulas de ER mostrando linhas de seleção e alterando o recuo.](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)

A Autoformatação permite manter toda a expressão formatada de modo a facilitar a manutenção adicional e simplificar a compreensão da lógica configurada.

## <a name=""></a><a name="IntelliSense">IntelliSense</a>

O editor fornece o preenchimento de palavras, que ajuda você a escrever expressões mais rapidamente e a evitar erros de digitação. Quando você começa a adicionar um novo texto, o editor oferece automaticamente uma lista de funções aceitas nas funções do ER que contêm os caracteres inseridos. Também é possível disparar o IntelliSense em qualquer lugar de uma expressão configurada digitando **CTRL + espaço**.

[![Gif do editor de fórmula de ER mostrando acionamento do IntelliSense.](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)

## <a name=""></a><a name="CodeCompletion">Preenchimento de código</a>

O editor fornece automaticamente o preenchimento de código com a:

- Inserção de um colchete de fechamento quando o colchete de abertura é inserido, mantendo o cursor dentro dos colchetes.
- Inserção do segundo símbolo de aspas quando o primeiro é inserido, mantendo o curso dentro das aspas.
- Inserção do segundo símbolo de aspas duplas quando o primeiro é inserido, mantendo o curso dentro das aspas.

[![Gif do editor de fórmulas de ER mostrando o editor automaticamente fornecendo conclusão de código.](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)

Quando você aponta para o colchete digitado, o segundo colchete deste par é realçado automaticamente para mostrar a construção permitida.

## <a name=""></a><a name="CodeNavigation">Navegação de código</a>

Você pode localizar linhas ou símbolos necessários em sua expressão digitando o comando **Ir para** usando a paleta de comandos ou o menu de contexto.

Por exemplo, para pular para a linha **8**, faça o seguinte:

- Pressione **CTRL + G**, digite o valor **8** e pressione **Enter**.

  - ou -

- Pressione **F1**, digite **G**, selecione **Ir para a linha**, digite o valor **8** e pressione **Enter**.

[![Gif do editor de fórmulas de ER mostrando como localizar partes de uma expressão usando a paleta de comando.](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)

## <a name=""></a><a name="CodeStructuring">Estruturação de código</a>

O código para algumas funções, como [IF](er-functions-logical-if.md) ou [CASE](er-functions-logical-case.md), é estruturado automaticamente. Você pode expandir e recolher qualquer uma das regiões de dobra deste código para reduzir a parte editável de uma expressão a fim de focar somente na parte do código que requer sua atenção. Os comandos de alternância entre dobrar/desdobrar podem ser usados para isso.

Por exemplo, para dobrar todas as regiões, faça o seguinte:

- Pressione **Ctrl + K**

  - ou -

- Pressione **F1**, pressione **FO**, selecione **Dobrar tudo** e pressione **Enter**

Para desdobrar todas as regiões, faça o seguinte:

- Pressione **Ctrl + J**

  - ou -
  
- Pressione **F1**, digite **UN**, selecione **Desdobrar tudo** e pressione **Enter**

[![Gif do editor de fórmula de ER mostrando o código sendo desdobrado.](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)

## <a name=""></a><a name="FindAndReplace">Localizar e substituir</a>

Para encontrar ocorrências de determinado texto, selecione o texto na expressão e faça o seguinte:

- Pressione **Ctrl + F** e, em seguida, **F3** para encontrar a próxima ocorrência do texto selecionado, ou pressione **Shift + F3** para encontrar a ocorrência anterior.

  - ou -
  
- Pressione **F1**, digite **F** e selecione a opção necessária para localizar o texto selecionado.

Para substituir ocorrências de um determinado texto, selecione o texto na expressão e faça o seguinte:

- Pressione **Ctrl + H**. Insira o texto alternativo e selecione a opção de substituição para substituir o texto selecionado ou todas as ocorrências desse texto na expressão atual.

  - ou -
  
- Pressione **F1**, digite **R** e selecione a opção necessária para substituir o texto selecionado. Insira o texto alternativo e selecione a opção de substituição para substituir o texto selecionado ou todas as ocorrências desse texto na expressão atual.

Para alterar todas as ocorrências de um determinado texto, selecione o texto na expressão e faça o seguinte:

- Pressione **Ctrl + F2** e insira o texto alternativo.

  - ou -
  
- Pressione **F1**, digite **C** e selecione a opção necessária para alterar o texto selecionado. Insira o texto alternativo.

[![Gif do editor de fórmula de ER mostrando localizar e substituir.](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)

## <a name=""></a><a name="DataPasting">Colagem de funções e fontes de dados</a>

Você pode selecionar **Adicionar fonte de dados**, que cola na expressão atual uma fonte de dados que está atualmente selecionada no painel esquerdo **Fonte de dados**. Da mesma forma, é possível selecionar **Adicionar função**, que cola na expressão atual uma função que está atualmente selecionada no painel direito **Funções**. Se você usar o editor de fórmula do ER, uma função selecionada ou uma fonte de dados selecionada sempre será colada no final da expressão configurada. Quando você usa o editor de fórmula avançado do ER, uma função selecionada ou uma fonte de dados selecionada pode ser colada em qualquer parte da expressão configurada. Será necessário usar o cursor para especificar onde deseja colar os dados.

[![Gif do editor de fórmulas de ER mostrando como adicionar uma fonte de dados e colar uma função.](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)

## <a name=""></a><a name="SyntaxColorization">Colorização da sintaxe</a>

Atualmente, diferentes cores são usadas para realçar as seguintes partes das expressões:

- O texto entre colchetes duplos que pode representar uma ID de etiqueta de uma constante de texto.

[![Editor de fórmula do ER.](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)

## <a name="limitations"></a>Limitações

No momento, o editor é compatível com os seguintes navegadores da Web:

- Chrome
- Borda
- Firefox
- Opera
- Safari

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral de Relatório eletrônico (ER)](general-electronic-reporting.md)
- [Designer de fórmulas no Relatório eletrônico](general-electronic-reporting-formula-designer.md)
- [Monaco Editor](https://microsoft.github.io/monaco-editor)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
