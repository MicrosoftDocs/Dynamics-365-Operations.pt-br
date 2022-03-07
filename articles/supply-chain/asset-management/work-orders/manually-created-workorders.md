---
title: Ordens de serviço criadas manualmente
description: Este tópico explica como criar ordens de serviço manualmente no Gerenciamento de Ativos.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderTableCreateRelated, EntAssetWorkOrderTableCreate, EntAssetWorkOrderTableCopy
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: a755fa579d929056296c5512f976d15c4808c336b6688b891a4712051e15e9a1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750091"
---
# <a name="manually-created-work-orders"></a>Ordens de serviço criadas manualmente

[!include [banner](../../includes/banner.md)]


É possível criar ordens de serviço manualmente de duas formas:

- Na página **Todas as ordens de serviço** ou **Ordens de serviço ativas** 
- Na página **Todas as solicitações de manutenção**, **Solicitações de manutenção ativas** ou **Minhas solicitações de manutenção de local funcional** 

## <a name="create-work-order"></a>Criar ordem de serviço

1. Selecione **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

2. Selecione **Novo**.

3. Na caixa de diálogo **Criar ordem de serviço**, selecione um tipo de ordem de serviço no campo **Tipo de ordem de serviço**.

4. Se necessário, selecione uma **Descrição**.

5. Selecione o ativo no campo **Ativo**.

>[!NOTE]
>Quando você seleciona um ativo, três guias podem ficar disponíveis no menu suspenso **Ativo**: 

- **Ativos ativos** - Esta guia contém uma lista de todos os ativos com o estado de ciclo de vida do ativo "Ativo". 
- **Exibição de ativo** - Esta guia apresenta um modo de exibição de árvore dos locais funcionais e dos ativos instalados nesses locais.
- **Meus ativos** - Esta guia contém os ativos relacionados aos locais funcionais aos quais você (o trabalhador conectado ao sistema) pode ser atribuído. (Para obter informações sobre a configuração, consulte [Funcionários de manutenção e grupos de trabalhadores](../setup-for-objects/workers-and-worker-groups.md).) Se nenhum local funcional estiver configurado em um trabalhador em [Funcionários de manutenção e grupos de trabalhadores](../setup-for-objects/workers-and-worker-groups.md), a guia **Meus ativos** não estará disponível. 

6. No campo **Tipo de trabalho de manutenção**, selecione o tipo de trabalho de manutenção para a ordem de serviço.

7. Se necessário, selecione **Grade do tipo de trabalho de manutenção** e **Ofício**.

8. Se necessário, você pode alterar o nível de serviço da ordem de serviço no campo **Nível de serviço**.

9. Selecione a **Data de início esperada** e a **Data de término esperada** nos campos relacionados.

10. Clique em **OK** para criar a ordem de serviço.

11. Na página de listagem **Todas as ordens de serviço**, é possível editar a ordem de serviço conforme o necessário.

Observe os seguintes pontos:

- Na exibição de detalhes da página de listagem **Todas ordens de serviço**, você pode incluir vários ativos para uma ordem de serviço, adicionando linhas na Guia Rápida **Trabalhos de manutenção da ordem de serviço**. Em um ativo, você pode selecionar apenas os tipos de trabalho de manutenção definidos no tipo de ativo selecionado no ativo.  

- Se você alterar o nível de serviço ou a severidade de um ativo depois de já ter usado o ativo em uma ordem de serviço, o nível de serviço ou a severidade na ordem de serviço não será atualizada de forma correspondente. Para obter mais informações sobre níveis de serviço e severidades, consulte [Níveis de serviço do ativo](../setup-for-objects/object-priorities.md) e [Tipos de severidade do ativo](../setup-for-objects/object-criticalities.md).

- A severidade em uma ordem de serviço é recalculada sempre que um trabalho da ordem de serviço é adicionado ou excluído da ordem de serviço.

