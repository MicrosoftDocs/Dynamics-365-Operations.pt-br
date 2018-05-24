---
title: "Designer de fórmulas no relatório eletrônico"
description: "Este tópico explica como usar o designer de fórmulas no ER (Relatório Eletrônico)."
author: NickSelin
manager: AnnBe
ms.date: 11/27/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 3988c437afda3d57e56a03264d3c1588af497920
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="formula-designer-in-electronic-reporting"></a>Designer de fórmulas no Relatório eletrônico

[!include [banner](../includes/banner.md)]

Este tópico explica como usar o designer de fórmulas no ER (Relatório Eletrônico). Ao criar um formato para um documento eletrônico específico em ER, você pode usar fórmulas para transformar dados, de forma que ele atenda aos requisitos da realização e formatação desse documento. Essas fórmulas assemelham-se às fórmulas do Microsoft Excel. Vários tipos de funções são suportados nas fórmulas: texto, data e hora, matemática, lógica, informações, conversão de tipo de dados e outras (funções específicas de domínio comercial).

## <a name="formula-designer-overview"></a>Visão geral do designer de fórmulas

O relatório eletrônico (RE) suporta o designer de fórmulas. Consequentemente, no tempo de design, você pode configurar as expressões que podem ser usadas para as seguintes tarefas no momento da execução:

- Transformar dados que são recebidos de um banco de dados do Microsoft Dynamics 365 for Finance and Operations e que devem ser inseridos em um modelo de dados de ER que foi desenvolvido para ser uma fonte de dados para formatos de ER. (Por exemplo, essas transformações podem incluir a filtragem, o agrupamento e a conversão de tipo de dados).
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

## <a name="designing-er-formulas"></a>Criação de fórmulas de ER

### <a name="data-binding"></a>Associação de dados

O designer de fórmulas de ER pode ser usado para definir uma expressão que torne os dados que são recebidos das fontes de dados, de modo que os dados possam ser preenchidos no consumidor de dados no tempo de execução:

- Das fontes de dados e parâmetros de runtime do Finance and Operations para um modelo de dados de ER.
- De um modelo de dados de ER a um formato de ER
- Das fontes de dados e parâmetros de runtime do Finance and Operations para um formato de ER

A ilustração a seguir mostra o design de uma expressão desse tipo. Neste exemplo, a expressão arredonda o valor do campo **Intrastat.AmountMST** da tabela Intrastat no Finance and Operations para duas casas decimais e, em seguida, retorna o valor arredondado.

[![Associação de dados](./media/picture-expression-binding.jpg)](./media/picture-expression-binding.jpg)

A ilustração a seguir mostra como uma expressão desse tipo pode ser usada. Neste exemplo, o resultado da expressão criada é inserido no componente **Transaction.InvoicedAmount** do modelo de dados **Modelo de relatório de impostos**.

[![Associação de dados que está sendo usada](./media/picture-expression-binding2.jpg)](./media/picture-expression-binding2.jpg)

No tempo de execução, a fórmula criada, **ROUND (Intrastat.AmountMST, 2)**, arredonda o valor do campo **AmountMST** para cada registro na tabela Intrastat para duas casas decimais. Depois, insere o valor arredondado no componente **Transaction.InvoicedAmount** do modelo de dados **Relatório de imposto**.

### <a name="data-formatting"></a>Formatação de dados

O designer de fórmulas de ER pode ser usado para definir uma expressão que formata os dados que são recebidos das fontes de dados, de modo que os dados podem ser enviados como parte da criação de um documento eletrônico. Você pode ter uma formatação que deve ser aplicada como uma regra comum que deve ser reutilizada para um formato. Neste caso, você pode apresentar essa formatação uma vez na configuração do formato, como uma transformação nomeada que tem uma expressão de formatação. Essa transformação nomeada poderá, em seguida, ser vinculada a vários componentes de formato cuja saída deve ser formatada de acordo com a formatação criada.

A ilustração a seguir mostra o design de uma transformação desse tipo. Neste exemplo, a transformação de **TrimmedString** trunca os dados de entrada do tipo de dados **Sequência de caracteres** removendo espaços à direita e à esquerda. Em seguida retorna o valor truncado da sequência de caracteres.

[![Transformação](./media/picture-transformation-design.jpg)](./media/picture-transformation-design.jpg)

A ilustração a seguir mostra como uma transformação desse tipo pode ser usada. Neste exemplo, vários componentes de formato enviam o texto como saída para o documento eletrônico gerado no tempo de execução. Todos os componentes do formato referem-se à transformação **TrimmedString** por nome.

[![Transformação que está sendo usada](./media/picture-transformation-usage.jpg)](./media/picture-transformation-usage.jpg)

Quando os componentes de formato, como o componente **partyName** na ilustração precedente, referem-se à transformação **TrimmedString**, a transformação envia o texto como saída para o documento eletrônico gerado. Este texto não inclui espaços à esquerda e à direita.

Se você tiver uma formatação que precise ser aplicada individualmente, ela poderá ser apresentada como a expressão individual da associação do componente de formato específico. A ilustração a seguir mostra uma expressão desse tipo. Neste exemplo, o componente do formato **partyType** é associado à fonte de dados por meio de uma expressão que converte os dados de entrada do campo **Model.Company.RegistrationType** na fonte de dados para texto com letras maiúsculas. Em seguida, a expressão envia esse texto como saída para o documento eletrônico.

[![Aplicar formatação a um componente individual](./media/picture-binding-with-formula.jpg)](./media/picture-binding-with-formula.jpg)

### <a name="process-flow-control"></a>Controle do fluxo de processo

O designer de fórmulas de ER pode ser usado para definir expressões que controlam o fluxo do processo de geração de documentos eletrônicos. Você pode executar estas tarefas:

- Define condições que determinam quando um processo de criação do documento deve ser interrompido
- Especificar expressões que criam mensagens para o usuário sobre processos interrompidos ou enviam mensagens do log de execução sobre a continuidade do processo de geração de relatórios.
- Especificar os nomes dos documentos eletrônicos gerados e controlar as condições de sua criação.

Cada regra de controle de fluxo de processo é criada como uma validação individual. A ilustração a seguir mostra uma validação desse tipo. Aqui está uma explicação da configuração neste exemplo:

- A validação é avaliada quando o nó **INSTAT** é criado durante a geração do arquivo XML.
- Se a lista de transações está vazia, a validação interrompe o processo de execução e retorna **FALSE**.
- A validação retorna uma mensagem de erro que inclui o texto de rótulo SYS70894 do Finance and Operations no idioma preferido do usuário.

[![Validação](./media/picture-validation.jpg)](./media/picture-validation.jpg)

O designer de fórmulas de ER também pode ser usado para gerar um nome de arquivo para um documento eletrônico gerado e controlar o processo de criação de arquivos. A ilustração a seguir mostra o design de um controle de fluxo de processo desse tipo. Aqui está uma explicação da configuração neste exemplo:

- A lista de registros da fonte de dados **model.Intrastat** é dividida em lotes. Cada lote contém até 1.000 registros.
- As saídas criam um arquivo relevante que contém um arquivo no formato XML para cada lote que foi criado.
- Uma expressão retorna um nome de arquivo para gerar documentos eletrônicos, concatenando o nome do arquivo e a extensão de nome do arquivo. Dependendo do lote e de todos os lotes subsequentes, o nome do arquivo contém a ID de lote como sufixo.
- Uma expressão habilita (retornando um **TRUE**) o processo de criação de arquivo para lotes que contêm pelo menos um registro.

[![Controle do arquivo](./media/picture-file-control.jpg)](./media/picture-file-control.jpg)

### <a name="basic-syntax"></a>Sintaxe básica

As expressões de ER podem conter alguns ou todos os elementos da seguir:

- Constantes
- Operadores
- Referências
- Caminhos
- Funções

#### <a name="constants"></a>Constantes

Quando você cria expressões, você pode usar constantes numéricas e de texto (isto é, valores que não são calculados). Por exemplo, a expressão **VALUE ("100") + 20** usa a constante numérica **20** e a constante da sequência de caracteres **"100"** e retorna o valor numérico **120**. O designer da fórmula de ER suporta sequências de escape. Portanto, você pode especificar uma sequência de caracteres da expressão que deve ser tratada de maneira diferente. Por exemplo, a expressão **"Leon Tolstói ""Guerra e Paz"" Volume 1"** retorna a seguinte cadeia de texto **Leon Tolstói "Guerra e Paz" Volume 1**.

