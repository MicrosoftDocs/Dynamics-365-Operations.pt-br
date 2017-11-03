---
title: "Movimento de estoque com trabalho associado no Gerenciamento de depósito"
description: "Este tópico descreve como configurar e aplicar a confirmação de separação de peças de um dispositivo móvel."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 463e438418c4bc1b38fd1bde8251d1383cb44a13
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="movement-of-inventory-with-associated-work-in-warehouse-management"></a>Movimento de estoque com trabalho associado no Gerenciamento de depósito

[!include[banner](../includes/banner.md)]

Ao usar o movimento de estoque, você pode decidir quais funcionários do depósito têm permissão para mover o estoque reservado. Isso fornece flexibilidade em depósitos regulamentados em que você pode decidir não permitir que um trabalhador escolha um novo local de separação para o trabalho de separação já criado. Também permite que o gerente de depósito controle quais recursos alguns trabalhadores menos experientes devem ter.

A flexibilidade para gerenciar operações diárias de trabalhadores de depósito pode ser útil em cenários como estes:

## <a name="scenario-1"></a>Cenário 1
Uma empresa possui uma área de recebimento relativamente pequena, e está congestionada devido a paletes e caixas que aguardam alocação. Uma grande remessa é esperada no dia atual, o auxiliar de recebimento decide liberar a área de remessa movendo alguns paletes para uma área de preparo de entrada secundária.

## <a name="scenario-2"></a>Cenário 2
Um trabalhador de depósito experiente percebe uma oportunidade de consolidar os itens em local único em vez de ser dividido por 3 locais próximos com pouca quantidade em cada um. O trabalhador deseja consolidar a quantidade movendo itens de cada um desses locais para o mesmo local e com a mesma placa de licença.

## <a name="scenario-3"></a>Cenário 3
Um palete está aguardando remessa em um local de preparo, como STAGE01, que é próximo de BAYDOOR01. Entretanto, devido a uma mudança de planos, o caminhão está programada para chegar em BAYDOOR04. O funcionário de remessa está ciente disso e precisa garantir que o caminhão não tenha que aguardar para ser carregado a partir do STAGE01. O funcionário de remessa decide mover os itens dessa remessa de STAGE01 para STAGE04, que é mais próximo do novo destino.

### <a name="current-limitations"></a>Limitações atuais

As reservas de trabalho que você pode mover são limitadas à Ordem de venda, à Emissão de ordem de transferência, ao Recebimento da ordem de transferência, à Ordem de compra e ao Trabalho de reabastecimento.

Mover itens se restringe a evitar a divisão de linhas de trabalho. Isso significa que se você tem uma linha de trabalho de 100 peças de item A, localização Loc1, não será possível mover somente 30 peças de item A para outro local. Isso levaria a uma divisão da linha de trabalho existente em 30 e 70, pois agora as localizações são diferentes.

Para cenários de preparo em que você move a placa de licença da mercadoria ou em que você move a placa de licença para a mercadoria são definidas como LP de destino para uma ordem de trabalho, somente é permitido o movimento do LP inteiro, de forma a não dividir o LP de destino.
Somente o movimento ad hoc tem suporte atualmente. Isso significa que não será possível mover estoque reservado por modelo de itens de menu do dispositivo móvel.

### <a name="set-up-permission-to-move-reserved-inventory-for-individual-workers"></a>Configurar permissão para mover o estoque reservado para trabalhadores individuais

Para o trabalhador que terá permissão para mover o estoque reservado, marque a caixa de seleção **Permitir movimento de estoque com trabalho associado** em **Gerenciamento de depósito** > **Configuração** > **Trabalhador**.  

### <a name="backported"></a>Atualização retroativa

Este recurso também foi atualizado de forma retroativa para Microsoft Dynamics AX 2012 R3 e estará disponível como parte do CU12.
Ele também pode ser baixado individualmente com o número de KB 3192548. 