- Na exibição de detalhes **Todas as ordens de serviço** > guia **Cabeçalho** > Guia Rápida **Agendar**, você pode selecionar um grupo de funcionários de manutenção responsáveis ou um funcionário de manutenção responsável nos campos **Grupo responsável** ou **Responsável**. Essas configurações podem ser alteradas enquanto a ordem de serviço está ativa. Por exemplo, elas podem ser alteradas quando o estado de ciclo de vida da ordem de serviço é alterado. A seleção automática feita durante a criação da ordem de serviço é baseada na configuração na página **Funcionários de manutenção responsáveis**. Se você adicionar ou remover trabalhos da ordem de serviço após ter criado uma ordem de serviço e os campos **Grupo responsável** e **Responsável** estiverem em branco quando você atualizar a ordem de serviço, o Gerenciamento de Ativos tentará encontrar um grupo de funcionários de manutenção responsáveis ou um funcionário de manutenção responsável para obter uma possível correspondência na página de configuração. Se o campo **Grupo responsável** ou **Responsável** já estiver definido quando você atualizar a ordem de serviço, nenhuma alteração será feita. Para obter informações sobre funcionários de manutenção responsáveis e grupos de funcionários, consulte [Funcionários de manutenção responsáveis](../setup-for-maintenance-requests/responsible-workers.md).

- Na página [Status de manutenção](../controlling-and-reporting/maintenance-status.md), você pode fazer um cálculo para obter uma visão geral da carga de trabalho de ordens de serviço recebidas e concluídas.  

- Na exibição de detalhes da página **Todas as ordens de serviço**, na Guia Rápida **Detalhes da linha**, você pode usar os campos **Latitude** e **Longitude** para adicionar coordenadas geográficas para o ativo selecionado no trabalho da ordem de serviço.  


## <a name="create-related-work-order"></a>Criar ordem de serviço relacionada

Você pode criar uma ordem de serviço relacionada a uma ordem de serviço existente. Esse recurso é útil se você, por exemplo, quiser trabalhar com ordens de serviço primárias e secundárias. Uma nova ordem de serviço é baseada em um trabalho da ordem de serviço de uma ordem de serviço existente.

1. Selecione **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

2. Selecione a ordem de serviço para criar uma ordem de serviço relacionada.

3. No Painel de Ação, na guia **Ordem de serviço**, no grupo **Novo**, selecione **Ordem de serviço relacionada**.

4. Na caixa de diálogo **Criar ordem de serviço relacionada**, no campo **Trabalho da ordem de serviço**, selecione o trabalho da ordem de serviço para o qual criar uma ordem de serviço relacionada.

5. No campo **Tipo de trabalho de manutenção**, selecione o tipo de trabalho de manutenção.

6. Nos campos **Grade do tipo de trabalho de manutenção** e **Ofício**, selecione um tipo de trabalho de manutenção e um ofício relacionados, conforme necessário.

7. Se essa for a primeira ordem de serviço relacionada criada para a ordem de serviço selecionada, siga estas etapas:
    1. Selecione a opção **Nova ordem de serviço**.
    2. No campo **Tipo de ordem de serviço**, selecione um tipo de ordem de serviço.
    3. Em **Descrição**, insira uma descrição.
    4. Altere o nível de serviço da ordem de serviço no campo **Nível de serviço**, conforme necessário.
    5. Nos campos **Data de início esperada** e **Data de término esperada**, selecione as datas de início e término esperadas.
    6. Selecione **OK**. A nova ordem de serviço relacionada é exibida na página de listagem **Todas as ordens de serviço**.  

8. Se a ordem de serviço para a qual você está criando essa ordem de serviço relacionada já tiver ordens de serviço relacionadas, siga estas etapas para adicionar um novo trabalho de ordem de serviço a uma ordem de serviço relacionada existente:
    1. Selecione a opção **Adicionar à ordem de serviço relacionada**.
    2. No campo **Ordem de serviço**, selecione a ordem de serviço relacionada à qual adicionar um novo trabalho da ordem de serviço.
    3. Altere o nível de serviço da ordem de serviço no campo **Nível de serviço**, conforme necessário.
    4. Nos campos **Data de início esperada** e **Data de término esperada**, altere as datas de início e término esperadas, conforme necessário.
    5. Selecione **OK**. O trabalho da ordem de serviço é adicionado à ordem de serviço relacionada.

A ilustração a seguir mostra um exemplo da caixa de diálogo **Criar ordem de serviço relacionada**.

![Figura 1.](media/03-work-orders.png)

