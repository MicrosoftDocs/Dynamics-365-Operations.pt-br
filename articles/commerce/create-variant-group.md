---
title: Criar um grupo de grades
description: Este artigo descreve como criar um grupo de grades de tamanho, estilo ou cor para um produto do Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.search.form: RetailSizeGroupTable, ConfigGroupIdLookup, RetailStyleGroupTable
ms.openlocfilehash: 507076259c2d9dfe97a0e24d253b5ac0a8325fe2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270091"
---
# <a name="create-a-variant-group"></a>Criar um grupo de grades


[!include [banner](includes/banner.md)]

Este artigo descreve como criar um grupo de grades de tamanho, estilo ou cor para um produto do Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

O Dynamics 365 Commerce oferece suporte a várias grades para produtos. O ideal é configurar grupos de grades para as diferentes categorias de produtos. Por exemplo, é possível criar um grupo de tamanhos para camisetas com tamanhos extra pequeno, pequeno, médio, grande e extra grande, ou criar um grupo de cores para incluir todas as cores disponíveis de um produto. Os grupos de grades devem ser adicionados antes de os produtos serem adicionados.

Neste artigo, será criado e configurado um grupo de tamanhos. Procedimentos semelhantes podem ser usados para adicionar e configurar grupos de estilos e de cores.

## <a name="create-a-size-group"></a>Criar um grupo de tamanhos

Para criar um grupo de tamanhos, siga estas etapas.
 
1. No painel de navegação, Acesse **Módulos \> Varejo e comércio \> Produtos e categorias \> Grupos de grades \> Grupos de tamanho**.
1. No painel de ação, selecione **Novo**.
1. Na caixa **Grupo de tamanhos**, digite um nome para o grupo de tamanhos.
1. Na caixa **Descrição**, insira uma descrição apropriada.
1. No painel de ação, selecione **Salvar**.

## <a name="add-attributes-to-the-size-group"></a>Adicionar atributos ao grupo de tamanhos

Para adicionar atributos a um grupo de tamanhos, siga estas etapas.

1. No painel de navegação, Acesse **Módulos \> Varejo e comércio \> Produtos e categorias \> Grupos de grades \> Grupos de tamanho**
1. No painel de navegação, selecione um grupo de tamanhos.
1. Em **Linhas de grupo de tamanhos**, selecione **Adicionar**.
1. Na caixa **Tamanho**, insira uma sequência de caracteres que represente o tamanho (por exemplo, "GG").
1. Na caixa **Nome do tamanho**, digite um nome para o tamanho (por exemplo, "Extra Grande").
1. Na caixa **Peso de reabastecimento**, insira um número que represente o peso de reabastecimento.
1. Na caixa **Número no código de barras**, insira um número que represente o código de barras.
1. Na caixa **Ordem de exibição**, insira um número que represente a ordem de exibição.
1. Quando terminar de adicionar os tamanhos, selecione **Salvar** no painel de ação.

A imagem a seguir mostra um exemplo de grupo de tamanhos para "tamanhos de camisas casuais".

![Criar grupo de tamanhos.](media/Size-Groups.png)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral das informações do produto](../supply-chain/pim/product-information.md?toc=/dynamics365/commerce/toc.json)

[Configurar produtos de varejo](set-up-retail-products.md)

[Dimensões do produto](../supply-chain/pim/product-dimensions.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
