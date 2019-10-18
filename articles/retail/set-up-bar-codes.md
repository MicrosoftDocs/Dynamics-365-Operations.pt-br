---
title: Configurar códigos de barras
description: Este artigo descreve como usar códigos de barras no Dynamics 365 Retail.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailBarcodeMaskCharacter, RetailBarcodeMaskSetup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: b7a668f8b44c5f573957a91ab19a8b7fac7a95ba
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024881"
---
# <a name="set-up-bar-codes"></a>Configurar códigos de barras

[!include [banner](includes/banner.md)]

Este artigo descreve como usar códigos de barras no Dynamics 365 Retail.

Você pode usar códigos de barras para comprar e vender produtos, rastrear variantes de produtos, configurar clientes e funcionários. Você também pode usar códigos de barras para emitir e endossar cupons, vales-presentes e memorandos de crédito. Você pode configurar produtos de varejo para tenham códigos de barras padrão ou personalizados, e códigos de barras internos. Os produtos podem ter mais de um código de barras. Por exemplo, um produto podem ter vários códigos de barras se vier de vários fabricantes ou se tiver variantes baseadas em tamanho, estilo ou cor. Os códigos de barra podem incluir o peso ou o preço do produto. Máscaras de código de barras são modelos usados para criar códigos de barras.

> [!NOTE]
> Se você atribuir um único código de barras a cada combinação de variantes, poderá verificar o código de barras no registro e permitir que o programa determine que variante do produto está sendo vendida. Você também pode coletar e ver estatísticas sobre vendas por variante. A cada grupo de tamanhos, cores e estilos pode ser atribuído um número exclusivo que identifica o grupo no código de barras. O Retail usa a máscara de código de barra para gerar automaticamente códigos de barra para cada combinação variante. Essa funcionalidade pode ser útil quando há muitos tamanhos, cores e estilos, pois o número de combinações aumenta significativamente quando cada código de variante é adicionado. Se essa funcionalidade não for usada, os códigos de barras devem ser atribuídos manualmente a cada combinação que representa uma variante de produto.

É possível criar códigos de barras de modo manual ou automático. Para criar códigos de barras, conclua as tarefas a seguir na ordem em que são listadas.

1. [Configurar caracteres da máscara do código de barras](set-up-bar-code-masks.md).
2. [Configurar máscaras de código de barras](set-up-bar-code-masks.md).
3. Defina configurações do código de barras.
4. Crie códigos de barras para produtos.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar máscaras de código de barras](set-up-bar-code-masks.md)
