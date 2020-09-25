---
title: Tempo de inatividade de manutenção para ordens de serviço
description: Este tópico descreve como criar registros do tempo de inatividade de manutenção no ativo selecionado em uma ordem de serviço.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 263a044a0a378e95ea271ac1c6f468f9e3287f26
ms.sourcegitcommit: 5bb36b74935ffe140367fd6ecf956b4857ad12e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2020
ms.locfileid: "3802716"
---
# <a name="maintenance-downtime-for-work-orders"></a>Tempo de inatividade de manutenção para ordens de serviço

[!include [banner](../../includes/banner.md)]


Você pode criar registros do tempo de inatividade de manutenção no ativo selecionado em uma ordem de serviço. Esse recurso é útil se você quiser registrar o tempo de inatividade de manutenção em uma ou mais máquinas na área de produção. Primeiro, crie códigos para o motivo do tempo de inatividade de manutenção que deseja usar, como **Travamento** e **Parada planejada**. Isso é feito na página **Códigos de motivo do tempo de inatividade de manutenção**. Em seguida, você pode criar registros do tempo de inatividade de manutenção na página **Tempo de inatividade de manutenção** e adicionar os códigos de motivo do tempo de inatividade de manutenção relevantes.

## <a name="create-maintenance-downtime-reason-codes"></a>Criar códigos de motivo de tempo de inatividade de manutenção

1. Selecione **Gerenciamento de ativos** > **Configurar** > **Ordens de serviço** > **Códigos de motivo do tempo de inatividade de manutenção**.

2. Selecione **Novo**.

3. No campo **Código de motivo do tempo de inatividade de manutenção**, insira uma ID para o código de motivo do tempo de inatividade de manutenção.

4. No campo **Nome**, insira um nome.

5. Marque a caixa de seleção **Incluído no KPI** se desejar que o código de motivo seja incluído nos cálculos dos KPIs (Indicadores Chave de Desempenho) do ativo. Em geral, as paradas de produção planejadas não devem ser incluídas em cálculos de KPI, pois não afetam o desempenho esperado.

6. Selecione **Salvar**.

A ilustração a seguir mostra um exemplo da página **Códigos de motivo do tempo de inatividade de manutenção**.

![Figura 1](media/15-work-orders.png)

Depois de criar os códigos de motivo do tempo de inatividade de manutenção que deseja usar, você pode criar registros de tempo de inatividade de manutenção para ordens de serviço e ativos.


## <a name="create-maintenance-downtime-registrations"></a>Criar registros de tempo de inatividade de manutenção

1. Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

2. Selecione a ordem de serviço e, na guia **Ordem de serviço**, no grupo **Ativo**, selecione **Tempo de inatividade de manutenção**.

3. Selecione **Novo**.

4. Nos campos **De** e **A**, defina o intervalo de data e hora para o registro de tempo de inatividade de manutenção.

>[!NOTE]
>Quando você sair do campo **A**, a duração em horas é inserida automaticamente no campo **Duração**.

5. No campo **código de motivo do tempo de inatividade de manutenção**, selecione um código de motivo.

6. Repita as etapas 3 a 5 para adicionar mais registros.

7. Selecione **Salvar**.

A ilustração a seguir mostra um exemplo de registro de tempo de inatividade de manutenção.

![Figura 2](media/16-work-orders.png)

O calendário usado para calcular um registro de tempo de inatividade de manutenção depende da sua seleção na configuração de ativos e parâmetros. Se um recurso for selecionado em um ativo no campo **Recurso** da Guia Rápida **Ativo fixo** na página **Todos os ativos**, o calendário definido para o grupo de recursos associado será utilizado, conforme exibido na figura a seguir.

![Figura 3](media/17-work-orders.png)

Se nenhum recurso for selecionado no ativo, o calendário padrão selecionado na página **Parâmetros de gerenciamento de ativos** será utilizado, conforme mostrado na figura a seguir.

![Figura 4](media/18-work-orders.png)

Para obter uma visão geral de todos os registros de tempo de inatividade de manutenção, clique em **Gerenciamento de ativos** > **Consultas** > **Tempo de inatividade de manutenção**.

>[!NOTE]
>Todos os calendários usados no módulo **Gerenciamento de ativos** são configurados em **Administração da organização** > **Configurar** > **Calendários** > **Calendários**.

