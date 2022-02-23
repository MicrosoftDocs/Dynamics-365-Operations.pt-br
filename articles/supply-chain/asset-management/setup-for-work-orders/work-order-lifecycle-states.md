---
title: Estados de ciclo de vida da ordem de serviço
description: Este tópico explica os estados de ciclo de vida da ordem de serviço no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderLifecycleState, EntAssetWorkOrderLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2a8052942ff97c9e8033d5915723e82c42f964c8
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021570"
---
# <a name="work-order-lifecycle-states"></a>Estados de ciclo de vida da ordem de serviço


[!include [banner](../../includes/banner.md)]

 

Os estados de ciclo de vida da ordem de serviço definem os estados pelos quais uma ordem de serviço pode passar. Exemplos incluem **Criado**, **Agendado**, **Em andamento** e **Encerrado**. Os estados de ciclo de vida da ordem de serviço podem ser atualizados manualmente em uma ordem de serviço, ou podem ser automaticamente atualizados (por exemplo, durante o agendamento da ordem de serviço).

Os estados de ciclo de vida da ordem de serviço necessários para as ordens de serviço devem ser anexados a estágios do projeto correspondentes na página **Parâmetros de gerenciamento e contabilidade de projetos** (**Gerenciamento e contabilidade de projeto**\> **Parâmetros de gerenciamento e contabilidade de projetos**). Primeiramente, configure os estágios do projeto em Gerenciamento e contabilidade de projeto. Em seguida, configure os estados de ciclo de vida da ordem de serviço e os modelos de ciclo de vida da ordem de serviço em Gerenciamento de Ativos.

A tabela a seguir descreve as opções nas seções **Ordem de serviço** e **Agenda** na Guia Rápida **Geral** da página **Estado de ciclo de vida da ordem de serviço** (**Gerenciamento de Ativos**\> **Configuração**\> **Ordens de serviço**\> **Estados de ciclo de vida**).

![Página de estados do ciclo de vida da ordem de serviço](media/09-setup-for-work-orders.png)

