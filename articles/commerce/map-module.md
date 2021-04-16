---
title: Módulo do mapa
description: Este tópico abrange os módulos do módulo e descreve como configurá-los no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
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
ms.openlocfilehash: b8c3ab0653fd5e3561d0bfbe85624d912756e2be
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794178"
---
# <a name="map-module"></a>Módulo de mapa

[!include [banner](includes/banner.md)]


Este tópico abrange os módulos do módulo e descreve como configurá-los no Microsoft Dynamics 365 Commerce.

Um módulo de mapa mostra os locais de armazenamentos em um mapa interativo processado usando o [Controle da Web V8 do Bing Maps](https://docs.microsoft.com/bingmaps/v8-web-control/). Uma chave de API do Bing Maps é necessária e deve ser adicionada à página de parâmetros compartilhados na Sede do Commerce. Os módulos de mapa fornecem exibições diferentes, como estrada, aérea e Streetside, que os usuários podem selecionar para exibir os locais dos mapas. Eles também permitem interações como o zoom e o uso do local do usuário.

Um módulo de mapa trabalha em conjunto com o módulo seletor de lojas para determinar os locais geográficos das lojas que devem ser renderizados em um mapa. O seletor de armazenamento e os módulos de mapa interagem quando um usuário seleciona um armazenamento em um desses módulos em uma página do site. Os módulos de mapa podem ser estendidos para outros cenários, além da interação com os módulos do seletor de loja. No entanto, a personalização do módulo é necessária.

> [!NOTE]
> O mapa está disponível na versão 10.0.13 do Dynamics 365 Commerce.

A imagem a seguir mostra um exemplo de um módulo de mapa que é usado em uma página de locais da loja.

![Exemplo de um módulo de seletor de loja](./media/ecommerce-Storelocator.PNG)

## <a name="module-properties"></a>Propriedades do módulo

| Nome da propriedade             | Alíquota                 | descrição |
|---------------------------|-----------------------|-------------|
| Título | Texto | O título do módulo. |
| Opções de anotações: ícone padrão | Imagem | A imagem do símbolo de anotação a ser usada para lojas mostradas em um mapa. |
| Opções de anotações: ícone Ativo | Imagem | A imagem do símbolo de anotação a ser usada para uma loja selecionada em um mapa. |
| Opções de anotações: cor do ícone padrão | String de caracteres | O texto ou valor hexadecimal da cor dos símbolos de anotações em um mapa. |
| Opções de anotações: cor do ícone Ativo | String de caracteres | O texto ou valor hexadecimal da cor dos símbolos de anotações selecionados em um mapa. |
| Mostrar índice | **Verdadeiro** ou **Falso** | Se esta propriedade for definida como **verdadeira**, cada símbolo de anotação que indicar uma loja mostrará um índice. Esse índice corresponderá ao índice na exibição de lista mostrada pelo módulo seletor de loja. |

## <a name="add-allowed-mapping-urls-to-a-sites-content-security-policy-directives"></a>Adicionar URLs de mapeamento permitido a diretivas de diretiva de segurança de conteúdo de um site

Para que o módulo de mapas interaja com o Bing Mapas, você deve garantir que as seguintes URLs de mapeamento sejam permitidas conforme a política de segurança de conteúdo (CSP) do site. Essa configuração é executada na criação de site do Commerce, adicionando as URLs permitidas às várias diretivas da CSP do site (por exemplo, **img-src**). Para obter mais informações, consulte [Política de segurança de conteúdo](manage-csp.md). 

- Para a diretiva **connect-src**, adicione **&#42;.bing.com**.
- Para a diretiva **img-src**, adicione **&#42;.virtualearth.net**.
- Para a diretiva **script-src**, adicione **&#42;.bing.com, &#42;.virtualearth.net**.
- Para a diretiva **script style-src**, adicione **&#42;.bing.com**.

## <a name="add-a-map-module-to-a-page"></a>Adicionar um módulo de mapa a uma página

Para obter informações detalhadas sobre como configurar um módulo de mapa em uma página, consulte [módulo do seletor de loja](store-selector.md). 
 
## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de caixa de compra](add-buy-box.md)

[Módulo de carrinho](add-cart-module.md)

[Módulo de seletor de loja](store-selector.md)

[Gerenciar o Bing Mapas da sua organização](./dev-itpro/manage-bing-maps.md)

[Controle da Web V8 do Bing Maps](https://docs.microsoft.com/bingmaps/v8-web-control/)


[!INCLUDE[footer-include](../includes/footer-banner.md)]