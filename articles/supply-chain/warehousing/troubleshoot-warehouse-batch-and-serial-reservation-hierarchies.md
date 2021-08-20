---
title: Solucionar problemas de hierarquias de reserva de números de série e do lote do depósito
description: Este tópico descreve como corrigir problemas comuns que você poderá encontrar ao trabalhar com hierarquias de reserva que usam dimensões de números do lote ou de série.
author: perlynne
ms.date: 3/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 3/12/2021
ms.openlocfilehash: a2b6f76aba22c24c07a2727b2eb8752f6ce763654403d47e34932a21a776dccb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6748634"
---
# <a name="troubleshoot-warehouse-batch-and-serial-reservation-hierarchies"></a>Solucionar problemas de hierarquias de reserva de números de série e do lote do depósito

[!include [banner](../includes/banner.md)]

Este tópico descreve como corrigir problemas comuns que você poderá encontrar ao trabalhar com hierarquias de reserva que usam dimensões de números do lote ou de série.

Para obter mais informações, consulte [Política de reserva de dimensão no nível de depósito flexível](flexible-warehouse-level-dimension-reservation.md).

A hierarquia de reservas de um item dita a necessidade de dimensões de loja que devem ser atendidas para a atribuição de um local a uma ordem de demanda. Essas dimensões podem ser descritas como *dimensões acima do local*, para todas as dimensões que devem ser preenchidas antes que um local seja atribuído, e *dimensões abaixo do local*, para dimensões que podem ser alocadas depois que um local for atribuído à ordem de demanda. Essas hierarquias de reserva também são conhecidas como hierarquias de reserva *acima do número do lote* e *abaixo do número do lote*, ou hierarquias de reserva *acima do número de série* ou *abaixo do número de série*.

O estoque só poderá ser alocado com êxito se não houver intervalos nas dimensões acima do local. Por exemplo, em uma hierarquia de reservas *acima do número do lote*, você espera que as dimensões **Local**, **Depósito** e **número do lote** sejam especificadas na ordem de demanda. Se alguma dessas dimensões estiver ausente, o processo de alocação falhará. Por outro lado, em uma hierarquia de reservas *abaixo do número do lote* ou *abaixo do número de série*, um número do lote ou de série poderá ser especificado na ordem de demanda, mas o processo de alocação exige isso.

## <a name="i-receive-the-following-error-message-to-be-assigned-to-wave-load-lines-must-specify-the-dimensions-above-the-location-to-assign-these-dimensions-reserve-and-recreate-the-load-line"></a>Recebo a seguinte mensagem de erro: "Para ser atribuído ao ciclo, as linhas de carga devem especificar as dimensões acima do local. Para atribuir essas dimensões, reserve e recrie a linha de carga."

### <a name="issue-description"></a>Descrição do problema

Quando você usa um item com uma hierarquia de reservas *acima do número do lote*, o comando **Liberar para o depósito** na página **Bancada do planejamento de carga** não funcionará se você tentar liberar uma carga para uma quantidade parcial. Você recebe essa mensagem de erro e nenhum trabalho é criado para a quantidade parcial.

Contudo, quando usar um item com uma hierarquia de reservas *acima do número do lote*, você poderá liberar uma carga para a quantidade parcial da página **Bancada do planejamento de carga**.

### <a name="issue-cause"></a>Causa do problema

Quando uma dimensão estiver acima da dimensão **Local** na hierarquia de reservas, ela deverá ser especificada antes da liberação para o depósito. Quantidades parciais não podem ser liberadas se uma ou mais dimensões acima de **Local** não forem especificadas.

## <a name="the-auto-reservation-prompt-for-a-batch-number-is-triggered-even-though-there-is-available-inventory"></a>O aviso de reserva automática para um número do lote será disparado mesmo que haja um estoque disponível.

### <a name="issue-description"></a>Descrição do problema

Quando você usa um item com uma hierarquia de reservas *acima do número do lote* em um depósito que não tenha habilitado processos de depósito, e se a reserva automática estiver habilitada, o aviso de reserva automática para um número do lote será mostrado mesmo se apenas um lote estiver disponível para separação.

No entanto, quando você usar o mesmo item em um depósito onde os processos de depósito estiverem habilitados, o prompt de reserva automática não será exibido.

### <a name="issue-cause"></a>Causa do problema

Se uma hierarquia de reserva for definida como um *acima do número do lote* ou *acima do número de série*, a dimensão referenciada (**número do lote** ou **Número de série**) sempre deverá ser especificada em ordens de demanda. Talvez os processos de depósito consigam completar as informações se um único número do lote ou de série estiver disponível. No entanto, como o depósito não está habilitado para processos de depósito, o usuário sempre deverá especificar todas as dimensões acima do **Local**.

## <a name="slotting-templates-that-have-the-consider-on-hand-slot-criterion-dont-consider-current-on-hand-inventory-for-batch-enabled-items"></a>Os modelos de slots com o critério de slot Considerar disponível não consideram o estoque disponível atual para itens habilitados para lotes.

Para obter mais informações, consulte [Slots de depósito](warehouse-slotting.md).

### <a name="issue-description"></a>Descrição do problema

Os modelos de slots com o critério de slot *Considerar disponível* não consideram o estoque disponível atual para itens *acima do número do lote*. Eles só o considerarão se o número do lote for especificado na linha da ordem de venda.

No entanto, quando você usa itens *abaixo do número do lote*, o estoque disponível atual é considerado esperado.

### <a name="issue-cause"></a>Causa do problema

O cabeçalho do modelo de slot pode ser definido para a estratégia de demanda *Encomendado*, *Reservado* ou *Liberado*. Para a estratégia de demanda *Encomendado*, os mesmos requisitos de hierarquia de reservas se aplicam para reserva ou liberação para processos de depósito. Portanto, para os itens com hierarquias de reservas *acima do número do lote* e *abaixo do número de série*, o número do lote ou de série deverá ser especificado na ordem de demanda (venda ou transferência). Como alternativa, a estratégia de demanda *Reservado* poderá ser usada para selecionar o número do lote ou de série antes que a demanda de slots de depósito seja gerada.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
