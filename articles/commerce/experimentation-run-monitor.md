---
title: Executar e monitorar um experimento
description: Este tópico descreve como executar e monitorar um experimento em um serviço de terceiros. Também descreve como fazer alterações em variações após o início do experimento.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
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
ms.openlocfilehash: ee86a6761b27f3c08a65a2e250659cdcfd71db44
ms.sourcegitcommit: cd83f2bc0e52e13071ad306e07e4c255fc65cb03
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2020
ms.locfileid: "4410333"
---
# <a name="run-and-monitor-an-experiment"></a>Executar e monitorar um experimento

Este tópico descreve como executar e monitorar seu experimento em um aplicativo de terceiros e alterar variações, se necessário. Antes de concluir as etapas deste tópico, primeiro você precisará [publicar](experimentation-preview-publish.md) seu experimento no Commerce. 

O diagrama a seguir mostra todas as etapas envolvidas na configuração e execução de um experimento em um site de comércio eletrônico no Dynamics 365 Commerce. Etapas adicionais são abordadas em tópicos separados.

[ ![Usuário de teste de experimentação - executar e monitorar](./media/experimentation_run_monitor.svg) ](./media/experimentation_run_monitor.svg#lightbox)

Depois de publicar as variações, todas as etapas necessárias no Commerce para executar seu experimento estarão concluídas. A próxima etapa é determinar qual variação mostrar para cada usuário quando ele solicitar uma página. O serviço de terceiros faz essa determinação, mas primeiro você precisa ativar o experimento no serviço. Como as etapas para ativar um experimento variam de serviço para serviço, você precisará seguir as instruções incluídas no serviço ou provedor. Se o experimento não estiver ativado, os usuários verão apenas a versão padrão da página (nenhuma variação será exibida).

Você precisará manter a execução de experimento longa o bastante para retirar dados para resultados válidos estatisticamente. Use o serviço de terceiros para monitorar os dados relacionados à experimentação e a análise durante a execução do experimento.

## <a name="adjust-your-variations"></a>Ajustar suas variações
Se, por alguma razão, você precisar modificar suas variações, siga as etapas abaixo.

> [!IMPORTANT]
> Se você fizer alterações em um experimento ativo no Commerce ou no serviço de terceiros, seus resultados poderão ser significativamente afetados. É recomendável deixar o experimento seguir seu curso e criar um novo experimento para alterações importantes.

1. No construtor de sites do Commerce, selecione **Experimentos** no painel de navegação esquerdo e selecione o experimento. 
1. Selecione a variação que deseja atualizar no menu suspenso.
1. Faça as alterações necessárias e visualize e publique as variações. Para obter mais informações, consulte [Visualizar e publicar um experimento](experimentation-preview-publish.md).
1. Acesse o serviço de terceiros para fazer as alterações relacionadas à configuração de experimentos.
    
## <a name="previous-step"></a>Etapa anterior
[Visualizar e publicar um experimento](experimentation-preview-publish.md)

## <a name="next-step"></a>Próxima etapa
[Promover uma variação e concluir um experimento](experimentation-review-complete.md)
