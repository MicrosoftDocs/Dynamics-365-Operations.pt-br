---
title: "Integração do cliente do Microsoft Project"
description: "Planejar e manter uma agenda de projeto pode ser complexo, por isso os gerentes de projeto precisam usar ferramentas que os ajudem a gerenciar essa tarefa. A integração com o Cliente do Microsoft Project fornece suporte para abrir e gerenciar a estrutura de detalhamento de trabalho de um projeto."
author: KimANelson
manager: AnnBe
ms.date: 12/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjWbsTemplate
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-12-04
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 4a3445417d5ae88e2ff3676962a82921a7ab475d
ms.contentlocale: pt-br
ms.lasthandoff: 03/26/2018

---

# <a name="microsoft-project-client-integration"></a>Integração do cliente do Microsoft Project

[!include [banner](../includes/banner.md)]

Planejar e manter uma agenda de projeto pode ser complexo, por isso os gerentes de projeto precisam usar ferramentas que os ajudem a gerenciar essa tarefa. A integração com o Cliente do Microsoft Project fornece suporte para abrir e gerenciar a estrutura de detalhamento de trabalho de um projeto. O gerente do projeto pode publicar as alterações na estrutura de detalhamento de trabalho do projeto do Finance and Operations.

> [!NOTE]
> Se estiver usando a atualização de julho do Microsoft Dynamics 365 for Finance and Operations, você deverá instalar o KB 4054797 e o 4055884.

## <a name="configure-the-microsoft-project-client-add-in"></a>Configurar o suplemento do Cliente do Microsoft Project
Para habilitar a integração com o Cliente do Microsoft Project, um suplemento do Microsoft Dynamics 365 deve ser instalado no aplicativo do cliente do Microsoft Project do usuário. Isso é feito abrindo o **Espaço de trabalho de gerenciamento de projeto**.

•   Clique em **Configurar o suplemento do cliente do projeto** na seção **Links** > **Configuração** do espaço de trabalho.

•   Clique em **Abrir**, em seguida, clique em **Executar** quando solicitado.

## <a name="open-and-edit-an-existing-draft-work-breakdown-structure-in-microsoft-project-client"></a>Abrir e editar uma estrutura de detalhamento de trabalho de rascunho existente no Cliente do Microsoft Project
Se um projeto no Finance and Operations já tiver uma estrutura de detalhamento de trabalho criada, ela poderá ser aberta no aplicativo do Cliente do Microsoft Project se estiver em um status de rascunho. Para abrir a partir da página **Projeto**, clique no link **Abrir no Microsoft Project** da guia **Plano**. Essa página também pode ser aberta no aplicativo do Cliente do Microsoft Project clicando em **Abrir** na guia **Microsoft Dynamics 365**. Selecione a **Entidade legal** e o **Projeto** na lista.

> [!NOTE]
> Se estiver usando o Internet Explorer como navegador, você precisará clicar em **Salvar** para abrir manualmente do local onde o arquivo foi baixado. Ou clicar em **Salvar e abrir** para abrir o arquivo no Cliente do Microsoft Project. Não renomeie o arquivo ao salvar.

Antes de fazer quaisquer edições no arquivo usando o Cliente do Microsoft Project, você precisará fazer o check-out. Clique em **Check-out** na guia **Microsoft Dynamics 365**. Isso impedirá que outros usuários editem a estrutura de detalhamento de trabalho no Finance and Operations ao mesmo tempo. Para publicar a estrutura de detalhamento de trabalho após concluir alguma edição, clique em **Check-in** na guia **Microsoft Dynamics 365**.

Se uma equipe de projeto já tiver sido adicionada ao projeto em Finance and Operations, a lista de recursos será preenchida com os membros da equipe. Se uma equipe de projeto ainda não tiver sido adicionada ao projeto, você pode selecionar recursos e criar a equipe no Cliente do Microsoft Project clicando no botão **Recursos** na guia **Microsoft Dynamics 365**. 

Os seguintes dados serão sincronizados com o Finance and Operations como parte do processo de check-in:

•   Nome da tarefa

•   Data de início

•   Data de conclusão

•   Predecessores

•   Nomes de recurso

•   Categoria

•   Categoria de recurso

•   Horas de trabalho

•   Observações

•   Prioridade

> [!NOTE]
> Se você adicionar outras colunas ao seu arquivo do Cliente do Microsoft Project, elas não serão salvas no arquivo e não serão exibidas quando o arquivo for aberto novamente.

## <a name="create-the-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a>Criar a estrutura de detalhamento de trabalho para um projeto existente usando o Cliente do Microsoft Project
Para criar uma nova estrutura de detalhamento de trabalho usando o Cliente do Microsoft Project, siga estas etapas:


1.  Abra o Cliente do Microsoft Project.

2.  Na guia **Microsoft Dynamics 365**, clique em **Abrir**.

3.  Selecione a **Entidade legal** do projeto.

4.  Selecione o **Projeto**.

5.  Clique em **Check-out** na guia **Microsoft Dynamics 365**.

6.  Quando estiver pronto para publicar no Finance and Operations, clique em **Check-in** na guia **Microsoft Dynamics 365**.

## <a name="replace-the-existing-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a>Substitua a estrutura de detalhamento de trabalho existente para um projeto existente usando o Cliente do Microsoft Project
Para criar uma nova estrutura de detalhamento de trabalho usando o Cliente do Microsoft Project e substituir uma estrutura de detalhamento de trabalho existente para um projeto existente, siga estas etapas:

1.  Abra o Cliente do Microsoft Project.

2.  Crie a agenda no Cliente do Microsoft Project.

3.  Na guia **Microsoft Dynamics 365**, clique em **Salvar alterações** > **Substituir projeto existente**.

4.  Selecione a **Entidade legal** do projeto.

5.  Selecione o **Projeto**.

6.  Clique em **OK**.

## <a name="create-a-new-project-from-within-microsoft-project-client"></a>Criar um novo projeto no Cliente do Microsoft Project


1.  Abra o Cliente do Microsoft Project.

2.  Crie a agenda no Cliente do Microsoft Project.

3.  Na guia **Microsoft Dynamics 365**, clique em **Salvar alterações** > **Salvar no novo Projeto**.

4.  Selecione a **Entidade legal** do projeto.

5.  Insira a **ID do projeto**, se necessário.

6.  Insira o **Nome do projeto**.

7.  Selecione o **Tipo de projeto**, o **Grupo de projetos** e a **ID do contrato de projeto**. Como alternativa, você pode criar um novo contrato de projeto clicando em **Novo**.

8.  Selecione o **Calendário** a ser usado para os recursos.

11. Clique em **OK**.

