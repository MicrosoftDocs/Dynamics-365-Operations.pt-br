---
title: Implementar campos personalizados para o aplicativo móvel do Microsoft Dynamics 365 Project Timesheet no iOS e Android
description: Este tópico fornece padrões comuns para o uso de extensões para implementar campos personalizados.
author: KimANelson
manager: AnnBe
ms.date: 05/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: 10.0.3
ms.search.validFrom: 2019-05-29
ms.openlocfilehash: c0c578ca44919671b67daeea51a9ec7687f755c9
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773636"
---
# <a name="implement-custom-fields-for-the-microsoft-dynamics-365-project-timesheet-mobile-app-on-ios-and-android"></a>Implementar campos personalizados para o aplicativo móvel do Microsoft Dynamics 365 Project Timesheet no iOS e Android

[!include [banner](../includes/banner.md)]

Este tópico fornece padrões comuns para o uso de extensões para implementar campos personalizados. Os tópicos a seguir estão cobertos:

- Os vários tipos de dados a que a estrutura de campo personalizado oferece suporte
- Como mostrar campos somente leitura ou editáveis nas entradas de folha de ponto e salvar os valores fornecidos pelo usuário no banco de dados
- Como mostrar campos somente leitura no cabeçalho de folha de ponto
- Como integrar outra lógica de negócios personalizada para inserir valores padrão em campos e fazer uma validação adicional

## <a name="audience"></a>Público-alvo

Este tópico é destinado a desenvolvedores que estão integrando seus campos personalizados no aplicativo móvel do Microsoft Dynamics 365 Project Timesheet que está disponível para Apple iOS e Google Android. A suposição é que os leitores estão familiarizados com o desenvolvimento do X ++ e a funcionalidade de folha de ponto do projeto.

## <a name="data-contract--tstimesheetcustomfield-x-class"></a>Contrato dos dados – Classe TSTimesheetCustomField X++

A classe **TSTimesheetCustomField** é a classe de contrato de dados X++ que representa informações sobre um campo personalizado para a funcionalidade de folha de ponto. As listas dos objetos de campo personalizados são transmitidas no contrato de dados TSTimesheetDetails e no contrato de dados TSTimesheetEntry para mostrar campos personalizados no aplicativo móvel.

- **TSTimesheetDetails** - O contrato de cabeçalho da folha de ponto.
- **TSTimesheetEntry** - O contrato da transação da folha de ponto. Grupos desses objetos com as mesmas informações do projeto e o valor **timesheetLineRecId** constituem uma linha.

### <a name="fieldbasetype-types"></a>fieldBaseType (tipos)

A propriedade **FieldBaseType** no objeto **TsTimesheetCustom** determina o tipo do campo exibido no aplicativo. Os valores **Tipos** a seguir que são compatíveis.

| Tipos de valor | Tipo              | Observação |
|-------------|-------------------|-------|
| 0           | Sequência de caracteres (e enumeração) | O campo aparece como um campo de texto. |
| 1           | Inteiro           | O valor é mostrado como um número sem casas decimais. |
| 2           | Real              | O valor é mostrado como um número com casas decimais.<p>Para mostrar o valor real como uma moeda no aplicativo, use a propriedade **fieldExtenededType**. Você pode usar a propriedade **numberOfDecimals** para definir o número de casas decimais exibidas.</p> |
| 3           | Data              | Os formatos de data são determinados pelo formato **Formato de data, hora e número** do usuário, que é especificado em **Preferências de idioma e país/região** de **Opções do usuário**. |
| 4           | Booleano           | |
| 15          | GUID              | |
| 16          | Int64             | |

- Se a propriedade **stringOptions** não for fornecida no objeto **TSTimesheetCustomField**, um campo de texto livre é fornecido ao usuário.

    A propriedade **stringLength** pode ser usada para definir o comprimento máximo de sequência de caracteres que os usuários poderão inserir.

