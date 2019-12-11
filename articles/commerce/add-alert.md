---
title: Módulo de alerta
description: Este tópico abrange os módulos de alerta e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 82138dd7f0934f732215f67a3726638eb87075d4
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785343"
---
# <a name="alert-module"></a>Módulo de alerta

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de alerta e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Um módulo de alerta é usado para mostrar mensagens informativas em linha em uma página. Os módulos de alerta permitem uma mensagem de texto e um link. Eles podem ser usados para mostrar promoções em todo o site que aparecem em todas as páginas de um site de comércio eletrônico. 

Os módulos de alerta são direcionados por dados do sistema de gerenciamento de conteúdo (CMS) e podem ser colocados em qualquer página.

## <a name="examples-of-alert-modules-in-e-commerce"></a>Exemplos de módulos de alerta no comércio online

Os módulos de alerta podem ser usados no cabeçalho do site para indicar promoções ou mensagens em todo o site. Eis alguns exemplos:

"A venda anual termina em 10 dias"

"Economize bastante com a venda na volta às aulas. Compre agora."

## <a name="alert-module-properties"></a>Propriedades de módulo de alerta

| Nome da propriedade  | Alíquota                              | Descrição |
|----------------|------------------------------------|-------------|
| Texto           | Texto                               | A mensagem de texto que aparece no módulo de alerta. |
| Alinhamento de texto | **Direito**, **Esquerdo** ou **Centro** | Um valor que define como o texto é alinhado no módulo de alerta. |
| Ignorar alerta  | **Verdadeiro** ou **Falso**              | Se o valor estiver definido como **Verdadeiro**, o cliente poderá descartar o alerta. |
| Vincular           | URL                                | A URL para um link opcional. |

## <a name="add-an-alert-module-to-a-page"></a>Adicionar um módulo de alerta a uma página 

Para adicionar um módulo de alerta a uma página e definir as propriedades necessárias, siga estas etapas.

1. Criar um modelo da página chamado **modelo de alerta**.
1. No slot **Principal** da página padrão, adicione um módulo de alerta.
1. Faça check-in do modelo e publique-o. 
1. Use o modelo de alerta que criou para criar uma página nomeada **página de alerta**. 
1. No slot **Principal** da nova página, adicione um módulo de alerta.
1. Nas configurações do módulo de alerta, insira o texto do alerta. É possível editar as outras propriedades se desejar personalizar ainda mais o módulo de alerta.
1. Salve e exiba a página. Na parte superior da página, você verá um alerta com o texto que você adicionou.
1. Insira a página e publique-a. 

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo de carrossel](add-carousel.md)

[Módulo de bloco de conteúdo sofisticado](add-content-rich-block.md)

[Módulo de posicionamento de conteúdo](add-content-placement-modules.md)

[Módulo de recurso](add-feature-module.md)

[Módulo de hero](add-hero-module.md)

[Módulo de reprodutor de vídeo](add-video-player.md)