#### <a name="operators"></a>Operadores

A tabela a seguir mostra os operadores aritméticos que você pode usar para executar operações matemáticas, como adição, subtração, multiplicação e divisão.

| Operador | Significado               | Exemplo |
|----------|-----------------------|---------|
| +        | Adição              | 1+2     |
| -        | Subtração, negação | 5-2, -1 |
| \*       | Multiplicação        | 7\*8    |
| /        | Divisão              | 9/3     |

A tabela a seguir mostra os operadores de comparação que são suportados. Você pode usar esses operadores para comparar dois valores.

| Operador | Significado                  | Exemplo    |
|----------|--------------------------|------------|
| =        | Equivalente                    | X=Y        |
| &gt;     | Maior que             | X&gt;Y     |
| &lt;     | Menor que                | X&lt;Y     |
| &gt;=    | Maior que ou igual a | X&gt;=Y    |
| &lt;=    | Menor que ou igual a    | X&lt;=Y    |
| &lt;&gt; | Diferente de             | X&lt;&gt;Y |

Além disso, você pode usar um E comercial (&) como um operador de concatenação de texto. Assim, você pode adicionar, ou concatenar, uma ou mais sequências de texto em uma única parte do texto.

| Operador | Significado     | Exemplo                                             |
|----------|-------------|-----------------------------------------------------|
| &        | Concatenar | "Nada a ser impresso" & ":&nbsp;" & "nenhum registro encontrado" |

##### <a name="operator-precedence"></a>Precedência do operador

A ordem na qual as partes de uma expressão composta são avaliadas é importante. Por exemplo, o resultado da expressão **1 + 4/2** varia, dependendo de qual operação, adição ou divisão, é executada primeiro. Você pode usar parênteses para definir explicitamente como uma expressão será avaliada. Por exemplo, para indicar que a operação de adição deve ser executada primeiro, você pode alterar a expressão precedente para **(1 + 4)/2**. Se não indicar explicitamente a ordem das operações em uma expressão, a ordem será baseada na precedência padrão atribuída aos operadores suportados. A tabela a seguir mostra a precedência que está atribuída a cada operador. Os operadores que têm uma precedência maior (por exemplo, 7) são avaliados antes dos operadores que têm uma precedência menor (por exemplo, 1).

| Precedência | Operadores      | Sintaxe                                                                  |
|------------|----------------|-------------------------------------------------------------------------|
| 7          | Agrupamento       | ( … )                                                                   |
| 6          | Acesso do membro  | … . …                                                                   |
| 5          | Chamada de função  | … ( … )                                                                 |
| 4          | Multiplicativo | … \* …<br>… / …                                                         |
| 3          | Aditivo       | … + …<br>… - …                                                          |
| 2          | Comparação     | … &lt; …<br>… &lt;= …<br>… =&gt; …<br>… &gt; …<br>… = …<br>… &lt;&gt; … |
| 1          | Separação     | … , …                                                                   |

Se uma expressão tiver vários operadores consecutivos com a mesma precedência, essas operações serão avaliadas da esquerda para a direita. Por exemplo, a expressão **1 + 6 / 2 \* 3 &gt; 5** retorna **verdadeiro**. É recomendável usar parênteses para indicar explicitamente a ordem desejada das operações nas expressões, de forma que as expressões fiquem mais fáceis de ler e manter.

#### <a name="references"></a>Referências

Todas as fontes de dados do componente do ER atual que estão disponíveis durante a criação de uma expressão podem ser usadas como referências nomeadas. (O componente de ER atual pode ser um modelo ou um formato). Por exemplo, o modelo de dados de ER atual contém a fonte de dados **ReportingDate** e essa fonte de dados retorna um valor do tipo de dados **DATETIME** . Para formatar corretamente esse valor no documento gerado, você pode fazer referência à fonte de dados na expressão como **DATETIMEFORMAT (ReportingDate, "dd-MM-yyyy")**.

Todos os caracteres no nome de uma fonte de dados de referência que não representam uma letra de alfabeto devem ser precedidos por aspas simples ('). Se o nome de uma fonte de dados de referência contiver pelo menos um símbolo que não representa uma letra de alfabeto, o nome deve ser colocado entre aspas simples. (Por exemplo, estes símbolos não alfabéticos podem ser marcas de pontuação ou outros símbolos escritos.) Eis alguns exemplos:

- A fonte de dados **Data e hora de hoje** deve ser referenciada em uma expressão de ER como: **'Data e hora de hoje'**.
- O método **name()** da fonte de dados **Customers** deve ser referenciado na expressão de ER da seguinte maneira: **Customers.'name()'**.

Se os métodos de fontes de dados do Finance and Operations tiverem parâmetros, a seguinte sintaxe será usada para chamar esses métodos:

- Se o método **isLanguageRTL** da fonte de dados **System** tiver um parâmetro **EN-US** do tipo de dados **String**, esse método deve ser referenciado em uma expressão de ER como **System.'isLanguageRTL'("EN-US")**.
- Não é obrigatório o uso de aspas quando um nome de método contiver apenas símbolos alfanuméricos. Porém elas são obrigatórias para o método de uma tabela, se o nome tiver colchetes.

Quando a fonte de dados **System** é adicionada a um mapeamento de ER que se refere à classe do aplicativo **Global** do Finance and Operations, a expressão retorna o valor booliano **FALSE**. A expressão modificada **System.' isLanguageRTL'("AR")** retorna o valor booliano **TRUE**.

Você pode delimitar a maneira como os valores são passados para parâmetros desse tipo de método:

- Apenas as constantes podem ser aprovadas para os métodos deste tipo. Os valores das constantes são definidos no tempo de design.
- Somente os tipos de dados primitivos (básicos) são suportados para parâmetros deste tipo. (Os tipos de dados primitivos são inteiro, real, boolianos, sequência de caracteres, e assim por diante).

#### <a name="paths"></a>Caminhos

Quando uma expressão referencia uma fonte de dados estruturada, você pode usar a definição do caminho para selecionar um elemento específico primitivo dessa fonte de dados. Um caractere de ponto (.) é usado para separar os elementos individuais de uma fonte de dados estruturada. Por exemplo, o modelo atual de dados ER contém a fonte de dados **InvoiceTransactions** e essa origem de dados retorna uma lista de registros. A estrutura de registro **InvoiceTransactions** contém os campos **AmountDebit** e **AmountCredit** e esses campos retornam valores numéricos. Portanto, você pode criar a seguinte expressão para calcular o valor faturado: **InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit**.

#### <a name="functions"></a>Funções

A seção a seguir descreve as funções que podem ser usadas em expressões de ER. Todas as fontes de dados do contexto da expressão (modelo atual dos dados ER ou formato ER) podem ser usadas como parâmetros de funções de chamada, de acordo com a lista de argumentos das funções de chamada. As constantes também podem ser usadas como parâmetros de funções de chamada. Por exemplo, o modelo atual de dados ER contém a fonte de dados **InvoiceTransactions** e essa origem de dados retorna uma lista de registros. A estrutura de registro **InvoiceTransactions** contém os campos **AmountDebit** e **AmountCredit** e esses campos retornam valores numéricos. Portanto, para calcular o valor faturado, você pode criar a seguinte expressão que usa a função de arredondamento de ER incorporada: **ROUND (InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit, 2)**.

## <a name="supported-functions"></a>Funções com suporte

As tabelas a seguir descrevem o manuseio de dados da função que podem ser usados para criar modelos de dados de ER e relatórios de ER. A lista de funções não é fixa. Os desenvolvedores podem ampliá-la. Para ver a lista de funções que você pode usar, abra o painel de funções no designer de fórmulas de ER.

### <a name="date-and-time-functions"></a>Funções de data e de hora

| Função | Descrição | Exemplo |
|----------|-------------|---------|
| ADDDAYS (datetime, dias) | Adiciona o número especificado de dias ao valor de data/hora especificado. | **ADDDAYS (NOW(), 7)** retorna a data e a hora de sete dias no futuro. |
| DATETODATETIME (data) | Converte o valor de data especificado para um valor de data/hora. | **DATETODATETIME (CompInfo. 'getCurrentDate()')** retorna a data atual da sessão do Finance and Operations, 24 de dezembro de 2015, como **12/24/2015 12:00:00 AM**. Neste exemplo, **CompInfo** é uma fonte de dados de ER do tipo **Finance and Operations/Tabela** e se refere à tabela CompanyInfo. |
| AGORA () | Retorna a data e a hora atuais do servidor de aplicativos do Finance and Operations como um valor de data/hora. | |
| HOJE () | Retorna a data atual do servidor de aplicativos do Finance and Operations como um valor de data. | |
| NULLDATE () | Devolve um valor de dados **null**. | |
| NULLDATETIME () | Retorna um valor **nulo** de data/hora. | |
| DATETIMEFORMAT (datetime, formato) | Converte o valor de data/hora especificado em uma sequência de caracteres no formato especificado. (Para obter informações sobre os formatos suportados, consulte [padrão](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) e [personalizar](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx).) | **DATETIMEFORMAT (NOW(), "dd-MM-yyyy")** retorna a data atual do servidor de aplicativos do Finance and Operations, 24 de dezembro de 2015, como **"24-12-2015"**, com base no formato personalizado especificado. |
| DATETIMEFORMAT (datetime, formato, cultura) | Converte o valor de data/hora especificado na sequência de caráteres no formato especificado e [cultura](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx). (Para saber mais sobre os formatos compatíveis, consulte [padrão](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) e [personalizar](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx)). | **DATETIMEFORMAT (NOW(), "d", "de")** retorna a data atual do servidor de aplicativos do Finance and Operations, 24 de dezembro de 2015, como **"24.12.2015"**, com base na cultura alemã selecionada. |
| SESSIONTODAY () | Retorna a data atual da sessão do Finance and Operations como um valor de data. | |
| SESSIONNOW () | Retorna a data e a hora atuais da sessão do Finance and Operations como um valor de data/hora. | |
| DATEFORMAT (data, formato) | Retorna uma representação da sequência de caracteres da data especificada no formato especificado. | **DATEFORMAT (SESSIONTODAY (), "dd-MM-yyyy")** retorna a data atual da sessão do Finance and Operations, 24 de dezembro de 2015, como **"24-12-2015"**, com base no formato personalizado especificado. |
| DATEFORMAT (data, formato, cultura) | Converte o valor de data especificado em uma cadeia de caracteres no formato e [cultura](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx) especificados. (Para saber mais sobre os formatos compatíveis, consulte [padrão](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) e [personalizar](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx)). | **DATETIMEFORMAT (SESSIONNOW (), "d", "de")** retorna a data atual da sessão do Finance and Operations, 24 de dezembro de 2015, como **"24.12.2015"**, com base na cultura alemã selecionada. |
| DAYOFYEAR (data) | Retorna a representação do inteiro do número de dias entre 1º de janeiro e a data especificada. | **DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))** retorna **61**. **DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))** retorna **1**. |
| DAYS (data 1, data 2) | Retorne o número de dias entre a primeira e a segunda data especificada. Retorna um valor positivo quando a primeira data for posterior à segunda, retorna **0** (zero) quando a primeira data for igual à segunda ou retornar um valor negativo. | **DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS(NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))** retorna **-1**. |

