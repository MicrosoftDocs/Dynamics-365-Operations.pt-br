---
title: Criar pagamentos de fornecedor usando uma proposta de pagamento
description: "Este tópico oferece uma visão geral das opções de proposta de pagamento e inclui alguns exemplos que mostram como as propostas de pagamento funcionam. Com frequência, as propostas de pagamento são usadas para criar pagamentos de fornecedor, já que a consulta de proposta de pagamento pode ser usada para selecionar rapidamente as faturas de fornecedor para pagamento com base em critérios como a data de vencimento e o desconto à vista."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14312
ms.assetid: 585d5b0b-1b79-4a03-ab18-528918070377
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 2cb439e871d57f74c296697cfc42705fb0121bb7
ms.openlocfilehash: b46037b9509f329e18f0da69d530f6b1f88c8888
ms.lasthandoff: 03/31/2017


---

# <a name="create-vendor-payments-by-using-a-payment-proposal"></a>Criar pagamentos de fornecedor usando uma proposta de pagamento

Este tópico oferece uma visão geral das opções de proposta de pagamento e inclui alguns exemplos que mostram como as propostas de pagamento funcionam. Com frequência, as propostas de pagamento são usadas para criar pagamentos de fornecedor, já que a consulta de proposta de pagamento pode ser usada para selecionar rapidamente as faturas de fornecedor para pagamento com base em critérios como a data de vencimento e o desconto à vista. 

Com frequência, a organização usa propostas de pagamento para criar pagamentos de fornecedor, já que a consulta de proposta de pagamento pode ser usada para selecionar rapidamente as faturas de fornecedor para pagamento com base na data de vencimento, no desconto à vista e em outros critérios. 

A consulta de proposta de pagamento contém diversas guias, cada uma com diferentes opções para a seleção de faturas para pagamento. ** Parâmetro ** guia contém as que mais de uma organização do uso mais freqüência. ** Os registros a incluir em FastTab **, você pode especificar que a nota ou fornecedores a ser incluído para pagamento para definir intervalos mais características. Por exemplo, se quiser pagar somente um intervalo específico de fornecedores, você pode definir um filtro para o intervalo de fornecedores. Essa funcionalidade é usada para selecionar notas fiscais para um determinado de método de pagamento. Por exemplo, se você definir um filtro onde ** método de pagamento ** = ** cheque **, somente as notas fiscais que tenham o método de pagamento estiver selecionado para pagamento, desde que satisfaçam também outros critérios que são especificados na consulta. A guia **Parâmetros avançados** contém outras opções, algumas das quais podem não ser relevantes para a sua organização. Por exemplo, esta guia contém as opções para pagar faturas para pagamentos centralizados.

## <a name="parameters"></a>Parâmetros
-   ** Selecione as notas fiscais de notas fiscais – por ** no intervalo de data especificado por ** de data e ** ** até ** por campos podem ser selecionadas por data de vencimento, por data de desconto à vista, ou ambos. Se você usar a data de desconto à vista, o sistema procura primeiro as notas fiscais que têm uma data de desconto à vista entre de e até. O sistema determina se a fatura está qualificada para o desconto à vista usando a data da sessão para garantir que a data de desconto à vista ainda não passou.
-   **Data inicial** e** Data final** – as faturas com uma data de vencimento ou uma data de desconto à vista dentro desse intervalo de datas são selecionadas para pagamento.
-   **Data de pagamento** – se uma data for definida, todos os pagamentos serão criados nessa data. O campo **Data de pagamento mínima** será ignorado.
-   **Data de pagamento mínima** – insira a data de pagamento mínima. Por exemplo, data ** ** de e até ** ** campos especifique um intervalo do 1º de setembro ao 10 de setembro, e a data de pagamento mínimo. é o 5 de setembro Nesse caso, todas as notas fiscais que vencem do 1º de setembro ao 5 de setembro ter uma data de pagamento de 5 de setembro. Entretanto, notas fiscais que vencem do 5 de setembro ao 10 de setembro ter uma data de liquidação que seja igual à data de vencimento de cada nota fiscal.
-   **Limite de valor** – insira o valor total máximo para todos os pagamentos.
-   ** Criar acordos sem visualização fiscal ** – se essa opção está definida ** Sim **, os pagamentos serão criadas imediatamente ** ** pagamentos de fornecedor na página. ** Proposta de pagamento ** o página será ignorado. Consequentemente, os pagamentos serão criados com mais rapidez. Os pagamentos ainda podem ser modificados na página **Pagamentos de fornecedor**. Como alternativa, você pode voltar para a página **Proposta de pagamento** usando o botão **Editar faturas para pagamento selecionado**.

