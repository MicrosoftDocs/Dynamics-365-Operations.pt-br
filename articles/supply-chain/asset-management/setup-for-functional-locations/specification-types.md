---
title: Manutenção dos tipos do atributo
description: Este tópico explica como criar tipos de atributo no Asset Management.
author: johanhoffmann
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationTypeCopy, EntAssetAttributeType, EntAssetAttributeTypeValue, EntAssetFunctionalLocationType
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 283cff931ce665ae09152c8f3d3c976b7c8b66ff
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808511"
---
# <a name="maintenance-attribute-types"></a>Manutenção dos tipos do atributo

[!include [banner](../../includes/banner.md)]

 

Este tópico explica como criar tipos de atributo no Asset Management. Os atributos são usados para descrever as propriedades dos vários elementos. Você pode configurar atributos nos seguintes elementos:

- [Tipos de locais funcionais](../setup-for-functional-locations/functional-location-types.md)
- [Criar locais funcionais](../functional-locations/create-functional-locations.md)
- [Tipos de ativo](../setup-for-objects/object-types.md)
- Ativos

Os atributos configurados podem variar, dependendo do elemento. Por exemplo, para um local funcional, você pode configurar atributos da configuração e do tamanho físico do local. Para um tipo de ativo ou um ativo, você pode configurar atributos para o volume do motor, consumo de energia e capacidade máxima de carga sob condições diferentes.

## <a name="create-attribute-types"></a>Criar tipos de atributo

Você pode criar seus próprios tipos de atributo. Além disso, você pode transferir dimensões do produto para a página **Tipos de atributo**.

1. Selecione **Gerenciamento de ativos** \> **Configuração** \> **Tipos de atributo**.
2. Na primeira vez que você configurar tipos de atributo, selecione **Criar dimensões do produto** para transferir automaticamente dimensões do produto padrão.
3. Selecione **Novo** para criar um novo tipo de atributo.
4. No campo **Tipo de atributo**, insira um nome para o tipo de atributo.
5. No campo **Descrição**, insira uma descrição.
6. No campo **Unidade** , selecione a unidade de atributo relevante, conforme necessário.
7. No campo **Tipo de dados**, selecione um tipo de dados para a unidade.
8. Se você tiver selecionado **String** como o tipo de dados, siga estas etapas para criar valores para o tipo de atributo:

    1. Selecione o tipo de atributo e então selecione **Valores**.
    2. No campo **Valores do atributo**, selecione **Novo**.
    3. No campo **Tipo de atributo**, selecione um tipo de atributo (dimensão).
    4. No campo **Valor**, insira um valor relacionado.
    5. No campo **Descrição**, insira uma descrição.
    6. Salve o registro.
    7. Retorne à página **Tipos de atributo**.

9. Salve o registro.

    O campo **Tipos de local funcional** mostra o número de locais funcionais que usam o tipo de atributo. O campo **Tipos de ativo** mostra o número de tipos de ativo que o estão usando.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]