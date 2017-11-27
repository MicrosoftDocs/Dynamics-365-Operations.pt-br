---
title: Conectar o sistema de Ajuda
description: "Este tópico descreve os componentes do sistema de Ajuda do Microsoft Dynamics 365 for Finance and Operations, fornecendo uma visão geral de como conectá-los e um resumo de como criar a ajuda personalizada."
author: margoc
manager: AnnBe
ms.date: 09/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: c0942b66859da3659be49b19986bfd146ac43130
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="connect-the-help-system"></a>Conectar o sistema de Ajuda

[!include[banner](../includes/banner.md)]


Este tópico descreve os componentes do sistema de Ajuda do Microsoft Dynamics 365 for Finance and Operations. Ele fornece uma visão geral de como conectar esses componentes e um resumo de como criar a ajuda personalizada. 

## <a name="help-architecture"></a>Arquitetura de ajuda
A ilustração a seguir mostra as partes do sistema de Ajuda do Finance and Operations. O sistema de Ajuda do produto traz artigos do site do Finance and Operations em https://docs.microsoft.com, bem como guias de tarefas armazenadas no Modelador de processo de negócios do Lifecycle Services (LCS). 
> [!NOTE]
> Os recursos listados no diagrama com um asterisco (\*) estão planejados, mas ainda não estão disponíveis. [![Arquitetura de ajuda](./media/help-architecture.png)](./media/help-architecture.png)


## <a name="connecting-the-help-system"></a>Conectando o sistema de Ajuda
> [!NOTE]
> A guia **Guias de tarefas** não está disponível no Microsoft Dynamics 365 for Talent e no Microsoft Dynamics 365 for Retail. Estamos trabalhando atualmente para habilitar essa funcionalidade em uma versão futura. As guias de tarefas da experiência de Introdução ao Talent permanecerão disponíveis para a funcionalidade básica. A ajuda de procedimento também está disponível no site docs.microsoft.com ([docs.microsoft.com/dynamics365/unified-operations](../../index.md)) para ambos, Retail e Talent.
 

Usando a página de **Parâmetros do Sistema**, os administradores de sistema conectam as partes do sistema de Ajuda para uma implementação. [![Formulário de parâmetros do sistema com configurações de ajuda](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) Na página **Parâmetros do sistema**, siga estas etapas:

> [!IMPORTANT]
> A primeira vez que você abrir a guia de **Ajuda** é necessário conectar-se ao Lifecycle Services. Certifique-se de clicar no link no meio do formulário, aguarda a conexão, feche a caixa de diálogo e, em seguida, clique em **OK** para ir para a página **Parâmetros do Sistema**.[![Conectar-se ao LCS](./media/connect-to-lcs-crop-1024x365.png "Conectar-se ao LCS")](./media/connect-to-lcs-crop.png)

1.  Selecione o projeto do Lifecycle Services para se conectar.
2.  Selecione as bibliotecas do BPM (dentro do projeto selecionado) para recuperar gravações de tarefas delas.
    - Referente ao Finance and Operations, conteúdo da Microsoft, selecione a Biblioteca Unificada APQC mais recente para Finance and Operations. 
    - Para o Retail, liberaremos uma biblioteca em breve. 
    - Não é necessário selecionar uma biblioteca para o Talent - a conexão com a biblioteca correta é estabelecida para você. 

3.  Defina a ordem de exibição das bibliotecas do BPM. Isso determina a ordem em que as gravações de tarefas das bibliotecas irão aparecer no painel de **Ajuda**.

Após completar essas etapas, você pode abrir o painel de **Ajuda** e clicar em **Guias de tarefa**. Agora você verá as guias de tarefas que se aplicam à página que está sendo atualmente usada no Finance and Operations. Se nenhum guia de tarefa for encontrado, você pode inserir palavra-chave para refinar a pesquisa.

### <a name="showing-translated-task-guides"></a>Exibindo guias de tarefa traduzidos

Guias de tarefa traduzidas foram fornecidas primeiro na Biblioteca Unificada de APQC de maio de 2016, e na biblioteca Introdução. No Finance and Operations, para ver a ajuda da guia de tarefas localizada, certifique-se de que você está conectado à biblioteca de maio. O idioma que aparece em uma guia de tarefas é controlado para cada usuário pelas configurações de Idioma em **Opções** &gt; **Preferências**. 

> [!NOTE]
> Embora muitas guias de tarefas tenham sido traduzidas, agora o Finance and Operations não está exibindo os nomes das guias de tarefas traduzidos. Além disso, somente as guias de tarefas que foram lançadas em fevereiro de 2016 estão disponíveis em tradução na biblioteca de maio. Lançaremos uma biblioteca atualizada com traduções adicionais.
> -   Se uma guia de tarefa foi traduzida, quando você abrir esse guia de tarefa, todo o texto do guia de tarefa será exibido no idioma selecionado.
> -   Se uma guia de tarefa ainda não foi traduzida, quando você abrir esse guia de tarefa, apenas umas partes do texto (o texto dos controles) aparecerá em seu idioma selecionado.

## <a name="creating-custom-help"></a>Criando ajuda personalizada
Você pode criar ajuda personalizada para o Finance and Operations e para o Retail criando gravações de tarefas que refletem a sua implementação, e salvando-as em uma biblioteca de processo comercial de LCS. Você não pode criar guias de tarefas personalizadas para o Talent. 

Para parceiros, se você promover uma biblioteca como sendo uma biblioteca corporativa, e incluí-la em uma solução, ela estará disponível para os clientes. Você também pode fazer uma cópia da biblioteca global unificada de APQC e, em seguida, abrir a cópia, abrir os registros de tarefa a partir dela, modificá-los, e salvar os registros com suas alterações. Para obter mais informações [Como criar um registro de tarefa para usar como documentação ou treinamento](../../dev-itpro/user-interface/task-recorder.md).

<a name="see-also"></a>Consulte também
--------

[Visão geral da ajuda](help-overview.md)

[Visão geral do Gravador de tarefas](../../dev-itpro/user-interface/task-recorder.md)

[Como criar um registro de tarefa para usar como documentação ou treinamento](../../dev-itpro/user-interface/task-recorder-training-docs.md)





