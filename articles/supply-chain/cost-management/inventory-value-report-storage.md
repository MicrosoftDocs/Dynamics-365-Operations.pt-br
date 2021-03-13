---
title: Relatório de armazenamento de valor de estoque
description: Este tópico explica como executar um Relatório de armazenamento de valor de estoque e disponibilizar a saída digitalmente, como uma página interativa no Microsoft Dynamics 365 Supply Chain Management ou como um documento exportado em qualquer um dos vários formatos.
author: AndersGirke
manager: tfehr
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventValueProcess, InventValueReportSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 0f54c02fc828d60f4ddb28be932bbf8eb137ee92
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5008143"
---
# <a name="inventory-value-storage-report"></a>Relatório de armazenamento de valor de estoque

Este tópico explica como executar um relatório de **Armazenamento de valor de estoque** e disponibilizar a saída digitalmente, como uma página interativa no Microsoft Dynamics 365 Supply Chain Management ou como um documento exportado em qualquer um dos vários formatos.

Ao visualizar o relatório em seu navegador, as colunas e os saldos agregados são ajustados dinamicamente, dependendo do layout que você configurou. Você pode classificar os resultados, filtrá-los, detalhar os dados e muito mais.

Os resultados do relatório são armazenados na entidade de dados **Valor de estoque**. Portanto, você pode filtrar e exportar os resultados para um formato como os valores separados por vírgula (CSV) ou para o formato Microsoft Excel.

O relatório de **Armazenamento de valor de estoque** é útil quando a saída contém muitas linhas. Por exemplo, você tem 50.000 itens e 300 armazenamentos foram criados como depósitos. Nesse caso, se você solicitar saldos de finalização de estoque por item, site e depósito, a saída conterá várias linhas.

> [!NOTE]
> O relatório não incluirá os subtotais definidos no layout de relatório. Também não inclui saldos da contabilidade, mesmo quando são definidos no layout do relatório. A reconciliação para a contabilidade deve ser feita usando saldos de avaliação.

## <a name="turn-on-the-inventory-value-storage-feature"></a>Habilite o recurso de armazenamento de valor de estoque

Antes de gerar um relatório de **Armazenamento de valor de estoque**, você deve ativar o recurso no sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo se necessário. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo** – Gerenciamento de custos
- **Nome do recurso** – Armazenamento de valor de estoque

## <a name="generate-an-inventory-value-storage-report"></a>Gerar um relatório de armazenamento de valor de estoque

Siga estas etapas para gerar e armazenar um relatório de **Armazenamento de valor de estoque**.

1. Vá para **Gerenciamento de custos \> Consultas e relatórios \> Armazenamento do relatório de valor de estoque**.
1. Selecione **Novo**.
1. Na caixa de diálogo **Valor do estoque** que aparece, defina os valores a seguir para definir quais registros serão incluídos no relatório:

    - Na guia rápida **Parâmetros**, digite um nome exclusivo para o relatório e use os campos na seção  **Intervalo de datas** definir quais registros serão incluídos no relatório. Para definir o intervalo de datas, você pode selecionar um intervalo predefinido (relativo à data de geração do relatório) no campo **Código do intervalo de datas** ou selecionar datas específicas nos campos **De** e **Até**.
    - Na Guia Rápida **Registros a serem incluídos**, configure filtros e restrições para definir quais dados são incluídos no relatório.
    - Na Guia Rápida **Executar no plano de fundo**, especifique como, quando e com que frequência o relatório é gerado.

    > [!NOTE]
    > Esse relatório é sempre executado como parte de um trabalho em lotes.

1. Selecione **OK** para aplicar suas configurações e fechar a caixa de diálogo.

Depois que o trabalho em lotes for concluído, o relatório será listado na página **Armazenamento do relatório de valor de estoque**. Pode ser necessário atualizar a página para ver o relatório.

## <a name="explore-an-inventory-value-storage-report"></a>Explorar um relatório de armazenamento de valor de estoque

