---
title: Criar pagamentos de fornecedor usando uma proposta de pagamento
description: Este tópico oferece uma visão geral das opções de proposta de pagamento e inclui alguns exemplos que mostram como as propostas de pagamento funcionam.
author: abruer
ms.date: 04/04/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.custom: 14312
ms.assetid: 585d5b0b-1b79-4a03-ab18-528918070377
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 125cc9dd1fb2ba0d3aeced8018d15e615b5d78e6
ms.sourcegitcommit: cabd991fda2bfcabb55db84c225b24a7bb061631
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "6027833"
---
# <a name="create-vendor-payments-by-using-a-payment-proposal"></a>Criar pagamentos de fornecedores usando uma proposta de pagamento

[!include [banner](../includes/banner.md)]

Este tópico oferece uma visão geral das opções de proposta de pagamento e inclui alguns exemplos que mostram como as propostas de pagamento funcionam. Com frequência, as propostas de pagamento são usadas para criar pagamentos de fornecedor, já que a consulta de proposta de pagamento pode ser usada para selecionar rapidamente as faturas de fornecedor para pagamento com base em critérios como a data de vencimento e o desconto à vista. 

Com frequência, a organização usa propostas de pagamento para criar pagamentos de fornecedor, já que a consulta de proposta de pagamento pode ser usada para selecionar rapidamente as faturas de fornecedor para pagamento com base na data de vencimento, no desconto à vista e em outros critérios. 

A consulta de proposta de pagamento contém diversas guias, cada uma com diferentes opções para a seleção de faturas para pagamento. A guia **Parâmetro** contém opções que a maior parte da organização usa com mais frequência. Na Guia Rápida **Registros a serem incluídos**, você pode especificar qual fatura ou fornecedor será incluído definindo intervalos para várias características. Por exemplo, para pagar apenas a um intervalo específico de fornecedores, você pode definir um filtro para o intervalo de fornecedores. Essa funcionalidade é frequentemente usada para selecionar faturas para um método específico de pagamento. Por exemplo, se você definir um filtro onde **Método de pagamento** = **Verificação**, somente as faturas com esse método de pagamento serão selecionadas para pagamento, contanto que também satisfaçam outros critérios especificados na consulta. A guia **Parâmetros avançados** contém outras opções, algumas das quais podem não ser relevantes para a sua organização. Por exemplo, esta guia contém as opções para pagar faturas para pagamentos centralizados.

## <a name="parameters"></a>Parâmetros
-   **Selecionar faturas por** – Faturas no intervalo de datas especificado pelos campos **Data inicial** e **Data final** podem ser selecionadas por data de vencimento, data de desconto à vista ou ambas. Se usar a data de desconto à vista, o sistema procurará primeiro as faturas que têm uma data de desconto à vista entre a data inicial e a data final. O sistema determina se a fatura está qualificada para o desconto à vista usando a data da sessão para garantir que a data de desconto à vista ainda não passou.
-   **Data inicial** e **Data final** – as faturas com uma data de vencimento ou uma data de desconto à vista dentro desse intervalo de datas são selecionadas para pagamento.
-   **Data de pagamento mínima** – insira a data de pagamento mínima. Por exemplo, os campos **Data inicial** e **Data final** especificam um intervalo de 1 de setembro a 10 de setembro, e a data de pagamento mínimo é 5 de setembro. Nesse caso, todas as faturas com vencimento entre 1 de setembro e 5 de setembro têm 5 de setembro como data de pagamento. Contudo, todas as faturas com vencimento entre 5 de setembro e 10 de setembro têm uma data de pagamento igual à data de vencimento de cada fatura.
-   **Limite de valor** – insira o valor total máximo para todos os pagamentos.
-   **Criar pagamentos sem a visualização de fatura** – Se você definir a opção como **Sim**, os pagamentos serão criados imediatamente na página **Pagamentos de fornecedor**. A página **Proposta de pagamento** será ignorada. Consequentemente, os pagamentos serão criados com mais rapidez. Os pagamentos ainda podem ser modificados na página **Pagamentos de fornecedor**. Como alternativa, você pode voltar para a página **Proposta de pagamento** usando o botão **Editar faturas para pagamento selecionado**.

