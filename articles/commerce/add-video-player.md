---
title: Módulo de reprodutor de vídeo
description: Este tópico abrange os módulos de exibição e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 12/02/2019
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1c78583f39dbacdc7b38e89c33e67ae23731bf8a
ms.sourcegitcommit: 96bfc20eb748f4090a2b5e1ff9f54997d5a5d359
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2019
ms.locfileid: "2885892"
---
# <a name="video-player-module"></a>Módulo de reprodutor de vídeo

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de exibição e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Os módulos de reprodução de vídeo são usados para oferecer suporte a reprodução de vídeo. Dois módulos de reprodução de vídeo são fornecidos no kit inicial de armazenamento: o módulo de reprodutor de vídeo do ambiente e o módulo de reprodutor de vídeo. Ambos reprodutores oferecem suporte ao tipo de mídia .mp4.

## <a name="ambient-video-player-module"></a>Módulo de reprodutor de vídeo ambiente

O módulo de reprodutor de vídeo de ambiente oferece suporte a vídeos informacionais curtos. Deve ser usado para vídeos com menos de cinco segundos. Este reprodutor oferece suporte a funcionalidades de reprodução de vídeo limitado, como rodar e pausar.

### <a name="examples-of-ambient-video-player-modules-in-e-commerce"></a>Exemplos de módulos de reprodutor de vídeo de ambiente no comércio online

- Vídeos informacionais curtos que destacam novos produtos na página inicial
- Vídeos informacionais curtos que destacam recursos de produto em uma página de detalhes de produto

### <a name="ambient-video-player-module-properties"></a>Propriedades de módulo de reprodutor de vídeo ambiente

| Nome da propriedade     | Alíquota                 | Descrição |
|-------------------|-----------------------|-------------|
| Reprodução automática          | **Verdadeiro** ou **Falso** | Quando o valor é definido como **Verdadeiro**, o vídeo é executado automaticamente. |
| Ativar Mudo              | **Verdadeiro** ou **Falso** | Quando o valor é definido como **Verdadeiro**, o áudio fica no mudo. Para esse reprodutor, o valor padrão é **Verdadeiro**. No navegador do Google Chrome, vídeos reproduzidos automaticamente são mudos por padrão e o áudio é reproduzido apenas se o usuário reproduzir manualmente o vídeo. |
| Loop              | **Verdadeiro** ou **Falso** | Quando o valor é definido como **Verdadeiro**, o vídeo é repetido em um loop. |
| Mídia             |  Caminho e nome do arquivo de vídeo | O arquivo de vídeo é reproduzido pelo reprodutor de vídeo. |
| Controles de reprodução | **Verdadeiro** ou **Falso** | Quando o valor é definido como **Verdadeiro**, o botão reproduzir/pausa será mostrado no vídeo. Se o valor for definido como **Falso**, o botão de reprodução/pausa não é exibido, mas os usuários ainda podem pausar e retomar o vídeo usando o teclado. |

## <a name="video-player-module"></a>Módulo de reprodutor de vídeo

O módulo de reprodução de vídeo pode ser usado para exibir vídeos em um site comercial online. Oferece suporte a todas as funcionalidades de reprodução, como reproduzir, pausar, modo tela cheia e legendas. O módulo de exibição de vídeo também oferece suporte à personalização de legendas atender aos padrões de acessibilidade da Microsoft. Por exemplo, você pode personalizar o tamanho da fonte e a cor de plano de fundo.

O módulo player de vídeo também oferece suporte a faixas de áudio secundárias. Quando um vídeo é carregado, uma trilha de áudio secundária também pode ser carregada. O módulo de reprodutor de vídeo pode reproduzir a trilha de áudio secundária se um usuário selecioná-la.

### <a name="examples-of-video-player-modules-in-e-commerce"></a>Exemplos de módulos de reprodutor de vídeo no comércio online

- Vídeos instrutivas sobre a página de detalhes de produto ou páginas de marketing
- Vídeos promocionais ou vídeos sobre políticas em qualquer página de marketing
- Vídeos de marketing que destacam recursos de produto em páginas de detalhes de produto ou páginas de marketing

