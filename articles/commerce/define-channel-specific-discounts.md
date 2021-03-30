---
title: Definir descontos específicos do canal
description: Os fornecedores geralmente definem descontos diferentes em canais diferentes. Este tópico examina os conceitos que você precisa saber para criar um desconto para um canal específico.
author: scott-tucker
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailAffiliationPriceGroup, RetailCatalogPriceGroup, RetailChannelPriceGroup, RetailDiscountPriceGroup, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailStoreItemPriceList, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.custom: 16401
ms.assetid: d807fd51-86aa-47a0-8e00-6c5ddd21ff6b
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 36b2d8f96f8545f9fa792e42c639b03e1e14e8ee
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213737"
---
# <a name="define-channel-specific-discounts"></a>Definir descontos específicos do canal

[!include [banner](includes/banner.md)]

Este tópico examina os conceitos que você precisa saber para criar um desconto para um canal específico.

## <a name="channel-specific-discounts"></a>Descontos específicos do canal

Os fornecedores geralmente oferecem descontos diferentes em canais diferentes. Isso pode ser feito para lidar com as condições dos mercados locais ou com os varejistas concorrentes.

O Commerce usa grupos de preços para definir descontos específicos de canal. Grupos de preços podem ser atribuídos a uma ou mais das seguintes entidades: canais, catálogos, afiliações e programas de fidelidade. Este artigo aborda canais, mas os mesmos conceitos se aplicam a descontos de catálogo, descontos de afiliações e descontos de fidelidade.

## <a name="price-groups"></a>Grupos de preços

[![Grupos de preços](./media/price-groups-1024x608.png)](./media/price-groups.png)

O diagrama acima ilustra a relação entre entidades que podem estar em uma transação (canal, catálogo, associação, cliente, cartão-fidelidade) e em vários tipos de descontos que podem ser configurados. Todas as transações ocorrem em um canal, motivo pelo qual a presença do canal em uma transação é garantida. As demais entidades são opcionais. Em cada página de dados mestres, há um link para uma página de grupos de preços relacionada na qual é possível ver e adicionar grupos de preços quando necessário. Um grupo de preços é usado para relacionar quatro tipos de entidades diferentes a descontos, ajustes de preço e contratos comerciais. Recomendamos que você elabore uma estratégia para nomear seus grupos de preços de modo a mantê-los organizados. Uma das opções é usar um prefixo ou sufixo de letra ou número para distinguir os diferentes tipos. Por exemplo, 1-xxxxx para grupos de preços de canal e 2-xxxxx para grupos de preços de catálogo. Há quatro páginas de consulta com foco em cada uma das entidades de comércio que podem ter descontos associados a elas.

- **Grupos de preços do canal** – Esta página mostra uma lista de canais e descontos vinculados para cada grupo de preços.
- **Grupos de preços de catálogo**- Esta página mostra uma lista de catálogos e descontos vinculados entre si para cada grupo de preços.
- **Grupos de preços de fidelidade** – Esta página mostra uma lista de programas de fidelidade e descontos vinculados entre si para cada grupo de preços.
- **Grupos de preços de afiliação** – Esta página mostra uma lista de afiliações e descontos vinculados entre si para cada grupo de preços.

## <a name="example-channel-discount-set-up"></a>Exemplo de configuração de desconto de canal

O exemplo a seguir ilustra as tarefas envolvidas na configuração de um desconto de canal.

1. No exemplo, você tem um canal denominado **Houston** e criará um novo desconto denominado **Volta à escola**.
2. Como a estratégia de preços e descontos inclui a possibilidade de descontos de canal, você sempre criará um grupo de preços específico do canal quando criar um canal.
3. Você tem o grupo de preços **Houston-PG** que é atribuído ao canal **Houston**.
4. Após a criação do desconto **Volta à escola**, você precisa clicar em **Grupos de preços** na parte superior da página **Desconto**. A página **Grupos de preços de desconto** será aberta. Em seguida, clique em **Novo** e selecione o grupo de preços **Houston-GP**.
5. Agora você pode habilitar o desconto e enviá-lo por push ao canal.

## <a name="additional-resources"></a>Recursos adicionais

[Ajustes de preços e descontos](price-adjustments-discounts.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]