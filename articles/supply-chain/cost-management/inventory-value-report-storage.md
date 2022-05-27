---
title: Relatórios de valor de estoque
description: Este tópico explica como configurar, gerar e usar relatórios de valor de estoque. Esses relatórios fornecem detalhes sobre as quantidades e os valores físicos e financeiros de estoque.
author: JennySong-SH
ms.date: 10/19/2021
ms.topic: article
ms.search.form: InventValueProcess, InventValueReportSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-10-19
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 4f710ff308bac42a284cd506143dd0ae21ff2ec7
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8676149"
---
# <a name="inventory-value-reports"></a>Relatórios de valor de estoque

[!include [banner](../includes/banner.md)]

Os relatórios de valor de estoque fornecem detalhes sobre as quantidades e os valores físicos e financeiros de estoque. É possível exibir os relatórios de várias maneiras diferentes. Por exemplo, você pode mostrar totais ou transações, ou filtrar por itens ou um intervalo de tempo. Você pode exibir os COGS (custo dos produtos vendidos) ou WIP (trabalho em andamento) e definir outras opções.

Os relatórios de valor de estoque permitem executar as seguintes tarefas:

- Fazer a reconciliação entre a contabilidade e o estoque.
- Consultar o estoque disponível e os valores de um período específico.
- Criar configurações de relatório que são personalizadas para uma finalidade específica.
- Salvar configurações de relatório para que possam ser usadas várias vezes.
- Adicionar intervalos a dados de filtro quando você executar um relatório.

## <a name="types-of-inventory-value-report"></a>Tipos de relatório de valor de estoque

Há dois tipos de relatório de valor de estoque: **Valor de estoque** (o relatório padrão) e **Armazenamento de relatórios de valor de estoque**.

### <a name="standard-inventory-value-report"></a>Relatório de valor de estoque padrão

O relatório **Valor de estoque** padrão é um relatório simples que permite selecionar as informações incluídas e mostra essas informações na tela. Ele não salva os resultados. Ele também não oferece recursos interativos para filtragem, detalhamento, navegação ou exportação. Por esses motivos, recomendamos que você use o relatório **Armazenamento de relatórios de valor de estoque** na maioria dos casos.

### <a name="inventory-value-report-storage-report"></a>Relatório de armazenamento de relatórios de valor de estoque

O relatório **Armazenamento de relatórios de valor de estoque** fornece a saída digitalmente, como uma página interativa no Microsoft Dynamics 365 Supply Chain Management ou como um documento exportado em qualquer um dos vários formatos.

Ao visualizar o relatório em seu navegador, as colunas e os saldos agregados são ajustados dinamicamente, dependendo do layout que você configurou. Você pode classificar os resultados, filtrá-los, detalhar os dados e muito mais.

Os resultados do relatório são armazenados na entidade de dados **Valor de estoque**. Portanto, você pode filtrar e exportar os resultados para um formato como os valores separados por vírgula (CSV) ou para o formato Microsoft Excel.

O relatório **Armazenamento relatórios de valor de estoque** é útil quando a saída contém muitas linhas. Por exemplo, você tem 50.000 itens e 300 armazenamentos foram criados como depósitos. Nesse caso, se você solicitar saldos de finalização de estoque por item, site e depósito, a saída conterá várias linhas.

> [!NOTE]
> O relatório **Armazenamento de relatórios de valor de estoque** não inclui os subtotais definidos no layout do relatório. Também não inclui saldos da contabilidade, mesmo se esses saldos estiverem definidos no layout do relatório. A reconciliação para a contabilidade deve ser feita usando saldos de avaliação. No entanto, o relatório **Valor de estoque** padrão inclui esses subtotais e saldos.

## <a name="turn-the-inventory-value-report-storage-feature-on-or-off"></a>Ativar ou desativar o recurso Armazenamento de relatórios de valor de estoque

A partir da versão 10.0.25 do Supply Chain Management, este recurso está ativado por padrão. Os administradores podem ativar ou desativar essa funcionalidade, procurando o recurso *Armazenamento de relatórios de valor de estoque* no espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="define-inventory-value-report-configurations"></a><a name="report-configuration"></a>Definir configurações de relatório de valor de estoque

Use a página **Relatórios de valor de estoque** para configurar o conteúdo incluído nos diferentes tipos de relatório de valor de estoque. Você pode definir qualquer número de tipos de relatório. Sempre que você gerar um tipo de relatório de valor de estoque, será selecionado um tipo de relatório.

