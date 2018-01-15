---
title: "Uso de catálogos externos para compras eletrônicas de PunchOut"
description: "Este tópico explica como você pode usar catálogos externos para criar e enviar requisições."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchVendorPortalRequests
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c345f1f8d1aaa93dbe02f1f8c53df63bf3488a9e
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="use-external-catalogs-for-punchout-eprocurement"></a>Uso de catálogos externos para compras eletrônicas de PunchOut
Ao usar catálogos externos para PunchOut e-procurement, você não precisa manter informações sobre os produtos de seus fornecedores em seus próprios dados mestre. Em vez disso, o carrinho de compras no site de um fornecedor é convertido em linhas de requisição que possuem as informações corretas do produto. 

Você deve evitar manter as descrições e os preços dos produtos dos seus fornecedores nos dados mestre do seu próprio produto. Em vez disso, use catálogos externos para PunchOut e-procurement. Então, quando os funcionários criam requisições, eles podem "ir" ao site do catálogo externo de um fornecedor (em outras palavras, eles saem do seu sistema e vão para o site do fornecedor). Os produtos que são adicionados ao carrinho de compras no site do fornecedor podem então ser convertidos em linhas de requisição. Portanto, você obtém as informações corretas do produto: identificação do produto, nome, preço e assim por diante.

Para usar catálogos externos, um funcionário deverá criar uma requisição na página **Minhas requisições de compra**.

O funcionário que cria uma requisição é referido como o preparador da requisição. Como preparador, você pode completar as seguintes tarefas.

Use a ação de linha **Catálogos externos** para abrir uma página que inclui todos catálogos externos disponíveis para o solicitante especificado, a entidade legal de compra, e a unidade operacional de recebimento.

Dependendo das suas permissões, altere o solicitante, a entidade legal de compra, e a unidade operacional de recebimento. Uma alteração nesses valores pode alterar a lista de catálogos externos que estão disponíveis para um solicitante. Os catálogos externos disponíveis dependem das políticas de compra ativas atuais para a entidade legal de compra ou a unidade operacional de recebimento. Essas políticas podem permitir ou impedir o acesso a categorias específicas de aquisição. Portanto, a lista de catálogos externos que são mapeados para essas categorias de compras pode ser afetada.

Para obter mais informações sobre as políticas, consulte [Políticas de compra](../procurement/purchase-policies.md).

- Para encontrar catálogos externos para categorias de contratos específicos, insira texto no campo de pesquisa do catálogo.
- Para adicionar produtos do catálogo externo de um fornecedor no site do fornecedor, clique no catálogo externo. Em seguida, adicione produtos ao carrinho de compras e confira. As linhas do carrinho de compras serão transferidas para o Microsoft Dynamics 365.

Se houver várias opções para categorias de compras, selecione a categoria de compras correta antes de adicionar as linhas à requisição.
Depois que as linhas foram adicionadas a uma requisição, você pode adicionar mais linhas sem usar catálogos externos. Alternativamente, você pode continuar a usar catálogos externos para adicionar linhas.

Quando a requisição está pronta, use a ação **Fluxo de trabalho** > **Enviar** para enviar para a aprovação.