| Nome da opção                   | Descrição |
|-------------------------------|-------------|
| Com Atividade                        | Defina essa opção como **Sim** se a ordem de serviço deverá estar ativa quando estiver neste estado de ciclo de vida. |
| Adicionar linha                      | Defina essa opção como **Sim** se os trabalhos da ordem de serviço puderem ser adicionados a uma ordem de serviço que esteja nesse estado de ciclo de vida. |
| Excluir                        | Defina essa opção como **Sim** se uma ordem de serviço puder ser excluída quando estiver neste estado de ciclo de vida. |
| Excluir linha                   | Defina essa opção como **Sim** se os trabalhos da ordem de serviço puderem ser excluídos de uma uma ordem de serviço que esteja nesse estado de ciclo de vida. |
| Permitir agendamento              | Defina essa opção como **Sim** se uma ordem de serviço puder ser agendada quando estiver neste estado de ciclo de vida. |
| Definir início real              | Defina essa opção como **Sim** se o usuário deverá ser solicitado a selecionar uma data inicial e um horário para uma ordem de serviço quando ela for atualizada para este estado de ciclo de vida. |
| Definir final real                | Defina essa opção como **Sim** se o usuário deverá ser solicitado a selecionar uma data final e um horário para uma ordem de serviço quando ela for atualizada para este estado de ciclo de vida. |
| Lançar diários                 | Defina essa opção como **Sim** se os diários de ordem de serviço deverão ser lançados automaticamente quando uma ordem de serviço for atualizada para este estado de ciclo de vida. Se ocorrer um erro durante o lançamento no diário, uma mensagem será exibida, e a atualização do estado de ciclo de vida da ordem de serviço será cancelada. Para exibir as linhas do diário para uma ordem de serviço, selecione **Gerenciamento de Ativos**\> **Comum**\> **Ordens de serviço**\> **Todas as ordens de serviço**, **Ordens de serviço ativas** ou **Minhas ordens de serviço ativas**, selecione a ordem de serviço na lista, e selecione **Diários**. Essa configuração de lançamento automático de ordem de serviço no diário em um estado específico de ciclo de vida é a mesma que quando você seleciona **Lançar diários** na página **Diários de ordem de serviço**.<p>**Observação:** se você definir essa opção como **Sim**, os diários serão lançados automaticamente se nenhum fluxo de trabalho de aprovação foi configurado. Se a sua empresa usa a configuração de aprovação de diário que está na página **Aprovação de diário** (**Gerenciamento e contabilidade de projeto**\> **Configuração**\> **Diários**\> **Aprovação de diário**), um gerente ou funcionário deve validar e lançar os registros de consumo.</p> |
| Processar a lista de verificação de manutenção | Defina essa opção como **Sim** se todas as listas de verificação de manutenção deverão ser processadas quando uma ordem de serviço for atualizada para este estado de ciclo de vida. Como parte desse processo, todos os registros do contador que foram feitos em uma lista de verificação de serviço são lançados, e o resultado da lista de verificação de serviço inteira é avaliado. As linhas da lista de verificação de manutenção com resultados **Aprovado** e **Com falha** são avaliadas e, se houver falha em pelo menos uma linha, a lista de verificação de manutenção inteira será marcada como **Com falha** no Gerenciamento de Ativos. |
| Pronto                         | Defina essa opção como **Sim** se o status da agenda do trabalho da ordem de serviço para todos os trabalhos da ordem de serviço que forem criados em uma ordem de serviço deverá ser atualizado automaticamente como **Pronto** quando a ordem de serviço for atualizada para este estado de ciclo de vida. |
| Início                         | Defina essa opção como **Sim** se o status da agenda do trabalho da ordem de serviço para todos os trabalhos da ordem de serviço que forem criados em uma ordem de serviço deverá ser atualizado automaticamente como **Iniciado** quando a ordem de serviço for atualizada para este estado de ciclo de vida. |
| Fim                           | Defina essa opção como **Sim** se o status da agenda do trabalho da ordem de serviço para todos os trabalhos da ordem de serviço que forem criados em uma ordem de serviço deverá ser atualizado automaticamente como **Encerrado** quando a ordem de serviço for atualizada para este estado de ciclo de vida. |
| Excluir linhas da agenda         | Defina essa opção como **Sim** se o agendamento de todos os trabalhos da ordem de serviço que forem criados em uma ordem de serviço deverá ser excluído automaticamente quando a ordem de serviço for atualizada para este estado de ciclo de vida. Em outras palavras, as reservas de capacidade no ativo, o funcionário de manutenção relacionado e as ferramentas relacionadas serão excluídas. Por exemplo, você define essa opção como **Sim** em um estado de ciclo de vida da ordem de serviço que é chamado **Previsto**. Então, quando a ordem de serviço for revertida para esse estado de ciclo de vida porque o reagendamento é necessário, o agendamento poderá ser excluído dessa ordem de serviço. |

## <a name="set-up-project-stages-and-work-order-lifecycle-states"></a>Configurar estágios do projeto e estados de ciclo de vida da ordem de serviço

1. Selecione **Gerenciamento e contabilidade de projetos**\> **Configurar**\> **Parâmetros de gerenciamento e contabilidade de projetos**.
2. Na guia **Estágio do projeto**, para cada estágio que deseja usar, marque a caixa de seleção para cada tipo de projeto que é necessário para suas ordens de serviço. Os tipos de projeto definem regras sobre as tarefas financeiras que são permitidas. Exemplos de tarefas financeiras que incluem a criação de uma previsão, a criação de estimativas e a criação dos saldos iniciais.

    > [!IMPORTANT]
    > Se um estágio de projeto não estiver selecionado para um tipo de projeto, mas o estágio do projeto for usado para um estado de ciclo de vida da ordem de serviço, os projetos por ordem de serviço não serão atualizados da forma apropriada.

3. Feche a página **Parâmetros de gerenciamento e contabilidade de projetos**.
4. Selecione **Gerenciamento de Ativos**\> **Configuração**\> **Ordens de serviço**\> **Estados de ciclo de vida**.
5. Selecione **Novo** para criar um estado de ciclo da ordem de serviço.
6. No campo **Estado de ciclo de vida**, insira uma ID para o estado de ciclo de vida.
7. No campo **Nome**, insira um nome.

    Na Guia Rápida **Detalhes**, o campo **Modelos de ciclo de vida** mostra o número de modelos de ciclo de vida de ordem de serviço que usam esse estado de ciclo de vida.

