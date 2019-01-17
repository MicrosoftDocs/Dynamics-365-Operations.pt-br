---
title: Gerenciamento de estoque de loja
description: "Este artigo descreve os tipos de documentos que você pode usar para gerenciar inventário."
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 72f6f5e2645240ee3ddd31657176f27cb7db404f
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---

# <a name="store-inventory-management"></a>Gerenciamento de estoque de loja

[!include [banner](includes/banner.md)]

Este artigo descreve os tipos de documentos que você pode usar para gerenciar inventário.

Você pode usar os tipos de documentos a seguir para gerenciar o estoque da sua organização.

## <a name="purchase-orders"></a>Ordens de compra

As ordens de compra são criadas na matriz. Se um armazém de varejo estiver incluído no cabeçalho da ordem de compra, a ordem poderá ser recebida na loja usando o Modern POS (MPOS) ou PDV em Nuvem no Microsoft Dynamics 365 for Retail. Após a especificação das quantidades recebidas na loja, é possível salvá-las localmente para a modificação adicional. Como alternativa, as quantidades podem ser confirmadas e enviadas para a matriz. Na sede, as quantidades recebidas na loja são exibidas no Dynamics 365 for Retail, no campo **Receber agora** na ordem de compra.

## <a name="transfer-orders"></a>Ordens de transferência

Uma ordem de transferência pode especificar que uma loja específica é um local de onde os itens podem ser enviados. Nesse caso, a ordem de transferência aparece na loja como solicitação de separação no MPOS ou PDV em Nuvem. Após a separação das quantidades solicitadas, elas são confirmadas e enviadas à matriz. Na matriz, as quantidades recebidas e separadas na loja são exibidas no Dynamics 365 for Retail, no campo **Remeter agora** da ordem de transferência. Uma ordem de transferência pode especificar que uma loja específica é um local para onde os itens podem ser enviados. Nesse caso, a ordem de transferência aparece na loja como solicitação de recebimento no MPOS ou PDV em Nuvem. Após a especificação das quantidades recebidas na loja, é possível salvá-las localmente para a modificação adicional. Como alternativa, as quantidades podem ser confirmadas e enviadas para a matriz. Na sede, as quantidades recebidas na loja são exibidas no Dynamics 365 for Retail, no campo **Receber agora** na ordem de transferência.

## <a name="stock-counts"></a>Contagens de estoque

Contagens de estoque podem ser agendadas ou não agendadas. As contagens de estoque agendadas são iniciadas na matriz, que especifica os itens que devem ser contados. A matriz cria um documento de contagem que pode ser recebido na loja, onde as quantidades disponíveis em estoque reais são inseridas no MPOS ou PDV em Nuvem. Contagens de estoque não agendadas são iniciadas em uma loja, e as quantidades disponíveis em estoque reais são atualizadas no MPOS ou PDV em Nuvem. Diferente das contagens de estoque agendadas, as contagens de estoque não agendadas não têm uma lista predefinida de itens. Quando uma contagem de estoque de qualquer tipo é concluída, ela é confirmada e enviada para a matriz. Na matriz, a contagem é validada e lançada.

## <a name="inventory-lookup"></a>Pesquisa de estoque

A quantidade de produtos atual disponível para várias lojas e depósitos pode ser exibida na página de pesquisa Estoque. Além da quantidade atual disponível, as quantidades futuras disponíveis para promessa (ATP) podem ser exibidas para cada loja individual. Para fazê-lo, selecione a loja em que deseja exibir o ATP e clique em **Mostrar disponibilidade da loja**.

