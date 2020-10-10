---
title: Atividades de tempo de inatividade de manutenção
description: Este tópico explica como o tempo de inatividade de manutenção é usado para obter uma visão geral da capacidade necessária para executar trabalhos de manutenção em ativos específicos durante um período específico.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetMaintenanceStopCopy, EntAssetMaintenanceStopObject, EntAssetObjectProductionStop, EntAssetProductionStopType, EntAssetMaintenanceStop
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 617fca55226e216197c385c88a9d7a8e3de03b03
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889976"
---
# <a name="maintenance-downtime-activities"></a>Atividades de tempo de inatividade de manutenção

[!include [banner](../../includes/banner.md)]

O tempo de inatividade de manutenção é usado para obter uma visão geral da capacidade necessária para executar trabalhos de manutenção em ativos específicos durante um período específico. Por exemplo, você pode criar um registro do tempo de inatividade de manutenção para a linha de produção 10 no Espaço de Produção 29-A no local de produção 02. O registro do tempo de inatividade de manutenção tem uma data de início e de término indicando o período no qual os ativos relacionados à parada de manutenção não estão disponíveis para produção.

**Atividades do tempo de inatividade de manutenção** é uma visão geral das linhas de agendamento de manutenção e trabalhos de manutenção da ordem de serviço em ativos relacionados durante um período especificado. As linhas relacionadas aos trabalhos de manutenção da ordem de serviço têm uma data de início esperada dentro do período de parada da manutenção. Você pode extrair informações úteis e fazer ajustes em trabalhos de manutenção planejados:

- Obter uma visão geral de períodos de desativação necessários do equipamento de produção (ativos).  
- Obter uma visão geral de manutenção planejada (horas), agrupada por competências (grupos do funcionário de manutenção responsável ou funcionários de manutenção), por exemplo, capacidade máxima de eletricistas, ferreiros ou outros grupos de trabalho de manutenção necessários para executar os trabalhos de manutenção planejada.  
- Faça ajustes em linhas do programa de manutenção ou em trabalhos de manutenção da ordem de serviço relacionadas aos ativos, por exemplo, alterar horas inicial e final esperadas em uma linha ou selecionar outros funcionários de manutenção para otimizar o fluxo de trabalho para funcionários de manutenção e grupos de funcionários de manutenção.

Quando os ativos forem selecionados em um registro de tempo de inatividade de manutenção, todas as linhas de agendamento de manutenção e trabalhos de manutenção da ordem de serviços referentes às ordens de trabalho ativas são incluídos no registro do tempo de inatividade de manutenção.

## <a name="maintenance-downtime-activities"></a>Atividades de tempo de inatividade de manutenção

Clique em **Gerenciamento de ativos** > **Comum** > **Atividades do tempo de inatividade de manutenção** > **Todas atividades do tempo de inatividade de manutenção** para abrir uma lista de todas as atividades do tempo de inatividade de manutenção e para ver algumas informações relacionadas às atividades. Clique em um link na coluna **Atividades do tempo de inatividade de manutenção** para abrir a exibição de detalhes. A ilustração a seguir mostra um exemplo da lista **Atividades do tempo de inatividade de manutenção**.

![Figura 1](media/19-preventive-maintenance.png)


## <a name="create-a-maintenance-downtime-activity"></a>Criar uma atividade do tempo de inatividade de manutenção

1. Clique **Gerenciamento de ativos** > **Comum** > **Atividades do tempo de inatividade de manutenção** > **Todas atividades do tempo de inatividade de manutenção** ou **Atividades do tempo de inatividade de manutenção ativas**.

2. Clique em **Novo**.

3. Insira uma ID no campo **Atividades do tempo de inatividade de manutenção** e um nome no campo **Nome**.

4. Insira o período para a parada de manutenção nos campos **Data/hora de início** e **Data/hora de término**.

5. Na Guia Rápida **Ativos das atividades do tempo de inatividade de manutenção**> clique em **Adicionar linha** para adicionar ativos, um de cada vez, à atividade do tempo de inatividade de manutenção.

6. Clique em **Salvar** quando todos os ativos forem adicionados. A ilustração a seguir mostra um exemplo de uma atividade do tempo de inatividade de manutenção com ativos relacionados e trabalhos de manutenção.

7. Os trabalhos de manutenção da ordem de serviço e as linhas de agendamento de manutenção abertas relacionadas aos ativos selecionados são mostrados nas Guias Rápidas **Trabalhos de manutenção da ordem de serviço resultante** e **Linhas de agendamento de manutenção**. No campo **Geral** Guia Rápida > **Ordens de serviço** grupo > **Horas de previsão de manutenção** e Guia Rápida **Geral** > grupo de **Agendamento de manutenção** > campo **Horas de previsão de manutenção**, você verá o número total de horas previstas para os trabalhos de manutenção da ordem de serviço e das linhas de agendamento de manutenção.

A ilustração a seguir mostra um exemplo da exibição de detalhes **Atividades do tempo de inatividade de manutenção**.

![Figura 2](media/20-preventive-maintenance.png)

>[!NOTE]
>As linhas de agendamento de manutenção e dos trabalhos de manutenção da ordem de serviço relacionadas aos ativos selecionados são atualizadas automaticamente, se novas ordens de serviço ou as linhas de agendamento de manutenção forem criadas após você ter criado a atividade do tempo de inatividade de manutenção. Por exemplo, se você agendar planos de manutenção ou rounds de manutenção nos ativos relacionados dois dias após a atividade do tempo de inatividade de manutenção ter sido criada, novas linhas de agendamento de manutenção são adicionadas automaticamente à atividade do tempo de inatividade de manutenção. 