1. Acesse **Gerenciamento de custos \> Configuração das políticas contábeis de estoque \> Relatórios de valor de estoque**.
1. Siga uma destas etapas:

    - Para editar um relatório existente, selecione-a no painel de lista e, depois, selecione **Editar** no Painel de Ações.
    - Para criar um novo relatório, selecione **Novo** no Painel de Ações.

1. No cabeçalho do relatório novo ou selecionado, defina os seguintes campos:

    - **ID** – insira um identificador curto para o relatório. Esse valor deve ser exclusivo entre todas as configurações de relatório de valor de estoque. Ele não poderá ser editado depois que você salvar uma nova configuração.
    - **Nome** – insira um nome descritivo para o relatório.

1. Se estiver criando uma nova configuração de relatório, selecione **Salvar** no Painel de Ações para disponibilizar os campos restantes.
1. Na Guia Rápida **Geral**, defina os seguintes campos:

    - **Intervalo de datas** – selecione um intervalo de datas predefinido. Você pode substituir esse intervalo de datas ao executar o relatório.
    - **Intervalo** – selecione a *Data de lançamento* ou a *Hora da transação*, dependendo da data e da hora que deverá ser usada quando os registros forem recuperados para o relatório.
    - **Conjunto de dimensões** – selecione o conjunto de dimensões para os quais os dados serão executados. (As dimensões são definidas na contabilidade). Por exemplo, você pode executar os dados da *Conta principal* ou da *Conta principal + Unidade de negócios*. O conjunto de dimensões selecionado não deve ter mais de duas dimensões. Para obter mais informações, consulte [Conjuntos de dimensões financeiras](../../finance/general-ledger/financial-dimension-sets.md).

