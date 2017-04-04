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

Este tópico descreve os componentes do sistema de ajuda do Microsoft Dynamics 365 para as operações. Fornece uma visão geral de como conectar esses componentes e um resumo como criar a ajuda personalizado. 

<a name="help-architecture"></a>Arquitetura de ajuda
-----------------

A ilustração a seguir mostra as partes do 365 para o sistema de ajuda de operações. O sistema de ajuda de produto de artigos recebe dynamics 365 para o site de operações em https://docs.microsoft.com, bem como a tarefa guia armazenado no Modelador de processo de negócios em serviços (LCS) do ciclo de vida. 
** Observação: ** Recursos relacionados no diagrama a um asterisco (\*) são planejadas, mas ainda não estão disponíveis. [![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)

## <a name="connecting-the-help-system"></a>Conectando o sistema de ajuda
Usando ** parâmetros de sistema ** a página, os administradores de sistema conectam partes do sistema de ajuda para uma implementação. [os parâmetros do sistema![com as configurações da ajuda (]. /media/system-parameters_ops-1024x437.png)](. /media/system-parameters_ops.png) ** ** Parâmetros do sistema na página, acompanham estas etapas:

1.  ** Importante: ** A primeira vez que você abre ** ajuda ** o guia, é necessário conectar serviços do ciclo de vida. Verifique no link no meio do formulário, a conexão espere, feche a caixa de diálogo, clique em OK ** ** para obter ** ** parâmetros do sistema para a página. [! Conectar-se a LCS []. (/media/connect-to-lcs-crop-1024x365.png “Conectam a LCS”)](. /media/connect-to-lcs-crop.png)
2.  Selecione o projeto do Lifecycle Services para se conectar.
3.  Selecione as bibliotecas do BPM (dentro do projeto selecionado) para recuperar gravações de tarefas delas.
4.  Defina a ordem de exibição das bibliotecas do BPM. Isso determina a ordem em que as gravações de tarefas das bibliotecas irão aparecer no painel de **Ajuda**.

Após completar essas etapas, você pode abrir o painel de **Ajuda** e clicar na aba **Guias de tarefas**. Agora você verá as guias da tarefa que se aplicam à página que está sendo atualmente usada no Dynamics 365 for Operations. Se nenhum guia de tarefa for encontrado, você pode inserir palavra-chave para refinar a pesquisa.

### <a name="showing-translated-task-guides"></a>Exibindo guias de tarefa traduzidos

As guias da tarefa foram enviados principalmente na biblioteca APQC unificada de maio de 2016 e, na biblioteca de Guia de saída. No Microsoft Dynamics 365 for Operations, para ver a ajuda da guia de tarefas localizadas, certifique-se de que você está conectado à biblioteca de maio. O idioma que uma guia de tarefas é controlado em aparece para cada usuário por configurações de idioma em opções ** ** &gt; ** preferências **. **Observação:** Embora muitos guias de tarefa tem sido traduzidos, agora o cliente Dynamics 365 for Operations não está mostrando os nomes de guia tarefa traduzidos. Além disso, somente guias de tarefa que foram liberados em fevereiro de 2016 disponíveis na conversão na biblioteca de maio. Lançaremos uma biblioteca atualizada com traduções adicionais.

-   Se uma guia de tarefa foi traduzida, quando você abrir esse guia de tarefa, todo o texto do guia de tarefa será exibido no idioma selecionado.
-   Se uma guia de tarefa ainda não foi traduzida, quando você abrir esse guia de tarefa, apenas umas partes do texto (o texto dos controles) aparecerá em seu idioma selecionado.

## <a name="creating-custom-help"></a>Criando ajuda personalizada
Você pode criar ajuda personalizada para sua implementação do Dynamics 365 for Operations criando registros de tarefa que refletem sua implementação, e salvando-os em uma biblioteca de processo comercial de LCS. Para parceiros, se você promover uma biblioteca como sendo uma biblioteca corporativa, e incluí-la em uma solução, ela estará disponível para os clientes. Você também pode fazer uma cópia da biblioteca global unificada de APQC e, em seguida, abrir a cópia, abrir os registros de tarefa a partir dela, modificá-los, e salvar os registros com suas alterações. Para obter mais informações, consulte [como criar uma tarefa que registros para usar como documentação ou que treina (]. /user-interface/task-recorder.md).

<a name="see-also"></a>Consulte também
--------

[Help overview](help-overview.md)

[Visão geral do task recorder (]. /user-interface/task-recorder.md)

[Como criar um registro de tarefa para usar como documentação ou treinamento](../user-interface/task-recorder-training-docs.md)

[Criando novas bibliotecas de treinamento para dynamics 365 para operações em serviços do ciclo de vida usando o task recorder link (externa)](https://docs.com/mufife/163372c6-f366-4c5a-94fa-93e2c25f878a/creating-new-training-libraries-for-dynamics-ax)


