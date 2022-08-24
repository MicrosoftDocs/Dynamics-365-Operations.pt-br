---
title: Configurar produtos de varejo
description: Este artigo descreve como configurar produtos no Dynamics 365 Commerce.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.industry: Retail
ms.search.form: RetailProductAndCategoryWorkspace, EcoResProductDetails
ms.openlocfilehash: 22a3ecb235b21e239b23e5450ca4a2f12f9a41ac
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276065"
---
# <a name="set-up-retail-products"></a>Configurar produtos de varejo

[!include [banner](includes/banner.md)]

Este artigo descreve como configurar produtos no Dynamics 365 Commerce.

Para poder oferecer produtos para revenda em seus canais de comércio, você precisa criar e configurar os produtos. O Commerce cria produtos para toda a organização no produto mestre. Você pode criar os produtos, definir as propriedades e os atributos dos produtos, e atribuir os produtos a hierarquias de categoria de comércio. Para tornar os produtos disponíveis em seus canais e adicioná-los a um sortimento ativo, libere os produtos para as entidades legais onde eles estão disponíveis. Para configurar os produtos vendidos usando canais, conclua as seguintes tarefas.

1. **Defina uma hierarquia de produtos.** Usando os recursos de hierarquia de categoria do Commerce, você pode definir as hierarquias de categoria de varejo para agrupar e categorizar os produtos que você distribuir em seus canais de varejo. Atributos definidos pelo usuário e pelo sistema podem ser definidos no nível de categoria. Em seguida, todos os produtos atribuídos à categoria herdam esses atributos. Várias hierarquias de categoria podem ser definidas, e cada produto pode ser atribuído a várias hierarquias. No entanto, em uma única hierarquia, cada produto pode ser atribuídos a apenas uma categoria.
2. **Adicione produtos e variantes de produto ao produto mestre.** Os produtos que são adicionados ao produto mestre representam uma lista global de produtos. Você pode adicionar produtos manualmente, um de cada vez, ou pode importar dados de produtos de seus fornecedores.
3. **Libere os produtos para entidades legais.** Somente os produtos liberados para entidades legais podem ser disponibilizados em seus canais de comércio. Ao definir um produto pela primeira vez, você define-o no nível da organização. Depois, você pode selecionar uma ou mais entidades legais para liberar os produtos. Feito isso, os produtos são disponibilizados para vários canais da sua organização. Você pode usar essa funcionalidade para criar um produto uma vez, adicionar e atualizar atributos e propriedades de produtos em um local, e distribuir o produto em sua organização, para os canais na qual ela está disponível.
4. **Adicione produtos a classificações.** Uma classificação representa um conjunto de produtos que você oferece em seus canais. Você pode definir uma ou várias classificações, e cada produto pode ser atribuído a uma ou várias classificações. Para atribuir produtos a canais de varejo, atribua as classificações a esses canais. Ao criar um sortimento, você pode adicionar produtos que ainda não foram liberados para uma entidade legal. No entanto, você deve liberar os produtos para uma entidade legal para que eles possam ser disponibilizados nos canais.
5. **Adicione produtos às hierarquias de navegação.** Antes que os produtos possam ser procurados online ou no ponto de venda (POS), eles devem ser categorizados em uma hierarquia de navegação do Commerce.
6. **Adicionar produtos em catálogos.** Embora essa etapa seja opcional para o PDV, os armazenamentos online exigem que os produtos sejam incluídos em pelo menos um catálogo.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
