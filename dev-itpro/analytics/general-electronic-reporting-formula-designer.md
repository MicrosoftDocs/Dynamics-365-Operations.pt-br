---
title: "Designer de fórmulas no relatório eletrônico"
description: "Este tópico explica como usar o designer de fórmulas no ER (Relatório Eletrônico). Quando você cria um formato para um documento eletrônico específico em ER, você pode usar o Microsoft Excel (como fórmulas para a transformação de dados) que atende aos requisitos da realização e a formatação desse documento. Os vários tipos de funções são suportados: texto, a data e hora, lógica matemática, informações, conversão de tipo de dados, e outras (funções específicas de domínio comercial)."
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 298ac47e2253f8add1aa3938dda15afe186afbeb
ms.openlocfilehash: 655a6fd99c0688b13c31c79f3322a287f902e7f1
ms.contentlocale: pt-br
ms.lasthandoff: 06/20/2017


---

# <a name="formula-designer-in-electronic-reporting"></a>Designer de fórmulas no relatório eletrônico

[!include[banner](../includes/banner.md)]


Este tópico explica como usar o designer de fórmulas no ER (Relatório Eletrônico). Quando você cria um formato para um documento eletrônico específico em ER, você pode usar o Microsoft Excel (como fórmulas para a transformação de dados) que atende aos requisitos da realização e a formatação desse documento. Os vários tipos de funções são suportados - texto, data e hora, lógica, matemática, informações, conversão de tipo de dados, e outras (funções específicas de domínio comercial).

<a name="formula-designer-overview"></a>Visão geral do designer de fórmulas
-------------------------

O relatório eletrônico (RE) suporta o designer de fórmulas. Consequentemente, no momento da criação, você pode configurar as expressões que podem ser usadas para as seguintes tarefas no momento da execução:

-   Transformar dados que são recebidos do banco de dados do Microsoft Dynamics 365 for Finance and Operations e que devem ser preenchidos em um modelo de dados ER que foi desenvolvido para ser uma fonte de dados para formatos ER (filtragem, agrupamento, conversão de tipos de dados etc.).
-   Formatar dados que devem ser enviados para gerar um documento eletrônico de acordo com o layout e as condições de um formato ER específico (de acordo com o idioma ou a cultura solicitada, a codificação etc.).
-   Controlar o processo de geração de documentos eletrônicos (habilitar/desabilitar a saída de elementos específicos do formato, dependendo do processamento de dados, da interrupção na criação de documentos, do envio de mensagens a usuários finais etc.).

A página do designer de fórmulas pode ser aberta quando você fizer o seguinte:

-   Associar itens da fonte de dados a componentes do modelo de dados.
-   Associar itens da fonte de dados a componentes do formato.
-   Concluir a manutenção dos campos calculados como parte das fontes de dados.
-   Definir as condições de visibilidade dos parâmetros de entrada de usuário.
-   Criar as transformações de um formato.
-   Definir as condições de habilitação dos componentes do formato.
-   Definir os nomes de arquivo para os componentes do ARQUIVO do formato.
-   Definir as condições para as validações do controle de processo.
-   Definir o texto da mensagem para as validações do controle de processo.

## <a name="designing-er-formulas"></a>Criação de fórmulas de ER
### <a name="data-binding"></a>Associação de dados

O designer de fórmulas de ER pode ser usado para definir uma expressão que torne os dados que são recebidos das fontes de dados, de modo que os dados podem ser preenchidos no consumidor de dados em tempo de execução:

-   Das fontes de dados do Finance and Operations e parâmetros em tempo de execução para o modelo de dados ER.
-   De um modelo de dados ER para um formato ER.
-   Das fontes de dados do Finance and Operations e parâmetros em tempo de execução para o formato ER.

A ilustração a seguir mostra o design de uma expressão desse tipo. Neste exemplo, a expressão retorna o valor do campo **Intrastat.AmountMST** da tabela **Intrastat** do Finance and Operations, após o valor ter sido arredondado para duas casas decimais. [![picture-expression-binding](./media/picture-expression-binding.jpg)](./media/picture-expression-binding.jpg) A ilustração a seguir mostra como uma expressão deste tipo pode ser usada. Neste exemplo, o resultado da expressão criada é preenchido no componente **Transaction.InvoicedAmount** do modelo de dados **Modelo de relatório de impostos**. [![picture-expression-binding2](./media/picture-expression-binding2.jpg)](./media/picture-expression-binding2.jpg) No momento da execução, a fórmula criada, **ROUND (Intrastat.AmountMST, 2)**, arredondará o valor do campo **AmountMST** para cada registro da tabela **Intrastat** para duas casas decimais, e preencherá o valor arredondado para o componente **Transaction.InvoicedAmount** do modelo de dados **Relatório de imposto**.

### <a name="data-formatting"></a>Formatação de dados

O designer de fórmulas de ER pode ser usado para definir uma expressão que formata os dados que são recebidos das fontes de dados, de modo que os dados podem ser enviados como parte da criação de um documento eletrônico. Se você tem a formatação que deve ser aplicada como uma regra típica que será reutilizada para um formato, você pode apresentar formatando uma vez em uma configuração de formato como uma transformação nomeada que tenha uma expressão de formatação. Essa transformação nomeada poderá depois ser vinculada a vários componentes de formato cuja saída deve ser formatada de acordo com a expressão criada. A ilustração a seguir mostra o design de uma transformação desse tipo. Neste exemplo, a transformação de **TrimmedString** leva dados de entrada do tipo de dados **Cadeia de caracteres**, e trunca espaços em excesso quando devolve o valor da cadeia de caracteres. [![picture-transformation-design](./media/picture-transformation-design.jpg)](./media/picture-transformation-design.jpg) A ilustração a seguir mostra como uma transformação desse tipo pode ser usada. Neste exemplo, vários componentes do formato que enviam o texto como as saídas para a geração de documento eletrônico no momento de execução se referem a transformação de **TrimmedString** por nome. [![picture-transformation-usage](./media/picture-transformation-usage.jpg)](./media/picture-transformation-usage.jpg) Quando os componentes do formato se referem à transformação **TrimmedString ** (por exemplo, o componente **partyName** na ilustração anterior), o texto é enviado como saída para o documento gerado. O texto não inclui espaços à esquerda e à direita. Se você tiver uma formatação que precise ser aplicada individualmente, ela poderá ser apresentada como a expressão individual da associação do componente de formato específico. A ilustração a seguir mostra uma expressão desse tipo. Neste exemplo, o componente do formato **partyType** é associado à fonte de dados por meio de uma expressão que converte os dados de entrada do campo **Model.Company.RegistrationType** na fonte de dados em texto maiúscula e a envia como SMS de saída no documento eletrônico. [![picture-binding-with-formula](./media/picture-binding-with-formula.jpg)](./media/picture-binding-with-formula.jpg)

### <a name="process-flow-control"></a>Controle do fluxo de processo

O designer de fórmulas de ER pode ser usado para definir expressões que controlam o fluxo do processo de geração de documentos. Você pode:

-   Define condições que determinam quando um processo de criação do documento deve ser interrompido
-   Especificar expressões que criarão mensagens para o usuário final sobre processos interrompidos ou enviarão mensagens do log de execução sobre a continuidade do processo de geração de relatórios.
-   Especifique os nomes dos arquivos para gerar documentos, e condições de controle de sua criação.

Cada regra de controle de fluxo de processo é criada como uma validação individual. A ilustração a seguir mostra uma validação desse tipo. Aqui está uma explicação da configuração neste exemplo:

-   A validação é avaliada quando o nó **INSTAT** é criado no arquivo XML de geração.
-   Se a lista de transações está vazia, a validação interrompe o processo de execução e retorna **FALSE**.
-   A validação retorna uma mensagem de erro que inclui o texto de rótulo SYS70894 no idioma preferido do usuário.

