---
title: Módulo de seletor de site
description: Este tópico abrange o módulo de seletor de sites e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/20/2020
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
ms.openlocfilehash: a5f6f6e3ff459447aa4b3c0058b5526c9e8d1038a5d2629eefbed197012aebf0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6772219"
---
# <a name="site-selector-module"></a>Módulo de seletor de site

[!include [banner](includes/banner.md)]

Este tópico abrange o módulo de seletor de sites e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.

Quando uma empresa tem sites diferentes em mercados, regiões e locais, os usuários do site precisam de uma maneira fácil de alternar entre sites e selecionar o site de compras preferido. Para acomodar esse cenário, o módulo de seletor de sites permite que os usuários naveguem por vários sites.

O módulo de seletor de sites deve ser configurado com a lista de sites (mercados, regiões ou localidades) em que os usuários do site podem navegar.

> [!NOTE]
> O módulo de seletor de sites está disponível na versão 10.0.14 do Dynamics 365 Commerce.

A ilustração a seguir mostra um exemplo de um módulo de seletor de sites que é apresentado no cabeçalho de uma página do site.

![Exemplo de um módulo do seletor de site no cabeçalho de uma página do site.](./media/ecommerce-sitepicker.PNG)

## <a name="site-selector-module-properties"></a>Propriedades do módulo de seletor de sites

| Nome da propriedade | Alíquota                 | descrição |
|---------------|-----------------------|-------------|
| Cabeçalho       | Texto                  | O título do módulo. |
| Opções de site  | Nome, Imagem, URL      | Essa propriedade especifica um nome, um link para a home page do site e uma imagem opcional a ser mostrada para cada site incluído no módulo. A imagem pode ser um sinalizador ou alguma representação de mercado, região ou localidade. |

## <a name="add-a-site-selector-module-to-a-page"></a>Adicionar um módulo de seletor de sites a uma página

O módulo de seletor de sites pode ser adicionado ao [módulo Cabeçalho](author-header-module.md) sob o slot de seletor de sites. Depois de adicionado, você pode definir as opções de cabeçalho e site do módulo.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de cabeçalho](author-header-module.md)

[Módulo de trilha de navegação](add-breadcrumb.md)

[Módulos de menu de navegação](nav-menu-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]