8. Na Guia Rápida **Geral**, na seção **Ordem de serviço**, selecione as funções que devem estar disponíveis para esse estado de ciclo de vida definindo as opções relevantes como **Sim**. Para obter descrições das opções, consulte a tabela anterior deste tópico.
9. Na seção **Projeto**, no campo **Estágio**, selecione o estágio do projeto que deve estar relacionado a esse estado de ciclo de vida.
10. Na seção **Projeto**, defina a opção **Fechar atividades** como **Sim** se atividades do projeto que estão relacionadas a cada trabalho da ordem de serviço deverão ser fechadas automaticamente quando a ordem de serviço estiver nesse estado de ciclo de vida.

    > [!NOTE]
    > Para encontrar o número da atividade do projeto relacionada a um trabalho da ordem de serviço, selecione **Gerenciamento de ativos**\> **Comum**\> **Ordens de serviço**\> **Todas as ordens de serviço**, **Ordens de serviço ativas** ou **Minhas ordens de serviço ativas**. Abra a ordem de serviço e selecione o trabalho da ordem de serviço. O número da atividade é exibido no campo **Número da atividade** na seção **Projeto** na guia **Geral** da Guia Rápida **Detalhes da linha**.

11. Na seção **Previsão**, defina a opção **Copiar previsão de horas**, **Copiar previsão de item** e/ou **Copiar previsão de despesas** como **Sim** se as previsões do projeto da ordem de serviço devem ser copiadas automaticamente nos diários de ordens de serviço quando a ordem de serviço estiver neste estado de ciclo de vida.
12. Na seção **Agenda**, defina uma das opções como **Sim** se o status da agenda para os trabalhos da ordem de serviço for atualizado quando a ordem de serviço estiver neste estado de ciclo de vida. Para obter descrições das opções **Pronto**, **Iniciar**, **Encerrar** e **Excluir linhas da agenda**, consulte a tabela anterior deste tópico.

    > [!NOTE]
    > Para exibir linhas da agenda que estão relacionadas a trabalhos da ordem de serviço, selecione **Gerenciamento de ativos**\> **Comum**\> **Ordens de serviço**\> **Todas as ordens de serviço**, **Ordens de serviço ativas** ou **Minhas ordens de serviço ativas**. Abra a ordem de serviço, selecione o trabalho da ordem de serviço na Guia Rápida **Trabalhos da ordem de serviço** e exiba as informações relacionadas na Guia Rápida **Detalhes da linha**. O campo **Status** na guia **Agenda** mostra o status do trabalho da ordem de serviço. O campo **Status** pode ser definido como os seguintes valores: **Agendado**, **Pronto**, **Iniciado**, **Parado** e **Encerrado**.

