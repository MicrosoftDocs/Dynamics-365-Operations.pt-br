---
title: Configurar um produto para ser adquirido gratuitamente
description: Este tópico descreve como configurar um produto para que ele possa ser comprado gratuitamente no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 2ad96a3dde93a48694aee418ecfbbd33dc9830d6
ms.sourcegitcommit: 6bf9e18989e6d77497a9dda1c362f324b3c2fbf2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2021
ms.locfileid: "7713876"
---
# <a name="configure-a-product-to-be-purchased-for-free"></a>Configurar um produto para ser adquirido gratuitamente

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este tópico descreve como configurar um produto para que ele possa ser comprado gratuitamente no Microsoft Dynamics 365 Commerce.

## <a name="configure-the-product"></a>Configurar o produtos

Para vender um produto gratuitamente no Dynamics 365 Commerce, você deve definir seu preço como 0 (zero). Além disso, você deve ajustar a configuração **Peço zero válido** do produto.

Para definir a configuração **Preço zero válido** na matriz do Commerce, siga estas etapas.

1. Acesse **Retail e Commerce \> Produtos e categorias \> Produtos lançados por categoria**.
1. Acesse a página do produto que você deseja vender gratuitamente. 
1. Na seção **Commerce** da página do produto, defina a opção **Preço zero válido** como **Sim**.

Esta ilustração mostra um exemplo de um produto em que opção **Preço zero válido** está definida como **Sim**.

![Exemplo de um produto em que a opção de preço zero válida está definida como Sim.](./media/Zero-price.png)

## <a name="configure-the-online-stores-functionality-profile"></a>Configurar o perfil de funcionalidade online da loja

Antes de as transações gratuitas serem processadas, você deve ajustar a configuração **Permitir a finalização da compra sem pagamento** do perfil de funcionalidade online da loja para que as transações que não tenham pagamentos sejam permitidas. Para obter informações sobre como criar perfis de funcionalidade, consulte o artigo [Criar um perfil de funcionalidade online](online-functionality-profile.md).

Para definir a configuração **Permitir a finalização da compra sem pagamento** na matriz do Commerce, siga estas etapas.

1. Acesse **Retail e Commerce \> Configuração de canal \> Configuração da loja online**.
1. Na página do perfil de funcionalidade da loja, em **Finalização da compra**, defina a opção **Permitir a finalização da compra sem pagamento** como **Sim**.

Esta ilustração mostra um exemplo de um perfil de loja online em que a opção **Permitir a finalização da compra sem pagamento** está definida como **Sim**.

![Exemplo de um perfil de loja online em que a opção Permitir a finalização da compra sem pagamento está definida como Sim.](./media/Zero-price-profile.png)

## <a name="additional-resources"></a>Recursos adicionais

[Gerenciamento de preços de vendas de varejo](price-management.md)

[Criar um perfil de funcionalidade online](online-functionality-profile.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
