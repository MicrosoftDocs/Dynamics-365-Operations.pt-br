---
title: Módulo de cabeçalho
description: Este tópico abrange os módulos de cabeçalho e descreve como criar cabeçalhos de página no Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: efadd19681bbb21ea5b2b469e55bc6f4b0535046
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025641"
---
# <a name="header-module"></a>Módulo de cabeçalho


[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de cabeçalho e descreve como criar cabeçalhos de página no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

No Dynamics 365 Commerce, um cabeçalho de página consiste em vários módulos, como os de cabeçalho, menu de navegação, pesquisa, faixa promocional e consentimento de cookie. 

O módulo de cabeçalho inclui um logotipo do site, links para a hierarquia de navegação, links para outras páginas do site, um símbolo de carrinho, um símbolo de lista de desejos, opções de entrada e a barra de pesquisa. Um módulo de cabeçalho é otimizado automaticamente para o dispositivo onde o site está sendo exibido (ou seja, um dispositivo móvel ou de desktop). Por exemplo, em um dispositivo móvel, a barra de navegação é recolhida em um botão **Menu** (que é conhecido ocasionalmente como *menu hambúrguer*).

## <a name="properties-of-a-header-module"></a>Propriedades de um módulo de cabeçalho

Um módulo de cabeçalho oferece suporte às propriedades **Imagem de logotipo**, **Link de logotipo** e **Links da minha conta**. 

As propriedades **Imagem de logotipo** e **Link de logotipo** são usadas para definir um logotipo na página. Para obter mais informações, consulte [Adicionar um logotipo](add-logo.md). 

A propriedade **Links da minha conta** pode ser usada para definir as páginas da conta das quais o proprietário do site quer mostrar links rápidos no cabeçalho.

## <a name="modules-that-are-available-in-a-header-module"></a>Módulos disponíveis em um módulo de cabeçalho

Os módulos a seguir podem ser usados em um módulo de cabeçalho:

- **Menu de navegação** – O menu de navegação representa a hierarquia de navegação de canal e outros links estáticos de navegação. A hierarquia de navegação de canal pode ser configurada no Dynamics 365 Commerce. O menu de navegação tem uma propriedade **Origem de Navegação** usada para especificar itens do menu de navegação do Retail Server e itens de menu estático como origem. Se itens de menu estático forem especificados como origem, poderão ser fornecidos links relativos a outras páginas do site. Os itens configurados aparecerão como navegação de cabeçalho. 
- **Pesquisa** – O módulo de pesquisa permite que os usuários insiram termos para procurar produtos. A URL da página de pesquisa padrão e os parâmetros de consulta de pesquisa devem ser fornecidos em **Configurações do Site \> Extensões**. O módulo de pesquisa tem propriedades que permitem suprimir o botão ou o rótulo de pesquisa, conforme necessário. O módulo de pesquisa também oferece suporte a opções de sugestão automática, como resultados de pesquisa por produtos, palavras-chave e categorias.

## <a name="create-a-header-module-for-a-page"></a>Criar um módulo de cabeçalho para uma página

Para criar um módulo de cabeçalho, siga estas etapas.

1. Crie um fragmento chamado **Fragmento de cabeçalho** e adicione um módulo de contêiner a ele.
1. No painel de propriedades do módulo de contêiner, defina a propriedade **Largura** como **Preencher contêiner**.
1. Adicione módulos de consentimento de cookie e de faixa promocional ao módulo de contêiner.
1. Adicione outro módulo de contêiner ao fragmento e defina a propriedade **Largura** como **Preencher contêiner**.
1. Adicione um módulo de cabeçalho ao segundo módulo de contêiner.
1. No slot **Menu de navegação** do módulo de cabeçalho, adicione um módulo de menu de navegação. 
1. No painel de propriedades do módulo de menu de navegação, configure as propriedades do módulo.
1. No slot **Pesquisa** do módulo de cabeçalho, adicione um módulo de pesquisa. 
1. No painel de propriedades do módulo de pesquisa, configure as propriedades do módulo. 
1. Salve o fragmento de página, termine de editá-lo e publique-o. 

Para ajudar a garantir que um cabeçalho aparece em cada página, siga estas etapas em cada modelo da página que é desenvolvido para o site.

1. No slot **Principal** da página padrão, adicione ao cabeçalho o fragmento de página de cabeçalho que contém o módulo de cabeçalho.
1. Salve o modelo, termine de editá-lo e publique-o.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo de contêiner](add-container-module.md)

[Comprar módulo de caixa](add-buy-box.md)

[Módulo de carrinho](add-cart-module.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de confirmação da ordem](order-confirmation-module.md)

[Módulo de cabeçalho](author-header-module.md)

[Módulo de rodapé](author-footer-module.md)
