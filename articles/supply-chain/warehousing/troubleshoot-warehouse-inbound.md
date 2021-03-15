---
title: Resolver problemas de operações de depósito de entrada
description: Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com operações de depósito de entrada no Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 71f590ec01b757de298bd2692fdbdb0324843376
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970230"
---
# <a name="troubleshoot-inbound-warehouse-operations"></a>Resolver problemas de operações de depósito de entrada

[!include [banner](../includes/banner.md)]

Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com operações de depósito de entrada no Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-receive-the-following-error-message-quality-order-1-has-been-generated-cluster-profile-could-not-be-found-please-check-your-configuration"></a>Recebo a seguinte mensagem de erro: "A ordem de qualidade %1 foi gerada. Não foi possível localizar o perfil do cluster. Verifique a sua configuração."

### <a name="issue-description"></a>Descrição do problema

Essa mensagem de erro está relacionada a um processo de recebimento em que o gerenciamento de qualidade (QMS) está ativado. Dependendo das configurações de seu ambiente, detalhes adicionais sobre a transação que está gerando a mensagem de erro podem ajudar a corrigir o problema.

### <a name="issue-resolution"></a>Resolução do problema

Primeiro, revise a configuração de [separação de cluster](set-up-cluster-picking.md) e certifique-se de que seus perfis de cluster estejam configurados corretamente. Você não pode usar um item de menu de dispositivo móvel para seleção de cluster, a menos que os perfis de cluster sejam configurados. Dependendo do seu ambiente, você também pode ter que revisar outras configurações relacionadas.

## <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-except-credit"></a>O recebimento de placas de licença mistas não funciona para nenhum código de disposição, exceto Crédito.

### <a name="issue-description"></a>Descrição do problema

Quando o campo **Ação** para um código de disposição é definido como *Crédito* ou *Sucata*, você pode usar somente o item de menu [Recebimento de placa de licença mista](mixed-license-plate-receiving.md) para processar itens devolvidos.

### <a name="issue-resolution"></a>Resolução do problema

A Microsoft avaliou esse problema e determinou que é uma limitação de recurso. Atualmente, somente [códigos de disposição](../service-management/set-up-disposition-codes.md) em que o campo **Ação** é definido como *Crédito* ou *Sucata* são compatíveis para recebimento de placa de licença mista.

## <a name="when-i-run-the-update-product-receipts-periodic-task-unconfirmed-purchase-orders-are-confirmed"></a>Quando executo a tarefa periódica Atualizar recebimentos de produtos, as ordens de compra não confirmadas são confirmadas.

### <a name="issue-description"></a>Descrição do problema

Depois de executar a tarefa periódica *Atualizar recebimentos de produtos*, o sistema confirma automaticamente as ordens de compra não confirmadas com status de transação de estoque *Registrado*.

### <a name="issue-resolution"></a>Resolução do problema

Um novo recurso de processamento de cargas de entrada, *Recebimento a mais de quantidade de carga*, corrige esse problema. Para ativar esse recurso, vá para [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative os seguintes recursos (na ordem em que estão listados):

1. Associar transações de estoque da ordem de compra com carga
1. Recebimento a mais de quantidade de carga

Para obter mais informações, consulte [Lançar quantidades de produtos registrados nas ordens de compra](inbound-load-handling.md#post-registered-quantities).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]