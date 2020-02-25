---
title: Configurar um canal de call center
description: Este tópico descreve como criar um novo canal de call center no Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
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
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6ec42ab920868f541eeac54556f4f24cb1efaa3a
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002441"
---
# <a name="set-up-a-call-center-channel"></a>Configurar um canal de call center


[!include [banner](includes/banner.md)]

Este tópico descreve como criar um novo canal de call center no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

No Dynamics 365 Commerce, call center é um tipo de canal de varejo que pode ser definido no aplicativo. Definir um canal para as entidades de call center permite que o sistema vincule dados e padrões de processamento de ordens específicos a ordens de venda. Uma empresa pode definir vários canais de call center no Commerce. 

Antes de criar um novo canal de call center, verifique se você concluiu os [Pré-requisitos de configuração de canal](channels-prerequisites.md).

## <a name="create-and-configure-a-new-call-center-channel"></a>Criar e configurar um novo canal de call center

Para criar e configurar um novo canal de call center, siga estas etapas.

1. No painel de navegação, vá para **Módulos \> Canais \> Call centers \> Todos os call centers**.
1. No painel de ação, selecione **Novo**.
1. No campo **Nome**, forneça um nome para o novo canal.
1. Selecione a **Entidade legal** apropriada na lista suspensa.
1. Selecione a localização de **Depósito** apropriada na lista suspensa.
1. No campo **Cliente padrão**, forneça um cliente padrão válido.
1. No campo **Perfil de notificação por email**, forneça um perfil de notificação por email válido.
1. Forneça um código informativo de **Substituição de preço**. Talvez você precise criar um código informativo para isso primeiro.
1. Forneça um código informativo de **Código de bloqueio**. Talvez você precise criar um código informativo para isso primeiro.
1. Forneça um código informativo de **Crédito**. Talvez você precise criar um código informativo para isso primeiro.
1. Selecione **Salvar**.

A imagem a seguir mostra a criação de um novo canal de call center.

![Novo canal de call center](media/channel-setup-callcenter-1.png)

A imagem a seguir mostra um exemplo de canal de call center.

![Exemplo de canal de call center](media/channel-setup-callcenter-2.png)

## <a name="additional-channel-setup"></a>Configuração adicional do canal

Outras tarefas necessárias para a configuração do canal de call center incluem configurar métodos de pagamento e modos de entrega.

A imagem a seguir mostra opções de configuração de **Modos de entrega** e **Métodos de pagamento** na guia **Configurar**.

![Outras ações de configuração do canal de call center](media/channel-setup-callcenter-3.png)

### <a name="set-up-payment-methods"></a>Configurar métodos de pagamento

Para configurar métodos de pagamento, siga estas etapas para cada tipo de pagamento com suporte neste canal.

1. No painel de ação, selecione a guia **Configurar** e, depois, **Métodos de pagamento**.
1. No painel de ação, selecione **Novo**.
1. No painel de navegação, selecione o método de pagamento desejado.
1. Na seção **Geral**, forneça um **Nome de operação** e defina quaisquer outras configurações desejadas.
1. Defina as configurações adicionais necessárias para o tipo de pagamento.
1. No painel de ação, selecione **Salvar**.

A imagem a seguir mostra um exemplo de método de pagamento à vista.

![Exemplo de métodos de pagamento](media/channel-setup-retail-5.png)

### <a name="set-up-modes-of-delivery"></a>Configurar os modos de entrega

Você pode ver os modos de entrega configurados selecionando **Modos de entrega** na guia **Configurar** do **Painel de ação**.  

Para alterar ou adicionar um modo de entrega, siga estas etapas.

1. No painel de navegação, vá para **Módulos \> Gerenciamento de estoque \> Modos de entrega**.
1. No painel de ação, selecione **Novo** para criar um novo modo de entrega ou selecione um modo existente.
1. Na seção **Canais de varejo**, selecione **Adicionar linha** para adicionar o canal. Adicionar canais usando nós de organização em vez de adicionar cada canal individualmente pode otimizar esse processo.

A imagem a seguir mostra um exemplo de modo de entrega.

![Configurar os modos de entrega](media/channel-setup-retail-7.png)

## <a name="additional-resources"></a>Recursos adicionais

[Pré-requisitos de configuração de canal](channels-prerequisites.md)

[Funcionalidade de vendas do call center](call-center-functionality.md)

[Configurar opções de processamento de ordens do call center](set-up-order-processing-options.md)

[Catálogos do call center](call-center-catalogs.md)

[Configurar e trabalhar com alertas de fraude](set-up-fraud-alerts.md)

[Configurar programas de continuidade para call centers](set-up-continuity-program.md)
