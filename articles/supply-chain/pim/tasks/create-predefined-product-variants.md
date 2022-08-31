---
title: Criar grades de produtos predefinidas
description: Este procedimento mostra como criar variantes de produto para um produto mestre que usam as combinações de dimensões do produto.
author: t-benebo
ms.date: 08/09/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions, EcoResProductVariantsPendingReleaseFormPart, EcoResProductVariantSuggestionsEnhanced
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: a26439b8c7346cdce2b4c9804493fea94c29ac31
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335905"
---
# <a name="predefined-product-variants"></a>Grades de produtos predefinidas

[!include [banner](../../includes/banner.md)]

## <a name="example-scenario-create-predefined-product-variants"></a>Cenário de exemplo: Criar grades de produtos predefinidas

Este cenário de exemplo mostra como criar variantes de produto para um produto mestre usando combinações de dimensões do produto.

### <a name="make-demo-data-available"></a>Disponibilizar dados de demonstração

Para seguir este cenário usando os valores sugeridos aqui, você deve ter dados de demonstração instalados e deve selecionar a entidade legal *USMF*.

### <a name="step-1-create-a-product-master"></a>Etapa 1: criar um produto mestre

Para criar um produto mestre:

1. Acesse **Gerenciamento de informações sobre produtos > Produtos > Produtos mestres**.
1. Selecione **Novo**.
1. Se o campo **Número do produto** ainda não mostrar um número, insira um valor. Isso só é necessário se nenhuma sequência numérica foi definida para este campo.
1. Insira um nome no campo **Nome do produto**.
1. No campo **Grupo de dimensões do produto**, selecione o grupo de dimensões do produto *SizeCol* (Tamanho e Cor).
1. Selecione **OK** para criar e abrir o novo produto mestre.

### <a name="step-2-add-product-dimensions"></a>Etapa 2: adicionar dimensões do produto

Este exemplo a seguir mostra como inserir manualmente as dimensões do produto. Você pode optar por selecionar um tamanho, cor ou grupo de estilo que inclui os valores de dimensão de produto que deseja usar.

Para adicionar dimensões do produto:

1. Com o novo produto mestre ainda aberto, selecione **Dimensões do produto** no Painel de Ações.
1. Abra a guia **Tamanho** e selecione **Novo** na barra de ferramentas para adicionar uma linha à grade. Faça as seguintes configurações para a nova linha:
    - **Tamanho:** Selecione um valor de tamanho.
    - **Nome:** – Insira um nome do tamanho.
1. Selecione **Novo** na barra de ferramentas e adicione um segundo tamanho à grade com um novo **Tamanho** e **Nome**.
1. Abra a guia **Cores** e selecione **Novo** na barra de ferramentas para adicionar uma linha à grade. Faça as seguintes configurações para a nova linha:
    - **Cor:** selecione um valor de cor.
    - **Nome:** insira um nome para a cor.
1. Selecione **Novo** na barra de ferramentas e adicione uma segunda cor à grade com **Cor** e **Nome** novos.
1. Selecione **Salvar**.
1. Feche a página para retornar ao novo produto mestre.

### <a name="step-3-generate-product-variants"></a>Etapa 3: gerar grades de produtos

> [!NOTE]
> Esta seção descreve como gerar grades de produto quando o recurso *Aperfeiçoamentos de página sugestões de grade* não estiver habilitado. Consulte a próxima seção para obter detalhes sobre como gerar grades de produto quando esse recurso estiver disponível.

Para gerar grades de produtos:

1. Com o novo produto mestre ainda aberto, selecione **Grades do produto** no Painel de Ações.
1. Selecione **Sugestões de grade** no Painel de Ações.
1. O sistema gera uma lista com todas as combinações possíveis dos tamanhos e cores definidos para o produto. Escolha **Selecionar tudo** na barra de ferramentas.
    - Neste exemplo, selecione todas as grades possíveis. Se você só quiser usar um subconjunto das combinações de dimensão de produto possíveis, marque somente as caixas de seleção necessárias, conforme necessário.  
1. Selecione **Criar**.
1. Selecione **Salvar**.

## <a name="improved-variant-suggestions"></a>Sugestões de grade aprimoradas

O recurso *Aperfeiçoamentos de páginas de sugestões de grade* melhora a página **Sugestões de grade** para tratar das questões de desempenho e usabilidade de empresas que têm um alto número de combinações de dimensões de produtos. O processo avançado para selecionar os valores de dimensão do produto para os quais gerar sugestões de grade torna mais rápido e fácil identificar e liberar o conjunto relevante de grades de produto.

Os aprimoramentos a seguir são adicionados por esse recurso:

- **Geração adiada de sugestões de grade:** a página **Sugestões de grade** não mostra mais sugestões quando você a abre pela primeira vez. Em vez disso, você deve escolher explicitamente quais valores serão necessários e, em seguida, selecionar o botão **Sugerir** para gerar as combinações. Isso torna o processo mais visível e interativo.
- **Seleção de valores de dimensões:** quando você tem vários valores de dimensão, geralmente está interessado em gerar sugestões de grade que incluam apenas alguns deles (como ao introduzir um novo conjunto de cores ou estilos). Com o design aprimorado, você pode selecionar os valores de dimensão para os quais deseja gerar sugestões de grade de produtos. Isso aumenta bastante a relevância das variantes sugeridas e melhora o desempenho do sistema e a produtividade do usuário.

### <a name="turn-the-variant-suggestions-page-improvements-feature-on-or-off"></a>Ativar ou desativar o recurso Aprimoramentos na página de sugestões de grade

Para usar esse recurso, você deve habilitá-lo no seu sistema. A partir do Supply Chain Management versão 10.0.25, o recurso está ativado por padrão. A partir do Supply Chain Management versão 10.0.29, o recurso é obrigatório e não pode ser desativado. Se você estiver executando uma versão anterior à 10.0.29, os administradores poderão habilitar ou desabilitar essa funcionalidade pesquisando o recurso *Aprimoramentos na página de sugestões de grade* no espaço de trabalho [Gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="work-with-the-improved-variant-suggestions"></a>Trabalhar com as sugestões de grade aprimoradas

Para gerar sugestões de grade de produto quando o recurso *Aperfeiçoamentos de página de sugestões de grade* estiver habilitado:

1. Abra ou crie um produto mestre e adicione as dimensões de produto necessárias a ele, conforme descrito na seção anterior.
1. Com o produto mestre aberto, selecione **Grades do produto** no Painel de Ações.
1. Selecione **Sugestões de grade** no Painel de Ações.
1. Selecione os valores que deseja usar para cada uma das dimensões.
1. Na barra de ferramentas superior, selecione **Sugerir**.
1. O sistema gera uma lista com todas as combinações possíveis dos tamanhos e cores selecionados. Na FastTab **Variantes sugeridas**, marque a caixa de seleção para cada combinação de dimensão de produto que deseja usar ou escolha **Selecionar tudo** na barra de ferramentas para selecionar todas elas.  
1. Selecione **Criar** para adicionar as grades ao produto mestre atual.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
