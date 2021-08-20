---
title: Previsões de estoque
description: Este tópico descreve a funcionalidade de previsão de fornecimento e demanda que pode ser usada para criar previsões de estoque no Microsoft Dynamics 365 Supply Chain Management.
author: crytt
ms.date: 06/08/2021
ms.topic: article
ms.search.form: EcoResProductDetailsExtended, ForecastSales, ForecastPurch, ForecastInvent
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-08
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a0919706ddcc70fecd15df6bf1cbdd58fe9a8e337b2d45cd61a4fb9d821e4114
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6757797"
---
# <a name="inventory-forecasts"></a>Previsões de estoque

[!include [banner](../includes/banner.md)]

Este tópico descreve como visualizar e criar previsões de estoque. Você pode criar e visualizar linhas de previsão de fornecimento e demanda para itens, grupos de itens, chaves de alocação de itens, contas de clientes, grupos de clientes, contas de fornecedores e grupos de fornecedores.

Para cada linha de previsão, você pode selecionar o modelo de previsão que é usado. Em seguida, é possível especificar o item ou o grupo de itens, mais a quantidade ou o valor da transação. Você também pode definir um cronograma para alocar a quantidade de previsão.

As linhas de previsão de fornecimento e demanda produzem uma previsão de estoque para a mesma combinação de um item e um modelo. Esta previsão de estoque representa um saldo entre o fornecimento e a demanda que foram inseridas para o mesmo item. Não é possível editá-la. A previsão de estoque ajuda a equipe de gerenciamento de estoque a revisar as mudanças esperadas no estoque disponível de um item durante o próximo período que foi previsto.

Depois de inserir a demanda e/ou o fornecimento, é possível executar o planejamento de previsão para calcular os requisitos brutos de materiais e capacidade, bem como para gerar as ordens planejadas.

## <a name="view-and-manually-enter-forecast-lines"></a><a name="manual-entry"></a>Exibir e inserir manualmente linhas de previsão

Use este procedimento para criar manualmente linhas de previsão para produtos.

Há também outras maneiras de criar linhas de previsão:

- [Gerar uma previsão estatística](generate-statistical-baseline-forecast.md).
- [Importar dados históricos para previsões de demanda](import-historical-data.md).
- [Gerar a previsão usando um serviço Web do Machine Learning do Microsoft Azure](demand-forecasting-setup.md).
- [Importar linhas de previsão de demanda ou fornecimento usando a estrutura de gerenciamento de dados (entidades de dados ForecastDemandForecastEntryStaging and ForecastSupplyForecastEntryStaging)](../../dev-itpro/data-entities/data-entities-data-packages.md).

Como a tabela da etapa 1 mostra, existem diferentes maneiras de acessar as páginas que são usadas.

1. Dependendo do tipo de entidade para a qual deseja criar uma previsão e do tipo de previsão que deseja criar, abra uma página de previsão de fornecimento, demanda ou estoque conforme descrito na tabela a seguir.

    | Entidade | Instruções |
    |---|---|
    | Produtos liberados | <ol><li>Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.</li><li>Selecione o produto para o qual será criada uma previsão.</li><li>No Painel de Ação, na guia **Plano**, no grupo **Previsão**, selecione **Previsão de demanda**, **Previsão de fornecimento** ou **Previsão de estoque**, dependendo do tipo de previsão com a qual deseja trabalhar.</li></ol> |
    | Grades de produtos liberadas | <ol><li>Acesse **Gerenciamento de informações do produto \> Produtos \> Grades de produtos liberadas**.</li><li>Selecione a grade para a qual será criada uma previsão.</li><li>No Painel de Ação, na guia **Plano**, no grupo **Previsão**, selecione **Previsão de demanda**, **Previsão de fornecimento** ou **Previsão de estoque**, dependendo do tipo de previsão com a qual deseja trabalhar.</li></ol> |
    | Grupos de itens | <ol><li>Acesse **Gerenciamento de estoque \> Configuração \> Divisão de estoque \> Grupos de itens**.</li><li>Selecione o grupo de itens para o qual será criada uma previsão.</li><li>No Painel de Ação, selecione **Previsão \> Demanda**, **Previsão \> Fornecimento** ou **Previsão \> Previsão de estoque**, dependendo do tipo de previsão com a qual deseja trabalhar.</li></ol> |
    | Chaves de alocação de itens | <ol><li>Acesse **Gerenciamento do estoque \> Configuração \> Previsão**.</li><li>Selecione a chave de alocação do item para a qual será criada uma previsão.</li><li>No Painel de Ações, selecione **Previsão de demanda**.</li></ol> |
    | Clientes | <ol><li>Acesse **Planejamento mestre \> Previsão \> Entrada de previsão manual \> Clientes**.</li><li>Selecione o cliente para o qual será criada uma previsão.</li><li>No Painel de Ações, selecione **Definir previsão de demanda**.</li></ol> |
    | Grupos de clientes | <ol><li>Acesse **Planejamento mestre \> Previsão \> Entrada de previsão manual \> Grupos de clientes**.</li><li>Selecione o grupo de clientes para o qual será criada uma previsão.</li><li>No Painel de Ações, selecione **Definir previsão de demanda**.</li></ol> |
    | Fornecedores | <ol><li>Acesse **Planejamento mestre \> Previsão \> Entrada de previsão manual \> Fornecedores**.</li><li>Selecione o fornecedor para o qual será criada uma previsão.</li><li>No Painel de Ação, selecione **Entrada** para abrir a página **Previsão de fornecimento**.</li></ol> |
    | Grupos de fornecedores | <ol><li>Acesse **Planejamento mestre \> Previsão \> Entrada de previsão manual \> Grupos de fornecedores**.</li><li>Selecione o grupo de fornecedores para o qual será criada uma previsão.</li><li>No Painel de Ação, selecione **Entrada** para abrir a página **Previsão de fornecimento**.</li></ol> | 
    | Todas as linhas | <ul><li>Acesse **Planejamento mestre \> Previsão \> Linhas de previsão de demanda** ou **Planejamento mestre \> Previsão \> Linhas de previsão de fornecimento**, dependendo do tipo de previsão com a qual você deseja trabalhar.</li></ul> |

    Dependendo da sua seleção, a página **Previsão de fornecimento** ou **Previsão de demanda** será exibida. Ela mostra todas as linhas de previsão existentes para o registro selecionado antes da abertura da página.

