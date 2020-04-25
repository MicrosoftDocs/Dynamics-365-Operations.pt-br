---
title: Ordens de serviço e ativos fixos
description: Este tópico explica as ordens de serviço e os ativos fixos no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
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
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ca7a5d88de4308d7be9c1bc749b9dbf1da027c2c
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208814"
---
# <a name="work-orders-and-fixed-assets"></a>Ordens de serviço e ativos fixos

[!include [banner](../../includes/banner.md)]


No Gerenciamento de Ativos, os ativos podem estar relacionados a ativos fixos, e podem criar ordens de serviço para esses ativos. Se usar essa funcionalidade, você terá uma visão geral de ativos fixos, de projetos de investimento relacionados e dos custos que estão registrados em projetos de investimento nos módulos **Gerenciamento e contabilidade de projeto** e **Ativos fixos** do Microsoft Dynamics 365 for Finance and Operations.

>[!NOTE]
>O campo **Número de ativo fixo** só será configurado no projeto de trabalho de ordem de serviço se o tipo **Investimento** for selecionado como o tipo de projeto no projeto de trabalho de ordem de serviço.

A ilustração abaixo mostra a relação entre um projeto de investimento no módulo **Gerenciamento e contabilidade de projeto** e um projeto de trabalho de ordem de serviço.

![Figura 1](media/24-work-orders.png)

O procedimento a seguir descreve a relação entre ativos, ordens de serviço, projetos de trabalho de ordem de serviço e ativos fixos.

1. Você cria um ativo que será relacionado a um ativo fixo.

![Figura 2](media/25-work-orders.png)

2. Quando configura os tipos de ordem de serviço na página **Tipos de ordem de serviço** (**Gerenciamento de ativos** > **Configuração** > **Ordens de serviço** > **Tipos de ordem de serviço**), você cria um tipo de ordem de serviço para lidar com investimentos. Consulte também [Tipos de ordem de serviço](../setup-for-work-orders/work-order-types.md).

![Figura 3](media/26-work-orders.png)

3. Quando configura grupos de projetos de ordem de serviço na guia **Grupo de projetos** da página **Configuração do projeto de ordem de serviço** (**Gerenciamento de ativos** > **Configuração** > **Ordens de serviço** > **Configuração de projeto**), você cria uma relação entre o tipo de ordem de serviço que é usado para investimentos e o grupo de projetos que foi criado para investimentos na página **Grupos de projetos** no módulo **Gerenciamento e contabilidade de projeto** (**Gerenciamento e contabilidade de projeto** > **Configuração** > **Lançamento** > **Grupos de projetos**).

![Figura 4](media/27-work-orders.png)

4. Ao criar uma ordem de serviço que está relacionada a um objeto de ativo fixo, você seleciona o tipo de ordem de serviço que é usado para tratar investimentos como, por exemplo, **Investimento**.

5. Quando a ordem de serviço é criada, o tipo de ordem de serviço relacionada será mostrado na página **Todas as ordens de serviço**.

![Figura 5](media/28-work-orders.png)

6. Quando a ordem de serviço é criada, o projeto que está relacionado à ordem de serviço é criado na página **Todos os projetos** no módulo **Gerenciamento e contabilidade de projeto** (**Gerenciamento e contabilidade de projeto** > **Projetos** > **Todos os projetos**). Para exibir as informações relacionadas ao projeto, selecione o link no campo **ID do projeto** na guia **Geral** na Guia Rápida **Detalhes da linha** na exibição de detalhes da página **Todas as ordens de serviço** no módulo **Gerenciamento de ativos** (**Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço**).

![Figura 6](media/29-work-orders.png)

7. Para exibir uma visão geral dos projetos associados a um ativo fixo, selecione **Ativos fixos** > **Ativos fixos** > **Ativos fixos** e, em seguida, no campo **Número do ativo fixo**, selecione o link do ativo fixo para abrir a exibição de detalhes. Expanda o painel **Informações relacionadas** do lado direito da página e selecione a Guia Rápida **Projetos associados**.

