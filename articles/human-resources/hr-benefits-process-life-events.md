---
title: Processar eventos de vida
description: Durante o ciclo de vida do funcionário no Microsoft Dynamics 365 Human Resources, cada funcionário pode encontrar várias alterações de eventos de vida.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ba8d21482a18c6baa93437fc65c165907bdb515d
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2020
ms.locfileid: "3229915"
---
# <a name="process-life-events"></a>Processar eventos de vida

Durante o ciclo de vida do funcionário no Microsoft Dynamics 365 Human Resources, cada funcionário pode encontrar várias alterações de eventos de vida. Por exemplo, casamento, mudança de emprego ou alteração de dependente/beneficiário. Para usar eventos de vida, você deve habilitar eventos de vida no formulário de parâmetros de benefícios, configurar tipos de eventos de vida e configurar opções de eventos de vida para tipos de plano.

Antes de poder processar eventos de vida, você já deve ter executado a inscrição aberta pelo menos uma vez durante um período de contratação. Nos Estados Unidos, a inscrição aberta costuma ocorrer uma vez por ano. Fora dos Estados Unidos, a inscrição aberta pode ser realizada no momento da contratação. Um trabalhador não precisa selecionar um plano de benefícios para que os eventos de vida sejam processados, mas eles precisam ter sido incluídos no processamento de inscrição aberta. 

Use o processamento de eventos de vida quando tiver trabalhadores com eventos de vida que ocorrerão em uma data futura. Este evento processará todos os eventos de vida que não foram processados (como eventos de vida futuros ou eventos de vida adicionados que não são específicos para nenhum trabalhador; por exemplo, um novo benefício). Os eventos de vida em tempo real estão ocultos.

Por exemplo, se hoje for 1º de fevereiro, houver um agendamento para que trabalhador José da Silva altere entidades legais em 14 de fevereiro e você executar o processamento de eventos de vida em 15 de fevereiro, o sistema processará todos os eventos até 15 de fevereiro. 

1. No espaço de trabalho **Gerenciamento de benefícios**, em **Processando**, selecione **Processamento de eventos de vida**.

2. No caixa de diálogo **Executar o processamento de eventos de vida**, especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | **Período de inscrição** | O período de inscrição para processar eventos de vida. |
   | **Pessoa jurídica em geral** | A entidade legal para processar eventos de vida. |
   | **Data do evento de vida** | O sistema processa todos os eventos durante o período de inscrição que ocorrem até a data atual. |
   | **Trabalhador** | O trabalhador para processar eventos de vida. Se você deixar esse campo em branco, os eventos de vida serão processados para todos os trabalhadores. |

3. Se você deseja executar o processo em segundo plano, selecione **Executar em segundo plano** e execute as seguintes tarefas:

   1. Insira informações para o processo.

   2. Para configurar um trabalho recorrente, selecione **Recorrência**, insira as informações de recorrência e selecione **OK**.

   3. Para configurar um alerta de trabalho, selecione **Alertas**, selecione os alertas a receber e, em seguida, selecione **OK**.

   4. Selecione **OK**. O processo será executado com os parâmetros definidos por você.

4. Selecione **OK**.
