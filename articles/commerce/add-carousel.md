---
title: Módulo de carrossel
description: Este tópico abrange os módulos de carrossel e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: c2c5adc8ab2e0330f7b07e5153fd8332ab0203e5
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785228"
---
# <a name="carousel-module"></a>Módulo de carrossel

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de carrossel e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Um módulo de carrossel é usado para colocar vários itens promocionais em um carrossel que os clientes possam navegar. É um módulo de contêiner especial que hospeda outros módulos. Por exemplo, um varejista pode usar um módulo de carrossel em uma home page para exibir vários novos produtos ou promoções.

Você pode adicionar módulos de hero e recurso dentro de um módulo de carrossel. As propriedades do módulo de carrossel definem como esses módulos são renderizados.

## <a name="examples-of-carousel-modules-in-e-commerce"></a>Exemplos de módulos de carrossel no comércio online

- Um carrossel que possui vários módulos promocionais pode ser usado em uma home page.
- Um carrossel que possui vários módulos promocionais pode ser usado em uma página de detalhes do produto.
- Um carrossel pode ser usado em qualquer página de marketing para promover várias promoções ou produtos.

## <a name="carousel-module-properties"></a>Propriedades do módulo de carrossel

| Nome da propriedade             | Alíquota                                | Descrição |
|---------------------------|--------------------------------------|-------------|
| Reprodução automática                  | **Verdadeiro** ou **Falso**                | Se o valor estiver definido como **Verdadeiro**, a transição entre os itens dentro no carrossel ocorrerá automaticamente. Se o valor estiver definido como **Falso**, nenhuma transição ocorrerá, a menos que o cliente use o teclado ou o mouse para passar de um item para o próximo. |
| Intervalo de transição de slides | Um valor em segundos                   | O intervalo para transições entre itens. |
| Animação de transição      | **Slide** ou **Fade**                | O efeito de transição. |
| Largura                     | **Ajustar contêiner** ou **Preencher tela** | Se o valor estiver definido como **Ajustar contêiner**, os itens dentro do carrossel serão restritos à largura do carrossel. Se o valor estiver definido como **Preencher tela**, os itens não serão restritos à largura do carrossel, mas poderão entrar no modo de tela cheia. É possível alterar o valor para obter o layout desejado. |

## <a name="add-a-carousel-module-to-a-page"></a>Adicionar um módulo de carrossel a uma página

Para adicionar um módulo de carrossel a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Criar um modelo da página chamado **modelo de carrossel**.
1. No slot **Principal** da página padrão, adicione um módulo de carrossel.
1. Adicione um módulo de hero ao módulo de carrossel.
1. Adicione um módulo de recurso ao módulo de carrossel.
1. Faça check-in do modelo e publique-o. 
1. Use o modelo de carrossel que criou para criar uma página nomeada **página do carrossel**.
1. No slot **Principal** da nova página, adicione um módulo de carrossel.
1. Defina a propriedade **Largura** do módulo de carrossel como **Preencher tela**. 
1. Defina a propriedade **Animação de transição** como **Slide**.
1. Adicione um módulo de hero ao módulo de carrossel.
1. No módulo de hero, adicione uma imagem e um cabeçalho e selecione **Salvar**.
1. Adicione um módulo de recurso ao módulo de carrossel.
1. No módulo de recurso, adicione uma imagem, um cabeçalho e um parágrafo de texto.
1. Salve e exiba a página. A página deve mostrar um carrossel que possui dois módulos (um módulo de hero e um módulo de recurso). Você pode alterar propriedades adicionais para os módulos de carrossel, hero e recurso, para obter o efeito desejado.
1. Insira a página e publique-a.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo de alerta](add-alert.md)

[Módulo de bloco de conteúdo sofisticado](add-content-rich-block.md)

[Módulo de posicionamento de conteúdo](add-content-placement-modules.md)

[Módulo de recurso](add-feature-module.md)

[Módulo de hero](add-hero-module.md)

[Módulo de reprodutor de vídeo](add-video-player.md)
