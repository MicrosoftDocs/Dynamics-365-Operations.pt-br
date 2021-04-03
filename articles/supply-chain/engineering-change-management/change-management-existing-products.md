---
title: Habilitar gerenciamento de modificações em produtos existentes
description: Este tópico explica como você pode habilitar o gerenciamento de alterações para produtos existentes. Ele também descreve casos em que a capacidade de habilitar o gerenciamento de alterações é limitada.
author: t-benebo
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-05-02
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 8b9f34f5980937da62610d9668a95816ba6054ef
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500853"
---
# <a name="enable-change-management-on-existing-products"></a>Habilitar gerenciamento de modificações em produtos existentes

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico explica como você pode habilitar o gerenciamento de alterações para produtos existentes. Ele também descreve casos em que a capacidade de habilitar o gerenciamento de alterações é limitada.

Ao habilitar o gerenciamento de alterações para um produto existente, você pode criar versões desse produto e rastrear as alterações feitas a ele durante toda a sua vida. Portanto, você pode rastrear essas alterações usando ordens de alteração. Para habilitar o gerenciamento de alterações, você deve converter os produtos relevantes em *itens de engenharia* (também conhecidos como produtos de engenharia). Os produtos de engenharia são produtos com versão e que são gerenciados por meio do gerenciamento de alterações. Um assistente é fornecido para orientar você durante o processo de conversão.

## <a name="turn-on-the-feature-in-your-system"></a>Ative o recurso no seu sistema

Para usar esse recurso, você deve concluir as seguintes tarefas:

