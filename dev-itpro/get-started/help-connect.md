---
title: Conectar o sistema de Ajuda
description: "Este tópico descreve os componentes do sistema de ajuda para Microsoft Dynamics 365 for Operations, fornecendo uma visão geral de como conectá-los e um resumo de como criar a ajuda personalizada."
author: margoc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 5ac5e30cff2239f601778001368fa7aaba478f5c
ms.lasthandoff: 03/31/2017


---

# <a name="connect-the-help-system"></a>Conectar o sistema de Ajuda

Este tópico descreve os componentes do sistema de Ajuda do Microsoft Dynamics 365 for Operations. Ele fornece uma visão geral de como conectar esses componentes e um resumo de como criar a ajuda personalizada. 

<a name="help-architecture"></a>Arquitetura de ajuda
-----------------

A ilustração a seguir mostra as partes do sistema de Ajuda do Microsoft Dynamics 365 for Operations. O sistema de Ajuda do produto traz artigos do site do Dynamics 365 for Operations em https://docs.microsoft.com, bem como guias de tarefa armazenados no Business Process Modeler no Lifecycle Services (LCS). 
**Observação:** Os recursos listados no diagrama com um asterisco (\*) estão planejados, mas ainda não estão disponíveis. [![Arquitetura de ajuda](./media/help-architecture.png)](./media/help-architecture.png)

## <a name="connecting-the-help-system"></a>Conectando o sistema de Ajuda
Usando a página de **Parâmetros do Sistema**, os administradores de sistema conectam as partes do sistema de Ajuda para uma implementação. [![Formulário de parâmetros do sistema com configurações de ajuda](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) Na página **Parâmetros do sistema**, siga estas etapas:

1.  **Importante:** A primeira vez que você abrir a guia da **Ajuda**, é necessário conectar serviços do ciclo de vida. Certifique-se de clicar no link no meio do formulário, aguarda a conexão, feche a caixa de diálogo e, em seguida, clique em **OK** para ir para a página **Parâmetros do Sistema**.[![Conectar-se ao LCS](./media/connect-to-lcs-crop-1024x365.png "Conectar-se ao LCS")](./media/connect-to-lcs-crop.png)
2.  Selecione o projeto do Lifecycle Services para se conectar.
3.  Selecione as bibliotecas do BPM (dentro do projeto selecionado) para recuperar gravações de tarefas delas.
4.  Defina a ordem de exibição das bibliotecas do BPM. Isso determina a ordem em que as gravações de tarefas das bibliotecas irão aparecer no painel de **Ajuda**.

Após completar essas etapas, você pode abrir o painel de **Ajuda** e clicar na aba **Guias de tarefas**. Agora você verá as guias da tarefa que se aplicam à página que está sendo atualmente usada no Dynamics 365 for Operations. Se nenhum guia de tarefa for encontrado, você pode inserir palavra-chave para refinar a pesquisa.

### <a name="showing-translated-task-guides"></a>Exibindo guias de tarefa traduzidos

Guias de tarefa traduzidas foram fornecidas primeiro na Biblioteca Unificada de APQC de maio de 2016, e na biblioteca Introdução. No Microsoft Dynamics 365 for Operations, para ver a ajuda da guia de tarefas localizadas, certifique-se de que você está conectado à biblioteca de maio. O idioma que aparece em uma guia de tarefas é controlado para cada usuário pelas configurações de Idioma em **Opções** &gt; **Preferências**. **Observação:** Embora muitos guias de tarefa tem sido traduzidos, agora o cliente Dynamics 365 for Operations não está mostrando os nomes de guia tarefa traduzidos. Além disso, somente as guias de tarefas que foram lançadas em fevereiro de 2016 estão disponíveis em tradução na biblioteca de maio. Lançaremos uma biblioteca atualizada com traduções adicionais.

-   Se uma guia de tarefa foi traduzida, quando você abrir esse guia de tarefa, todo o texto do guia de tarefa será exibido no idioma selecionado.
-   Se uma guia de tarefa ainda não foi traduzida, quando você abrir esse guia de tarefa, apenas umas partes do texto (o texto dos controles) aparecerá em seu idioma selecionado.

## <a name="creating-custom-help"></a>Criando ajuda personalizada
Você pode criar ajuda personalizada para sua implementação do Dynamics 365 for Operations criando registros de tarefa que refletem sua implementação, e salvando-os em uma biblioteca de processo comercial de LCS. Para parceiros, se você promover uma biblioteca como sendo uma biblioteca corporativa, e incluí-la em uma solução, ela estará disponível para os clientes. Você também pode fazer uma cópia da biblioteca global unificada de APQC e, em seguida, abrir a cópia, abrir os registros de tarefa a partir dela, modificá-los, e salvar os registros com suas alterações. Para obter mais informações [Como criar um registro de tarefa para usar como documentação ou treinamento](../user-interface/task-recorder.md).

<a name="see-also"></a>Consulte também
--------

[Visão geral da ajuda](help-overview.md)

[Visão geral do Gravador de tarefas](../user-interface/task-recorder.md)

[Como criar um registro de tarefa para usar como documentação ou treinamento](../user-interface/task-recorder-training-docs.md)

[Criar novas bibliotecas de treinamento para o Dynamics 365 for Operations nos serviços de ciclo de vida usando o Gravador de Tarefas (link externo)](https://docs.com/mufife/163372c6-f366-4c5a-94fa-93e2c25f878a/creating-new-training-libraries-for-dynamics-ax)


