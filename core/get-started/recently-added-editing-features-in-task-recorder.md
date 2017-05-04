---
title: "Recursos de edição adicionados recentemente ao gravados de tarefas"
description: "Se usar o gravador de tarefas para criar as guias de tarefa, você poderá editar seus arquivos de forma mais eficiente usando a funcionalidade descrita neste wiki."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: Core
ms.custom: 266464
ms.assetid: b4640e67-4b92-4855-8041-1bfc71aadc47
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
translationtype: Human Translation
ms.sourcegitcommit: c8c96dc9705688308dd4a5c720700ddc17657d75
ms.openlocfilehash: c4f9ac515eab6ed8b194fc8985f6d3fae40ced38
ms.lasthandoff: 03/31/2017


---

# <a name="recently-added-editing-features-in-task-recorder"></a>Recursos de edição adicionados recentemente ao gravados de tarefas

Se usar o gravador de tarefas para criar as guias de tarefa, você poderá editar seus arquivos de forma mais eficiente usando a funcionalidade descrita neste wiki.

Esses recursos estão disponíveis no menu **Configurações &gt; Gravador de tarefas &gt; Editar gravação**.

-   Inserção etapas sem registrar novamente o arquivo completo.
-   Mova as etapas em uma subtarefa sem registrar novamente o arquivo completo.
-   Recolher campos de nome e descrição da gravação.

## <a name="insert-steps-without-rerecording-the-entire-file"></a>Inserir etapas sem registrar novamente o arquivo completo
Agora você pode adicionar uma etapa em qualquer lugar em uma guia de tarefa sem ter de rodar novamente ou gravar novamente o arquivo inteiro.

1.  Selecione a etapa após a qual você deseja que a nova etapa seja inserida. Verifique se a etapa está realçada.

Para que o gravador de tarefas insira uma etapa, você deve ter a página correta aberta. A página correta é a página na qual a nova etapa ocorre. O gravador de tarefas tem um mecanismo que determina qual é a página ativa, e desabilitará a funcionalidade se a página correta não estiver aberta. 

[![tg1](./media/tg1.png)](./media/tg1.png) 


Quando estiver na página correta, **Inserir etapa** torna-se disponível.

[![tg2](./media/tg2-231x300.png)](./media/tg2.png)

2. Clique em **Inserir etapa**.

Quando clicar em **Inserir etapa**, o gravador de tarefas muda para o modo de gravação. Qualquer ação realizada na IU agora será gravada e adicionada no lugar como etapas.

3. Clique em **Parar**.

Você pode repetir o processo, adicionando quantas etapas ou movendo quantas tarefas forem necessário (consulte subtarefas abaixo).

4. Quando tiver terminado a edição da guia de tarefas, clique em **Finalizar edição** e depois escolha uma das opções para salvar ou publicar o guia de tarefas.

## <a name="move-steps-under-a-subtask-without-rerecording-the-entire-file"></a>Mova as etapas em uma subtarefa sem registrar novamente o arquivo completo
Você pode mover as etapas em uma subtarefa sem rodar novamente ou registrar novamente o arquivo completo. Você também pode mover a etapa da subtarefa ou a etapa de subtarefa final se desejar agrupar um bloco de etapas existente.

1.  Selecione a etapa ou a etapa de subtarefa que deseja mover. Verifique se a etapa está realçada.
2.  Clique nas reticências e depois em **Mover etapa para frente**.

[![tg3](./media/tg3.png)](./media/tg3.png)

3. Selecione a etapa ou as etapas de subtarefa que deseja mover para a próxima etapa ou etapas de subtarefa. O gravador de tarefas moverá a etapa.

4. Para mover a etapa de subtarefa final, selecione-a, clique nas reticências, clique em **Mover etapa para frente** e depois selecione a etapa para frente onde deseja que a etapa de subtarefa final esteja.

Se quiser que a primeira etapa no guia de tarefas esteja dentro de uma subtarefa, crie uma etapa de subtarefa como a segunda etapa, e depois mova a primeira tarefa nela. Você pode adicionar ou mover quantas etapas ou subtarefas forem necessário.

5. Quando tiver terminado a edição da guia de tarefas, clique em **Finalizar edição** e depois escolha uma das opções para salvar ou publicar o guia de tarefas.

## <a name="collapse-recording-name-and-description"></a>Recolher nome e descrição de gravação
Você pode expandir e recolher os campos **Nome de registro** e **Descrição de registro**. Quando esses campos são recolhidos, mais etapas ficarão visíveis no painel de edição do gravador de tarefas. 

[![tg4](./media/tg4-300x252.png)](./media/tg4.png)  

<a name="see-also"></a>Consulte também
--------

[Criar documentação ou treinamento utilizando Gravações de tarefas](/dynamics365/operations/dev-itpro/user-interface/task-recorder)

[Referência rápida ao gravador de tarefas](/dynamics365/operations/dev-itpro/user-interface/task-recorder-quick-reference)


