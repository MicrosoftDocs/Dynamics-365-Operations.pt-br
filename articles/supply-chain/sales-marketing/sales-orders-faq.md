---
title: Perguntas frequentes sobre ordens de venda
description: Esta página aborda as perguntas frequentes que aparecem ao trabalhar com ordens de venda no Dynamics 365 Supply Chain Management.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d75022dcc476052040b16c9033cf5ff2a697ae6c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475571"
---
# <a name="sales-order-faqs"></a>Perguntas frequentes sobre ordens de venda

Esta página aborda as perguntas frequentes que aparecem ao trabalhar com ordens de venda no Dynamics 365 Supply Chain Management.

## <a name="can-i-link-a-purchase-order-to-a-sales-order-to-fulfill-demand"></a>É possível vincular uma ordem de compra a uma ordem de venda para atender a demanda?

Você pode criar uma ordem de compra de uma ordem de venda. Para obter mais informações, consulte [Criar uma ordem de compra de uma ordem de venda](/dynamics365/supply-chain/sales-marketing/tasks/create-purchase-order-sales-order).

## <a name="can-i-cancel-or-delete-a-sales-order-or-return-order"></a>Posso cancelar ou excluir uma ordem de venda ou ordem de devolução?

Você pode cancelar somente ordens de venda e ordens de devolução que estão em um estado *Criado*. Para obter mais informações, consulte [Cancelar uma ordem de devolução](/dynamics365/supply-chain/service-management/cancel-return-order).

## <a name="can-i-restore-an-invoiced-sales-order-that-was-deleted"></a>É possível restaurar uma ordem de venda faturada que foi excluída?

Se uma ordem de venda faturada tiver sido excluída por engano e você puder restaurá-la ou exibir seus detalhes.

Acesse **Conta de cliente \> Transações \> Documento original \> Exibir detalhes**. Localize a fatura que você está procurando e selecione-a para exibir os detalhes. Esses detalhes incluem a referência da ordem de venda. Você também deve ser capaz de acessar os detalhes da ordem de venda nessa página.

## <a name="how-do-i-delete-orphaned-sales-order-records"></a>Como faço para excluir registros órfãos da ordem de venda?

Para limpar registros de ordem de venda órfãos, execute o trabalho periódico *Exclusão da ordem de venda* indo para um dos seguintes locais:

- Vendas e marketing \> Tarefas periódicas \> Limpar \> Excluir ordens de venda
- Varejo e comércio \> TI de Varejo e Comércio \> Limpar \> Excluir ordens de venda

## <a name="is-there-a-way-to-calculate-commissions-on-invoices-that-have-already-been-posted"></a>Existe alguma forma de calcular comissões sobre faturas que já foram lançadas?

O Supply Chain Management não oferece suporte no momento ao cálculo de comissões para faturas lançadas.