### <a name="data-conversion-functions"></a>Funções de conversão de dados

| Função | descrição | Exemplo |
|----------|-------------|---------|
| DATETODATETIME (data) | Converte o valor de data especificado para um valor de data/hora. | **DATETODATETIME (CompInfo. 'getCurrentDate()')** retorna a data atual da sessão do Finance and Operations, 24 de dezembro de 2015, como **12/24/2015 12:00:00 AM**. Neste exemplo, **CompInfo** é uma fonte de dados de ER do tipo **Finance and Operations/Tabela** e se refere à tabela CompanyInfo. |
| DATEVALUE (cadeia de caracteres, formato) | Retorna uma representação de data da sequência de caracteres especificada no formato especificado. | **DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")** retorna a data 21 de dezembro de 2016 com base no formato personalizado especificado e na cultura padrão **EN-US** do aplicativo. |
| DATEVALUE (cadeia de caracteres, formato, cultura) | Retorna uma representação de data da sequência de caracteres especificada no formato e cultura especificados. | **DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")** retorna a data 21 de janeiro de 2016, com base no formato personalizado e cultura especificados. Porém, **DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")** gerará uma exceção para informar ao usuário que a sequência de caracteres especificada não é reconhecida como uma data válida. |
| DATETIMEVALUE (cadeia de caracteres, formato) | Retorna uma representação de data/hora da sequência de caracteres especificada no formato especificado. | **DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")** retorna 2:55:00 AM em 21 de dezembro de 2016, com base no formato personalizado e na cultura **EN-US** do aplicativo padrão especificados. |
| DATETIMEVALUE (cadeia de caracteres, formato, cultura) | Retorna uma representação de data/hora da sequência de caracteres especificada no formato e cultura especificados. | **DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")** retorna 2:55:00 AM em 21 de dezembro de 2016, com base no formato e cultura personalizados especificados. Porém, **DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")** gerará uma exceção para informar ao usuário que a sequência de caracteres especificada não é reconhecida como uma data/hora válida. |

