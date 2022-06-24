---
title: Criação de ordens de serviço
description: Este artigo explica como criar ordens de serviço no Gerenciamento de Ativos.
author: johanhoffmann
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetMaintenancePlan, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePoolsOpen
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: b1b8b3d8d83bdad2efe49bd4e878793cca6c49f4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891195"
---
# <a name="creating-work-orders"></a>Criação de ordens de serviço

[!include [banner](../../includes/banner.md)]

Depois de agendar trabalhos de manutenção preventiva, a próxima etapa é criar ordens de serviço para eles. Você pode concluir essa etapa usando um dos agendamentos de manutenção. Os trabalhos agendados em um agendamento de manutenção podem ter diferentes tipos de referência, conforme descrito na seguinte tabela.

| Tipo de referência | descrição |
|---|---|
| Planos de manutenção | Trabalhos de manutenção que são baseadas com base no tipo de plano de manutenção *Tempo* ou *Contador*. |
| Rounds de manutenção | Trabalhos de manutenção preventiva que têm vários ativos que requerem um tipo semelhante de manutenção. |
| Solicitação de manutenção | Uma solicitação criada manualmente para manutenção ou reparo de um ativo. Essa solicitação pode ser convertida em uma ordem de trabalho. |

## <a name="create-work-orders-based-on-your-maintenance-schedule"></a>Criar ordens de trabalho com base no seu plano de manutenção

Para criar ordens de trabalho baseadas na sua agenda de manutenção, siga estas etapas.

1. Abra uma das seguintes páginas, dependendo de como você deseja selecionar itens de agendamento para suas ordens de trabalho:

    - Todos os cronogramas de manutenção (**Gerenciamento de ativos \> Agenda de gerenciamento \> Todos os agendamentos de manutenção**)
    - Abra as linhas do agendamento de manutenção (**Gerenciamento de ativos \> Agenda de gerenciamento \> Abrir linhas do agendamento de manutenção**)
    - Abra os pools do agendamento de manutenção (**Gerenciamento de ativos \> Agenda de gerenciamento \> Abrir pools do agendamento de manutenção**)

1. Na grade, marque a caixa de seleção para cada trabalho de manutenção agendado para o qual você deseja criar uma ordem de serviço. Em seguida, no Painel de Ação, selecione **Ordem de serviço**.

    A caixa de diálogo **Criar ordens de serviço** será exibida. O campo **Horas de previsão de manutenção** exibe o número total de horas de previsão para as linhas selecionadas.

    ![Caixa de diálogo Criar ordens de serviço.](media/18-preventive-maintenance.png)

1. Na seção **Parâmetros**, especifique o número de ordens de serviço que devem ser criadas. Selecione uma das seguintes opções:

    - **Uma ordem de serviço por linha** – Cria uma ordem de serviço por linha do agendamento de manutenção.
    - **Uma ordem de serviço por grupo** – Cria ordens de serviço que são agrupadas de acordo com as configurações das outras opções que ficam disponíveis quando você seleciona esta opção.

1. No campo **Tipo de ordem de serviço**, selecione o tipo de ordem de serviço que será usado para todas as ordens de serviço criadas.
1. Selecione **OK** para criar as ordens de serviço de acordo com as configurações.

## <a name="group-work-order-lines-that-are-automatically-created-while-a-maintenance-plan-runs"></a>Agrupar linhas de ordem de serviço que são criadas automaticamente enquanto um agendamento de manutenção é executado

Esse recurso permite definir regras para agrupar linhas de ordem de serviço em uma única ordem de serviço quando o sistema é configurado para gerar ordens de serviço automaticamente, com base em um agendamento de manutenção. Antes, as ordens de serviço geradas automaticamente podiam conter apenas uma linha. No entanto, agora você pode agrupar ordens de serviço com base, por exemplo, no ativo, tipo de ativo ou local funcional. (As ordens de serviço criadas manualmente já podem ser agrupadas dessa forma, conforme descrito na seção anterior deste artigo.)

### <a name="enable-grouping-for-automatically-generated-work-orders"></a>Habilitar agrupamento para ordens de serviço geradas automaticamente

Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *gerenciamento de ativos*
- **Nome do recurso:** *Aplicar regras para agrupar ordens de serviço ao executar um plano de manutenção*

### <a name="set-up-grouping-for-automatically-generated-work-orders"></a>Configurar agrupamento para ordens de serviço geradas automaticamente

Para configurar agrupamento para ordens de serviço geradas automaticamente, siga estas etapas.

1. Acesse **Gerenciamento de ativos \> Configuração \> Manutenção preventiva \> Planos de manutenção**.
1. Para cada plano em que você deseja gerar ordens de serviço agrupadas, siga estas etapas:

    1. No painel de lista, selecione o plano desejado.
    1. Na guia rápida **Linhas**, certifique-se de que a caixa de seleção **Criação automática** esteja marcada em todas as linhas.

1. Acesse **Gerenciamento de ativos \> Periódico \> Manutenção preventiva \> Agendar planos de manutenção**.
1. Na caixa de diálogo **Agendar planos de manutenção**, na seção **Período**, especifique o horizonte de tempo para o plano (até que ponto ele deve procurar ao localizar trabalhos de manutenção agendados para os quais gerar trabalho).
1. Defina a opção **Criar ordem de serviço com base no agendamento automaticamente** como *Sim*.
1. Na seção **Ordem de serviço**, selecione uma destas opções:

    - **Uma ordem de serviço por linha** – Cria uma ordem de serviço por linha do agendamento de manutenção. (Esta opção oferece a mesma funcionalidade disponível quando o recurso *Aplicar regras para agrupar ordens de serviço durante a execução de um plano de manutenção* está desativado.)
    - **Uma ordem de serviço por grupo** – Cria ordens de serviço que são agrupadas de acordo com as configurações das outras opções que ficam disponíveis quando você seleciona esta opção.

1. Se você deseja que as opções sejam aplicadas ao executar apenas alguns dos planos de manutenção, na guia rápida **Registros que serão incluídos**, adicione filtros conforme necessário, da mesma forma que em outros trabalhos em lote no Microsoft Dynamics 365 Supply Chain Management.
1. Na guia rápida **Executar em segundo plano**, configure as opções de lote e de agendamento conforme necessário, da mesma forma que em outros trabalhos em lote no Supply Chain Management.
1. Selecione **OK** para executar e/ou programar os planos de manutenção selecionados.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]