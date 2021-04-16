---
title: Exibir encargos para um item fabricado
description: Os custos constantes de um item fabricado refletem os tempos de preparação da operação e os componentes com uma quantidade constante ou um valor de sucata constante.
author: AndersGirke
ms.date: 04/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.custom: 274483
ms.assetid: 6f5b851b-c5a7-43ef-b380-0d316667c1ef
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: d65e3c4220c05d143d57413749ef805fd58dcf08
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813258"
---
# <a name="display-charges-for-a-manufactured-item"></a>Exibir encargos para um item fabricado

[!include [banner](../includes/banner.md)]

Os custos constantes de um item fabricado refletem os tempos de preparação da operação e os componentes com uma quantidade constante ou um valor de sucata constante.

O valor calculado dos encargos de um item pode ser exibido com os custos unitários do item. Entretanto, os encargos são exibidos algumas vezes em campos separados, e não estão incluídos nos custos unitários do item. Quando os encargos aparecem como campos separados, um campo mostra o valor total dos encargos e outro campo exibe o tamanho do lote de custos usado para amortizar o valor. A página Preço de item, por exemplo, exibe os encargos como dois campos separados. Entretanto, a página Concluído exibe o custo total do item por unidade e os custos amortizados são incluídos nos custos unitários.

Os encargos de um item fabricado são sempre incluídos no custo unitário do item para fins de custo padrão. Opcionalmente, eles podem ser incluídos para custos planejados. Uma política na versão de avaliação de custo impõe a inclusão de encargos no custo de um item fabricado. Ao ativar um registro de custo de um item, você atualiza os encargos das informações de custo base do item, exibidas na página Preço do item. Os encargos são exibidos como dois campos separados e não estão incluídos no custo unitário do item. Cada ativação atualiza as informações de custo base do item, mesmo se a ativação refletir sites diferentes. Portanto, considere as informações de custo base como informações de referência.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]