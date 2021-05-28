---
title: Estão faltando produtos e categorias após a cópia do ambiente
description: Este tópico fornece orientações de solução de problemas que podem ajudar quando produtos e categorias estiverem faltando depois que um local for copiado entre ambientes ou no mesmo ambiente.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: 4964b9623a91286d4f8260bcae7941feb48f8962
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022389"
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
