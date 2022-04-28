---
title: Módulo de seletor de sites
description: Este tópico abrange o módulo de seletor de sites e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/06/2022
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
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: ad4d4d5f950d0631059d8f509e9e808a9106eb98
ms.sourcegitcommit: 4861ec2d3ae24cc9dd4ad3ac748fd05be3d80c70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2022
ms.locfileid: "8551685"
---
# <a name="site-picker-module"></a>Módulo de seletor de sites

[!include [banner](includes/banner.md)]

Este tópico abrange o módulo de seletor de sites e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.

Quando uma empresa tem sites diferentes em mercados, regiões e locais, os usuários do site precisam de uma maneira fácil de alternar entre sites e selecionar o site de compras preferido. Para acomodar esse cenário, o módulo de seletor de sites permite que os usuários naveguem por vários sites. Uma selecionadora de site também é recomendável quando [a detecção geográfica e o redirecionamento](geo-detection-redirection.md) foram implementados para seu site de comércio eletrônico, de forma que os clientes tenham uma forma de substituir a preferência do site que eles indicam usando o módulo de [seletor de país/região](country-region-picker-module.md). 

O módulo de seletor de sites deve ser configurado com a lista de sites (mercados, regiões ou localidades) em que os usuários do site podem navegar. A ilustração a seguir mostra um exemplo de um módulo de seletor de sites que é apresentado no cabeçalho de uma página do site.

![Exemplo de um módulo do seletor de site no cabeçalho de uma página do site.](./media/ecommerce-sitepicker.PNG)

## <a name="site-picker-module-properties"></a>Propriedades do módulo de seletor de sites

| Nome da propriedade | Valor                 | Descrição |
|---------------|-----------------------|-------------|
| Título       | Texto                  | O título do módulo. |
| Opções de site  | Nome, Imagem, URL      | Essa propriedade especifica um nome, um link para a home page do site e uma imagem opcional a ser mostrada para cada site incluído no módulo. A imagem pode ser um sinalizador ou alguma representação de mercado, região ou localidade. |

## <a name="add-a-site-picker-module-to-a-page"></a>Adicionar um módulo de seletor de sites a uma página

O módulo de seletor de sites pode ser adicionado ao slot **Seletor de sites** do [módulo de cabeçalho](author-header-module.md). Depois que um módulo de seletor de sites for adicionado, você poderá definir as opções de cabeçalho e site do módulo. Geralmente, um módulo de cabeçalho está em um fragmento de cabeçalho que pode ser compartilhado entre páginas de comércio eletrônico de um site. No exemplo a seguir, o módulo de seletor de sites foi adicionado ao slot **Selecionador de sites** de um módulo de cabeçalho que está em um fragmento de cabeçalho chamado **HeaderContainer**.

![Exemplo de um módulo de seletor de sites em um fragmento de cabeçalho.](./media/ecommerce-sitepicker-2.png)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de cabeçalho](author-header-module.md)

[Módulo de trilha de navegação](add-breadcrumb.md)

[Módulos de menu de navegação](nav-menu-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
