---
title: Aplicar configurações de estoque
description: Este tópico abrange as configurações de estoque e descreve como aplicá-las no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: d7d25fd62efca52dd2d60ed3435104c3507a1d19
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817600"
---
# <a name="apply-inventory-settings"></a>Aplicar configurações de estoque

[!include [banner](includes/banner.md)]

Este tópico abrange as configurações de estoque e descreve como aplicá-las no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

As configurações de estoque especificam se o estoque deverá ser verificado antes que os produtos sejam adicionados ao carrinho. Eles também definem as mensagens de merchandising relacionadas ao estoque, como "Em estoque" e "Apenas alguns restantes". Essas configurações garantem que um produto não seja comprado se estiver esgotado.

O Dynamics 365 Commerce fornece estimativas de disponibilidade em estoque para produtos. Para obter informações sobre como é calculada a disponibilidade em estoque estimada, consulte [Calcular a disponibilidade de estoque para canais de varejo](calculated-inventory-retail-channels.md).

No construtor de sites do Commerce, os limites de estoque e intervalos podem ser definidos para um produto ou uma categoria. Eles determinam se o estoque pode ser classificado como em estoque, estoque baixo ou esgotado. Para obter detalhes, consulte [Configurar buffers de estoque e níveis de estoque](inventory-buffers-levels.md).

> [!NOTE]
> O suporte para limites e intervalos de estoque está disponível na versão 10.0.12 do Dynamics 365 Commerce.

## <a name="inventory-settings"></a>Configurações de estoque

No Commerce, as configurações de estoque são definidas em **Configurações do Site \> Extensões \> Gerenciamento de Estoque** no construtor de sites. Há quatro configurações de estoque, uma das quais está obsoleta (preterida):

- **Habilitar verificação de estoque no aplicativo** – essa configuração ativa uma verificação de estoque de produto. Os módulos caixa de compras, carrinho e separação na loja verificarão então o estoque do produto e só permitirão que um produto seja adicionado ao carrinho se o estoque estiver disponível.
- **Nível de estoque baseado em** – essa configuração define como os níveis de estoque são calculados. Os valores disponíveis são **Total Disponível**, **Físico Disponível** e **Limite de esgotado**. No Commerce, o limite e os intervalos de estoque podem ser definidos para cada produto e categoria. As APIs de estoque retornam informações de estoque de produtos para a propriedade **total Disponível** e a propriedade **Físico Disponível**. O varejista decide se o **Total Disponível** ou **Físico Disponível** deve ser usado para determinar a contagem de estoque e os intervalos correspondentes para os status em estoque e esgotado.

    O valor **Limite de esgotado** da configuração **Nível de estoque com base em** é um valor antigo (herdado) e obsoleto. Quando ele está selecionado, a contagem de estoque é determinada dos resultados do valor de **Total Disponível**, mas o limite é definido pela configuração numérica **Limite de esgotado**, descrita posteriormente. Essa configuração de limite se aplica a todos os produtos em um site de comércio eletrônico. Se o estoque estiver abaixo do número limite, um produto será considerado esgotado. Caso contrário, ele será considerada em estoque. Os recursos do valor **Limite de esgotado** são limitados e não é recomendável usá-lo na versão 10.0.12 e posteriores.

- **Intervalos de estoque** – essa configuração define os intervalos de estoque em que a mensagem é mostrada nos módulos de site. Isso só se aplicará se o valor **Total Disponível** ou o valor **Físico Disponível** for selecionado para a configuração **Nível de estoque com base em**. Os valores disponíveis são **Todos**, **Baixo e esgotado** e **Esgotado**.

    - Quando **Tudo** estiver selecionado, as mensagens de todos os intervalos de estoque, de em estoque (mensagem "Disponível") a esgotado (mensagem "Esgotado"), serão mostradas.
    - Quando **Baixo e esgotado** estiver selecionado, as mensagens de todos os intervalos de estoque, exceto em estoque (mensagem "Disponível") serão mostradas.
    - Quando **Esgotado** não estiver selecionado, apenas a mensagem "Esgotado" será mostrada.

- **Limite de esgotado** – essa configuração numérica antiga só entrará em vigor se o valor **Limite de esgotado** estiver selecionado para a configuração **Nível de estoque com base em**.

> [!IMPORTANT] 
> Essas configurações estão disponíveis na versão 10.0.12 do Dynamics 365 Commerce. Se estiver atualizando de uma versão mais antiga do Dynamics 365 Commerce, você deverá atualizar manualmente o arquivo appsettings.json. Para obter instruções sobre como atualizar o arquivo appsettings.json, consulte [SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="modules-that-use-inventory-settings"></a>Módulos que usam configurações de estoque

Os módulos caixa de compras, lista de desejos, seletor de loja, carrinho e ícone de carrinho usam configurações de estoque para mostrar os intervalos de estoque e as mensagens.

A imagem a seguir mostra um exemplo de uma página de detalhes do produto (PDP) que está mostrando uma mensagem de em estoque ("Disponível").

![Exemplo de um módulo PDP com uma mensagem de em estoque](./media/pdp-InStock.png)

A imagem a seguir mostra um exemplo de uma página de detalhes do produto (PDP) que está mostrando uma mensagem "Esgotado".

![Exemplo de um módulo PDP com uma mensagem de esgotado](./media/pdp-outofstock.png)

A imagem a seguir mostra um exemplo de um carrinho mostrando uma mensagem de em estoque ("Disponível").

![Exemplo de um módulo carrinho com uma mensagem de em estoque](./media/cart-instock.png)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Configurar buffers de estoque e níveis de estoque](inventory-buffers-levels.md)

[Módulo de carrinho](add-cart-module.md)

[Módulo de caixa de compra](add-buy-box.md)

[Páginas e módulos de gerenciamento de contas](account-management.md)

[Módulo de seletor de loja](store-selector.md)

[SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md)
