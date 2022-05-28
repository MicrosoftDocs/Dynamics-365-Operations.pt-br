---
title: Exemplos e lógica de relatório de valor de estoque
description: Este tópico fornece alguns exemplos de resultados que são apresentados em cada tipo de relatório de valor de estoque. Os relatórios de valor de estoque fornecem detalhes sobre as quantidades e os valores físicos e financeiros de estoque.
author: JennySong-SH
ms.date: 10/19/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-10-19
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 0d594fc18a104c434a334a5b6d1d249330a6be9a
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675309"
---
# <a name="inventory-value-report-examples-and-logic"></a>Exemplos e lógica de relatório de valor de estoque

[!include [banner](../includes/banner.md)]

Os relatórios de valor de estoque fornecem detalhes sobre as quantidades e os valores físicos e financeiros de estoque. Este tópico fornece alguns exemplos de resultados que são apresentados em cada tipo de relatório de valor de estoque.

Para obter mais informações sobre como gerar e usar cada tipo de relatório de valor de estoque, consulte [Relatórios de valor de estoque](inventory-value-report-storage.md).

## <a name="sample-data-that-is-used-in-these-examples"></a>Dados de exemplo usados nestes exemplos

Os exemplos neste tópico se baseiam nos dados de exemplo de transação de estoque descritos nesta seção.

### <a name="storage-dimension-setup"></a>Configuração de dimensão de armazenamento

O sistema de exemplo contém a seguinte configuração de dimensões de armazenamento.

| Nome | Ativos | Estoque físico | Estoque financeiro |
|---|---|---|---|
| Site | Sim | Sim | Sim |
| Depósito | Sim | Sim | Não |

### <a name="inventory-model"></a>Modelo de estoque

Para o sistema de exemplo, o modelo de estoque para os produtos liberados é *PEPS*, e o campo **Preço de custo** para o modelo de estoque está definido como *Incluir valor físico*.

### <a name="inventory-transactions"></a>Transações de estoque

O sistema de exemplo contém as seguintes transações de estoque para um produto liberado que tem o número de item *B0001*.

| Demonstrativo | Site | Depósito | Recebimento | Problema | Data física | Data financeira | Quantidade | Valor de custo | Valor de custo físico |
|---|---|---|---|---|---|---|---|---|---|
| Ordem de Compra | 1 | 11 | Comprado | | 15 de março | 15 de março | 10 | 1.000 | 1.000 |
| Ordem de Compra | 2 | 21 | Comprado | | 15 de março | 15 de março | 10 | 2,000 | 2,000 |
| Ordem de Compra | 1 | 11 | Recebida | | 15 de abril | | 5 | | 375 |
| Ordem de transferência | 1 | 11 | | Vendido | Maio de 2 | Maio de 2 | -5 | -458,33 | -458,33 |
| Ordem de transferência | 1 | 12 | Comprado | | Maio de 2 | Maio de 2 | 5 | 458.33 | 458.33 |
| Ordem de venda | 1 | 12 | | Vendido | Maio de 3 | Maio de 3 | -1 | -91,67 | -91,67 |

### <a name="inventory-value-report-configuration"></a>Configuração de relatórios de valor de estoque

O sistema de exemplo inclui uma configuração de relatório de valor de estoque com as seguintes configurações:

- **Intervalo:**  *Data de lançamento*
- **Estoque:** *Sim*
- **Calcular custo unitário médio:** *Sim*
- **Quantidade e valor totais:** *Sim*
- **Site, Exibir:** *Selecionado*
- **ID do recurso, Exibir:** *Sim*
- **Nível:** *Totais*

## <a name="inventory-value-report-example-1"></a>Exemplo de relatório de valor de estoque 1

A tabela e as ilustrações a seguir mostram os resultados ao usar os dados de exemplo e a configuração do relatório descritos anteriormente neste tópico.

| Tipo de recurso | Recurso | Site | Demonstrativo | Estoque: quantidade financeira | Estoque: valor financeiro | Estoque: quantidade física lançada | Estoque: valor físico lançado | Estoque: quantidade | Estoque: valor | Custo unitário médio |
|---|---|---|---|---|---|---|---|---|---|---|
| Material | B0001 | 1 | Saldo final | 9.00 | 908.33 | 5.00 | 375.00 | 14,00 | 1,283.33 | 91.67 |
| Material | B0001 | 2 | Saldo final | 10,00 | 2,000.00 | 0,00 | 0,00 | 10,00 | 2,000.00 | 200.00 |

### <a name="standard-inventory-value-report-for-example-1"></a>Relatório de valor de estoque padrão para o exemplo 1

A ilustração a seguir mostra o relatório **Valor de estoque** padrão para o exemplo 1. (Selecione a ilustração para abrir uma versão maior.)

