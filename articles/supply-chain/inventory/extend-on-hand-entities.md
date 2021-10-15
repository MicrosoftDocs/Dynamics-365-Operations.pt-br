---
title: Estender entidades de dados disponíveis em estoque
description: Este tópico fornece um exemplo que mostra como adicionar campos estendidos às exibições INVENTORSITEONHANDENTITY e INVENTWAREHOUSEONHANDENTITY, de forma que os recursos das entidades de dados disponíveis de estoque possam trabalhar com as extensões.
author: yufeihuang
ms.date: 07/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2020-07-27
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 8161d951c3296b63476c4e7b527efca163a4f4b3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7577687"
---
# <a name="extend-inventory-on-hand-data-entities"></a>Estender entidades de dados disponíveis em estoque

[!include [banner](../includes/banner.md)]

O Microsoft Dynamics 365 Supply Chain Management fornece recursos de [extensibilidade](../../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md) que permitem [adicionar campos a tabelas por meio da extensão](../../fin-ops-core/dev-itpro/extensibility/add-field-extension.md). Este tópico fornece um exemplo que mostra como adicionar campos estendidos às exibições `INVENTORSITEONHANDENTITY` e `INVENTWAREHOUSEONHANDENTITY`, de forma que os recursos das entidades de dados disponíveis de estoque possam trabalhar com as extensões. Para obter mais informações sobre entidades de dados, consulte [Visão geral de gerenciamento de dados](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).

> [!NOTE]
> Esta é uma lista de algumas entidades de dados disponíveis em estoque:
>
> - Estoque disponível por site
> - Estoque disponível por site V2
> - Estoque disponível por depósito
> - Estoque disponível por depósito v2

Depois de adicionar campos às tabelas que são usadas pela exibição `inventSiteOnHandView`, você deve sincronizar o mecanismo para que as extensões sejam reconhecidas corretamente.

1. Estenda a exibição `InventSiteOnHandView` adicionando o campo de extensão.
1. Estenda a exibição `InventSiteOnHandAggregatedView` com os campos de extensão.
1. Estenda a classe de viewBuilder `InventSiteOnHandAggregatedViewBuilder` modificando o método `getExtensionFields()`. Dessa forma, você mapeia os campos de exibição antigos para novos campos de exibição quando a sincronização do viewBuilder é executada.

Por exemplo, você adicionou os seguintes quatro campos à tabela `InventTable` por meio de extensão:

- Campo personalizado 1
- Campo personalizado 2
- Campo personalizado 3
- Campo personalizado 4

No caso, você deve modificar o método `getExtensionFields()` conforme descrito a seguir.

```xpp
[ExtensionOf(classStr(InventSiteOnHandAggregatedViewBuilder))]
public final class InventOnHandAggregatedViewBuilder\_Extension
{
    protected Map getExtensionFields()
    {
        next getExtensionFields();
        Map extensionFields = new Map(Types::Int64, Types::Int64);
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 1), fieldNum(InventSiteOnHandAggregatedView, Custom field 1));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 2), fieldNum(InventSiteOnHandAggregatedView, Custom field 2));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 3), fieldNum(InventSiteOnHandAggregatedView, Custom field 3));
        extensionFields.insert(fieldNum(InventSiteOnHandView, Custom field 4), fieldNum(InventSiteOnHandAggregatedView, Custom field 4));
        return extensionFields;
    }
}
```

Depois de concluir essas etapas, você pode estender o estoque disponível por site e estoque disponível, por entidades de dados de depósito, adicionando os novos campos. Dessa forma, você garante que os campos estendidos sejam reconhecidos e incluídos durante a migração de dados que usa essas entidades de dados.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]