- Se a propriedade **stringOptions** for fornecida no objeto **TSTimesheetCustomField**, esses elementos da lista são os únicos valores que os usuários podem selecionar usando os botões de opção.

    Nesse caso, o campo de sequência de caracteres pode atuar como um valor de enumeração para fins de entrada do usuário. Para salvar o valor no banco de dados como uma enumeração, mapeie manualmente o valor da sequência para o valor de enumeração antes de salvar no banco de dados usando a cadeia de comando (consulte “Usar cadeia de comando na classe TSTimesheetEntryService para salvar uma entrada de folha de ponto do aplicativo ao banco de dados” posteriormente neste tópico para obter um exemplo).

### <a name="fieldextendedtype-tscustomfieldextendedtype"></a>fieldExtendedType (TSCustomFieldExtendedType)

Você pode usar essa propriedade para formatar valores reais como moeda. Essa abordagem é aplicável somente quando o valor **fieldBaseType** é **Real**.

- **TSCustomFieldExtendedType:None** – Nenhuma formatação é aplicada.
- **TSCustomFieldExtendedType::Moeda** – Formate o valor como moeda.

    Quando a formatação da moeda está ativa, o campo **stringValue** pode ser usado para passar o código da moeda que deve ser exibido no aplicativo. O valor é um valor somente leitura.

    O campo **realValue** contém o valor monetário que deve ser salvo no banco de dados.

### <a name="fieldsection-tscustomfieldsection"></a>fieldSection (TSCustomFieldSection)

É possível usar essa propriedade para especificar onde o campo personalizado deve aparecer no aplicativo.

- **TSCustomFieldSection::Cabeçalho** – O campo aparecerá na seção **Exibir mais detalhes** no aplicativo. Esses campos são sempre somente leitura.
- **TSCustomFieldSection::Linha** – O campo aparecerá depois de todos os campos da linha pronta para uso nas entradas de folha de ponto. Esses campos podem ser editáveis ou somente leitura.

### <a name="fieldname-fieldnameshort"></a>fieldName (FieldNameShort)

Essa propriedade identifica o campo quando os valores fornecidos pelo aplicativo são salvos no banco de dados.

### <a name="tablename-tablenameshort"></a>tableName (TableNameShort)

Essa propriedade identifica o campo quando os valores fornecidos pelo aplicativo são salvos no banco de dados.

### <a name="iseditable-noyes"></a>isEditable (NoYes)

Defina essa propriedade como **Sim** para especificar que o campo na seção de entrada de folha de ponto deve ser editável pelos usuários. Defina a propriedade **Não** para tornar o campo somente leitura.

### <a name="ismandatory-noyes"></a>isMandatory (NoYes)

Defina essa propriedade como **Sim** para especificar que o campo na seção de entrada de folha de ponto deve ser obrigatório.

### <a name="label-str"></a>etiqueta (str)

Essa propriedade especifica o rótulo mostrado ao lado do campo no aplicativo.

### <a name="stringoptions-list-of-strings"></a>stringOptions (lista de caracteres)

Essa propriedade é aplicável somente quando **fieldBaseType** é definido como **Sequência de caracteres**. Se **stringOptions** for definido, os valores de string disponíveis para seleção por meio de botões de opção são especificados pelas sequências de caracteres na lista. Se nenhuma sequência de caracteres for fornecida, a entrada de texto livre no campo de sequência de caracteres será permitida (consulte a seção “Usar cadeia de comando na classe TSTimesheetEntryService para salvar uma entrada de folha de ponto do aplicativo ao banco de dados” posteriormente neste tópico para obter um exemplo) .

### <a name="stringlength-int"></a>stringLength (int)

Essa propriedade especifica o comprimento máximo de um campo de sequência de caracteres. É aplicável somente quando **fieldBaseType** é definido como **Sequência de caracteres**.

### <a name="numberofdecimals-int"></a>numberOfDecimals (int)

Essa propriedade especifica o número de casas decimais exibidas para um campo real. É aplicável somente quando **fieldBaseType** é definido como **Real**.

### <a name="ordersequence-int"></a>orderSequence (int)