1. Na Guia Rápida **Colunas**, defina os campos a seguir. Esses campos controlam as colunas que o seu relatório inclui e os tipos de dados que essas colunas contêm.

    - **Estoque** – defina essa opção como *Sim* para mostrar os valores de estoque. Em seguida, você pode reconciliar esses valores com os saldos da conta contábil.
    - **WIP** – defina essa opção como *Sim* para mostrar os valores de WIP. Em seguida, você pode reconciliar esses valores com os saldos da conta WIP na contabilidade. Quando você definir esta opção como *Sim*, o relatório mostrará somente as quantidades físicas e os volumes de estoque com o status WIP. Ordens de produção com status de WIP foram separadas ou informadas como concluídas, mas não foram encerradas.
    - **COGS diferido** – defina essa opção como *Sim* para exibir uma coluna que mostre as quantidades físicas e as quantidades de estoque para o COGS diferido. O COGS diferido é mostrado com o uso de quantidades físicas e valores, pois desloca as quantidades e os valores da guia de remessa.
    - **COGS diferido** – defina essa opção como *Sim* para exibir uma coluna que mostre as quantidades e os valores financeiros para COGS. O COGS diferido é mostrado com o uso de quantidades e valores financeiros, pois desloca as quantidades e os valores da fatura.
    - **Lucros e perdas** – defina essa opção como *Sim* para exibir uma coluna que mostre o valor financeiro lançado nas contas de lucros e perdas para estoque.
    - **Imprimir valores cumulativos da conta para comparação** – defina essa opção como *Sim* para exibir uma coluna que mostre o saldo da conta contábil. Dessa forma, você não precisará verificar o saldo do rastro. Essa opção só funciona com o relatório **Valor de estoque** padrão, não com o relatório **Armazenamento de relatórios de valor de estoque**. Depois de definir esta opção como *Sim*, você deverá usar os campos a seguir para especificar cada conta contábil que deseja listar, dependendo das opções de **Posição financeira** habilitadas.

        > [!NOTE]
        > Se você selecionar uma conta *total* para qualquer um desses campos, o valor de cada conta de estoque incluído na conta de totais e o valor da conta de totais será mostrado.

        - **Conta de estoque** – especifique a conta contábil para a qual as informações de estoque devem ser mostradas. (Tanto a opção **Estoque** e a opção **Imprimir valores cumulativos de conta para comparação** devem ser definidas como *Sim*.)
        - **Conta WIP** – especifique a conta contábil para a qual as informações de WIP devem ser mostradas. (Tanto a opção **WIP** e a opção **Imprimir valores cumulativos de conta para comparação** devem ser definidas como *Sim*.)
        - **Conta COGS diferida** – especifique a conta contábil para a qual as informações de COGS diferidas devem ser mostradas. (Tanto a opção **COGS diferida** e a opção **Imprimir valores cumulativos de conta para comparação** devem ser definidas como *Sim*.)
        - **Conta COGS** – especifique a conta contábil para a qual as informações de COGS devem ser mostradas. (Tanto a opção **COGS** e a opção **Imprimir valores cumulativos de conta para comparação** devem ser definidas como *Sim*.)

    - **Resumir valores físicos e financeiros** – defina essa opção como *Sim* para exibir uma coluna que mostre a quantidade total de estoque e o valor do estoque (um resumo dos valores de estoque físico e financeiro). Se essa opção for definida como *Não*, o relatório mostrará os valores de estoque físico e financeiro.
    - **Incluir não lançado no razão** Defina essa opção como *Sim* para exibir uma coluna que mostre as transações que nunca foram lançadas na contabilidade. As transações para os seguintes tipos de itens talvez não sejam lançadas na contabilidade:

        - Itens recebidos e ainda não faturados quando a opção **Lançar estoque físico** é desmarcada para o grupo de modelos de item relevante.
        - Itens recebidos e ainda não faturados quando a opção **Lançar recebimento de produtos no razão** estiver desmarcada na Guia Rápida **Recebimento de produtos** na guia **Geral** da página **Parâmetros de contas a pagar** (**Contas a pagar \> Configuração \> Parâmetros de contas a pagar**).

    - **Calcular custo unitário médio** – defina essa opção como *Sim* para exibir uma coluna que mostre o custo unitário médio. O custo unitário médio é o valor total dividido pela quantidade total.
    - **Quantidade e valor totais** – defina essa opção como *Sim* para exibir colunas que mostrem a quantidade total de estoque físico (e as quantidades financeiras) e o valor total de estoque físico (e os valores financeiros). Você só poderá definir essa opção como *Sim* se a opção **Resumir valores físicos e financeiros** estiver definida como *Não*.
    - **Dimensões de estoque** – nessa grade, marque a caixa de seleção **Exibir** para cada dimensão que você deseja exibir no relatório. Somente as dimensões nas quais a opção **Estoque financeiro** está habilitada mostrarão valores no relatório. Outras dimensões só mostrarão colunas em branco. Para as dimensões selecionadas para exibição, você pode marcar a caixa de seleção **Total** para incluir os totais também.
    - **ID do recurso** – defina a opção **Exibir** como *Sim* para exibir uma coluna que identifique o item para cada linha. Defina a opção **Total** como *Sim* para incluir os totais também. Dependendo do tipo de item listado em cada linha, a coluna mostra um dos seguintes tipos de informação:

        - **Material** – a coluna mostra o valor do campo `ItemID` para o registro de material relevante.
        - **Trabalho** – a coluna mostra o valor do campo `WorkCenterID` para o registro de trabalho relevante.
        - **Custo indireto** – a coluna mostra o valor do campo `CodeID` para o registro de custo relevante.

        Se a opção **Exibir** estiver definida como *Não* para o campo **ID do recurso** e o campo **Grupo de Recursos**, você verá apenas um valor de estoque total baseado nas dimensões de estoque selecionadas.

    - **Grupo de Recursos** – defina a opção **Exibir** como *Sim* para exibir uma coluna que identifique o grupo de recursos para cada linha. Defina a opção **Total** como *Sim* para incluir os totais também. Dependendo do tipo de item listado em cada linha, a coluna mostra um dos seguintes tipos de informação:

        - **Material** – a coluna mostra o valor do campo `ItemGroup` para o registro de material relevante.
        - **Trabalho** – a coluna mostra o valor do campo `WorkcenterGroup` para o registro de trabalho relevante.
        - **Custo indireto** – a coluna mostra o valor do campo `CostGroup` para o registro de custo relevante. (O valor de `CostGroupType` deve ser *Indireto*.)

        Se a opção **Exibir** estiver definida como *Não* para o campo **ID do recurso** e o campo **Grupo de Recursos**, você verá apenas um valor de estoque total baseado nas dimensões de estoque selecionadas.