[![Relatório de valor de estoque para o exemplo 1.](media/inventory-value-report-ex1-small.png "Relatório de valor de estoque para o exemplo 1")](media/inventory-value-report-ex1.png)

### <a name="inventory-value-report-storage-report-for-example-1"></a>Relatório de armazenamento de relatórios de valor de estoque para o exemplo 1

A ilustração a seguir mostra o relatório **Armazenamento de relatórios de valor de estoque** para o exemplo 1. (Selecione a ilustração para abrir uma versão maior.)

[![Relatório de armazenamento de relatórios de valor de estoque para o exemplo 1.](media/inventory-value-report-storage-ex1-small.png "Relatório de armazenamento de relatórios de valor de estoque para o exemplo 1")](media/inventory-value-report-storage-ex1.png)

## <a name="inventory-value-report-example-2"></a>Exemplo de relatório de valor de estoque 2

A tabela e as ilustrações a seguir mostram os resultados quando você usa os dados de exemplo descritos anteriormente neste tópico, mas altera o valor do campo **Nível** para *Transações* na configuração do relatório e define o campo **Data inicial** como *15 de março* quando você executa o relatório.

| Tipo de recurso | Recurso | Site | Data | Número | Demonstrativo | Estoque: quantidade financeira | Estoque: valor financeiro | Estoque: quantidade física lançada | Estoque: valor físico lançado | Estoque: quantidade | Estoque: valor |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Material | B0001 | 1 | 15/03/2021 | 00000126 | Ordem de compra | 0,00 | 0,00 | 10,00 | 1.000.00 | **10.00** | **1,000.00** |
| Material | B0001 | 1 | 15/03/2021 | 00000126 | Ordem de compra | 10,00 | 1.000.00 | -10,00 | -1.000,00 | **0.00** | **0.00** |
| Material | B0001 | 1 | 15/04/2021 | 00000128 | Ordem de compra | 0,00 | 0,00 | 5.00 | 375.00 | **5.00** | **375.00** |
| Material | B0001 | 1 | 02/05/2021 | 000003 | Remessa da ordem de transferência | -5,00 | -458,33 | 0,00 | 0,00 | **-5.00** | **-458.33** |
| Material | B0001 | 1 | 02/05/2021 | 000003 | Recebimento da ordem de transferência | 5.00 | 458.33 | 0,00 | 0,00 | **5.00** | **458.33** |
| Material | B0001 | 1 | 03/05/2021 | 000835 | Ordem de venda | 0,00 | 0,00 | -1.00 | -91,67 | **-1.00** | **-91.67** |
| Material | B0001 | 1 | 03/05/2021 | 000835 | Ordem de venda | -1.00 | -91,67 | 1,00 | 91.67 | **0.00** | **0.00** |
| Material | B0001 | 2 | 15/03/2021 | 00000127 | Ordem de compra | 0,00 | 0,00 | 10,00 | 2,000.00 | **10.00** | **2,000.00** |
| Material | B0001 | 2 | 15/03/2021 | 00000127 | Ordem de compra | 10,00 | 2,000.00 | -10,00 | -2.000,00 | **0.00** | **0.00** |
| Material | B0001 | 2 | 02/05/2021 | 000003 | Remessa da ordem de transferência | 5.00 | 458.33 | 0,00 | 0,00 | **5.00** | **458.33** |
| Material | B0001 | 2 | 02/05/2021 | 000003 | Recebimento da ordem de transferência | -5,00 | -458,33 | 0,00 | 0,00 | **-5.00** | **-458.33** |

### <a name="standard-inventory-value-report-for-example-2"></a>Relatório de valor de estoque padrão para o exemplo 2

A ilustração a seguir mostra o relatório **Valor de estoque** padrão para o exemplo 2. (Selecione a ilustração para abrir uma versão maior.)

[![Relatório de valor de estoque padrão para o exemplo 2.](media/inventory-value-report-ex2-small.png "Relatório de valor de estoque para o exemplo 2")](media/inventory-value-report-ex2.png)

### <a name="inventory-value-report-storage-report-for-example-2"></a>Relatório de armazenamento de relatórios de valor de estoque para o exemplo 2

A ilustração a seguir mostra o relatório **Armazenamento de relatórios de valor de estoque** para o exemplo 2. (Selecione a ilustração para abrir uma versão maior.)

[![Relatório de armazenamento de relatórios de valor de estoque para o exemplo 2.](media/inventory-value-report-storage-ex2-small.png "Relatório de armazenamento de relatórios de valor de estoque para o exemplo 2")](media/inventory-value-report-storage-ex2.png)

## <a name="inventory-value-report-example-3"></a>Exemplo de relatório de valor de estoque 3

É recomendável que você execute relatórios de valor de estoque após o recálculo ou o fechamento do estoque, para que as transações e os valores sejam afetados pelo recálculo ou pelo fechamento do estoque.

