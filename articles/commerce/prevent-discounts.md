---
title: Opções para impedir descontos em produtos de varejo
description: Há vários motivos que levam varejistas a impedir que alguns produtos tenham descontos, seja em uma promoção ou durante a venda no PDV.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 85183
ms.assetid: e8c5a24f-7edd-4fd6-af80-5e0ac9f03127
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 6a683ffce487dc4388711ad160c2e8dc55a690dd
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057455"
---
# <a name="options-for-preventing-discounts-for-retail-products"></a>Opções para impedir descontos em produtos de varejo

[!include [banner](includes/banner.md)]

Há vários motivos que levam varejistas a impedir que alguns produtos tenham descontos, seja em uma promoção ou durante a venda no PDV.

As seguintes opções, que podem ser encontradas na guia **Commerce** de produtos liberados, permitirão que os produtos sejam configurados para evitar todos os descontos ou os descontos manuais. As configurações também podem ser especificadas no nível da categoria a partir da hierarquia de categoria.

- **Impedir todos os descontos** – selecione esta opção para impedir que todos os tipos de descontos sejam aplicados a este produto. Isso inclui promoções, como compra combinada, descontos de quantidade e de limite, bem como os descontos manuais de linha e de transação que são aplicados durante uma venda por um usuário do PDV.
- **Impedir descontos manuais** – selecione esta opção para evitar apenas os descontos de linha manual ou de transação que são aplicados durante uma venda por um usuário do PDV. Produtos com essa opção selecionada ainda estão qualificados para promoções, como descontos de compra combinada e descontos de quantidade e de limite.

> [!NOTE]
> Essas configurações não restringem a operação de substituição de preço, pois elas definem o preço base e não são tratadas como um desconto.

[![Campo Impedir descontos](./media/prevent-discounts.png)](./media/prevent-discounts.png)
