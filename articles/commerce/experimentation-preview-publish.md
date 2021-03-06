---
title: Visualizar e publicar um experimento
description: Este tópico descreve como visualizar e publicar um experimento desde o Dynamics 365 Commerce.
author: sushma-rao
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 52ca23e5aaeb7058853fed2241d5804180fa7f8d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798954"
---
# <a name="preview-and-publish-an-experiment"></a>Visualizar e publicar um experimento

Este tópico descreve como visualizar e publicar seu experimento no Dynamics 365 Commerce depois de [conectar seu experimento e editar suas variações](experimentation-connect-edit.md). O diagrama a seguir mostra todas as etapas envolvidas na configuração e execução de um experimento em um site de comércio eletrônico no Dynamics 365 Commerce. Etapas adicionais são abordadas em tópicos separados.

[ ![Jornada do usuário na experimentação - visualizar e publicar](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)

## <a name="preview-your-experiment-variations"></a>Visualizar suas variações de experimento
Você pode visualizar suas variações e continuar editando-as até que tenham a aparência desejada.

Para visualizar suas variações de experimento no construtor de sites do Commerce, siga estas etapas.

1. No menu suspenso de variações, abaixo da barra de comandos, selecione o conteúdo a ser visualizado. 
1. Na barra de comandos, selecione **Visualização**. Será exibida uma visualização da aparência do conteúdo quando publicado.
1. Para visualizar uma variação diferente, selecione-a no menu suspensa de variação e selecione **Visualização** novamente.

## <a name="publish-your-experiment"></a>Publicar seu experimento
Se você não estiver usando um grupo de publicação para agendar quando o experimento ficará ativo e desejar publicar imediatamente, selecione **Publicar** na barra de comandos. Todas as variações que pertencem ao experimento serão publicadas.
    
> [!IMPORTANT]
> Se a página tiver uma URL não publicada, você deverá primeiro publicar a URL ou ela não ficará visível para os usuários do site. Para obter detalhes, consulte [Salvar, visualizar, e publicar uma página](save-preview-publish-page.md).
    
### <a name="use-publish-groups-to-schedule-when-your-experiment-goes-live"></a>Usar grupos de publicação para agendar quando o experimento ficará ativo
As variações criadas no construtor de sites podem ser agendadas para publicação usando um grupo de publicação. Em um grupo de publicações, você pode conectar uma página ou fragmento ao seu experimento selecionando **Experimentos** no painel de navegação esquerdo. Você também pode fazer isso selecionando **Páginas** ou **Fragmentos** e seguindo as instruções em [Conectar um experimento e editar variações](experimentation-connect-edit.md). Para obter informações sobre grupos de publicação, consulte [Trabalhar com grupos de publicação](publish-groups.md).

Ao usar grupos de publicação com experimentos, há algumas considerações importantes a serem observadas.
- Quando você adiciona uma página ou um fragmento com um experimento em execução em um grupo de publicação, o experimento será removido da página ou fragmento no grupo de publicação.
- Os experimentos conectados a páginas em um site ativo não estão disponíveis para páginas em grupos de publicação e vice-versa. Da mesma forma, as páginas com experimentos em execução em um site ativo não estão disponíveis para outros experimentos em grupos de publicação e vice-versa.
- Quando você publica ou planeja um grupo de publicação, todo o conteúdo do grupo de publicação é publicado, independentemente de haver um experimento associado ao grupo de publicação.
- Como um grupo de publicação continua a persistir após ser publicado em um site ativo, os experimentos no grupo de publicação também persistirão. Portanto, você não poderá associar outros experimentos à mesma página ou fragmento. Para evitar essa limitação, exclua todos os grupos de publicações com experimentos persistentes. Da mesma forma, se você deseja excluir um experimento em um site ativo que também existe em um grupo de publicação, exclua-a do grupo de publicação primeiro.

## <a name="previous-step"></a>Etapa anterior
[Conectar e editar um experimento](experimentation-connect-edit.md)

## <a name="next-step"></a>Próxima etapa
[Executar e monitorar um experimento](experimentation-run-monitor.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]