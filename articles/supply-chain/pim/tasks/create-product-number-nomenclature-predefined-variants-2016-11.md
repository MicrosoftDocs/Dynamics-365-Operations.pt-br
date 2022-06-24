---
title: Criar uma nomenclatura de produtos de grades de produto predefinidas
description: Este artigo explica como configurar uma nomenclatura de número de produto para grades de produtos predefinidas e como você pode atribuí-la ao grupo de dimensões do produto apropriado.
author: t-benebo
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e77c8eabe1657f7fbfef71747627207dccff3b60
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887302"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>Criar uma nomenclatura de produtos de grades de produto predefinidas

[!include [banner](../../includes/banner.md)]

Este artigo explica como configurar uma nomenclatura de número de produto para grades de produtos predefinidas e como você pode atribuí-la ao grupo de dimensões do produto apropriado. A empresa de dados demo usada para criar este procedimento é USMF. A nova nomenclatura de número de produto é atribuída ao grupo de dimensão de produto Cor e Tamanho. A tarefa geralmente seria realizada por um designer de produto.


## <a name="create-a-product-number-nomenclature"></a>Criar uma nomenclatura de número de produto

1. Acesse **Gerenciamento de informações sobre produtos \> Configuração \> Nomenclatura de produto**.
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