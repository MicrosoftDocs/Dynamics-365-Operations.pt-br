---
title: Solucionar problemas de ordens de venda
description: Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com as ordens de venda.
author: SmithaNataraj
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 8f4a28b0cf47ec1c2534fc97c4dee6790fa6c51637bddf64caa7147e9ce6d6db
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746103"
---
# <a name="troubleshoot-sales-orders"></a>Solucionar problemas de ordens de venda

Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com as ordens de venda.

## <a name="the-tax-information-isnt-updated-if-i-change-the-location-on-a-sales-order-header"></a>As informações sobre impostos não são atualizadas quando altero o local em um cabeçalho de ordem de venda.

### <a name="issue-description"></a>Descrição do problema

Se o local, o depósito ou o endereço de entrega for alterado em um cabeçalho de ordem de venda ou no nível de linha, as informações de imposto do caso não serão atualizadas automaticamente para as linhas.

### <a name="issue-resolution"></a>Resolução do problema

Esse comportamento é por design. O problema ocorre porque o endereço de entrega, o site e o depósito não são alterados automaticamente no nível da linha. Você deve atualizá-los manualmente.

## <a name="if-there-are-two-trade-agreements-for-the-same-period-or-overlapping-periods-the-same-agreement-line-is-always-selected"></a>Se houver dois contratos comerciais para o mesmo período ou períodos sobrepostos, a mesma linha de contrato será sempre selecionada.

### <a name="issue-description"></a>Descrição do problema

Se dois contratos comerciais forem definidos para o mesmo período ou períodos sobrepostos, o mesmo contrato comercial parecerá ser selecionado toda vez que você criar linhas de ordem de venda que contenham esses itens.

### <a name="issue-resolution"></a>Resolução do problema

Se houver mais de um contrato comercial para uma determinada data, o contrato comercial com o menor preço será sempre selecionado. Para obter mais informações, baixe o seguinte white paper: [Contratos comerciais no Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).

## <a name="can-i-link-a-purchase-order-to-a-sales-order-to-fulfill-demand"></a>É possível vincular uma ordem de compra a uma ordem de venda para atender a demanda?

Você pode criar uma ordem de compra de uma ordem de venda. Para obter mais informações, consulte [Criar uma ordem de compra de uma ordem de venda](tasks/create-purchase-order-sales-order.md).

## <a name="i-cant-cancel-or-delete-a-return-order-or-a-sales-order"></a>Não consigo cancelar nem excluir uma ordem de devolução, nem uma ordem de venda.

Você pode cancelar somente ordens de venda e ordens de devolução que estão em um estado *Criado*. Para obter mais informações, consulte [Cancelar uma ordem de devolução](../service-management/cancel-return-order.md).

## <a name="when-i-try-to-cancel-a-sales-order-i-receive-a-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations-error"></a>Quando tento cancelar uma ordem de venda, recebo uma mensagem de erro "As reservas não podem ser removidas porque há um trabalho criado com base nas reservas".

Código de erro: WAX4661

Se o trabalho estiver associado a uma ordem de venda, não será possível cancelar a ordem de venda até que o trabalho seja cancelado e revertido. Esse requisito se aplica mesmo que o trabalho associado à ordem de venda seja fechado.

Para corrigir esse problema, siga estas etapas.

1. Cancele o trabalho e coloque o estoque novamente no local desejado. Acesse o carregamento relevante da ordem de venda e selecione **Reduzir quantidade separada** na linha de carga ou **Reverter trabalho** no Painel de Ações.

    O trabalho agora tem um status *Cancelado* e o novo trabalho de movimentação de estoque é criado automaticamente e processado para colocar o estoque de volta ao local descrito no momento da reversão.

2. Excluir a carga. A remessa também será excluída.
3. Agora, você poderá ir para a ordem de venda e cancelá-la.

## <a name="i-cant-cancel-an-intercompany-purchase-order-that-is-linked-to-a-sales-order"></a>Não consigo cancelar uma ordem de compra intercompanhia vinculada a uma ordem de venda.

### <a name="issue-description"></a>Descrição do problema

Se você tentar cancelar uma ordem de compra intercompanhia vinculada a uma ordem de venda, você poderá receber a seguinte mensagem de erro: "A quantidade não pode ser reduzida porque a quantidade de atualização restante muda o sinal."

### <a name="issue-resolution"></a>Resolução do problema

Esse problema foi corrigido no Microsoft Dynamics 365 Supply Chain Management, version 10.0.13. Nessa versão e em versões posteriores, agora você pode cancelar uma ordem de compra intercompanhia vinculada a uma ordem de venda.

## <a name="can-i-restore-an-invoiced-sales-order-that-was-deleted"></a>É possível restaurar uma ordem de venda faturada que foi excluída?

### <a name="issue-description"></a>Descrição do problema

Uma ordem de venda faturada foi excluída por engano e você deseja restaurá-la ou exibir seus detalhes.

### <a name="issue-resolution"></a>Resolução do problema

Se a ordem de venda excluída já foi faturada, Acesse **Conta do cliente \> Transações \> Documento original \> Exibir detalhes**. Localize a fatura que você está procurando e selecione-a para exibir os detalhes. Esses detalhes incluem a referência da ordem de venda. Você também deve ser capaz de acessar os detalhes da ordem de venda nessa página.

## <a name="the-deadline-of-a-sales-order-header-cant-be-found-in-the-salesorderheaderv2entity-data-entity"></a>O prazo final de um cabeçalho da ordem de venda não pode ser encontrado na entidade de dados SalesOrderHeaderV2Entity.

O campo prazo final não existe na entidade *SalesOrderHeaderV2Entity*.

## <a name="i-must-delete-orphaned-sales-order-records"></a>É preciso excluir registros órfãos da ordem de venda.

Para limpar registros de ordem de venda órfãos, execute o trabalho periódico *Exclusão da ordem de venda* indo para um dos seguintes locais:

- Vendas e marketing \> Tarefas periódicas \> Limpar \> Excluir ordens de venda
- Varejo e comércio \> TI de Varejo e Comércio \> Limpar \> Excluir ordens de venda

## <a name="is-there-a-way-to-calculate-commissions-on-invoices-that-have-already-been-posted"></a>Existe alguma forma de calcular comissões sobre faturas que já foram lançadas?

O Supply Chain Management não oferece suporte no momento ao cálculo de comissões para faturas lançadas.

## <a name="a-bundle-item-isnt-supported-in-an-intercompany-process"></a>Não há suporte para um item de pacote em um processo intercompanhia.

O item de pacote não está disponível para a ordem de compra porque, se você examinar as linhas da ordem de venda para o item de pacote, verá que a quantidade é *0* (zero) e o status é *Cancelado*. Esse comportamento é por design. A ordem de venda compra somente os componentes do item de pacote. Ele não compra o próprio item do pacote.

Se você precisar comprar um pacote, considere se é necessário marcá-lo como item de pacote porque essa funcionalidade foi criada para cenários de reconhecimento de receita. Para obter mais informações sobre itens do pacote, consulte [Pacotes](../../finance/accounts-receivable/revenue-recognition-setup.md#bundles).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]