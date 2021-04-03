---
title: Configurar atividades paralelas em um fluxo de trabalho
description: Para configurar uma atividade paralela, execute estes procedimentos no editor de fluxo de trabalho.
author: ChrisGarty
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 450420d44ad4aab233afc5a116369e993aa7a15b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570605"
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

3. Para configurar cada ramificação, consulte [Configurar ramificações paralelas em um fluxo de trabalho](configure-parallel-branch-workflow.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]