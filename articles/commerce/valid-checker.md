---
title: Validar transações de loja para cálculo de demonstrativo
description: Este artigo descreve a funcionalidade para validar transações da loja no Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 01/31/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: analpert
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: 4be40189777a37495f185467050b61af47b684d7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890503"
---
# <a name="validate-store-transactions-for-statement-calculation"></a>Validar transações de loja para cálculo de demonstrativo

[!include [banner](includes/banner.md)]

Este artigo descreve a funcionalidade para validar transações da loja no Microsoft Dynamics 365 Commerce. O processo de validação identifica e marca as transações que causarão erros de lançamento, antes que sejam selecionados pelo processo de lançamento do demonstrativo.

Quando você tenta lançar um demonstrativo, o processo de validação pode falhar devido a dados inconsistentes nas tabelas de transação comercial. Veja a seguir alguns exemplos de fatores que podem causar essas inconsistências:

- O total da transação na tabela de cabeçalho não corresponde ao total da transação nas linhas.
- O número de itens especificado na tabela de cabeçalho não corresponde ao número de itens na tabela de transações.
- Os impostos na tabela de cabeçalho não correspondem ao valor do imposto nas linhas. 

Se transações inconsistentes forem escolhidas pelo processo de lançamento de demonstrativo, as faturas de venda e os diários de pagamento criados poderão causar falha no lançamento de demonstrativo. O processo **Validar transações de loja** evita esses problemas, garantindo que somente as transações que passam nas regras de validação de transação sejam passadas para o processo de cálculo do demonstrativo de transação.

A ilustração a seguir mostra os processos diurnos recorrentes para carregar transações, validar transações, bem como calcular e lançar demonstrativos de transação e os processos de fim de dia para cálculo e lançamento do demonstrativo financeiro.

![Ilustração mostrando os processos diurnos recorrentes para carregar transações, validar transações, bem como calcular e lançar demonstrativos de transação e os processos de fim de dia para cálculo e lançamento do demonstrativo financeiro](./media/valid-checker-statement-posting-flow.png)

## <a name="store-transaction-validation-rules"></a>Regras de validação de transação de loja

O processo em lote **Validar transações de loja** verifica a consistência das tabelas de transações de comércio, com base nas regras de validação a seguir.

> [!NOTE]
> As regras de validação continuarão sendo adicionadas em versões subsequentes.

### <a name="transaction-header-validation-rules"></a>Regras de validação de cabeçalho de transação

A tabela a seguir lista as regras de validação de cabeçalho de transação que são verificadas em relação ao cabeçalho das transações de varejo antes que essas transações sejam passadas para o lançamento de demonstrativo.

| Regra | Descrição |
|-------|-------------|
| Data comercial | Essa regra valida que a data comercial da transação está associada a um período fiscal aberto no razão. |
| Arredondamento de moedas | Essa regra valida que os valores da transação são arredondados de acordo com a regra de arredondamento de moeda. |
| Conta do cliente | Essa regra valida que o cliente usado na transação existe no banco de dados. |
| Valor do desconto | Essa regra valida que o valor do desconto no cabeçalho é igual à soma dos valores de desconto das linhas. |
| Status de lançamento de nota fiscal (Brasil) | Essa regra valida que a nota fiscal pode ser lançada com êxito. |
| Valor bruto | Essa regra valida que o valor bruto no cabeçalho de transação corresponde ao valor líquido, incluindo o imposto, das linhas de transação mais os encargos. |
| Líquido | Essa regra valida que o valor líquido no cabeçalho de transação corresponde ao valor líquido, excluindo o imposto, das linhas de transação mais os encargos. |
| Líquido + imposto | Essa regra valida que o valor bruto no cabeçalho de transação corresponde ao valor líquido, excluindo o imposto, das linhas de transação mais todos os impostos e encargos. |
| Número de itens | Essa regra valida que o número de itens especificado no cabeçalho de transação corresponde à soma das quantidades nas linhas de transação. |
| Valor do pagamento | Essa regra valida que o valor do pagamento no cabeçalho de transação corresponde à soma de todas as transações de pagamento. |
| Cálculo de isenção de imposto | Essa regra valida que a soma do valor calculado e da isenção do valor do imposto das linhas do encargo é igual ao valor calculado original. |
| Preço incluído no imposto | Essa regra valida que o sinalizador **Imposto está incluído no preço** está consistente em todo o cabeçalho de transação e nas transações de imposto. |
| Transação não vazia | Essa regra valida que a transação contém linhas e que, pelo menos, uma linha não está anulada. |
| Pagamento a maior/a menor | Essa regra valida que a diferença entre o valor bruto e o valor do pagamento não é maior que a configuração máxima de pagamento maior/a menor. |

