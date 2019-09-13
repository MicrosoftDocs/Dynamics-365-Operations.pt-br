---
title: Ordens de serviço criadas manualmente
description: Este tópico explica como criar ordens de serviço manualmente no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 261448a134a7c1aacfbb4ea6f954ce03a63c23e2
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875503"
---
# <a name="manually-created-work-orders"></a>Ordens de serviço criadas manualmente

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


É possível criar ordens de serviço manualmente de duas formas:

- em **Todas as ordens de serviço** ou em **Ordens de serviço ativas**  
- em **Todas as solicitações de manutenção** ou **Solicitações de manutenção ativas** ou **Minhas solicitações de manutenção de local funcional**  

## <a name="create-work-order"></a>Criar ordem de serviço

1. Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

2. Clique no botão **Novo**.

3. Na lista suspensa **Criar ordem de serviço**, selecione um tipo de ordem de serviço.

4. Se necessário, selecione uma descrição.

5. Selecione o ativo para a ordem de serviço e também como um tipo de trabalho de manutenção.

>[!NOTE]
>Quando você seleciona um ativo, três guias podem estar disponíveis: A guia **Meus ativos** contém ativos relacionados aos locais funcionais para os quais você (o funcionário que está conectado no sistema) pode estar alocado (configurar em [Funcionários de manutenção e grupos de trabalhadores](../setup-for-objects/workers-and-worker-groups.md)). Se nenhum local funcional for configurado em um funcionário na guia [Funcionários de manutenção e grupos de trabalhadores](../setup-for-objects/workers-and-worker-groups.md), a guia **Meus ativos** não ficará visível. A guia **Ativos ativos** contém uma lista de todos os ativos com o estado de ciclo de vida do ativo "Ativo". A guia **Exibição de ativo** exibe um modo de exibição de árvore dos locais funcionais e ativos instalados nesses locais.

6. Se necessário, selecione **Grade do tipo de trabalho de manutenção** e **Ofício**.

7. Se necessário, você pode alterar o nível de serviço da ordem de serviço no campo **Nível de serviço**.

8. Selecione as datas de início e de término nos campos relacionados.

9. Clique em **OK** para criar uma nova ordem de serviço.

10. Edite a ordem de serviço em **Todas ordens de serviço**, se necessário.

- Em **Todas ordens de serviço**, você pode adicionar vários ativos para uma ordem de serviço na exibição Detalhes, adicionando linhas na Guia Rápida **Trabalhos de manutenção da ordem de serviço**. Em um ativo você só poderá selecionar os tipos de trabalho de manutenção definidos no tipo de ativo selecionado para o ativo.  
- Se tiver alterado um nível de serviço do ativo ou uma severidade do ativo após ter usado-o em uma ordem de serviço (consulte [Níveis de serviço do ativo](../setup-for-objects/object-priorities.md) e [Severidade do ativo](../setup-for-objects/object-criticalities.md)), o nível de serviço ou a severidade da ordem de serviço será atualizada adequadamente.
- A severidade em uma ordem de serviço é recalculada sempre que uma linha da ordem de serviço for adicionada ou excluída da ordem de serviço.
- Na exibição **Todas as ordens de serviço** Exibição de detalhes > **Cabeçalho** > Guia Rápida **Agendar**, você pode selecionar um grupo de funcionários de manutenção responsáveis ou um funcionário de manutenção responsável nos campos **Grupo responsável** ou **Responsável**. Essas configurações podem ser alteradas desde que a ordem de serviço esteja ativa, por exemplo, quando o estado do ciclo de vida da ordem de trabalho for alterado. A seleção automática criada durante a criação da ordem de serviço é baseada na configuração de **Funcionários de manutenção responsáveis**. Se você adicionar ou remover trabalhos da ordem de serviço após ter criado uma ordem de serviço e os campos **Grupo responsável** e **Responsável** estiverem em branco quando você atualizar a ordem de serviço, o Gerenciamento de Ativos pesquisará uma possível correspondência no formulário de configuração de um grupo de funcionários de manutenção ou de um funcionário de manutenção responsável. Se o campo **Grupo responsável** ou o campo **Responsável** já estiver preenchido quando você atualizar a ordem de serviço, nenhuma alteração será feita. 

- No **Status de manutenção**, você pode fazer um cálculo para obter uma visão geral da carga de trabalho referente às ordens de serviço recebidas e concluídas.  

- Na Guia Rápida **Detalhes da linha**, use os campos **Latitude** e **Longitude** para adicionar coordenadas geográficas para o ativo selecionado no trabalho da ordem de serviço.  

## <a name="create-related-work-order"></a>Criar ordem de serviço relacionada

Você pode criar uma ordem de serviço relacionada para uma ordem de serviço existente se, por exemplo, quiser trabalhar com ordens de serviço principais e secundárias. Uma nova ordem de serviço é baseada em um trabalho da ordem de serviço de uma ordem de serviço existente.

1. Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

2. Selecione a ordem de serviço para a qual você deseja criar uma ordem de serviço relacionada.

3. Clique em **Ordem de serviço relacionada**.

