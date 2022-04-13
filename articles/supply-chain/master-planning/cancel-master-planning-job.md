---
title: Cancelar um trabalho mestre de planejamento
description: Este tópico explica como cancelar um trabalho de planejamento ativo que usa funcionalidade de planejamento integrado.
author: t-benebo
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace, ReqProcessList
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-12-16
ms.dyn365.ops.version: ''
ms.openlocfilehash: d96f946c0c87db44ac5fe1adda68e47838dcc0d7
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469216"
---
# <a name="cancel-a-master-planning-job"></a>Cancelar um trabalho mestre de planejamento

[!include [banner](../includes/banner.md)]

No Microsoft Dynamics 365 Supply Chain Management, há várias opções para cancelar um trabalho de planejamento mestre. Por exemplo, talvez você queira cancelar um trabalho de planejamento mestre se ele tiver sido iniciado por engano ou estiver sendo executado mais tempo do que o esperado e desejar encerrá-lo. A melhor maneira de cancelar um trabalho de planejamento é a partir da página **Processos de planejamento inacabados**. As opções alternativas das páginas **Trabalhos em lotes** e **Trabalhos em lotes avançados** só devem ser usadas se o cancelamento do trabalho de planejamento mestre da página **Processos de planejamento não concluídos** não tiver sido concluído em alguns minutos.

## <a name="preferred-cancel-option"></a>Opção de cancelamento preferencial
### <a name="cancel-master-planning-job-from-unfinished-planning-processes-page"></a>Cancelar o trabalho de planejamento mestre a partir da página **Processos de planejamento não concluídos**
1. Acesse **Planejamento mestre > Consultas e relatórios > Planejamento mestre > Processos de planejamento não concluídos**.
2. Selecione a linha com o processo de planejamento que você deseja cancelar.
3. Clique em **Cancelar**.

## <a name="additional-cancel-options"></a>Opções de cancelamento adicionais
Eles devem ser usados somente se o cancelamento do trabalho de planejamento mestre da página **Processos de planejamento não concluídos** não foram concluídas em alguns minutos.

### <a name="delete-master-planning-job-from-the-batch-jobs-page"></a>Excluir trabalho de planejamento mestre da página **Trabalho em lotes**
1. Acesse **Administração do sistema > Consultas > Trabalhos em lotes**.
2. Selecione a linha com o trabalho de planejamento que você deseja excluir.
3. Clique em **Excluir**.

### <a name="abort-master-planning-job-task-from-the-batch-jobs-enhanced-page"></a>Cancelar tarefa de planejamento mestre da página **Trabalho em lotes aprimorado**
1. Acesse **Administração do sistema > Consultas > Trabalhos em lotes**.
2. Se a ID do trabalho não for mostrada na lista, clique em **Alterar para formulário avançado**, caso contrário, continue com a próxima etapa.
3. Abrir o trabalho em lotes. Clique em **ID de trabalho** para o trabalho em lotes com as tarefas que você deseja encerrar.
4. Em **Tarefas em lotes**, selecione as tarefas a serem encerradas.
5. Clique em **Alterar status**, escolha **Cancelar** e clique em **OK**.
6. Na Guia Rápida **Tarefas em lotes** clique em **Anular**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]