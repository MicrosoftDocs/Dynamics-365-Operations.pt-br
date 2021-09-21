---
title: A unidade e a quantidade de unidades não estão funcionando corretamente no diário de estoque
description: A unidade e a quantidade de unidades não estão funcionando corretamente no diário de estoque
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 39f462ae325aa1104a25a8290daed70388e624ec
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475561"
---
# <a name="the-unit-and-unit-quantity-arent-working-correctly-in-the-inventory-journal"></a>A unidade e a quantidade de unidades não estão funcionando corretamente no diário de estoque

## <a name="symptoms"></a>Sintomas

Você pode encontrar um ou ambos os problemas a seguir ao trabalhar com unidades e quantidades em um diário de estoque:

- Você não vê unidades ou quantidades de unidades no diário de estoque enquanto uma unidade de conversão é configurada para o produto liberado e você não consegue alterar a unidade no diário de estoque.
- Você vê os campos **Quantidade** e **Unidade** no diário de estoque, mas não vê o campo **Quantidade de unidades**. Se você alterar a unidade, inserir uma quantidade e lançar o diário, ele ainda mostrará a unidade de medida original para essa quantidade.

## <a name="resolution"></a>Resolução

Para corrigir esse problema, siga estas etapas.

1. No espaço de trabalho **Gerenciamento de recursos**, verifique se o recurso *Usar unidade de medida e quantidade de unidades em diários de estoque* está ativado. Esse recurso adiciona os campos **Unidade** e **Quantidade de unidades** ao diário.
1. Após a ativação do recurso, use os campos **Quantidade**, **Quantidade de unidades** e **Unidade** da seguinte maneira:

    - **Quantidade** – Especifique a quantidade usando a unidade padrão definida para o produto liberado. No entanto, a unidade padrão em si não é mostrada aqui. Se uma conversão for configurada entre a unidade padrão e a unidade selecionada no campo **Unidade**, o campo **Quantidade** será atualizado automaticamente com base nas seleções nos campos **Quantidade de unidades** e **Unidade**.
    - **Quantidade de unidades** – Especifique a quantidade usando a unidade selecionada no campo **Unidade**.
    - **Unidade** – Selecione a unidade a ser aplicada ao valor no campo **Quantidade de unidades**.