Depois de gerar um relatório, você pode visualizá-lo e explorá-lo a qualquer momento seguindo estas etapas.

1. Vá para **Gerenciamento de custos \> Consultas e relatórios \> Armazenamento do relatório de valor de estoque**.
1. Selecione um relatório na lista.
1. Selecione **Exibir detalhes** para mostrar o conteúdo do relatório.
1. Explore o relatório seguindo estas etapas:

    - Como para a maioria das páginas padrão no Supply Chain Management, você pode selecionar quase qualquer cabeçalho da coluna para classificar ou filtrar a grade pelos valores nessa coluna.
    - Use o campo **Filtrar** para filtrar o relatório por qualquer valor em qualquer uma das várias colunas disponíveis.
    - Use o menu de exibição (acima do campo **Filtrar**) para salvar e carregar suas combinações favoritas de opções de classificação e filtro.

## <a name="export-an-inventory-value-storage-report"></a>Exportar um relatório de armazenamento de valor de estoque

Todos relatórios que você gera é armazenado na entidade de dados **Valor do estoque**. Você pode usar os recursos de gerenciamento de dados padrão do Supply Chain Management para exportar dados dessa entidade para qualquer formato de dados compatível, como CSV ou Excel.

O exemplo a seguir mostra como exportar um relatório **Relatório de valor de estoque**.

1. Vá para **Administração de sistema \> Locais de trabalho \> Gerenciamento de dados**.
1. Na seção **Importar/Exportar**, selecione o bloco **Exportar**. 
1. Na página **Exportar** que aparece, você configurará o trabalho de exportação. Primeiro, insira um nome de grupo para o trabalho.
1. Na seção **Entidades selecionadas**, selecione **Adicionar entidade**.
1. Na caixa de diálogo que aparece, defina os campos a seguir:

    - **Nome da entidade** – Selecione **Valor de estoque**.
    - **Formato de dados de destino** – Selecione o formato para o qual os dados devem ser exportados.

1. Selecione **Adicionar** para adicionar a nova linha e selecione **Fechar** para fechar a caixa de diálogo.
1. Geralmente, você exportará um relatório por vez. Para exportar um único relatório, configure um filtro para a linha que você acabou de adicionar à caixa de diálogo **Consulta**. Dessa forma, você pode definir o relatório da entidade de **Valor de estoque** que será incluído na exportação. Siga estas etapas para definir as seguintes opções de filtro para exportar um único relatório:

    1. Na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha.
    2. Defina o campo **Tabela** como **Valor do estoque**.
    3. Defina o campo **Tabela derivada** como **Valor do estoque**.
    4. Defina o campo **Campo** como o campo pelo qual você deseja filtrar. Normalmente, você usará o campo **Nome de execução** e/ou o campo **Tempo de execução**.
    5. Defina o campo **Critérios** como o valor que você deseja procurar no campo selecionado. (Se você selecionou o campo **Nome de execução** na etapa anterior, este valor será o nome do relatório. Se você selecionou o campo **Tempo de execução**, a hora exibida será a hora que o relatório foi gerado.
    6. Adicione mais linhas à tabela **Intervalo** conforme necessário, até identificar o relatório que você procura exclusivamente.

1. Selecione **OK** para salvar suas configurações e fechar a caixa de diálogo.
1. Selecione **Salvar** para salvar sua configuração de exportação.
1. Na guia **Opções de exportação**, selecione **Exportar agora** para gerar o arquivo de exportação.
1. Na página **Resumo de execução** na que aparece, você pode ver o status do seu trabalho de exportação e uma lista de entidades que foram exportadas. Na seção **Status de processamento da entidade**, selecione a entidade **Valor de estoque** na lista, e selecione **Baixar arquivo** para baixar os dados que foram exportados a partir dessa entidade.

Para obter mais informações sobre como usar o gerenciamento de dados para exportar dados, consulte [Visão geral de trabalhos de importação e exportação de dados](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).
