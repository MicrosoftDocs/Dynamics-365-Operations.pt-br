---
title: Corrigir o erro de mecanismo de agendamento "Não foi possível localizar capacidade suficiente"
description: Este tópico fornece informações sobre os motivos e as resoluções para "Não foi possível agendar a ordem de produção %1. Não foi possível localizar capacidade suficiente".
author: crytt
ms.date: 7/29/2021
ms.topic: article
ms.search.form: ProdTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-19
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 37c990067a0c175d93ecf298866041f4d2afc1bc
ms.sourcegitcommit: ab1455c67f6ee6ca36bec148bea0dbb0f7704eda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "7428906"
---
# <a name="fix-the-not-enough-capacity-could-be-found-scheduling-engine-error"></a>Corrigir o erro de mecanismo de agendamento "Não foi possível localizar capacidade suficiente"

[!include [banner](../includes/banner.md)]

Ao executar o agendamento, você pode receber a seguinte mensagem de erro:

> A ordem de produção %1 não pôde ser agendada. Não foi possível localizar capacidade suficiente.

Há vários motivos para a falha no mecanismo de agendamento e essa mensagem de erro. Este tópico fornece diretrizes que o ajudarão a encontrar a causa raiz do erro e mitigá-la.

## <a name="review-the-applicable-resources"></a>Revisar os recursos aplicáveis

O erro pode ocorrer se nenhum recurso aplicável atender aos requisitos de operação no site da ordem de produção.

Para revisar os recursos aplicáveis, siga estas etapas.

1. Acesse **Controle de produção \> Ordens de produção \> Todas as ordens de produção** e abra ou selecione a ordem de produção que não pode ser agendada.
1. No Painel de Ações, na guia **Ordem de produção**, no grupo **Detalhes de produção**, selecione **Roteiro**.
1. Na página **Roteiro de produção**, selecione a operação e, no Painel de Ações, selecione **Recursos aplicáveis**.
1. Na caixa de diálogo **Recursos aplicáveis**, defina o campo **Usar requisitos de uso para** como *Agendamento de operações* ou *Agendamento de trabalho*, dependendo do tipo de agendamento que você está usando.
1. Verifique se há recursos aplicáveis no site da ordem de produção.

## <a name="review-the-calendars-that-are-associated-with-resources"></a>Revise os calendários associados aos recursos

O erro pode ocorrer se nenhum calendário estiver associado ao recurso ou grupo de recursos ou se o calendário associado não estiver configurado corretamente (por exemplo, se não houver horários de trabalho ou sua eficiência como uma porcentagem for 0 \[zero\]).

Para verificar se um calendário está associado ao recurso ou grupo de recursos, siga estas etapas.

1. Acesse **Controle de produção \> Ordens de produção \> Todas as ordens de produção** e abra ou selecione a ordem de produção que não pode ser agendada.
1. No Painel de Ações, na guia **Ordem de produção**, no grupo **Detalhes de produção**, selecione **Roteiro**.
1. Na página **Roteiro de produção**, selecione a operação e, no Painel de Ações, selecione **Recursos aplicáveis**.
1. Na caixa de diálogo **Recursos aplicáveis**, selecione o recurso e **Exibir recurso**. Como alternativa, selecione e segure ou clique com o botão direito do mouse no campo **Grupo de recursos** selecione **Exibir detalhes**.
1. Na página **Recursos** ou **Grupos de recursos**, na Guia Rápida **Calendários**, verifique se um calendário está associado ao recurso ou ao grupo de recursos.

> [!NOTE]
> Se o erro ocorrer durante o agendamento de operações, você deve verificar se um calendário está associado a todos os grupos de recursos aplicáveis.

Para revisar a configuração do calendário, siga estas etapas.

1. Acesse **Administração da organização \> Configuração \> Calendários \> Calendários** e selecione o calendário associado ao recurso ou grupo de recursos.
1. No Painel de Ações, selecione **Horários de trabalho**.
1. Na página **Horários de trabalho**, verifique se a página não está em branco. Além disso, para os dias em que você está interessado, verifique se o campo **Controle** não está definido como *Fechado*, se horários de trabalho existem e se o campo **Eficiência é percentual** não está definido como *0* (zero).

Se o calendário estiver associado ao calendário base, você também deverá revisar a configuração do calendário base.

> [!NOTE]
> No agendamento de operações, o calendário do grupo de recursos é usado para determinar as datas e horas de início e término de cada operação. Ele também limita o tempo durante o qual o sistema pode agendar uma operação específica para um dia específico em um grupo de recursos específico. Por exemplo, se os horários de trabalho para um grupo de recursos em um dia específico são das 8:00 às 16:00, a carga que uma operação coloca no grupo de recursos não pode exceder a carga que pode ser acomodada em oito horas, independentemente da quantidade de capacidade disponível que o grupo de recursos tem nesse dia. Entretanto, a capacidade disponível pode limitar ainda mais a carga.

## <a name="review-the-scheduling-parameters"></a>Revisar os parâmetros de agendamento

Para garantir um bom desempenho, o mecanismo de agendamento pesquisará um recurso somente por um período específico e um número específico de conflitos de agendamento.

Para revisar os parâmetros de agendamento, siga estas etapas.

1. Acesse **Administração da organização \> Configuração \> Parâmetros de agendamento**.
1. Siga uma destas etapas:

    - Se a opção **Tempo limite de agendamento habilitado** estiver definida como *Não*, vá para a etapa 3.
    - Se a opção **Tempo limite de agendamento habilitado** estiver definida como *Sim*, aumente o valor do campo **Tempo de planejamento máximo por sequência** para dar ao processamento mais tempo de conclusão.

1. Siga uma destas etapas:

    - Se a opção **Tempo limite de otimização de agendamento habilitado** estiver definida como *Não*, vá para a etapa 4.
    - Se a opção **Tempo limite de otimização de agendamento habilitado** estiver definida como *Sim*, aumente o valor do campo **Tempo limite de tentativas de otimização** para dar ao processamento mais tempo de conclusão.

1. Se você alterou qualquer uma das configurações na página, reagende a ordem para tentar novamente.

## <a name="review-capacity"></a>Revisar capacidade

O erro pode ocorrer quando você executa o agendamento finito, mas não há capacidade livre.

Para executar um agendamento de capacidade infinito, siga estas etapas.

1. Acesse **Controle de produção \> Ordens de produção \> Todas as ordens de produção** e selecione ou abra a ordem de produção que não pode ser agendada.
1. No Painel de Ações, na guia **Agendar**, no grupo **Ordens de produção**, selecione **Operações de agendamento** ou **Agendar trabalhos**.
1. Na caixa de diálogo **Agendamento de operações** ou **Agendamento de trabalho**, defina a opção **Capacidade finita** como *Não*.
1. Selecione **OK** para agendar a ordem.

Para revisar a capacidade disponível no recurso, siga estas etapas.

1. Acesse **Administração da organização \> Recursos \> Recursos** e selecione um recurso aplicável à ordem que não pode ser agendada.
1. No Painel de Ações, na guia **Recurso**, no grupo **Exibir**, selecione **Carga de capacidade** ou **Carga de capacidade, graficamente** e verifique se há capacidade disponível.

Para revisar a capacidade disponível no grupo de recursos, siga estas etapas.

1. Acesse **Administração da organização \> Recursos \> Grupos de recursos** e selecione um grupo de recursos aplicável à ordem que não pode ser agendada.
1. No Painel de Ações, na guia **Grupo de recursos**, no grupo **Exibir**, selecione **Carga de capacidade** ou **Carga de capacidade, graficamente** e verifique se há capacidade disponível.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
