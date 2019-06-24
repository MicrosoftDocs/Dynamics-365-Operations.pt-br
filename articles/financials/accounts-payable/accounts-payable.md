---
title: Home page de Contas a pagar
description: Este tópico oferece uma visão geral de contas a pagar.
author: ShylaThompson
manager: AnnBe
ms.date: 02/15/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 21901
ms.assetid: 1e4c2ac4-077b-4678-8733-5cec8f6ff659
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: f1acf2bade2bb279a35fdf4689bbbcc49e64101f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1559448"
---
# <a name="accounts-payable-home-page"></a>Home page de Contas a pagar

[!include [banner](../includes/banner.md)]

Este tópico oferece uma visão geral de contas a pagar. 

Você pode inserir faturas de fornecedor manualmente ou recebê-las eletronicamente por uma entidade de dados. Depois que as faturas são lançadas ou recebidas, você pode revisar e aprovar as faturas usando um diário de aprovação de faturas ou a página **Fatura de fornecedor**. Você pode usar a conciliação de faturas, as políticas de faturas de fornecedor e o fluxo de trabalho para automatizar o processo de revisão, para que as faturas que atenderem a certos critérios sejam aprovadas automaticamente, e as faturas restantes sejam sinalizadas para revisão por um usuário autorizado.

**Processos de negócios**

[![Processo de negócios](./media/AP-process.PNG)](./media/AP-process.PNG)

## <a name="set-up-accounts-payable"></a>Configurar Contas a pagar

Configure grupos de fornecedores, fornecedores, perfis de lançamento, várias opções de pagamento e parâmetros relacionados a fornecedores, encargos, entregas e destinos, notas promissórias e outros tipos de informações de Contas a pagar. 

[Configurar Contas a pagar](accounts-payable-overview.md)

[Distribuições contábeis e entradas no diário-razão auxiliar para faturas de fornecedor](accounting-distributions-subledger-journal-entries-vendor-invoices.md) 

[Reavaliação de moeda estrangeira para Contas a pagar e Contas a receber](../cash-bank-management/foreign-currency-revaluation-accounts-payable-accounts-receivable.md)

## <a name="configure-vendor-invoices"></a>Configurar faturas de fornecedor

Use Contas a pagar para rastrear faturas e despesas de saída para fornecedores.

[Conciliação de faturas de contas a pagar](accounts-payable-invoice-matching.md)

[Perfis de lançamentos de fornecedores](vendor-posting-profiles.md)

[Configurar a validação de conciliação de faturas de contas a pagar](tasks/set-up-accounts-payable-invoice-matching-validation.md)

[Políticas de conciliação tripla](three-way-matching-policies.md)

[Conciliação de faturas e ordens de compra intercompanhia](invoice-matching-intercompany-purchase-orders.md)

[Resolver discrepâncias durante a conciliação de totais de fatura](resolve-invoice-totals-invoice-matching-discrepancies.md)

[Contrapartidas padrão para diários de faturas de fornecedor e diários de aprovações de faturas](default-offset-accounts-vendor-invoice-journals.md)

[Aprovações de faturas móveis](mobile-invoice-approvals.md)

[Espaço de trabalho de faturamento da colaboração de fornecedores](vendor-portal-invoicing-workspace.md)

[Automação de faturas de fornecedores](vendor-invoice-automation.md)

## <a name="configure-vendor-payments"></a>Configurar pagamentos de fornecedores 

Atribua um tipo de pagamento definido pelo sistema, como cheque, pagamento eletrônico ou nota promissória, a qualquer método de pagamento definido pelo usuário. Os tipos de pagamentos são opcionais, mas são úteis quando você valida pagamentos eletrônicos e quer ter a possibilidade de determinar rapidamente o tipo de um pagamento. 

[Espaço de trabalho de pagamentos de fornecedores](vendor-payments-workspace.md)

[Definir taxas de pagamento de fornecedor](tasks/define-vendor-payment-fees.md)