13. Na seção **Solicitações de manutenção**, no campo **estado de ciclo de vida**, selecione o estado de ciclo de vida de solicitação de manutenção para o qual as solicitações de manutenção relacionadas devem ser atualizadas. Essa atualização ocorre automaticamente. Ela poderá ser feita somente se o estado de ciclo de vida da solicitação de manutenção estiver selecionado no modelo do ciclo de vida da solicitação de manutenção usado para a solicitação de manutenção.
14. Na seção **Ativo**, defina a opção **Atualizar BOM de ativos** como **Sim** se todos os itens que serão usados em uma ordem de serviço deverão ser atualizados automaticamente na **BOM de ativos** quando a ordem de serviço for atualizada para este estado de ciclo de vida. Essa configuração pode ser relevante se, por exemplo, o estado de ciclo de vida da ordem de serviço define a ordem de serviço como concluída ou encerrada.
15. Na seção **Grupo de ordens de serviço**, defina a opção **Excluir referência de grupo** como **Sim** se as ordens de serviço que estiverem nesse estado de ciclo de vida deverão ser excluídas automaticamente nos grupos de ordens de serviço.
16. Na Guia Rápida **Validar**, selecione os tipos de validação que deverão ser ativados neste estado de ciclo de vida definindo as opções relevantes como **Sim**. Em seguida, no campo **Tipo** de cada tipo de validação selecionada, selecione o tipo de mensagem que deverá ser exibida se os campos obrigatórios relacionados ao tipo de validação não forem validados. Se você selecionar **Erro**, a atualização do estado de ciclo de vida da ordem de serviço será cancelada até que os campos obrigatórios relacionados sejam atualizados na ordem de serviço.

    - As opções **Tempo de inatividade de manutenção**, **Lista de verificação de manutenção**, **Sintoma da falha**, **Causa da falha** e **Correção da falha** estão relacionados às opções na seção **Obrigatório** na página **Tipos de ordem de serviço** (**Gerenciamento de ativos**\> **Configuração**\> **Ordens de serviço**\> **Tipos de ordem de serviço**). Para ativar as validações, as opções relacionadas também devem ser definidas como **Sim** no tipo de ordem de serviço usado.
    - Se a opção **Lista de verificação de manutenção** estiver definida como **Sim** para o estado de ciclo de vida para o qual uma ordem de serviço é atualizada, a validação será realizada para verificar se as linhas de lista de verificação de manutenção marcadas como **Obrigatório** foram registradas como **Verificado** ou **Não aplicável**. Se nenhum desses registros foi feito nas linhas obrigatórias, um erro informativo ou uma mensagem de aviso será exibida quando a ordem de serviço for atualizada para este estado de ciclo de vida.
    - Se a opção **Custo comprometido** estiver definida como **Sim** para o estado de ciclo de vida para o qual uma ordem de serviço é atualizada, o valor total do custo comprometido (ou seja, o valor total de despesas que a entidade legal se comprometeu a pagar) será calculado para cada trabalho da ordem de serviço. Uma mensagem será exibida se o valor do custo comprometido for maior que 0 (zero). Selecione os tipos de compromisso de custo incluídos na Guia Rápida **Compromissos de custo** na guia **Controle de custos** da página **Parâmetros de gerenciamento e contabilidade de projetos** (**Gerenciamento e contabilidade de projeto**\> **Configuração**\> **Parâmetros de gerenciamento e contabilidade de projetos**).
    - Se a opção **Tempo de inatividade de manutenção** estiver definida como **Sim** para o estado de ciclo de vida para o qual uma ordem de serviço é atualizada, a validação do tempo de inatividade de manutenção será feita no ativo relacionado à ordem de serviço. Se um registro do tempo de inatividade de manutenção foi feito, mas não houver nenhum registro **Encerrado**, a mensagem será exibida quando a ordem de serviço for atualizada para este estado de ciclo de vida.
    - Se a configuração padrão do projeto não inclui todos os estágios necessários para sua configuração de Gerenciamento de Ativos, você poderá configurar estágios do projeto definidos pelo usuário na guia **Estágio do projeto** da página **Parâmetros de gerenciamento e contabilidade de projetos**. A ilustração a seguir mostra a guia **Estágio do projeto** na página **Parâmetros de gerenciamento e contabilidade de projetos**.

    ![Página de configuração de fases do projeto dos vários tipos de projeto](media/10-setup-for-work-orders.png)

> [!NOTE]
> Se o estado de ciclo de vida para o qual você atualizar uma ordem de serviço estiver inativo, os diários relacionados à ordem de serviço mas que ainda não foram lançados serão excluídos automaticamente. Esse comportamento ajuda a garantir a limpeza automática de dados não utilizados. (O estado de ciclo de vida estará inativo se a opção **Ativo** estiver definida como **Não** na Guia Rápida **Geral** da página **estado de ciclo de vida da ordem de serviço**.)
>
> No entanto, se você definir manualmente uma ordem de serviço para que ela fique inativa, os diários relacionados à ordem de serviço mas que ainda não foram lançados **não** serão excluídos automaticamente. (Para desativar manualmente uma ordem de serviço, selecione **Gerenciamento de ativos**\> **Comum**\> **Ordens de serviço**\> **Todas as ordens de serviço** ou **Ordens de serviço ativas**. Abra a ordem de serviço e alterne para a exibição do **Cabeçalho**. Na Guia Rápida **Geral**, selecione **Editar** e defina a opção **Ativo** como **Não**.)

## <a name="relations-among-work-order-lifecycle-models-work-order-types-and-work-order-lifecycle-states"></a>Relações entre modelos de ciclo de vida, tipos de ordem de serviço e estados de ciclo de vida da ordem serviço