## <a name="advanced-options"></a>Opções avançadas
- **Verificar saldo de fornecedor** – se essa opção for definida como **Sim**, o sistema verificará se um fornecedor não possui um saldo de débito antes de qualquer fatura ser paga. Se um fornecedor tiver um saldo de débito, nenhum pagamento será criado. Por exemplo, o fornecedor pode ter notas de crédito, ou pagamentos que foram lançados mas não liquidados. Nesses casos, o fornecedor não deve ser pago. Em vez disso, as notas de crédito ou os pagamentos devem ser liquidados em relação às faturas pendentes.
- **Excluir pagamentos negativos** – essa opção funciona de forma diferente, dependendo de os pagamentos serem efetuados para as faturas individuais ou para a soma das faturas que atendam aos critérios de pagamento. Esse comportamento é definido no método de pagamento.
- **Pagamento para cada fatura** – se a opção **Excluir pagamentos negativos** for definida como **Sim**, e se houver uma fatura e um pagamento não liquidados para um fornecedor, apenas a fatura será marcada para pagamento. O pagamento existente não é liquidado com a fatura. Se a opção **Excluir pagamentos negativos** for definida como **Não**, e se uma fatura e um pagamento não estiverem liquidados, a fatura e o pagamento serão selecionados para pagamento. Um pagamento foi criado para o pagamento, e um reembolso (pagamento negativo) foi criado para o pagamento.
- **Pagamento para a soma de faturas** – se a opção **Excluir pagamentos negativos** for definida como **Sim**, e se houver uma fatura e um pagamento não liquidados para um fornecedor, a fatura e o pagamento não liquidados serão selecionados para pagamento e os valores serão somados para produzir o valor total do pagamento. A única exceção ocorrerá se a soma resultar em um reembolso. Nesse caso, nem a fatura nem o pagamento serão selecionados. Se a opção **Excluir pagamentos negativos** for definida como **Não** e se não houver uma fatura e um pagamento liquidados, a fatura e o pagamento serão selecionados para pagamento e os valores serão somados para produzir o valor total do pagamento.
- **Imprimir apenas o relatório** – defina essa opção como **Sim** para ver os resultados da proposta de pagamento em um relatório, mas sem criar quaisquer pagamentos.
- **Incluir faturas de fornecedor de outras entidades legais** – se sua organização tiver um processo centralizado para pagamento, e se a proposta de pagamento tiver de incluir faturas de outras entidades legais incluídas nos critérios da pesquisa, defina essa opção como **Sim**.
- **Propõe o pagamento de fornecedor separados por pessoa jurídica** – se essa opção for definida como **Sim**, um pagamento separado será criado para cada entidade legal por fornecedor. O fornecedor no pagamento é o fornecedor da fatura de cada entidade legal. Se essa opção for definida como **Não**, e se o mesmo fornecedor tiver faturas em várias entidades legais, um pagamento será criado para o valor total das faturas selecionadas. O fornecedor no pagamento é o fornecedor na entidade legal atual. Se a conta do fornecedor não existir na entidade legal atual, será usada a conta do fornecedor da primeira fatura que deve ser paga.
- **Moeda do pagamento** – Esse campo especifica a moeda em que todos os pagamentos são criados. Se uma moeda não for definida, cada fatura será paga na moeda da fatura.
- **Dia da semana de pagamento** – insira o dia da semana em que o pagamento deve ser feito. Esse campo só será usado se o método de pagamento for configurado para o total de faturas para pagamento em um determinado dia da semana.
- **Tipo de contrapartida** e **Contrapartida** – Defina esses campos para definir um tipo de conta específico (como **Razão** ou **Banco**) e a contrapartida (como uma conta bancária específica). O método de pagamento da fatura define o tipo de contrapartida e a contrapartida padrão, mas você pode usar esses campos para substituir os valores padrão.
- **Data do pagamento resumido** – Isso será usado somente quando o campo **Período** no método de pagamento estiver definido como **Total**. Se uma data for definida, todos os pagamentos serão criados nessa data. O campo **Data de pagamento mínima** será ignorado.
- **Filtros adicionais** – na Guia Rápida **Registros a serem incluídos**, você pode definir intervalos adicionais de critérios. Por exemplo, se você quiser pagar somente um intervalo de fornecedores, poderá definir um filtro para o intervalo de fornecedores. Essa funcionalidade é frequentemente usada para selecionar faturas para um método específico de pagamento. Por exemplo, se você definir um filtro onde **Método de pagamento** = **Verificação**, somente as faturas com esse método de pagamento serão selecionadas para pagamento, contanto que também satisfaçam outros critérios especificados na consulta.

## <a name="scenarios"></a>Cenários

| Fornecedor | Fatura | Data da fatura | Valor da fatura | Data de conclusão | Data do desconto à vista | Valor de desconto à vista |
|--------|---------|--------------|----------------|----------|--------------------|----------------------|
| 3050   | 1001    | 15 de junho      | 500,00         | 15 de julho  | 29 de junho            | 10.00                |
| 3050   | 1002    | 20 de junho      | 600,00         | 20 de julho  | 4 de julho             | 12:00                |
| 3075   | 1003    | 15 de junho      | 250,00         | 29 de junho  |                    | 0,00                 |
| 3100   | 1004    | 17 de junho      | 100,00         | 17 de julho  | 1 de julho             | 1.00                 |

