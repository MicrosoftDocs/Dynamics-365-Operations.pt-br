---
title: Criar uma nomenclatura de produtos de grades de produto configuradas
description: Este procedimento mostra como configurar uma nomenclatura de número de produto para grades de produtos configurados e como ela pode ser anexada a um produto mestre configurável.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7ea30dc107213b1a2c6b2a109188066a6ea82159
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921002"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a>Criar uma nomenclatura de produtos de grades de produto configuradas

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como configurar uma nomenclatura de número de produto para grades de produtos configurados e como ela pode ser anexada a um produto mestre configurável. O procedimento também demonstra como você pode criar uma nomenclatura de configuração para um componente de modelo de configuração de produto. A empresa de dados demo usada para criar este procedimento é USMF. A nova nomenclatura de número de produto é atribuída ao produto mestre D0004. A tarefa geralmente seria realizada por um designer de produto.

## <a name="create-a-product-number-nomenclature"></a>Criar uma nomenclatura de número de produto

1. Vá para **Gerenciamento de informações sobre produtos \> Configuração \> Nomenclatura de produto**.
1. Selecione **Novo**.
1. No campo **Nome**, digite um valor.
1. No campo **Descrição**, digite um valor.
1. Selecione **Adicionar**.
1. Selecione **Número do produto mestre**.
1. Selecione **Adicionar**.
1. Selecione **Constante de texto**.
1. Na lista, marque a linha selecionada.
1. No campo **Texto**, digite um valor.
1. Selecione **Adicionar**.
1. Selecione **Configuração**.
1. Feche a página.

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a>Atribuir a nomenclatura de número de produto a um produto mestre

1. Vá para **Gerenciamento de informações sobre produtos \> Produtos \> Produtos mestre**.
1. Use o Filtro Rápido para localizar registros. Por exemplo, filtre no campo **Número do produto** com um valor de 'D'.
1. Na lista, selecione o link na linha selecionada.
1. Selecione **Editar**.
1. Selecione *Sim* no campo **Usar nomenclatura**.
1. No campo **Nomenclatura de número de grade de produto**, insira ou selecione um valor.
1. Feche a página.
1. Feche a página.

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a>Criar nomenclatura para um componente de modelo de configuração de produto

1. Vá para **Gerenciamento de informações do produto \> Produtos \> Modelos de configuração do produto**.
1. Na lista, localize e selecione o registro desejado.
1. Na lista, selecione o link na linha selecionada.
1. Selecione **Editar**.
1. Selecione *Sim* no campo **Usar nomenclatura de configuração**.
1. Selecione **Adicionar**.
1. Selecione **Valor do atributo**.
1. Na lista, marque a linha selecionada.
1. No campo **Atributo**, informe ou selecione um valor.
1. Selecione **Adicionar**.
1. Selecione **Constante de texto**.
1. Na lista, marque a linha selecionada.
1. No campo **Texto**, digite um valor.
1. Selecione **Adicionar**.
1. Selecione **Valor do atributo**.
1. Na lista, marque a linha selecionada.
1. No campo **Atributo**, informe ou selecione um valor.
1. Selecione **Adicionar**.
1. Selecione **Constante de texto**.
1. Na lista, marque a linha selecionada.
1. No campo **Texto**, digite um valor.
1. Selecione **Adicionar**.
1. Selecione **Valor do atributo**.
1. Na lista, marque a linha selecionada.
1. No campo **Atributo**, informe ou selecione um valor.
1. Selecione **Adicionar**.
1. Selecione **Constante de texto**.
1. Na lista, marque a linha selecionada.
1. No campo **Texto**, digite um valor.
1. Selecione **Adicionar**.
1. Selecione **Valor do atributo**.
1. Na lista, marque a linha selecionada.
1. No campo **Atributo**, informe ou selecione um valor.
1. Selecione **Adicionar**.
1. Selecione **Constante de texto**.
1. Na lista, marque a linha selecionada.
1. No campo **Texto**, digite um valor.
1. Selecione **Adicionar**.
1. Selecione **Valor de sequência numérica**.
1. Na lista, marque a linha selecionada.
1. No campo **Sequência numérica**, informe ou selecione um valor.
1. Feche a página.
1. Feche a página.
1. Feche a página.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]