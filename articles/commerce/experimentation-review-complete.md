---
title: Promover uma variação e concluir um experimento
description: Este artigo descreve como promover uma variação bem-sucedida e concluir um experimento no Dynamics 365 Commerce.
author: sushma-rao
ms.date: 06/07/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: 3e9a978551622bbb14d9213f607d9dfabe42672a
ms.sourcegitcommit: ddcb62bb5fbf26a1178c2bb1aec45a3d2362339e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2022
ms.locfileid: "8942728"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a>Promover uma variação e concluir um experimento

Este artigo descreve como promover a variação que produziu os melhores resultados no seu experimento e como concluí-lo. O diagrama a seguir mostra todas as etapas envolvidas na configuração e execução de um experimento em um site de comércio eletrônico no Dynamics 365 Commerce. Etapas adicionais são abordadas em artigos separados.

[ ![Jornada do usuário na experimentação - Análise e conclusão.](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)

Depois de [executar seu experimento](experimentation-run-monitor.md) e retirar dados suficientes para determinar qual variação você deseja usar no seu site ativo, promova a variação e encerre o experimento.

## <a name="promote-a-variation"></a>Promover uma variação
Use os dados e a análise relacionados ao experimento no serviço de terceiros para decidir que variação produziu os melhores resultados. Você poderá então promovê-la substituindo o conteúdo atual no site ativo com a variação vencedora para que fique disponível para todos os usuários do seu site, faça o seguinte.

Para promover a variação vencedora, siga estas etapas. 

1. No construtor de sites do Commerce, selecione **Experimentos** no painel de navegação esquerdo e selecione o experimento.
1. Na barra de comando, selecione **Concluir experimento**.
1. Na caixa de diálogo **Completar o experimento**, selecione **Analisar os dados do experimento**. O serviço de terceiros abre onde você pode validar as métricas e determinar qual variação teve o melhor desempenho.
1. Na caixa de diálogo **Completar o experimento** no construtor de sites, selecione a variação vencedora e, em seguida, selecione **Avançar**.
1. Abra o serviço de terceiros e interrompa o experimento.
1. No construtor de sites, selecione **Completar** para substituir a página ativa original e publicar a variação vencedora para que ela fique disponível para todos os usuários do seu site. 

> [!NOTE]
> Se você optar por manter a página ativa atual e não publicar uma variação, selecione **Republicar a página original**.

## <a name="delete-your-experiment"></a>Excluir seu experimento
Embora não seja necessário excluir um experimento concluído no Commerce, você pode optar por excluí-lo para economizar espaço ou limpar o espaço de trabalho. 

Para excluir um experimento concluído no construtor de sites do Commerce, siga estas etapas.

1. Selecione **Experimentos** no painel de navegação esquerdo e selecione o experimento. 
    > [!NOTE]
    > Se o experimento ainda estiver ativo, interrompa-o no serviço de terceiros antes de prosseguir.
1. Na barra de comando, selecione **Cancelar publicação** para remover o conteúdo da variação do site ativo.
1. Selecione **Excluir** para excluir o experimento.

## <a name="previous-step"></a>Etapa anterior
[Executar e monitorar um experimento](experimentation-run-monitor.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
