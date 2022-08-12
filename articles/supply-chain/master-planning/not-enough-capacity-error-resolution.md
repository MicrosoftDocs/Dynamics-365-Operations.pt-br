---
title: Corrigir o erro de mecanismo de agendamento 'Não foi possível localizar capacidade suficiente'
description: Este artigo fornece informações sobre os motivos e as resoluções para "Não foi possível agendar a ordem de produção %1. Não foi possível localizar capacidade suficiente".
author: t-benebo
ms.date: 7/29/2021
ms.topic: article
ms.search.form: ProdTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-19
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d4f54c06a07b3cdd0b8fe2cc52614189ff31ba7f
ms.sourcegitcommit: 6b209919de39c15e0ebe4abc9cbcd30618f2af0b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2022
ms.locfileid: "9135589"
---
# <a name="fix-the-not-enough-capacity-could-be-found-scheduling-engine-error"></a>Corrigir o erro de mecanismo de agendamento "Não foi possível localizar capacidade suficiente"

[!include [banner](../includes/banner.md)]

Ao executar o agendamento, você pode receber a seguinte mensagem de erro:

> A ordem de produção %1 não pôde ser agendada. Não foi possível localizar capacidade suficiente.

Há vários motivos para a falha no mecanismo de agendamento e essa mensagem de erro. Este artigo fornece diretrizes que o ajudarão a encontrar a causa raiz do erro e mitigá-la.

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
1. No Painel de Ações, na guia **Recurso**, no grupo **Exibir**, selecione **Capacidade máxima** ou **Capacidade máxima, graficamente** e verifique se há capacidade disponível.

Para revisar a capacidade disponível no grupo de recursos, siga estas etapas.

1. Acesse **Administração da organização \> Recursos \> Grupos de recursos** e selecione um grupo de recursos aplicável à ordem que não pode ser agendada.
1. No Painel de Ações, na guia **Grupo de recursos**, no grupo **Exibir**, selecione **Capacidade máxima** ou **Capacidade máxima, graficamente** e verifique se há capacidade disponível.

## <a name="master-planning-books-a-resource-when-the-resource-calendar-is-closed"></a>O planejamento mestre reserva um recurso quando o calendário de recursos é fechado

Ao usar o planejamento de operações, o planejamento mestre planejará a capacidade de acordo com o calendário do grupo de recursos principal. Ele reserva a operação secundária ao mesmo tempo que a operação principal e não leva em consideração os calendários ou a capacidade da operação secundária. Isso pode resultar na ordem de produção que está sendo planejada em um calendário fechado ou em um horário em que a operação secundária não está disponível (calendário fechado, sem capacidade).

Ao usar o agendamento de trabalho, o planejamento mestre levará em conta a capacidade e o calendário de operações principal e secundária ao agendar a ordem. Para que a ordem seja agendada, os calendários dos recursos de ambas as operações devem ser abertos e ter capacidade disponível.

## <a name="maximum-job-lead-time-is-too-short"></a>O prazo máximo de entrega do trabalho é muito curto

O mecanismo de planejamento não poderá programar uma ordem, se o **Prazo máximo de entrega do trabalho** definido para o seu site for menor do que o prazo de entrega especificado para um item em suas configurações de ordem padrão ou configurações de cobertura.

Para exibir ou editar a configuração do **Prazo máximo de entrega do trabalho** para o seu site, vá para **Controle de produção \> Configuração \> Parâmetros de controle de produção** e abra a guia **Geral**.

Para exibir ou editar as definições de ordem padrão para um item, siga estas etapas:

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Localize e selecione o produto relevante na lista.
1. No Painel de Ações, abra a guia **Gerenciar estoque** e selecione **Definições de ordem padrão**.
1. Expanda a guia rápida **Estoque** e exiba ou edite a configuração do **Prazo de entrega do estoque**, conforme necessário.

Para exibir ou editar as configurações de cobertura para um item, siga estas etapas:

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Localize e selecione o produto relevante na lista.
1. No Painel de Ações, abra a guia **Planejar** e selecione **Cobertura do item**.
1. Abra a guia **Prazo de entrega** e exiba ou edite o valor do **Tempo de produção**, conforme necessário.

## <a name="excessive-quantity-of-required-resources"></a>Quantidade excessiva de recursos necessários

Durante o planejamento, o mecanismo tenta fazer a correspondência entre o conjunto de quantidades de recursos necessários para uma operação de roteiro dos recursos aplicáveis, de acordo com os requisitos de recursos de operação. A definição da quantidade de recursos muito alta pode levar a um roteiro inviável, o que produzirá um erro de planejamento.

Use o procedimento a seguir para verificar a quantidade especificada e os recursos aplicáveis para uma operação de roteiro selecionada, produto e roteiro:

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Localize e selecione o produto relevante na grade.
1. No Painel de Ações, abra a guia **Projetar** e selecione **Roteiro**.
1. Localize e selecione o roteiro relevante na grade.
1. Abra a guia **Visão geral**, na parte inferior da página.
1. Selecione uma operação na lista das operações de roteiro selecionadas.
1. Selecione **Recursos aplicáveis** para abrir uma caixa de diálogo na qual é possível exibir os recursos aplicáveis à operação de roteiro selecionada.
1. Abra a guia **Carga de recursos**. A **Quantidade** mostra a quantidade de recursos necessária para a operação de roteiro selecionada. Exiba e/ou edite-o, conforme necessário.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