## <a name="advanced-options"></a>Opções avançadas
-   **Verificar saldo de fornecedor** – se essa opção for definida como **Sim**, o sistema verificará se um fornecedor não possui um saldo de débito antes de qualquer fatura ser paga. Se um fornecedor tiver um saldo devedor, nenhum pagamento será criado. Por exemplo, o fornecedor pode ter memorandos de crédito, ou pagamentos lançados mas não liquidados. Nesses casos, o fornecedor não deve ser pago. Em vez disso, as notas de crédito ou os pagamentos devem ser liquidados em relação às faturas pendentes.
-   **Excluir pagamentos negativos** – essa opção funciona de forma diferente, dependendo de os pagamentos serem efetuados para as faturas individuais ou para a soma das faturas que atendam aos critérios de pagamento. Esse comportamento é definido no método de pagamento.
-   **Pagamento para cada fatura** – se a opção **Excluir pagamentos negativos** for definida como **Sim**, e se houver uma fatura e um pagamento não liquidados para um fornecedor, apenas a fatura será marcada para pagamento. O pagamento existente não é liquidado com a fatura. Se a opção **Excluir pagamentos negativos** for definida como **Não**, e se uma fatura e um pagamento não estiverem liquidados, a fatura e o pagamento serão selecionados para pagamento. Um pagamento foi criado para o pagamento, e um reembolso (pagamento negativo) foi criado para o pagamento.
-   **Pagamento para a soma de faturas** – se a opção **Excluir pagamentos negativos** for definida como **Sim**, e se houver uma fatura e um pagamento não liquidados para um fornecedor, a fatura e o pagamento não liquidados serão selecionados para pagamento e os valores serão somados para produzir o valor total do pagamento. A única exceção ocorrerá se a soma resultar em um reembolso. Nesse caso, nem a fatura nem o pagamento serão selecionados. ** Se pagamentos negativos de exclusão ** a opção é definida ** nenhum **, e uma nota fiscal e um pagamento não será liquidada, a nota fiscal e o pagamento está marcada para o pagamento, os valores serão adicionadas juntas para gerar o valor do pagamento total.
-   **Imprimir apenas o relatório** – defina essa opção como **Sim** para ver os resultados da proposta de pagamento em um relatório, mas sem criar quaisquer pagamentos.
-   **Incluir faturas de fornecedor de outras entidades legais** – se sua organização tiver um processo centralizado para pagamento, e se a proposta de pagamento tiver de incluir faturas de outras entidades legais incluídas nos critérios da pesquisa, defina essa opção como **Sim**.
-   **Propõe o pagamento de fornecedor separados por pessoa jurídica** – se essa opção for definida como **Sim**, um pagamento separado será criado para cada entidade legal por fornecedor. O fornecedor no pagamento é o fornecedor da fatura de cada entidade legal. Se essa opção for definida como **Não**, e se o mesmo fornecedor tiver faturas em várias entidades legais, um pagamento será criado para o valor total das faturas selecionadas. O fornecedor no pagamento é o fornecedor na entidade legal atual. Se a conta do fornecedor não existir na entidade legal atual, será usada a conta do fornecedor da primeira fatura que deve ser paga.
-   ** A moeda de pagamento ** – este campo especifica a moeda que todos os pagamentos serão criados. Se uma moeda não for definida, cada nota fiscal é paga na moeda da nota fiscal.
-   **Dia da semana de pagamento** – insira o dia da semana em que o pagamento deve ser feito. Esse campo só será usado se o método de pagamento for configurado para o total de faturas para pagamento em um determinado dia da semana.
-   ** Tipo de contrapartida ** ** e contrapartida ** – definir esses campos para definir um tipo de conta específico (como ** ** ** razão ou banco **) e a contrapartida (como uma conta bancária específica). O método de pagamento para a fatura define o tipo de contrapartida e a contrapartida padrão, mas você pode usar esses campos para substituir os valores padrão.
-   ** Filtros adicionais ** ** – os registros a incluir em FastTab **, defina intervalos adicionais dos critérios. Por exemplo, se quiser pagar somente um intervalo de fornecedores, você pode definir um filtro para o intervalo de fornecedores. Essa funcionalidade é usada para selecionar notas fiscais para um determinado de método de pagamento. Por exemplo, se você definir um filtro onde ** método de pagamento ** = ** cheque **, somente as notas fiscais que tenham o método de pagamento estiver selecionado para pagamento, desde que satisfaçam também outros critérios que são especificados na consulta.

## <a name="scenarios"></a>Cenários
| Fornecedor | Fatura | Data da fatura | Valor da fatura | Data de conclusão | Data do desconto à vista | Valor de desconto à vista |
|--------|---------|--------------|----------------|----------|--------------------|----------------------|
| 3050   | 1001    | 15 de junho      | 500,00         | 15 de julho  | 29 de junho            | 10.00                |
| 3050   | 1002    | 20 de junho      | 600,00         | 20 de julho  | 4 de julho             | 12:00                |
| 3075   | 1003    | 15 de junho      | 250,00         | 29 de junho  |                    | 0,00                 |
| 3100   | 1004    | 17 de junho      | 100,00         | 17 de julho  | 1 de julho             | 1.00                 |

