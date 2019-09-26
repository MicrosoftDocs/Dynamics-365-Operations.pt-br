---
title: Calcular previsão de itens
description: Este tópico explica como calcular a previsão de itens no Gerenciamento de Ativos.
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
ms.openlocfilehash: 9091ff7a394cd08b68e78c8f668d7cd962003e6d
ms.sourcegitcommit: 109a6ef2d20758dc4a25c51b11e22dd2214a1cc4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1886761"
---
# <a name="calculate-item-forecast"></a>Calcular previsão de itens

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Da mesma forma que você pode fazer cálculos de capacidade máxima, descritos na seção anterior, também é possível fazer cálculos de previsão de itens em

- Linhas do agendamento de manutenção  
- Ordens de serviço que ainda não foram agendadas  
- Ordens de serviço agendadas

Isso é útil se você deseja obter uma visão geral do consumo esperado de itens (peças sobressalentes e outros itens necessários para concluir as ordens de serviço) por um período específico. O cálculo da previsão do item pode ser feito em todos os ativos ou ativos selecionados. Também é possível fazer um cálculo em uma atividade de tempo de inatividade de manutenção (**Todas as atividades de inatividade de manutenção** ou **Atividades de inatividade de manutenção ativa**) ou em um conjunto de ordens de serviço (**Todos os grupos de ordens de serviço** ou **Grupos de ordens de serviço ativos**).

1. Clique em **Gerenciamento de ativos** > **Consultas** > **Previsão de item** ou **Gerenciamento de ativos** > **Comum** > **Grupos de ordens de serviço** > **Todos os grupos de ordens de serviço** / **Grupos de ordens de serviço ativos** > selecione o grupo de ordens de serviço na lista > botão **Previsão de Item** ou **Gerenciamento de ativos** > **Comum** > **Atividades de tempo de inatividade de manutenção** > **Todas as atividades de inatividade de manutenção** / **Grupos de ordens de serviço ativos** > selecione a atividade de tempo de inatividade de manutenção na lista > botão **Previsão de item**.

2. Na caixa de diálogo **Calcular previsão de itens**, selecione um período para o cálculo nos campos **Data/hora inicial** e **Data/hora final**.

3. Selecione "Sim" no botão **Incluir agendamento de manutenção** para incluir as linhas do agendamento de manutenção no cálculo da previsão.

4. Selecione "Sim" no botão **Incluir ordem de serviço** para alternar entre os trabalhos de ordem de serviço no cálculo da previsão.

5. Você pode usar o campo **Nível** para indicar o nível de detalhamento desejado das linhas de previsão de item em relação aos locais funcionais. Por exemplo, se você inserir o número "1" no campo e tiver uma estrutura de local funcional de vários níveis, todas as linhas de agendamento de manutenção e ordens de serviço de um local funcional serão mostradas no nível superior e, portanto, as horas de uma linha podem ser adicionadas dos locais funcionais localizados em nível inferior. Se você inserir o número "0" no campo **Nível**, verá um resultado detalhado mostrando todas as linhas do agendamento de manutenção e todas as ordens de serviço em todos os níveis do local funcional ao qual elas estão relacionadas.

6. Clique em **OK**para iniciar o cálculo.

7. Nos grupos do Painel de Ações **Agrupar por...**, clique nos botões relevantes para mostrar o nível de detalhe necessário do cálculo. Os botões do grupo de painéis de ação selecionados são destacados na cor azul. Clique em um botão para ativá-los ou desativá-los.

8. Clique no botão **Exibir dimensões** se desejar ver as dimensões do produto, armazenamento ou rastreamento relacionadas aos itens. Marque as caixas de seleção relevantes e clique em **OK**.

A figura abaixo mostra uma captura de tela da interface.

![Figura 1](media/02-capacity-planning.png)