1. Habilite o recurso Gerenciamento de alterações de engenharia e sua chave de configuração conforme descrito em [Visão geral do gerenciamento de alterações de engenharia](product-engineering-overview.md).
1. Ative o recurso *Habilitar o gerenciamento de alterações em produtos existentes* no gerenciamento de recursos. Para obter mais informações, consulte [Visão geral do Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="restrictions-and-limitations"></a>Restrições e limitações

Nem todos os tipos de produtos podem ser convertidos em todos os outros tipos. As seguintes restrições e limitações são aplicáveis:

- Quando você converte um produto em um produto de engenharia, ele continua sendo um *produto*. Ele não se torna um *produto mestre*.
- Quando você converte um produto mestre que tenha um conjunto específico de dimensões, essas dimensões são mantidas após a alteração. Por exemplo, se você converter um produto mestre que tenha a dimensão de tamanho, ele manterá a dimensão de tamanho.

Portanto, se tiver um produto distinto, você poderá alterá-lo somente para um produto de engenharia que não rastreie a dimensão do produto nas transações (ou seja, a dimensão da versão não seja usada). Consulte as seções restantes deste tópico para obter mais informações sobre esses problemas.

## <a name="prepare-for-conversion-by-creating-all-required-engineering-product-categories"></a>Preparar para conversão criando todas as categorias de produtos de engenharia necessárias

Uma *categoria de produto de engenharia* deve ser atribuída a todos os produtos de engenharia. Você fará essa atribuição quando executar o assistente para **Converter em produto de engenharia**. As categorias de produtos de engenharia devem existir para todos os produtos padrão relevantes *antes* que eles possam ser convertidos.

A categoria de produto de engenharia fornecem a base para a criação de um produto de engenharia e estabelece um conjunto de valores e políticas padrão. A categoria de produto de engenharia deve corresponder ao produto ao qual ela foi atribuída. Por exemplo, o tipo de produto e o grupo de dimensões devem corresponder com o produto e com sua categoria de produto de engenharia. Para obter mais informações, consulte [Versões de engenharia e categorias de produto de engenharia](engineering-versions-product-category.md).

> [!IMPORTANT]
> O assistente para **Converter em produto de engenharia** pode converter o produto somente em produtos de engenharia nos quais a versão não é rastreada nas transações. Portanto, a opção **Rastrear versão nas transações** deve ser definida como *Não* para as categorias de produtos de engenharia que você cria para converter os produtos existentes.

Para obter mais informações sobre como criar categorias de produtos de engenharia, consulte [Versões de engenharia e categorias de produtos de engenharia](engineering-versions-product-category.md).

## <a name="run-the-convert-to-engineering-product-wizard"></a>Executar o assistente para Converter em produto de engenharia

O assistente para **Converter em produto de engenharia** ajuda você a converter um ou mais produtos existentes em produtos de engenharia. Ele converte os produtos em produtos de engenharia (produtos com versão) em que a versão não é rastreada nas transações (ou seja, a dimensão da versão não é usada). Após a conclusão da conversão, você poderá gerenciar os produtos usando o Gerenciamento de alterações de engenharia.

A conversão é permanente. Portanto, você não poderá revertê-la posteriormente. 

Cada produto de engenharia convertido continuará sendo liberado nas mesmas empresas em que o produto original foi liberado. No entanto, a BOM (lista de materiais) de engenharia e os roteiros não serão liberados automaticamente para essas empresas.

Siga estas etapas para executar o assistente para **Converter em produto de engenharia** e converta um produto em um produto de engenharia.

1. Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Na grade, marque a caixa de seleção para cada produto que você deseja converter.
1. No Painel de Ações, na guia **Engenharia**, no grupo **Gerenciamento de alterações de engenharia**, selecione **Converter em produto de engenharia** para abrir o assistente.
1. A primeira página do assistente é a página de **Boas-vindas**. Se ainda não estiver familiarizado com o processo de conversão, leia atentamente as informações nesta página. Quando estiver pronto para continuar, selecione **Avançar**.
1. A página **Selecionar detalhes dos produtos a serem convertidos** mostra cada produto selecionado antes de você abrir o assistente. Inspecione a lista. Use os botões **Novo** e **Excluir** na barra de ferramentas para adicionar ou remover produtos conforme necessário.
1. Use os campos a seguir na parte superior da grade para atribuir valores padrão a cada produto listado. (Você poderá alterar esses valores para produtos individuais após a conclusão da conversão.) Os valores padrão não serão atribuídos aos produtos aos quais um valor relevante já tenha sido atribuído.

    - **Categoria de engenharia padrão** — selecione uma categoria de produto de engenharia inicial a ser atribuída a todos os produtos listados. A categoria selecionada será aplicada somente aos produtos compatíveis com ela.
    - **Versão padrão** — insira a versão inicial do produto a ser atribuída a cada produto listado. Cada produto de engenharia tem pelo menos uma versão de engenharia.
    - **Estado do ciclo de vida padrão** — selecione o estado inicial do ciclo de vida do produto a ser atribuído a cada produto listado.
    - **A BOM atual será parte do produto de engenharia** — marque esta caixa de seleção se a BOM atual de cada produto listado deve ser usada como uma BOM para o produto de engenharia.

    Para obter mais informações sobre configurações do produto, consulte a próxima etapa.

1. Revise cada produto listado na grade e avalie como os valores padrão atribuídos se aplicam a ele. Para cada linha, revise as informações a seguir e defina os campos relevantes:

    - **Número do produto** — o número do produto.
    - **Nome do produto** — o nome do produto.
    - **Categoria de engenharia** — selecione a categoria de produto de engenharia à qual o produto deve pertencer após a conversão. Uma categoria apropriada já deve existir para cada produto, como foi explicado na seção anterior deste tópico. Você deve atribuir uma categoria a cada produto.
    - **Versão** — insira a versão do produto a ser atribuída ao produto após a conversão. Por exemplo, você pode selecionar um número que caiba na sequência numérica que a categoria já usa. Cada versão de engenharia armazena os dados relevantes da engenharia que são específicos dessa versão. Para obter mais informações, consulte [Versões de engenharia e categorias de produto de engenharia](engineering-versions-product-category.md).
    - **Estado do ciclo de vida do produto** — selecione o estado do ciclo de vida do produto em que o produto deve estar após a conversão. O estado do ciclo de vida do produto permite que você controle quais transações são permitidas para uma determinada versão da engenharia. Para obter mais informações, consulte [Estados e transações de ciclo de vida do produto](product-lifecycle-state-transactions.md).
    - **Tem BOM** — uma caixa de seleção marcada indica que o produto tem uma BOM. A configuração desta caixa de seleção pode ajudar você a decidir como definir a caixa de seleção **A BOM atual será parte do produto de engenharia**.
    - **A BOM atual será parte do produto de engenharia** — marque esta caixa de seleção se a BOM do produto deve ser usada como uma BOM para o produto de engenharia. Essa BOM será então gerenciada pelo Gerenciamento de alterações de engenharia. Se o produto não tiver uma BOM ou se você preferir criar manualmente uma BOM para o produto convertido mais tarde, desmarque esta caixa de seleção.
    - **Tem erros** — uma caixa de seleção marcada indica que a configuração do produto tem um ou mais erros. Por exemplo, o tipo de produto ou o grupo de dimensões pode não corresponder à categoria. Os produtos com erros serão ignorados e não serão convertidos.

1. Quando terminar, selecione **Validar** na barra de ferramentas para validar a configuração do produto. Em cada linha, a caixa de seleção **Tem erros** será atualizada para indicar o status do produto. Ajuste os valores até que a configuração de cada produto esteja sem erros.
1. Quando todos os produtos estiverem configurados corretamente, selecione **Avançar** para continuar.
1. A página **Confirmar seleção** mostra o número de produtos sem erros na configuração e que, portanto, estão prontos para conversão. Ele também mostra o número de produtos que serão ignorados devido a erros. Para executar a conversão como um trabalho em lotes, defina a opção **Executar em lote** como *Sim*.
1. Selecione **Concluir** para aplicar as configurações e começar a converter os produtos em produtos de engenharia.

> [!NOTE]
> Se o seu sistema estiver configurado para aceitar manualmente os produtos antes que eles sejam liberados, você deverá aceitar cada produto convertido usando a página **Abrir liberações de produtos** nas empresas apropriadas. Para obter mais informações, consulte [Revisar e aceitar o produto antes de liberá-lo na empresa local](engineering-scenarios.md#accept).
