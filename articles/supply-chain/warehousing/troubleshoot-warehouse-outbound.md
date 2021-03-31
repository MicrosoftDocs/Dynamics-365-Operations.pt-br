---
title: Resolver problemas de operações de depósito de saída
description: Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com operações de depósito de saída no Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 1344a1c16bf72b31f7aaf18aaeb6e08c7bc9d87e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5223257"
---
# <a name="troubleshoot-outbound-warehouse-operations"></a>Resolver problemas de operações de depósito de saída

[!include [banner](../includes/banner.md)]

Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com operações de depósito de saída no Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-sales-order-could-not-be-released"></a>Recebo a seguinte mensagem de erro: "Não foi possível liberar a ordem de venda."

### <a name="issue-description"></a>Descrição do problema

Esse problema pode ocorrer por vários motivos. Por exemplo, a ordem está em espera de gerenciamento de crédito e nenhuma remessa pode ser criada até que um endereço postal válido seja inserido para todas as linhas de vendas associadas a uma ordem de venda. Como alternativa, há um bloqueio de ordem que deve ser resolvido antes que a ordem possa ser liberada para o depósito. Esse bloqueio pode ser específico da ordem ou pode ocorrer na conta do cliente.

### <a name="issue-resolution"></a>Resolução do problema

Adicione ou atualize o endereço na ordem de venda e nas linhas de ordem e, depois, libere a ordem para o depósito. As ordens podem ser liberadas para o depósito somente se elas tiverem um endereço de entrega válido (de acordo com a configuração do formato de endereço no módulo **Administração da organização**).

Investigue o bloqueio da ordem e resolva os problemas. Depois, remova o bloqueio da ordem ou do cliente e libere a ordem no depósito.

## <a name="i-receive-the-following-message-the-shipment-for-load-1-has-been-confirmed-however-no-lines-are-posted"></a>Recebo a seguinte mensagem: "A remessa para carga 1% foi confirmada." Contudo, nenhuma linha é lançada.

### <a name="issue-description"></a>Descrição do problema

Uma remessa em uma carga foi confirmada, mas nenhum lançamento adicional ocorreu.

### <a name="issue-resolution"></a>Resolução do problema

A confirmação da remessa não afeta o lançamento. Ela apenas atualiza a remessa e o status da carga. O lançamento deve ocorrer em um processo separado.

## <a name="i-receive-the-following-error-message-direct-delivery-is-not-able-to-process-for-warehouse-1-as-it-has-warehouse-management-enabled-please-specify-another-warehouse-that-is-not-enabled-for-warehouse-management"></a>Recebo a seguinte mensagem de erro: "A entrega direta não é capaz de processar para o depósito 1% porque tem o gerenciamento do depósito habilitado. Especifique outro depósito que não esteja habilitado para gerenciamento de depósito."

### <a name="issue-description"></a>Descrição do problema

Um item é adicionado a uma linha de vendas para entrega direta de um depósito habilitado para gerenciamento de depósito (WMS). Você recebe essa mensagem de erro quando a linha de vendas é atualizada. 

### <a name="issue-resolution"></a>Resolução do problema

A Microsoft avaliou esse problema e determinou que é uma limitação de recurso. Atualmente, o WMS não oferece suporte para entrega direta. Portanto, para usar a entrega direta, você deve selecionar um item e depósito que não é WMS.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]