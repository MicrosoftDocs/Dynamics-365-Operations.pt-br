---
title: Configurar a função de Gerente de ausências
description: Este artigo explica como configurar a função Gerente de ausências para o gerenciamento de licenças de funcionários.
author: twheeloc
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace, LeaveAbsenceManager
audience: Application User
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 40f9607fb6fc16b96373141d8d2610538e3fdec7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886092"
---
# <a name="configure-the-absence-manager-role"></a>Configurar a função de Gerente de ausências

>[!Important]
>A funcionalidade mencionada neste artigo está disponível atualmente para clientes individuais de Dynamics 365 Human Resources. Algumas ou todas as funcionalidades estarão disponíveis como parte de uma versão futura na infraestrutura do Finance após a versão Finance 10.0.26.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Em algumas organizações, é possível que os gerentes de pessoal não gerenciem as licenças das equipes. Em vez disso, um gerente de ausências pode lidar com esse processo para membros da equipe em vários departamentos e equipes. Os gerentes de ausências têm os seguintes recursos para o gerenciamento de licenças:

- Analisar e aprovar a folga, com base em uma hierarquia alternativa.
- Exibir saldos de membros da equipe.
- Exibir o calendário de ausências.

## <a name="turn-on-the-feature"></a>Ativar o recurso

1. No espaço de trabalho **Administração do sistema**, selecione **Gerenciamento de recursos**.

2. Na guia **Gerenciamento de recursos**, habilite o recurso **Gerente de ausências para gerenciar a licença**.

## <a name="define-a-custom-hierarchy"></a>Definir uma hierarquia personalizada

A funcionalidade do gerente de ausências usa uma hierarquia personalizada que deve ser configurada.

1. No espaço de trabalho **Administração da organização**, selecione **Tipos de hierarquia de cargo**.

2. Crie um tipo de hierarquia de cargo denominado de **Licença**.

3. No espaço de trabalho **Licença e ausência**, em **Links**, selecione **Parâmetros de licença e ausência**.

4. Na guia **Geral**, na lista suspensa **Hierarquia de ausências**, selecione o tipo de hierarquia **Licença** criado anteriormente. A associação de hierarquia de licenças deve ser concluída para cada entidade legal na qual a funcionalidade do gerente de ausências será usada.

Depois que o tipo de hierarquia é definido, o relatório de hierarquia de cargo deve ser atribuído ao cargo.

1. No espaço de trabalho **Administração da Organização**, selecione **Todos os cargos**.

2. Selecione o cargo ao qual adicionar a hierarquia de licenças.

3. Na guia **Relacionamentos**, selecione **Adicionar**.

4. No campo **Nome da hierarquia**, selecione **Licença**.

5. No campo **Subordinado ao cargo**, insira ou selecione um cargo. O nome do trabalhador é preenchido automaticamente após a seleção de um cargo.

## <a name="assign-the-absence-manager-role-to-a-user"></a>Atribuir a função Gerente de ausências a um usuário

A função Gerente de ausências deve ser atribuída aos funcionários para permitir que eles aprovem ou neguem solicitações de licença.

1. No espaço de trabalho **Administrador do sistema**, selecione **Links**.

2. Na seção **Usuários**, selecione o link **Usuários**.

3. Na lista de usuários, selecione o usuário ao qual atribuir a função Gerente de ausências.

4. Na guia **Função do usuário**, selecione **Atribuir funções**.

5. Na lista, selecione a função **Gerente de ausências**. Em seguida, selecione **OK**.

    > [!IMPORTANT]
    > Verifique se a função Funcionário também foi atribuída ao usuário para o qual você está atribuindo a função Gerente de ausências. Caso contrário, o trabalhador não poderá usar o recurso.

6. Depois de criar a hierarquia de licenças, você pode exibi-la seguindo estas etapas:

    1. No espaço de trabalho **Administração da Organização**, selecione **Hierarquia de cargo**.
    
    2. No campo **Tipo da hierarquia**, selecione **Licença**.

## <a name="absence-manager-workspace"></a>Espaço de trabalho do gerente de ausências