Essa propriedade controla a ordem em que os campos personalizados são mostrados no aplicativo quando mais de um campo personalizado é especificado. Campos com números inferiores são mostrados primeiro.

### <a name="booleanvalue-boolean"></a>booleanValue (booliano)

Para os campos do tipo **Booliano**, essa propriedade transmite o valor booliano do campo entre o servidor e o aplicativo.

### <a name="guidvalue-guid"></a>guidValue (guid)

Para campos do tipo **GUID**, essa propriedade transmite o valor de identificador global exclusivo (GUID) do campo entre o servidor e o aplicativo.

### <a name="int64value-int64"></a>int64Value (int64)

Para os campos do tipo **Int64**, essa propriedade transmite o valor int64 do campo entre o servidor e o aplicativo.

### <a name="intvalue-int"></a>intValue (int)

Para os campos do tipo **Int**, essa propriedade transmite o valor int do campo entre o servidor e o aplicativo.

### <a name="realvalue-real"></a>realValue (real)

Para os campos do tipo **Real**, essa propriedade transmite o valor real do campo entre o servidor e o aplicativo.

### <a name="stringvalue-str"></a>stringValue (str)

Para os campos do tipo **Sequência de caracteres**, essa propriedade transmite o valor de sequência de caracteres do campo entre o servidor e o aplicativo. Ela também é usada em campos do tipo **Real** que são formatados como moeda. Para esses campos, a propriedade é usada para transmitir o código da moeda para o aplicativo.

### <a name="datevalue-date"></a>dateValue (data)

Para os campos do tipo **Data**, essa propriedade transmite o valor de data do campo entre o servidor e o aplicativo.

## <a name="show-and-save-a-custom-field-in-the-timesheet-entry-section"></a>Mostrar e salvar um campo personalizado na seção de entrada de folha de ponto

Veja abaixo uma captura de tela do aplicativo móvel de uma criação de entrada de folha de ponto. Ela mostra os campos prontos para uso e um campo personalizado na seção "Entrada de tempo" chamada "Sequência de caracteres de teste" com um valor de enumeração da "Segunda opção" já definido.

![Campo personalizado de sequência de caracteres de teste no aplicativo](media/timesheet-entry.jpg)



Veja abaixo uma captura de tela do aplicativo móvel do usuário, selecionando uma das opções de enumeração disponíveis para o campo personalizado "Sequência de caracteres de teste".  As duas opções são "Primeira opção" e "Segunda opção" mostradas como botões de opção. A segunda opção está atualmente selecionada.

![Botões de opção para o campo personalizado de sequência de caracteres de teste](media/enum-option.jpg)



### <a name="extend-the-tstimesheetline-table-so-that-it-has-a-custom-field"></a>Estenda a tabela TSTimesheetLine para que ela tenha um campo personalizado

Em cenários típicos, é provável que os dados de um campo personalizado na seção de entrada de folha de ponto sejam salvos na tabela TSTimesheetLine. Contudo, outras tabelas podem ser usadas se os dados puderem ser recuperados com base em um registro TSTimesheetTrans fornecido ou se ele não tiver contexto de registro específico (por exemplo, se o campo estiver configurado como somente leitura nos parâmetros do projeto).

Observe que os campos personalizados não precisam ter nenhum registro de banco de dados de apoio. Eles podem ser gerados dinamicamente com base na lógica X++. Essa abordagem pode ser útil em cenários somente leitura (consulte a seção “Usar cadeia de comando na classe TSTimesheetDetails, no comando buildCustomFieldListForHeader para preencher detalhes da folha de ponto” para obter um exemplo de valores de campos personalizados gerados dinamicamente).

Veja abaixo uma captura de tela do Visual Studio da árvore de objetos de aplicativo. Ela mostra uma extensão da tabela TSTimesheetLine com o campo TestLineString adicionado como um campo personalizado.

![Sequência de caracteres da linha](media/b6756b4a3fc5298093327a088a7710fd.png)

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-timesheet-entry-section"></a>Use cadeia de comando no método buildCustomFieldList da classe TSTimesheetSettings para mostrar um campo na seção de entrada de folha de ponto