>[!NOTE]
>Se você configurou uma máscara da ordem de serviço relacionada em **Parâmetros de gerenciamento de ativos** > guia **Ordens de serviço** > campo **Máscara da ordem de serviço relacionada**, as IDs da ordem de serviço serão criadas de acordo com a configuração da máscara. Se nenhuma máscara da ordem de serviço relacionada estiver configurada, a próxima ID da ordem de serviço disponível será usada para ordens de serviço relacionadas.

## <a name="copy-a-work-order"></a>Copiar uma ordem de serviço

É possível criar uma nova ordem de serviço rapidamente por meio de uma ordem de serviço existente. Essa forma de trabalhar com ordens de serviço é diferente de criar ordens de serviço com base em [planos de manutenção](../preventive-and-reactive-maintenance/maintenance-plans.md). É útil se, por exemplo, uma ordem de serviço tiver vários trabalhos de ordem de serviço, e esses vários trabalhos tiverem de ser concluídos em ativos diferentes em intervalos regulares.

1. Selecione **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

2. Selecione a ordem de serviço da qual copiar o conteúdo.

3. No Painel de Ação > guia **Ordem de serviço** > grupo **Novo**, selecione **Copiar ordem de serviço**.

4. A configuração da ordem de serviço selecionada é mostrada. Você pode editar alguns campos, conforme necessário.

5. Selecione **OK** para criar a nova ordem de serviço.

6. Na página de listagem **Todas as ordens de serviço**, é possível editar a ordem de serviço conforme o necessário.

>[!NOTE]
>Quando a nova ordem de serviço for criada, algumas informações serão copiadas diretamente da existente. Informações sobre previsões, ferramentas, listas de verificação de manutenção, local funcional, endereços e agendamentos não são copiados. Em vez disso, são inicializados na configuração atual no Gerenciamento de Ativos. Portanto, se essas informações tiverem sido alteradas entre o momento em que a primeira ordem de serviço foi criada e o momento em que você fez uma cópia da ordem de serviço, as alterações serão incluídas na nova ordem de serviço. Os exemplos incluem alterações nas previsões e atualizações de listas de verificação de manutenção.

A ilustração a seguir mostra um exemplo da caixa de diálogo **Copiar ordem de serviço**.

![Figura 2.](media/04-work-orders.png)


## <a name="create-a-work-order-based-on-a-maintenance-request"></a>Criar uma ordem de serviço com base em uma solicitação de manutenção

1. Selecione **Gerenciamento de ativos** > **Comum** > **Solicitações de manutenção** > **Todas as solicitações de manutenção** ou **Solicitações de manutenção ativas**.

2. Selecione a solicitação de manutenção para a qual criar uma ordem de serviço e clique em **Editar**.

3. No Painel de Ação > guia **Solicitação de manutenção** > grupo **Novo**, selecione **Ordem de serviço**.

4. Na caixa de diálogo **Ordem de serviço**, defina os campos. Se um tipo de trabalho de manutenção tiver sido selecionado na solicitação de manutenção, você poderá selecionar outro tipo de trabalho de manutenção ao criar a ordem de serviço, se necessário.

5. Selecione **OK**. Uma mensagem informa que a ordem de serviço foi criada.

6. Para exibir as ordens de serviço vinculadas a uma solicitação de manutenção, na página de listagem **Todas as solicitações de manutenção** ou **Solicitações de manutenção ativas**, selecione a solicitação de manutenção. Em seguida, no Painel de Ação, na guia **Solicitação de manutenção**, no grupo **Novo**, selecione **Ordens de serviço**.


A ilustração a seguir mostra um exemplo da caixa de diálogo **Criar ordem de serviço**.

![Figura 3.](media/05-work-orders.png)


>[!NOTE]
>Se quiser que as ordens de serviço sejam criadas automaticamente, você pode agendar trabalhos de plano de manutenção ou pode configurar a opção de criação automática de [planos de manutenção](../preventive-and-reactive-maintenance/maintenance-plans.md) ou [rounds de manutenção](../preventive-and-reactive-maintenance/maintenance-rounds.md) em um ativo. As ordens de serviço criadas com base em solicitações de manutenção na página de listagem **Todos os agendamentos de manutenção** possuem os tipos de trabalho de manutenção selecionados nas solicitações de manutenção.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]