---
title: Criação de ordens de serviço
description: Este tópico explica como criar ordens de serviço no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b23ed3251b2f6cf4f34b423ce2f85301d6ab31a1
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875499"
---
# <a name="creating-work-orders"></a>Criação de ordens de serviço


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Quando você agendar trabalhos de manutenção preventiva, a próxima etapa é criar ordens de serviço para os trabalhos. Isso é feito em um dos agendamentos de manutenção. Os trabalhos agendados em um agendamento de manutenção podem ter diferentes tipos de referência:

| Tipo de referência | Descrição                    |
|-----------------------|------------------------------------------------------------------------------------------------------------|
| Planos de manutenção     | Trabalhos de manutenção preventiva com base nos tipos de plano de manutenção "Tempo" ou "Contador".                       |
| Rounds de manutenção    | Trabalhos de manutenção preventiva contendo vários ativos que requerem um tipo semelhante de manutenção.           |
| Solicitação de manutenção   | Solicitação criada manualmente para manutenção ou reparo de um ativo, que pode ser convertida em uma ordem de serviço. |


1. Clique em **Gerenciamento de ativos** > **Comum** > **Todos os planos de manutenção** ou **Abrir linhas do agendamento de manutenção** ou **Abrir grupos de agendamento de manutenção**.

2. Selecione os trabalhos de manutenção agendados para os quais deseja criar uma ordem de serviço e clique em **Ordem de serviço**. O número total de horas de previsão para as linhas selecionadas é mostrado no campo **Horas de previsão de manutenção**.

3. Na seção **Parâmetros**, selecione quantas ordens de serviço devem ser criadas. Você pode criar uma ordem de serviço por linha de programação de manutenção ou várias ordens de serviço com base nas suas seleções na seção **Uma ordem de serviço por**.

4. Selecione um **Tipo de ordem de trabalho** que será usado em todas as ordens de serviço que você criar.

5. Clique em **OK**. Uma ou mais ordens de serviço são criadas.

![Figura 1](media/18-preventive-maintenance.png)