4. Na caixa de diálogo suspensa **Criar ordem de serviço relacionada**, selecione o trabalho da ordem de serviço para o qual você deseja criar uma ordem de serviço relacionada no campo **Trabalho da ordem de serviço**.

5. Selecione um tipo de trabalho de manutenção no campo **Tipo de trabalho de manutenção** e, se necessário, uma grade e ofício do tipo de trabalho de manutenção relacionado nos campos **Grade do tipo de trabalho de manutenção** e **Ofício**.

6. Se esta for a primeira ordem de serviço relacionada que você cria, clique no botão de opção **Nova ordem de serviço**.

7. Selecione um **Tipo de ordem de serviço** e uma **Descrição** nos campos relacionados.

8. Se necessário, altere o nível de serviço da ordem de serviço no campo **Nível de serviço**.

9. Insira as datas de início e de término esperadas nos campos relacionados.

10. Clique em **OK**. A nova ordem de serviço relacionada é mostrada na lista **Todas as ordens de serviço**.

11. Se criar uma ordem de serviço relacionada em uma ordem que já tem ordens de serviços, você poderá adicionar o trabalho da ordem de serviço em um já relacionada. Isso é feito clicando no botão de opção **Adicionar à ordem de serviço relacionada** na etapa 6. Em seguida, você seleciona a ordem de serviço relacionada para a qual você deseja adicionar um novo trabalho da ordem de serviço. Edite os campos **Nível de serviço**, **Início esperado** e **Término esperado**, conforme necessário e clique em **OK**. O trabalho da ordem de serviço é adicionado à ordem de serviço relacionada.


![Figura 1](media/03-work-orders.png)

**Observação:** Se você configurou uma máscara da ordem de serviço relacionada no link **Parâmetros de gerenciamento de ativos** > **Ordens de serviço** > campo **Máscara da ordem de serviço relacionada**, as IDs da ordem de serviço serão criadas de acordo com a configuração da máscara. Se nenhuma máscara da ordem de serviço relacionada for configurada, a próxima ID da ordem de serviço disponível será usada para ordens de serviço relacionadas.

## <a name="copy-work-order"></a>Copiar ordem de serviço

É possível criar uma nova ordem de serviço rapidamente usando uma existente. Esta forma de trabalhar com ordens de serviço é diferente de criar ordens de serviço com base em planos de manutenção. É útil se, por exemplo, você tiver uma ordem de serviço que contém vários trabalhos da ordem de serviço com vários trabalhos em ativos diferentes que devem ser concluídos em intervalos regulares.

1. Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

2. Selecione a ordem de serviço da qual você deseja copiar o conteúdo.

3. Clique em **Copiar ordem de serviço**. A configuração da ordem de serviço selecionada é mostrada. Se necessário, você pode editar alguns campos.

4. Clique em **OK** para criar a nova ordem de serviço.

5. Edite a ordem de serviço em **Todas ordens de serviço**, se necessário.

>[!NOTE]
>Quando a nova ordem de serviço for criada, algumas informações serão copiadas diretamente da existente. Informações relacionadas às previsões, às ferramentas, às listas de verificação da manutenção, ao local funcional, aos endereços e ao agendamento não serão copiadas, mas inicializadas da configuração atual no Gerenciamento de Ativos. Isso significa que, se forem feitas alterações nesses dados desde o momento da criação da primeira ordem de serviço até o momento em que você fez uma cópia da ordem de serviço, essas alterações serão incluídas na nova ordem de serviço que você criou. Os exemplos são alterações nas previsões ou em listas de verificação de manutenção atualizadas.


![Figura 2](media/04-work-orders.png)


## <a name="create-work-order-based-on-a-maintenance-request"></a>Criar uma ordem de serviço com base em uma solicitação de manutenção

1. Clique em **Gerenciamento de ativos** > **Comum** > **Solicitações de manutenção** > **Todas as solicitações de manutenção** ou **Solicitações de manutenção ativas**.

2. Selecione a solicitação de manutenção para a qual você deseja criar uma ordem de serviço e clique em **Editar**.

3. Em **Todas as solicitações**, clique em **Ordem de serviço**.

4. Preencha a lista suspensa **Ordem de serviço**. Se um tipo de trabalho de manutenção tiver sido selecionado na solicitação de manutenção, você poderá selecionar outro tipo de trabalho de manutenção, se necessário, ao criar a ordem de serviço.

5. Clique em **OK**. Você verá uma mensagem informando que a ordem de serviço foi criada.

6. Se quiser ver quais ordens de serviços estão conectadas a uma solicitação de manutenção, selecione a solicitação de manutenção nas listas **Todas as solicitações de manutenção** ou **Solicitações de manutenção ativas** e clique no botão **Ordens de serviço**.


![Figura 3](media/05-work-orders.png)


>[!NOTE]
>As ordens de serviço também podem ser criadas automaticamente através do agendamento de trabalhos do plano de manutenção, ou pela configuração de planos de manutenção ou rounds de manutenção de "Criação automática" em um ativo. As ordens de serviço criadas das solicitações de manutenção no **Agendamento de manutenção** são criadas com os tipos de trabalho de manutenção selecionados nas solicitações de manutenção.

