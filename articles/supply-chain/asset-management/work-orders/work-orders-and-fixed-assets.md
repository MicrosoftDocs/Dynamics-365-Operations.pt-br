---
title: Ordens de serviço e ativos fixos
description: Este artigo explica as ordens de serviço e os ativos fixos no Gerenciamento de Ativos.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ed83450592d85205743c9ff1aefd0e66e5d2b90c
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111949"
---
# <a name="work-orders-and-fixed-assets"></a>Ordens de serviço e ativos fixos

[!include [banner](../../includes/banner.md)]


No Gerenciamento de Ativos, os ativos podem estar relacionados a ativos fixos, e podem criar ordens de serviço para esses ativos. Se usar essa funcionalidade, você terá uma visão geral completa de ativos fixos, de projetos de investimento relacionados e dos custos que são registrados em projetos de investimento no módulo **Gerenciamento e contabilidade do projeto** e nos módulos de **Ativos fixos** nos aplicativos de finanças e operações.

>[!NOTE]
>O campo **Número de ativo fixo** só será configurado no projeto de trabalho de ordem de serviço se o tipo **Investimento** for selecionado como o tipo de projeto no projeto de trabalho de ordem de serviço.

A ilustração abaixo mostra a relação entre um projeto de investimento no módulo **Gerenciamento e contabilidade de projeto** e um projeto de trabalho de ordem de serviço.

![Figura 1.](media/24-work-orders.png)

O procedimento a seguir descreve a relação entre ativos, ordens de serviço, projetos de trabalho de ordem de serviço e ativos fixos.

1. Você cria um ativo que será relacionado a um ativo fixo.

![Figura 2.](media/25-work-orders.png)

2. Quando configura os tipos de ordem de serviço na página **Tipos de ordem de serviço** (**Gerenciamento de ativos** > **Configuração** > **Ordens de serviço** > **Tipos de ordem de serviço**), você cria um tipo de ordem de serviço para lidar com investimentos. Consulte também [Tipos de ordem de serviço](../setup-for-work-orders/work-order-types.md).

![Figura 3.](media/26-work-orders.png)

3. Quando configura grupos de projetos de ordem de serviço na guia **Grupo de projetos** da página **Configuração do projeto de ordem de serviço** (**Gerenciamento de ativos** > **Configuração** > **Ordens de serviço** > **Configuração de projeto**), você cria uma relação entre o tipo de ordem de serviço que é usado para investimentos e o grupo de projetos que foi criado para investimentos na página **Grupos de projetos** no módulo **Gerenciamento e contabilidade de projeto** (**Gerenciamento e contabilidade de projeto** > **Configuração** > **Lançamento** > **Grupos de projetos**).

![Figura 4.](media/27-work-orders.png)

4. Ao criar uma ordem de serviço que está relacionada a um objeto de ativo fixo, você seleciona o tipo de ordem de serviço que é usado para tratar investimentos como, por exemplo, **Investimento**.

5. Quando a ordem de serviço é criada, o tipo de ordem de serviço relacionada será mostrado na página **Todas as ordens de serviço**.

![Figura 5.](media/28-work-orders.png)

6. Quando a ordem de serviço é criada, o projeto que está relacionado à ordem de serviço é criado na página **Todos os projetos** no módulo **Gerenciamento e contabilidade de projeto** (**Gerenciamento e contabilidade de projeto** > **Projetos** > **Todos os projetos**). Para exibir as informações relacionadas ao projeto, selecione o link no campo **ID do projeto** na guia **Geral** na Guia Rápida **Detalhes da linha** na exibição de detalhes da página **Todas as ordens de serviço** no módulo **Gerenciamento de ativos** (**Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço**).

![Figura 6.](media/29-work-orders.png)

7. Para exibir uma visão geral dos projetos associados a um ativo fixo, selecione **Ativos fixos** > **Ativos fixos** > **Ativos fixos** e, em seguida, no campo **Número do ativo fixo**, selecione o link do ativo fixo para abrir a exibição de detalhes. Expanda o painel **Informações relacionadas** do lado direito da página e selecione a Guia Rápida **Projetos associados**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
