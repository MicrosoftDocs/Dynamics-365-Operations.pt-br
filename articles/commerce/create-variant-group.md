---
title: Criar um grupo de grades
description: Este tópico descreve como criar um grupo de grades de tamanho, estilo ou cor para um produto do Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailSizeGroupTable, ConfigGroupIdLookup, RetailStyleGroupTable
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 0462958d8225de145a8d886b096f96cd3f2cb5c5
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799532"
---
# <a name="create-a-variant-group"></a>Criar um grupo de grades


[!include [banner](includes/banner.md)]

Este tópico descreve como criar um grupo de grades de tamanho, estilo ou cor para um produto do Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

O Dynamics 365 Commerce oferece suporte a várias grades para produtos. O ideal é configurar grupos de grades para as diferentes categorias de produtos. Por exemplo, é possível criar um grupo de tamanhos para camisetas com tamanhos extra pequeno, pequeno, médio, grande e extra grande, ou criar um grupo de cores para incluir todas as cores disponíveis de um produto. Os grupos de grades devem ser adicionados antes de os produtos serem adicionados.

Neste tópico, será criado e configurado um grupo de tamanhos. Procedimentos semelhantes podem ser usados para adicionar e configurar grupos de estilos e de cores.

## <a name="create-a-size-group"></a>Criar um grupo de tamanhos

Para criar um grupo de tamanhos, siga estas etapas.
 
1. No painel de navegação, vá para **Módulos \> Varejo e comércio \> Produtos e categorias \> Grupos de grades \> Grupos de tamanho**.
1. No painel de ação, selecione **Novo**.
1. Na caixa **Grupo de tamanhos**, digite um nome para o grupo de tamanhos.
1. Na caixa **Descrição**, insira uma descrição apropriada.
1. No painel de ação, selecione **Salvar**.

## <a name="add-attributes-to-the-size-group"></a>Adicionar atributos ao grupo de tamanhos

Para adicionar atributos a um grupo de tamanhos, siga estas etapas.

1. No painel de navegação, vá para **Módulos \> Varejo e comércio \> Produtos e categorias \> Grupos de grades \> Grupos de tamanho**
1. No painel de navegação, selecione um grupo de tamanhos.
1. Em **Linhas de grupo de tamanhos**, selecione **Adicionar**.
1. Na caixa **Tamanho**, insira uma sequência de caracteres que represente o tamanho (por exemplo, "GG").
1. Na caixa **Nome do tamanho**, digite um nome para o tamanho (por exemplo, "Extra Grande").
1. Na caixa **Peso de reabastecimento**, insira um número que represente o peso de reabastecimento.
1. Na caixa **Número no código de barras**, insira um número que represente o código de barras.
1. Na caixa **Ordem de exibição**, insira um número que represente a ordem de exibição.
1. Quando terminar de adicionar os tamanhos, selecione **Salvar** no painel de ação.

A imagem a seguir mostra um exemplo de grupo de tamanhos para "tamanhos de camisas casuais".

![Criar grupo de tamanhos](media/create-variant-group.png)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral das informações do produto](../supply-chain/pim/product-information.md?toc=/dynamics365/commerce/toc.json)

[Configurar produtos de varejo](set-up-retail-products.md)

[Dimensões do produto](../supply-chain/pim/product-dimensions.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]