---
title: Módulo de reprodutor de vídeo
description: Este tópico abrange os módulos de exibição e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e94658eed12b12d6666e63d2c06b86646c81a120
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025634"
---
# <a name="video-player-module"></a>Módulo de reprodutor de vídeo


[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de exibição e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

O módulo de player de vídeo é usado para dar suporte à reprodução de vídeo. Ele pode ser adicionado a qualquer página, desde que o conteúdo de vídeo seja carregado e disponibilizado no sistema de gerenciamento de conteúdo (CMS). O módulo de player de vídeo oferece suporte para o tipo de mídia. mp4.

## <a name="video-player-module"></a>Módulo de reprodutor de vídeo

O módulo de reprodução de vídeo pode ser usado para exibir vídeos em um site comercial online. Ele é compatível com todas as funcionalidades de reprodução, como reproduzir, pausar, modo tela cheia, descrições de áudio e legendas. O módulo de exibição de vídeo também oferece suporte à personalização de legendas atender aos padrões de acessibilidade da Microsoft. Por exemplo, você pode personalizar o tamanho da fonte e a cor de plano de fundo.

O módulo player de vídeo também oferece suporte a faixas de áudio secundárias. Quando um vídeo é carregado no CMS, uma trilha de áudio secundária também pode ser carregada. O módulo de reprodutor de vídeo pode reproduzir a trilha de áudio secundária se um usuário selecioná-la.

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
| Reproduzir em tela cheia       | **Verdadeiro** ou **Falso**               | Quando o valor é definido como **Verdadeiro**, o vídeo é exibido no modo tela cheia. |
| Disparador da pausa de reprodução    | **Verdadeiro** ou **Falso**               | Quando o valor é definido como **Verdadeiro**, o botão reproduzir/pausa será mostrado no vídeo. |
| Controles do player de vídeo | **Verdadeiro** ou **Falso**               | Quando o valor é definido como **Verdadeiro**, todos os controles do player de vídeo são exibidos. Esses controles incluem botões de reprodução e pausa, um indicador de progresso e opções de legenda. |
| Ocultar imagem do pôster     | **Verdadeiro** ou **Falso**               | Uma vídeo pode ter uma borda. Quando o valor desta propriedade é definido como **Verdadeiro**, a borda fica oculta. |
| Nível de máscara            | Um número de **0** a **100** | A máscara aplicada ao vídeo para estilo. |

## <a name="add-a-video-player-module-to-a-page"></a>Adicionar um módulo de reprodutor de vídeo à página

> [!NOTE] 
> Antes de criar um módulo de player de vídeo, primeiro você deve carregar um vídeo na Biblioteca de Mídia.

Para adicionar um módulo de reprodução de vídeo a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Criar um modelo da página chamado **modelo de reprodutor de vídeo**.
1. No slot **Principal** da página padrão, adicione um módulo de contêiner.
1. No módulo de contêiner, adicione os módulos de reprodutor de vídeo e reprodutor de vídeo ambiente.
1. Termine de editar o modelo e publique-o.
1. Use o modelo de player de vídeo que você criou para criar uma página chamada **página do player de vídeo**.
1. No slot **Principal** da nova página, adicione um módulo de reprodução de vídeo.
1. No painel de propriedades do módulo de player de vídeo, selecione **Adicionar um vídeo**.
1. Na caixa de diálogo **Seletor de Mídia**, selecione um vídeo e clique em **Carregar novo item de mídia**.
1. Salve e exiba a página. Você deve ver o módulo de vídeo na página. Você pode alterar outras configurações para personalizar o comportamento do módulo.
1. Termine de editar a página e publique-a.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo de faixa promocional](add-alert.md)

[Módulo do carrossel](add-carousel.md)

[Módulo de bloco de texto](add-content-rich-block.md)

[Módulo de bloco de conteúdo](add-hero-module.md)
