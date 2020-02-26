---
title: Módulo de faixa promocional
description: Este tópico abrange os módulos de faixa promocional e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: da5e220e4578d1064eb7b627b441d3f585b3c095
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025611"
---
# <a name="promo-banner-module"></a>Módulo de faixa promocional


[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de faixa promocional e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Os módulos de faixa promocional são usados para mostrar mensagens informativas em linha em uma página. Eles podem ser usados para mostrar promoções em todo o site que aparecem em todas as páginas de um site de comércio eletrônico. 

Os módulos de faixa promocional fornecem suporte a uma mensagem de texto e um link. Se várias mensagens forem adicionadas a um módulo de faixa promocional, ele se tornará uma faixa de carrossel giratória que permite aos clientes percorrerem todas as mensagens. 

Os módulos de faixa promocional são controlados por dados do sistema de gerenciamento de conteúdo (CMS) e podem ser colocados em qualquer página.

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a>Exemplos de uso de faixas promocionais no comércio eletrônico

As faixas promocionais podem ser usadas no cabeçalho do site para mostrar promoções ou mensagens em todo o site, como nos exemplos a seguir.

"A venda anual termina em 10 dias"

"Economize bastante com a venda na volta às aulas. Compre agora."

## <a name="promo-banner-module-properties"></a>Propriedades do módulo de faixa promocional

| Nome da propriedade             | Value                              | Descrição |
|---------------------------|------------------------------------|-------------|
| Mensagens da faixa           | Textos e links                     | Uma matriz de texto e links. |
| Reprodução automática                  | **Verdadeiro** ou **Falso**              | Um valor que indica se é possível percorrer automaticamente as mensagens caso várias mensagens estejam configuradas. |
| Intervalo de transição de slides | Um número de milissegundos (ms)      | O intervalo usado para percorrer as mensagens. |
| Permitir ignorar             | **Verdadeiro** ou **Falso**              | Se o valor estiver definido como **Verdadeiro**, os clientes poderão dispensar o alerta. |
| Mostrar palheta do carrossel     | **Verdadeiro** ou **Falso**              | Um valor que indica se as palhetas do carrossel devem ser mostradas, de forma que os clientes possam percorrer vários itens de faixa manualmente. |
| Alinhamento de texto            | **Direito**, **Esquerdo** ou **Centro** | O alinhamento do texto no módulo de faixa promocional. |
| Vincular                      | URL A                              | A URL para um link opcional. |

## <a name="add-a-promo-banner-module-to-a-page"></a>Adicionar um módulo de faixa promocional a uma página 

Para adicionar um módulo de faixa promocional a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Criar um modelo da página chamado **Modelo de faixa promocional**.
1. Em **Estrutura de Tópicos de Página**, adicione um módulo **Página padrão** ao slot **Corpo**. 
1. Faça check-in do modelo e publique-o. 
1. Use o modelo que você acabou de criar para criar uma página com o nome **Página de faixa promocional**. 
1. No slot **Principal** da nova página, adicione um módulo de contêiner. 
1. No painel à direita, defina o valor da **Largura** como **Preencher Contêiner**.
1. Em **Estrutura de Tópicos de Página**, adicione um módulo de faixa promocional ao módulo de contêiner.
1. Nas configurações do módulo de faixa, adicione uma ou mais mensagens de faixa. Cada mensagem pode ter texto juntamente com um link. É possível editar as outras propriedades para personalizar ainda mais o módulo.
1. Salve e exiba a página. Na parte superior da página, você verá um alerta que mostra o texto que você adicionou.
1. Termine de editar a página e publique-a. 

> [!NOTE]
> Em geral, uma faixa promocional é usada no slot do cabeçalho da página ou em um slot de subcabeçalho.


## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo do carrossel](add-carousel.md)

[Módulo de bloco de texto](add-content-rich-block.md)

[Módulo de bloco de conteúdo](add-hero-module.md)

[Módulo de reprodutor de vídeo](add-video-player.md)
