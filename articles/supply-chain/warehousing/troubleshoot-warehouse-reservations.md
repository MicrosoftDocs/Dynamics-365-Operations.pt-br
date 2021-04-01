---
title: Solucionar problemas de reservas no gerenciamento de depósito
description: Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com reservas de depósito no Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a9a5d20732a802fc58c392853af8334bbc07de73
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5248706"
---
# <a name="troubleshoot-reservations-in-warehouse-management"></a>Solucionar problemas de reservas no gerenciamento de depósito

[!include [banner](../includes/banner.md)]

Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com reservas de depósito no Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations"></a>Recebo a seguinte mensagem de erro: "As reservas não podem ser removidas porque há um trabalho criado com base nas reservas."

### <a name="issue-description"></a>Descrição do problema

Não é possível cancelar a reserva de estoque em uma linha de vendas, porque há trabalho aberto em relação à linha.

### <a name="issue-resolution"></a>Resolução do problema

Investigue se existe trabalho de grupo de embalagem aberto para mudar o item de uma estação de embalagem para outro local (como *Baydoor*). Revise os registros nas páginas **Log de histórico de criação de trabalho** e **Detalhes do trabalho** para determinar o que está reservando fisicamente o estoque e, depois, conclua ou exclua o trabalho para liberar a reserva.

## <a name="i-receive-the-following-error-message-inventory-quantity--1-could-not-be-updated-due-to-insufficient-inventory-transactions-for-item-2"></a>Recebo a seguinte mensagem de erro: "A quantidade em estoque -%1 não pôde ser atualizada em razão de transações de estoque insuficientes para o item %2...."

### <a name="issue-description"></a>Descrição do problema

Esse problema pode ocorrer se o sistema não puder atualizar uma quantidade de estoque porque não há transações de estoque suficientes com as dimensões especificadas. Aqui está o texto completo da mensagem de erro completa:

> A quantidade de estoque -%1 não pôde ser atualizada em razão de transações de estoque insuficientes para o item %2 com dimensões de Tamanho = %3, Cor = %4, Adições = %5, Local = %6, Depósito = %7, Local = %8, Status do estoque = Disponível, Placa de licença = %9, Número do lote = %10 para a ID de referência %11 na ID de lote %12.

### <a name="issue-resolution"></a>Resolução do problema

Certifique-se de que nenhuma transação de estoque esteja reservando fisicamente a quantidade. Por exemplo, essas transações podem abrir ordens de qualidade, registros de bloqueio de estoque ou ordens de saída.

## <a name="i-receive-the-following-error-message-physical-on-handcannot-be-reserved-because-only-000-are-available-in-the-inventory"></a>Recebo a seguinte mensagem de erro: "Físico disponível... não pode ser reservado porque apenas 0,00 estão disponíveis no estoque."

### <a name="issue-description"></a>Descrição do problema

Esse problema pode ocorrer se o sistema não puder atualizar uma quantidade de estoque porque não há transações de estoque suficientes com as dimensões especificadas. Aqui está o texto completo da mensagem de erro completa:

> Físico disponível Local = %1, Depósito = %2, Status do estoque = Disponível, Nº do lote = %3, Proprietário = %4: %5 não pode ser reservado porque somente 0,00 está disponível no estoque.

### <a name="issue-resolution"></a>Resolução do problema

Esse problema é provavelmente causado por um trabalho aberto. Conclua a obra ou receba sem criação de trabalho. Certifique-se de que nenhuma transação de estoque esteja reservando fisicamente a quantidade. Por exemplo, essas transações podem abrir ordens de qualidade, registros de bloqueio de estoque ou ordens de saída.

## <a name="i-receive-the-following-error-message-to-be-assigned-to-wave-load-lines-must-specify-the-dimensions-above-the-location-to-assign-these-dimensions-reserve-and-recreate-the-load-line"></a>Recebo a seguinte mensagem de erro: "Para ser atribuído ao ciclo, as linhas de carga devem especificar as dimensões acima do local. Para atribuir essas dimensões, reserve e recrie a linha de carga."

### <a name="issue-description"></a>Descrição do problema

Quando você usa um item que tem uma hierarquia de reserva de "lote acima" (com a dimensão **Nº do lote** posicionada *acima* da dimensão **Local**), o comando **Liberar para o depósito** na página **Bancada do planejamento de carga** para uma quantidade parcial não funciona. Você recebe essa mensagem de erro e nenhum trabalho é criado para a quantidade parcial.

Contudo, se você usar um item que tem uma hierarquia de reserva de "lote abaixo" (com a dimensão **Nº do lote** posicionada *abaixo* da dimensão **Local**), você pode liberar uma carga da página **Bancada do planejamento de carga** para uma quantidade parcial.

### <a name="issue-resolution"></a>Resolução do problema

Esse comportamento é por design. Se você colocar uma dimensão acima da dimensão **Local** na hierarquia de reserva, ela deve ser especificada antes da liberação para o depósito. A Microsoft avaliou esse problema e determinou que é uma limitação do recurso durante as liberações para o depósito da bancada de planejamento de carga. Quantidades parciais não podem ser liberadas se uma ou mais dimensões acima de **Local** não forem especificadas.

Para obter mais informações, consulte [Política de reserva de dimensão no nível de depósito flexível](flexible-warehouse-level-dimension-reservation.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]