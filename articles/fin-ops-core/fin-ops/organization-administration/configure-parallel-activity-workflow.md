---
title: Configurar atividades paralelas em um fluxo de trabalho
description: Para configurar uma atividade paralela, execute estes procedimentos no editor de fluxo de trabalho.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 11b541c3e159b2c38e4dd2fa9f2ad08e4c1e4500
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176505"
---
# <a name="configure-parallel-activities-in-a-workflow"></a>Configurar atividades paralelas em um fluxo de trabalho

[!include [banner](../includes/banner.md)]

Para configurar uma atividade paralela, execute estes procedimentos no editor de fluxo de trabalho.

Uma atividade paralela consiste em ramificações do fluxo de trabalho que são executadas simultaneamente.

## <a name="name-a-parallel-activity"></a>Forneça um nome à atividade paralela.

Siga estas etapas para inserir um nome para a atividade paralela.

1. Clique com o botão direito do mouse na atividade paralela e clique em **Propriedades** para abrir o formulário **Propriedades**.
2. No painel esquerdo, clique em **Configurações Básicas**.
3. No campo **Nome**, insira um nome exclusivo para a atividade paralela.
4. Clique em **Fechar**.

## <a name="configure-the-branches-of-a-parallel-activity"></a>Configurar as ramificações da atividade paralela

Siga estas etapas para adicionar e configurar as ramificações dessa atividade paralela.

1. Clique duas vezes na atividade paralela para exibir suas ramificações.
2. Para adicionar uma ramificação, arraste o elemento **Ramificação** da área **Elemento de fluxo de trabalho** para um ponto de inserção na tela. A figura a seguir mostra um ponto de inserção.

    ![Ponto de inserção](./media/workflow_insertionpoint.gif)

    > [!NOTE]
    > A ordem das ramificações não é importante porque todas as ramificações de uma atividade paralela são executadas ao mesmo tempo.

3. Cada ramificação para configurar, consulte [Configurar uma filial paralelo](configure-parallel-branch-workflow.md).
