---
title: Relatório de comparação de armazenamento de preços de item
description: Saiba como gerar um Relatório de comparação de armazenamento de preços de item e, em seguida, procurar e/ou exportar o resultado.
author: JennySong-SH
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace, InventItemPriceCompareStorage, InventItemPriceCompareStorageDetailsChart, InventItemPriceCompareStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: c9e2ccbe613a4aab40a4f519bbb82a9175d46e72
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846203"
---
# <a name="compare-item-prices-storage-report"></a>Relatório de comparação de armazenamento de preços de item

[!include [banner](../includes/banner.md)]

Este artigo explica como executar um relatório de **Comparação de armazenamento de preços de item** e disponibilizar a saída digitalmente, como uma página interativa no Dynamics 365 Supply Chain Management ou como um documento exportado em qualquer um dos vários formatos.

Ao visualizar o relatório em seu navegador, as colunas e os saldos agregados são ajustados dinamicamente, dependendo do layout configurado. Você pode classificar os resultados, filtrá-los, detalhar os dados e muito mais.

Os resultados do relatório são armazenados na entidade de dados **Comparar preços de item**, que permite filtrar e exportar os resultados para um formato como CSV ou Microsoft Excel.

O **Relatório de comparação de armazenamento de preços de item** é útil nos casos em que a saída contém muitas linhas. Por exemplo, a saída conterá muitas linhas se você tiver mais de 40.000 itens com um preço de item pendente na versão de avaliação de custo.

## <a name="enable-compare-item-prices-storage"></a>Habilitar comparação de armazenamento de preços de item

Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário. Aqui o recurso está listado como:

- **Módulo** - Gerenciamento de custos
- **Nome do recurso** - Comparação de armazenamento de preços de item

## <a name="generate-a-compare-item-prices-storage-report"></a>Gerar um relatório de comparação de armazenamento de preços de item

Siga estas etapas para gerar e armazenar um **Relatório de comparação de armazenamento de preços de item**:

1. Acesse **Gerenciamento de custos > Consultas e relatórios > Relatórios de custo predeterminado > Comparação de armazenamento de preços de item**.

1. Selecione **Novo** para abrir o painel **Comparar preços de item**. Defina as seguintes opções para determinar quais preços comparar no seu relatório:

    - Na Guia Rápida **Parâmetros**, dê ao relatório um único **Nome** e use os campos nas seções **Preços pendentes a serem comparados** e **Preços usados na comparação** para definir quais preços e datas comparar.
    - Na Guia Rápida **Registros a serem incluídos**, configure filtros e restrições para definir quais dados incluir no relatório.
    - Na Guia Rápida **Executar em segundo plano**, configure como, quando e com que frequência você deseja gerar o relatório.
    > [!NOTE]
    > Esse relatório é sempre executado como parte de um trabalho em lotes.

1. Selecione **OK** para aplicar suas configurações e fechar o painel.

1. Após a conclusão do trabalho em lotes, ele será listado na página **Comparação de armazenamento de preços de item**. Pode ser necessário atualizar a página para ver o relatório.

## <a name="explore-the-compare-item-prices-storage-report"></a>Explorar o Relatório de comparação de armazenamento de preços de item

Depois de gerar um relatório, você pode visualizá-lo e explorá-lo a qualquer momento, da seguinte maneira:

1. Acesse **Gerenciamento de custos > Consultas e relatórios > Relatórios de custo predeterminado > Comparação de armazenamento de preços de item**.

1. Selecione um relatório na lista.

1. Execute um destes procedimentos:

    - Selecione **Visão geral** para obter uma visão geral dos resultados do seu relatório.
    - Selecione **Exibir detalhes** para ter uma visão mais detalhada do seu relatório

