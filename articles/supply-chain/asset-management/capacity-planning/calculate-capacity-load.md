---
title: Calcular a capacidade máxima
description: Este tópico explica como calcular a capacidade máxima no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c6d15861492a46ddb1222db2210f8c751ed38cb3
ms.sourcegitcommit: 109a6ef2d20758dc4a25c51b11e22dd2214a1cc4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1886784"
---
# <a name="calculate-capacity-load"></a>Calcular a capacidade máxima

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

No Gerenciamento de Ativos, você pode calcular a capacidade máxima em

- linhas do agendamento de manutenção  
- ordens de serviço que ainda não foram agendadas  
- ordens de serviço agendadas

Isso é útil para obter uma visão geral da capacidade máxima esperada por um período específico. O cálculo da capacidade máxima pode ser feito em todos os ativos ou ativos selecionados. Você também pode fazer um cálculo sobre atividades de tempo de inatividade de manutenção ou conjuntos de ordens de serviço.

1. Clique em **Gerenciamento de ativos** > **Consultas** > **Capacidade máxima** ou **Gerenciamento de ativos** > **Comum** > **Grupos de ordens de serviço** > **Todos os grupos de ordens de serviço** / **Grupos de ordens de serviço ativos** > selecione o grupo de ordens de serviço na lista > botão **Capacidade máxima** ou **Gerenciamento de ativos** > **Comum** > **Atividades de tempo de inatividade de manutenção** > **Todas as atividades de inatividade de manutenção** / **Grupos de ordens de serviço ativos** > selecione a atividade de manutenção na lista > botão **Capacidade máxima**.

2. Na caixa de diálogo **Calcular capacidade máxima**, selecione um período para o cálculo nos campos **Data/hora inicial** e **Data/hora final**.

3. Selecione "Sim" no botão **Incluir agendamento de manutenção** para incluir as linhas do agendamento de manutenção no cálculo.

4. Selecione "Sim" no botão **Incluir ordem de serviço** para alternar entre os trabalhos de ordem de serviço no cálculo.

5. Você pode usar o campo **Nível** para indicar o nível de detalhamento desejado das linhas de capacidade máxima em relação aos locais funcionais. Por exemplo, se você inserir o número "1" no campo e tiver uma estrutura de local funcional de vários níveis, todas as linhas de agendamento de manutenção e ordens de serviço de um local funcional serão mostradas no nível superior e, portanto, as horas de uma linha podem ser adicionadas dos locais funcionais localizados em nível inferior. Se você inserir o número "0" no campo **Nível**, verá um resultado detalhado mostrando todas as linhas do agendamento de manutenção e todas as ordens de serviço em todos os níveis do local funcional ao qual elas estão relacionadas.

6. Clique em **OK**para iniciar o cálculo.

7. Nos grupos do Painel de Ações **Agrupar por...**, clique nos botões relevantes para mostrar o nível de detalhe necessário do cálculo. Os botões do grupo de painéis de ação selecionados são destacados na cor azul. Clique em um botão para ativá-los ou desativá-los.

A figura abaixo mostra um exemplo de tela da interface.

![Figura 1](media/01-capacity-planning.png)

>[!NOTE]
>Se você deseja se concentrar apenas no planejamento de capacidade em relação às ordens de serviço agendadas, consulte [Calcular a capacidade máxima em ordens de serviço agendadas](../work-order-scheduling/calculate-capacity-load-on-scheduled-work-orders.md).