No espaço de trabalho **Autoatendimento para funcionários**, a guia **Gerenciamento de licenças** mostra as informações de ausência sobre os funcionários atribuídos ao gerente de ausências na hierarquia de licenças. Existem algumas opções disponíveis para o gerente de ausências: 
 - Analisar solicitações de folga.</br>
 - Envie uma solicitação de folga em nome de um funcionário.</br>
 - Exiba todos os funcionários atribuídos ao gerente como parte da hierarquia de licenças.</br>
 - Exibir o calendário do gerente de ausências.</br>

No espaço de trabalho **Gerenciamento de licenças**, há duas guias:
 - **Solicitações de folga**: essa guia listará todas as solicitações de folga pendentes que o gerente de ausências pode aprovar. O gerente de ausências pode selecionar vários registros e executar uma ação em relação a eles ao mesmo tempo. Se a exibição de licença entre empresas estiver habilitada, essa lista mostrará solicitações de folga pendentes em todas as entidades legais às quais o gerente têm acesso. Caso contrário, ela mostrará as solicitações de folga pendentes da entidade legal selecionada no momento. </br>
 - **Todos os funcionários**: essa guia listará todos os funcionários atribuídos ao gerente de ausências na hierarquia de licenças. Há várias opções disponíveis para cada funcionário:
    - **Solicitar folga** - envie uma nova solicitação de folga para o funcionário selecionado.</br>
    - **Folga** – exibe saldos, solicitações de folga e solicitações de folga aprovadas para o funcionário selecionado.</br>

## <a name="approve-time-off-requests"></a>Aprovar solicitações de folga

Os gerentes de ausências podem aprovar ou negar solicitações de folga de funcionários. 

> [!IMPORTANT]
> Para que gerentes de ausências possam aprovar ou negar solicitações de folga, o fluxo de trabalho de solicitação de licença deve ser configurado para atribuir itens de trabalho de solicitação de licença para análise.
>
> 1. Na página **Fluxos de trabalho de recursos humanos**, selecione ou crie o fluxo de trabalho de solicitação de licença.
> 2. Selecione a opção **Associar hierarquia** e, em seguida, no campo **Nome da hierarquia**, selecione **Licença**.
> 3. Atualize o fluxo de trabalho no designer de fluxo de trabalho. Em **Tipo de atribuição**, selecione a opção **Hierarquia** e, na guia **Seleção de hierarquia**, selecione **Hierarquia configurável**.
>
> Para obter informações sobre como criar o fluxo de trabalho de solicitações de licença, consulte [Criar um fluxo de trabalho de solicitações de licença](hr-leave-and-absence-workflow.md).

1. No espaço de trabalho **Autoatendimento para funcionários**, selecione a guia **Gerenciamento de licenças**.

2. Na guia **Solicitações de folga**, selecione as solicitações de folga para as quais você deseja executar ações. Você pode selecionar vários registros nessa exibição de lista.

3. Use os botões de ação na parte superior da grade para Aprovar, Negar ou Delegar a solicitação de folga. 

Como alternativa, o usuário também pode usar o bloco **Solicitações de folga** no lado esquerdo para navegar até a lista de todos os itens de trabalho de solicitação de folga. 

## <a name="view-time-off-in-the-calendar"></a>Exibir folga no calendário

Os usuários na função Gerente de ausências podem exibir solicitações de folga no calendário. Siga estas etapas para acessar o calendário de licenças.

> [!IMPORTANT]
> Um administrador do sistema deve configurar as opções de exibição para o calendário do gerente de ausências. Na página **Parâmetros de licença e ausência**, na guia **Calendário**, há opções para ocultar ou mostrar aniversários, ausências sem detalhes, licenças e solicitações de licença pendentes. Há também uma opção para filtrar a opção de exibição calendário por tipo de trabalhador.

1. No espaço de trabalho **Autoatendimento para funcionários**, selecione **Gerenciamento de licenças** e **Calendário do gerente de ausências**.

2. No campo **Data**, insira as datas desejadas.

3. Atualize as opções de exibição, conforme necessário.

O calendário do gerente de ausências mostra todos os registros dos funcionários subordinados ao gerente de ausências na hierarquia de licenças.

## <a name="see-also"></a>Consulte também

- [Visão geral de licença e ausência](hr-leave-and-absence-overview.md)
- [Criar um fluxo de trabalho de solicitação de licença](hr-leave-and-absence-workflow.md)
- [Exibir calendários da equipe e da empresa](hr-employee-self-service-calendar.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
