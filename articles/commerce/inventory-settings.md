---
title: Aplicar configurações de estoque
description: Este artigo abrange as configurações de estoque e descreve como aplicá-las no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: bc55715b7c74f3b572459dd1aa7d409b7175535b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287583"
---
# <a name="apply-inventory-settings"></a>Aplicar configurações de estoque

[!include [banner](includes/banner.md)]

Este artigo abrange as configurações de estoque e descreve como aplicá-las no Microsoft Dynamics 365 Commerce.

As configurações de estoque especificam se o estoque deverá ser verificado antes que os produtos sejam adicionados ao carrinho. Eles também definem as mensagens de merchandising relacionadas ao estoque, como "Em estoque" e "Apenas alguns restantes". Essas configurações garantem que um produto não seja comprado se estiver esgotado.

O Dynamics 365 Commerce fornece estimativas de disponibilidade em estoque para produtos. Para obter informações sobre como é calculada a disponibilidade em estoque estimada, consulte [Calcular a disponibilidade de estoque para canais de varejo](calculated-inventory-retail-channels.md).

No construtor de sites do Commerce, os limites de estoque e intervalos podem ser definidos para um produto ou uma categoria. Eles determinam se o estoque pode ser classificado como em estoque, estoque baixo ou esgotado. Para obter detalhes, consulte [Configurar buffers de estoque e níveis de estoque](inventory-buffers-levels.md).

> [!NOTE]
> O suporte para limites e intervalos de estoque está disponível na versão 10.0.12 do Dynamics 365 Commerce.

## <a name="inventory-settings"></a>Configurações de estoque

No Commerce, as configurações de estoque são definidas em **Configurações do Site \> Extensões \> Gerenciamento de Estoque** no construtor de sites. Há seis configurações de estoque, uma das quais está obsoleta (preterida):

- **Habilitar verificação de estoque no aplicativo** – essa configuração ativa uma verificação de estoque de produto. Os módulos caixa de compras, carrinho e separação na loja verificarão então o estoque do produto e só permitirão que um produto seja adicionado ao carrinho se o estoque estiver disponível.
- **Nível de estoque baseado em** – essa configuração define como os níveis de estoque são calculados. Os valores disponíveis são **Total Disponível**, **Físico Disponível** e **Limite de esgotado**. No Commerce, o limite e os intervalos de estoque podem ser definidos para cada produto e categoria. As APIs de estoque retornam informações de estoque de produtos para a propriedade **total Disponível** e a propriedade **Físico Disponível**. O varejista decide se o **Total Disponível** ou **Físico Disponível** deve ser usado para determinar a contagem de estoque e os intervalos correspondentes para os status em estoque e esgotado.

    O valor **Limite de esgotado** da configuração **Nível de estoque com base em** é um valor antigo (herdado) e obsoleto. Quando ele está selecionado, a contagem de estoque é determinada dos resultados do valor de **Total Disponível**, mas o limite é definido pela configuração numérica **Limite de esgotado**, descrita posteriormente. Essa configuração de limite se aplica a todos os produtos em um site de comércio eletrônico. Se o estoque estiver abaixo do número limite, um produto será considerado esgotado. Caso contrário, ele será considerada em estoque. Os recursos do valor **Limite de esgotado** são limitados e não é recomendável usá-lo na versão 10.0.12 e posteriores.