[![picture-validation](./media/picture-validation.jpg)](./media/picture-validation.jpg) O designer de fórmulas de ER também pode ser usado para especificar um nome de arquivo para um documento eletrônico gerado e controlar o processo de criação de arquivos. A ilustração a seguir mostra o design de um controle de fluxo de processo desse tipo. Aqui está uma explicação da configuração neste exemplo:

-   A lista de registros da fonte de dados **model.Intrastat** é dividida por lotes que contêm até 1.000 registros
-   As saídas criam um arquivo relevante que contém um arquivo no formato XML para cada lote que foi criado.
-   Uma expressão retorna um nome de arquivo para gerar documentos eletrônicos concatenando o nome do arquivo e a extensão do arquivo. Dependendo do lote e de todos os lotes subsequentes, o nome do arquivo contém a ID de lote como sufixo.
-   Uma expressão habilita (retornando um **TRUE**) o processo de uma criação de arquivo para os únicos lotes que contêm pelo menos um registro.

[![picture-file-control](./media/picture-file-control.jpg)](./media/picture-file-control.jpg)

### <a name="basic-syntax"></a>Sintaxe básica

As expressões de ER podem conter alguns ou todos os elementos da seguir:

-   Constantes
-   Operadores
-   Referências
-   Caminhos
-   Funções

#### <a name="constants"></a>Constantes

As constantes de texto e numéricas (valores que não são calculados) podem ser usadas na criação de expressões. Por exemplo, a expressão **VALUE ("100") + 20 **usa a constante numérica 20 e a constante da cadeia “100” e retorna o valor numérico **120**. O designer de fórmulas de ER oferece suporte a sequências de escape, o que significa que você pode especificar a cadeia de caracteres da expressão que deve ser tratada de forma diferente. Por exemplo, a expressão **"Leon Tolstói ""Guerra e Paz"" Volume 1"** retorna a seguinte cadeia de texto **Leon Tolstói "Guerra e Paz" Volume 1**.

#### <a name="operators"></a>Operadores

A tabela a seguir mostra aos operadores aritméticos o que pode ser usado para executar operações matemáticas básicas, como o acréscimo, a subtração, a divisão e a multiplicação.

| Operador | Significado              | Exemplo |
|----------|----------------------|---------|
| +        | Adição             | 1+2     |
| -        | Negação de subtração | 5-2 -1  |
| \*       | Multiplicação       | 7\*8    |
| /        | Divisão             | 9/3     |

A tabela a seguir mostra os operadores de comparação com suporte e que podem ser usados para comparar dois valores.

| Operador | Significado                  | Exemplo    |
|----------|--------------------------|------------|
| =        | Equivalente                    | X=Y        |
| &gt;     | Maior que             | X&gt;Y     |
| &lt;     | Menor que                | X&lt;Y     |
| &gt;=    | Maior que ou igual a | X&gt;=Y    |
| &lt;=    | Menor que ou igual a    | X&lt;=Y    |
| &lt;&gt; | Diferente de             | X&lt;&gt;Y |

Além disso, você pode usar um E comercial (&) como um operador de concatenação de texto para unir, ou concatenar, uma ou mais cadeias de caracteres em apenas um pedaço de texto.

| Operador | Significado     | Exemplo                                        |
|----------|-------------|------------------------------------------------|
| &        | Concatenar | "Nada a ser impresso" & ": " & "não foram encontrados registros" |

#### <a name="operator-precedence"></a>Precedência do operador

A ordem em que as partes de uma expressão composta são avaliadas é importante. Por exemplo, o resultado da expressão ** 1 + 4 / 2** é diferente, dependendo da operação de adição ou da operação de divisão que é executada primeiro. Você pode usar parênteses para definir explicitamente como uma expressão será avaliada. Por exemplo, para indicar que a operação de adição deve ser executada primeiro, você pode alterar a expressão **(1 + 4)/2** acima. Se a ordem das operações que devem ser executadas em uma expressão não for definida explicitamente, a ordem será baseada na precedência padrão atribuída aos operadores com suporte. As tabelas a seguir mostram os operadores e a precedência que está atribuída a cada um. Os operadores que têm uma precedência maior (por exemplo, 7) são avaliados antes dos operadores que têm uma precedência menor (por exemplo, 1).

| Precedência | Operadores      | Sintaxe                                                   |
|------------|----------------|----------------------------------------------------------|
| 7          | Agrupamento       | ( … )                                                    |
| 6          | Acesso do membro  | … . …                                                    |
| 5          | Chamada de função  | … ( … )                                                  |
| 4          | Multiplicativo | … \* … … / …                                             |
| 3          | Aditivo       | … + … … - …                                              |
| 2          | Comparação     | … &lt; … … &lt;= … … =&gt; … … &gt; … … = … … &lt;&gt; … |
| 1          | Separação     | … , …                                                    |

Os operadores na mesma linha têm prioridade igual. Se uma expressão incluir mais de um desses operadores, a expressão será avaliada da esquerda para a direita. Por exemplo, a expressão **1 + 6 / 2 \* 3 &gt; 5** retorna **verdadeiro**. É recomendável usar parênteses para indicar explicitamente a ordem de classificação desejada para expressões, para efetuar as expressões mais fáceis de ler e manter.

#### <a name="references"></a>Referências