Este código controla as configurações de exibição do campo no aplicativo. Por exemplo, ele controla o tipo de campo, o rótulo, se o campo é obrigatório e em qual seção o campo aparece.

O exemplo a seguir mostra um campo de sequência de caracteres nas entradas de hora. Esse campo tem duas opções, **Primeira opção** e **Segunda opção**, que estão disponíveis por meio de botões de opção. O campo no aplicativo é associado ao campo **TestLineString** que é adicionado à tabela TSTimesheetLine.

Observe o uso do método **TSTimesheetCustomField::newFromMetatdata()** para simplificar a inicialização das propriedades do campo personalizado: **fieldBaseType**, **tableName**, **fieldname**, **label**, **isEditable**, **isMandatory**, **stringLength** e **numberOfDecimals**. Você também pode definir esses parâmetros manualmente, como preferir.

```
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('Second option');
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforentry-method-of-the-tstimesheetentry-class-to-enter-values-in-a-timesheet-entry"></a>Use cadeia de comando no método buildCustomFieldListForEntry da classe TSTimesheetEntry para inserir valores em uma entrada de folha de ponto

O método **buildCustomFieldListForEntry** é usado para inserir valores nas linhas de folha de ponto salvas no aplicativo móvel. Leva um registro TSTimesheetTrans como um parâmetro. Os campos desse registro podem ser usados para preencher o valor do campo personalizado no aplicativo.

```
...
[ExtensionOf(classStr(TsTimesheetEntry))]
final class TsTimesheetEntry_Extension
{
    protected List buildCustomFieldListForEntry(TSTimesheetTrans _tsTimesheetTrans)
    {
        List customFieldList = next buildCustomFieldListForEntry(_tsTimesheetTrans);
        TSTimesheetLine tsTimesheetLine = _tsTimesheetTrans.timesheetLine();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        tsTimesheetCustomField.parmStringValue(tsTimesheetLine.TestLineString);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('second option;);
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-tstimesheetentryservice-class-to-save-a-timesheet-entry-from-the-app-back-to-the-database"></a>Use a cadeia de comando na classe TSTimesheetEntryService para salvar uma entrada de folha de ponto do aplicativo no banco de dados

Para salvar um campo personalizado no banco de dados em uso típico, você deve estender vários métodos:

- O método **timesheetLineNeedsUpdating** é usado para determinar se o registro de linha foi alterado pelo usuário no aplicativo e deve ser salvo no banco de dados. Se o desempenho não é uma preocupação, esse método pode ser simplificado para que ele sempre retorne **verdadeiro**.
- Os métodos **populateTimesheetLineFromEntryDuringCreate** e **populateTimesheetLineFromEntryDuringUpdate** podem ser estendidos para inserir valores no registro do banco de dados TSTimesheetLine a partir do registro de contrato de dados TSTimesheetEntry fornecido. No exemplo a seguir, observe como o mapeamento entre o campo do banco de dados e o campo de entrada é feito manualmente por meio do código X++.
- O método **populateTimesheetWeekFromEntry** também pode ser estendido se o campo personalizado mapeado para o objeto **TSTimesheetEntry** precisar gravar na tabela de banco de dados TSTimesheetLineweek.

> [!NOTE]
> O exemplo a seguir salva o valor **firstOption** ou **secondOption** que o usuário seleciona no banco de dados como um valor de sequência de caracteres não processado. Se o campo do banco de dados for um campo do tipo **Enumeração**, esses valores poderão ser mapeados manualmente para um valor de enumeração e, em seguida, salvos em um campo de enumeração na tabela do banco de dados.

```
...
[ExtensionOf(classStr(TSTimesheetEntryService))]
final class TSTimesheetEntryService_Extension
{
    protected boolean timesheetLineNeedsUpdating(TSTimesheetLine _tsTimesheetLine,
    TsTimesheetEntry _tsTimesheetEntry)
    {
        boolean ret = next timesheetLineNeedsUpdating(_tsTimesheetLine,
        _tsTimesheetEntry);
        if (!ret)
        {
            */ Loop through custom fields to see if value needs updating*/
            ListEnumerator enumerator =  _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    */ If Custom field value for TestLineString field has changed, We need to update the timesheet line.*/
                    if (_tsTimesheetLine.TestLineString != customField.parmStringValue())
                    {
                        ret = true;
                    }
                }
            }
        }
        return ret;
    }
    protected void populateTimesheetLineFromEntryDuringCreate(TSTimesheetLine
    _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
    {
        next populateTimesheetLineFromEntryDuringCreate(_tsTimesheetLine,
        _tsTimesheetEntry);
        this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
        _tsTimesheetEntry);
        }
        protected void populateTimesheetLineFromEntryDuringUpdate(TSTimesheetLine
        \_tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            next populateTimesheetLineFromEntryDuringUpdate(_tsTimesheetLine,
            _tsTimesheetEntry);
            this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
            _tsTimesheetEntry);
        }
        private void populateTimesheetLineFromCustomFields(TSTimesheetLine
        _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            ListEnumerator enumerator =
            _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    _tsTimesheetLine.TestLineString = customField.parmStringValue();
                }
            }
        }
    }
...
```

## <a name="show-a-custom-field-in-the-timesheet-header-section"></a>Mostrar um campo personalizado na seção de cabeçalho de folha de ponto

Veja abaixo uma captura de tela do aplicativo móvel de um usuário que visualiza uma folha de ponto. O botão "Mais informações" foi selecionado no canto superior direito para mostrar a opção "Exibir mais detalhes".  

![Comando Exibir mais detalhes](media/show-more.png)

Veja abaixo uma captura de tela do aplicativo móvel mostrando a seção “Mais” de uma folha de ponto. Um campo personalizado chamado “Taxa de utilização desta folha de ponto (campo personalizado computado)” foi adicionado à seção de cabeçalho de folha de ponto. Um valor somente leitura de "0,667" é definido no campo personalizado.

![Seção Mais](media/more-section.jpg)

### <a name="extend-the-tstimesheettable-table-so-that-it-has-a-custom-field"></a>Estenda a tabela TSTimesheetTable para que ela tenha um campo personalizado

Em cenários típicos, é provável que os dados de um campo personalizado na seção de cabeçalho será extraído da tabela TSTimesheetHeader. Contudo, outras tabelas podem ser usadas se os dados puderem ser recuperados com base em um registro TSTimesheetTable fornecido ou se ele não tiver contexto de registro específico (por exemplo, se o campo estiver configurado como somente leitura nos parâmetros do projeto).

Observe que os campos personalizados não precisam ter nenhum registro de banco de dados de apoio. Eles podem ser gerados dinamicamente com base na lógica X++. O exemplo a seguir mostra essa abordagem.

Os campos na seção de cabeçalho são sempre somente leitura no aplicativo.

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-header-section"></a>Use cadeia de comando no método buildCustomFieldList da classe TSTimesheetSettings para mostrar um campo na seção do cabeçalho

Este código controla as configurações de exibição do campo no aplicativo. Por exemplo, ele controla o tipo de campo, o rótulo, se o campo é obrigatório e em qual seção o campo aparece.

O exemplo a seguir mostra um valor computado na seção de cabeçalho no aplicativo.

```
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforheader-method-of-the-tstimesheetdetails-class-to-fill-in-timesheet-details"></a>Use cadeia de comando no método buildCustomFieldListForHeader da classe TSTimesheetDetails para preencher os detalhes de folha de ponto

O método **buildCustomFieldListForHeader** é usado para preencher os detalhes do cabeçalho de folha de ponto no aplicativo para dispositivos móveis. Leva um registro TSTimesheetTable como um parâmetro. Os campos desse registro podem ser usados para preencher o valor do campo personalizado no aplicativo. O exemplo a seguir não lê nenhum valor do banco de dados. Em vez disso, ele usa a lógica X++ para gerar um valor computado que é exibido no aplicativo.


```
...
[ExtensionOf(classStr(TSTimesheetDetails))]
final class TSTimesheetDetails_Extension
{
    protected List buildCustomFieldListForHeader(TSTimesheetTable
    _tsTimesheetTable)
    {
        List customFieldList = next buildCustomFieldListForHeader(_tsTimesheetTable);
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        real utilizationRate = 0;
        if (_tsTimesheetTable.totalHours() != 0)
        {
            utilizationRate = _tsTimesheetTable.totalHoursBillable() /
            _tsTimesheetTable.totalHours();
        }
        tsTimesheetCustomField.parmRealValue(utilizationRate);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

## <a name="other-configurabilityextensibility-opportunities"></a>Outras oportunidades de configurabilidade/extensibilidade

### <a name="adding-additional-validation-for-the-app"></a>Adição de validação adicional para o aplicativo

A lógica existente para a funcionalidade de folha de ponto no nível do banco de dados ainda funcionará conforme o esperado. Para interromper a conclusão de salvar ou enviar operações e mostrar uma mensagem de erro específica, você pode adicionar **gerar erro ("mensagem para usuário")** ao código por meio de uma cadeia de extensão de comando. Veja três exemplos de métodos extensíveis úteis:

- Se **validateWrite** na tabela TSTimesheetLine retornar **falso** durante uma operação de salvamento para uma linha da folha de ponto, uma mensagem de erro será mostrada no aplicativo móvel.
- Se **validateSubmit** na tabela TSTimesheetTable retornar **falso** durante o envio da folha de ponto no aplicativo, uma mensagem de erro é mostrada ao usuário.
- A lógica que preenche os campos (por exemplo, **Propriedade da linha**) durante o método **inserir** na tabela TSTimesheetLine ainda será executada.

### <a name="hiding-and-marking-out-of-box-fields-as-read-only-via-configuration"></a>Ocultação e marcação de campos prontos para uso como somente leitura por meio de configuração

Nos parâmetros do projeto, você pode criar campos prontos para uso somente leitura ou ocultos no aplicativo para dispositivos móveis. Defina as opções na seção **Folhas de ponto móveis** na guia **Folha de ponto** da página **Parâmetros de gerenciamento e contabilidade de projetos**.

![Parâmetros do projeto](media/5753b8ecccd1d8bb2b002dd538b3f762.png)

### <a name="changing-the-activities-that-are-available-for-selection-via-extensions"></a>Alteração das atividades que estão disponíveis para seleção por meio de extensões

As atividades disponíveis para seleção de um projeto são preenchidas por meio dos métodos **getActivitiesForProject()** e **getActivityQuery()** na classe **TsTimesheetProjectService**. É possível usar a cadeia de comando para alterar esse comportamento para corresponder ao seu cenário de negócios para as atividades que estão disponíveis para seleção de um projeto específico.

### <a name="entering-a-default-project-category-on-timesheet-entries"></a>Inserção de uma categoria de projeto padrão nas entradas de folha de ponto

A entrada de uma categoria de projeto padrão nas entradas do quadro de horários ocorre em três níveis. Você pode usar a cadeia de comando para estender o comportamento em qualquer um ou todos esses níveis para obter o comportamento desejado. Esta é a hierarquia usada:

1. O aplicativo tenta colocar a categoria padrão do recurso do projeto. Essa categoria padrão é definida nos métodos**getCurrentUserResource** e **getDelegatedResourcesForCurrentUser** na classe **TSTimesheetSettingsService**.
2. Se a categoria padrão não for fornecida no nível do recurso do projeto, o aplicativo tentará extraí-la da atividade do projeto. Essa categoria padrão é definida no método **getActivitiesForProject** na classe **TSTimesheetProjectService**.
3. Se a categoria padrão não for fornecida no nível de atividade do projeto, a categoria padrão será obtida dos parâmetros do projeto. Essa categoria padrão é definida no método **getProjectDetailsbyRule** na classe **TSTimesheetProjectService**.
