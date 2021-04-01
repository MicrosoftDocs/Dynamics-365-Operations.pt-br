---
title: Solucionar problemas de criação de carga e remessas
description: Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com a criação de cargas e remessas no Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: c7dc9cc9de4d5089d497c36759931669ee2e9e55
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5259497"
---
# <a name="troubleshoot-load-building-and-shipments"></a>Solucionar problemas de criação de carga e remessas

[!include [banner](../includes/banner.md)]

Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com a criação de cargas e remessas no Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-you-cant-create-a-load-line-for-this-order-line-because-it-contains-inventory-dimensions-that-are-invalid"></a>Recebo a seguinte mensagem de erro: "Não é possível criar uma linha de carga para esta linha da ordem porque ela contém dimensões de estoque que são inválidas..."

### <a name="issue-description"></a>Descrição do problema

Você recebe a seguinte mensagem de erro ao tentar liberar uma ordem de devolução para o depósito:

> Não é possível criar uma linha de carga para esta linha da ordem porque ela contém dimensões de estoque que são inválidas. Você não pode fazer referência às dimensões de estoque localizadas abaixo da dimensão do local na hierarquia de reserva. Remova as dimensões inválidas da linha da ordem.

### <a name="issue-resolution"></a>Resolução do problema

Infelizmente, o produto não oferece suporte ao processamento de carga para um processo de devolução de venda. Portanto, você não pode liberar a ordem de venda de devolução para o depósito.

Em transações de ordens de venda, você não pode fazer referência a dimensões de estoque localizadas abaixo da dimensão do **local** na hierarquia de reserva. A resolução consiste em remover as dimensões inválidas da linha da ordem.

## <a name="i-receive-the-following-error-message-one-of-the-lines-is-already-on-a-load-unable-to-release-to-warehouse"></a>Recebo a seguinte mensagem de erro: "Uma das linhas já está carregada. Não foi possível liberar para o depósito."

### <a name="issue-description"></a>Descrição do problema

Se você criar cargas manualmente ou configurar o processo de forma que as cargas já sejam criadas antes que a entrada da linha da ordem de vendas ocorra, a suposição é que a liberação subsequente será feita manualmente e que a rota e a classificação da carga serão usadas.

Em outro cenário possível, você está tentando fazer uma liberação automática para o depósito, mas houve falha no processo de ciclo durante a criação do trabalho. Portanto, uma remessa ou carga aberta ainda será criada. Essa remessa ou carga aberta bloqueia as tentativas subsequentes de liberar automaticamente a ordem até que você exclua a remessa ou carga aberta ou reprocesse manualmente o ciclo.

### <a name="issue-resolution"></a>Resolução do problema

É possível liberar na página de ordem de venda ou a liberação automática pode ser feita na página de liberação de ordem de venda, somente se não houver carga antes da liberação para o depósito. A carga será criada automaticamente após o processamento da onda.

## <a name="i-receive-the-following-error-message-the-delivery-note-correction-cant-be-processed-the-delivery-note-only-contains-items-that-are-subject-to-warehouse-management-processes-as-these-are-not-supported-by-delivery-note-correction"></a>Recebo a seguinte mensagem de erro: "A correção da nota de entrega não pode ser processada. A nota de entrega contém apenas itens que estão sujeitos a processos de gerenciamento de depósito, uma vez que eles não são compatíveis com a correção de nota de entrega."

### <a name="issue-description"></a>Descrição do problema

Depois de postar uma nota de entrega, você não poderá cancelá-la, porque o botão **Cancelar** não estará disponível. Você também não poderá corrigir a nota de entrega. Se você tentar, receberá esta mensagem de erro.

### <a name="issue-resolution"></a>Resolução do problema

Para corrigir guias de remessa lançadas para itens habilitados para gerenciamento avançado de depósito (WMS), você deve fazer o lançamento da carga, não diretamente usando a ordem.

## <a name="how-can-i-create-work-from-outbound-loads-instead-of-waves"></a>Como posso criar trabalho usando cargas de saída em vez de ciclos?

### <a name="issue-description"></a>Descrição do problema

Aqui está uma maneira de reproduzir esse problema.

1. Crie uma carga de saída usando uma ordem de venda ou ordem de transferência.
2. Libere a carga para o depósito.
3. Observe que nenhum trabalho de separação foi gerado ainda.

### <a name="issue-resolution"></a>Resolução do problema

Se o trabalho deve ser gerado imediatamente quando a carga é liberada, você deve configurar o modelo de ciclo adequadamente. No modelo de ciclo, defina as seguintes opções como *Sim*:

- Automatizar criação da onda
- Processar onda na liberação para o depósito
- Automatizar liberação da onda

## <a name="i-cant-re-release-a-partially-shipped-load"></a>Não consigo liberar de novo uma carga parcialmente enviada.

### <a name="issue-description"></a>Descrição do problema

Não é possível liberar uma carga parcialmente enviada para o depósito. Quando você realiza a liberação para o depósito, uma mensagem "Operação concluída" aparece, mas nada acontece e nenhum trabalho é criado para a quantidade restante. Esse problema ocorre quando você usa a funcionalidade de carregamento de transporte e há uma reserva incompleta.

### <a name="issue-resolution"></a>Resolução do problema

O [problema do KB 470069](https://fix.lcs.dynamics.com/Issue/Details?kb=4574490&bugId=470069&dbType=3&qc=84ce1e09d7032d8b8ef86f5a0c68b86badf3dfaf29686c5ebbe97c53c0957b5f) ("Cargas parcialmente enviadas podem ser colocadas em ciclo e processadas de novo") foi corrigido na [versão 10.0.15](../get-started/whats-new-scm-10-0-15.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]