---
title: Atributos de lote
description: Este tópico fornece informações sobre atributos de lote. Os atributos de lote são características de matérias-primas e produtos acabados que compõem os lotes de estoque. O tópico também explica como atribuir atributos de lote e como você pode pesquisar neles ao reservar lotes.
author: ShylaThompson
manager: tfehr
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PdsBatchAttrib, PdsBatchAttribAssociate, PdsBatchAttribByAttribGroup, PdsBatchAttribByItem, PdsBatchAttribByitemCustomer, PdsBatchAttribGroup, WHSBatchAttribReserve
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19271
ms.assetid: 41de0250-4a96-412e-a412-aa06615b6b1d
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b5e2a27fe73ddd9fcd7cafc0ded05fd8a15841fd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966496"
---
# <a name="batch-attributes"></a>Atributos de lote

[!include [banner](../includes/banner.md)]

Este tópico fornece informações sobre atributos de lote. Os atributos de lote são características de matérias-primas e produtos acabados que compõem os lotes de estoque. O tópico também explica como atribuir atributos de lote e como você pode pesquisar neles ao reservar lotes.

Os atributos de lote são características de matérias-primas e produtos acabados que compõem os lotes de estoque. Os atributos de lote podem variar, dependendo de fatores como as condições do ambiente, a qualidade de matérias-primas usadas para produzir o lote ou o resultado do produto acabado. O número e os tipos de atributos de lote que são usados podem variar muito de um setor para outro. Veja a seguir dois exemplos que mostram como usar atributos de lote:

-   Na indústria de queijo, o leite, que é uma das matérias-primas usadas para fabricar o queijo, pode ter atributos como gordura e porcentagem de peso. O queijo que é produzido do leite pode ter outros atributos, como o teor de umidade e idade.
-   Na indústria siderúrgica, o ferro que é produzido pode ter atributos, como as porcentagens de teor de magnésio, prata e zinco.

Para gerenciar melhor o número e os tipos de atributos, você pode usar os grupos de atributos de lote. Dessa forma, você não precisará adicionar cada atributo individualmente.

## <a name="assign-batch-attributes"></a>Atribuir atributos de lote
Você pode atribuir atributos de lote a produtos individuais que são mantidos em lotes de estoque, ou você pode atribuí-los a produtos associados a clientes específicos. Antes de atribuir um atributo de lote no nível do cliente, primeiro você deverá atribuí-lo no nível do produto. O produto deve ter a dimensão de lote definida como **Ativa** no grupo de dimensão de rastreamento. Para atribuir um atributo de lote a um produto individual, use a página específica do produto. Se o atributo for específico de um produto para um cliente, use a página específica do cliente. Quando você adiciona um atributo a um produto, você também define outros parâmetros. Eis alguns exemplos:

-   Os intervalos mínimo e máximo de um atributo do tipo **Inteiro** ou **Fração**.
-   As ações de tolerância para um atributo do tipo **Inteiro** ou **Fração**. Se o valor do atributo estiver fora do intervalo mínimo e máximo, a ação pode ser uma mensagem de aviso ou uma mensagem de erro.
-   O valor de meta do atributo. Esse é o melhor valor do atributo, e se aplica a todos os tipos de atributo.

Você pode acessar as páginas dos produtos selecionados na página de **Produtos liberados** no Gerenciamento de informações do produto. Depois de atribuir atributos de lote a um produto, você poderá adicionar valores específicos aos atributos na página **Atributos de lotes de estoque**.

## <a name="reserve-batches"></a>Reservar lotes
Você pode pesquisar em atributos de lote ao processar as reservas de lote para uma ordem de venda a fim de atender ao pedido de um cliente, ou quando você escolhe e reserva lotes para uma ordem de produção. A pesquisa ajuda a localizar um lote de estoque que contém o produto que tem o atributo de lote que você deseja. Depois de localizar o lote ou os lotes, será possível reservar o produto na linha de transação de estoque de origem.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]