Em 1º de julho, April paga os fornecedores. Ela usa uma proposta de pagamento para ajudar a concluir essa tarefa de modo mais eficiente.

### <a name="option-1-by-cash-discount"></a>Opção 1: Por desconto à vista

Alice seleciona **Desconto à vista** como o tipo de proposta. Ela insere um intervalo de datas de 26 de junho a 10 de julho. As seguintes faturas são incluídas na proposta:

-   1002, porque a data de desconto de 4 de julho está no intervalo de datas de pagamento.
-   1004, porque a data de desconto de 1º de julho está no intervalo de datas de pagamento.

As faturas a seguir não são incluídas na proposta:

-   1001, porque a data do desconto de 29 de junho já expirou e, portanto, essa fatura não está mais qualificada para o desconto à vista.
-   1003, porque essa fatura não tem uma data de desconto.

### <a name="option-2-by-due-date"></a>Opção 2: Por data de vencimento

Alice seleciona **Por data de vencimento** como o tipo de proposta. Ela insere um intervalo de datas de 26 de junho a 10 de julho. As seguintes faturas são incluídas na proposta:

-   1003, porque a data de vencimento de 29 de junho está no intervalo de datas de pagamento.

As faturas a seguir não são incluídas na proposta:

-   1001, porque a data de vencimento de 15 de julho está fora do intervalo de datas de pagamento.
-   1002, porque a data de vencimento de 20 de julho está fora do intervalo de datas de pagamento.
-   1004, porque a data de vencimento de 17 de julho está fora do intervalo de datas de pagamento.

### <a name="option-3-by-due-date-and-cash-discount"></a>Opção 3: Por data de vencimento e desconto à vista

Alice seleciona **Data de vencimento e desconto à vista** como o tipo de proposta. Ela insere um intervalo de datas de 26 de junho a 10 de julho. As seguintes faturas são incluídas na proposta:

-   1003, porque a data de vencimento de 29 de junho está no intervalo de datas de pagamento.
-   1002, porque a data de desconto de 4 de julho está no intervalo de datas de pagamento.
-   1004, porque a data de desconto de 1º de julho está no intervalo de datas de pagamento.

As faturas a seguir não são incluídas na proposta:

-   1001, porque a data do desconto de 29 de junho já expirou e, portanto, essa fatura não está mais qualificada para o desconto à vista e a data de vencimento de 15 de julho também está fora do intervalo de datas.

## <a name="country-specific-considerations"></a>Considerações específicas por país
### <a name="norway"></a>Noruega

#### <a name="dimension-control"></a>Controle de dimensão

O controle de dimensão permite que você controle ao agrupar linhas gerados por meio de pagamento e define as dimensões baseadas padrão usadas dimensões financeiras das faturas aplicadas. No contexto do país norueguês, para cada método de pagamento, há uma guia de dimensão financeira em que você pode ativar o controle de dimensão e habilitar o agrupamento para cada dimensão. As opções disponíveis são:

-   O campo **Controle de dimensão** é desabilitado. A proposta de pagamento comporta-se quanto para qualquer outro país.
-   O campo **Controle de dimensão** é ativado sem definir ainda mais as dimensões. A proposta de pagamento será criada sem levar em consideração dimensões. A transação não será herdado criada nenhuma dimensão de entrada aplicada.
-   O campo **Controle de dimensão** é ativado e as dimensões adicionais são habilitadas. Agora você define como as dimensões serão copiadas para o diário. Por exemplo: • marque a caixa de seleção **BusinessUnit** para criar uma proposta de pagamento por unidade de negócios para o método de pagamento, • marque a caixa de seleção **CostCenter** para criar uma proposta de pagamento por centro de custos para o método de pagamento.

> [[!NOTE]
> Se você selecionar mais de uma dimensão na terceira opção, será criada uma proposta de pagamento para a combinação de dimensões.

#### <a name="bank-account-selection"></a>Seleção de conta bancária

Você pode definir um padrão que debita a conta de pagamento por método de indiferente contexto do país de pagamento. Isso será definido nas linhas de pagamento geradas pela proposta. Com o recurso de conta bancária, você pode definir várias contas bancárias de débito gerenciadas por dimensão e moeda ou uma combinação delas para usar diferentes contas bancárias de débito, dependendo de cada combinação. Configure essas combinações na página **Métodos de pagamento** usando o botão **Contas bancárias** disponível para cada método de pagamento com **Tipo de lançamento​ de conta** = **Banco**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]