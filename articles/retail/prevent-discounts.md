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
ms.openlocfilehash: c9d3e7af95dffddfddc34059d93a2a5a350d08e5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550735"
---
# <a name="options-for-preventing-discounts-for-retail-products"></a>Opções para impedir descontos em produtos de varejo

[!include [banner](includes/banner.md)]

Há vários motivos que levam varejistas a impedir que alguns produtos tenham descontos, seja em uma promoção ou durante a venda no PDV.

As seguintes opções, que podem ser encontradas na guia **Varejo** de produtos liberados, permitirão que os produtos sejam configurados para evitar todos os descontos ou os descontos manuais. As configurações também podem ser especificadas no nível da categoria a partir da hierarquia da categoria de varejo.

- **Impedir todos os descontos** – selecione esta opção para impedir que todos os tipos de descontos sejam aplicados a este produto. Isso inclui promoções, como compra combinada, descontos de quantidade e de limite, bem como os descontos manuais de linha e de transação que são aplicados durante uma venda por um usuário do PDV.
- **Impedir descontos manuais** – selecione esta opção para evitar apenas os descontos de linha manual ou de transação que são aplicados durante uma venda por um usuário do PDV. Produtos com essa opção selecionada ainda estão qualificados para promoções, como descontos de compra combinada e descontos de quantidade e de limite.

> [!NOTE]
> Essas configurações não restringem a operação de substituição de preço, pois elas definem o preço base e não são tratadas como um desconto.

[![campo impedir descontos](./media/prevent-discounts.png)](./media/prevent-discounts.png)
