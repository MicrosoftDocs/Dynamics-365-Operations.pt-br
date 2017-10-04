---
title: Configurar produtos de varejo
description: Este artigo descreve como configurar produtos de revenda no Microsoft Dynamics 365 para Varejo.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: 2be44e0000e9730aa93076f21a4204f5d56f6aac
ms.contentlocale: pt-br
ms.lasthandoff: 06/20/2017

---

# <a name="set-up-retail-products"></a>Configurar produtos de varejo

[!include[banner](includes/banner.md)]


Este artigo descreve como configurar produtos de revenda no Microsoft Dynamics 365 para Varejo.

Para poder oferecer produtos para revenda em seus canais de varejo, você deve criar e configurar os produtos no Dynamics 365 para Varejo. O varejo usará os recursos de produto no Dynamics 365 para Varejo para criar produtos no nível da organização no produto mestre. É possível criar os produtos, definir as propriedades e os atributos dos produtos, bem como atribuir os produtos a hierarquias de categoria de varejo. Para tornar os produtos disponíveis em seus canais de varejo e adicioná-los a um sortimento ativo, é preciso liberar os produtos para as entidades legais em que estão disponíveis. Para configurar os produtos vendidos usando canais de varejo, conclua as seguintes tarefas.

1.  Defina uma hierarquia de produtos de varejo. Usando os recursos de hierarquia de categoria no Dynamics 365 para Varejo você pode definir as hierarquias de categoria de varejo para agrupar e categorizar os produtos que você distribui em seus canais de varejo. Atributos definidos pelo usuário e pelo sistema podem ser definidos no nível de categoria. Em seguida, todos os produtos atribuídos à categoria herdam esses atributos. Várias hierarquias de categoria podem ser definidas, e cada produto pode ser atribuído a várias hierarquias. No entanto, em uma única hierarquia, cada produto pode ser atribuídos a apenas uma categoria.
2.  Adicione produtos e variantes de produto ao produto mestre. Os produtos que são adicionados ao produto mestre representam uma lista global de produtos. Você pode adicionar produtos manualmente, um de cada vez, ou pode importar dados de produtos de seus fornecedores.
3.  Libere os produtos para entidades legais. Somente os produtos liberados para entidades legais podem ser disponibilizados em seus canais de varejo. Ao definir um produto pela primeira vez, você define-o no nível da organização. Depois, você pode selecionar uma ou mais entidades legais para liberar os produtos. Feito isso, os produtos são disponibilizados para vários canais de varejo da sua organização. Você pode usar essa funcionalidade para criar um produto uma vez, adicionar e atualizar atributos e propriedades de produtos em um local, e distribuir o produto em sua organização, para os canais de varejo na qual ela está disponível.
4.  Adicione produtos a classificações. Uma classificação representa um conjunto de produtos que você oferece em seus canais de varejo. Você pode definir uma ou várias classificações, e cada produto pode ser atribuído a uma ou várias classificações. Para atribuir produtos a canais de varejo, atribua as classificações a esses canais de varejo. Ao criar um sortimento, você pode adicionar produtos que ainda não foram liberados para uma entidade legal. No entanto, você deve liberar os produtos para uma entidade legal para que eles possam ser disponibilizados nos canais de varejo.
5.  Adicione produtos às hierarquias de navegação. Antes que os produtos possam ser procurados online ou no ponto de venda (POS), eles devem ser categorizados em uma hierarquia de navegação de Varejo.
6.  Adicionar produtos em catálogos. Embora essa etapa seja opcional para o PDV, os armazenamentos online exigem que os produtos sejam incluídos em pelo menos um catálogo.




