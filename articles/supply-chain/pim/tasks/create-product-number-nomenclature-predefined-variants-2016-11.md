---
title: Criar uma nomenclatura de produtos de grades de produto predefinidas
description: Este tópico explica como configurar uma nomenclatura de número de produto para grades de produtos predefinidas e como você pode atribuí-la ao grupo de dimensões do produto apropriado.
author: ShylaThompson
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4bb73854f52525c0722683086d1b4f1dd7173306
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920648"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>Criar uma nomenclatura de produtos de grades de produto predefinidas

[!include [banner](../../includes/banner.md)]

Este tópico explica como configurar uma nomenclatura de número de produto para grades de produtos predefinidas e como você pode atribuí-la ao grupo de dimensões do produto apropriado. A empresa de dados demo usada para criar este procedimento é USMF. A nova nomenclatura de número de produto é atribuída ao grupo de dimensão de produto Cor e Tamanho. A tarefa geralmente seria realizada por um designer de produto.


## <a name="create-a-product-number-nomenclature"></a>Criar uma nomenclatura de número de produto

1. Vá para **Gerenciamento de informações sobre produtos \> Configuração \> Nomenclatura de produto**.
1. Selecione **Novo**.
1. No campo **Nome**, digite um nome de nomenclatura que ajude a identificar o grupo de dimensões do produto de destino, por exemplo, `ColorSize`.
1. No campo **Descrição**, digite um valor.
1. Selecione **Adicionar**.
1. Selecione o número do **Produto mestre**.
1. Selecione **Adicionar**.
1. Selecione **Constante de texto**.
1. No campo **Texto**, digite um valor.
1. Selecione **Adicionar**.
1. Selecione **Cor**.
1. Selecione **Adicionar**.
1. Selecione **Constante de texto**.
1. No campo **Texto**, digite um valor.
1. Selecione **Adicionar**.
1. Selecione **Tamanho**.
1. Feche a página.

## <a name="assign-the-nomenclature-to-a-product-master"></a>Atribuir a nomenclatura a um produto mestre

1. Selecione **Grupos de dimensões de produto**.
2. Selecione o grupo **Dimensão do produto SizeCol**.
3. Selecione **Editar**.
4. Selecione **Sim** no campo **Usar nomenclatura**.
5. No campo **Nomenclatura de número de grade de produto**, insira ou selecione um valor.
6. Feche a página.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]