Todas as fontes de dados do componente do ER atuais (um módulo ou um formato) que estão disponíveis durante o design de uma expressão podem ser usadas como referências nomeadas. Por exemplo, o modelo atual de dados ER contém a fonte de dados **ReportingDate** que retorna o valor do tipo de dados **DATETIME**. Para formatar corretamente esse valor no documento gerado, você pode fazer referência à fonte de dados da seguinte maneira: **DATETIMEFORMAT (ReportingDate, "dd-MM-yyyy")** Todos os caracteres no nome de uma fonte de dados referenciada que não representem uma letra do alfabeto devem ser precedidos por uma única aspas simples ('). Se o nome de uma fonte de dados referenciada contiver pelo menos um símbolo que não representa uma letra de alfabeto (por exemplo, marca de pontuação ou qualquer outro símbolo escrito), o nome deve ser colocado entre aspas simples. Eis alguns exemplos:

-   A fonte de dados **Data e hora de hoje** deve ser referenciada em uma expressão ER como: **'Data e hora de hoje'**
-   O método **name()** da fonte de dados **Customers** deve ser referenciado na expressão ER da seguinte maneira: **Customers.'name()'**

Observe que a seguinte sintaxe é usada para chamar métodos da fontes de dados do Dynamics 365 for Operation com parâmetros:

- O método isLanguageRTL de fonte de dados do sistema com um parâmetro EN-US do tipo de dados de cadeia de caracteres deve ser referenciado na expressão ER da seguinte maneira: Sistema.’isLanguageRTL’(“EN-US”).
- Não é obrigatório o uso de aspas quando um nome de método contém apenas símbolos alfanuméricos. Elas são obrigatórias para o método de uma tabela cujo nome inclui colchetes.

Quando a fonte de dados do Sistema é adicionada ao mapeamento de ER que se refere à classe de aplicativo Global Dynamics 365 for Operation, a expressão retorna o valor booliano FALSE. A expressão modificada, System.’ isLanguageRTL’(“AR”) retorna o valor booliano TRUE.

Observe que na passagem para esses métodos, os parâmetros podem ser definidos com as seguintes limitações:

- Apenas as constantes podem ser passadas para esses métodos, cujos valores são definidos no tempo de design.
- Somente os tipos de dados (básicos) primitivos têm suporte para esses parâmetros (inteiro, real, booliano, cadeia de caracteres, etc.).

#### <a name="path"></a>Caminho

Quando uma expressão referencia uma fonte de dados estruturada, você pode usar a definição do caminho para selecionar um elemento específico primitivo dessa fonte de dados. Um caractere de ponto (.) é usado para separar os elementos individuais de uma fonte de dados estruturada. Por exemplo, o modelo atual de dados ER contém a fonte de dados **InvoiceTransactions** que retorna a lista de registros. A estrutura de registro **InvoiceTransactions** contém os campos **AmountDebit** e **AmountCredit** que retornam valores numéricos. Uma expressão para calcular o valor faturado pode ser criada da seguinte maneira: **InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit**

#### <a name="functions"></a>Funções

A seção a seguir descreve as funções que podem ser usadas em expressões de ER. Todas as fontes de dados do contexto da expressão (modelo atual dos dados ER ou formato ER), bem como constantes podem ser usadas como parâmetros de funções de chamada de acordo com a lista de argumentos da função de chamada. Por exemplo, o modelo atual de dados ER contém a fonte de dados **InvoiceTransactions** que retorna a lista de registros. A estrutura de registro **InvoiceTransactions** contém os campos **AmountDebit** e **AmountCredit** que retornam valores numéricos. Portanto, uma expressão para calcular o valor faturado pode ser criada da seguinte maneira, usando a função interna de arredondamento de ER: **ROUND (InvoiceTransactions.AmountDebit - InvoiceTransactions.AmountCredit, 2)**

## <a name="supported-functions"></a>Funções com suporte
As tabelas a seguir descrevem o manuseio de dados da função que podem ser usados para criar modelos de dados de ER e relatórios de ER. Esta lista de funções não é fixa e pode ser estendida por desenvolvedores. Para ver a lista de funções que você pode usar, acesse o painel de funções no designer de fórmulas de ER.

### <a name="date-and-time-functions"></a>Funções de data e de hora

| Função                                   | Descrição                                                                                                                                                                                                                                                                                                                                                      | Exemplo                                                                                                                                                                                                                                                                                               |
|--------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ADDDAYS (datetime, dias)                   | Adicionar o número especificado de dias ao valor especificado datetime.                                                                                                                                                                                                                                                                                                | **ADDDAYS (NOW(), 7)** retorna a data e a hora de sete dias no futuro.                                                                                                                                                                                                                            |
| DATETODATETIME (data)                      | Converter o valor especificado para um valor datetime.                                                                                                                                                                                                                                                                                                            | **DATETODATETIME (CompInfo. 'getCurrentDate()')** retorna a data atual da sessão do Finance and Operations, 24/12/2015, como **24/12/2015 12:00:00**. Neste exemplo, **CompInfo** é uma fonte de dados de ER do tipo **Finance and Operations/Tabela** que se refere à tabela CompanyInfo. |
| AGORA ()                                     | Retorna a data e a hora atuais do servidor de aplicativos do Finance and Operations como um valor datetime.                                                                                                                                                                                                                                                             |                                                                                                                                                                                                                                                                                                       |
| HOJE ()                                   | Retorna a data atual do servidor de aplicativos do Finance and Operations como um valor de data.                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                       |
| NULLDATE ()                                | Devolve um valor de dados **null**.                                                                                                                                                                                                                                                                                                                                    |                                                                                                                                                                                                                                                                                                       |
| NULLDATETIME ()                            | Devolve um valor datetime **null**.                                                                                                                                                                                                                                                                                                                                |                                                                                                                                                                                                                                                                                                       |
| DATETIMEFORMAT (datetime, formato)          | Converte o valor especificado datetime a uma cadeia de caráteres no formato especificado. (Para obter informações sobre os formatos suportados, consulte [padrão](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) e [personalizar](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx).)                                                                        | **DATETIMEFORMAT (NOW(), "dd-MM-aaaa")** retorna a data atual do servidor de aplicativos do Finance and Operations, 12/24/2015, como **"24-12-2015"**, de acordo com o formato personalizado especificado.                                                                                                          |
| DATETIMEFORMAT (datetime, formato, cultura) | Converte o valor especificado datetime a uma cadeia de caráteres no formato especificado e [cultura](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx). (Para saber mais sobre os formatos compatíveis, consulte [padrão](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) e [personalizar](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx)). | **DATETIMEFORMAT (NOW(), "d", "de")** retorna a data atual do servidor de aplicativos do Finance and Operations, 12/24/2015, como **"24.12.2015"**, de acordo com a cultura alemã selecionada.                                                                                                             |
| SESSIONTODAY ()                            | Retorna a data atual da sessão do Dynamics 365 for Finance and Operations como um valor de data.                                                                                                                                                                                                                                                                                      |                                                                                                                                                                                                                                                                                                       |
| SESSIONNOW ()                              | Retorna a data e a hora atuais da sessão do Dynamics 365 for Finance and Operations como um valor datetime.                                                                                                                                                                                                                                                                         |                                                                                                                                                                                                                                                                                                       |
| DATEFORMAT (data, formato)                  | Retorna a representação de cadeia de caracteres de data usando o formato especificado.                                                                                                                                                                                                                                                                                                    | **DATEFORMAT (SESSIONTODAY (), "dd-MM-yyyy")** retorna a data atual da sessão do Dynamics 365 for Finance and Operations, 12/24/2015, como "**24-12-2015**", de acordo com o formato personalizado especificado.                                                                                                                      |
| DATEFORMAT (data, formato, cultura)         | Converte o valor de data especificado em uma cadeia de caracteres no formato e [cultura](https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx) especificados. (Para saber mais sobre os formatos compatíveis, consulte [padrão](https://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.110).aspx) e [personalizar](https://msdn.microsoft.com/en-us/library/8kb3ddd4(v=vs.110).aspx)).     | **DATETIMEFORMAT (SESSIONNOW (), "d", "de")** retorna a data atual da sessão do Finance and Operations, 12/24/2015, como **"24.12.2015"**, de acordo com a cultura alemã selecionada.                                                                                                                       |
| DAYOFYEAR (data)              | Retorna a representação inteira do número de dias entre 1º de janeiro e a data especificada.       | **DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))** retorna **61**.
**DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))** retorna **1**.                                                                                                                       |

**Funções de conversão de dados**

