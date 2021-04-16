---
title: Bloqueio de estoque
description: Este tópico oferece uma visão geral do bloqueio de estoque, que faz parte do processo de inspeção de qualidade no Supply Chain Management. Você pode usar o bloqueio de estoque para evitar que os itens sejam processados ou consumidos.
author: perlynne
ms.date: 03/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventBlocking, InventQualityOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2094
ms.assetid: 1968e32f-eff9-4c17-8f7f-a870f0c38fbc
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d07313050b59a32756fa5e31037f1831a2cbe862
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829875"
---
# <a name="inventory-blocking"></a>Bloqueio de estoque

[!include [banner](../includes/banner.md)]

Este tópico oferece uma visão geral do bloqueio de estoque, que faz parte do processo de inspeção de qualidade no Supply Chain Management. Você pode usar o bloqueio de estoque para evitar que os itens sejam processados ou consumidos.

Você pode bloquear itens de estoque das seguintes maneiras:

- Manualmente
- Criando uma ordem de qualidade
- Usando um processo que gera uma ordem de qualidade
- Usando um bloqueio de status de estoque

## <a name="blocking-items-manually"></a>Bloqueando itens manualmente

Você pode bloquear uma quantidade de um item criando uma transação na página **Bloqueio de estoque**. Somente os itens que estão disponíveis como estoque disponível podem ser bloqueados manualmente. Para quantidades bloqueadas manualmente, você deve decidir se as atividades de planejamento incluirão os recebimentos esperados como uma quantidade disponível esperada. Os recebimentos esperados são itens bloqueados que você espera que estejam disponíveis como inventário disponível após a conclusão da inspeção. É possível manter a data esperada. Por padrão, a opção **Recebimentos esperados** é selecionada para os itens bloqueados por meio de uma ordem de qualidade. Você pode cancelar o bloqueio manual em uma quantidade ao excluir a transação na página **Bloqueio de estoque**.

## <a name="blocking-items-by-creating-a-quality-order"></a>Bloqueando itens ao criar uma ordem de qualidade

Você pode especificar os itens que devem ser inspecionados ao criar uma ordem de qualidade na página **Ordens de qualidade**. Quando você criar uma ordem de qualidade, a quantidade especificada para um item será bloqueada. O plano de amostragem associado aos controles de uma ordem de qualidade controla somente a quantidade de itens que devem ser inspecionados, e não a quantidade que está bloqueada. A quantidade inserida na ordem de qualidade é a quantidade bloqueada, independentemente da quantidade que o plano de amostragem especifica que deve ser enviada para inspeção.

> [!NOTE]
> O uso dos recursos data de vencimento do lote e status do estoque de bloqueio não têm suporte no planejamento mestre. Isso pode resultar em dupla exclusão do estoque disponível, que pode ocorrer durante o planejamento mestre. Recomendamos que você se baseie nos códigos de disposição em lotes, em vez do status do estoque, para bloquear lotes expirados.

## <a name="blocking-items-by-using-a-process-that-generates-a-quality-order"></a>Bloqueando itens ao usar um processo que gera uma ordem de qualidade

Se um processo de qualidade especificar que um item deve ser inspecionado, uma quantidade do item será automaticamente bloqueada. Dessa forma, quando uma ordem de qualidade for gerada automaticamente, o plano de amostragem do item associado aos controles da ordem de qualidade controlará a quantidade de itens bloqueados, e não apenas a quantidade que deve ser inspecionada. Se a opção **Bloqueio total** da página **Amostragem de itens** estiver selecionada, a quantidade total de, por exemplo, uma linha de ordem de compra, será bloqueada durante a inspeção, independentemente da quantidade de amostragem do item.

### <a name="example"></a>Exemplo

No exemplo a seguir, uma ordem de qualidade será gerada quando uma guia de remessa de ordem de compra for lançada. Na página **Associações de qualidade**, você especificou que o lançamento de uma guia de remessa de ordem de compra será especificado como o processo que ativa uma ordem de qualidade.

|Configurar |Ação do usuário |Resultado |
|----|---|---|
| Uma associação de qualidade especifica que uma ordem de qualidade deverá ser gerada quando uma guia de remessa de ordem de compra for lançada. A configuração de amostragem do item da ordem de qualidade especifica que 10% da quantidade na linha de ordem de compra serão inspecionados. Além disso, por causa da opção **Bloqueio total** selecionada na configuração da amostragem de item, a quantidade total da linha de ordem de compra deverá ser bloqueada durante a inspeção, independentemente da quantidade que será enviada para inspeção. | A guia de remessa é lançada. | Uma ordem de qualidade é gerada. Dez por cento da quantidade da ordem de compra para o item serão enviados para inspeção. A quantidade total da linha de ordem de compra é bloqueada. |

## <a name="blocking-items-by-using-inventory-status-blocking"></a>Bloqueando itens ao usar um bloqueio de status de estoque

Você pode especificar quais status de estoque estão bloqueando os status usando o parâmetro **Bloqueio de estoque** na página **Status de estoque**. Você não pode usar status de estoque como status de bloqueio para ordens de produção, ordens de venda, ordens de transferência, transações de saída ou integrações de projeto. Para o trabalho de saída, use itens com status de estoque disponível. Se os itens tiverem um status **Quebrado** e se o planejamento mestre for executado nesses itens, os itens serão considerados ausentes e o estoque será reabastecido automaticamente.

