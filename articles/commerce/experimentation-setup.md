---
title: Configurar um experimento
description: Este tópico descreve como configurar um experimento em um serviço de terceiros.
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
ms.openlocfilehash: 9976ca461f7e988c32b81565fa2d084709e5ad6e
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792495"
---
# <a name="set-up-an-experiment"></a>Configurar um experimento

Depois de [definir uma hipótese e determinar quais métricas de sucesso você deseja usar](experimentation-identify.md), você precisará configurar seu experimento no serviço de terceiros. O diagrama a seguir mostra todas as etapas envolvidas na configuração e execução de um experimento em um site de comércio eletrônico no Dynamics 365 Commerce. Etapas adicionais são abordadas em tópicos separados.

[ ![Usuário de teste de experimentação - configuração](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)


## <a name="set-up-your-experiment-in-the-third-party-service"></a>Configurar seu experimento no serviço de terceiros
Você já deve ter escolhido o serviço de terceiros para ser executado e monitorar seu experimento e configurar o conector de experimentação. Esses pré-requisitos estão listados em [Experimentação no Dynamics 365 Commerce](experimentation-overview.md).

Siga as etapas necessárias para criar seu experimento no serviço de terceiros. Se o conector estiver configurado corretamente, a lista completa de experimentos configurados no serviço de terceiros aparecerá no construtor de sites do Commerce em cerca de 5 minutos.

## <a name="set-up-your-success-metrics"></a>Configurar métricas de sucesso
Cada experimento precisa de métricas para medir o impacto das variações e para validar a hipótese. Siga as etapas abaixo para habilitar o cálculo de métricas no serviço de terceiros usando eventos de telemetria ativos do Dynamics 365 Commerce.

Para configurar suas métricas de êxito, siga estas etapas:

1. No construtor de sites do Commerce, selecione **Páginas** no painel de navegação esquerdo e, em seguida, selecione a página na qual deseja retirar métricas. 
1. Vá para a seção **IDs de evento para rastrear** no painel de propriedades à direita da página ou do módulo que você deseja rastrear.
1. Selecione **Exibir**. Uma lista de todas as IDs de evento é exibida. Copie o evento que você deseja rastrear e cole a chave de evento no local designado no serviço de terceiros. Se você precisar de mais de um evento, copie as chaves uma de cada vez. 
    - Para saber como exibir todos os atributos e eventos disponíveis, incluindo exibições de página e controle de receita, consulte [Eventos de componente do Commerce para diagnóstico e solução de problemas](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).
1. Execute outras etapas para controlar as métricas necessárias no serviço de terceiros.

## <a name="previous-step"></a>Etapa anterior
[Identificar uma hipótese e determinar as métricas para um experimento](experimentation-identify.md) 


## <a name="next-step"></a>Próxima etapa
[Conectar e editar um experimento](experimentation-connect-edit.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]