[Definir condições de pagamento de fornecedor](tasks/define-vendor-payment-terms.md)

[Visão geral de pagamento positivo](positive-pay-overview.md)

[Configurar e gerar arquivos de pagamento positivo](set-up-generate-positive-pay-files.md)

[Criar pagamentos de fornecedores usando uma proposta de pagamento](create-vendor-payments-payment-proposal.md)

[Pagamentos de fornecedores para um valor parcial](vendor-payments-partial-amount.md)

[Obter um desconto maior que o desconto calculado para um pagamento de fornecedor](take-discount-more-calculated-discount-vendor-payment.md)

[Obter um desconto à vista fora do período de desconto à vista](take-cash-discount-outside-cash-discount-timeframe.md)

[Relatório eletrônico para cheques de fornecedores](electronic-reporting-sample-vendor-checks.md)

[Reverter um pagamento de fornecedor](reverse-vendor-payment.md)

[Visão geral de faturas de pagamento antecipado e de pagamentos antecipados](prepayments-invoices-vs-prepayments.md)

[Pagamentos centralizados de Contas a pagar](centralized-payments-accounts-payable.md)

## <a name="settlements"></a>Liquidações

Os seguintes tópicos fornecem informações sobre liquidações. A liquidação é o processo de liquidar pagamentos com faturas. 

[Configurar liquidação](../cash-bank-management/configure-settlement.md)

[Liquidar um pagamento parcial de fornecedor antes da data do desconto](settle-partial-vendor-payment-before-discount-or-final-payment-after.md)

[Liquidar um pagamento parcial de fornecedor que tem descontos sobre notas de crédito de fornecedor](settle-partial-vendor-payment-discounts-vendor-credit-notes.md)

[Liquidar um pagamento parcial de fornecedor que tem vários períodos de desconto](settle-partial-vendor-payment-multiple-discount-periods.md)

[Liquidar um pagamento parcial ou pagamento final de fornecedor antes do desconto](settle-partial-vendor-payment-or-final-payment-before-discount.md)

[Comprovante único com vários registros de cliente ou de fornecedor](single-voucher-multiple-customer-vendor-records.md)



### <a name="additional-resources"></a>Recursos adicionais

#### <a name="whats-new-and-in-development"></a>Novidades e o que está em desenvolvimento

Acesse as [Notas de versão do Microsoft Dynamics 365](https://go.microsoft.com/fwlink/?linkid=2010158) para ver quais novos recursos estão planejados. 

#### <a name="blogs"></a>Blogs

Você encontra opiniões, notícias, além de informações sobre Contas a pagar e outras soluções no [blog do Microsoft Dynamics 365](https://community.dynamics.com/b/msftdynamicsblog?c=Enterprise)e no [blog de finanças do Microsoft Dynamics 365 Finance and Operations](https://community.dynamics.com/365/financeandoperations/b/financials).

O [Blog da Comunidade de Parceiros do Microsoft Dynamics Operations](https://community.dynamics.com/partner/b/operationspartnercommunityblog) fornece aos Parceiros do Microsoft Dynamics um recurso único para saberem mais sobre as novidades e as tendências do MBS Operations.

#### <a name="community-blogs"></a>Blogs da comunidade

[Como gerenciar contas a pagar no Dynamics 365 for Finance and Operations](https://financefunction.tech/2019/02/15/how-to-manage-payables-in-dynamics-365-for-finance-and-operations)

#### <a name="task-guides"></a>Guias de tarefas
Há ajuda adicional disponível como guias de tarefas dentro do Finance and Operations. Para acessar os guias de tarefas, clique no botão Ajuda em qualquer página.

#### <a name="videos"></a>Vídeos

Confira os vídeos de instruções que agora estão disponíveis no [canal do Microsoft Dynamics 365 no YouTube](https://www.youtube.com/channel/UCJGCg4rB3QSs8y_1FquelBQ).