8. Em **Todas as atividades do tempo de inatividade de manutenção** > **Atividades do tempo de inatividade de manutenção**, selecione uma atividade do tempo de inatividade de manutenção na lista e clique em **Capacidade máxima** para abrir a caixa de diálogo **Calcular a capacidade máxima**. Use esta caixa de diálogo para obter uma visão geral da capacidade máxima, por exemplo, datas, ativos, tipos de ativos e tipos de trabalho de manutenção. Observe que as datas mostradas na caixa de diálogo são as datas de início e de término selecionadas em **Atividades do tempo de inatividade de manutenção**. Este cálculo inclui os ativos relacionados à atividade do tempo de inatividade de manutenção.

9. Na caixa de diálogo **Calcular a capacidade máxima**, edite as horas inicial e final, se necessário, e selecione se você quer incluir ordens de serviço e agendamentos de manutenção no cálculo. Você pode usar o campo **Nível** para indicar o nível de detalhes que você deseja que o cálculo de capacidade máxima tenha em relação aos locais funcionais. Por exemplo, se você inserir o número "1" no campo e tiver uma estrutura de local funcional de vários níveis, todos os ativos do local funcional, selecionados na atividade do tempo de inatividade de manutenção serão mostrados em nível superior, e portanto, as horas em uma linha podem ser adicionadas de locais funcionais localizados em nível inferior. Se você inserir o número "0" no campo **Nível**, verá um resultado detalhado mostrando todas as linhas da capacidade máxima em todos os níveis do local funcional ao qual elas estão relacionadas.

10. Clique em **OK**para iniciar o cálculo. O número total de horas é mostrado na visão geral **Capacidade máxima**. Na guia **Capacidade máxima** > grupos do Painel de Ações **Agrupar por...**, clique nos botões relevantes para obter uma visão geral mais detalhada da alocação de horas previstas. A ilustração a seguir mostra os resultados de um cálculo de **Capacidade máxima**.

![Figura 3](media/21-preventive-maintenance.png)

11. Depois de obter uma visão geral da capacidade máxima, se quiser fazer ajustes em trabalhos de manutenção da ordem de serviço ou em linhas de agendamento de manutenção, retorne à exibição de detalhes **Atividades do tempo de inatividade de manutenção** e selecione as linhas que deseja ajustar nas FastTabs **Trabalhos de manutenção da ordem de serviço resultantes** e **Linhas de agendamento de manutenção**.

12. Clique no botão **Ajustar** e atualize as datas de início/de término esperada, nível de serviço ou funcionários de manutenção responsáveis para os trabalhos de manutenção da ordem de serviço ou as linhas de agendamento de manutenção.

13. Clique em **OK** quando tiver feito os ajustes necessários. 

>[!NOTE]
>Os trabalhos de manutenção da ordem de serviço e as linhas de agendamento de manutenção que não estiverem incluídos no período de tempo de inatividade de manutenção depois que você tiver feito os ajustes serão removidos das **Atividades do tempo de inatividade de manutenção**.

14. Em **Todas as atividades do tempo de inatividade de manutenção** > **Atividades do tempo de inatividade de manutenção** > selecione uma atividade do tempo de inatividade de manutenção da lista e clique em **Previsão do item** para abrir a caixa de diálogo **Calcular previsão do item**. Use esta caixa de diálogo para calcular previsões para itens (peças sobressalentes e outros itens necessários) e para agrupá-las para obter uma visão geral, por exemplo, por data, por ativo, por tipo de ativo e por tipo de trabalho de manutenção. Observe que as datas mostradas na caixa de diálogo são as datas de início e de término selecionadas em **Atividades do tempo de inatividade de manutenção**. Este cálculo inclui peças sobressalentes e os itens relacionados aos ativos selecionados na atividade do tempo de inatividade de manutenção.

15. Na caixa de diálogo **Calcular previsão do item**, edite as horas inicial e final, se necessário, selecione se você quer incluir ordens de serviço e agendamentos de manutenção no cálculo. Você pode usar o campo **Nível** para indicar o nível de detalhes que você deseja que o cálculo de capacidade máxima tenha em relação aos locais funcionais. Por exemplo, se você inserir o número "1" no campo e tiver uma estrutura de local funcional de vários níveis, todos os ativos do local funcional, selecionados na atividade do tempo de inatividade de manutenção serão mostrados em nível superior, e portanto, as horas em uma linha podem ser adicionadas de locais funcionais localizados em nível inferior. Se você inserir o número "0" no campo **Nível**, verá um resultado detalhado mostrando todas as linhas da capacidade máxima em todos os níveis do local funcional ao qual elas estão relacionadas.

16. Clique em **OK**para iniciar o cálculo. O número total de previsões do item é mostrado na visão geral **Previsão do item**. Na guia **Previsão de itens** > grupos do Painel de Ações **Agrupar por...**, clique nos botões relevantes para obter uma visão geral mais detalhada da alocação de itens previstos. A ilustração a seguir mostra os resultados de um cálculo de **Previsão de itens**.

![Figura 4](media/22-preventive-maintenance.png)

- Você pode copiar ativos de uma atividade do tempo de inatividade de manutenção para outra. Em **Todas atividades do tempo de inatividade de manutenção**, selecione o botão **Copiar atividades do tempo de inatividade de manutenção** e faça suas seleções nos campos **Atividades iniciais do tempo de inatividade de manutenção** e **Atividades finais do tempo de inatividade de manutenção** e clique em **OK**.
- Em **Todas atividades do tempo de inatividade de manutenção**, clique no botão **Linhas de agendamento de manutenção** ou no botão **Ordens de serviço ativas** para abrir as listas relacionadas e exibi-las na atividade do tempo de inatividade de manutenção.

