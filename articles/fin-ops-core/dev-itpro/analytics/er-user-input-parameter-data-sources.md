---
title: Usar fontes de dados de PARÂMETRO DE ENTRADA DO USUÁRIO para especificar parâmetros para um relatório
description: Este artigo explica como usar fontes de dados de PARÂMETRO DE ENTRADA DO USUÁRIO para especificar parâmetros para relatórios gerados por você.
author: kfend
ms.date: 04/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Version 10.0.27
ms.custom: 220314
ms.assetid: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
ms.openlocfilehash: c6d0f1a0d9c5eb70a9812459a25d5b14407cce7a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278697"
---
# <a name="use-user-input-parameter-data-sources-to-specify-parameters-for-a-report"></a>Usar fontes de dados de PARÂMETRO DE ENTRADA DO USUÁRIO para especificar parâmetros para um relatório

[!include[banner](../includes/banner.md)]

Ao criar os componentes [Relatório Eletrônico](general-electronic-reporting.md) (ER) [mapeamento de modelo](er-overview-components.md#model-mapping-component) e [formato](er-overview-components.md#format-component) ER, você pode usar fontes de dados de um tipo *PARÂMETRO DE ENTRADA DO USUÁRIO* para obter os valores necessários que podem ser especificados nos campos de entrada de dados na caixa de diálogo no runtime, antes de começar a execução de um formato ER. Este artigo descreve as fontes de dados de *PARÂMETRO DE ENTRADA DO USUÁRIO* que têm suporte no momento.

## <a name="mandatory-properties"></a><a name="mandatory-properties"></a>Propriedades obrigatórias

Você deve especificar as seguintes propriedades para fontes de dados de cada tipo *PARÂMETRO DE ENTRADA DO USUÁRIO*:

- No campo **Nome**, insira o nome interno da fonte de dados. Você pode usar esse nome em outras [expressões](er-formula-language.md) e associações do componente de mapeamento ou de formato de modelo configurado.

## <a name="optional-properties"></a><a name="optional-properties"></a>Propriedades opcionais

Opcionalmente, você pode especificar as seguintes propriedades para fontes de dados de um tipo *PARÂMETRO DE ENTRADA DO USUÁRIO*:

- No campo **Etiqueta**, especifique a etiqueta usada para o campo de entrada de dados relacionado na caixa de diálogo no runtime. Você pode adicionar texto de etiquetas diferentes para códigos de idiomas diferentes ativando o campo **Etiqueta** e selecionando **Traduzir**.
- No campo **Ajuda**, especifique o texto de ajuda mostrado no tempo de design na parte inferior da página **Designer de formato** ou da página **Designer de mapeamento de modelos** quando uma fonte de dados editável de um tipo *PARÂMETRO DE ENTRADA DO USUÁRIO* for selecionada. Esse texto pode fornecer detalhes adicionais sobre a fonte de dados para ajudar os usuários a configurar o componente de formato editável ou de mapeamento de modelo. Você pode adicionar um texto de ajuda diferente para códigos de idiomas diferentes, selecionando **Traduzir**.

    > [!NOTE]
    > O botão **Traduzir** que pode ser usado para adicionar [etiquetas e texto específicos de idioma](er-design-multilingual-reports.md#format-component) só é disponibilizado depois que você adiciona a fonte de dados, salva as alterações e reabre a fonte de dados para edição.

- No campo **Somente leitura**, configure uma expressão que retorne um valor *[Booliano](er-formula-supported-data-types-primitive.md#boolean)*.

    - Se a expressão configurada retornar um valor **Verdadeiro** no runtime, o campo de entrada de dados relacionado aparecerá esmaecido na caixa de diálogo e você não poderá alterar o valor.
    - Se a expressão configurada retornar um valor **Falso** no runtime, ou se nenhuma expressão for configurada, o campo de entrada de dados relacionado será disponibilizado na caixa de diálogo e você poderá alterar o valor.

- No campo **Valor padrão**, configure uma expressão que retorne o valor do tipo de parâmetro referenciado. Este valor pode ser usado para preencher um valor padrão para o campo de entrada de dados relacionado na caixa de diálogo no runtime.

    Quando você executa um formato ER, o valor inserido no campo de entrada de dados relacionado na caixa de diálogo no runtime é salvo na memória como o valor usado anteriormente. Os valores usados anteriormente são salvos individualmente para cada campo, executando o formato ER, o usuário atual e a organização atual (empresa).

    - Defina a opção **Sempre redefinir para o valor padrão** como **Sim** se o valor retornado pela expressão **Valor padrão** deve sempre ser usado como o valor padrão, independentemente do valor usado anteriormente.
    - Defina a opção **Sempre redefinir para o valor padrão** como **Não** se o valor retornado pelo valor de expressão **Valor padrão** precisar ser usado como o valor padrão somente quando o valor usado anteriormente estiver ausente.

    > [!NOTE]
    > Se você definir a opção **Sempre redefinir para o valor padrão** como **Sim**, uma expressão deverá ser configurada no campo **Valor padrão**.

- Se você definir a opção **Permitir várias seleções** como **Sim**, poderá selecionar vários valores para o parâmetro configurado no runtime. Se você defini-la como **Não**, só poderá selecionar um único valor.

    > [!NOTE]
    > Esta opção não se aplica a todos os tipos de *PARÂMETRO DE ENTRADA DO USUÁRIO*. Em tempo de design, uma exceção é lançada para informar ao usuário que o parâmetro de entrada do usuário configurado não dá suporte à seleção múltipla, e que apenas um único valor pode ser selecionado ou inserido.
    >
    > Se você definir a opção **Permitir várias seleções** como **Sim**, e especificar uma expressão no campo **Valor padrão**, essa expressão poderá ser usada para definir apenas um único valor padrão.

- Selecione a opção **Editar visibilidade** para especificar se o parâmetro configurado deve ser mostrado na caixa de diálogo no runtime.

    > [!NOTE]
    > A visibilidade padrão de fontes de dados de um tipo de *PARÂMETRO DE ENTRADA DO USUÁRIO* depende do componente ER que as mantém.
    >
    > - Se uma fonte de dados estiver configurada no componente de formato, ela ficará visível por padrão.
    > - Se uma fonte de dados estiver configurada no componente de mapeamento de modelos, ela ficará visível apenas se o valor da fonte de dados afetar o resultado quando um componente ER for executado. Por exemplo, você adicionou uma fonte de dados, mas não a utilizou em expressões e associações do componente de mapeamento de modelo atual. Nesse caso, por padrão, o campo de entrada de dados relevante não será mostrado na caixa de diálogo no runtime. 

    Na página **Designer de fórmulas**, no campo **Fórmula**, configure uma expressão que retorne um valor *Booliano*.

    - Se a expressão configurada retornar um valor **Verdadeiro** no runtime, ou se nenhuma expressão for configurada, o campo de entrada de dados relacionado ficará visível na caixa de diálogo no runtime.
    - Se a expressão configurada retornar um valor **Falso**, o campo de entrada de dados relacionado ficará oculto na caixa de diálogo no runtime. Quando ele é chamado por outras expressões no runtime, ele retorna o valor padrão, o valor usado anteriormente ou o padrão para o valor do tipo de dados atual, dependendo de outras configurações.

## <a name="type-specific-properties"></a>Propriedades específicas do tipo

### <a name="application-dependent-user-input-parameter"></a>Parâmetro de entrada do usuário dependente da aplicação

Use uma fonte de dados do tipo **Geral** \> **Parâmetro de entrada de usuário** para obter os valores necessários de um tipo de dados especificado para a instância atual da aplicação Microsoft Dynamics 365 Finance. Ao adicionar uma fonte de dados deste tipo a um componente ER, especifique as seguintes propriedades:

- No campo **Nome do tipo de dados de operações (EDT, enum)**, selecione um [tipo de dados estendidos (EDT)](../extensibility/extensible-edts.md) da aplicação ou uma enumeração de aplicativo.

> [!NOTE]
> É recomendável revisar as expressões configuradas nos campos **Somente leitura** e **Valor padrão** ao alterar a referência **Nome do tipo de dados de operações (EDT, enum)** em uma fonte de dados editável deste tipo de *PARÂMETRO DE ENTRADA DO USUÁRIO*.

A ilustração a seguir mostra as propriedades da fonte de dados `$TaxRegNum` que foi definida na configuração do formato ER **Instat XML (DE)**. Esta fonte de dados é configurada para usar o EDT *Descrição* para oferecer o campo de entrada de dados **Número de inscrição de imposto** na caixa de diálogo no runtime.

![Propriedades de uma fonte de dados do tipo PARÂMETRO DE ENTRADA DO USUÁRIO na caixa de diálogo da página Designer de formatação.](./media/er-user-input-parameter-data-sources-01.png)

A ilustração a seguir mostra a caixa de diálogo mostrada no runtime quando a configuração de formato ER de **Instat XML (DE)** é executada para [gerar](../../../finance/localizations/tasks/eur-00002-eu-intrastat-declaration.md) a declaração Intrastat. Observe que o campo **Número de inscrição de imposto** está disponível para entrada de dados.

![Caixa de diálogo Relatório Intrastat do formato de ER em execução na página Intrastat.](./media/er-user-input-parameter-data-sources-02.png)

### <a name="data-model-enumeration-user-input-parameter"></a>Parâmetro de entrada do usuário de enumeração de modelo de dados

Use uma fonte de dados do tipo **Modelo de dados** \> **Parâmetro de entrada de usuário de enumeração** para obter os valores necessários de uma [enumeração](er-formula-supported-data-types-primitive.md#enumeration) de um único modelo de dados. Ao adicionar uma fonte de dados deste tipo a um componente ER, especifique as seguintes propriedades:

- No campo **Modelo**, especifique uma referência para o modelo de dados base.
- No campo **Enumeração de modelo**, especifique uma referência a uma enumeração do modelo de dados referenciado.
- No campo **Versão**, selecione o número da revisão do componente do modelo de dados ER que contém a enumeração do modelo referenciado.

    > [!TIP]
    > Em tempo de design, você pode deixar o campo **Versão** em branco para acessar a lista de enumerações do componente do modelo de dados referenciado que reside na versão de rascunho da configuração do modelo de dados ER correspondente. Dessa forma, você pode editar simultaneamente a versão de rascunho do componente de mapeamento de modelos ou de formato e a versão de rascunho do componente do modelo de dados base.
    >
    > No entanto, observe que o campo **Versão** pode ser deixado em branco somente na versão de rascunho de um componente de mapeamento de modelo ou de formato. Quando você altera o status de um mapeamento de modelo de ER ou uma configuração de formato de **Rascunho** para **Concluído**, este campo é preenchido automaticamente pelo número de revisão de modelo mais alto disponível na instância atual do Finance. Se você inserir uma nova enumeração ou um novo valor de enumeração na versão de rascunho do modelo de dados base e referir-se a ela no componente de mapeamento de modelo ou de formato editável, complete a versão de rascunho da configuração do modelo de dados base antes que a versão de rascunho do mapeamento de modelos ER ou a configuração de formato seja concluída. Caso contrário, uma exceção "Caminho não encontrado" será lançada quando você alterar o status do mapeamento do modelo ou da configuração de formato de **Rascunho** para **Concluído**. A mensagem informará que o valor de enumeração ou a enumeração referenciada está faltando no modelo de dados base.

A ilustração a seguir mostra as propriedades da fonte de dados `$ReportDirection` que foi definida na configuração do formato ER **Instat XML (DE) Contoso**. A configuração de **Instat XML (DE) Contoso** foi [derivada](general-electronic-reporting.md#Configuration) da configuração de **Instat XML (DE)**. Esta fonte de dados é configurada para usar a enumeração de modelo *ReportDirection* para oferecer o campo de pesquisa apropriado na caixa de diálogo no runtime.

![Propriedades da fonte de dados do tipo PARÂMETRO DE ENTRADA DO USUÁRIO na caixa de diálogo da página Designer de formatação.](./media/er-user-input-parameter-data-sources-03.png)

### <a name="format-enumeration-user-input-parameter"></a>Parâmetro de entrada de usuário de enumeração de formato

Use uma fonte de dados do tipo **Enumeração de formato** \> **Parâmetro de entrada de usuário de enumeração** para obter os valores necessários de uma enumeração de formato único. Ao adicionar uma fonte de dados deste tipo a um componente ER, especifique as seguintes propriedades:

- No campo **Enumeração de formato**, especifique uma enumeração do formato editável.

> [!NOTE]
> As fontes de dados deste tipo podem ser configuradas somente no escopo do componente de formatação editável.

## <a name="additional-resources"></a>Recursos adicionais

[Designer de fórmulas no Relatório eletrônico](general-electronic-reporting-formula-designer.md)

[Iniciar os valores de fonte de dados do tipo USER INPUT PARAMETER do código-fonte](er-initiate-uip-data-source-value-from-source-code.md)
