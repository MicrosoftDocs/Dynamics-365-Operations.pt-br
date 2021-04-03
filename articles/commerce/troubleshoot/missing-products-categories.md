---
title: Estão faltando produtos e categorias após a cópia do ambiente
description: Este tópico fornece orientações de solução de problemas que podem ajudar quando produtos e categorias estiverem faltando depois que um local for copiado entre ambientes ou no mesmo ambiente.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 35f2cbd98a91149395f40bf821c1d5d7e58eaf77
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585203"
---
# <a name="products-and-categories-missing-after-environment-copy"></a>Estão faltando produtos e categorias após a cópia do ambiente

[!include [banner](../../includes/banner.md)]

Este tópico fornece orientações de solução de problemas que podem ajudar quando produtos e categorias estiverem faltando depois que um local for copiado entre ambientes ou no mesmo ambiente.

## <a name="description"></a>descrição

Depois que um site é copiado de um ambiente para outro, ou no mesmo ambiente, os produtos e as categorias estão faltando no site. Os produtos e as categorias estarão faltando na vitrine de comércio eletrônico e na guia **Produtos** no construtor de sites do Commerce.

## <a name="resolution"></a>Resolução

### <a name="map-the-channel-operating-unit-number-to-a-newly-copied-site-in-commerce-site-builder"></a>Mapear o número da unidade operacional do canal para um site recém copiado no construtor de sites do Commerce

Para mapear o número da unidade operacional (OUN) do canal para um site recém copiado no construtor de sites do Commerce, siga estas etapas.

1. Selecione o site recém copiado.
1. Em **Configurações do site**, selecione **Canais**.
1. Ao lado do nome do canal, selecione as reticências (**...**) e selecione **Alterar canal da loja online**.
1. Na caixa de diálogo **Alterar canal da loja online**, selecione o canal a ser mapeado para o site recém copiado e selecione **OK**.
1. Selecione **Salvar e publicar**.

## <a name="additional-resources"></a>Recursos adicionais

[Associar um site do Dynamics 365 Commerce a um canal online](../associate-site-online-store.md)
