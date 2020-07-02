---
title: Disponibilidade de estoque em gravação dupla
description: Este tópico fornece informações sobre como verificar a disponibilidade de estoque em gravação dupla.
author: yijialuan
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 227a2062a7985a787f8278c196f7df2fb6f31691
ms.sourcegitcommit: cf709f1421a0bf66ecea493088ecb4eb08004187
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2020
ms.locfileid: "3443863"
---
# <a name="inventory-availability-in-dual-write"></a>Disponibilidade de estoque em gravação dupla

[!include [banner](../../includes/banner.md)]

Usando a disponibilidade de estoque, você pode verificar seu estoque antes de adicionar um produto à página **Cotações**, **Ordens** ou **Faturas** no Microsoft Dynamics 365 Sales. Por exemplo, você verifica o estoque e determina uma data de atendimento como uma tarefa fundamental no processo de [pagamento à vista](dual-write-prospect-to-cash.md).

Se não tiver estoque suficiente, você poderá estimar uma data de entrega com base em recebimentos e saídas de estoque projetado. Você também pode verificar as informações de disponível para promessa (ATP), em que é possível encontrar a quantidade ATP no limite de tempo predefinido.

## <a name="on-hand-inventory"></a>Estoque Disponível

No Dynamics 365 Sales, um novo botão **Estoque disponível** foi adicionado ao cabeçalho das páginas **Cotações**, **Ordens** e **Faturas**. Quando você seleciona esse botão, uma caixa de diálogo é exibida e você pode especificar a empresa e o produto para o qual deseja verificar o estoque disponível. Essa caixa de diálogo mostra as mesmas informações do que o [Estoque disponível](../../../../supply-chain/inventory/tasks/check-availability-stock.md).

A caixa de diálogo retorna as informações de estoque do Dynamics 365 Supply Chain Management. Essas informações incluem as seguintes quantidades:

- Quantidade disponível
- Quantidade disponível reservada
- Quantidade disponível
- Quantidade encomendada
- Quantidade na ordem
- Quantidade encomendada reservada
- Quantidade disponível total

## <a name="atp-information"></a>Informações sobre ATP

No Sales, um novo botão **Informações sobre ATP** foi adicionado aos itens de linha nas páginas **Cotações**, **Ordens** e **Faturas**. Quando você selecione essa botão, uma caixa de diálogo é exibida e você pode especificar empresa, produto, site do estoque, depósito de estoque e quantidade da ordem. Essa caixa de diálogo tem as mesmas configurações descritas em [Promessa de ordem](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).

A caixa de diálogo retorna as informações sobre ATP do Supply Chain Management. Essas informações incluem as seguintes quantidades:

- Quantidade ATP
- Quantidade recebida
- Quantidade emitida
- Quantidade disponível