Os modelos de ciclo de vida fazem referência aos fluxos de trabalho, e os estados de ciclo de vida são selecionados em um modelo de ciclo de vida em ordem sequencial. Os modelos de ciclo de vida são configurados nos tipos de ordem de serviço. Os tipos de ordem de serviço determinam o tamanho ou a extensão dos fluxos de trabalho e dos processos de trabalho. Por exemplo, **Manutenção**, que é um tipo de ordem de serviço padrão, pode estar relacionada a um modelo de ciclo de vida da ordem da serviço que tenha vários estados de ciclo de vida. Por outro lado, você pode ter um tipo de ordem de serviço **Corretivo** que é usado para ordens de serviço que não foram agendadas ou para ordens de serviço em que o trabalho foi concluído antes que a ordem de serviço fosse feita devido a uma situação urgente. Este tipo de ordem de serviço pode estar relacionada a um modelo de ciclo de vida da ordem de serviço que tenha somente alguns estados de ciclo de vida.

O motivo de usar tipos é que quando um tipo é definido em, por exemplo, uma ordem de serviço ou um ativo, os processos de trabalho relacionados (estados de ciclo de vida) são definidos automaticamente. Para obter mais informações sobre como configurar tipos de ordem de serviço, consulte [Tipos de ordem de serviço](../setup-for-work-orders/work-order-types.md).

> [!NOTE]
> Os estados de ciclo de vida, os modelos de ciclo de vida e os tipos são aplicáveis a locais funcionais, ativos e solicitações de manutenção, além das ordens de serviço.

A ilustração a seguir mostra a relação entre os tipos de ordem de serviço, os modelos de ciclo de vida e os estados de ciclo de vida.

![Página de tipos de ordem de serviço comparada à página de modelos de ciclo de vida de ordem de serviço](media/11-setup-for-work-orders.png)

## <a name="work-order-lifecycle-models"></a>Modelos de ciclo de vida da ordem de serviço

Depois que você criar os estados de ciclo de vida da ordem de serviço que são necessários para suas ordens de serviço, eles poderão ser divididos em modelos de ciclo de vida da ordem de serviço. No mínimo, é necessário criar um modelo de ciclo de vida padrão.

1. Selecione **Gerenciamento de Ativos**\> **Configuração**\> **Ordens de serviço**\> **Modelos de ciclo de vida**.
2. Selecione **Novo** para criar um modelo de ciclo da ordem de serviço.
3. No campo **Modelo de ciclo de vida**, insira a ID do modelo de ciclo de vida.
4. No campo **Nome**, insira um nome.

    Na Guia Rápida **Detalhes**, o campo **Estados de ciclo de vida** mostra o número de estados de ciclo de vida selecionados no modelo de ciclo de vida. O campo **Tipos de ordem de serviço** mostra o número de tipos de ordem de serviço que usam esse modelo de ciclo de vida.

5. Na Guia Rápida **Estados de ciclo de vida**, selecione os estados de ciclo de vida que devem ser incluídos no modelo de ciclo de vida:

    - Para incluir um estado de ciclo de vida no modelo de ciclo de vida, selecione-o na seção **Estados de ciclo de vida restantes** e selecione o botão de seta para a direita ![Seta para a direita](media/12-setup-for-work-orders.png) para movê-lo até a seção **Estados de ciclo de vida selecionados**.
    - Para incluir todos os estados de ciclo de vida disponíveis no modelo de ciclo de vida, selecione o botão **Selecionar todos os estágios disponíveis** ![Selecionar todos os estágios disponíveis](media/13-setup-for-work-orders.png). Todos os estados de ciclo de vida são movidos para a seção **Estados de ciclo de vida selecionados**.
    - Para remover um estado de ciclo de vida do modelo de ciclo de vida, selecione-o na seção **Estados de ciclo de vida selecionados** e selecione o botão de seta para a esquerda ![Seta para a esquerda](media/14-setup-for-work-orders.png) para movê-lo até a seção **Estados de ciclo de vida restantes**.

6. Selecione **Atualizações do estado de ciclo de vida** para definir os estados de ciclo de vida que podem acompanhar um estado de ciclo de vida selecionado.
7. Na Guia Rápida **Atualizações**, no campo **Estado agendado**, selecione o estado de ciclo de vida que sempre deverá ser selecionado para uma ordem de serviço para a qual você concluiu o agendamento da ordem de serviço, independentemente estado de ciclo de vida anterior da ordem de serviço.
8. No campo **Estado de ciclo de vida não agendado**, selecione o estado de ciclo de vida que sempre deverá ser selecionado para uma ordem de serviço se o agendamento da ordem de serviço for excluído.
9. Salve o modelo de ciclo de vida da ordem de serviço.

![Página de modelos de ciclo de vida da ordem de serviço](media/15-setup-for-work-orders.png)
