---
title: Promover uma variação e concluir um experimento
description: Este tópico descreve como promover uma variação bem-sucedida e concluir um experimento no Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 2e011f10e908d6a2efe2e928fc5e0abc7659cb8b
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930136"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a>Promover uma variação e concluir um experimento

Este tópico descreve como promover a variação que produziu os melhores resultados no seu experimento e como concluí-lo. O diagrama a seguir mostra todas as etapas envolvidas na configuração e execução de um experimento em um site de comércio eletrônico no Dynamics 365 Commerce. Etapas adicionais são abordadas em tópicos separados.

[ ![Jornada do usuário na experimentação - análise e conclusão](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)

Depois de [executar seu experimento](experimentation-run-monitor.md) e retirar dados suficientes para determinar qual variação você deseja usar no seu site ativo, promova a variação e encerre o experimento.

## <a name="promote-a-variation"></a>Promover uma variação
Use os dados e a análise relacionados ao experimento no serviço de terceiros para decidir que variação produziu os melhores resultados. Para substituir o conteúdo atual no site ativo com a variação vencedora para que fique disponível para todos os usuários do seu site, faça o seguinte. 

1. Vá para a guia **Experimentos** no construtor de sites e selecione o experimento.
1. Selecione **Experimento completo** na barra superior.
1. No menu de diálogo **Completar o experimento**, selecione **Analisar os dados do experimento**. O serviço de terceiros abre onde você pode validar as métricas e determinar qual variação teve o melhor desempenho.
1. No menu do diálogo **Completar o experimento** no construtor de sites, selecione a variação vencedora e, em seguida, selecione **Avançar**.
1. Abra o serviço de terceiros e interrompa o experimento.
1. No construtor de sites, selecione **Completar** para substituir a página ativa original e publicar a variação vencedora para que ela fique disponível para todos os usuários do seu site. 

> [!NOTE]
> Se você optar por manter a página ativa atual e não publicar uma variação, selecione **Republicar a página original**.

## <a name="delete-your-experiment"></a>Excluir seu experimento
Embora não seja necessário excluir um experimento concluído no Commerce, você pode optar por excluí-lo para economizar espaço ou limpar o espaço de trabalho. Para excluir um experimento, faça o seguinte.

1. Vá para a guia **Experimentos** no construtor de sites e selecione o experimento. 
    > [!NOTE]
    > Se o experimento ainda estiver ativo, interrompa-o no serviço de terceiros antes de prosseguir.
1. Selecione **Cancelar publicação** na barra de comandos para remover o conteúdo da variação do site ativo.
1. Selecione **Excluir** na barra de comandos para excluir o experimento.

## <a name="previous-step"></a>Etapa anterior
[Executar e monitorar um experimento](experimentation-run-monitor.md)