1. Após a exibição selecionada ser aberta, você poderá fazer o seguinte:

    - Selecione quase qualquer cabeçalho de coluna para classificar ou filtrar a tabela por valores nessa coluna, assim como nos formulários mais padrão no Supply Chain Management. Observe que você não pode classificar ou filtrar a coluna **% de preço de alteração líquida** porque é um campo calculado.
    - Selecione **Exibição de dimensão** para abrir um painel onde você pode escolher qual coluna de dimensão incluir no formulário. Defina **Salvar configuração** como **Sim** se deseja salvar essas configurações para que elas sejam preservadas na próxima vez que você abrir o relatório. Selecione **OK** para aplicar suas configurações e fechar.
    - Selecione qualquer linha no formulário e selecione **Exibir detalhes** para ver mais informações sobre o item selecionado. Você poderá detalhar os dados a partir daqui.
    - Selecione qualquer linha no formulário e, em seguida, selecione **Exibir gráfico de comparação** para ver uma representação gráfica interativa dos seus resultados relacionados ao item selecionado. Você pode explorar esses resultados selecionando vários elementos gráficos no gráfico e na legenda do gráfico.
    - Selecione qualquer linha no formulário e selecione **Exibir detalhes do cálculo** para ver mais informações sobre cálculos relacionados ao item selecionado. Você poderá detalhar os dados a partir daqui.

## <a name="export-the-compare-item-prices-storage-report"></a>Exportar o Relatório de comparação de armazenamento de preços de item

Cada relatório que você gera é armazenado na entidade de dados **Comparar preços de item**. Você pode usar os recursos de gerenciamento de dados padrão do Supply Chain Management para exportar dados dessa entidade para qualquer formato de dados compatível, incluindo CSV ou Microsoft Excel.

Veja a seguir um exemplo de como exportar um **Relatório de comparação de armazenamento de preços de item**:

1. Acesse **Acesse Administração de sistema > Locais de trabalho > Gerenciamento de dados**.

1. Selecione o botão **Exportar** na seção **Gerenciamento de dados**.

1. É aberta a página **Exportar**, que você usará para configurar seu trabalho de exportação. Comece dando ao seu trabalho uma **Nome do grupo**.

1. Na seção **Entidades selecionadas**, selecione **Adicionar entidade** para abrir uma caixa de diálogo onde você pode definir as seguintes opções:

    - **Nome da entidade** - Selecione **Comparar preços de item**.
    - **Formato de dados de destino** - Escolha o formato para o qual você deseja exportar.

1. Selecione **Adicionar** para adicionar a nova linha e selecione **Fechar** para fechar a caixa de diálogo.

1. Geralmente, você exportará um relatório por vez. Para isso, configure um **Filtro** da linha que você acabou de adicionar ao painel **Consulta**. Isso permitirá que você defina quais relatórios da entidade **Comparar preços de item** que você deseja incluir na sua exportação. Defina as seguintes opções de filtro para exportar um único relatório:

    - Na guia **Intervalo**, selecione **Adicionar** para adicionar uma nova linha.
    - Defina **Tabela** como **Comparar preços de item**.
    - Defina **Tabela derivada** como **Comparar preços de item**.
    - Defina **Campo** como o campo pelo qual você deseja filtrar. Em geral, você usará **Nome de execução** ou **Tempo de execução**.
    - Defina **Critérios** como o valor do campo selecionado que você deseja procurar (o nome do relatório ou a hora em que o relatório foi gerado).
    - Se necessário, adicione mais linhas à tabela **Intervalo** até identificar o relatório que você procura exclusivamente.

1. Selecione **OK** para salvar suas configurações e fechar.

1. Selecione **Salvar** para salvar sua configuração de exportação.

1. Abra a guia **Opções de exportação** e selecione **Exportar agora** para gerar o arquivo de exportação.

1. É aberta a página **Resumo de execução** na qual você pode ver o status do seu trabalho de exportação e uma lista de entidades que foram exportadas. Selecione a entidade **Comparar preços de item** listada na área **Status de processamento da entidade** e, em seguida, selecione **Baixar arquivo** para baixar os dados exportados dessa entidade.

Para obter mais informações sobre como usar o gerenciamento de dados para exportar dados, consulte [Visão geral de trabalhos de importação e exportação de dados](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]