1. Na Guia Rápida **Linhas**, defina os campos a seguir. Esses campos permitem que você adicione subseções relacionadas a WIP correspondentes ao relatório ou as remova.

    - **Material** – defina essa opção como *Sim* para mostrar informações sobre materiais. *Material* é um tipo de recurso padrão porque os materiais devem ser incluídos em todas as configurações de relatório para criar uma saída confiável.
    - **Trabalho** – defina essa opção como *Sim* para mostrar os custos de trabalho do WIP.
    - **Custo indireto** – defina essa opção como *Sim* para mostrar os custos indiretos do WIP.
    - **Terceirização direta** – defina essa opção como *Sim* para mostrar os custos de terceirização direta do WIP. Essas informações são úteis para subcontratação.
    - **Nível de Detalhe** – selecione uma opção de exibição para o relatório:

        - *Transações* – exiba todas as transações relevantes no relatório. Observe que você pode enfrentar problemas de desempenho ao exibir relatórios que incluem um grande volume de transações. Portanto, se desejar usar esta opção de exibição, recomendamos que você use o relatório **Armazenamento de relatórios de valor de estoque**.
        - *Totais* – exiba o resultado total.

    - **Incluir saldo inicial** – defina essa opção como *Sim* para mostrar o saldo inicial. Essa opção só estará disponível quando o campo **Nível de detalhe** estiver definido como *Transações*.

## <a name="generate-an-inventory-value-report-storage-report"></a>Gerar um relatório de armazenamento de relatórios de valor de estoque

Siga estas etapas para gerar e armazenar um relatório **Armazenamento de relatórios de valor de estoque**.

