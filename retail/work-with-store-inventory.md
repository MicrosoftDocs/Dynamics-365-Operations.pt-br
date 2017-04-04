---
title: Gerenciar estoque de armazenamento
description: "Este artigo descreve os tipos de documentos que você pode usar para gerenciar o estoque."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: fbe9945799f1e65ed6ad624a3df270fa4eb72b88
ms.lasthandoff: 03/31/2017


---

# <a name="manage-store-inventory"></a>Gerenciar estoque de armazenamento

Este artigo descreve os tipos de documentos que você pode usar para gerenciar o estoque.

Você pode usar os tipos de documentos a seguir para gerenciar o estoque da sua organização.

## <a name="purchase-orders"></a>Ordens de compra
As ordens de compra são criadas na matriz. Se um depósito de varejo é incluído no cabeçalho de compra, a ordem pode ser armazenado no armazenamento usando o retail moderno (MPOS) ou a retail do nuvem no Microsoft Dynamics 365 para operações de varejo. Após a especificação das quantidades recebidas na loja, é possível salvá-las localmente para a modificação adicional. Como alternativa, as quantidades podem ser confirmadas e enviadas para a matriz. Na matriz, que as quantidades foram recebidas na loja são exibidas em dynamics 365 para operações, em ** receber agora ** campos na ordem de compra.

## <a name="transfer-orders"></a>Ordens de transferência
Uma ordem de transferência pode especificar que uma loja específica é um local de onde os itens podem ser enviados. Nesse caso, a ordem de transferência é exibido no armazenamento de uma solicitação de separação em MPOS ou em do nuvem POS. Após a separação das quantidades solicitadas, elas são confirmadas e enviadas à matriz. Na matriz, que as quantidades foram separadas na loja são exibidas em dynamics 365 para operações, em ** remeter agora ** campos na ordem de transferência. Uma ordem de transferência pode especificar que uma loja específica é um local para onde os itens podem ser enviados. Nesse caso, a ordem de transferência é exibido no armazenamento de uma solicitação de remessa em MPOS ou em do nuvem POS. Após a especificação das quantidades recebidas na loja, é possível salvá-las localmente para a modificação adicional. Como alternativa, as quantidades podem ser confirmadas e enviadas para a matriz. Na matriz, que as quantidades foram recebidas na loja são exibidas em dynamics 365 para operações, em ** receber agora ** campos na ordem de transferência.

## <a name="stock-counts"></a>Contagens de estoque
Contagens de estoque podem ser agendadas ou não agendadas. As contagens de estoque agendadas são iniciadas na matriz, que especifica os itens que devem ser contados. A matriz cria um documento de contagem que pode ser retirada na loja, onde as quantidades reais disponíveis em estoque são inseridas em MPOS ou se nublam POS. Contagens de estoque não programadas são iniciadas em um armazenamento, as quantidades disponível real de estoque são atualizadas em MPOS ou nublam-se POS. Diferente das contagens de estoque agendadas, as contagens de estoque não agendadas não têm uma lista predefinida de itens. Quando uma contagem de estoque de qualquer tipo é concluída, ela é confirmada e enviada para a matriz. Na matriz, a contagem é validada e lançada.