### <a name="video-player-module-properties"></a>Propriedades de módulo de reprodutor de vídeo

| Nome da propriedade         | Alíquota                               | Descrição |
|-----------------------|-------------------------------------|-------------|
| Reprodução automática             | **Verdadeiro** ou **Falso**               | Quando o valor é definido como **Verdadeiro**, o vídeo é executado automaticamente. |
| Ativar Mudo                  | **Verdadeiro** ou **Falso**               | Quando o valor é definido como **Verdadeiro**, o áudio fica no mudo. Para esse reprodutor, o valor padrão é **Falso**. No navegador do Chrome, vídeos reproduzidos automaticamente são mudos por padrão e o áudio é reproduzido apenas se o usuário reproduzir manualmente o vídeo. |
| Loop                  | **Verdadeiro** ou **Falso**               | Quando o valor é definido como **Verdadeiro**, o vídeo é repetido em um loop. |
| Mídia                 | Caminho e nome do arquivo de vídeo | O arquivo de vídeo é reproduzido pelo reprodutor de vídeo. |
| Controles de reprodução     | **Verdadeiro** ou **Falso**               | Quando o valor é definido como **Verdadeiro**, o botão reproduzir/pausa será mostrado no vídeo. Se o valor for definido como **Falso**, o botão de reprodução/pausa não é exibido, mas os usuários ainda podem pausar e retomar o vídeo usando o teclado. |
| Reproduzir em tela cheia       | **Verdadeiro** ou **Falso**               | Quando o valor é definido como **Verdadeiro**, o vídeo é exibido no modo tela cheia. |
| Controles              | **Verdadeiro** ou **Falso**               | Quando o valor é definido como **Verdadeiro**, os controles são exibidos. Esses controles incluem botões de reprodução e pausa, um indicador de progresso e legendas. |
| Ocultar borda     | **Verdadeiro** ou **Falso**               | Uma vídeo pode ter uma borda. Quando o valor desta propriedade é definido como **Verdadeiro**, a borda fica oculta. |
| Nível de máscara            | Um número de **0** a **100** | A máscara aplicada ao vídeo para estilo. |
| Estilo de ícone de tela cheia | **Quadrado** ou **Seta**             | O estilo do ícone de tela cheia exibido no reprodutor de vídeo. |

## <a name="add-a-video-player-module-to-a-page"></a>Adicionar um módulo de reprodutor de vídeo à página

Para adicionar um módulo de reprodução de vídeo a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Criar um modelo da página chamado **modelo de reprodutor de vídeo**.
1. No slot **Principal** da página padrão, adicione um módulo de contêiner.
1. No módulo de contêiner, adicione os módulos de reprodutor de vídeo e reprodutor de vídeo ambiente.
1. Faça check-in do modelo e publique-o.
1. Use o modelo de reprodução de vídeo que criou para criar uma página nomeada **página do reprodutor de vídeo**.
1. No slot **Principal** da nova página, adicione um módulo de reprodução de vídeo ambiente.
1. Nas configurações do módulo de reprodução de vídeo ambiente, acesse **Mídia** e carregue um arquivo de vídeo. Você pode alterar a **Reprodução automática**, **Loop** e outras propriedades, se necessário.
1. Salve e exiba a página.
1. No slot **Principal** da nova página, adicione um módulo de reprodução de vídeo.
1. Nas configurações do módulo de reprodução de vídeo, acesse **Mídia** e carregue um arquivo de vídeo.
1. Salve e exiba a página. Você deve ver ambos módulos de vídeo na página. Você pode alterar as configurações adicionais para personalizar o comportamento de cada módulo.
1. Insira a página e publique-a.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo de alerta](add-alert.md)

[Módulo de carrossel](add-carousel.md)

[Módulo de bloco de conteúdo sofisticado](add-content-rich-block.md)

[Módulo de posicionamento de conteúdo](add-content-placement-modules.md)

[Módulo de recurso](add-feature-module.md)

[Módulo de hero](add-hero-module.md)
