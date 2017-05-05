---
title: "Configurar códigos de barra"
description: "Este artigo descreve como usar códigos de barras no Microsoft Dynamics 365 for Operations - Varejo."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 15971
ms.assetid: 6b4b2ac2-0344-41aa-8818-62c30017d5ac
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 7734a08756f5b737744f9c8ce1d358be020b859f
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-bar-codes"></a>Configurar códigos de barra

[!include[banner](includes/banner.md)]


Este artigo descreve como usar códigos de barras no Microsoft Dynamics 365 for Operations - Varejo.

Você pode usar códigos de barras para comprar e vender produtos, rastrear variantes de produtos, configurar clientes e funcionários. Você também pode usar códigos de barras para emitir e endossar cupons, vales-presentes e memorandos de crédito. Você pode configurar produtos de varejo para tenham códigos de barras padrão ou personalizados, e códigos de barras internos. Os produtos podem ter mais de um código de barras. Por exemplo, um produto podem ter vários códigos de barras se vier de vários fabricantes ou se tiver variantes baseadas em tamanho, estilo ou cor. Os códigos de barra podem incluir o peso ou o preço do produto. Máscaras de código de barras são modelos usados para criar códigos de barras. **Observação:** se você atribuir um código de barras exclusivo a cada combinação de variantes, poderá passar o código de barras no scanner da registradora e permitir que o programa determine que variante do produto está sendo vendida. Você também pode coletar e ver estatísticas sobre vendas por variante. A cada grupo de tamanhos, cores e estilos pode ser atribuído um número exclusivo que identifica o grupo no código de barras. O Dynamics 365 for Operations utiliza a máscara de código de barras para gerar automaticamente códigos de barras para cada combinação de variantes. Essa funcionalidade pode ser útil quando há muitos tamanhos, cores e estilos, pois o número de combinações aumenta significativamente quando cada código de variante é adicionado. Se essa funcionalidade não for usada, os códigos de barras devem ser atribuídos manualmente a cada combinação que representa uma variante de produto. É possível criar códigos de barras de modo manual ou automático. Para criar códigos de barras, conclua as tarefas a seguir na ordem em que são listadas.

1.  [Configurar caracteres da máscara do código de barras](set-up-bar-code-masks.md).
2.  [Configurar máscaras de código de barras](set-up-bar-code-masks.md).
3.  Defina configurações do código de barras.
4.  Crie códigos de barras para produtos.


<a name="see-also"></a>Consulte também
--------

[Configurar máscaras de código de barras](set-up-bar-code-masks.md)