| Função                                   | descrição                                                                                                                                                                                                                                                                                                                                                      | Exemplo                                                                                                                                                                                                                                                                                               |
|--------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| DATETODATETIME (data)                 | Converter o valor especificado para um valor datetime.           | **DATETODATETIME (CompInfo. 'getCurrentDate()')** retorna a data atual da sessão do Finance and Operations, 24/12/2015, como **24/12/2015 12:00:00**. Neste exemplo, **CompInfo** é uma fonte de dados de ER do tipo **Finance and Operations/Tabela** que se refere à tabela **CompanyInfo**.                                                                                                                       |
| DATEVALUE (cadeia de caracteres, formato)              | Retorna a representação de data de uma cadeia de caracteres usando o formato especificado.       | **DATEVALUE ("21-Dez-2016", "dd-MMM-yyyy")** retorna a data 12/21/2016 de acordo com o formato personalizado especificado e a cultura **EN-US** padrão do aplicativo.                                                                                                                       |
| DATEVALUE (cadeia de caracteres, formato, cultura)              | Retorna a representação de data de uma cadeia de caracteres usando o formato e a cultura especificados       | **DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", “IT”)** retorna a data 01/21/2016 de acordo com a cultura e o formato personalizado especificados. Uma exceção será acionada para a chamada de função, **DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", “EN-US”)** informando que uma determinada cadeia de caracteres não foi reconhecida como uma data válida.                                                                                                                       |
| DATETIMEVALUE (cadeia de caracteres, formato)              | Retorna a representação de datetime de uma cadeia de caracteres usando o formato especificado.       | **DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")** retorna 2:55:00 de 21 de dezembro de 2016 de acordo com o formato personalizado especificado e a cultura **EN-US** padrão do aplicativo.                                                                                                                       |
| DATETIMEVALUE (cadeia de caracteres, formato, cultura)              | Retorna a representação de datetime de uma cadeia de caracteres usando o formato e a cultura especificados.       | **DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", “IT”)** retorna 2:55:00 de 21 de dezembro de 2016 de acordo com a cultura e o formato personalizado especificados. Uma exceção será acionada para a chamada de função, **DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", “EN-US”)** informando que uma determinada cadeia de caracteres não foi reconhecida como uma datetime válida.                                                                                                                       |
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
<td>Neste exemplo, a fonte de dados <strong>Linhas</strong> é criada como uma lista de registros de três os registros, que é dividida em lotes, cada qual contém até dois registros. <a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a> Isso mostra o layout do formato criado, em que as associações à fonte de dados <strong>Linhas</strong> são criadas para gerar saída no formato XML que apresenta nós individuais para cada lote e os registros contidos nele. <a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a> O resultado da execução do formato criado é o seguinte. <a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a></td>
</tr>
<tr class="odd">
<td>LIST (registro 1 [, registro 2, ...])</td>
<td>Devolve uma nova lista criada de argumentos especificados.</td>
<td><strong>LIST (model.MainData, model.OtherData)</strong> devolve um registro vazio, onde a lista de campos contém todos os campos de <strong>MainData</strong> e listas de registro <strong>OtherData</strong>.</td>
</tr>
<tr class="even">
<td>LISTJOIN (lista 1, lista 2, ...)</td>
<td>Devolve uma lista incluída que foi criada a partir de listas de argumentos específicos.</td>
<td><strong>LISTJOIN (SPLIT (&quot;abc&quot;, 1), SPLIT (&quot;def&quot;, 1))</strong> retorna a lista de seis registros, na qual um campo do tipo de dados <strong>STRING</strong> contém apenas letras.</td>
</tr>
<tr class="odd">
<td>ISEMPTY (lista)</td>
<td>Devolve <strong>VERDADEIRO</strong> se a lista especificada não conter quaisquer elementos. Caso contrário, devolve <strong>FALSO</strong>.</td>
<td></td>
</tr>
<tr class="even">
<td>EMPTYLIST (lista)</td>
<td>Devolve uma lista em branco usando a lista especificada como uma origem da estrutura da lista.</td>
<td><strong>EMPTYLIST (SPLIT (&quot;abc&quot;, 1))</strong> retorna uma nova lista vazia que tem a mesma estrutura que a lista retornada pela função <strong>SPLIT</strong>.</td>
</tr>
<tr class="odd">
<td>FIRST (lista)</td>
<td>Devolve o primeiro registro de lista especificada, se esse registro não estiver vazio. Caso contrário, jogue uma exceção.</td>
<td></td>
</tr>
<tr class="even">
<td>FIRSTORNULL (lista)</td>
<td>Devolve o primeiro registro de lista especificada, se esse registro não estiver vazio. Caso contrário, devolve um registro <strong>null</strong>.</td>
<td></td>
</tr>
<tr class="odd">
<td>LISTOFFIRSTITEM (lista)</td>
<td>Retorna uma lista contendo apenas o primeiro item de determinada lista.</td>
<td></td>
</tr>
<tr class="even">
<td>ALLITEMS (caminho)</td>
<td>Retorna uma nova lista simplificada que representa todos os itens que correspondem ao caminho especificado. O caminho deve ser definido como um caminho de fonte de dados válido para um elemento da fonte de dados de um tipo de dados de lista de registros. O caminho para os elementos de dados de cadeia de caracteres, data, etc. deve gerar um erro no momento da criação no Construtor de expressões de ER.</td>
<td>Se você inserir <strong>SPLIT(&quot;abcdef&quot; , 2)</strong> como uma origem de dados (DS), <strong>COUNT( ALLITEMS (DS.Value))</strong> retornará <strong>3</strong>.</td>
</tr>
<tr class="odd">
<td>ORDERBY (lista [, expressão 1, expressão 2, …])</td>
<td>Retorna a lista especificada, que é classificada de acordo com os argumentos especificados que podem ser definidos como expressões.</td>
<td>Quando <strong>Fornecedor </strong>estiver configurado como uma fonte de dados de ER que se refira a tabela VendTable,<strong>ORDERBY (Vendors, Vendors.'name()')</strong> retorna a lista de fornecedores que é classificada por nome em ordem ascendente.</td>
</tr>
<tr class="even">
<td>REVERSE (lista)</td>
<td>Retorna a lista especificada na ordem de classificação revertida.</td>
<td>Quando <strong>Fornecedor </strong>estiver configurado como uma fonte de dados de ER que se refira a tabela VendTable,<strong>REVERSE (ORDERBY (fornecedores, fornecedores. nome()')) )</strong> retorna a lista de fornecedores que é classificada por nome em ordem descendente.</td>
</tr>
<tr class="odd">
<td>WHERE (lista, condição)</td>
<td>Retorna a lista especificada, que é filtrada de acordo com a condição específica. Diferentemente da função de<strong>FILTRO</strong>, a condição especificada é aplicada à lista na memória.</td>
<td>Quando <strong>Fornecedor</strong> estiver configurado como uma fonte de dados de ER que se refira a tabela VendTable, <strong>WHERE(Vendors, Vendors.VendGroup = &quot;40&quot;)</strong> retornará a lista de fornecedores que pertence ao grupo de fornecedor 40.</td>
</tr>
<tr class="even">
<td>ENUMERATE (lista)</td>
<td>Devolve uma nova lista de registros que consistem de registros enumerados da lista especificada, e que expõem os seguintes elementos:
<ul>
<li>Lista de registros específicas como listas comuns (componente <strong>Valor</strong>)</li>
<li>O índice do registro atual (componente <strong>Número</strong>)</li>
</ul></td>
<td>No exemplo a seguir, a fonte de dados <strong>Enumerada</strong> é criada como uma lista enumerada dos registros do fornecedor da fonte de dados <strong>Fornecedores</strong> que refere-se a tabela <strong>VendTable</strong>. <a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a>Aqui está o formato, em que as associações são criadas para gerar saída no formato XML que apresenta fornecedores individuais como nós enumerados. <a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a> O resultado da execução do formato criado é este: <a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a></td>
</tr>
<tr class="odd">
<td>COUNT (lista)</td>
<td>Devolve o número de registros de lista especificada, se a lista estiver vazia. Caso contrário, devolve <strong>0</strong> (zero).</td>
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
A lista criada consistirá em registros com os seguintes campos:
<ul>
<li>Nome</li>
<li>Etiqueta</li>
<li>descrição</li>
</ul>
Os campos Etiqueta e Descrição retornarão valores no tempo de execução com base nas configurações do idioma do formato.</td>
<td>O exemplo a seguir mostra a enumeração apresentada em um modelo de dados. <a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="GER LISTOFFIELDS function - model enumeration" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a>Considere o exemplo a seguir:
<ul>
<li>A enumeração do modelo inserida em um relatório como uma fonte de dados.</li>
<li>A expressão ER criada para usar a enumeração do modelo como o parâmetro dessa função.</li>
<li>A fonte de dados do tipo lista de registros inserida em um relatório usando a expressão de ER criada.</li>
</ul>
<a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="GER LISTOFFIELDS function - in format expression" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a> O exemplo a seguir mostra os elementos do formato ER que estão associados à fonte de dados do tipo lista de registros criada usando a função LISTOFFIELDS.<a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="GER LISTOFFIELDS function - format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a>Este é o resultado da execução do formato criado.<a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="GER LISTOFFIELDS function - format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a><strong>Observação:</strong> o texto traduzido das etiquetas e descrições é preenchido no formato ER de saída de acordo com as configurações de idioma definidas para os elementos do formato do ARQUIVO e da PASTA pai.</td>
</tr>
<tr class="odd">
<td>STRINGJOIN (lista, nome de campo, delimitador)</td>
<td>Retorna a cadeia de caracteres de valores concatenados de um campo a partir de uma lista separada com um delimitador selecionado.</td>
<td>Se você inseriu a SPLIT("abc", 1) como uma fonte de dados DS, a expressão STRINGJOIN (DS, DS.Value, ":") retorna "a:b:c"</td>
</tr>
<tr class="even">
<td>SPLITLISTBYLIMIT (lista, valor de limite, fonte de limite)</td>
<td>Divide a lista fornecida em uma nova lista de sublistas e retorna o resultado no conteúdo da lista de registros. O parâmetro de valor de limite especifica o valor do limite para dividir a lista de origem. O parâmetro de fonte de limite especifica a etapa na qual aumenta-se a soma total. O limite não é aplicado a um único item da lista fornecida quando a fonte do limite excede o limite definido.</td>
<td>O exemplo a seguir mostra o formato de exemplo usando fontes de dados. <a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="GER SPLITLISTBYLIMIT - format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a><a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="GER SPLITLISTBYLIMIT - datasources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a>Este é o resultado da execução do formato que apresenta a lista simples de itens de mercadoria.<a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="GER SPLITLISTBYLIMIT - output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a>O exemplo a seguir mostra o mesmo formato que foi ajustado para apresentar a lista de itens de mercadorias em lotes quando um único lote deverá incluir mercadorias com o peso total que não devem exceder o limite de 9.<a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="GER SPLITLISTBYLIMIT - format 1" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a><a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="GER SPLITLISTBYLIMIT - datasources 1" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a>Este é o resultado da execução do formato ajustado. <a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="GER SPLITLISTBYLIMIT - output 1" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a><strong>Observação:</strong> o limite não será aplicado ao último item da lista de origem já que o valor (11) de sua fonte de limite (peso) ultrapassa o limite definido (9). Use a função <strong>ONDE</strong> ou a expressão <strong>Habilitado</strong> do elemento de formato correspondente para ignorar as sublistas (pular) durante a geração do relatório (se necessário).</td>
</tr>
<tr class="odd">
<td>FILTRO (lista, condição)</td>
<td>Retorna a lista fornecida filtrada para a condição especificada modificando a consulta. Diferentemente da função <strong>ONDE</strong>, a condição especificada é aplicada no nível da base de dados a qualquer fonte de dados de ER do tipo de registros da tabela.</td>
<td>FILTER (Vendors, Vendors.VendGroup = &quot;40&quot;) retorna a lista de fornecedores que pertencem somente ao grupo de fornecedores "40" quando o <strong>Fornecedor</strong> estiver configurado como a fonte de dados de ER referente à tabela <strong>VendTable</strong></td>
</tr>
</tbody>
</table>

### <a name="logical-functions"></a>Funções lógicas

| Função                                                                                | descrição                                                                                                                                                                                                                                                                     | Exemplo                                                                                                                                                                                                                                                      |
|-----------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CASE (expressão, opção 1, resultado 1 \[, opção 2, resultado 2\] ... \[, resultado padrão\]) | Avalia o valor especificado da expressão com as opções alternativas especificadas. Devolve o resultado da opção que é igual ao valor da expressão. Caso contrário, devolve o resultado padrão (opcionalmente inserido ao último parâmetro que não é precedido por uma opção). | **CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")** devolve a cadeia de caracteres **"WINTER"** quando a data da sessão atual do Finance and Operations está entre outubro e dezembro. Caso contrário, retorna uma cadeia de caracteres em branco. |
| IF (condição, valor 1, valor 2)                                                        | Devolve o valor especificado 1 quando a condição especificada é atingida. Caso contrário, retorna o valor 2. Se o valor 1 e o valor 2 são registros ou listas de registro, o resultado será somente os campos que existem em ambas as listas.                                                                     | **IF (1=2, "condição é alcançada", "condição não é alcançada")** devolve a cadeia **"condição não é alcançada"**.                                                                                                                                                      |
| NOT (condição)                                                                         | Devolve o valor da condição lógica revertido especificado.                                                                                                                                                                                                                   | **NOT (TRUE)** devolve **FALSE**.                                                                                                                                                                                                                            |
| AND (condição 1\[, condição 2, ...\])                                                 | Devolve **TRUE** se *todas* as condições especificadas forem verdade. Caso contrário, devolve **FALSO**.                                                                                                                                                                                            | **AND (1=1, "a"="a")** devolve **TRUE**. **AND (1=2, "a"="a")** devolve **FALSE**.                                                                                                                                                                           |
| OR (condição 1\[, condição 2, ...\])                                                  | Devolve **FALSE** se *todas* as condições especificadas forem falsas. Devolve **TRUE** se *quaisquer* condições especificadas forem verdade.                                                                                                                                                                 | **OR (1=2, "a"="a")** devolve **TRUE**.                                                                                                                                                                                                                      |

### <a name="mathematical-functions"></a>Funções matemáticas

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Função</th>
<th>Descrição</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>ABS (número)</td>
<td>Retorna o valor absoluto de um número específico (o número sem seu sinal).</td>
<td><strong>ABS (-1)</strong> retorna <strong>1</strong>.</td>
</tr>
<tr class="even">
<td>POWER (número, potência)</td>
<td>Devolve o resultado de aumento do número positivo especificado para a potência especificada.</td>
<td><strong>POWER (10, 2)</strong> devolve <strong>100</strong>.</td>
</tr>
<tr class="odd">
<td>NUMBERVALUE (cadeia de caracteres, separador decimal, separador de grupo de dígitos)</td>
<td>Converte a cadeia de caracteres especificada como um número. O símbolo especificado é usado para separar o inteiro e as partes fracionárias de um número decimal, e o separador de milhares especificado também é usado.</td>
<td><strong>NUMBERVALUE(&quot;1 234,56&quot;, &quot;,&quot;, &quot; &quot;)</strong> retorna o valor <strong>1234.56</strong>.</td>
</tr>
<tr class="even">
<td>VALUE (cadeia de caracteres)</td>
<td>Converte a cadeia de caracteres especificada como um número. As vírgulas e os caracteres de ponto (.) são considerados separadores decimais, e um hífen principal (-) é usado como o sinal negativo. Joga uma exceção se outros caracteres numéricos não são atendidos na cadeia de caracteres especificada.</td>
<td><strong>VALUE (&quot;1 234,56&quot;)</strong> gera uma exceção.</td>
</tr>
<tr class="odd">
<td>ROUND (número, decimais)</td>
<td>Devolve o número especificado, que é arredondado ao número especificado de casas decimais:
<ul>
<li>Se o valor especificado de decimais for maior do que 0 (zero), o número especificado é arredondado ao número especificado de casas decimais.</li>
<li>Se o valor especificado de decimais for 0 (zero), o número especificado é arredondado para o inteiro mais próximo.</li>
<li>Se o valor especificado de decimais for menor do que 0 (zero), o número especificado é arredondado ao ponto decimal à esquerda.</li>
</ul></td>
<td><strong>ROUND (1200.767, 2)</strong> arredonda para duas casas decimais e devolve <strong>1200.77</strong>. <strong>ROUND (1200.767, -3)</strong> arredonda para o múltiplo mais próximo de 1.000 e devolve <strong>1000</strong>.</td>
</tr>
<tr class="even">
<td>ROUNDDOWN (número, decimais)</td>
<td>Devolve o número especificado, que é arredondado para baixo (para zero) ao número especificado de casas decimais. <strong>Observação:</strong> Esta função comporta-se como <strong>ROUND</strong>, mas sempre arredonda o número especificado para baixo.</td>
<td><strong>ROUNDDOWN (1200.767, 2)</strong> arredonda para baixo duas casas decimais e devolve <strong>1200.76</strong>. <strong>ROUNDDOWN (1700.767, -3)</strong> arredonda para baixo o múltiplo mais próximo de 1.000 e devolve <strong>1000</strong>.</td>
</tr>
<tr class="odd">
<td>ROUNDUP (número, decimais)</td>
<td>Devolve o número especificado, que é arredondado para cima (longe de zero) ao número especificado de casas decimais. <strong>Observação:</strong> Esta função comporta-se como <strong>ROUND</strong>, mas sempre arredonda o número especificado para cima.</td>
<td><strong>ROUNDUP (1200.763, 2)</strong> arredonda para cima duas casas decimais e devolve <strong>1200.77</strong>. <strong>ROUNDUP (1200.767, -3)</strong> arredonda para cima o múltiplo mais próximo de 1.000 e devolve <strong>2000</strong>.</td>
</tr>
</tbody>
</table>

**Funções de conversão de dados**

| Função             | descrição                                                                                                                                                                                                                                     | Exemplo                                                                                                                                             |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| VALUE (cadeia de caracteres) | Converte a cadeia de caracteres especificada como um número. As vírgulas e os caracteres de ponto (.) são considerados separadores decimais, e um hífen principal (-) é usado como um sinal negativo. Se outros caracteres não numéricos forem atendidos na cadeia de caracteres especificada, ocorrerá um erro.                                                                                  | **VALUE ("1 234,56")** exibe uma exceção.   |
| NUMBERVALUE (cadeia de caracteres, separador decimal, separador de grupo de dígitos) | Converte a cadeia de caracteres especificada como um número. O símbolo especificado é usado para separar o inteiro e as partes fracionárias de um número decimal, e o separador de milhares especificado também é usado.                                                                                  | **NUMBERVALUE("1 234,56", ",", " ")** devolve o valor **1234.56**.    |
| INTVALUE (cadeia de caracteres) | Retorna a representação inteira de uma cadeia de caracteres. Todas as partes decimais disponíveis serão truncadas.                                                                                  | **INTVALUE (“100.77”)** retorna **100**. |
| INTVALUE (número) | Retorna a representação inteira de um número. Todas as partes decimais disponíveis serão truncadas.                                                                                  | **INTVALUE (-100.77)** retorna **-100**. |
| INT64VALUE (cadeia de caracteres) | Retorna a representação int64 de uma cadeia de caracteres. Todas as partes decimais disponíveis serão truncadas.                                                                                  | **INT64VALUE (“22565422744”)** retorna **22565422744**. |
| INT64VALUE (número) | Retorna a representação int64 de um número. Todas as partes decimais disponíveis serão truncadas.                                                                                  | **INT64VALUE (22565422744.00)** retorna **22565422744**. |



### <a name="record-functions"></a>Funções de registro

| Função             | descrição                                                                                                                                                                                                                                     | Exemplo                                                                                                                                             |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| NULLCONTAINER (lista) | Devolve um registro **null** com a mesma estrutura que a lista de inscrição ou o registro especificado. **Observação:** Esta função é obsoleta. Use **EMPTYRECORD** em seu lugar.                                                                                  | **NULLCONTAINER (SPLIT ("abc", 1))** devolve um novo registro vazio que tem a mesma estrutura que a lista devolvida pela função **SPLIT**. |
| EMPTYRECORD (registro) | Devolve um registro **null** com a mesma estrutura que a lista de inscrição ou o registro especificado. **Observação:** um registro **nulo** é um registro onde todos os campos têm um valor vazio (**0** \[zero\] para números, e uma cadeia vazia para cadeia de caracteres, e assim por diante). | **EMPTYRECORD (SPLIT ("abc", 1))** devolve um novo registro vazio que tem a mesma estrutura que a lista devolvida pela função **SPLIT**.   |

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
<th>Descrição</th>
<th>Exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>UPPER (cadeia de caracteres)</td>
<td>Retorna a cadeia de caracteres especificada, que é convertida para as letras maiúsculas.</td>
<td><strong>UPPER(&quot;Sample&quot;)</strong> retorna <strong>&quot;SAMPLE&quot;</strong>.</td>
</tr>
<tr class="even">
<td>LOWER (cadeia de caracteres)</td>
<td>Retorna a cadeia de caracteres especificada, que é convertida para as letras minúsculas.</td>
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
<td><strong>CHAR (255)</strong> retorna <strong>&quot;ÿ&quot;</strong>. <strong>Observação:</strong> a sequência de caracteres retornada depende da codificação que foi selecionada no elemento do formato do ARQUIVO pai. A lista de codificações com suporte pode ser encontrada no tópico <a href="https://msdn.microsoft.com/en-us/library/system.text.encoding(v=vs.110).aspx">Classe de codificação</a>.</td>
</tr>
<tr class="even">
<td>CONCATENATE (cadeia de caracteres 1 [, cadeia de caracteres 2, …])</td>
<td>Retorna todas as cadeias de caracteres de texto especificado, que são adicionadas em uma cadeia de caracteres.</td>
<td><strong>CONCATENATE (&quot;abc&quot;, &quot;def&quot;)</strong> retorna <strong>&quot;abcdef&quot;</strong>. <strong>Observação:</strong> A expressão <strong>&quot;abc&quot; &amp; &quot;def&quot;</strong> também retorna <strong>&quot;abcdef&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>TRANSLATE (cadeia de caracteres, padrão, substituição)</td>
<td>Retorna a cadeia de caracteres especificada, na qual todas as as ocorrências dos caracteres na cadeia de caracteres especificada pelos caracteres padrão são substituídas na posição correspondente da cadeia de caracteres especificada de substituição.</td>
<td><strong>TRANSLATE (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;)</strong> substitui o padrão <strong>&quot;cd&quot;</strong> pela cadeia <strong>&quot;GH&quot;</strong> e retorna <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr class="even">
<td>REPLACE (cadeia de caracteres, padrão, substituição, sinalizador da expressão regular)</td>
<td>Quando o sinalizador da expressão regular é <strong>verdadeiro</strong>, retorne a cadeia de caracteres especificada, que é alterada aplicando a expressão regular que é especificada como um padrão do argumento para a função. A expressão é usada para localizar os caracteres que devem ser substituídos. Os caracteres do argumento especificado de substituição são usados para substituir os caracteres que são encontrados. Quando o sinalizador da expressão regular é <strong>false</strong> especificado, esta função comporta-se como <strong>TRANSLATE</strong>.</td>
<td>  <strong>REPLACE (&quot;+1 923 456 4971&quot;, &quot;[^0-9]&quot;, &quot;&quot;, true)</strong> aplica uma expressão comum que remove todos os símbolos não numéricos, e retorna <strong>&quot;19234564971&quot;</strong>. <strong>REPLACE (&quot;abcdef&quot;, &quot;cd&quot;, &quot;GH&quot;, false)</strong> substitui o padrão <strong>&quot;cd&quot;</strong> pela cadeia <strong>&quot;GH&quot;</strong> e retorna <strong>&quot;abGHef&quot;</strong>.</td>
</tr>
<tr class="odd">
<td>TEXT (entrada)</td>
<td>Retorna a entrada especificada, que é convertida em uma cadeia de caracteres de texto que é formatada de acordo com as configurações de localidade do servidor da instância atual do Finance and Operations. Para valores do tipo <strong>real</strong>, a conversão de cadeia de caracteres é limitada para duas casas decimais.</td>
<td>Se a localidade do servidor da instância do Finance and Operations é definida como <strong>EN-US</strong>, <strong>TEXT (NOW ())</strong> retorna a data da sessão atual do Finance and Operations, 12/17/2015, como a cadeia de caracteres de texto <strong>&quot;17/12/2015 07:59:23&quot;</strong>. <strong>TEXT (1/3)</strong> retorna <strong>&quot;0.33&quot;</strong>.</td>
</tr>
<tr class="even">
<td>FORMAT (cadeia de caracteres 1, cadeia de caracteres 2[, cadeia de caracteres 3, ...])</td>
<td>Retorna a cadeia de caracteres especificada, que é formatada substituindo todas as ocorrências <strong>%N</strong> pelo e<em>n</em>ésimo argumento. Os argumentos são cadeias de caracteres. Se o argumento não for fornecido para um parâmetro, o parâmetro retornará como <strong>&quot;%N&quot;</strong> na cadeia. Para valores do tipo <strong>real</strong>, a conversão de cadeia de caracteres é limitada para duas casas decimais.</td>
<td>Neste exemplo, a fonte de dados <strong>PaymentModel</strong> retorna a lista de registros de cliente por meio do componente <strong>Cliente</strong> e o valor da data de processamento por meio do campo <strong>ProcessingDate</strong>. <a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a> No formato ER que é projetado para gerar um arquivo eletrônico para clientes selecionados, <strong>PaymentModel</strong> é selecionado como uma fonte de dados e controla o fluxo do processo. Uma exceção será jogada para usuários finais quando um cliente selecionado for parado para a data em que o relatório será processado. A fórmula que é criada para este tipo de controle de processamento pode usar os seguintes recursos:
<ul>
<li>Etiqueta SYS70894 do Finance and Operations, que tem o seguinte texto:
<ul>
<li><strong>Para o idioma Inglês dos EUA:</strong> &quot;Nothing to print&quot;</li>
<li><strong>Para o idioma alemão:</strong> &quot;Nichts zu drucken&quot;</li>
</ul></li>
<li>Etiqueta SYS18389 do Finance and Operations, que tem o seguinte texto:
<ul>
<li><strong>Para o idioma Inglês dos EUA:</strong> &quot;Customer %1 is stopped for %2.&quot;</li>
<li><strong>Para o idioma Alemão:</strong> &quot;Debitor '%1' wird für %2 gesperrt.&quot;</li>
</ul></li>
</ul>
Veja a fórmula que pode ser criada: FORMAT (CONCATENATE (@&quot;SYS70894&quot;, &quot;. &quot;, @&quot;SYS18389&quot;), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, &quot;d&quot;)) Se um relatório é processado para o <strong>cliente Litware Retail</strong> em 17 de dezembro de 2015, na cultura <strong>EN-US</strong> e no idioma <strong>EN-US</strong> esta fórmula retorna o texto a seguir, que pode ser apresentado como uma mensagem de exceção para o usuário final: &quot;Nothing to print. O cliente Litware Retail está bloqueado para 12/17/2015.&quot; Se o mesmo relatório for processado para o<strong> cliente Litware Retail</strong> em 17 de dezembro de 2015, na cultura da <strong>Alemanha</strong> no idioma <strong>Alemão</strong>, esta fórmula retornará o texto a seguir, que usa um formato de data diferente: &quot;Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.&quot; <strong>Observação:</strong> A sintaxe a seguir é aplicada em fórmulas de ER para etiquetas:
<ul>
<li><strong>Para etiquetas dos recursos do Finance and Operations:</strong> <strong>@&quot;X&quot;</strong>, em que X é a ID da etiqueta na AOT (Árvore de Objetos de Aplicativo)</li>
<li><strong>Para as etiquetas que residem nas configurações:</strong> <strong>@&quot;GER_LABEL:X&quot;</strong>, onde X é a ID da etiqueta na configuração de ER</li>
</ul></td>
</tr>
<tr class="odd">
<td>NUMBERFORMAT (número, formato)</td>
<td>Retorna a representação da cadeia de caracteres do número especificado no formato especificado. (Para obter informações sobre os formatos suportados, consulte <a href="https://msdn.microsoft.com/en-us/library/dwhawy9k(v=vs.110).aspx">padrão</a> e <a href="https://msdn.microsoft.com/en-us/library/0c899ak8(v=vs.110).aspx">personalizada</a>.) O contexto que esta função é executada determina a cultura usada para formatar números.</td>
<td>Para a cultura EN-US, <strong>NUMBERFORMAT (0.45, &quot;p&quot;)</strong> retorna <strong>&quot;45.00 %&quot;</strong>. <strong>NUMBERFORMAT (10.45, &quot;#&quot;)</strong> retorna <strong>&quot;10&quot;</strong>.</td>
</tr>
<tr class="even">
<td>NUMERALSTOTEXT (número, idioma, moeda, sinalizador imprimir nome da moeda, casas decimais)</td>
<td>Retorna o número soletrado (convertido) em cadeias de caracteres de texto no idioma definido. O código do idioma é opcional: quando for definido como cadeia de caracteres vazia, o código de idioma do contexto em execução (definido para a geração de uma pasta ou de um arquivo) será utilizado. O código de moeda é opcional. Quando ele for definido como cadeia de caracteres vazia, a moeda da empresa será utilizada. Observe que o parâmetro <strong>Imprimir nome da moeda</strong> e o parâmetro <strong>Casas decimais</strong> são analisados somente para os seguintes códigos de idioma: <strong>CS</strong>, <strong>ET</strong>, <strong>HU</strong>, <strong>LT</strong>, <strong>LV</strong>, <strong>PL</strong>, <strong>RU</strong>. Observe que o parâmetro <strong>Imprimir nome da moeda</strong> é analisado somente para empresas do Finance and Operations com o contexto do país que ofereça suporte à declinação da moeda.</td>
<td>NUMERALSTOTEXT (1234.56, &quot;EN&quot;, &quot;&quot;, false, 2) retorna "Mil duzentos e trinta e quatro e 56" NUMERALSTOTEXT (120, &quot;PL&quot;, &quot;&quot;, false, 0) retorna “Sto dwadzieścia” NUMERALSTOTEXT (120.21, &quot;RU&quot;, &quot;EUR&quot;, true, 2) retorna “Сто двадцать евро 21 евроцент”</td>
</tr>
<tr class="odd">
<td>PADLEFT (cadeia de caracteres, comprimento, caracteres de preenchimento)</td>
<td>Retorna uma cadeia de um tamanho especificado em que o início da cadeia atual é preenchido com caracteres especificados.</td>
<td>PADLEFT (“1234”, 10, “ “) retorna a cadeia de caracteres de texto "      1234"</td>
</tr>
<tr class="even">
<td>TRIM (cadeia de caracteres)</td>
<td>Retorna o texto fornecido após o truncamento de espaços à direita e à esquerda, e remove vários espaços entre palavras. </td>
<td><strong>TRIM ("     Sample     text     ")</strong> retorna <strong>"Texto de exemplo".</strong></td>
=======
<td>GETENUMVALUEBYNAME (caminho da fonte de dados de enumeração, texto do rótulo do valor de enumeração)</td>
<td>Retorna o valor de uma fonte de dados de enumeração especificada pelo texto especificado desse rótulo de enumeração.</td>
<td>O exemplo a seguir mostra a enumeração ReportDirection apresentada em um modelo de dados. Observe que as etiquetas são definidas por valores de enumeração.
Os exemplos a seguir mostram:
<ul><li>A enumeração do modelo <strong>ReportDirection</strong> inserida em um relatório como uma fonte de dados <strong>$Direction</strong>.</li>
<li>A expressão ER <strong>$IsArrivals</strong> criada para usar a enumeração do modelo como o parâmetro dessa função. O valor dessa expressão é <strong>TRUE</strong></li></ul></td>
</tr>
</tbody>
</table>

**Funções de conversão de dados**

| Função             | descrição                                                                                                                                                                                                                                     | Exemplo                                                                                                                                             |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| TEXT (entrada) | Retorna a entrada especificada, que é convertida em uma cadeia de caracteres de texto que é formatada de acordo com as configurações de localidade do servidor da instância atual do Finance and Operations.
Para valores do tipo real, a conversão de cadeia de caracteres é limitada para duas casas decimais.| Se a localidade do servidor da instância do Finance and Operations é definida como **EN-US, TEXT (NOW ())**, a data da sessão atual do Finance and Operations, 12/17/2015, retorna como a cadeia de caracteres de texto **"17/12/2015 07:59:23"**.
**TEXT (1/3) devolve "0.33"**. |
| QRCODE (cadeia de caracteres) | Retorna a imagem do código QR no formato Base64 binário de uma sequência específica. | **QRCODE (“Texto exemplo”)** retorna **U2FtcGxlIHRleHQ=**.   |

### <a name="data-collection-functions"></a>Funções de coleta de dados

| Função             | descrição                                                                                                                                                                                                                                     | Exemplo                                                                                                                                             |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| FORMATELEMENTNAME () | Retorna o nome do elemento de formato atual. Retorna a cadeia de caracteres vazia quando o sinalizador **Coletar detalhes de saída** dos arquivos atuais estiver desativado.| Consulte o Guia de tarefas **ER Usar dados de saída do formato contagem e soma** (parte do processo comercial **Adquirir/Desenvolver componentes de solução/serviço de TI**) para saber mais sobre o uso dessas funções. |
| SUMIFS (cadeia de caracteres chave para somar, cadeia de caracteres do critério range1, cadeia de caracteres do critério value1 \[, cadeia de caracteres do critério range2, cadeia de caracteres do critério value2, …\]) |Retorna uma soma dos valores de nós (com o nome definido como uma chave) do XML, que foi coletada durante a execução deste formato e atende às condições inseridas (pares de intervalo e valor). Retorna o valor zero quando o sinalizador **Coletar detalhes de saída** dos arquivos atuais estiver desativado. |            |
| SUMIF (cadeia de caracteres chave para somar, cadeia de caracteres de intervalo de critérios, cadeia de caracteres de valor de critérios) | Retorna uma soma dos valores de nós (com o nome definido como uma chave) do XML, que foi coletada durante a execução deste formato e atende à condição inserida (intervalo e valor). Retorna o valor zero quando o sinalizador **Coletar detalhes de saída** dos arquivos atuais estiver desativado.|           |
| COUNTIFS (cadeia de caracteres do critério range1, cadeia de caracteres do critério value1 \[, cadeia de caracteres do critério range2, cadeia de caracteres do critério value2, …\]) | Retorna o número de nós do XML, que foi coletado durante a execução deste formato e atende às condições inseridas (pares de intervalo e valor). Retorna o valor zero quando o sinalizador **Coletar detalhes de saída** dos arquivos atuais estiver desativado.|     |
| COUNTIF (cadeia de caracteres de intervalo de critérios, cadeia de caracteres de valor de critérios) | Retorna o número de nós do XML, que foi coletado durante a execução deste formato e atende à condição inserida (intervalo e valor). Retorna o valor zero quando o sinalizador **Coletar detalhes de saída** dos arquivos atuais estiver desativado.|          |
| COLLECTEDLIST (cadeia de caracteres do critério range1, cadeia de caracteres do critério value1 \[, cadeia de caracteres do critério range2, cadeia de caracteres do critério value2, …\]) | Retorna uma lista de valores de nós do XML, que foi coletada durante a execução deste formato e atende às condições inseridas (pares de intervalo e valor). Retorna uma cadeia de caracteres vazia quando o sinalizador **Coletar detalhes de saída** dos arquivos atuais estiver desativado.|               |   




### <a name="other-business-domainspecific-functions"></a>Outras funções (específicas de domínio comercial)

| Função                                                                         | descrição                                                                                                                                                                                                                                                        | Exemplo                                                                                                                                                                                                                                                                                                       |
|----------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CONVERTCURRENCY (valor, moeda de origem, moeda de destino, data, empresa)        | Converte o valor monetário especificado da moeda de origem para a moeda de destino usando as configurações da empresa especificada do Finance and Operations na data especificada.                                                                            | **CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")** retorna equivalentes do euro em dólares norte-americanos na data da sessão atual, com base nas configurações da empresa de DEMF.                                                                                                                                  |
| ROUNDAMOUNT (número, decimais, regra de arredondamento)                                       | Arredonde valor especificado de acordo com a regra de arredondamento especificada e o número especificado de casas decimais. **Observação:** a regra de arredondamento deve ser especificada como um valor de enumeração **RoundOffType** do Finance and Operations.                          | Se o parâmetro **model.RoundOff** estiver definido para ****Arredondar para baixo****, **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** retorna o valor **1000.78**. Se o parâmetro **model.RoundOff** é definido para **Normal** ou **Arredondar para cima**, **ROUNDAMOUNT (1000.787, 2, model.RoundOff)** devolve o valor **1000.79**. |
| CURCredRef (dígitos)                                                              | Devolve uma referência do credor, com base nos dígitos do número da nota fiscal especificada.                                                                                                                                                                                  | **CURCredRef ("VEND-200002")** retorna **"2200002"**.                                                                                                                                                                                                                                                         |
| MOD\_97 (digits)                                                                 | Devolve uma referência do credor como uma expressão de MOD97, com base nos dígitos do número da nota fiscal especificada.                                                                                                                                                            | **MOD\_97 ("VEND-200002")** retorna **"20000285"**.                                                                                                                                                                                                                                                           |
| ISOCredRef (dígitos)                                                              | Devolve uma referência do credor de ISO, com base nos dígitos e símbolos alfabéticos do número da nota fiscal especificada. **Observação:** Para eliminar alfabetos dos símbolos que não são compatíveis com ISO, o parâmetro de entrada deve ser traduzido antes de transmita à essa função. | **ISOCredRef ("VEND-200002")** retorna **"RF23VEND-200002"**.                                                                                                                                                                                                                                                 |
| CN\_GBT\_AdditionalDimensionID (cadeia de caracteres, número)                                  | Obtenha a ID da dimensão financeira adicional. As dimensões são representadas nesta cadeia de caracteres como IDs separadas por vírgulas. Os números definem o código de sequência da dimensão solicitada nesta cadeia de caracteres.                                                                            | CN\_GBT\_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH",3) retorna “CC”                                                                                                                                                                                                                                      |
| GetCurrentCompany ()                                                             | Retorna a representação de texto de um código de uma entidade legal (empresa) à qual um usuário está conectado no momento.                                                                                                                                                                                                                    | **GETCURRENTCOMPANY ()** retorna **USMF** para o usuário da empresa **Contoso Entertainment System USA** que efetuou o logon no Finance and Operations.                                                                                                                                                                                                                                                                                                              |
| CH\_BANK\_MOD\_10 (dígitos)                                                       | Retorna uma referência de credor como uma expressão MOD10, com base nos dígitos do número da fatura fornecido.                                                                                                                                                                      | CH\_BANK\_MOD\_10 ("VEND-200002") retorna 3                                                                                                                                                                                                                                                                   |
| FA\_SUM (código do ativo fixo, código de modelo de depreciação, data inicial, data final)               | Retorna o contêiner de dados preparado de valores de um ativo fixo para um período.                                                                                                                                                                                         | FA\_SUM ("COMP-000001", “Current”, Date1, Date2) retorna o contêiner de dados preparado do ativo fixo "COMP-000001" com o modelo de depreciação "Current" (Atual) para o período da Date1 a Date2.                                                                                                                        |
| FA\_BALANCE (código do ativo fixo, código de modelo de depreciação, ano do relatório, data do relatório) | Retorna o contêiner de dados preparado de saldos de um ativo fixo. O ano do relatório deve ser especificado como um valor de enumeração **AssetYear** do Finance and Operations.                                                                                           | FA\_SUM ("COMP-000001", “Current”, AxEnumAssetYear.ThisYear, SESSIONTODAY ()) retorna o contêiner de dados preparado dos saldos para o ativo fixo "COMP-000001" com o modelo de valor “Current” (Atual) na data atual da sessão do 365 for Finance and Operations.                                                                |
| TABLENAME2ID (cadeia de caracteres)                                                       | Retorna a representação de inteiro de uma ID de tabela para um nome de tabela fornecido.                                                                                                                                                                      | **TABLENAME2ID (“Intrastat”)** retorna **1510**.                                                                                                                                                                                                                                                                   |
| ISVALIDCHARACTERISO7064 (cadeia de caracteres)                                                       | Retorna booliano **TRUE** quando uma determinada cadeia de caracteres representa um número de conta bancária internacional válido (IBAN). Caso contrário, retorna booliano **FALSE**.                                                                                                                                                                      | **ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")** retorna **TRUE**. **ISVALIDCHARACTERISO7064 ("AT61")** retorna **FALSE**.                                                                                                                                                                                                                                                                   |

### <a name="functions-list-extension"></a>Extensão da lista de funções

ER deixa você estender a lista de funções que são usadas em expressões ER. Isso exige alguns esforços de engenharia. Para informações detalhadas, consulte [Estender a lista de funções do relatório eletrônico](general-electronic-reporting-formulas-list-extension.md).

<a name="see-also"></a>Consulte também
--------

[Visão geral do Relatório Eletrônico](general-electronic-reporting.md)

[Estender a lista de funções do ER (Relatório eletrônico)](general-electronic-reporting-formulas-list-extension.md)




