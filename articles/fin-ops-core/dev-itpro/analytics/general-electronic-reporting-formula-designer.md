---
title: Designer de fórmulas no relatório eletrônico (ER)
description: Este tópico fornece informações sobre como usar o designer de fórmulas no relatório eletrônico (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0028d1f64aced1bbff91b18456c81adbb95bce30
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914809"
---
# <a name="formula-designer-in-electronic-reporting-er"></a>Designer de fórmulas no relatório eletrônico (ER)

[!include [banner](../includes/banner.md)]

Este tópico explica como usar o designer de fórmulas no ER (Relatório Eletrônico). Ao criar um formato para um documento eletrônico específico em ER, você pode usar fórmulas para transformar dados, de forma que ele atenda aos requisitos da realização e formatação desse documento. Essas fórmulas assemelham-se às fórmulas do Microsoft Excel. Vários tipos de funções têm suporte nas fórmulas: texto, data e hora, matemática, lógica, informações, além de funções de conversão de tipo de dados, entre outras, como funções específicas de domínio comercial.

## <a name="formula-designer-overview"></a>Visão geral do designer de fórmulas

O relatório eletrônico (RE) suporta o designer de fórmulas. Consequentemente, no tempo de design, você pode configurar as expressões que podem ser usadas para as seguintes tarefas no momento da execução:

- Transformar os dados que são recebidos de um banco de dados de aplicativo e que devem ser inseridos em um modelo de dados de ER criado para ser uma fonte de dados para formatos de ER. (Por exemplo, essas transformações podem incluir a filtragem, o agrupamento e a conversão de tipo de dados).
- Formatar os dados que devem ser enviados para gerar um documento eletrônico, de acordo com o layout e as condições de um formato de ER específico. (Por exemplo, a formatação pode ser feita de acordo com o idioma ou cultura solicitados, ou a codificação).
- Controlar o processo de criar documentos eletrônicos. (Por exemplo, as expressões pode habilitar ou desabilitar a saída de elementos específicos do formato de dados, dependendo dos dados de processamento. Também pode interromper o processo de criação do documento ou enviar mensagens para os usuários.)

Você pode abrir a página **Designer de fórmulas** quando executar qualquer uma das seguintes ações:

- Associar itens da fonte de dados a componentes do modelo de dados.
- Associar itens da fonte de dados a componentes do formato.
- Concluir a manutenção dos campos calculados que fazem parte das fontes de dados.
- Definir as condições de visibilidade dos parâmetros de entrada de usuário.
- Criar as transformações de um formato.
- Definir as condições de habilitação dos componentes do formato.
- Definir os nomes de arquivo para os componentes do ARQUIVO do formato.
- Definir as condições para as validações do controle de processo.
- Definir o texto da mensagem para as validações do controle de processo.

## <a name="Binding">Associação de dados</a>

O designer de fórmulas de ER pode ser usado para definir uma expressão que transforme os dados recebidos das fontes de dados, de modo que eles possam ser inseridos no consumidor de dados das seguintes maneiras no tempo de execução:

- Das fontes de dados do aplicativo e parâmetros em tempo de execução para um modelo de dados de ER
- De um modelo de dados de ER a um formato de ER
- Das fontes de dados do aplicativo e parâmetros em tempo de execução para um formato de ER

A ilustração a seguir mostra o design de uma expressão desse tipo. Neste exemplo, a expressão arredonda o valor do campo **Intrastat.AmountMST** na tabela Intrastat para duas casas decimais e, em seguida, retorna o valor arredondado.

[![Expressão de associação de dados](./media/picture-expression-binding.jpg)](./media/picture-expression-binding.jpg)

A ilustração a seguir mostra como uma expressão desse tipo pode ser usada. Neste exemplo, o resultado da expressão criada é inserido no componente **Transaction.InvoicedAmount** do modelo de dados **Modelo de relatório de impostos**.

[![Expressão de associação de dados que está sendo usada](./media/picture-expression-binding2.jpg)](./media/picture-expression-binding2.jpg)

No tempo de execução, a fórmula criada, `ROUND (Intrastat.AmountMST, 2)`, arredonda o valor do campo **AmountMST** de cada registro na tabela Intrastat para duas casas decimais. Depois, insere o valor arredondado no componente **Transaction.InvoicedAmount** do modelo de dados **Relatório de imposto**.

## <a name="Transformation">Formatação de dados</a>

O designer de fórmulas de ER pode ser usado para definir uma expressão que formata os dados que são recebidos das fontes de dados, de modo que os dados podem ser enviados como parte da criação de um documento eletrônico. Você pode ter uma formatação que deve ser aplicada como uma regra comum que deve ser reutilizada para um formato. Neste caso, você pode apresentar essa formatação uma vez na configuração do formato, como uma transformação nomeada que tem uma expressão de formatação. Essa transformação nomeada poderá, em seguida, ser vinculada a vários componentes de formato cuja saída deve ser formatada de acordo com a expressão formatada criada.

A ilustração a seguir mostra o design de uma transformação desse tipo. Neste exemplo, a transformação de **TrimmedString** trunca os dados de entrada do tipo de dados *Sequência de caracteres* removendo espaços à direita e à esquerda. Em seguida, ela retorna o valor truncado da sequência de caracteres.

[![Transformação](./media/picture-transformation-design.jpg)](./media/picture-transformation-design.jpg)

A ilustração a seguir mostra como uma transformação desse tipo pode ser usada. Neste exemplo, vários componentes de formato enviam o texto como saída para o documento eletrônico gerado no tempo de execução. Todos os componentes do formato referem-se à transformação **TrimmedString** por nome.

[![Transformação que está sendo usada](./media/picture-transformation-usage.jpg)](./media/picture-transformation-usage.jpg)

Quando os componentes de formato, como o componente **partyName** na ilustração precedente, referem-se à transformação **TrimmedString**, a transformação envia o texto como saída para o documento eletrônico gerado. Este texto não inclui espaços à esquerda e à direita.

Se você tiver uma formatação que precise ser aplicada individualmente, ela poderá ser apresentada como a expressão individual da associação do componente de formato específico. A ilustração a seguir mostra uma expressão desse tipo. Neste exemplo, o componente do formato **partyType** é associado à fonte de dados por meio de uma expressão que converte os dados de entrada do campo **Model.Company.RegistrationType** na fonte de dados para texto com letras maiúsculas. Em seguida, a expressão envia esse texto como saída para o documento eletrônico.

[![Aplicar formatação a um componente individual](./media/picture-binding-with-formula.jpg)](./media/picture-binding-with-formula.jpg)

## <a name="Validation">Controle do fluxo de processo</a>

O designer de fórmulas de ER pode ser usado para definir expressões que controlam o fluxo do processo de geração de documentos eletrônicos. Você pode executar estas tarefas:

- Define condições que determinam quando um processo de criação do documento deve ser interrompido
- Especificar expressões que criam mensagens para o usuário sobre processos interrompidos ou enviam mensagens do log de execução sobre a continuidade do processo de geração de relatórios.
- Especificar os nomes dos documentos eletrônicos gerados e controlar as condições de sua criação.

Cada regra de controle de fluxo de processo é criada como uma validação individual. A ilustração a seguir mostra uma validação desse tipo. Aqui está uma explicação da configuração neste exemplo:

- A validação é avaliada quando o nó **INSTAT** é criado durante a geração do arquivo XML.
- Se a lista de transações está vazia, a validação interrompe o processo de execução e retorna **FALSE**.
- A validação retorna uma mensagem de erro que inclui o texto de rótulo SYS70894 no idioma preferido do usuário.

[![Validação](./media/picture-validation.jpg)](./media/picture-validation.jpg)

O designer de fórmulas de ER também pode ser usado para gerar um nome de arquivo para um documento eletrônico gerado e controlar o processo de criação de arquivos. A ilustração a seguir mostra o design de um controle de fluxo de processo desse tipo. Aqui está uma explicação da configuração neste exemplo:

- A lista de registros da fonte de dados **model.Intrastat** é dividida em lotes. Cada lote contém até 1.000 registros.
- As saídas criam um arquivo relevante que contém um arquivo no formato XML para cada lote que foi criado.
- Uma expressão retorna um nome de arquivo para gerar documentos eletrônicos, concatenando o nome do arquivo e a extensão de nome do arquivo. Dependendo do lote e de todos os lotes subsequentes, o nome do arquivo contém a ID de lote como sufixo.
- Uma expressão habilita (retornando um **TRUE**) o processo de criação de arquivo para lotes que contêm pelo menos um registro.

[![Controle do fluxo de processo](./media/picture-file-control.jpg)](./media/picture-file-control.jpg)

## <a name="Enabled">Controle de conteúdo de documentos</a>

O designer de fórmulas de ER pode ser usado para configurar expressões que controlam quais dados serão inseridos nos documentos eletrônicos gerados no tempo de execução. As expressões podem habilitar ou desabilitar a saída de elementos específicos do formato de dados, dependendo dos dados de processamento e da lógica configurada. Essas expressões podem ser inseridas para um único elemento de formato no campo **Habilitado** na guia **Mapeamento** da página **Designer de operações**. Você pode inserir as expressões como uma condição lógica que retorna um valor *Booliano*:

- Se a condição retornar **Verdadeiro**, o elemento de formato atual será executado.
- Se a condição retornar **Falso**, o elemento de formato atual será ignorado.

A ilustração a seguir mostra expressões desse tipo. (A versão 11.12.11 da configuração de formato **Transferência de crédito ISO20022 (NO)** que é fornecida pela Microsoft é usada como exemplo.) O componente de formato **XMLHeader** foi configurado para descrever a estrutura da mensagem de transferência de crédito de acordo com os padrões de mensagens XML ISO 20022. O componente de formato **XMLHeader/Document/CstmrCdtTrfInitn/PmtInf/CdtTrfTxInf/RmtInf/Ustrd** foi configurado para adicionar o elemento XML **Ustrd** à mensagem gerada e colocar as informações de remessa em um formato não estruturado como texto dos seguintes elementos XML:

- O componente **PaymentNotes** é usado para gerar o texto das notas de pagamento.
- O componente **DelimitedSequence** gera números de fatura separados por vírgula que são usados para liquidar a transferência de crédito atual.

[![Componentes PaymentNotes e DelimitedSequence](./media/GER-FormulaEditor-ControlContent-1.png)](./media/GER-FormulaEditor-ControlContent-1.png)

> [!NOTE]
> Os componentes **PaymentNotes** e **DelimitedSequence** são rotulados com um ponto de interrogação. Um ponto de interrogação indica que o uso de um componente é condicional. Nesse caso, o uso dos componentes se baseia nos seguintes critérios:
>
> - A expressão `@.PaymentsNotes <> ""` definida para o componente **PaymentNotes** permite (retornando **TRUE**) que o elemento XML **Ustrd** seja preenchido com o texto das notas de pagamento, se esse texto não estiver em branco para a transferência de crédito atual.
>
>    [![Expressão para o componente PaymentNotes](./media/GER-FormulaEditor-ControlContent-2.png)](./media/GER-FormulaEditor-ControlContent-2.png)
>
> - A expressão `@.PaymentsNotes = ""` definida para o componente **DelimitedSequence** permite (retornando **TRUE**) que o elemento XML **Ustrd** seja preenchido com uma lista separada por vírgula dos números de fatura usados para liquidar a transferência de crédito atual, se o texto das notas de pagamento dessa transferência de crédito estiver em branco.
>
>    [![Expressão para o componente DelimitedSequence](./media/GER-FormulaEditor-ControlContent-3.png)](./media/GER-FormulaEditor-ControlContent-3.png)
> 
> Com base nessa configuração, a mensagem gerada para cada pagamento de devedor, o elemento XML **Ustrd**, conterá o texto das notas de pagamento ou, quando esse texto estiver em branco, uma lista separada por vírgula dos números de fatura que são usados para liquidar o pagamento.

## <a name="TestFormula">Validação de fórmulas configuradas</a>

Na página **Designer de fórmulas**, selecione **Testar** para validar como a fórmula configurada funciona.

[![Selecionar Testar para validar uma fórmula](./media/ER-FormulaTest-Start.png)](./media/ER-FormulaTest-Start.png)

Quando os valores dos argumentos da fórmula forem necessários, você poderá abrir a caixa de diálogo **Testar expressão** na página **Designer de fórmulas**. Na maioria dos casos, esses argumentos devem ser definidos manualmente, porque as associações configuradas não são executadas no momento do design. A guia **Resultado do teste** na página **Designer de fórmulas** mostra o resultado da execução da fórmula configurada.

O exemplo a seguir mostra como você pode testar a fórmula configurada para o domínio de comércio exterior a fim de garantir que o código de mercadoria Intrastat contenha apenas dígitos.

Ao testar essa fórmula, você pode usar a caixa de diálogo **Testar expressão** para especificar o valor do código de mercadoria Intrastat para teste.

[![Especificar o código de mercadoria Intrastat para teste](./media/ER-FormulaTest-Start-EnterArguments.png)](./media/ER-FormulaTest-Start-EnterArguments.png)

Depois que você especificar o código de mercadoria Intrastat e selecionar **OK**, a guia **Resultado do teste** na página **Designer de fórmulas** mostrará o resultado da execução da fórmula configurada. Em seguida, você poderá avaliar se o resultado é aceitável. Se o resultado não for aceitável, você poderá atualizar a fórmula e testá-la novamente.

[![Resultado do teste](./media/ER-FormulaTest-Result.png)](./media/ER-FormulaTest-Result.png)

Algumas fórmulas não podem ser testadas no momento do design. Por exemplo, uma fórmula pode retornar um resultado de um tipo de dados que não pode ser exibido na guia **Resultado do teste**. Neste caso, você receberá uma mensagem de erro informando que a fórmula não pode ser testada.

[![Mensagem de erro](./media/ER-FormulaTest-Error.png)](./media/ER-FormulaTest-Error.png)

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral do Relatório Eletrônico](general-electronic-reporting.md)
- [Linguagem da fórmula de relatório eletrônico](er-formula-language.md)
