---
title: Módulo de seletor de sites
description: Este tópico abrange o módulo de seletor de sites e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/04/2022
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
ms.openlocfilehash: a1954f6b2fea35d5138218e6a2a23ab1fd04c8fc
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8710294"
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

O módulo de seletor de sites pode ser adicionado ao slot **Seletor de sites** do [módulo de cabeçalho](author-header-module.md). Depois que um módulo de seletor de sites for adicionado, você poderá definir as opções de cabeçalho e site do módulo. Geralmente, um módulo de cabeçalho está em um fragmento de cabeçalho que pode ser compartilhado entre páginas de comércio eletrônico de um site. 

Para adicionar o módulo do seletor de sites a um módulo de cabeçalho, siga estas etapas.

1. No slot **Seletor de sites** do módulo de cabeçalho do fragmento de cabeçalho, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Selecionar módulos**, adicione um módulo **Seletor de módulos** e, em seguida, selecione **OK**.
1. No painel de propriedades do **Seletor de sites**, selecione **Adicionar lista de opções de site**. Uma opção de **Lista de opções de site** editável é exibida.
1. Selecione **Lista de opções de site**. A caixa de diálogo **Lista de opções de site** é exibida.
1. Em **Nome do site**, insira o texto do nome do site que será mostrado na lista suspensa do seletor de sites.
1. Em **URL de redirecionamento do site**, selecione **Adicionar um link**. O painel de submenu **Adicionar um link** é exibido.
1. No painel **Adicionar um link**, selecione **Página personalizada** e, em seguida, selecione **Avançar**.
1. Na lista URL do site, selecione a URL com o caminho que você criou ao adicionar o canal ao site (por exemplo, `www.adventure-works.com/fr-ca`) e selecione **Aplicar**.
1. Selecione **OK**.
1. Selecione **Salvar** e **Finalizar edição**.
1. Selecione **Publicar** para publicar a página.

No exemplo a seguir, o módulo de seletor de sites foi adicionado ao slot **Selecionador de sites** de um módulo de cabeçalho que está em um fragmento de cabeçalho chamado **HeaderContainer**.

![Exemplo de um módulo de seletor de sites em um fragmento de cabeçalho.](./media/ecommerce-sitepicker-2.png)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de cabeçalho](author-header-module.md)

[Módulo de trilha de navegação](add-breadcrumb.md)

[Módulos de menu de navegação](nav-menu-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
