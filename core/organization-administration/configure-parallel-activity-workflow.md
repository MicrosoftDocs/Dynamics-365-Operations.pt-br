---
title: Configurar uma atividade em paralelo um fluxo de trabalho
description: Para configurar uma atividade paralela, execute estes procedimentos no editor de fluxo de trabalho.
author: sericks007
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 818fb054742b935d002a7341e54a37eca0bb4761
ms.lasthandoff: 03/31/2017


---

# <a name="configure-a-parallel-activity-in-a-workflow"></a>Configurar uma atividade em paralelo um fluxo de trabalho

Para configurar uma atividade paralela, execute estes procedimentos no editor de fluxo de trabalho.

Uma atividade paralela consiste em ramificações do fluxo de trabalho que são executadas simultaneamente.

## <a name="name-a-parallel-activity"></a>Forneça um nome à atividade paralela.
Siga estas etapas para inserir um nome para a atividade paralela.
1.  Clique com o botão direito em paralelo, a atividade e clique em propriedades ** ** para abrir ** propriedades ** o formulário.
2.  No painel esquerdo, clique em **Configurações Básicas**.
3.  No campo **Nome**, insira um nome exclusivo para a atividade paralela.
4.  Clique em **Fechar**.

## <a name="configure-the-branches-of-a-parallel-activity"></a>Configurar as ramificações da atividade paralela
Siga estas etapas para adicionar e configurar as ramificações dessa atividade paralela.
1.  Clique duas vezes na atividade paralela para exibir suas ramificações.
2.  Para adicionar uma ramificação, arraste o elemento **Ramificação** da área **Elemento de fluxo de trabalho** para um ponto de inserção na tela. A figura a seguir mostra um ponto de inserção.![Ponto de inserção](./media/workflow_insertionpoint.gif)
    | **Nota **                                                                                                         |
    |------------------------------------------------------------------------------------------------------------------|
    | A ordem das ramificações não é importante porque todas as ramificações de uma atividade paralela são executadas ao mesmo tempo. |

3.  Cada ramificação para configurar, consulte [Configurar uma filial paralelo](http://axhelp.dynamics.com/en/wiki/configure-a-parallel-branch/).