As subseções a seguir mostram os relatórios de valor de estoque que são gerados depois que você fecha o estoque até 30 de maio.

### <a name="example-3-when-the-totals-level-is-used"></a>Exemplo 3 quando o nível Totais é usado

A tabela a seguir mostra os resultados ao usar os dados de exemplo e a configuração do relatório descritos anteriormente neste tópico. (Na configuração do relatório, o campo **Nível** está definido como *Totais*.)

| Tipo de recurso | Recurso | Site | Demonstrativo | Estoque: quantidade financeira | Estoque: valor financeiro | Estoque: quantidade física lançada | Estoque: valor físico lançado | Estoque: quantidade | Estoque: valor | Custo unitário médio |
|---|---|---|---|---|---|---|---|---|---|---|
| Material | B0001 | 1 | Saldo final | 9.00 | 900.00 | 5.00 | 375.00 | 14,00 | 1,275.00 | 91.07 |
| Material | B0001 | 2 | Saldo final | 10,00 | 2,000.00 | 0,00 | 0,00 | 10,00 | 2,000.00 | 200.00 |

### <a name="example-3-when-the-transactions-level-is-used"></a>Exemplo 3 quando o nível Transações é usado

A tabela a seguir mostra os resultados quando você usa os dados de exemplo descritos anteriormente neste tópico, mas altera o valor do campo **Nível** para *Transações* na configuração do relatório.

| Tipo de recurso | Recurso | Site | Data | Número | Demonstrativo | Estoque: quantidade financeira | Estoque: valor financeiro | Estoque: quantidade física lançada | Estoque: valor físico lançado | Estoque: quantidade | Estoque: valor |
|---|---|---|---|---|---|---|---|---|---|---|---|
| Material | B0001 | 1 | 15/03/2021 | 00000126 | Ordem de compra | 0,00 | 0,00 | 10,00 | 1.000.00 | 10,00 | 1.000.00 |
| Material | B0001 | 1 | 15/03/2021 | 00000126 | Ordem de compra | 10,00 | 1.000.00 | -10,00 | -1.000,00 | 0,00 | 0,00 |
| Material | B0001 | 1 | 15/04/2021 | 00000128 | Ordem de compra | 0,00 | 0,00 | 5.00 | 375.00 | 5.00 | 375.00 |
| Material | B0001 | 1 | 02/05/2021 | 000003 | Remessa da ordem de transferência | -5,00 | -458,33 | 0,00 | 0,00 | -5,00 | -458,33 |
| Material | B0001 | 1 | 02/05/2021 | 000003 | Recebimento da ordem de transferência | 5.00 | 458.33 | 0,00 | 0,00 | 5.00 | 458.33 |
| Material | B0001 | 1 | 03/05/2021 | 000835 | Ordem de venda | 0,00 | 0,00 | -1.00 | -91,67 | -1.00 | -91,67 |
| Material | B0001 | 1 | 03/05/2021 | 000835 | Ordem de venda | -1.00 | -91,67 | 1,00 | 91.67 | 0,00 | 0,00 |
| Material | B0001 | 1 | 31/05/2021 | 000835 | Ordem de venda | 0,00 | -8,33 | 0,00 | 0,00 | 0,00 | -8,33 |
| Material | B0001 | 1 | 31/05/2021 | 000003 | Remessa da ordem de transferência | 0,00 | -41,67 | 0,00 | 0,00 | 0,00 | -41,67 |
| Material | B0001 | 1 | 31/05/2021 | 000003 | Recebimento da ordem de transferência | 0,00 | 41.67 | 0,00 | 0,00 | 0,00 | 41.67 |
| Material | B0001 | 2 | 15/03/2021 | 00000127 | Ordem de compra | 0,00 | 0,00 | 10,00 | 2,000.00 | 10,00 | 2,000.00 |
| Material | B0001 | 2 | 15/03/2021 | 00000127 | Ordem de compra | 10,00 | 2,000.00 | -10,00 | -2.000,00 | 0,00 | 0,00 |
| Material | B0001 | 2 | 02/05/2021 | 000003 | Remessa da ordem de transferência | 5.00 | 458.33 | 0,00 | 0,00 | 5.00 | 458.33 |
| Material | B0001 | 2 | 02/05/2021 | 000003 | Recebimento da ordem de transferência | -5,00 | -458,33 | 0,00 | 0,00 | -5,00 | -458,33 |
| Material | B0001 | 2 | 31/05/2021 | 000003 | Remessa da ordem de transferência | 0,00 | 41.67 | 0,00 | 0,00 | 0,00 | 41.67 |
| Material | B0001 | 2 | 31/05/2021 | 000003 | Recebimento da ordem de transferência | 0,00 | -41,67 | 0,00 | 0,00 | 0,00 | -41,67 |
