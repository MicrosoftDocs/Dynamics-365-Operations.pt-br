---
title: Projetar relatórios multilíngues em Relatórios eletrônicos
description: Este tópico explica como você pode usar etiquetas de Relatório eletrônico (ER) para criar e gerar relatórios multilíngues.
author: NickSelin
ms.date: 09/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f5a2e8cca441189020e6274248a48c5e9dd80e00
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753543"
---
# <a name="design-multilingual-reports-in-electronic-reporting"></a>Projetar relatórios multilíngues em Relatórios eletrônicos

[!include[banner](../includes/banner.md)]

## <a name="overview"></a>Visão Geral

Como um usuário comercial, você pode usar a estrutura de [Relatório eletrônico (ER)](general-electronic-reporting.md) para configurar formatos para documentos de saída que precisam ser gerados de acordo com os requisitos legais de vários países ou regiões. Quando esses requisitos exigirem que os documentos de saída sejam gerados em diferentes idiomas para países ou regiões diferentes, você poderá configurar um único [formato](general-electronic-reporting.md#FormatComponentOutbound) de ER que contenha recursos dependentes de idioma. Dessa forma, você pode reutilizar o formato para gerar documentos de saída para vários países ou regiões. Você também pode usar um único formato de ER para gerar um documento de saída em diferentes idiomas para clientes, fornecedores, subsidiárias ou outros participantes correspondentes.

Você pode configurar os modelos de dados de ER e mapeamentos de modelo como fontes de dados dos formatos de ER configurados para definir o fluxo de dados que especifica quais dados de aplicativo são colocados em documentos gerados. Como um [provedor](general-electronic-reporting.md#Provider) de configuração de ER, você pode [publicar ](tasks/er-upload-configuration-into-lifecycle-services.md#upload-a-configuration-into-lcs) [modelos de dados](general-electronic-reporting.md#data-model-and-model-mapping-components), [mapeamentos de modelo](general-electronic-reporting.md#data-model-and-model-mapping-components) e [formatos](general-electronic-reporting.md#FormatComponentOutbound) configurados como componentes de uma solução de ER para gerar documentos de saída específicos. Você também pode permitir que os clientes [carreguem](general-electronic-reporting-manage-configuration-lifecycle.md) a solução de ER publicada de forma que ela possa ser usada e personalizada. Se esperar que talvez os clientes falem em outros idiomas, você poderá configurar os componentes de ER para que eles contenham recursos dependentes de idioma. Dessa forma, o conteúdo de um componente de ER editável pode ser apresentado no idioma preferencial do usuário do cliente em tempo de design.

Você pode configurar recursos dependentes do idioma como etiquetas de ER. Em seguida, você poderá usar essas etiquetas para configurar os componentes de ER para as seguintes finalidades:

- Em tempo de design:

    - Apresente o conteúdo dos componentes de ER configurados no idioma preferencial do usuário.

- Em runtime:

    - Gere conteúdo dependente do idioma para documentos de saída.
    - Forneça mensagens de aviso e de erro no idioma preferencial do usuário.
    - Solicite campos obrigatórios no idioma preferencial do usuário.

As etiquetas de ER podem ser configuradas em cada [configuração](general-electronic-reporting.md#Configuration) de ER que contém componentes diferentes. As etiquetas podem ser mantidas independentemente da lógica configurada dos modelos de dados de ER, dos mapeamentos de modelo de ER e dos componentes de formato de ER.

Cada etiqueta de ER é identificada por uma ID exclusiva no escopo da configuração de ER que contém essa etiqueta. Cada etiqueta pode conter texto para cada idioma com suporte na instância atual do Microsoft Dynamics 365 Finance. Esses idiomas com suporte incluem os idiomas das personalizações implantadas.

## <a name="entry"></a>Entrada

Quando um modelo de dados de ER é projetado, um mapeamento de modelo de ER ou um formato de ER, a opção **Traduzir** é mostrada sempre que você seleciona um campo que possa conter o contexto traduzível. Ao selecionar essa opção, você poderá vincular o campo selecionado a uma etiqueta de ER no <a name="TextTranslationPane">painel</a> **Tradução de texto**. Você pode selecionar uma etiqueta de ER existente ou pode adicionar um nova etiqueta de ER, se ainda não estiver disponível. Ao selecionar ou adicionar uma etiqueta de ER, você poderá adicionar texto relacionado para cada idioma com suporte na atual instância do Finance.

A ilustração a seguir mostra como essa tradução é feita em um modelo de dados de ER editável. Neste exemplo, o atributo **Descrição** do campo **PurchaseOrder** do **Modelo de fatura** editável é traduzido nos idiomas alemão austríaco (de-at) e japonês (ja).

![Como fornecer tradução de uma etiqueta de ER no designer de modelos de dados de ER](./media/er-multilingual-labels-refer.png)

Somente o texto da etiqueta para etiquetas que residem em um componente de ER editável pode ser traduzido. Por exemplo, se você selecionar **Traduzir** para o atributo de etiqueta de uma fonte de dados de mapeamento do modelo de ER e selecionar uma etiqueta de ER que reside no modelo de dados de ER pai, verá o conteúdo da etiqueta, mas não poderá alterá-lo. Nesses casos, o campo **Texto traduzido** não estará disponível, conforme mostrado na ilustração a seguir.

![Como analisar a tradução fornecida de uma etiqueta de ER no designer de mapeamento de modelo de ER](./media/er-multilingual-labels-refer-mapping.png)

> [!NOTE]
> Não é possível usar os designers para excluir etiquetas que foram inseridos em um componente de ER editável.

## <a name="scope"></a>Escopo

É possível fazer referência a etiquetas de ER em vários atributos traduzíveis de componentes de ER.

### <a name="data-model-component"></a>Componente do modelo de dados

Ao configurar um modelo de dados de ER, você poderá adicionar etiquetas de ER a ele. Os atributos **Etiqueta** e **Descrição** do item de modelo, de cada campo de modelo e de cada <a id="LinkModelEnum"></a>valor de enumeração de modelo podem ser vinculados a uma etiqueta de ER que é adicionado ao modelo de dados de ER.

![Como fornecer tradução para o atributo Descrição no designer de modelos de dados de ER](./media/er-multilingual-labels-refer.png)

Quando um modelo de dados de ER é configurado dessa forma, seu conteúdo será apresentado aos usuários do designer de modelos de dados de ER no idioma preferencial de cada usuário. Portanto, a manutenção do modelo é simplificada. As ilustrações a seguir mostram como essa funcionalidade funciona para usuários que têm DE-AT e JA definidos como seu idioma preferido.

![Layout do designer de modelos de dados de ER para um usuário com DE-AT definido como o idioma preferencial](./media/er-multilingual-labels-refer-de.png)

![Layout do designer de modelos de dados de ER para um usuário com JA definido como seu idioma preferencial](./media/er-multilingual-labels-refer-ja.png)

### <a name="model-mapping-component"></a>Componente de mapeamento de modelos

Como o mapeamento do modelo de ER se baseia em um modelo de dados de ER, as etiquetas dos elementos do modelo de dados referenciados são exibidas no idioma preferencial do usuário no designer de mapeamento do modelo. A ilustração a seguir mostra como o significado do campo **PurchaseOrder** é explicado no mapeamento do modelo editável usando a etiqueta do atributo **Descrição** que foi adicionado ao modelo de dados configurado. Observe que essa etiqueta é apresentada no idioma preferencial do usuário (DE-AT, neste exemplo).

![Layout do designer de mapeamento de modelo de ER para um usuário com DE-AT definido como o idioma preferencial](./media/er-multilingual-labels-show-mapping.png)

Quando o atributo **Etiqueta** da fonte de dados **Parâmetro de entrada do usuário** é configurado como vinculado a uma etiqueta de ER, o campo de parâmetro correspondente a essa fonte de dados é apresentado na caixa de diálogo do usuário em runtime para os usuários no idioma preferencial.

### <a name="format-component"></a>Componente de formato

Ao configurar um formato de ER, você poderá adicionar etiquetas de ER a ele. Os atributos **Etiqueta** e **Texto da ajuda** de cada fonte de dados configurada podem ser vinculados a uma etiqueta de ER adicionada ao formato de ER. Os atributos **Etiqueta** e **Descrição** de cada <a id="LinkFormatEnum"></a>valor de enumeração de formato também podem ser vinculados a uma etiqueta de ER que pode ser acessada desde o formato de ER editável.

> [!NOTE]
> Você também pode vincular esses atributos a uma etiqueta de ER do modelo de dados de ER pai que reutiliza as etiquetas do modelo em todos os formatos de ER configurados para esse modelo de dados de ER.

Quando um formato de ER é configurado dessa forma, o conteúdo do formato será apresentado aos usuários do designer de Operação do ER no idioma preferencial de cada usuário. Portanto, a manutenção do formato e a análise da lógica configurada são simplificadas.

Como o formato de ER ER se baseia em um modelo de dados de ER, as etiquetas referenciadas nos elementos do modelo de dados são apresentadas no designer de formato de ER no idioma preferencial do usuário.

Quando o atributo **Etiqueta** da fonte de dados **Parâmetro de entrada do usuário** é configurado como vinculado a uma etiqueta de ER, o campo de parâmetro correspondente ao parâmetro na caixa de diálogo do usuário em runtime é apresentado ao usuário como um prompt. As ilustrações a seguir mostram como é possível vincular o atributo **Etiqueta** da fonte de dados **Parâmetro de entrada do usuário** em tempo de design a uma etiqueta de ER, para que os usuários sejam solicitados a fornecer o parâmetro em diferentes idiomas preferenciais do usuário (mostrados para os idiomas inglês dos Estados Unidos (en-US) e DE-AT) em runtime.

![Como fornecer tradução de atributos de um parâmetro de entrada do usuário no designer de Operação do ER](./media/er-multilingual-labels-refer-format.png)

![Processamento de pagamento de Fornecedor de ER em runtime para o idioma preferencial do usuário EN-US](./media/er-multilingual-labels-show-runtime-en.png)

![Processamento de pagamento de Fornecedor de ER em runtime para o idioma preferencial do usuário DE-AT](./media/er-multilingual-labels-show-runtime-de.png)

### <a name="expressions"></a>Expressões

Para usar uma etiqueta em uma [expressão](er-formula-language.md) de ER, você deverá usar a sintaxe **@"GER\_LABEL:X"**, em que o prefixo **@** indica que o operando se refere a uma etiqueta, **GER\_LABEL** indica que uma etiqueta de ER está envolvida e **X** é a ID da etiqueta de ER.

![Como configurar uma expressão de ER contendo uma referência a uma etiqueta de ER no designer de fórmulas de ER](./media/er-multilingual-labels-expression1.png)

Para fazer referência a uma etiqueta de sistema (aplicativo), use a sintaxe **@"X"**, em que o prefixo **@** indica que o operando se refere a uma etiqueta, e **X** é a ID da etiqueta do sistema.

![Como configurar uma expressão de ER contendo uma referência a uma etiqueta de aplicativo designer de fórmulas de ER](./media/er-multilingual-labels-expression2.png)

#### <a name="model-mapping"></a>Mapeamento de modelo

Uma expressão de um mapeamento de modelo de ER pode ser configurada usando uma etiqueta. Quando esse mapeamento é chamado por um formato de ER executado para gerar um documento de saída, o contexto da execução inclui um código de idioma. Uma etiqueta de expressão configurada será preenchida com o texto da etiqueta que foi configurada para o idioma desse contexto.

Se uma etiqueta referenciado não tiver tradução para o idioma do contexto de execução de formato que chama o mapeamento do modelo, será usado o texto da etiqueta no idioma EN-US.

#### <a name="format"></a>Formatar

Uma expressão de ER de um formato de ER pode ser configurada usando etiquetas. Quando esse formato é executado para gerar um documento de saída, o contexto da execução inclui um código de idioma. Uma etiqueta de expressão configurada será preenchida com o texto da etiqueta que foi configurada para o idioma desse contexto.

![Como fornecer tradução de uma etiqueta de ER da expressão de ER editável no designer de fórmulas de ER](./media/er-multilingual-labels-refer-in-expression.png)

![Exemplo de associação de dados que se refere a uma etiqueta de ER no designer de Operação do ER](./media/er-multilingual-labels-refer-in-binding.png)

Você pode configurar o componente **ARQUIVO** de um formato de ER para gerar o relatório no idioma preferencial do usuário.

![Configure o componente ARQUIVO no designer de Operação do ER para gerar o relatório no idioma preferencial do usuário](./media/er-multilingual-labels-language-context-user.png)

Se você configurar um formato de ER dessa forma, o relatório será gerado usando o texto correspondente das etiquetas de ER. As ilustrações a seguir mostram exemplos de relatórios para os idiomas do usuário EN-US e DE-AT.

![A visualização do relatório que foi gerada no idioma preferencial do usuário EN-US](./media/er-multilingual-labels-report-preview-en.png)

![A visualização do relatório que foi gerada no idioma preferencial do usuário DE-AT](./media/er-multilingual-labels-report-preview-de.png)

Se uma etiqueta referenciada não tiver tradução para o idioma do contexto de execução de formato, será usado o texto da etiqueta no idioma EN-US.

## <a name="language"></a>Idioma

O ER oferece suporte a diferentes maneiras de especificar um idioma para um relatório gerado. No campo **Preferências de idioma** na guia **Formatar**, você pode selecionar os seguintes valores:

- **Preferência da empresa** – gere um relatório em um idioma especificado pela empresa.

    ![Especificar no designer de Operação do ER um idioma preferencial da empresa como o idioma de um relatório gerado](./media/er-multilingual-labels-language-context-company.png)

- **Preferência do usuário** – gere um relatório no idioma preferencial do usuário.
- **Explicitamente definido** – gere um relatório em um idioma especificado no tempo de design.

    ![Especificar no designer de Operação do ER um idioma definido em tempo de design como o idioma de um relatório gerado](./media/er-multilingual-labels-language-context-fixed.png)

- **Definido em runtime** – gere um relatório em um idioma especificado em runtime. Se você selecionar esse valor, no campo **Idioma**, configure uma expressão de ER que retorne o código do idioma, como o idioma do cliente correspondente.

    ![Especificar no designer de Operação do ER um idioma definido em runtime como o idioma de um relatório gerado](./media/er-multilingual-labels-language-context-runtime.png)

## <a name="translation"></a>Tradução

Você pode adicionar etiquetas de ER necessárias a um componente de ER editável. Quando uma etiqueta de ER é adicionada, ela pode ser traduzida de duas maneiras: manual e automaticamente.

### <a name="manual-translation"></a>Tradução manual

Ao adicionar uma etiqueta de ER no [painel](#TextTranslationPane) **Tradução de texto**, você poderá convertê-la manualmente em todos os idiomas com suporte na instância atual do Finance. Você pode selecionar o idioma preferencial no campo **Idioma** na seção **Idioma do sistema** ou **Idioma do usuário**, insira o texto apropriado no campo **Texto traduzido** correspondente e, em seguida, selecione **Traduzir**. Esse processo deve ser repetido para cada idioma necessário e para todas as etiquetas adicionadas.

### <a name="automatic-translation"></a>Tradução automática

A configuração de um componente de ER é feita na versão de rascunho da configuração de ER na qual o componente de ER editável reside.

![Página Configurações de ER oferecendo acesso à versão da configuração no status Rascunho](./media/er-multilingual-labels-configurations.png)

Conforme descrito anteriormente neste tópico, você pode adicionar etiquetas de ER necessárias a um componente de ER editável. Dessa forma, você pode especificar o texto das etiquetas ER no idioma EN-US. Em seguida, você poderá exportar as etiquetas do componente de ER usando a função de ER interna. Selecione a versão de rascunho de uma configuração de ER que contém o componente de ER editável e selecione **Câmbio \> Exportar etiquetas**.

![Página Configurações de ER que permite exportar etiquetas de ER da versão de configuração selecionada](./media/er-multilingual-labels-export.png)

Você pode exportar todas as etiquetas ou as etiquetas de um único idioma especificado no início da exportação. As etiquetas são exportadas como um arquivo zip que contém arquivos XML. Todo arquivo XML contém etiquetas para um único idioma.

![Exemplo do arquivo exportado que contém as etiquetas de ER para o idioma DE-AT](./media/er-multilingual-labels-in-xml.png)

Esse formato é usado para a tradução automática de etiquetas por serviços de tradução externos, como o [Dynamics 365 Translation Service](../lifecycle-services/translation-service-overview.md). Ao receber as etiquetas traduzidas, você poderá importá-las novamente para a versão de rascunho de uma configuração de ER que contém os componentes de ER que possuem essas etiquetas. Selecione a versão de rascunho de uma configuração de ER que contém o componente de ER editável e selecione **Câmbio \> Carregar etiquetas**.

![Página Configurações de ER que permite importar etiquetas de ER para a versão de configuração selecionada](./media/er-multilingual-labels-load.png)

As etiquetas traduzidas serão importadas para a configuração de ER selecionada. As etiquetas traduzidas que existem na configuração de ER são substituídas. Se houver alguma etiqueta traduzido na configuração de ER, ela será anexada.

## <a name="lifecycle"></a>Ciclo de vida

As etiquetas de um componente de ER que podem ser editadas são mantidas, juntamente com outro conteúdo para o componente, na versão apropriada de uma configuração de ER.

Etiquetas de um componente ER base podem ser referenciadas em uma versão derivada do componente de ER que você cria para apresentar suas modificações.

Atribuição de etiqueta de controles de versão de ER para qualquer atributo em um componente de ER. As alterações na atribuição de etiqueta são registradas na lista de alterações (delta) de um componente de ER editável que foi criado como uma versão derivada do componente de ER fornecido. Essas alterações serão validadas quando uma versão derivada for baseada novamente em uma nova versão base.

## <a name="functions"></a>Funções

A função [LISTOFFIELDS](er-functions-list-listoffields.md) interna pode acessar as etiquetas de ER que foram configuradas para alguns itens dos componentes de ER.

Conforme descrito anteriormente neste tópico, os atributos **Etiqueta** e **Descrição** de cada valor da enumeração de ER [modelo](#LinkModelEnum) ou [formato](#LinkFormatEnum) podem ser vinculados a uma etiqueta de ER que pode ser acessado no componente de ER apropriado. Você pode configurar uma expressão de ER na qual chama a função **LISTOFFIELDS** usando a enumeração de ER como um argumento. Essa expressão retorna uma lista que contém um registro para cada valor de uma enumeração de ER que foi definida como um argumento dessa função. Cada registro contém o valor de uma etiqueta de ER vinculada a um valor de enumeração de ER:

- O valor de uma etiqueta de ER vinculado aos atributos **Etiqueta** é armazenado no campo **Etiqueta** do registro retornado.
- O valor de uma etiqueta de ER vinculada aos atributos **Descrição** é armazenado no campo **Descrição** do registro retornado.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral do Relatório Eletrônico](general-electronic-reporting.md)
- [Funções do Relatório eletrônico](er-formula-language.md#functions)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]