- **Nível de estoque para vários depósitos** – esta configuração permite que o nível de estoque seja calculado com relação ao depósito padrão ou a vários depósitos. A opção **Com base em depósito individual** calculará os níveis de estoque com base no depósito padrão. Como alternativa, um site de comércio eletrônico pode apontar para vários depósitos para facilitar o atendimento. Nesse caso, a opção **Baseado em agregado para depósitos de remessa e de retirada** é usada para indicar a disponibilidade de estoque. Por exemplo, quando um cliente compra um item e seleciona "remessa" como o modo de entrega, o item pode ser enviado de qualquer depósito no grupo de atendimento que tem estoque disponível. A página Detalhes do produto (PDP) mostrará uma mensagem "Em estoque" para remessa se qualquer depósito de remessa disponível no grupo de atendimento tiver estoque. 

    > [!IMPORTANT] 
    > A configuração **Nível de estoque para vários depósitos** está disponível a partir do Commerce versão 10.0.19. Se estiver atualizando de uma versão mais antiga do Commerce, você deverá atualizar manualmente o arquivo appsettings.json. Para obter instruções, consulte [SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

- **Configurações de estoque para páginas de lista de produtos** – essa configuração define como os produtos fora de estoque são mostrados em listas de produtos renderizadas por coleção de produtos e módulos de resultados de pesquisa. Os valores disponíveis são **Exibidos em ordem com outros produtos**, **Ocultar produtos fora de estoque da lista** e **Exibir produtos fora de estoque no final da lista**. Para usar essa configuração, primeiro você precisa definir algumas configurações de pré-requisitos no Commerce headquarters. Para obter mais informações, consulte [Habilitar o reconhecimento de estoque para o módulo de resultados de pesquisa](search-result-module.md#enable-inventory-awareness-for-the-search-results-module).

    > [!IMPORTANT] 
    > A configuração **Configurações de estoque para páginas de listagem de produtos** está disponível a partir do Commerce versão 10.0.20. Se estiver atualizando de uma versão mais antiga do Commerce, você deverá atualizar manualmente o arquivo appsettings.json. Para obter instruções, consulte [SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

- **Intervalos de estoque** – essa configuração define os intervalos de estoque em que a mensagem é mostrada nos módulos de site. Isso só se aplicará se o valor **Total Disponível** ou o valor **Físico Disponível** for selecionado para a configuração **Nível de estoque com base em**. Os valores disponíveis são **Todos**, **Baixo e esgotado** e **Esgotado**.

    - Quando **Tudo** estiver selecionado, as mensagens de todos os intervalos de estoque, de em estoque (mensagem "Disponível") a esgotado (mensagem "Esgotado"), serão mostradas.
    - Quando **Baixo e esgotado** estiver selecionado, as mensagens de todos os intervalos de estoque, exceto em estoque (mensagem "Disponível") serão mostradas.
    - Quando **Esgotado** não estiver selecionado, apenas a mensagem "Esgotado" será mostrada.

- **Limite de esgotado** – essa configuração numérica antiga só entrará em vigor se o valor **Limite de esgotado** estiver selecionado para a configuração **Nível de estoque com base em**.

> [!IMPORTANT] 
> Essas configurações estão disponíveis na versão 10.0.12 do Dynamics 365 Commerce. Se estiver atualizando de uma versão mais antiga do Dynamics 365 Commerce, você deverá atualizar manualmente o arquivo appsettings.json. Para obter instruções sobre como atualizar o arquivo appsettings.json, consulte [SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="modules-that-use-inventory-settings"></a>Módulos que usam configurações de estoque

Os módulos caixa de compras, lista de desejos, seletor de loja, carrinho e ícone de carrinho usam configurações de estoque para mostrar os intervalos de estoque e as mensagens.

No exemplo da ilustração a seguir, um PDP mostra uma mensagem em estoque ("disponível").

![Exemplo de um módulo PDP com uma mensagem de em estoque.](./media/pdp-InStock.png)

No exemplo da ilustração a seguir, um PDP mostra uma mensagem "Esgotado".

![Exemplo de um módulo PDP com uma mensagem de esgotado.](./media/pdp-outofstock.png)

No exemplo da ilustração a seguir, um carrinho mostra uma mensagem em estoque ("disponível").

![Exemplo de um módulo carrinho com uma mensagem de em estoque.](./media/cart-instock.png)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Configurar buffers de estoque e níveis de estoque](inventory-buffers-levels.md)

[Módulo de carrinho](add-cart-module.md)

[Módulo de caixa de compra](add-buy-box.md)

[Páginas e módulos de gerenciamento de contas](account-management.md)

[Módulo de seletor de loja](store-selector.md)

[SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