1. No Painel de Ações, selecione **Novo** para adicionar uma linha de previsão à grade na parte superior da página.
1. Na nova linha, no campo **Modelo**, selecione o modelo de previsão a ser usado. Em seguida, insira outros detalhes conforme necessário, como item, grupo de itens, conta ou grupo de cliente ou fornecedor, quantidade de itens ou valor total da transação. Para obter detalhes completos sobre os campos disponíveis nas páginas **Previsão de fornecimento** e **Previsão de demanda**, consulte as seções posteriores neste tópico.
1. Para distribuir a previsão durante o período, na guia **Visão geral**, selecione **Alocar previsão** na barra de ferramentas.
1. Na grade **Alocação**, revise o horizonte e os intervalos de tempo usados para distribuir as quantidades de previsão.

## <a name="supply-forecast-lines"></a>Linhas de previsão de fornecimento

A previsão de fornecimento permite criar um plano para itens que devem ser comprados. Ele informa aos funcionários de compras e fornecimento o que eles devem encomendar.

Você pode inserir uma previsão de fornecimento por item, grupo de itens, chave de alocação de item, fornecedor e grupo de fornecedores. Para obter informações sobre todas as maneiras de abrir a página **Previsão de fornecimento** para várias entidades e registros, consulte a seção [Exibir e inserir manualmente as linhas de previsão](#manual-entry) anteriormente neste tópico.

A parte superior da página **Previsão de fornecimento** fornece uma grade de linhas de previsão de fornecimento e um conjunto de guias que você pode usar para exibir e definir mais informações sobre uma linha de previsão selecionada. A parte inferior da página fornece uma grade de **Alocação**.

As subseções a seguir descrevem todos os campos disponíveis em cada guia e todos os comandos disponíveis no Painel de Ação da página e na barra de ferramentas da guia **Visão geral**.

### <a name="action-pane-commands-on-the-supply-forecast-page"></a>Comandos do Painel de Ação na página Previsão de fornecimento

A tabela a seguir descreve os comandos disponíveis no Painel de Ações da página **Previsão de fornecimento**.

| Comando | descrição |
|---|---|
| Salvar | Salve as configurações atuais. |
| Edição | Habilite as configurações na página a ser editada. |
| Criar | Adicione uma linha de previsão à grade superior. |
| Delete | Remova a linha de previsão selecionada da grade superior. |
| Saldos de previsão | Exiba os saldos de previsão que foram calculados para a ID do modelo da linha selecionada para o ano fiscal atual. Os saldos são divididos por período (mês). |
| Previsões de Fluxo de Caixa | Exiba as transações de previsão que foram alocadas para a contabilidade. Para obter mais informações, consulte [Previsão de fluxo de caixa](../../finance/cash-bank-management/cash-flow-forecasting.md). |
| Estoque \> Exibir dimensões | Selecione as dimensões de estoque que devem ser mostradas na grade da guia **Visão geral**. |

### <a name="toolbar-commands-on-the-overview-tab-of-the-supply-forecast-page"></a>Comandos da barra de ferramentas na guia Visão geral da página Previsão de fornecimento

A tabela a seguir descreve os comandos disponíveis na barra de ferramentas da guia **Visão Geral** da página **Previsão de fornecimento**.

| Comando | descrição |
|---|---|
| Alocar previsão | Se você estiver usando um método de alocação, gere as linhas da agenda individuais para a transação de previsão. A quantidade da linha é distribuída por data (de acordo com os intervalos de tempo selecionados), a quantidade e o valor para todo o horizonte de tempo. |
| Atualização em massa | Abra a página **Editar transações de previsão**. (Consulte a seção [Transações de previsão de atualização em massa](#bulk-update) posteriormente neste tópico.) |
| Previsão de Estoque | Abra uma exibição da página **Previsão de estoque** filtrada para a combinação de item/modelo selecionada. (Consulte a seção [Previsão de estoque](#inventory-forecast) posteriormente neste tópico.) |
| Criar requisição de itens | Abra uma caixa de diálogo na qual é possível criar requisições de itens, ordens de venda ou linhas de diário de itens para transações de previsão relacionadas ao projeto. Embora este comando esteja disponível para as linhas de previsão de fornecimento e de demanda, ele não pode ser usado na página **Previsão de fornecimento**. |

### <a name="the-overview-tab-on-the-supply-forecast-page"></a>A guia Visão geral na página Previsão de fornecimento

A tabela a seguir descreve os campos na guia **Visão geral** da página **Previsão de fornecimento**.

| Campo | descrição |
|---|---|
| **Modelo** | O modelo de previsão ao qual a transação está associada. |
| **Data** | A data de início da transação. |
| **Conta de Fornecedor** | A conta do fornecedor à qual a transação está associada. |
| **Grupo de Fornecedores** | O grupo de fornecedores ao qual a transação está associada. |
| **Número do item** | O identificador do item. |
| **Grupo de itens** | O grupo de itens ao qual a transação está associada. |
| **Chave de alocação de itens** | A chave de alocação do item associada à previsão. |
| **Quantidade em PV** | A quantidade de previsão na unidade de peso variável especificada. |
| **Unidade de PV** | A unidade de peso variável em que o item é comprado. O valor é recuperado automaticamente da configuração do item. |
| **Quantidade** | A quantidade de previsão na unidade de compra especificada. |
| **Unidade** | A unidade na qual o item é comprado. O valor é recuperado automaticamente da configuração do item. No entanto, você poderá modificá-lo se as conversões de unidade forem configuradas. |
| **Valor** | O valor bruto, menos os descontos, com o qual a transação de previsão contribui para a previsão. |
| **Moeda** | A moeda usada para a transação de previsão. A moeda padrão é inserida automaticamente, mas você pode selecionar uma moeda diferente. |
| (Outras dimensões) | Dimensões adicionais podem ser mostradas como colunas na grade. Para selecionar as dimensões adicionais que são mostradas, selecione **Exibir dimensões** no Painel de Ações. |

### <a name="the-general-tab-on-the-supply-forecast-page"></a>A guia Geral na página Previsão de fornecimento

A guia **Geral** mostra mais informações sobre a linha selecionada no momento na guia **Visão geral**. Algumas dessas informações são repetidas na guia **Visão geral**. A tabela a seguir descreve os campos exclusivos da guia **Geral**.

| Campo | descrição |
|---|---|
| Relatório | Defina esta opção como *Sim* para incluir a transação no relatório. |
| Comentários | Insira quaisquer comentários que você tenha sobre a transação de previsão. |
| Com Atividade | Selecione esta caixa de seleção para incluir a transação no relatório de orçamento. |
| Incluir em previsões de fluxo de caixa | Selecione esta caixa de seleção para alocar a transação de previsão para a contabilidade. A configuração dessa caixa de seleção não pode ser modificada para transações de relatório. |
| Grupo de impostos sobre vendas | O grupo de impostos usado para especificar o imposto para a transação de previsão. |
| Grupo de impostos do item | O grupo de impostos do item usado para especificar o imposto para a transação de previsão. |
| Método | <p>Selecione o método usado para alocar a transação de previsão:</p><ul><li>**Nenhum** – Nenhuma alocação ocorre.</li><li>**Período** – Preveja a mesma quantidade para cada período. Se você selecionar este valor, especifique uma quantidade no campo **Por** e uma unidade de tempo no campo **Unidade**.</li><li>**Chave** – Aloque a previsão de acordo com a chave de alocação de período especificada no campo **Chave de período**. Use este método quando desejar que a variação sazonal seja considerada.</li></ol>|
| Por | <p>Insira o número de intervalos de tempo no futuro em que a previsão se estende. Esse campo está disponível somente se você seleciona *Período* no campo **Método**.</p><p>Por exemplo, selecione *Período* no campo **Método**, digite *1* no campo **Por** e selecione *Meses* no campo **Unidade**. No campo **Finalizar**, especifique uma data de término que se estende por um ano no futuro. Nesse caso, uma linha de previsão será criada para cada mês do ano seguinte, com base no item e na quantidade que são especificados na linha do cabeçalho.</p> |
| Unidade | Selecione a unidade do intervalo de tempo: *Dias*, *Meses* ou *Anos*. A alocação corresponderá ao número de dias, meses ou anos que você especifica no campo **Por**.|
| Chave de período | Especifique a chave de alocação de período. |
| Fim | Especifique a data final ao usar os campos **Por** e **Unidade**. |

### <a name="the-item-tab-on-the-supply-forecast-page"></a>A guia Item na página Previsão de fornecimento

A guia **Item** exibe mais informações de itens sobre a linha selecionada no momento na guia **Visão geral**.

A grade na parte superior da guia **Item** repete as informações de itens que também são mostradas na guia **Visão geral**. Além disso, ela inclui o campo **Preço unitário**, que mostra o preço de compra para o número de unidades especificado no campo **Unidade**. O preço unitário é recuperado automaticamente da configuração do item, mas é possível modificá-lo.

Os campos abaixo da grade fornecem mais detalhes do item. Algumas dessas informações são repetidas na guia **Visão geral**. A tabela a seguir descreve os campos exclusivos da guia **Item**.

| Campo | descrição |
|---|---|
| Unidade de preço | O número de unidades às quais o preço de compra se aplica. O valor é recuperado automaticamente da tabela Itens, mas é possível modificá-lo. |
| Encargos de compras | Encargos fixos no preço de compra. Os encargos são independentes da quantidade. |
| Percentual de desconto | O desconto como porcentagem. |
| Valor do desconto | O desconto como um valor por unidade de venda. |
| Valor bruto | O valor quando nenhum desconto é aplicado. |
| Quantidade | A quantidade da transação na unidade de estoque do item. |
| Sub-BOM | O número da lista de materiais (BOM) de uma sub-BOM específica. |
| Sub-roteiro | Número de roteiro de um sub-roteiro específico. |

### <a name="the-financial-dimensions-tab-on-the-supply-forecast-page"></a>A guia Dimensões financeiras na página Previsão de fornecimento

A guia **Dimensões financeiras** mostra todos os valores de dimensão financeira para a linha selecionada no momento na guia **Visão geral**.

### <a name="the-inventory-dimensions-tab-on-the-supply-forecast-page"></a>A guia Dimensões de estoque na página Previsão de fornecimento

A guia **Dimensões de estoque** mostra todos os valores de dimensão de estoque para a linha selecionada no momento na guia **Visão geral**.

### <a name="the-allocation-grid-on-the-supply-forecast-page"></a>A grade Alocação na página Previsão de fornecimento

Se você estiver usando uma chave de alocação de itens ou se tiver inserido uma previsão de item para um ou mais períodos futuros, poderá alocar a previsão selecionando **Alocar previsão** na barra de ferramentas da guia **Visão geral**. A quantidade será distribuída na forma indicada pelas linhas na grade **Alocação**.

## <a name="demand-forecast-lines"></a>LInhas de previsão de demanda

A previsão de demanda permite que você insira ou gere demanda para um cliente. Ela ajuda os funcionários de vendas e marketing a informar os funcionários do planejamento mestre sobre a demanda esperada durante o próximo período de previsão.

Você pode inserir uma previsão de demanda por item, grupo de itens, chave de alocação de item, cliente e grupo de clientes. Para obter informações sobre todas as maneiras de abrir a página **Previsão de demanda** para várias entidades e registros, consulte a seção [Exibir e inserir manualmente as linhas de previsão](#manual-entry) anteriormente neste tópico.

A parte superior da página **Previsão de demanda** fornece uma grade de linhas de previsão de demanda e um conjunto de guias que você pode usar para exibir e definir mais informações sobre uma linha de previsão selecionada. A parte inferior da página fornece uma grade de **Alocação**.

As subseções a seguir descrevem todos os campos disponíveis em cada guia e todos os comandos disponíveis no Painel de Ação da página e na barra de ferramentas da guia **Visão geral**.

### <a name="action-pane-commands-on-the-demand-forecast-page"></a>Comandos do Painel de Ação na página Previsão de demanda

A tabela a seguir descreve os comandos disponíveis no Painel de Ações da página **Previsão de demanda**.

| Comando | descrição |
|---|---|
| Salvar | Salve as configurações atuais. |
| Edição | Habilite as configurações na página a ser editada. |
| Criar | Adicione uma linha de previsão à grade superior. |
| Delete | Remova a linha de previsão selecionada da grade superior. |
| Saldos de previsão | Exiba os saldos de previsão que foram calculados para a ID do modelo da linha selecionada para o ano fiscal atual. Os saldos são divididos por período (mês). |
| Previsão de fluxo de caixa | Exiba as transações de previsão que devem ser alocadas para a contabilidade. Para obter mais informações, consulte [Previsão de fluxo de caixa](../../finance/cash-bank-management/cash-flow-forecasting.md). |
| Exibir dimensões | Selecione as dimensões de produto, armazenamento e rastreamento que devem ser mostradas na grade da guia **Visão geral**. |
| Visualização da contabilidade | Visualize as entradas de contabilidade para a transação selecionada. |
| Transferir linhas de cotação | Transfira linhas de cotação para o projeto selecionado. |

### <a name="toolbar-commands-on-the-overview-tab-of-the-demand-forecast-page"></a>Comandos da barra de ferramentas na guia Visão geral da página Previsão de demanda

A tabela a seguir descreve os comandos disponíveis na barra de ferramentas da guia **Visão Geral** da página **Previsão de demanda**.

| Comando | descrição |
|---|---|
| Alocar previsão | Se você estiver usando um método de alocação, gere as linhas da agenda individuais para a transação de previsão. A quantidade da linha é distribuída por data (de acordo com os intervalos de tempo selecionados), a quantidade e o valor para todo o horizonte de tempo. |
| Atualização em massa | Abra a página **Editar transações de previsão**. (Consulte a seção [Transações de previsão de atualização em massa](#bulk-update) posteriormente neste tópico.) |
| Previsão de Estoque | Abra uma exibição da página **Previsão de estoque** filtrada para a combinação de item/modelo selecionada. (Consulte a seção [Previsão de estoque](#inventory-forecast) posteriormente neste tópico.) |
| Criar requisição de itens | Abra uma caixa de diálogo na qual é possível criar requisições de itens, ordens de venda ou linhas de diário de itens para transações de previsão relacionadas ao projeto. |

### <a name="the-overview-tab-on-the-demand-forecast-page"></a>A guia Visão geral na página Previsão de demanda

A tabela a seguir descreve os campos na guia **Visão geral** da página **Previsão de demanda**.

| Campo | descrição |
|---|---|
| **Nome da Tarefa** | O nome da tarefa em lote que foi usada para criar a linha de previsão. |
| **Modelo** | O modelo de previsão ao qual a transação está associada. |
| **Data** | A data de início da transação. |
| **Conta do cliente** | A conta do cliente à qual a transação está associada. |
| **Grupo de clientes** | O grupo de clientes à qual a transação está associada. |
| **Número do item** | O identificador do item. |
| **Nome do produto** | A descrição do item. |
| **Chave de alocação de itens** | A chave de alocação de item que é usada durante a alocação de previsão de estoque. |
| **Quantidade de venda** | A quantidade da transação na unidade de vendas especificada. |
| **Unidade** | A unidade em que o item é vendido. |
| **Valor** | O valor bruto, excluindo os descontos, com o qual a transação de previsão contribui para a previsão. |
| **Preço de venda** | O preço de venda para o número de unidades especificado no campo **Unidade de preço**. O valor é recuperado da configuração do item, mas é possível modificá-lo. |
| **Moeda de venda** | A moeda usada para a transação de previsão. A moeda padrão é inserida automaticamente, mas você pode selecionar uma moeda diferente. |
| **Quantidade em PV** | A quantidade de previsão na unidade de peso variável especificada. |
| **Unidade de PV** | A unidade de peso variável em que o item é vendido. O valor é recuperado automaticamente da configuração do item. |
| (Outras dimensões) | Dimensões adicionais de produto, armazenamento e rastreamento podem ser mostradas como colunas na grade. Para selecionar as dimensões adicionais que são mostradas, selecione **Exibir dimensões** no Painel de Ações. |

### <a name="the-general-tab-on-the-demand-forecast-page"></a>A guia Geral na página Previsão de demanda

A guia **Geral** mostra mais informações sobre a linha selecionada no momento na guia **Visão geral**. Algumas dessas informações são repetidas na guia **Visão geral**. A tabela a seguir descreve os campos exclusivos da guia **Geral**.

| Campo | descrição |
|---|---|
| Número de sequência de previsão de demanda | O número exclusivo da linha de previsão de demanda. Esse número é gerado usando a sequência numérica selecionada para previsões de demanda na página **Parâmetros de planejamento mestre**. |
| Grupo de itens | O grupo de itens ao qual a transação está associada. |
| Relatório | Defina esta opção como *Sim* para incluir a transação no relatório. |
| Comentários | Insira quaisquer comentários que você tenha sobre a transação de previsão. |
| Com Atividade | Selecione esta caixa de seleção para incluir a transação no relatório de orçamento. A configuração dessa caixa de seleção não pode ser modificada para transações de relatório. |
| Incluir em previsões de fluxo de caixa | Selecione esta caixa de seleção para alocar a transação de previsão para a contabilidade. A configuração dessa caixa de seleção não pode ser modificada para transações de relatório. Para obter mais informações, consulte [Previsão de fluxo de caixa](../../finance/cash-bank-management/cash-flow-forecasting.md). |
| Grupo de impostos sobre vendas | O grupo de impostos usado para especificar o imposto para a transação de previsão. |
| Grupo de impostos do item | O grupo de impostos do item usado para especificar o imposto para a transação de previsão. |
| Método | <p>Selecione o método usado para alocar a transação de previsão:</p><ul><li>**Nenhum** – Nenhuma alocação ocorre.</li><li>**Período** – Preveja a mesma quantidade para cada período. Se você selecionar este valor, especifique uma quantidade no campo **Por** e uma unidade de tempo no campo **Unidade**.</li><li>**Chave** – Aloque a previsão de acordo com a chave de alocação de período especificada no campo **Chave de período**. Use este método quando desejar que a variação sazonal seja considerada.</li><ul>|
| Por | <p>Insira o número de intervalos de tempo no futuro em que a previsão se estende. Esse campo está disponível somente se você seleciona *Período* no campo **Método**.</p><p>Por exemplo, selecione *Período* no campo **Método**, digite *1* no campo **Por** e selecione *Meses* no campo **Unidade**. No campo **Finalizar**, especifique uma data de término que se estende por um ano no futuro. Nesse caso, uma linha de previsão será criada para cada mês do ano seguinte, com base no item e na quantidade que são especificados na linha do cabeçalho. |
| Unidade | Selecione a unidade do intervalo de tempo: *Dias*, *Meses* ou *Anos*. A alocação corresponderá ao número de dias, meses ou anos que você especifica no campo **Por**.|
| Chave de período | Especifique a chave de alocação de período usada para alocar a previsão. Para obter mais informações, consulte [Alocação de dados do planejamento de orçamento](../../finance/budgeting/budget-planning-data-allocation.md). |
| Fim | Especifique a data final ao usar os campos **Por** e **Unidade**. |

### <a name="the-item-tab-on-the-demand-forecast-page"></a>A guia Item na página Previsão de demanda

A guia **Item** mostra mais informações de item sobre a linha selecionada no momento na guia **Visão geral**. Algumas dessas informações são repetidas na guia **Visão geral**. A tabela a seguir descreve os campos exclusivos da guia **Item**.

| Campo | descrição |
|---|---|
| Unidade de preço | O número de unidades de vendas às quais o preço de venda se aplica. O valor é recuperado automaticamente da tabela Itens, mas é possível modificá-lo. |
| Encargos de vendas | Encargos fixos no preço de venda. Os encargos são independentes da quantidade. |
| Preço de custo | O custo da transação de previsão por unidade de estoque. O valor é recuperado da tabela Itens, mas é possível modificá-lo. |
| Percentual de desconto | O desconto como porcentagem. |
| Valor do desconto | O desconto como um valor por unidade de venda. |
| Valor bruto | O valor quando nenhum desconto é aplicado. |
| Quantidade em estoque | A quantidade da transação na unidade de estoque do item. |
| Usar BOM específica | Número de BOM para BOM específica. |
| Usar roteiro específico | Número de roteiro de um sub-roteiro específico. |

### <a name="the-project-tab-on-the-demand-forecast-page"></a>A guia Projeto na página Previsão de demanda

A guia **Projeto** mostra mais informações de projeto sobre a linha selecionada no momento na guia **Visão geral**. Algumas dessas informações são repetidas na guia **Visão geral**, **Geral** ou **Item**. A tabela a seguir descreve os campos exclusivos da guia **Projeto**.

| Campo | descrição |
|---|---|
| Data do projeto | A data da transação de previsão de demanda. |
| ID do projeto | O identificador do projeto referido pela transação atual. |
| Fonte de financiamento | A fonte de financiamento à qual a previsão de demanda está associada. |
| Número da atividade | A atividade associada à transação de previsão de demanda. |
| Categoria | A categoria de custo da transação atual. |
| Propriedade da linha | O status ao qual a transação está associada. |
| Id de transação | O identificador do sistema para a transação de previsão de demanda. |
| Valor de custo | O valor da transação de previsão de demanda. |
| Preço unitário | O preço por unidade. |
| Modificação de | O identificador do trabalhador que modificou a transação selecionada pela última vez. |
| Data da fatura | Insira a data prevista da fatura. |
| Data de eliminação | Exiba ou altere a data de eliminação. Quando a previsão é criada, a data de eliminação é definida para a data final do projeto. Se o projeto não tiver data final, a data do projeto será aplicada. Este campo se aplica a projetos de preço fixo e de investimento. |
| Data do pagamento de custo | Insira a data prevista para o pagamento da compra. |
| Data de pagamento de vendas | Insira a data prevista para o pagamento da venda. |

### <a name="the-financial-dimensions-tab-on-the-demand-forecast-page"></a>A guia Dimensões financeiras na página Previsão de demanda

A guia **Dimensões financeiras** mostra todos os valores de dimensão financeira para a linha selecionada no momento na guia **Visão geral**.

### <a name="the-inventory-dimensions-tab-on-the-demand-forecast-page"></a>A guia Dimensões de estoque na página Previsão de demanda

A guia **Dimensões de estoque** mostra todos os valores de dimensão de estoque para a linha selecionada no momento na guia **Visão geral**.

### <a name="the-allocation-grid-on-the-demand-forecast-page"></a>A grade Alocação na página Previsão de demanda

Se você estiver usando uma chave de alocação de itens ou se tiver inserido uma previsão de item para um ou mais períodos futuros, poderá alocar a previsão selecionando **Alocar previsão** na barra de ferramentas da guia **Visão geral**. A quantidade será distribuída na forma indicada pelas linhas na grade **Alocação**.

## <a name="inventory-forecast"></a><a name="inventory-forecast"></a>Previsão de Estoque

As páginas de linhas de previsão de demanda e de fornecimento têm um botão **Previsão de estoque** que abre uma exibição da página **Previsão de estoque** filtrada para a mesma combinação de item/modelo. A previsão de estoque representa um saldo entre o fornecimento e a demanda que foram inseridas para o mesmo item. Não é possível editá-la. A previsão de estoque ajuda a equipe de gerenciamento de estoque a revisar as mudanças esperadas no estoque disponível de um item durante o próximo período que foi previsto.

### <a name="the-action-pane-on-the-inventory-forecast-page"></a>O Painel de Ação na página Previsão de estoque

A tabela a seguir descreve os comandos disponíveis no Painel de Ações da página **Previsão de estoque**.

| Ação | descrição |
|---|---|
| Previsão de fornecimento | Abra uma exibição da página **Previsão de fornecimento** filtrada para a mesma combinação de item/modelo/data. |
| Previsão de demanda | Abra uma exibição da página **Previsão de demanda** filtrada para a mesma combinação de item/modelo/data. |
| Estoque \> Exibir dimensões | Selecione as dimensões de produto, armazenamento e rastreamento que devem ser mostradas na grade **Visão geral**. |

### <a name="the-grid-on-the-inventory-forecast-page"></a>A grade na página Previsão de estoque

A tabela a seguir descreve os campos na grade da página **Previsão de estoque**.

| Campo | descrição |
|---|---|
| **Modelo** | O modelo de previsão ao qual a transação está associada. |
| **Número do item** | O identificador do item. |
| **Data do orçamento** | A data da transação de previsão. |
| **Tipo de previsão** | A origem da transação (*Previsão de demanda* ou *Previsão de fornecimento*). |
| **Quantidade em PV** | A quantidade de previsão na unidade de peso variável. |
| **Quantidade** | A quantidade de previsão na unidade de estoque. |
| **Peso variável acumulado** | A quantidade de previsão acumulada na unidade de peso variável quando várias linhas de previsão são acumuladas para o mesmo item. |
| **Sub-BOM** | Número de BOM para sub-BOM específica. |
| **Sub-roteiro** | Número de roteiro de um sub-roteiro específico. |
| (Outras dimensões) | Dimensões adicionais podem ser mostradas como colunas na grade. Para selecionar as dimensões adicionais que são mostradas, selecione **Estoque \> Exibir dimensões** no Painel de Ações. |

## <a name="bulk-update-forecast-transactions"></a><a name="bulk-update"></a>Transações de previsão de atualização em massa

Use este procedimento para processar linhas de transações de previsão existentes. Você pode copiar, editar e excluir linhas de transações de previsão.

1. Na página de linhas de previsão de fornecimento ou demanda, selecione **Atualização em massa**.
1. Na caixa de diálogo , selecione **Filtro**.
1. Na guia **Intervalo**, selecione os critérios que identificam os dados de previsão de origem que deseja copiar, editar ou excluir. Os dados podem incluir o modelo de previsão, o número do item e a conta do cliente.
1. Selecione **OK** para confirmar a seleção.

    Depois que os dados são selecionados, é possível usar a caixa de diálogo **Editar transações de previsão** para definir como deseja copiar, editar ou excluir.

    > [!NOTE]
    > A etapa de filtragem é um pré-requisito para o uso da funcionalidade **Edição em massa**. Se você ignorá-la, o programa selecionará e atualizará **todas** as linhas de previsão. Portanto, você pode causar a duplicação ou a remoção de transações acidentalmente.

1. Na seção **Gerenciamento**, selecione se deseja copiar, atualizar ou excluir as transações de previsão selecionadas.
1. Use a seção **Modificações no campo** para alterar os parâmetros da previsão. Marque a caixa de seleção de um parâmetro e selecione uma dentre as opções disponíveis. Por exemplo, marque a caixa de seleção **Modelo** e, em seguida, selecione um número de modelo de previsão. As linhas de previsão existentes são copiadas para o modelo de previsão selecionado.
1. Use a seção **Alteração de período** para mover as datas de início e término da previsão para frente ou para trás. Marque a caixa de seleção e, em seguida, use os campos de quantidade e período para definir como as datas de previsão devem ser movidas. Você pode inserir uma quantidade negativa para mover a data de início para frente (ou seja, antecipá-la).

    Por exemplo, para atrasar a data de início da transação de previsão em seis meses, marque a caixa de seleção, insira *6* como a quantidade e selecione *Meses* como o período.

1. Use a seção **Campo correto** para atualizar os dados de previsão atuais. No campo **Campo**, selecione o critério que deseja alterar. No campo **Fator**, insira um fator de multiplicação para aplicar ao critério selecionado ou insira uma constante para adicionar ou subtrair. Por exemplo, selecione *Quantidade* como o critério e insira um fator de *1,5* para multiplicar a quantidade do item por 1,5. Como alternativa, insira uma constante de *-25* para diminuir a quantidade do item em 25 unidades.
1. Use a seção **Dimensões financeiras** para atualizar as dimensões financeiras das linhas de previsão. Selecione as dimensões financeiras que deseja alterar e insira um valor a ser aplicado às dimensões selecionadas.
1. Selecione **OK** para aplicar as alterações.

## <a name="use-forecasts-with-master-planning"></a>Usar previsões com o planejamento mestre

Depois de inserir sua previsão de demanda e/ou previsão de fornecimento, você pode incluir as previsões durante o planejamento mestre para explicar a demanda e/ou a oferta esperadas em sua execução de planejamento mestre. Quando as previsões são incluídas no planejamento mestre, são calculados requisitos brutos para materiais e capacidade, bem como ordens planejadas.

### <a name="set-up-a-master-plan-to-include-an-inventory-forecast"></a>Configurar um plano mestre para incluir uma previsão de estoque

Para configurar um plano mestre de forma que inclua uma previsão de estoque, siga estas etapas.

1. Acesse **Planejamento mestre \> Configuração \> Planos \> Planos mestres**.
1. Selecione um plano existente ou crie um novo plano.
1. Na Guia Rápida **Geral**, defina os seguintes campos:

    - **Modelo de previsão** – selecione o modelo de previsão a ser aplicado. Esse modelo será considerado quando uma sugestão de fornecimento for gerada para o plano mestre atual.
    - **Incluir previsão de fornecimento** – defina esta opção como *Sim* para incluir a previsão de fornecimento no plano mestre atual. Se você defini-la como *Não*, as transações de previsão de fornecimento não serão incluídas no plano mestre.
    - **Incluir previsão de demanda** – defina esta opção como *Sim* para incluir a previsão de demanda no plano mestre atual. Se você defini-la como *Não*, as transações de previsão de demanda não serão incluídas no plano mestre.
    - **Método usado para reduzir requisitos de previsão** – selecione o método que deve ser usado para reduzir requisitos de previsão. Para obter mais informações, consulte [Chaves de redução de previsão](planning-optimization/demand-forecast.md#reduction-keys).

1. Na FastTab **Limite de tempo em dias**, você pode definir os seguintes campos para especificar o período de inclusão da previsão durante:

    - **Plano de previsão** – defina esta opção como *Sim* para substituir o limite de tempo do plano de previsão originado dos grupos de cobertura individuais. Defina como *Não* para usar os valores dos grupos de cobertura individuais para o plano mestre atual.
    - **Período de tempo de previsão** – se você definir a opção **Plano de previsão** como *Sim*, especifique o número de dias (a partir da data de hoje) em que a previsão de demanda deve ser aplicada.

    > [!IMPORTANT]
    > A opção de **Plano de previsão** ainda não tem suporte com a Otimização de Planejamento.

### <a name="run-a-master-plan-that-includes-an-inventory-forecast"></a>Executar um plano mestre que inclua uma previsão de estoque

Para executar um plano mestre de forma que inclua uma previsão de estoque, siga estas etapas.

1. Acesse **Planejamento mestre \> Espaços de trabalho \> Planejamento mestre**.
1. No campo **Planejamento mestre**, digite ou selecione o plano mestre que você configurou no procedimento anterior.
1. No bloco **Planejamento mestre**, selecione **Executar**.
1. Na caixa de diálogo **Planejamento mestre**, defina a opção **Rastrear tempo de processamento** como *Sim*.
1. No campo **Número de threads**, insira um número.
1. Na Guia Rápida **Registros a incluir**, selecione **Filtro**.
1. Uma caixa de diálogo do editor de consultas padrão é exibida. Na guia **Intervalo**, selecione a linha em que o campo **Campo** é definido como *Número do item*.
1. No campo **Critérios**, selecione o número do item a ser analisado no plano.
1. Selecione **OK**.

Para exibir os requisitos calculados, abra a página **Requisitos brutos**. Por exemplo, na página **Produtos liberados**, no Painel de Ações, na guia **Plano**, no grupo **Requisitos**, selecione **Requisitos brutos**.

Para exibir as ordens planejadas que são geradas, Acesse **Planejamento mestre \> Comum \> Ordens planejadas** e selecione o plano de previsão apropriado.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral da previsão de demanda](introduction-demand-forecasting.md)
- [Configuração da previsão de demanda](demand-forecasting-setup.md)
- [Gerar uma previsão estatística](generate-statistical-baseline-forecast.md)
- [Faça ajustes manuais para a previsão estatística](manual-adjustments-baseline-forecast.md)
- [Planejamento mestre com previsões de demanda](planning-optimization/demand-forecast.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
