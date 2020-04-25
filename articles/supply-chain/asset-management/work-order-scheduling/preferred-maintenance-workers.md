---
title: Configurar funcionários de manutenção preferenciais
description: Este tópico explica como configurar funcionários de manutenção preferidos no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 327cda12a05ad54b310e472a652f1c822ad97142
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215323"
---
# <a name="set-up-preferred-maintenance-workers"></a>Configurar funcionários de manutenção preferenciais

[!include [banner](../../includes/banner.md)]

 

Durante o agendamento da ordem de serviço, você pode criar uma preferência em relação a qual funcionário de manutenção ou grupo de funcionários está alocado para concluir a ordem de serviço. O uso dessa funcionalidade é opcional, mas pode ajudá-lo a escolher o funcionário de manutenção mais qualificado para concluir um trabalho, com base nas habilidades e competências do funcionário. Apenas os funcionários de manutenção disponíveis no momento do agendamento serão agendados. Se uma configuração preferencial do funcionário de manutenção corresponder a uma ordem de serviço durante o agendamento, mas o funcionário de manutenção estiver alocado para outros trabalhos, a ordem de serviço será agendada para outro funcionário de manutenção disponível.

Para poder configurar funcionários de manutenção preferenciais, você deve primeiro configurar os funcionários de manutenção e os grupos de funcionários. Para obter uma descrição de como configurar os funcionários de manutenção e os grupos de funcionários, consulte [Funcionários de manutenção e grupos de trabalhadores](../setup-for-objects/workers-and-worker-groups.md).

## <a name="set-up-preferred-workers"></a>Configurar funcionários preferenciais

Um funcionário de manutenção ou grupo de funcionários preferencial pode estar relacionado a um ou mais do seguinte:

- comércio  
- grade do tipo de trabalho de manutenção  
- tipo de trabalho de manutenção  
- categoria do tipo de trabalho de manutenção  
- ativo  
- tipo de ativo  

Quanto mais seleções você fizer no mesmo registro, mais específica será sua configuração.

1. Clique **Gerenciamento de ativos** > **Configuração** > **Funcionários** > **Funcionários de manutenção preferenciais**.

2. Clique em **Novo** para criar um novo registro.

3. Comece criando um funcionário de manutenção ou grupo de funcionários "padrão". Isso significa que você só faz uma seleção no campo **Grupo de funcionários de manutenção preferenciais** ou **Funcionário de manutenção preferencial**. Na captura de tela abaixo, é exibido um exemplo no primeiro registro em que "Solicitações" está selecionado como **Grupo de funcionários de manutenção preferencial**.

    [!NOTE] A configuração padrão será usada durante o agendamento da ordem de serviço caso nenhuma outra combinação mais específica corresponda ao conteúdo da ordem de serviço.

4. Repita a etapa 2 para criar um novo registro. Faça seleções necessárias, dependendo do nível de detalhe do funcionário ou grupo de funcionários preferenciais. 

    *Exemplo:* na captura de tela a seguir, no sexto registro, o funcionário de manutenção Shawn Richardson foi selecionado como funcionário preferencial. Ele será selecionado automaticamente durante o agendamento de uma ordem de serviço que inclua o ativo "CH-BP1-03-02" e o tipo de trabalho de manutenção "Avaliação de instalações", se ele estiver disponível no horário agendado.

    [!NOTE] Geralmente, quando um funcionário de manutenção preferencial é selecionado durante o agendamento da ordem de serviço, o Gerenciamento de Ativos passa por todos os registros de **Funcionários de manutenção preferenciais** verifica a existência uma correspondência possível, verificando sempre a combinação mais específica primeiro. Se nenhuma correspondência for encontrada, o registro "padrão" com uma seleção no campo **Grupo de funcionários de manutenção preferenciais** ou o campo **Funcionário de manutenção preferencial** é usado.

![Figura 1](media/02-work-order-scheduling.png)

Você também pode configurar funcionários de manutenção *responsáveis*, que podem ser selecionados quando uma solicitação de manutenção ou uma ordem de serviço for criada. É possível editar a seleção em **Todas as ordens de serviço** e **Todas as solicitações de manutenção**, se necessário. Para obter mais informações, consulte [Funcionários de manutenção responsáveis](../setup-for-maintenance-requests/responsible-workers.md).

Durante o agendamento da ordem de serviço, diferentes pontuações são calculadas para determinar quais funcionários devem concluir os trabalhos relacionados a uma ordem de serviço (aquelas pontuações são configuradas no link **parâmetros do Gerenciamento de ativos** > **agendamento da Ordem de serviço**). Se dois ou mais funcionários de manutenção preferenciais ou funcionários de manutenção responsáveis obtiverem a mesma pontuação durante o agendamento da ordem de serviço, um funcionário é selecionado aleatoriamente. Caso contrário, é sempre o funcionário com a pontuação mais alta que é alocado para concluir uma ordem de serviço.

