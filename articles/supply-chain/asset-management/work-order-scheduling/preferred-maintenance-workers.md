---
title: Configurar funcionários de manutenção preferenciais
description: Este tópico explica como configurar funcionários de manutenção preferidos no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
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
ms.openlocfilehash: 8f26be81e7057d0cea1473d81452216251633ad9
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887402"
---
# <a name="preferred-maintenance-workers"></a>Funcionários de manutenção preferenciais

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Você pode criar uma preferência em relação a quais funcionários de manutenção estão alocados para concluir as ordens de serviço durante o agendamento da ordem de serviço. O uso dessa funcionalidade é opcional, mas pode ajudá-lo a escolher o funcionário de manutenção mais qualificado para concluir um trabalho, com base nas habilidades e competências do funcionário. Portanto, durante o agendamento da ordem de serviço, a configuração em **Funcionários de manutenção preferenciais** é usada para determinar se um funcionário de manutenção ou um grupo de funcionários deve ser agendado para uma ordem de serviço. Apenas os funcionários de manutenção disponíveis no momento do agendamento serão agendados. Se uma configuração do funcionário de manutenção corresponder a uma ordem de serviço durante o agendamento, mas o funcionário de manutenção estiver alocado para outros trabalhos, a ordem de serviço será agendada para outro funcionário de manutenção disponível.

Antes de configurar funcionários de manutenção preferenciais, você deverá primeiro configurar os funcionários e grupos de funcionários de manutenção que devem estar disponíveis para seleção. Consulte [Funcionários e grupos de funcionários de manutenção](../setup-for-objects/workers-and-worker-groups.md) para obter uma descrição de como configurar os funcionários e grupos de funcionários de manutenção.

## <a name="set-up-preferred-workers"></a>Configurar funcionários preferenciais

Um funcionário ou grupo de funcionários de manutenção preferenciais podem estar relacionados a um determinado

- comércio  
- grade do tipo de trabalho de manutenção  
- tipo de trabalho de manutenção  
- categoria do tipo de trabalho de manutenção  
- ativo  
- tipo de ativo  

ou uma combinação dessas seleções. Quanto mais seleções você fizer no mesmo registro, mais específica será sua configuração.

1. Clique **Gerenciamento de ativos** > **Configuração** > **Funcionários** > **Funcionários de manutenção preferenciais**.

2. Clique em **Novo** para criar um novo registro.

3. Comece criando uma configuração de funcionário de manutenção ou grupo de funcionários "padrão" que não possui seleções nos campos mostrados na lista de marcadores acima. Isso significa que você só faz uma seleção no campo **Grupo de funcionários de manutenção preferenciais** ou **Funcionário de manutenção preferencial**. Na figura abaixo, você vê um exemplo no primeiro registro em que "Solicitações" é selecionado como grupo de funcionários de manutenção preferenciais.

>[!NOTE]
>A configuração padrão será usada durante o agendamento da ordem de serviço, caso nenhuma outra combinação mais específica corresponda ao conteúdo da ordem de serviço durante o agendamento da ordem de serviço.

4. Repita a etapa 2 para criar um novo registro. Faça seleções necessárias, dependendo do nível de detalhe do funcionário ou grupo de funcionários preferenciais. *Exemplo:* Na figura abaixo, no sexto registro, o funcionário de manutenção Shawn Richardson foi selecionado como funcionário preferencial. Ele será selecionado automaticamente durante o agendamento de uma ordem de serviço que inclua o ativo "CH-BP1-03-02 e o tipo de trabalho de manutenção geral" Avaliação de instalações ", se ele estiver disponível no horário agendado.

>[!NOTE]
>Geralmente, quando um funcionário de manutenção preferencial é selecionado durante o agendamento da ordem de serviço, o Gerenciamento de Ativos passa por todos os registros de **Funcionários de manutenção preferenciais** verifica a existência uma correspondência possível, verificando sempre a combinação mais específica primeiro. Se nenhuma correspondência for encontrada, o registro "padrão" com uma seleção no campo **Grupo de funcionários de manutenção preferenciais** ou o campo **Funcionário de manutenção preferencial** é usado.


![Figura 1](media/02-work-order-scheduling.png)

Você também pode configurar os funcionários de manutenção responsáveis que podem ser selecionados quando a uma solicitação de manutenção ou uma ordem de serviço for criada. Em **Todas as ordens de trabalho** e **Todas as solicitações de manutenção**, você pode editar a seleção, se necessário. Consulte [Funcionários de manutenção responsáveis](../setup-for-maintenance-requests/responsible-workers.md) para obter mais informações.

Durante o agendamento da ordem de serviço, diferentes pontuações são calculadas para determinar quais funcionários devem concluir os trabalhos relacionados a uma ordem de serviço (aquelas pontuações são configuradas no link **parâmetros do Gerenciamento de ativos** > **agendamento da Ordem de serviço**). Se dois ou mais funcionários de manutenção preferenciais ou funcionários de manutenção responsáveis obtiverem a mesma pontuação durante o agendamento da ordem de serviço, um funcionário é selecionado aleatoriamente. Caso contrário, é sempre o funcionário com a pontuação mais alta que é alocado para concluir uma ordem de serviço.

