---
title: Tempo de inatividade de manutenção
description: Este tópico descreve tempo de inatividade de manutenção no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cc79dc1b5911679586fa560142ada5add1a881d2
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918235"
---
# <a name="maintenance-downtime"></a>Tempo de inatividade de manutenção


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Você pode criar registros do tempo de inatividade de manutenção no ativo selecionado em uma ordem de serviço. Isso é útil se você quiser registrar tempo de inatividade de manutenção em uma ou mais máquinas na área de produção. Primeiro, crie códigos de motivo do tempo de inatividade de manutenção que deseja usar, por exemplo, divisão e parada planejada. Isso é feito em **Códigos de motivo do tempo de inatividade de manutenção**. Em seguida, você pode criar registros do tempo de inatividade de manutenção em **Tempo de Inatividade de Manutenção** e adicionar os códigos do motivo relevantes.

## <a name="create-maintenance-downtime-reason-codes"></a>Criar códigos de motivo de tempo de inatividade de manutenção

1. Clique em **Gerenciamento de ativos** > **Configuração** > **Ordens de serviços** > **Códigos de motivo do tempo de inatividade de manutenção**.

2. Clique em **Novo**.

3. Inserir um ID no campo **Código de motivo do tempo de inatividade de manutenção**.

4. Insira um nome para o código do motivo no campo **Nome**.

5. Marque a caixa de seleção **KPI incluído** se o código do motivo tiver que ser incluído nos cálculos de KPI do ativo. Geralmente, as paradas de produção planejadas não devem se incluídas em cálculos de KPI porque não afetam o desempenho esperado.

6. Clique em **Salvar**.

![Figura 1](media/15-work-orders.png)


Quando você criar códigos de motivo do tempo de inatividade de manutenção que deseja usar, você pode criar registros do tempo de inatividade de manutenção para ordens de serviço e ativos.


## <a name="create-maintenance-downtime-registrations"></a>Criar registros de tempo de inatividade de manutenção

1. Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.

2. Selecione a ordem de serviço e clique em **Tempo de inatividade de manutenção**.

3. Clique em **Novo**.

4. Insira o intervalo de data e hora para o registro de tempo de inatividade de manutenção nos campos **De** e **A**.

5. Quando você sair do campo **A**, a duração em horas é inserida automaticamente no campo **Duração**.

6. Selecione um código de motivo no campo **código de motivo de tempo de inatividade de manutenção**.

7. Repita as etapas 3 e 6 se quiser adicionar mais registros.

8. Clique em **Salvar**.


![Figura 2](media/16-work-orders.png)


O calendário usado para calcular um registro do tempo de inatividade de manutenção depende de sua seleção na configuração de ativos e parâmetros. Se um recurso for selecionado em um ativo no campo **Todos os ativos** > **Ativo fixo** Guia Rápida > **Recurso**, será usada a configuração do calendário para o grupo de recursos associado, conforme mostrado na seguinte figura.

![Figura 3](media/17-work-orders.png)


Se nenhum recurso for selecionado no ativo, o calendário padrão selecionado em **Parâmetros de gerenciamento de ativos** é usado, conforme mostrado na seguinte figura.

![Figura 4](media/18-work-orders.png)


Clique **Gerenciamento de ativos da empresa** > **Consultas** > **Tempo de inatividade de manutenção** para exibir uma visão geral de todos os registros de tempo de inatividade de manutenção.

>[!NOTE]
>Todos os calendários usados no módulo **Gerenciamento de ativos** são configurados na **Administração da organização** > **Configuração** > **Calendários** > **Calendários**.

