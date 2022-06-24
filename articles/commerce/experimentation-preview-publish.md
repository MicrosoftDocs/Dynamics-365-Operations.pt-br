---
title: Visualizar e publicar um experimento
description: Este artigo descreve como visualizar e publicar um experimento desde o Dynamics 365 Commerce.
author: sushma-rao
ms.date: 06/08/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: 5da7a4e3c17057278d02ebd45702d1de404f0dc6
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946123"
---
# <a name="preview-and-publish-an-experiment"></a>Visualizar e publicar um experimento

Este artigo descreve como visualizar e publicar seu experimento no Dynamics 365 Commerce depois de [conectar seu experimento e editar suas variações](experimentation-connect-edit.md). O diagrama a seguir mostra todas as etapas envolvidas na configuração e execução de um experimento em um site de comércio eletrônico no Dynamics 365 Commerce. Etapas adicionais são abordadas em artigos separados.

[ ![Jornada do usuário na experimentação - Visualizar e publicar.](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)

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

### <a name="force-variations-for-testing"></a>Forçar variações para testes

Quando o experimento é dinâmico, você pode acrescentar a ID do experimento e a ID da variação à URL de página padrão de modo a forçar uma variação para fins de teste ou automação. Por exemplo, se a URL de página padrão for `https://fabrikam.com/modern/homepage`, você poderá forçar uma variação com uma URL como `https://fabrikam.com/modern/homepage?exp=18012910471|18024360464`. Você pode obter a ID do experimento e a ID da variação da sua variação de experimento na URL de visualização na experiência de **Visualização** acima.

## <a name="previous-step"></a>Etapa anterior
[Conectar e editar um experimento](experimentation-connect-edit.md)

## <a name="next-step"></a>Próxima etapa
[Executar e monitorar um experimento](experimentation-run-monitor.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
