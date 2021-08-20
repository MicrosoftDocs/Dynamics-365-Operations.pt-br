---
title: Aplicar configurações de unidade de medida
description: Este tópico abrange as configurações de unidade de medida e descreve como aplicá-las no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/23/2021
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
ms.openlocfilehash: 7fe5cf6b57a8897a0bd541146cb1ad17b496d5633c0a1df9d58b2a4fbc868139
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6761505"
---
# <a name="apply-unit-of-measure-settings"></a>Aplicar configurações de unidade de medida

[!include [banner](includes/banner.md)]

Este tópico abrange as configurações de unidade de medida e descreve como aplicá-las no Microsoft Dynamics 365 Commerce.

Um produto pode ser vendido em unidades diferentes, como "cada", "par" e "dúzia". Na matriz do Commerce, a unidade de medida de venda pode ser definida para um produto e mostrada em um site de comércio eletrônico. Por exemplo, se um varejista vender um produto individualmente e em dúzias, as unidades de medida disponíveis poderão ser mostradas junto com outras informações do produto.

No exemplo da ilustração a seguir, uma unidade de medida de venda de **ea** (cada) foi configurada para um produto na matriz do Commerce.

![Exemplo de um produto configurado com uma unidade de medida na matriz do Commerce.](./media/Productunit-headquarters.PNG)

> [!NOTE]
> O suporte para a aplicação e a exibição da unidade de medida está disponível a partir do Commerce versão 10.0.19.

## <a name="unit-of-measure-settings"></a>Configurações de unidade de medida

As configurações de exibição de unidade de medida são definidas no construtor de sites do Commerce, em **Configurações do site \> Extensões \> Exibir unidade de medida de produtos**. Há três configurações com suporte:

- **Não exibir** – Quando esta configuração for selecionada, o site de comércio eletrônico não mostrará a unidade de medida do produto. Esse é o comportamento padrão.
- **Exibir na experiência de compra do produto** – Quando esta configuração for selecionada, a unidade de medida será mostrada nas páginas de detalhes do produto, carrinho, finalização da compra, histórico de ordens e detalhes da ordem.
- **Exibir na experiência de navegação e compra do produto** – Quando esta configuração for selecionada, a unidade de medida será mostrada nas páginas de experiência de compra do produto e também durante a experiência de navegação do produto. Como parte desse comportamento, as unidades de medida são mostradas nos resultados da pesquisa e nos módulos de coleção de produtos.

> [!IMPORTANT]
> As configurações de exibição de unidade de medida estão disponíveis a partir do Commerce versão 10.0.19. Se estiver atualizando de uma versão mais antiga do Commerce, você deverá atualizar manualmente o arquivo appsettings.json. Para obter instruções, consulte [SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="modules-that-use-unit-of-measure-settings"></a>Módulos que usam configurações de unidade de medida

Os módulos que usam as configurações de unidade de medida incluem os módulos de caixa de compra, lista de desejos, carrinho, ícone de carrinho, contêiner de resultados da pesquisa, coleção de produtos, finalização da compra e detalhes da ordem.

No exemplo da ilustração a seguir, uma página de detalhes do produto (PDP) mostra a unidade de medida (**ea**) de um produto.

![Exemplo de uma PDP que mostra a unidade de medida.](./media/Productunit-PDP.png)

No exemplo da ilustração a seguir, um módulo de coleção de produtos mostra a unidade de medida (**ea**) de um produto.

![Exemplo de um módulo de coleção de produtos que mostra a unidade de medida.](./media/Productunit-productcollection.png)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de carrinho](add-cart-module.md)

[Módulo de caixa de compra](add-buy-box.md)

[Páginas e módulos de gerenciamento de contas](account-management.md)

[SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
