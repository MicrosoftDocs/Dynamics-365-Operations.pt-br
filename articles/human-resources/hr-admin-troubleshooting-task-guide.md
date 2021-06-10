---
title: Salvar guias de tarefa no LCS e repeti-las
description: Este artigo explica como salvar as guias de tarefa para o Microsoft Dynamics Lifecycle Services (LCS) e depois reproduzi-las.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8a18bb14ba8c3c926065c97b0ee26c38ee86ded2
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053266"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a>Salvar guias de tarefa no LCS e repeti-las

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Detalhes do ambiente** 

Microsoft Dynamics 365 Human Resources, que foi implantado por meio do Microsoft Dynamics Lifecycle Services (LCS)

**Problema**

O cliente quer salvar novos registros do trabalho no projeto LCS e, então, reproduzir os guias de tarefa salvos.

**Resolução**

Siga estas etapas para salvar uma gravação de tarefas ao LCS.

1. Conecte-se ao LCS e selecione o projeto.
2. Selecione o quadro **Modelador de processo de negócios**.
3. Exibir a página na "Experiência de BPM atualizado".
4. Selecione uma biblioteca e selecione **Copiar**.
5. Insira um nome para o modelo do Modelador de processo de negócios (BPM).
6. Faça logon no Human Resources do LCS.
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


[!INCLUDE[footer-include](../includes/footer-banner.md)]