### <a name="transaction-line-validation-rules"></a>Regras de validação de linha de transação

A tabela a seguir lista as regras de validação de linha de transação que são verificadas em relação aos detalhes da linha das transações de varejo antes que essas transações sejam passadas para o lançamento de demonstrativo.

| Regra | Descrição |
|-------|-------------|
| Código de barras | Essa regra valida que todos os códigos de barras do item usados nas linhas de transação existem no banco de dados. |
| Linhas de encargo | Essa regra valida que a soma do valor calculado e da isenção do valor do imposto das linhas do encargo é igual ao valor calculado original. |
| Devoluções de cartão-presente | Essa regra valida que não há devoluções de cartões-presente na transação. |
| Grade de itens | Essa regra valida que todos os itens e todas as grades de item usados nas linhas de transação existem no banco de dados do. |
| Desconto de linha | Essa regra valida que o valor do desconto de linha corresponde à soma das transações de desconto. |
| Imposto de linha | Essa regra valida que o valor do imposto de linha corresponde à soma das transações de imposto. |
| Preço negativo | Essa regra valida que nenhum preço negativo é usado nas linhas de transação. |
| Controlado por número de série | Essa regra valida que o número de série está presente na linha de transação dos itens que são controlados por número de série. |
| Dimensão de números de série | Essa regra valida que nenhum número de série será fornecido se a dimensão de número de série do item estiver inativa. |
| Contradição de sinal | Essa regra valida que o sinal da quantidade e o sinal do valor líquido são iguais em todas as linhas de transação. |
| Isenção de imposto | Essa regra valida que a soma do preço do item de linha e da isenção do valor do imposto é igual ao preço original. |
| Atribuição de grupo de impostos | Essa regra valida que a combinação do grupo de impostos sobre vendas e do grupo de impostos sobre itens produz uma interseção de impostos válida. |
| Conversões de unidade de medida | Essa regra valida que a unidade de medida de todas as linhas tem uma conversão válida para a unidade de medida de estoque. |

## <a name="enable-the-store-transaction-validation-process"></a>Habilitar o processo de validação de transação de loja

Configure o trabalho **Validar transações de loja** para execuções periódicas na matriz do Commerce (**Retail e Commerce \> TI de Retail e Commerce \> Lançamento do PDV**). O trabalho em lotes é agendado com base na hierarquia da organização da loja. É recomendável configurar esse processo em lotes para ser executado na mesma frequência que os trabalhos em lotes **Trabalho P** e **Cálculo de demonstrativo transacional**.

## <a name="results-of-the-validation-process"></a>Resultados do processo de validação

Os resultados do processo em lote **Validar transações de loja** podem ser exibidos em cada transação de loja de varejo. O campo **Status de validação** no registro de transação é definido como **Êxito**, **Erro** ou **Nenhum**. O campo **Hora da última validação** mostra a data da última execução de validação.

A tabela a seguir descreve cada status de validação.

| Status de validação | Descrição |
|-------------------|-------------|
| Êxito | Todas as regras de validação habilitadas foram aprovadas. |
| Erro | Uma regra de validação habilitada identificou um erro. Você pode exibir mais detalhes sobre o erro selecionando **Erros de validação** no Painel de Ações. |
| Nenhum | O tipo de transação não requer que as regras de validação sejam aplicadas. |

![A página de transações de loja mostrando o campo Status de validação e o botão Erros de validação.](./media/valid-checker-validation-status-errors.png)

Somente as transações com um status de validação de **Êxito** serão inseridas nos demonstrativos transacionais. Para exibir transações com um status de **Erro**, revise o bloco **Falhas na validação de cash and carry** no espaço de trabalho **Finanças da loja**.

![Blocos no espaço de trabalho Finanças da loja.](./media/valid-checker-cash-carry-validation-failures.png)

Para obter mais informações sobre como corrigir falhas de cash and carry, confira [Editar e auditar transações cash and carry e de gerenciamento de caixa](edit-cash-trans.md).

## <a name="additional-resources"></a>Recursos adicionais

[Editar e auditar transações cash and carry e de gerenciamento de caixa](edit-cash-trans.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
