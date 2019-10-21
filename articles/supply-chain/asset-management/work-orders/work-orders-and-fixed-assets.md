---
title: Ordens de serviço e ativos fixos
description: Este tópico explica as ordens de serviço e os ativos fixos no Gerenciamento de Ativos.
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
ms.openlocfilehash: 95fe394d22f9fe81511c230a2cf7b8ddf00d896f
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250820"
---
# <a name="work-orders-and-fixed-assets"></a>Ordens de serviço e ativos fixos


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


No Gerenciamento de Ativos, os ativos podem estar relacionados a ativos fixos, e podem criar ordens de serviço para esses ativos. Se usar essa funcionalidade, você terá uma visão geral completa de ativos fixos, de projetos de investimento relacionados e dos custos registrados em projetos de investimento no módulo **Gerenciamento e contabilidade de projeto** e no módulo **Ativos fixos**.

>[!NOTE]
>O campo **Número de ativo fixo** só será preenchido no projeto de trabalho de ordem de serviço se o tipo "Investimento" for selecionado como o tipo de projeto no projeto de trabalho de ordem de serviço.

![Figura 1](media/24-work-orders.png)

O procedimento a seguir descreve a relação entre ativos, ordens de serviço, projetos de trabalho de ordem de serviço e ativos fixos.

1. Você cria um ativo que relaciona a um ativo fixo, conforme mostra a figura abaixo.

![Figura 2](media/25-work-orders.png)

2. Quando configura os tipos de ordem de serviço (**Gerenciamento de ativos** > **Configuração** > **Ordens de serviço** > **Tipos de ordem de serviço**), você cria um tipo de ordem de serviço para lidar com investimentos. Consulte também [Tipos de ordem de serviço](../setup-for-work-orders/work-order-types.md).

![Figura 3](media/26-work-orders.png)

3. Quando configura grupos de projetos de ordem de serviço (link **Gerenciamento de ativos** > **Configuração** > **Ordens de serviço** > **Configuração de projeto** > **Grupo de projetos**), você cria uma relação entre o tipo de ordem de serviço usado para investimentos no módulo **Gerenciamento e contabilidade de projeto** (**Gerenciamento e contabilidade de projeto** > **Configuração** > **Lançamento** > **Grupos de projetos**).

![Figura 4](media/27-work-orders.png)

4. Quando cria uma ordem de serviço relacionada a um objeto de ativo fixo, você seleciona o tipo de ordem de serviço usado para lidar com investimentos, por exemplo, "Investimento".

5. Quando a ordem de serviço for criada, o tipo de ordem de serviço relacionada é mostrado em **Todas as ordens de serviço**.

![Figura 5](media/28-work-orders.png)

6. Quando a ordem de serviço é criada, o projeto relacionado à ordem de serviço é criado em **Gerenciamento e contabilidade de projeto** > **Todos os projetos**. Você verá informações relacionadas ao projeto clicando no link **ID do Projeto** na ordem de serviço (em **Gerenciamento de ativos**, abra a ordem de serviço na exibição Detalhes > **Detalhes da linha** Guia Rápida > guia **Geral** > campo **ID do Projeto**).

![Figura 6](media/29-work-orders.png)

7. Em **Ativos fixos**, você terá uma visão geral dos projetos associados a um ativo fixo (**Ativos fixos** > **Ativos fixos** > **Ativos fixos** > clique no ativo fixo no campo **Número do ativo fixo** > exiba o conteúdo no painel **Informações relacionadas** > seção **Projetos associados**).

