---
title: Módulo do menu de navegação
description: Este tópico abrange os módulos do menu de navegação e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/01/2020
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
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: b0e8168ca9ec9ca68011650a73cc09983deca645
ms.sourcegitcommit: 765056b5dc1d0a8c27e56ff2cbd310ad3349ff09
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2020
ms.locfileid: "4055728"
---
# <a name="navigation-menu-module"></a>Módulo do menu de navegação

[!include [banner](includes/banner.md)]

Este tópico abrange os módulos do menu de navegação e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

A finalidade principal dos módulos do menu de navegação é permitir que os usuários do site naveguem por produtos e páginas do site de acordo com a hierarquia de navegação de canal definida na matriz do Dynamics 365 Commerce. Os itens configurados em um módulo de menu de navegação aparecem como uma navegação de cabeçalho de site. Os módulos do menu de navegação também dão suporte a itens de menu estático que se vinculam a outras páginas em um site de comércio eletrônico.

O módulo do menu de navegação pode ser adicionado ao módulo de cabeçalho de uma página. Por padrão, no tema Fabrikam, o menu de navegação mostra dois níveis. Por padrão, no tema Início, o menu de navegação mostra três níveis. Para alterar para o número de níveis, é necessário ter uma extensão de exibição no tema.

A ilustração a seguir mostra um exemplo de um menu de navegação para o site da Fabrikam com dois níveis de hierarquia de categoria e alguns itens de menu estático.
![Exemplo de um módulo menu de navegação](./media/ecommerce-header.png)

## <a name="navigation-menu-module-properties"></a>Propriedades do módulo do menu de navegação

| Nome da propriedade             | Alíquota                 | descrição |
|---------------------------|-----------------------|-------------|
| Origem                  | **Varejo** , **Criação manual** , **Varejo e criação manual** | O valor **Varejo** permite que a hierarquia de navegação de canal da matriz do Commerce seja exibida no menu de navegação. O valor **Criação manual** permite que os itens de menu estático sejam organizados. O valor **Criação manual e de varejo** permite uma combinação de ambos. |
| Mostrar imagens da categoria | **Verdadeiro** ou **Falso**    | Quando habilitada, essa propriedade exibe imagens de categoria no menu de navegação, conforme definido na matriz do Commerce para cada categoria. Adicionado ao Commerce Release 10.0.14. |
| Habilitar menu de navegação de vários níveis | **Verdadeiro** ou **Falso** | Quando esta propriedade estiver habilitada, o menu de navegação poderá mostrar vários níveis da hierarquia de navegação. Esse recurso só está disponível na versão 10.0.15 do Dynamics 365 Commerce. |
| Número de níveis | inteiro | Essa propriedade define os números de níveis que deverão ser mostrados se a propriedade **Habilitar menu de navegação de vários níveis** estiver definida como **Verdadeira**. |
| Item de menu estático| Matriz de valores| Os itens de menu estático que associam um nome de item de menu a um link para uma página de site estática. Você pode criar itens de menu abaixo de outros itens de menu. Por padrão, os menus estáticos aparecem no nível raiz e serão acrescentados à hierarquia de navegação de canal, caso exista. |
| Mostrar menu raiz | **Verdadeiro** ou **Falso** | Quando essa propriedade estiver habilitada, o menu de navegação poderá ser definido em uma raiz personalizada (por exemplo, **Compre agora** ). Esse recurso só está disponível na versão 10.0.15 do Dynamics 365 Commerce. |
| Menu raiz | cadeia de caracteres | Essa propriedade pode ser usada para definir texto para uma raiz personalizada se a propriedade **Mostrar menu raiz** estiver definida como **Verdadeira**. |

A ilustração a seguir mostra um exemplo de uma imagem de categoria exibida no menu de navegação do site da Fabrikam.
![Exemplo de um módulo de meu de navegação com imagens de categoria](./media/ecommerce-categoryimages.PNG)

## <a name="add-a-navigation-menu-module-to-a-header-module"></a>Adicionar um módulo de menu de navegação a um módulo de cabeçalho

Para obter detalhes sobre como adicionar um módulo de menu de navegação a um módulo de cabeçalho, consulte [Módulo de cabeçalho](author-header-module.md).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de trilha de navegação](add-breadcrumb.md)

[Módulo de seletor de site](site-selector.md)

[Módulo de caixa de compra](add-buy-box.md)

[Compatível com cookies](cookie-compliance.md)

[Módulo de cabeçalho](author-header-module.md)
