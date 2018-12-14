---
title: Salvar as guias de tarefa para LCS e repeti-las
description: "Este tópico explica como salvar as guias de tarefa para Microsoft Dynamics Lifecycle Services (LCS) e depois repeti-las."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 40b4c3154a04a557b8a670e1f1ae3722c71122fe
ms.contentlocale: pt-br
ms.lasthandoff: 12/04/2018

---

# <a name="save-task-guides-to-lcs-and-replay-them"></a>Salvar as guias de tarefa para LCS e repeti-las

[!include [banner](includes/banner.md)]

**Detalhes do ambiente** 

Microsoft Dynamics 365 for Talent, que foi implantado por meio do Microsoft Dynamics Lifecycle Services (LCS)

**Saída**

O cliente deseja salvar novas gravações de tarefa para seu projeto LCS, e depois repeti-las às guias de tarefa salvas.

**Resolução**

Siga estas etapas para salvar uma gravação de tarefas ao LCS.

1. Conecte-se ao LCS e selecione o projeto.
2. Selecione o quadro **Modelador de processo de negócios**.
3. Exibir a página na "Experiência de BPM atualizado".
4. Selecione uma biblioteca e selecione **Copiar**.
5. Insira um nome para o modelo do Modelador de processo de negócios (BPM).
6. Entre em Talent a partir do LCS.
7. No campo **Pesquisar**, insira **ajuda**. Ajuda do Lifecycle Services é aberta.
8. Selecione o botão **Atualizar** para configuração da ajuda do Lifecycle Services.

    A nova biblioteca de BPM deve aparecer e deve ficar ativa.

9. Feche a página.
10. Criar uma gravação de tarefas.
11. Quando terminar, selecione **Salvar para Lifecycle Services**.

    ![Salvar no Lifecycle Services](media/task-guides.png)

12. Selecione a biblioteca e nó de BPM onde deseja salvar a gravação de tarefa.

Rastrear essas etapas para repetir uma guia de tarefas do LCS.

1. Iniciar Gravador de tarefas.
2. Selecione **Abrir a partir do LCS**.
3. Selecione a biblioteca e o nó de BPM que têm a guia da tarefa salva.
4. Abrir a guia de tarefas.