## <a name="take-care-when-blocking-items-that-use-both-inventory-status-blocking-and-quality-order-blocking"></a>Tome cuidado ao bloquear itens que usem bloqueio de status de estoque e bloqueio de ordem de qualidade

Você pode criar uma ordem de qualidade associada ao estoque com um status de estoque que tenha o parâmetro **Bloqueio de estoque** habilitado. Nesse caso, a ordem de qualidade gerará um registro extra de bloqueio de estoque além do criado pelo status do estoque. Como o bloqueio de estoque da ordem de qualidade terá o parâmetro **Recebimentos esperados** habilitado, isso gera uma transação extra de *Estoque encomendado* que também é bloqueada pelo status do estoque. Essa combinação pode levar a dificuldades na compreensão do significado de transações de estoque geradas, pois ela aparecerá como se a quantidade total bloqueada excedesse a quantidade total disponível. Vamos examinar as transações em um exemplo de um recebimento de 10 peças do item A0001 com uma ordem de qualidade gerada para a peça de exemplo 1. O comportamento também dependerá de a opção **Reservar itens encomendados** estar habilitada na página **Parâmetros de gerenciamento de estoque e depósito**.

>[!NOTE]
>Se você estiver usando o bloqueio de status de estoque e as ordens de qualidade juntas, será altamente recomendável que a opção **Reservar itens encomendados** esteja habilitada.

### <a name="example-with-reserve-ordered-items-enabled"></a>Exemplo com "Reservar itens encomendados" habilitada

Quando a opção **Reservar itens encomendados** estiver habilitada, todas as transações de bloqueio de estoque terão o status *Qtd. reservada* ou *Qtd. encomendada*.

| Referência de transação de estoque | Recebimento | Problema | Quantidade | Site | Depósito | Status do estoque | Localização | Placa de licença | Comentar |
|---|---|---|---|---|---|---|---|---|---|
| Ordem de Compra | Comprado | | 10 Pças. | 2 | 24 | Bloqueio | RECV | receiptLp1 | | 
| Bloqueio de estoque | | Qtd. reservada | -9 Pças. | 2 | 24 | Bloqueio | | | Transação gerada pelo bloqueio do status do estoque |
| Bloqueio de estoque | | Qtd. reservada | -1 Pças. | 2 | 24 | Bloqueio | RECV | receiptLp1 | Transação gerada pelo bloqueio de amostragem de ordem de qualidade |
| Bloqueio de estoque | Encomenda feita | | 1 Pças. | 2 | 24 | Bloqueio | RECV | receiptLp1 | Recebimentos esperados do bloqueio de amostragem de ordem de qualidade |
| Bloqueio de estoque | | Qtd. encomendada | 1 Pças. | 2 | 24 | Bloqueio | | | Transação gerada pelo bloqueio do status do estoque

### <a name="example-with-reserve-ordered-items-disabled"></a>Exemplo com "Reservar itens encomendados" desabilitada

Quando **Reservar itens encomendados** está desabilitada, os recebimentos esperados não podem ser reservados porque seu status é *Encomendado*; portanto, alguns bloqueios ficarão no status *Em ordem*.

| Referência de transação de estoque | Recebimento | Problema | Quantidade | Site | Depósito | Status do Estoque | Localização | Placa de licença | Comentar |
|---|---|---|---|---|---|---|---|---|---|
| Ordem de Compra | Comprado | | 10 Pças. | 2 | 24 | Bloqueio | RECV | receiptLp1 | |
| Bloqueio de estoque | | Qtd. reservada | -9 Pças. | 2 | 24 | Bloqueio | | | Transação gerada pelo bloqueio do status do estoque |
| Bloqueio de estoque | | Qtd. reservada | -1 Pças. | 2 | 24 | Bloqueio | RECV | receiptLp1 | Transação gerada pelo bloqueio de amostragem de ordem de qualidade |
| Bloqueio de estoque | Encomenda feita | | 1 Pças. | 2 | 24 | Bloqueio | RECV | receiptLp1 | Recebimentos esperados do bloqueio de amostragem de ordem de qualidade |
| Bloqueio de estoque | | Em ordem | 1 Pças. | 2 | 24 | Bloqueio | RECV | receiptLp1 | Transação gerada pelo bloqueio do status do estoque

Observe a diferença no status e nas dimensões da transação entre os dois casos. Por esse motivo, é recomendável habilitar a opção **Reservar itens encomendados**.

<!-- KFM: (Enable this section when the feature leaves private preview)

### Disable expected receipts from quality orders that sample blocked inventory feature

To simplify the inventory transactions in the case of quality orders that sample inventory blocked as a consequence of inventory status, the system provides a feature that disables expected receipts from such quality orders. As the expected receipt is in any case immediately blocked by inventory status blocking, there is no reduction of on-hand inventory because of this change.

-->

## <a name="additional-resources"></a>Recursos adicionais

[Criar e manter um bloqueio de estoque](tasks/create-maintain-inventory-blocking.md)

[Processos de gerenciamento de qualidade](quality-management-processes.md)

[Verificar a qualidade de mercadorias](tasks/inspect-quality-goods.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]