1. Acesse **Gerenciamento de custos \> Consultas e relatórios \> Armazenamento do relatório de valor de estoque**.
1. No Painel de Ações, selecione **Novo**.
1. Na caixa de diálogo **Valor de estoque**, na Guia Rápida **Parâmetros**, defina estes campos:

    - **Nome** – insira um nome exclusivo para o relatório.
    - **ID** – selecione a [configuração do relatório de valor de estoque](#report-configuration) a ser usada para o relatório. A configuração estabelece opções para as colunas e linhas que serão incluídas no relatório.
    - **Intervalo de datas** – use os campos dessa seção para definir quais registros serão incluídos no relatório. Para definir o intervalo de datas, você pode selecionar um intervalo predefinido (relativo à data de geração do relatório) no campo **Código do intervalo de datas** ou selecionar datas específicas nos campos **De** e **Até**.

1. Na Guia Rápida **Registros a serem incluídos**, configure filtros e restrições para definir quais dados são incluídos no relatório. Selecione **Filtrar** para abrir uma um diálogo de editor de consultas padrão, onde você poderá definir critérios de seleção, critérios de classificação e junções. Os campos funcionam da mesma forma que em outros tipos de consultas no Supply Chain Management. Todos esses filtros serão aplicados às transações de estoque, mas não ao saldo da contabilidade. Tenha esse comportamento em mente ao configurar seus filtros. Caso contrário, você poderá ver uma discrepância entre o estoque e a contabilidade geral.
1. Na Guia Rápida **Executar no plano de fundo**, especifique como, quando e com que frequência o relatório é gerado. Os campos funcionam da mesma forma que em outros tipos de [trabalhos em segundo plano](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) no Supply Chain Management.

    > [!NOTE]
    > Esse relatório é sempre executado como parte de um trabalho em lotes.

1. Selecione **OK** para aplicar suas configurações e fechar a caixa de diálogo.

Depois que o trabalho em lotes for concluído, o relatório será listado na página **Armazenamento do relatório de valor de estoque**. Pode ser necessário atualizar a página para ver o relatório.

> [!IMPORTANT]
> Na configuração do relatório de valor de estoque selecionado, será possível obter um saldo inicial incorreto se você selecionar a mesma data nos campos **Data inicial** e **Data final** e se também definir a opção **Incluir saldo inicial** como *Sim*.

## <a name="explore-an-inventory-value-report-storage-report"></a>Explorar um relatório de armazenamento de relatórios de valor de estoque

Depois de gerar um relatório, você pode visualizá-lo e explorá-lo a qualquer momento seguindo estas etapas.

1. Acesse **Gerenciamento de custos \> Consultas e relatórios \> Armazenamento do relatório de valor de estoque**.
1. Selecione um relatório na lista. A página mostra os detalhes da [configuração do relatório de valor de estoque](#report-configuration) usada para gerar o relatório selecionado.
1. No Painel de Ação, selecione **Exibir detalhes** para mostrar o conteúdo do relatório.
1. Explore o relatório seguindo estas etapas:

    - Como para a maioria das páginas padrão no Supply Chain Management, você pode selecionar quase qualquer cabeçalho da coluna para classificar ou filtrar a grade pelos valores nessa coluna.
    - Use o campo **Filtrar** para filtrar o relatório por qualquer valor em qualquer uma das várias colunas disponíveis.
    - Use o menu de exibição (acima do campo **Filtrar**) para salvar e carregar suas combinações favoritas de opções de classificação e filtro.

## <a name="export-an-inventory-value-report-storage-report"></a>Exportar um relatório de armazenamento de relatórios de valor de estoque

Todos relatórios que você gera é armazenado na entidade de dados **Valor do estoque**. Você pode usar os recursos de gerenciamento de dados padrão do Supply Chain Management para exportar dados dessa entidade para qualquer formato de dados compatível, como CSV ou Excel.

O exemplo a seguir mostra como exportar um relatório **Armazenamento de relatórios de valor de estoque**.

1. Acesse **Administração de sistema \> Locais de trabalho \> Gerenciamento de dados**.
1. Na seção **Importar/Exportar**, selecione o bloco **Exportar**.
1. Na página **Exportar** que aparece, você configurará o trabalho de exportação. Primeiro, insira um nome de grupo para o trabalho.
1. Na seção **Entidades selecionadas**, selecione **Adicionar entidade**.
1. Na caixa de diálogo que aparece, defina os campos a seguir:

    - **Nome da entidade** – Selecione *Valor de estoque*.
    - **Formato de dados de destino** – Selecione o formato para o qual os dados devem ser exportados.

1. Selecione **Adicionar** para adicionar a nova linha e selecione **Fechar** para fechar a caixa de diálogo.
1. Geralmente, você exportará um relatório por vez. Para exportar um único relatório, configure um filtro para a linha que você acabou de adicionar à caixa de diálogo **Consulta**. Dessa forma, você pode definir o relatório da entidade de **Valor de estoque** que será incluído na exportação. Siga estas etapas para definir as seguintes opções de filtro para exportar um único relatório:

    1. Na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha.
    2. Defina o campo **Tabela** como *Valor do estoque*.
    3. Defina o campo **Tabela derivada** como *Valor do estoque*.
    4. Defina o campo **Campo** como o campo pelo qual você deseja filtrar. Normalmente, você usará o campo **Nome de execução** e/ou o campo **Tempo de execução**.
    5. Defina o campo **Critérios** como o valor que você deseja procurar no campo selecionado. (Se você selecionou o campo **Nome de execução** na etapa anterior, este valor será o nome do relatório. Se você selecionou o campo **Tempo de execução**, a hora exibida será a hora que o relatório foi gerado.
    6. Adicione mais linhas à tabela **Intervalo** conforme necessário, até identificar o relatório que você procura exclusivamente.

1. Selecione **OK** para salvar suas configurações e fechar a caixa de diálogo.
1. Selecione **Salvar** para salvar sua configuração de exportação.
1. Na guia **Opções de exportação**, selecione **Exportar agora** para gerar o arquivo de exportação.
1. Na página **Resumo de execução** na que aparece, você pode ver o status do seu trabalho de exportação e uma lista de entidades que foram exportadas. Na seção **Status de processamento da entidade**, selecione a entidade **Valor de estoque** na lista, e selecione **Baixar arquivo** para baixar os dados que foram exportados a partir dessa entidade.

Para obter mais informações sobre como usar o gerenciamento de dados para exportar dados, consulte [Visão geral de trabalhos de importação e exportação de dados](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md).

## <a name="generate-a-standard-inventory-value-report"></a>Gerar um relatório Valor de estoque padrão

Use o procedimento a seguir para gerar um relatório **Valor de estoque** padrão.

1. Acesse **Gerenciamento de custos \> Consultas e relatórios \> Contabilidade do estoque - relatórios de status \> Valor de estoque**.
1. Na caixa de diálogo do relatório **Valor de estoque**, na Guia Rápida **Parâmetros**, defina estes campos:

    - **Nome** – insira um nome exclusivo para o relatório.
    - **ID** – selecione a [configuração do relatório de valor de estoque](#report-configuration) a ser usada para o relatório. A configuração estabelece opções para as colunas e linhas que serão incluídas no relatório.
    - **Intervalo de datas** – use os campos dessa seção para definir quais registros serão incluídos no relatório. Para definir o intervalo de datas, você pode selecionar um intervalo predefinido (relativo à data de geração do relatório) no campo **Código do intervalo de datas** ou selecionar datas específicas nos campos **De** e **Até**.

1. Na Guia Rápida **Registros a serem incluídos**, configure filtros e restrições para definir quais dados são incluídos no relatório. Selecione **Filtrar** para abrir uma um diálogo de editor de consultas padrão, onde você poderá definir critérios de seleção, critérios de classificação e junções. Os campos funcionam da mesma forma que em outros tipos de consultas no Supply Chain Management.
1. Na Guia Rápida **Executar no plano de fundo**, especifique como, quando e com que frequência o relatório é gerado. Os campos funcionam da mesma forma que em outros tipos de [trabalhos em segundo plano](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) no Supply Chain Management.
1. Selecione **OK** para aplicar suas configurações e fechar a caixa de diálogo. O relatório é exibido.

## <a name="reading-inventory-value-reports"></a>Como ler relatórios de valor de estoque

Esta seção fornece algumas diretrizes sobre como ler e entender um relatório de valor de estoque.

O Supply Chain Management aceita os dois conceitos importantes a seguir relacionados ao status do estoque:

- **Atualização financeira** – esse conceito indica que as transações de estoque já foram faturadas. Para ordens de produção, indica o fim de uma ordem de produção.
- **Atualização física** – esse conceito indica que as transações de estoque ainda não foram faturadas, mas foram recebidas ou remetidas. Para ordens de produção, indica que o material foi separado ou que a ordem de produção foi informada como concluída.

Quando você entender esses dois conceitos, deverá ser fácil entender as seguintes colunas na saída do relatório:

- **Estoque: Quantidade Financeira** – a quantidade que foi atualizada financeiramente.
- **Estoque: Valor Financeiro** – o valor do estoque que foi atualizado financeiramente.
- **Estoque: Quantidade Física Lançada** – a quantidade que foi atualizada fisicamente.
- **Estoque: Valor Físico Lançado** – o valor do estoque que foi atualizado fisicamente.
- **Estoque: Quantidade Física Não Lançada** – a quantidade com transações de estoque, mas que ainda não foi lançada na contabilidade. Por exemplo, você tem um grupo de modelos de item em que as opções **Lançar estoque físico** e **Lançar estoque financeiro** estão desmarcadas, e você tem um item vinculado a esse grupo. Em seguida, você cria uma ordem de compra, a recebe e a fatura. Nesse ponto, se você revisar o relatório de valor de estoque para o item, verá que a quantidade e o valor na ordem de compra são mostrados nas colunas **Estoque: Quantidade Física Não Lançada** e **Estoque: Valor Físico Não Lançado**.
- **Estoque: Valor Físico Não Lançado** – você pode configurar seus relatórios para que eles mostrem valores não lançados. No entanto, se você estiver usando o relatório para reconciliação de estoque, não use esse valor. Caso contrário, o valor não será lançado na contabilidade.
- **Estoque: Quantidade** – a quantidade total de todas as colunas de quantidade no relatório.
- **Estoque: Valor** – a quantidade total de todas as colunas de valor no relatório. Quando fizer a reconciliação de estoque, não use essa coluna se o relatório incluir a coluna **Estoque: Valor Físico Não Lançado**. Nesse caso, você deverá excluir o valor de **Estoque: Valor Físico Não Lançado** do valor total.
- **Custo unitário médio** – o valor total dividido pela quantidade total.

Normalmente, você usará um relatório de valor de estoque para exibir o valor e a quantidade do estoque. No entanto, às vezes, o relatório não mostrará todas as dimensões de estoque relevantes. Se você não encontrar as dimensões que esperava, valide as seguintes configurações:

- Revise os grupos de armazenamento de item e de dimensão de rastreamento. Somente as dimensões nas quais a opção **Estoque financeiro** está habilitada poderão ser mostradas no relatório.
- Acesse **Gerenciamento de custos \> Configuração de políticas de contabilidade de estoque \> Relatórios de valor de estoque**, selecione a configuração de relatório usada para gerar o relatório e verifique se as dimensões de estoque necessárias estão selecionadas na coluna **Exibir**.

Por exemplo, você tem um item com o número do item *A0001*. No grupo de dimensões de armazenamento, somente o local será habilitado para estoque financeiro. O local e o depósito estão habilitados para o estoque físico. No grupo de dimensões de rastreamento, o número do lote está habilitado para o estoque físico, mas não para o estoque financeiro. Em seguida, você usa uma configuração de relatório na qual o local, o depósito e o número do lote estão todos selecionados. Ao exibir o relatório, você verá um valor somente para o site. As colunas para o depósito e o número do lote estão em branco. Como mostra este exemplo, os relatórios de valor de estoque só podem mostrar a dimensão de estoque habilitada para o estoque financeiro.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