### <a name="list-functions"></a>Funções de listagem

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Função</th>
<th>descrição</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>SPLIT (entrada, comprimento)</td>
<td>Divide a cadeia de caracteres de entrada especificada em subcadeias de caracteres, cada qual tem o período especificado. Devolve o resultado como uma nova lista.</td>
<td><strong>SPLIT (&quot;abcd&quot;, 3)</strong> retorna uma nova lista que consiste de dois registros que têm um campo <strong>STRING</strong>. O campo no primeiro registro contém o texto <strong>&quot;abc&quot;</strong> e o campo no segundo registro contém o texto <strong>&quot;d&quot;</strong>.</td>
</tr>
<tr class="even">
<td>SPLITLIST (lista, número)</td>
<td>Divide a lista especificada em lotes, cada qual contém o número de registros especificado. Devolve o resultado como uma nova lista de lotes que contém os seguintes elementos:
<ul>
<li>Lotes como listas normais (componente <strong>Valor</strong>)</li>
<li>O número do lote atual (componente <strong>BatchNumber</strong>)</li>
</ul></td>
<td>Na seguinte ilustração, uma origem de dados de <strong>Linha</strong> é criada como uma lista de registros de três registros. Esta lista é dividida em lotes, cada um contendo até dois registros.
<p><a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a></p>
<p>A ilustração a seguir mostra o formato de layout criado. Nesse formato de layout, as associações à fonte de dados de <strong>Linhas</strong> são criados para gerar saída no formato XML. Esta saída apresenta nós individuais para cada lote e os registros existentes nele.</p>
<p><a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a></p>
<p>A ilustração a seguir mostra o formato o resultado quando o formato criado é executado.</p>
<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a></td>
</tr>
<tr class="odd">
<td>LIST (record 1 [, record 2, …])</td>
<td>Devolve uma nova lista criada de argumentos especificados.</td>
<td><strong>LIST (model.MainData, model.OtherData)</strong> devolve um registro vazio, onde a lista de campos contém todos os campos de <strong>MainData</strong> e listas de registro <strong>OtherData</strong>.</td>
</tr>
<tr class="even">
<td>LISTJOIN (list 1, list 2, …)</td>
<td>Devolve uma lista incluída que foi criada a partir de listas de argumentos específicos.</td>
<td><strong>LISTJOIN (SPLIT (&quot;abc&quot;, 1), SPLIT (&quot;def&quot;, 1))</strong> retorna uma lista de seis registros, onde um campo do tipo de dados <strong>STRING</strong> contém apenas letras.</td>
</tr>
<tr class="odd">
<td>ISEMPTY (lista)</td>
<td>Retorna <strong>TRUE</strong> se a lista especificada não contiver elementos. Caso contrário, devolve <strong>FALSO</strong>.</td>
<td></td>
</tr>
<tr class="even">
<td>EMPTYLIST (lista)</td>
<td>Devolve uma lista em branco usando a lista especificada como uma origem da estrutura da lista.</td>
<td><strong>EMPTYLIST (SPLIT (&quot;abc&quot;, 1))</strong> retorna uma nova lista vazia que tem a mesma estrutura como a lista que é retornada pela função <strong>SPLIT</strong>.</td>
</tr>
<tr class="odd">
<td>FIRST (lista)</td>
<td>Devolva o primeiro registro da lista especificada se esse registro não estiver vazio. Caso contrário, jogue uma exceção.</td>
<td></td>
</tr>
<tr class="even">
<td>FIRSTORNULL (lista)</td>
<td>Devolva o primeiro registro da lista especificada se esse registro não estiver vazio. Caso contrário, devolve um registro <strong>null</strong>.</td>
<td></td>
</tr>
<tr class="odd">
<td>LISTOFFIRSTITEM (lista)</td>
<td>Retorna uma lista contendo apenas o primeiro item de determinada lista.</td>
<td></td>
</tr>
<tr class="even">
<td>ALLITEMS (caminho)</td>
<td>Retorna uma nova lista simplificada que representa todos os itens que correspondem ao caminho especificado. O caminho deve ser definido como um caminho de fonte de dados válido de um elemento da fonte de dados de um tipo de dados da lista de registros. Os elementos de dados, como sequência de caracteres de caminho e data devem gerar um erro no construtor de expressão de ER no tempo de design.</td>
<td>Se você inserir <strong>SPLIT(&quot;abcdef&quot; , 2)</strong> como uma origem de dados (DS), <strong>COUNT( ALLITEMS (DS.Value))</strong> retornará <strong>3</strong>.</td>
</tr>
<tr class="odd">
<td>ORDERBY (lista [, expressão 1, expressão 2, …])</td>
<td>Retorna a lista especificada depois que ela for classificada de acordo com os argumentos especificados. Esses argumentos podem ser definidos como expressões.</td>
<td>Se o <strong>Fornecedor</strong> for configurado como uma fonte de dados de ER que faça referência à tabela VendTable, <strong>ORDERBY (Vendors, Vendors.&#39;nome()&#39;)</strong> retorna uma lista de fornecedores classificada por nome na ordem crescente.</td>
</tr>
<tr class="even">
<td>REVERSE (lista)</td>
<td>Retorna a lista especificada na ordem de classificação revertida.</td>
<td>Se <strong>Fornecedor</strong> for configurado como uma origem de dados de ER que faça referência à tabela VendTable, <strong>REVERSE (ORDERBY (Vendors, Vendors.&#39;nome()&#39;)) )</strong> retorna uma lista de fornecedores classificada por nome na ordem decrescente.</td>
</tr>
<tr class="odd">
<td>WHERE (lista, condição)</td>
<td>Retorna a lista especificada depois que ela for filtrada, de acordo com a condição especificada. A condição especificada é aplicada à lista na memória. Dessa forma, a função <strong>WHERE</strong> é diferente da função <strong>FILTER</strong>.</td>
<td>Se <strong>Fornecedor</strong> for configurado como uma origem de dados de ER que se refere à tabela VendTable, <strong>WHERE(Vendors, Vendors.VendGroup = &quot;40&quot;)</strong> retorna uma lista de fornecedores que pertencem ao grupo do fornecedor 40.</td>
</tr>
<tr class="even">
<td>ENUMERATE (lista)</td>
<td>Devolve uma nova lista de registros que consistem de registros enumerados da lista especificada, e que expõem os seguintes elementos:
<ul>
<li>Lista de registros específicas como listas comuns (componente <strong>Valor</strong>)</li>
<li>O índice do registro atual (componente <strong>Número</strong>)</li>
</ul></td>
<td>Na ilustração a seguir, uma fonte de dados <strong>Enumerada</strong> é criada como uma lista enumerada de registros do fornecedor da fonte de dados <strong>Fornecedores</strong> que se refere à tabela VendTable.
<p><a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a></p>
<p>A ilustração a seguir mostra o formato. Nesse formato, as associações são criadas para gerar saída no formato XML. Esta saída apresenta fornecedores individuais como nós enumerados.</p>
<p><a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a></p>
<p>A ilustração a seguir mostra o formato o resultado quando o formato criado é executado.</p>
<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a></td>
</tr>
<tr class="odd">
<td>COUNT (lista)</td>
<td>Retorne o número de registros na lista especificada se a lista estiver vazia. Caso contrário, devolve <strong>0</strong> (zero).</td>
<td><strong>COUNT (SPLIT(&quot;abcd&quot; , 3))</strong> retorna <strong>2</strong>, porque a função <strong>SPLIT</strong> cria uma lista que consiste em dois registros.</td>
</tr>
<tr class="even">
<td>LISTOFFIELDS (caminho)</td>
<td>Retorna uma lista de registros criada a partir de um argumento de um dos seguintes tipos:
<ul>
<li>Enumeração do modelo</li>
<li>Enumeração de formato</li>
<li>Contêiner</li>
</ul>
<p>A lista que é criada consistem em registros que têm os seguintes campos:</p>
<ul>
<li>Nome</li>
<li>Rótulo</li>
<li>descrição</li>
</ul>
Em tempo de execução, os campos <strong>Rótulo</strong> e <strong>Descrição</strong> retornam valores que são baseados nas definições de idioma do formato.</td>
<td>Na ilustração a seguir, uma enumeração é apresentada em um modelo de dados.
<p><a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="Enumeration in a model" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a></p>
<p>A ilustração a seguir mostra estes detalhes:</p>
<ul>
<li>A enumeração do modelo inserida em um relatório como uma fonte de dados.</li>
<li>Uma expressão de ER usa a enumeração do modelo como um parâmetro da função <strong>LISTOFFIELDS</strong>.</li>
<li>Uma fonte de dados do tipo de lista de registro é inserido em um relatório usando a expressão de ER que é criada.</li>
</ul>
<p><a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="Format" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a></p>
<p>O exemplo a seguir mostra elementos de formato de ER que são associados à fonte de dados do tipo de lista de registro que foi criada usando a função <strong>LISTOFFIELDS</strong>.</p>
<p><a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="Format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a></p>
<p>A ilustração a seguir mostra o formato o resultado quando o formato criado é executado.</p>
<p><a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="Format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a></p>
<blockquote>[!NOTE]<br>
Com base nas configurações de idioma definidas Dos elementos de formato FILE e FOLDER pais, o texto traduzido para rótulos e descrições é inserido na saída do formato ER.</blockquote></td>
</tr>
<tr class="odd">
<td>LISTOFFIELDS (caminho, idioma)</td>
<td>Retorna uma lista de registros criada de um argumento, como uma enumeração do modelo, uma enumeração de formato ou um contêiner. A lista que é criada consistem em registros que têm os seguintes campos:
<ul>
<li>Nome</li>
<li>Rótulo</li>
<li>descrição</li>
<li>Traduzido(a)</li>
</ul>
<p>Em tempo de execução, os campos <strong>Rótulo</strong> e <strong>Descrição</strong> retornam valores que são baseados nas definições de idioma do formato e no idioma especificado. O campo <strong>Traduzido</strong> indica que o campo <strong>Rótulo</strong> foi traduzido no idioma especificado.</td>
<td>Por exemplo, use o tipo de fonte de dados <strong>Campo calculado</strong> para configurar as fontes de dados <strong>enumType_de</strong> e <strong>enumType_deCH</strong> para a enumeração do modelo de dados <strong>enumType</strong>:
<ul>
<li>enumType_de = <strong>LISTOFFIELDS</strong> (enumType, &quot;de&quot;)</li>
<li>enumType_deCH = <strong>LISTOFFIELDS</strong> (enumType, &quot;de-CH&quot;)</li>
</ul>
Nesse caso, você pode usar a seguinte expressão para obter o rótulo do valor de enumeração em alemão suíço, se esta tradução estiver disponível. Se a tradução do alemão suíço não estiver disponível, o rótulo ficará em alemão: <strong>IF (NOT (enumType_deCH.IsTranslated), enumType_de.Label, enumType_deCH.Label)</strong>.</td>
</tr>
<tr class="even">
<td>STRINGJOIN (lista, nome de campo, delimitador)</td>
<td>Retorna uma sequência de caracteres com valores concatenados do campo especificado na lista especificada. Os valores são separados pelo delimitador especificado.</td>

<td>Se você inserir <strong>SPLIT(&quot;abc&quot; , 1)</strong> como uma fonte de dados (DS), a expressão <strong>STRINGJOIN (DS, DS.Value, &quot;:&quot;)</strong> retornará <strong>&quot;a</strong><strong>:b</strong><strong>:c&quot;</strong>.</td>

</tr>
<tr class="odd">
<td>SPLITLISTBYLIMIT (lista, valor de limite, fonte de limite)</td>
<td>Divide a lista especificada em uma nova lista de sublistas e retorna o resultado no conteúdo da lista de registros. O parâmetro de valor de limite define o valor do limite para dividir a lista original. O parâmetro de fonte de limite define a etapa na qual aumenta-se a soma total. O limite não será aplicado a um único item da lista original se a origem do limite exceder o limite definido.</td>
<td>As ilustrações a seguir mostram um formato e as fontes de dados usadas para ele. 
<p><a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="Format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a></p>
<p><a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="Data sources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a></p>
<p>A ilustração a seguir mostra o resultado quando o formato é executado. Nesse caso, a saída é uma lista simples de itens de mercadoria.</p>
<p><a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="Output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a></p>
<p>Nas ilustrações a seguir, o mesmo formato foi ajustado, de forma que apresente a lista de itens de mercadoria em lotes quando um lote único deve incluir mercadorias e o peso total não deve exceder o limite de 9.</p>
<p><a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="Adjusted format" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a></p>
<p><a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="Data sources for the adjusted format" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a></p>
<p>A ilustração a seguir mostra o resultado quando o formato ajustado é executado.</p>
<p><a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="Output of the adjusted format" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a></p>
<blockquote>[!NOTE]<br>
O limite não será aplicado ao último item da lista original porque o valor (11) da origem do limite (peso) excede o limite definido (9). Use a função <strong>WHERE</strong> ou a expressão <strong>Enabled</strong> do elemento do formato correspondente para ignorar sublistas durante a geração do relatório, conforme necessário.</blockquote></td>
</tr>
<tr class="even">
<td>FILTRO (lista, condição)</td>
<td>Retorna a lista especificada depois que a consulta foi modificada para filtrar a condição especificada. Esta função difere da função <strong>WHERE</strong> porque a condição especificada é aplicada à fonte de dados do ER do tipo de <strong>Registros da tabela</strong> em nível de banco de dados. A lista e a condição podem ser definidas usando tabelas e relações.</td>
  <td>Se <strong>Fornecedor</strong> for configurado como uma fonte de dados de ER que se refere à tabela VendTable, <strong>FILTER (Vendors, Vendors.VendGroup = &quot;40&quot;)</strong> retorna uma lista de fornecedores que pertencem ao grupo do fornecedor 40. Se <strong>Fornecedor</strong> for configurado como uma fonte de dados de ER que faça referência à tabela <strong>VendTable</strong> e o <strong>parmVendorBankGroup</strong> configurado como fonte de dados de ER retorna o valor no tipo de dados da cadeia de caracteres, <strong>FILTER (Vendor.&#39;&lt;Relations&#39;.VendBankAccount, Vendor.&#39;&lt;Relations&#39;.VendBankAccount.BankGroupID = parmVendorBankGroup)</strong> retorna uma lista de contas do fornecedor que pertence a um grupo de bancos específico.</td>
</tr>
</tbody>
</table>

### <a name="logical-functions"></a>Funções lógicas

| Função | descrição | Exemplo |
|----------|-------------|---------|
| CASE (expression, option 1, result 1 \[, option 2, result 2\] … \[, default result\]) | Avalia o valor especificado da expressão com as opções alternativas especificadas. Devolve o resultado da opção que é igual ao valor da expressão. Caso contrário, retorna o resultado padrão opcional, se um resultado padrão for especificado. (O resultado padrão é o último parâmetro que não é precedido por uma opção.) | **CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")** devolve a cadeia de caracteres **"WINTER"** quando a data da sessão atual do Finance and Operations está entre outubro e dezembro. Caso contrário, retorna uma cadeia de caracteres em branco. |
| IF (condição, valor 1, valor 2) | Retorna o primeiro valor especificado quando a condição especificada é atendida. Caso contrário, retorna o segundo valor especificado. Se o valor 1 e o valor 2 são registros ou listas de registro, o resultado tem somente os campos que existem em ambas as listas. | **IF (1=2, "condição é alcançada", "condição não é alcançada")** devolve a cadeia **"condição não é alcançada"**. |
| NOT (condição) | Devolve o valor da condição lógica revertido especificado. | **NOT (TRUE)** devolve **FALSE**. |
| AND (condition 1\[, condition 2, …\]) | Devolve **TRUE** se *todas* as condições especificadas forem verdade. Caso contrário, devolve **FALSO**. | **AND (1=1, "a"="a")** devolve **TRUE**. **AND (1=2, "a"="a")** devolve **FALSE**. |
| OR (condition 1\[, condition 2, …\]) | Devolve **FALSE** se *todas* as condições especificadas forem falsas. Devolve **TRUE** se *quaisquer* condições especificadas forem verdade. | **OR (1=2, "a"="a")** devolve **TRUE**. |

### <a name="mathematical-functions"></a>Funções matemáticas

| Função | Descrição | Exemplo |
|----------|-------------|---------|
| ABS (número) | Retorna o valor absoluto do número especificado. (Em outras palavras, retorna o número sem seu sinal). | **ABS (-1)** retorna **1**. |
| POWER (número, potência) | Devolve o resultado de aumento do número positivo especificado para a potência especificada. | **POWER (10, 2)** devolve **100**. |
| NUMBERVALUE (cadeia de caracteres, separador decimal, separador de grupo de dígitos) | Converte a cadeia de caracteres especificada como um número. O separador decimal especificado é usado entre o inteiro e as partes fracionárias de um número decimal. O separador de agrupamento de dígito especificado é usado como o separador de milhares. | **NUMBERVALUE("1 234,56", ",", " ")** devolve o valor **1234.56**. |
| VALUE (cadeia de caracteres) | Converte a cadeia de caracteres especificada como um número. As vírgulas e os caracteres de ponto (.) são considerados separadores decimais, e um hífen principal (-) é usado como um sinal negativo. Lança uma exceção, se a sequência de caracteres especificada contiver outros caracteres não numéricos. | **VALUE ("1 234,56")** exibe uma exceção. |
| ROUND (número, decimais) | Retorna o número especificado depois que ele for arredondado para o número especificado de casas decimais:<ul><li>Se o valor do parâmetro de decimais for maior que 0 (zero), o número especificado é arredondado para muitas casas decimais.</li><li>Se o valor do parâmetro decimais for **0** (zero), o número especificado é arredondado para o inteiro mais próximo.</li><li>Se o valor o parâmetro decimais for menor do que 0 (zero), o número especificado é arredondado para a esquerda do ponto decimal.</li></ul> | **ROUND (1200.767, 2)** arredonda para duas casas decimais e devolve **1200.77**. **ROUND (1200.767, -3)** arredonda para o múltiplo mais próximo de 1.000 e devolve **1000**. |
| ROUNDDOWN (número, decimais) | Retorna o número especificado depois que ele for arredondado para baixo para o número especificado de casas decimais.<blockquote>[!NOTE]<br>Esta função comporta-se como <strong>ROUND</strong>, mas sempre arredonda o número especificado para baixo (para zero).</blockquote> | **ROUNDDOWN (1200.767, 2)** arredonda para baixo duas casas decimais e devolve **1200.76**. **ROUNDDOWN (1700.767, -3)** arredonda para baixo o múltiplo mais próximo de 1.000 e devolve **1000**. |
| ROUNDUP (número, decimais) | Retorna o número especificado depois que ele for arredondado para cima para o número especificado de casas decimais.<blockquote>[!NOTE]<br>Esta função comporta-se como <strong>ROUND</strong>, mas sempre arredonda o número especificado para cima (longe do zero).</blockquote> | **ROUNDUP (1200.763, 2)** arredonda para cima duas casas decimais e devolve **1200.77**. **ROUNDUP (1200.767, -3)** arredonda para cima o múltiplo mais próximo de 1.000 e devolve **2000**. |

### <a name="data-conversion-functions"></a>Funções de conversão de dados

| Função | descrição | Exemplo |
|----------|-------------|---------|
| VALUE (cadeia de caracteres) | Converte a cadeia de caracteres especificada como um número. As vírgulas e os caracteres de ponto (.) são considerados separadores decimais, e um hífen principal (-) é usado como um sinal negativo. Lança uma exceção, se a sequência de caracteres especificada contiver outros caracteres não numéricos. | **VALUE ("1 234,56")** exibe uma exceção. |
| NUMBERVALUE (cadeia de caracteres, separador decimal, separador de grupo de dígitos) | Converte a cadeia de caracteres especificada como um número. O separador decimal especificado é usado entre o inteiro e as partes fracionárias de um número decimal. O separador de agrupamento de dígito especificado é usado como o separador de milhares. | **NUMBERVALUE("1 234,56", ",", " ")** retorna **1234.56**. |
| INTVALUE (cadeia de caracteres) | Retorna uma representação de inteiro da sequência de caracteres especificada. Todas as casas decimais são truncadas. | **INTVALUE ("100.77")** retorna **100**. |
| INTVALUE (número) | Retorna uma representação de inteiro do número especificado. Todas as casas decimais são truncadas. | **INTVALUE (-100.77)** retorna **-100**. |
| INT64VALUE (cadeia de caracteres) | Retorna uma representação de int64 da sequência de caracteres especificada. Todas as casas decimais são truncadas. | **INT64VALUE ("22565422744")** retorna **22565422744**. |
| INT64VALUE (número) | Retorna uma representação de int64 do número especificado. Todas as casas decimais são truncadas. | **INT64VALUE (22565422744.00)** retorna **22565422744**. |

### <a name="record-functions"></a>Funções de registro

| Função | descrição | Exemplo |
|----------|-------------|---------|
| NULLCONTAINER (lista) | Devolve um registro **null** com a mesma estrutura que a lista de inscrição ou o registro especificado.<blockquote>[!NOTE]<br>Esta função é obsoleta. Use <strong>EMPTYRECORD</strong> em seu lugar.</blockquote> | **NULLCONTAINER (SPLIT ("abc", 1))** devolve um novo registro vazio que tem a mesma estrutura que a lista devolvida pela função **SPLIT**. |
| EMPTYRECORD (registro) | Devolve um registro **null** com a mesma estrutura que a lista de inscrição ou o registro especificado.<blockquote>[!NOTE]<br>Um registro <strong>nulo</strong> é um registro no qual todos os campos tem um valor vazio. Um valor vazio é <strong>0</strong> (zero) para número, uma sequência de caracteres vazia para sequência de caracteres e assim por diante.</blockquote> | **EMPTYRECORD (SPLIT ("abc", 1))** devolve um novo registro vazio que tem a mesma estrutura que a lista devolvida pela função **SPLIT**. |

### <a name="text-functions"></a>Funções de texto

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Função</th>
<th>descrição</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>UPPER (cadeia de caracteres)</td>
<td>Retorna a sequência de caracteres especificada depois que é convertida em letras maiúsculas.</td>
<td><strong>UPPER(&quot;Sample&quot;)</strong> retorna <strong>&quot;SAMPLE&quot;</strong>.</td>
</tr>
<tr class="even">
<td>LOWER (cadeia de caracteres)</td>
<td>Retorna a sequência de caracteres especificada depois que é convertida em letras minúsculas.</td>
<td><strong>LOWER (&quot;Sample&quot;)</strong> retorna <strong>&quot;sample&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>LEFT (cadeia e número de caracteres)</td>
<td>Retorna o número de caracteres especificado desde o início de uma cadeia de caracteres específica.</td>
<td><strong>LEFT (&quot;Sample&quot;, 3)</strong> retorna <strong>&quot;Sam&quot;</strong>.</td>
</tr>
<tr class="even">
<td>RIGHT (cadeia e número de caracteres)</td>
<td>Retorna o número de caracteres especificado desde o final de uma cadeia de caracteres específica.</td>
<td><strong>RIGHT (&quot;Sample&quot;, 3)</strong> retorna <strong>&quot;ple&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>MID (cadeia, posição de início e número de caracteres)</td>
<td>Retorna o número de caracteres especificado de caracteres de uma cadeia específica, começando em uma posição especificada.</td>
<td><strong>MID (&quot;Sample&quot;, 2, 3)</strong> retorna <strong>&quot;amp&quot;</strong>.</td>
</tr>
<tr class="even">
<td>LEN (cadeia de caracteres)</td>
<td>Retorna o número de caracteres em uma cadeia de caracteres específica.</td>
<td><strong>LEN (&quot;Sample&quot;)</strong> retorna <strong>6</strong>.</td>
</tr>
<tr class="odd">
<td>CHAR (número)</td>
<td>Retornar a cadeia de caracteres que é referida pelo número especificado por Unicode.</td>
<td><strong>CHAR (255)</strong> retorna <strong>&quot;ÿ&quot;</strong>.
<blockquote>[!NOTE]<br>
A sequência de caracteres que esta função retorna depende da codificação que foi selecionada no elemento do formato do ARQUIVO pai. Da lista de codificações suportadas, consulte <a href="https://msdn.microsoft.com/en-us/library/system.text.encoding(v=vs.110).aspx">Classe de codificação</a>.</blockquote>
</td>
</tr>
<tr class="even">
<td>CONCATENATE (cadeia de caracteres 1 [, cadeia de caracteres 2, …])</td>
<td>Retorna todas as sequências de caracteres de texto depois que forem adicionadas em uma sequência de caracteres.</td>
<td><strong>CONCATENATE (&quot;abc&quot;, &quot;def&quot;)</strong> retorna <strong>&quot;abcdef&quot;</strong>.
<blockquote>[!NOTE]<br>
A expressão <strong>&quot;abc&quot; &amp; &quot;def&quot;</strong> também retorna <strong>&quot;abcdef&quot;</strong>.</blockquote>
</td>
</tr>
<tr class="odd">
<td>TRANSLATE (cadeia de caracteres, padrão, substituição)</td>
<td>Retorna a sequência de caracteres especificada depois que todas as ocorrências dos caracteres na sequência de caracteres de padrão especificada forem substituídas pelos caracteres na posição correspondente na sequência de caracteres de substituição especificada.</td>
<td><strong>TRANSLATE (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;)</strong> substitui o padrão <strong>&quot;cd&quot;</strong> pela cadeia <strong>&quot;GH&quot;</strong> e retorna <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr class="even">
<td>REPLACE (cadeia de caracteres, padrão, substituição, sinalizador da expressão regular)</td>
<td>Quando o sinalizador da expressão regular especificado for <strong>verdadeiro</strong>, retorna a sequência de caracteres especificada depois que ela foi alterada, aplicando a expressão regular que é especificada como um argumento padrão para esta função. A expressão é usada para localizar os caracteres que devem ser substituídos. Os caracteres do argumento especificado de substituição são usados para substituir os caracteres que são encontrados. Quando o sinalizador da expressão regular é <strong>false</strong> especificado, esta função comporta-se como <strong>TRANSLATE</strong>.</td>
<td><strong>REPLACE (&quot;+1 923 456 4971&quot;, &quot;[^0-9]&quot;, &quot;&quot;, true)</strong> aplica uma expressão comum que remove todos os símbolos não numéricos, e retorna <strong>&quot;19234564971&quot;</strong>. <strong>REPLACE (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;, false)</strong> substitui o padrão <strong>&quot;cd&quot;</strong> pela cadeia <strong>&quot;GH&quot;</strong> e retorna <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>TEXT (entrada)</td>
<td>Retorna a entrada especificada depois que ela for convertida em uma sequência de caracteres de texto que é formatada de acordo com as configurações de localidade do servidor da instância atual do Finance and Operations. Para valores do tipo <strong>real</strong>, a conversão de cadeia de caracteres é limitada para duas casas decimais.</td>
<td>Se a localidade do servidor da instância do Finance and Operations for definida como <strong>EN-US</strong>, <strong>TEXT (NOW ())</strong> retorna a data da sessão atual do Finance and Operations, 17 de dezembro de 2015, como sequência de caracteres de texto <strong>&quot;12/17/2015 07:59:23 AM&quot;</strong>. <strong>TEXT (1/3)</strong> retorna <strong>&quot;0.33&quot;</strong>.</td>
</tr>
<tr class="even">
<td>FORMAT (string 1, string 2[, string 3, …])</td>
<td>Retorna a sequência de caracteres especificada depois que for formatada, substituindo todas as ocorrências de <strong>%N</strong> pelo enésimo argumento <em>n</em>. Os argumentos são cadeias de caracteres. Se o argumento não for fornecido para um parâmetro, o parâmetro será retornado como <strong>&quot;%N&quot;</strong> na cadeia de caracteres. Para valores do tipo <strong>real</strong>, a conversão de cadeia de caracteres é limitada para duas casas decimais.</td>
<td>Na ilustração a seguir, a fonte de dados <strong>PaymentModel</strong> retorna a lista de registros do cliente por meio do componente <strong>Cliente</strong> e o valor da data de processamento por meio do campo <strong>ProcessingDate</strong>.
<p><a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a></p>
<p>No formato ER que é projetado para gerar um arquivo eletrônico para clientes selecionados, <strong>PaymentModel</strong> é selecionada como uma fonte de dados e controla o fluxo do processo. Uma exceção é gerada para informar ao usuário quando um cliente selecionado for interrompido na data na qual o relatório é processado. A fórmula que é criada para este tipo de controle de processamento pode usar os seguintes recursos:</p>
<ul>
<li>Etiqueta SYS70894 do Finance and Operations, que tem o seguinte texto:
<ul>
<li><strong>Para o idioma Inglês dos EUA:</strong> &quot;Nothing to print&quot;</li>
<li><strong>Para o idioma alemão:</strong> &quot;Nichts zu drucken&quot;</li>
</ul></li>
<li>Etiqueta SYS18389 do Finance and Operations, que tem o seguinte texto:
<ul>
<li><strong>Para o idioma Inglês dos EUA:</strong> &quot;Customer %1 is stopped for %2.&quot;</li>
<li><strong>Para o idioma alemão:</strong> &quot;Debitor &#39;%1&#39; wird für %2 gesperrt.&quot;</li>
</ul></li>
</ul>
<p>Veja a fórmula que pode ser criada:</p>
<p>FORMAT (CONCATENATE (@&quot;SYS70894&quot;, &quot;. &quot;, @&quot;SYS18389&quot;), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, &quot;d&quot;))</p>
<p>Se um relatório for processado para o cliente <strong>Litware Retail</strong> em 17 de dezembro de 2015, na cultura <strong>EN-US</strong> e no idioma <strong>EN-US</strong>, esta fórmula retornará o seguinte texto, que pode ser apresentado como uma mensagem de exceção para o usuário.</p>
<p>&quot;Nada para imprimir. O cliente Litware Retail é interrompido para 17/12/2015."&quot;</p>
<p>Se o mesmo relatório for processado para o cliente <strong>Litware Retail</strong> em 17 de dezembro de 2015, na cultura <strong>DE</strong> e no idioma <strong>DE</strong>, esta fórmula retornará o seguinte texto, que usa um formato de data diferente:</p>
<p>&quot;Nichts zu drucken. Debitor &#39;Litware Retail&#39; wird für 17.12.2015 gesperrt.&quot;</p>
<blockquote>[!NOTE]<br>
A seguinte sintaxe será aplicada em fórmulas de ER para rótulos:
<ul>
<li><strong>Para etiquetas de recursos do Finance and Operations:</strong> <strong>@&quot;X&quot;</strong>, onde X é a ID da etiqueta na AOT (Árvore de Objetos de Aplicativo)</li>
<li><strong>Para as etiquetas que residem nas configurações de ER:</strong> <strong>@&quot;GER_LABEL:X&quot;</strong>, onde X é a ID da etiqueta na configuração de ER</li>
</ul></blockquote></td>
</tr>
<tr class="odd">
<td>NUMBERFORMAT (número, formato)</td>
<td>Retorna uma representação da sequência de caracteres do número especificado no formato especificado. (Para obter informações sobre os formatos suportados, consulte <a href="https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx">padrão</a> e <a href="https://msdn.microsoft.com/en-us/library/0c899ak8(v=vs.110).aspx">personalizada</a>.) O contexto que esta função é executada determina a cultura usada para formatar números.</td>
<td>Para a cultura EN-US, <strong>NUMBERFORMAT (0.45, &quot;p&quot;)</strong> retorna <strong>&quot;45.00 %&quot;</strong>. <strong>NUMBERFORMAT (10.45, &quot;#&quot;)</strong> retorna <strong>&quot;10&quot;</strong>.</td>
</tr>
<tr class="even">
<td>NUMERALSTOTEXT (número, idioma, moeda, sinalizador imprimir nome da moeda, casas decimais)</td>
<td>Retorna o número especificado depois que for soletrado (convertido) em sequência de caracteres de texto no idioma especificado. O código do idioma é opcional. Quando for definido como uma cadeia de caracteres vazia, o código do idioma do contexto em execução será utilizado. (O código do idioma do contexto em execução é definido para uma pasta ou arquivo gerado). O código de moeda também é opcional. Quando for definida como uma cadeia de caracteres vazia, a moeda da empresa será utilizada.
<blockquote>[!NOTE]<br>
O sinalizador imprimir nome da moeda e os parâmetros de pontos decimais são analisados somente para os seguintes códigos de idioma: <strong>CS</strong>, <strong>ET</strong>, <strong>HU</strong>, <strong>LT</strong>, <strong>LV</strong>, <strong>PL</strong> e <strong>RU</strong>. Além disso, o parâmetro do sinalizador de nome da moeda impressa é analisado somente para empresas do Finance and Operations nas quais o contexto de país ou região é compatível com declinações de nomes da moeda.</blockquote></td>
<td><strong>NUMERALSTOTEXT (1234.56, &quot;EN&quot;, &quot;&quot;, false, 2)</strong> retorna <strong>&quot;Mil duzentos e trinta e quatro e 56&quot;</strong>. <strong>NUMERALSTOTEXT (120, &quot;PL&quot;, &quot;&quot;, false, 0)</strong> retorna <strong>&quot;Sto dwadzieścia&quot;</strong>. <strong>NUMERALSTOTEXT (120.21, &quot;RU&quot;, &quot;EUR&quot;, true, 2)</strong> retorna <strong>&quot;Сто двадцать евро 21 евроцент&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>PADLEFT (cadeia de caracteres, comprimento, caracteres de preenchimento)</td>
<td>Retorna uma sequência de caracteres do tamanho especificado, onde o início da sequência de caracteres especificada é preenchido com os caracteres especificados.</td>
<td><strong>PADLEFT (&quot;1234&quot;, 10, &quot;&nbsp;&quot;)</strong> retorna a sequência de caracteres de texto <strong>&quot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234&quot;</strong>.</td>
</tr>
<tr class="even">
<td>TRIM (cadeia de caracteres)</td>
<td>Retorna a sequência de caracteres de texto especificada depois que os espaços à direita e à esquerda forem truncados e depois que vários espaços entre as palavras forem removidos.</td>
<td><strong>TRIM (&quot;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Texto de&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;amostra&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&quot;)</strong> retorna <strong>&quot;Texto de amostra&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>GETENUMVALUEBYNAME (caminho da fonte de dados de enumeração, texto do rótulo do valor de enumeração)</td>
<td>Retorna um valor de uma fonte de dados de enumeração especificada com base no texto especificado do rótulo de enumeração.</td>
<td>Na ilustração a seguir, a enumeração de <strong>ReportDirection</strong> é apresentada em um modelo de dados. Observe que as etiquetas são definidas por valores de enumeração.
<p><a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a></p>
<p>A ilustração a seguir mostra estes detalhes:</p>
<ul>
<li>A enumeração do modelo <strong>ReportDirection</strong> é inserida em um relatório como uma fonte de dados, <strong>$Direction</strong>.</li>
<li>Uma expressão de ER, <strong>$IsArrivals</strong>, é criada para usar a enumeração do modelo como um parâmetro desta função. O valor dessa expressão é <strong>TRUE</strong>.</li>
</ul>
<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a></td>
</tr>
</tbody>
</table>

### <a name="data-conversion-functions"></a>Funções de conversão de dados

| Função | descrição | Exemplo |
|----------|-------------|---------|
| TEXT (entrada) | Retorna a entrada especificada depois que ela for convertida em uma sequência de caracteres de texto que é formatada de acordo com as configurações de localidade do servidor da instância atual do Finance and Operations. Para valores do tipo **real**, a conversão de cadeia de caracteres é limitada para duas casas decimais. | Se a localidade do servidor da instância do Finance and Operations for definida como **EN-US**, **TEXT (NOW ())** retorna a data da sessão atual do Finance and Operations, 17 de dezembro de 2015, como a string de texto **"12/17/2015 07:59:23 AM"**. **TEXT (1/3)** devolve **"0.33"**. |
| QRCODE (cadeia de caracteres) | Retorna uma imagem de QR code no formato binário base64 para a sequência de caracteres especificada. | **QRCODE ("Texto de amostra")** retorna **U2FtcGxlIHRleHQ=**. |

### <a name="data-collection-functions"></a>Funções de coleta de dados

| Função | descrição | Exemplo |
|----------|-------------|---------|
| FORMATELEMENTNAME () | Retorna o nome do elemento do formato atual. Retorna uma sequência de caracteres vazia quando o sinalizador **Coletar detalhes de saída** dos arquivos atuais forem desativados. | Para saber mais sobre como usar esta função, consulte o guia de tarefas **ER Usar dados de saída do formato contagem e soma**, que faz parte do processo de negócios **Adquirir/Desenvolver componentes de solução/serviço de TI**. |
| SUMIFS (cadeia de caracteres chave para somar, cadeia de caracteres do critério range1, cadeia de caracteres do critério value1 \[, cadeia de caracteres do critério range2, cadeia de caracteres do critério value2, …\]) | Retorna a soma de valores de nós de XML (na qual o nome é definido como uma chave) que foi coletada durante a execução do formato e que satisfaz as condições especificadas (pares de intervalos e valores). Retorna um valor **0** (zero) quando o sinalizador **Coletar detalhes de saída** dos arquivos atuais forem desativados. | |
| SUMIF (cadeia de caracteres chave para somar, cadeia de caracteres de intervalo de critérios, cadeia de caracteres de valor de critérios) | Retorna a soma de valores de nós de XML (na qual o nome é definido como uma chave) que foi coletada durante a execução do formato e que satisfaz a condição especificada (intervalo e valor). Retorna um valor **0** (zero) quando o sinalizador **Coletar detalhes de saída** dos arquivos atuais forem desativados. | |
| COUNTIFS (cadeia de caracteres do critério range1, cadeia de caracteres do critério value1 \[, cadeia de caracteres do critério range2, cadeia de caracteres do critério value2, …\]) | Retorna o número de nós de XML que foram coletados durante a execução do formato e que satisfazem às condições especificadas (pares de intervalos e valores). Retorna um valor **0** (zero) quando o sinalizador **Coletar detalhes de saída** dos arquivos atuais forem desativados. | |
| COUNTIF (cadeia de caracteres de intervalo de critérios, cadeia de caracteres de valor de critérios) | Retorna o número de nós do XML que foram coletados durante a execução do formato e que atendem à condição inserida (intervalo e valor). Retorna um valor **0** (zero) quando o sinalizador **Coletar detalhes de saída** dos arquivos atuais forem desativados. | |
| COLLECTEDLIST (cadeia de caracteres do critério range1, cadeia de caracteres do critério value1 \[, cadeia de caracteres do critério range2, cadeia de caracteres do critério value2, …\]) | Retorna a lista de valores de nós de XML do XML que foi coletado durante a execução do formato e que satisfaz às condições inseridas (intervalo e valor). Retorna uma lista vazia quando o sinalizador **Coletar detalhes de saída** dos arquivos atuais for desativado. | |

### <a name="other-business-domainspecific-functions"></a>Outras funções (específicas de domínio comercial)

| Função | descrição | Exemplo |
|----------|-------------|---------|
| CONVERTCURRENCY (valor, moeda de origem, moeda de destino, data, empresa) | Converte o valor monetário especificado da moeda de origem especificada para a moeda de destino especificada usando as configurações da empresa especificada do Finance and Operations na data especificada. | **CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")** retorna equivalentes do euro em dólares norte-americanos na data da sessão atual, com base nas configurações da empresa de DEMF. |
| ROUNDAMOUNT (número, decimais, regra de arredondamento) | Arredonda o valor especificado para o número especificado de casas decimais, de acordo com a regra de arredondamento especificada.<blockquote>[!NOTE]<br>A regra de arredondamento deve ser especificada como um valor de enumeração <strong>RoundOffType</strong> do Finance and Operations.</blockquote> | Se o parâmetro **model.RoundOff** for definido como **Para baixo**, **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** retorna o valor **1000.78**. Se o parâmetro **model.RoundOff** é definido para **Normal** ou **Arredondar para cima**, **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** devolve o valor **1000.79**. |
| CURCredRef (dígitos) | Devolve uma referência do credor, com base nos dígitos do número da nota fiscal especificada. | **CURCredRef ("VEND-200002")** retorna **"2200002"**. |
| MOD\_97 (digits) | Devolve uma referência do credor como uma expressão de MOD97, com base nos dígitos do número da nota fiscal especificada. | **MOD\_97 ("VEND-200002")** retorna **"20000285"**. |
| ISOCredRef (dígitos) | Retorna uma referência do credor de ISO (Organização Internacional de Normalização), com base nos dígitos e símbolos alfabéticos do número da fatura especificada.<blockquote>[!NOTE]<br>Para eliminar símbolos de alfabetos que não são compatíveis com ISO, o parâmetro de entrada deve ser traduzido antes de ser passado para esta função.</blockquote> | **ISOCredRef ("VEND-200002")** retorna **"RF23VEND-200002"**. |
| CN\_GBT\_AdditionalDimensionID (cadeia de caracteres, número) | Obtenha a ID da dimensão financeira adicional. As dimensões são representadas nesta sequência de caracteres como IDs que são separadas por vírgulas. Nesta string, os números definem o código de sequência da dimensão solicitada. | **CN\_GBT\_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH",3)** retorna **"CC"**. |
| GetCurrentCompany () | Retorna a representação de texto do código para a entidade legal (empresa) à qual um usuário está conectado no momento. | **GETCURRENTCOMPANY ()** retorna **USMF** para um usuário que está conectado à empresa **Contoso Entertainment System USA** no Finance and Operations. |
| CH\_BANK\_MOD\_10 (dígitos) | Retorna uma referência do credor como uma expressão MOD10, com base nos dígitos do número da fatura especificada. | **CH\_BANK\_MOD\_10 ("VEND-200002")** retorna **3**. |
| FA\_SUM (código do ativo fixo, código de modelo de depreciação, data inicial, data final) | Retorna o contêiner de dados preparados do valor do ativo fixo para o período especificado. | **FA\_SUM ("COMP-000001", "Current", Date1, Date2)** retorna o contêiner de dados preparado do ativo fixo **"COMP-000001"** que tem o modelo do valor **"Atual"** para um período de **Data1** para **Data2**. |
| FA\_BALANCE (código do ativo fixo, código de modelo de depreciação, ano do relatório, data do relatório) | Retorna o contêiner de dados preparados do saldo do ativo fixo. O ano do relatório deve ser especificado como um valor de enumeração **AssetYear** no Finance and Operations. | **FA\_SUM ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())** retorna o contêiner de dados preparado dos saldos para o ativo fixo **"COMP-000001"** que tem o modelo de valor **"Atual"** na data da sessão atual do Finance and Operations. |
| TABLENAME2ID (cadeia de caracteres) | Retorna uma representação de inteiro de uma ID de tabela para o nome da tabela especificada. | **TABLENAME2ID ("Intrastat")** retorna **1510**. |
| ISVALIDCHARACTERISO7064 (cadeia de caracteres) | Retorna o valor booliano **TRUE** quando a sequência de caracteres especificada representa um IBAN (número de conta de banco internacional) válido. Caso contrario, retorna um valor booliano **FALSE**. | **ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")** retorna **TRUE**. **ISVALIDCHARACTERISO7064 ("AT61")** retorna **FALSE**. |

### <a name="functions-list-extension"></a>Extensão da lista de funções

ER deixa você estender a lista de funções que são usadas em expressões ER. Isso exige alguns esforços de engenharia. Para informações detalhadas, consulte [Estender a lista de funções do relatório eletrônico](general-electronic-reporting-formulas-list-extension.md).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do Relatório Eletrônico](general-electronic-reporting.md)

[Estender a lista de funções do ER (Relatório eletrônico)](general-electronic-reporting-formulas-list-extension.md)

