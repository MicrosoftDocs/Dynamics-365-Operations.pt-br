---
title: Execução agendada
description: Este tópico explica execução agendada no Asset Management.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: a6d1761202697f62421bbf288c7e22efe559a986
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5022398"
---
# <a name="scheduled-execution"></a>Execução agendada

[!include [banner](../../includes/banner.md)]

 

Você pode usar níveis de serviço da ordem de serviço para configurar a execução agendada. (Para obter mais informações sobre níveis de serviço da ordem de serviço, consulte [Nível de serviço e descrição](service-level-and-description.md).) A execução agendada fornece flexibilidade no planejamento de trabalho para funcionários de manutenção, já você pode configurar requisitos mais ou menos detalhados para um intervalo em que uma ordem de serviço deve ser concluída. Por exemplo, um funcionário de manutenção que conclui um trabalho mais rápido que o esperado em uma fábrica pode ser capaz de mover para outro trabalho próximo que foi planejado para a semana atual, mas não necessariamente para o dia atual. Esta abordagem permite a otimização do planejamento do trabalhador e conclusão do trabalho.

Configuração de execução agendada, que é relacionada a ordens de serviço, pode ser genérica ou específica. Você pode configurar linhas genéricas que não são limitadas a tipos de ordem de serviço específicas, tipos de ativos e assim por diante. Alternativamente, você pode criar linhas de execução agendadas que se aplicam a um tipo de ordem de serviço específico, tipo de ativo, tipo de trabalho de manutenção, e assim por diante.

1. Selecione **Gerenciamento de Ativos** \> **Configuração** \> **Ordens de serviço** \> **Execução agendada**.
2. Selecione **Novo** para criar uma linha de execução agendada.
3. Nos campos **Local funcional**, **Tipo de ordem de serviço**, **Tipo de ativo**, **Fabricante**, **Modelo**, **Categoria de tipo de trabalho de manutenção**, **Tipo de trabalho de manutenção**, **Variação do tipo de trabalho de manutenção** e **Comércio**, selecione os valores que deseja.
4. No campo **Nível de serviço**, selecione um nível de serviço de ordem de serviço. Se deixar este campo em branco, você cria o tipo mais genérico de linha de execução agendada. Para um exemplo de uma linha genérica, consulte o primeiro registro na ilustração a seguir. Essa linha permite que todos as ordens de serviço que não tem um nível de serviço de ordem de serviço sejam agendadas para uma data e hora específica.
5. No campo **Execução agendada**, selecione o intervalo de tempo.
6. Selecione **Salvar**.

![Execução agendada](media/20-setup-for-work-orders.png)