Em 1º de julho, April paga os fornecedores. Ela usa uma proposta de pagamento para ajudar a concluir essa tarefa de modo mais eficiente.

### <a name="option-1-by-cash-discount"></a>Opção 1: Por desconto à vista

Alice seleciona **Desconto à vista** como o tipo de proposta. Inserir um intervalo de datas de do 26 de junho ao 10 de julho. Estas são notas fiscais incluídas na proposta:

-   1002, porque a data de desconto de 4 de julho está no intervalo de datas de pagamento.
-   1004, porque a data de desconto de 1º de julho está no intervalo de datas de pagamento.

As faturas a seguir não são incluídas na proposta:

-   1001, porque a data do desconto de 29 de junho já expirou e, portanto, essa fatura não está mais qualificada para o desconto à vista.
-   1003, porque essa fatura não tem uma data de desconto.

### <a name="option-2-by-due-date"></a>Opção 2: Por data de vencimento

Alice seleciona **Por data de vencimento** como o tipo de proposta. Inserir um intervalo de datas de do 26 de junho ao 10 de julho. Estas são notas fiscais incluídas na proposta:

-   1003, porque a data de vencimento de 29 de junho está no intervalo de datas de pagamento.

As faturas a seguir não são incluídas na proposta:

-   1001, porque a data de vencimento de 15 de julho está fora do intervalo de datas de pagamento.
-   1002, porque a data de vencimento de 20 de julho está fora do intervalo de datas de pagamento.
-   1004, porque a data de vencimento de 17 de julho está fora do intervalo de datas de pagamento.

### <a name="option-3-by-due-date-and-cash-discount"></a>Opção 3: Por data de vencimento e desconto à vista

Alice seleciona **Data de vencimento e desconto à vista** como o tipo de proposta. Inserir um intervalo de datas de do 26 de junho ao 10 de julho. Estas são notas fiscais incluídas na proposta:

-   1003, porque a data de vencimento de 29 de junho está no intervalo de datas de pagamento.
-   1002, porque a data de desconto de 4 de julho está no intervalo de datas de pagamento.
-   1004, porque a data de desconto de 1º de julho está no intervalo de datas de pagamento.

As faturas a seguir não são incluídas na proposta:

-   1001, porque a data do desconto de 29 de junho já expirou e, portanto, essa fatura não está mais qualificada para o desconto à vista e a data de vencimento de 15 de julho também está fora do intervalo de datas.

## <a name="country-specific-considerations"></a>Considerações específicas por país
### <a name="norway"></a>Noruega

#### <a name="dimension-control"></a>Controle de dimensão

O controle de dimensão permite que você controle ao agrupar linhas gerados por meio de pagamento e define as dimensões baseadas padrão usadas dimensões financeiras das faturas aplicadas. No contexto norueguês de país para cada método de pagamento da guia dimensão financeira que você poderá ativar o controle de dimensão e para habilitar o agrupamento para cada dimensão. As opções disponíveis são:

-   O campo **Controle de dimensão** é desabilitado. A proposta de pagamento comporta-se quanto para qualquer outro país.
-   O campo **Controle de dimensão** é ativado sem definir ainda mais as dimensões. A proposta de pagamento será criada sem levar em consideração dimensões. A transação não será herdado criada nenhuma dimensão de entrada aplicada.
-   O campo **Controle de dimensão** é ativado e as dimensões adicionais são habilitadas. Agora você define como as dimensões serão copiadas para o diário. Por exemplo: • Selecione BusinessUnit ** ** a caixa de seleção para criar uma proposta de pagamento por unidade de negócios para o método de pagamento, • Selecione CostCenter ** ** a caixa de seleção para criar uma proposta de pagamento por centro de custos para o método de pagamento

**Nota:** Se você selecionar mais de uma dimensão na terceira opção, será criada uma proposta de pagamento para a combinação de dimensões.

#### <a name="bank-account-selection"></a>Seleção de conta bancária

Você pode definir um padrão que debita a conta de pagamento por método de indiferente contexto do país de pagamento. Isso será definida nas linhas de pagamento geradas pela proposta. Com o recurso de conta bancária, você pode definir o múltiplo que debita contas bancárias gerenciadas por dimensão e a moeda ou uma combinação desses usar contas bancárias de débito diferentes, dependendo cada combinação. Você pode configurar a página nessas combinações ** métodos de pagamento usando ** ** contas bancárias ** botão disponível para cada método de pagamento com ** tipo de conta de postagem ** = ** ** banco.


