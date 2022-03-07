---
title: Aplicar configurações de adicionar produto ao carrinho
description: Este tópico abrange configurações de "Adicionar ao carrinho" e descreve como adicioná-las no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 55b81e7c644f884b052853206f312ac796031600
ms.sourcegitcommit: 7e976059118938b0089e40bef948029a8c088b38
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2021
ms.locfileid: "6479405"
---
# <a name="apply-add-product-to-cart-settings"></a>Aplicar configurações de adicionar produto ao carrinho

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este tópico abrange configurações de **Adicionar ao carrinho** e descreve como adicioná-las no Microsoft Dynamics 365 Commerce.

Diferentes fluxos de trabalho têm suporte quando um produto é adicionado ao carrinho em um site de comércio eletrônico do Dynamics 365 Commerce. Por exemplo, o usuário do site pode ser levado para a página do carrinho. Como alternativa, o usuário pode permanecer na página atual, mas receber uma notificação que confirma que o produto foi adicionado ao carrinho.

Para dar suporte a diferentes fluxos de trabalho, um campo **Adicionar produto ao carrinho** está disponível em **Configurações \> Extensões** no criador de sites do Commerce. Selecione uma das seguintes opções de configuração para implementar o fluxo de trabalho correspondente:

- **Navegar até página do carrinho** - Quando os usuários adicionarem um item ao carrinho, serão direcionados para a página do carrinho.
- **Mostrar notificação** - Quando os usuários adicionarem um item ao carrinho, receberão uma notificação de confirmação e poderão continuar a procurar na página detalhes do produto (PDP).
- **Mostrar o mini carrinho** – Quando os usuários adicionarem um item ao carrinho, o conteúdo do mini-carrinho será exibido. Os usuários podem revisar todos os itens no carrinho e podem prosseguir para a finalização da compra se estiverem prontos.
- **Mostrar notificação usando o módulo Notificações** – Quando os usuários adicionarem um item ao carrinho, o módulo Notificações será usado para mostrar uma notificação de confirmação. Para que essa opção de configuração funcione, o módulo de notificações deve ser adicionado ao cabeçalho da página.
- **Não navegar até página do carrinho** - Quando os usuários adicionarem um item ao carrinho, serão mantidos na página atual.

A ilustração a seguir mostra um exemplo das opções de configuração **Adicionar produto ao carrinho** no criador de sites.

![Exemplo de opções de configuração de Adicionar produto ao carrinho no criador de sites](./media/AW_sitesettings.PNG)

> [!IMPORTANT]
> - As configurações de **Adicionar produto ao carrinho** do site estão disponíveis a partir da versão 10.0.11 do Dynamics 365 Commerce. Se estiver atualizando de uma versão mais antiga do Dynamics 365 Commerce, você deverá atualizar manualmente o arquivo appsettings.json. Para obter mais informações sobre como atualizar o arquivo appsettings.json, consulte [SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).
> - A opção de configuração **Mostrar o mini carrinho** está disponível na versão 10.0.20 do Dynamics 365 Commerce. Se estiver atualizando de uma versão mais antiga do Dynamics 365 Commerce, você deverá atualizar manualmente o arquivo appsettings.json. Para obter mais informações sobre como atualizar o arquivo appsettings.json, consulte [SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

A ilustração a seguir mostra um exemplo de notificação de confirmação "adicionado ao carrinho" no site da Fabrikam.

![Exemplo de notificação de confirmação "adicionado ao carrinho" no site da Fabrikam](./media/ecommerce-addtocart-notifications.PNG)

A ilustração a seguir mostra um exemplo de notificação de confirmação "adicionado ao carrinho" no site da Adventure Works.

![Exemplo de notificação de confirmação "adicionado ao carrinho" no site da Adventure Works](./media/AW_minicart.PNG)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de caixa de compra](add-buy-box.md)

[Módulo de seletor de loja](store-selector.md)
