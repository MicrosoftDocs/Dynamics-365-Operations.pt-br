---
title: Conectar o Sistema de ajuda
description: Este tópico descreve os componentes do sistema de Ajuda dos aplicativos do Finance and Operations, além de fornecer uma visão geral de como conectá-los e um resumo de como criar a ajuda personalizada.
author: margoc
manager: AnnBe
ms.date: 10/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4427388d75c1aef40a978ce35c831d5b714f2562
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3006163"
---
# <a name="connect-the-help-system"></a>Conectar o Sistema de ajuda

[!include [banner](../includes/banner.md)]

Este tópico descreve os componentes do sistema de Ajuda dos aplicativos do Finance and Operations, como Dynamics 365 Finance, Supply Chain Management, Commerce e Human Resources. Ele fornece uma visão geral de como conectar esses componentes e um resumo de como criar a ajuda personalizada.

## <a name="help-architecture"></a>Arquitetura de ajuda

A ilustração a seguir mostra as partes do sistema de Ajuda. O sistema de Ajuda no produto traz artigos de https://docs.microsoft.com, bem como guias de tarefas armazenadas no Modelador de processo de negócios do Lifecycle Services (LCS).

> [!NOTE]
> Os recursos listados no diagrama com um asterisco (\*) estão planejados, mas ainda não estão disponíveis.

[![Arquitetura de ajuda](./media/help-architecture.png)](./media/help-architecture.png)

## <a name="connecting-the-help-system"></a>Conectando o sistema de Ajuda

> [!NOTE]
> No momento, a guia **Guias de tarefas** não está disponível no Dynamics 365 Human Resources nem no Commerce. Estamos trabalhando atualmente para habilitar essa funcionalidade em uma versão futura. As Guias de tarefas da experiência de Introdução ao Human Resources permanecerão disponíveis para a funcionalidade básica. A ajuda de procedimento também está disponível no site docs.microsoft.com para o Human Resources e o Commerce.

Usando a página de **Parâmetros do Sistema**, os administradores de sistema conectam as partes do sistema de Ajuda para uma implementação.

[![Formulário Parâmetros do Sistema com configurações da Ajuda](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)

Na página **Parâmetros do sistema**, siga estas etapas:

> [!IMPORTANT]
> A primeira vez que você abrir a guia de **Ajuda** é necessário conectar-se ao Lifecycle Services. Clique no link no meio do formulário, aguarde a conexão, feche a caixa de diálogo e clique em **OK** para acessar a página **Parâmetros do Sistema**.
>
> [![Conectar-se ao LCS](./media/connect-to-lcs-crop-1024x365.png "Conectar-se ao LCS")](./media/connect-to-lcs-crop.png)

1. Selecione o projeto do Lifecycle Services para se conectar.
2. Selecione as bibliotecas do BPM (dentro do projeto selecionado) para recuperar gravações de tarefas delas.
3. Defina a ordem de exibição das bibliotecas do BPM. Isso determina a ordem em que as gravações de tarefas das bibliotecas irão aparecer no painel de **Ajuda**.

Após concluir essas etapas, você poderá abrir o painel **Ajuda** e clicar na guia **Guias de tarefas**. Agora você verá as guias de tarefas que se aplicam à página em que está agora nos aplicativos do Finance and Operations. Se nenhum guia de tarefa for encontrado, você pode inserir palavra-chave para refinar a pesquisa.

### <a name="showing-translated-task-guides"></a>Exibindo guias de tarefa traduzidos

Guias de tarefa traduzidas foram fornecidas primeiro na Biblioteca Unificada de APQC de maio de 2016, e na biblioteca Introdução. Nos aplicativos do Finance and Operations, para ver a ajuda da guia de tarefas localizada, certifique-se de que você esteja conectado à biblioteca de maio. O idioma que aparece em uma guia de tarefas é controlado para cada usuário pelas configurações de Idioma em **Opções** &gt; **Preferências**.

> [!NOTE]
> Embora muitas guias de tarefas tenham sido traduzidas, no momento, o cliente não está mostrando os nomes de guias de tarefas traduzidos. Além disso, somente as guias de tarefas que foram lançadas em fevereiro de 2016 estão disponíveis em tradução na biblioteca de maio. Lançaremos uma biblioteca atualizada com traduções adicionais.
>
> - Se uma guia de tarefa foi traduzida, quando você abrir esse guia de tarefa, todo o texto do guia de tarefa será exibido no idioma selecionado.
> - Se uma guia de tarefa ainda não foi traduzida, quando você abrir esse guia de tarefa, apenas umas partes do texto (o texto dos controles) aparecerá em seu idioma selecionado.

## <a name="creating-custom-help"></a>Criando ajuda personalizada

Você pode usar guias de tarefa para criar ajuda personalizada ou conectar a um site para o painel da ajuda.

### <a name="create-custom-help-with-task-guides"></a>Criar Ajuda personalizada com guia de tarefas

Você pode criar ajuda personalizada para o Finance, o Supply Chain Management e o Commerce criando gravações de tarefas que refletem a sua implementação e salvando-as em uma biblioteca de processo de negócios do LCS. Não é possível criar guias de tarefas personalizadas para o Human Resources.

Para parceiros, se você promover uma biblioteca como sendo uma biblioteca corporativa, e incluí-la em uma solução, ela estará disponível para os clientes. Você também pode fazer uma cópia da biblioteca global unificada de APQC e, em seguida, abrir a cópia, abrir os registros de tarefa a partir dela, modificá-los, e salvar os registros com suas alterações. Para obter mais informações, consulte [Recursos do Gravador de tarefas](../../dev-itpro/user-interface/task-recorder.md).

### <a name="connect-a-custom-site"></a>Conectar um site personalizado

A Microsoft fornece um white paper e um código de amostra que descreve como criar e conectar um site de ajuda personalizado para o painel de Ajuda. Para obter mais informações, consulte:

- [Criar Ajuda Personalizada para aplicativos do Finance and Operations (white paper)](https://go.microsoft.com/fwlink/?linkid=2041185)
- [Repositório do GitHub de ajuda personalizado](https://github.com/microsoft/dynamics356f-o-custom-help)

## <a name="additional-resources"></a>Recursos adicionais

[Sistema de ajuda](help-overview.md)

[Recursos do Gravador de tarefas](../../dev-itpro/user-interface/task-recorder.md)

[Criar documentação ou treinamento com o Gravador de Tarefas](../../dev-itpro/user-interface/task-recorder-training-docs.md)
