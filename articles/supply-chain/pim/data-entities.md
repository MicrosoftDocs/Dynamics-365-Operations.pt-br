---
title: Entidades de dados do produto
description: Este tópico fornece informações sobre as diferentes entidades que podem ser usadas para importar e exportar dados de produtos.
author: cvocph
manager: tfehr
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: kamaybac
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2019-12-1
ms.openlocfilehash: e05d5febdd57a25d796fb3d085390758f5e7ceca
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007757"
---
# <a name="product-data-entities"></a>Entidades de dados do produto

[!include [banner](../includes/banner.md)]

Para importar e exportar dados de produto, você deve usar entidades de dados. A tabela a seguir fornece detalhes sobre as entidades de dados relacionadas ao produto e descreve a finalidade de cada uma.

| Entidade | Nome do árvore de objetos de aplicativo (AOT) (tipo) | Observação |
|--------|-------------------------------------------|-------|
| Produtos V2 | `EcoResProductV2Entity` | Esta entidade é usada para importar e exportar produtos compartilhados e distintos e produtos-mestre. Ele permite atualizações. Ele não oferece suporte a operações SQL baseadas em conjuntos. Está habilitado para protocolo de dados abertos (OData). |
| Produtos liberados V2 | `EcoResReleasedProductV2Entity` | Esta entidade é usada para importar e exportar produtos liberados e distintos e produtos-mestre. Ele permite atualizações. Isso requer que a grade de produto compartilhado já tenha sido criada. Quando um novo produto liberado é importado, ocorre uma liberação do produto compartilhado. Também há entidades separadas que podem ser usadas para importar e exportar os mestres de produtos liberados e lançar variantes distintas. Essa entidade não oferece suporte a operações SQL baseadas em conjuntos ou excluir operações. Ele está habilitado para OData. |
| Criação de produtos liberados V2 | `EcoResReleasedProductCreationV2Entity` | Essa entidade é usada para importar produtos compartilhados e produtos liberados em uma única etapa. Embora ofereça suporte a exportações, isso não é recomendável porque a finalidade da entidade é a criação de produtos. Ele não oferece suporte a atualizações. Ele oferece suporte a um conjunto limitado de campos (campos disponíveis na caixa de diálogo de criação de produtos). Ele não oferece suporte a operações SQL baseadas em conjuntos. Ele não é exposto por meio do OData. |
| Variantes de produtos | `EcoResProductVariantEntity` | Esta entidade é usada para importar e exportar grades de produtos compartilhados. Ele permite atualizações. Ele requer que os valores de dimensão já tenham sido criados. A chave de integração é o produto mestre mais as dimensões do produto. Essa entidade não oferece suporte a operações SQL baseadas em conjuntos. Ele está habilitado para OData. Ela oferece suporte a operações de exclusão. Ela não pode ser estendida por meio da adição de novas dimensões de produto. |
| Variantes de produtos por identificação de número de produto | `EcoResProductNumberIdentifiedProductVariantEntity` | Esta entidade é usada para importar e exportar grades de produtos compartilhados. Ele permite atualizações. Ele requer que os valores de dimensão já tenham sido criados. A chave de integração é o número do produto (sendo que a chave de integração para a entidade **Grades de produto** são o produto mestre mais dimensões do produto). |
| Grades de produtos liberadas | `EcoResReleasedProductVariantEntity` | Esta entidade é usada para importar e exportar grades de produtos liberados. Ele permite atualizações. Isso requer que a grade de produto compartilhado já tenha sido criada. Quando uma nova grade de produto é importada, ocorre uma liberação da grade de produto. Essa entidade não oferece suporte a operações SQL baseadas em conjuntos. Ele está habilitado para OData. Embora ofereça suporte a operações de exclusão, no momento esse uso causa a corrupção de dados por causa de um bug na plataforma atual. Essa entidade não pode ser estendida por meio da adição de novas dimensões de produto. |
| Variantes de produtos liberados por identificação de número de produto | `EcoResProductNumberIdentifiedReleasedProductVariantEntity` | Essa entidade se assemelha à entidade **Grades de produto liberados**, mas a chave de integração é o número do produto em vez do produto mestre mais dimensões do produto. Ela não pode ser estendida por meio da adição de novas dimensões de produto. |
| Produtos liberados comercializáveis | `EcoResSellableReleasedProductEntity` | Esta entidade é usada para exportar somente produtos comercializáveis. Os produtos comercializáveis são produtos contendo as informações necessárias para serem usados em uma ordem de venda. As mesmas regras se aplicam quando um produto é validado usando a função **Validar** na página **Produtos liberado**. |
| Produtos distintos liberados V2 | `EcoResDistinctProductV2Entity` | Esta entidade é usada para exportar produtos distintos. Esses produtos distintos podem ser produtos, produtos de subtipo e grades de produto. |
| Produtos mestres liberados V2 | `EcoResProductMasterV2Entity` | Esta entidade é usada para importar e exportar produtos mestre. Ela não está habilitada para o gerenciamento de dados. |
| Item - código de barras | `EcoResProductBarcodeEntityV3` | Esta entidade é usada para exportar produtos e códigos de barras. Esta entidade não permite controle de alterações, atualizações ou exclusões. Para usar o controle de alterações, atualizações ou exclusões em códigos de barras, use a entidade **Associação entre item e código de barras**. |
| Associação entre item e código de barras | `EcoResProductBarcodeAssociationEntity` | Esta entidade é usada para exportar produtos e códigos de barras. Ela permite controle de alterações, atualizações e exclusões. Para usar a entidade, o recurso *Aprimoramentos de itens e códigos de barras* deve estar habilitado no [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Sua chave de entidade é `AssociationID`, que cria a associação entre o código de barras e o produto. Para adicionar suporte a essa chave, a tabela `InventitemBarcodeAssociation` será preenchida para os dados existentes de código de barras do item quando você ativar o recurso. A tabela é preenchida por meio de um trabalho em lotes. Se a sua tabela de código de barras tiver muitos registros, talvez seja necessário um tempo significativo para executar o trabalho em lotes. Portanto, é recomendável planejar a habilitação do recurso (e, portanto, executar o trabalho em lotes) em um momento adequado à agenda de trabalho. |
| Estados do ciclo de vida de produto | `EcoResProductLifecycleSateEntity` | Esta entidade é usada para importar e exportar os diferentes estados do ciclo de vida do produto que podem ser atribuídos a um produto. |

> [!NOTE]
> Você pode usar a entidade de dados **Produtos lançados V2** para importar produtos para o sistema somente se o produto compartilhado já foi criado. Caso contrário, para importar produtos para o sistema, você deve usar a entidade de dados **Criação de produto**.
