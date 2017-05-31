---
title: Conectar o sistema de Ajuda
description: "Este tópico descreve os componentes do sistema de ajuda para Microsoft Dynamics 365 for Operations, fornecendo uma visão geral de como conectá-los e um resumo de como criar a ajuda personalizada."
author: margoc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 86c7cb3961ba5170c32979e77aaa5f506ffac8a1
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="connect-the-help-system"></a>Conectar o sistema de Ajuda

[!include[banner](../includes/banner.md)]


Este tópico descreve os componentes do sistema de Ajuda do Microsoft Dynamics 365 for Operations. Ele fornece uma visão geral de como conectar esses componentes e um resumo de como criar a ajuda personalizada. 

<a name="help-architecture"></a>Arquitetura de ajuda
-----------------

A ilustração a seguir mostra as partes do sistema de Ajuda do Microsoft Dynamics 365 for Operations. O sistema de Ajuda do produto traz artigos do site do Dynamics 365 for Operations em https://docs.microsoft.com, bem como guias de tarefa armazenados no Business Process Modeler no Lifecycle Services (LCS). 
**Observação:** Os recursos listados no diagrama com um asterisco (\*) estão planejados, mas ainda não estão disponíveis. [![Arquitetura de ajuda](./media/help-architecture.png)](./media/help-architecture.png)

## <a name="connecting-the-help-system"></a>Conectando o sistema de Ajuda
Usando a página de **Parâmetros do Sistema**, os administradores de sistema conectam as partes do sistema de Ajuda para uma implementação. [![Formulário de parâmetros do sistema com configurações de ajuda](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) Na página **Parâmetros do sistema**, siga estas etapas:

> [!IMPORTANT]
> A primeira vez que você abrir a guia da **Ajuda** é necessário conectar serviços do ciclo de vida.  Certifique-se de clicar no link no meio do formulário, aguarde a conexão, feche a caixa de diálogo e depois clique em **OK** para ir para a página **Parâmetros do Sistema**.[![Conectar-se ao LCS](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)

1.  Selecione o projeto do Lifecycle Services para se conectar.
2.  Selecione as bibliotecas do BPM (dentro do projeto selecionado) para recuperar gravações de tarefas delas.
3.  Defina a ordem de exibição das bibliotecas do BPM. Isso determina a ordem em que as gravações de tarefas das bibliotecas irão aparecer no painel de **Ajuda**.

Após completar essas etapas, você pode abrir o painel de **Ajuda** e clicar na aba **Guias de tarefas**. Agora você verá as guias da tarefa que se aplicam à página que está sendo atualmente usada no Dynamics 365 for Operations. Se nenhum guia de tarefa for encontrado, você pode inserir palavra-chave para refinar a pesquisa.

### <a name="showing-translated-task-guides"></a>Exibindo guias de tarefa traduzidos

Guias de tarefa traduzidas foram fornecidas primeiro na Biblioteca Unificada de APQC de maio de 2016, e na biblioteca Introdução. No Microsoft Dynamics 365 for Operations, para ver a ajuda da guia de tarefas localizadas, certifique-se de que você está conectado à biblioteca de maio. O idioma que aparece em uma guia de tarefas é controlado para cada usuário pelas configurações de Idioma em **Opções** &gt; **Preferências**. 

> [!NOTE]
> Embora muitas guias de tarefa tenham sido traduzidos, agora o cliente Dynamics 365 for Operations não está mostrando os nomes de guia de tarefa traduzidos. Além disso, somente as guias de tarefas que foram lançadas em fevereiro de 2016 estão disponíveis em tradução na biblioteca de maio. Lançaremos uma biblioteca atualizada com traduções adicionais.
> -   Se uma guia de tarefa foi traduzida, quando você abrir esse guia de tarefa, todo o texto do guia de tarefa será exibido no idioma selecionado.
> -   Se uma guia de tarefa ainda não foi traduzida, quando você abrir esse guia de tarefa, apenas umas partes do texto (o texto dos controles) aparecerá em seu idioma selecionado.

## <a name="creating-custom-help"></a>Criando ajuda personalizada
Você pode criar ajuda personalizada para sua implementação do Dynamics 365 for Operations criando registros de tarefa que refletem sua implementação, e salvando-os em uma biblioteca de processo comercial de LCS. Para parceiros, se você promover uma biblioteca como sendo uma biblioteca corporativa, e incluí-la em uma solução, ela estará disponível para os clientes. Você também pode fazer uma cópia da biblioteca global unificada de APQC e, em seguida, abrir a cópia, abrir os registros de tarefa a partir dela, modificá-los, e salvar os registros com suas alterações. Para obter mais informações [Como criar um registro de tarefa para usar como documentação ou treinamento](../user-interface/task-recorder.md).

<a name="see-also"></a>Consulte também
--------

[Visão geral da ajuda](help-overview.md)

[Visão geral do Gravador de tarefas](../user-interface/task-recorder.md)

[Como criar um registro de tarefa para usar como documentação ou treinamento](../user-interface/task-recorder-training-docs.md)





