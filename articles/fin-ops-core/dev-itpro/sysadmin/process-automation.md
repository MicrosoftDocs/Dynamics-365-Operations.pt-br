---
title: Automação de processos
description: Este tópico fornece detalhes sobre como a automação de processos permite o agendamento simples de processos que serão executados pelo servidor de lote.
author: RyanCCarlson2
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProcessScheduleSeries
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2020-06-30
ms.dyn365.ops.version: AX 10.0.11
ms.openlocfilehash: a861710e29962e1222d95bfa8c4ef7407bd3401d
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6343975"
---
# <a name="process-automation"></a>Automação de processos

[!include[banner](../includes/banner.md)]

A automação de processos permite o agendamento simples de processos que serão executados pelo servidor de lote. A exibição de calendário atualizada do trabalho agendado permite que os usuários finais exibam e executem ações no trabalho agendado e concluído.

## <a name="administration"></a>Administração

A página de administração central de todas as automações de processos é encontrada no módulo Administração do Sistema no menu **Configurar**. Essa página listará todos os processos automatizados (série) que estão configurados no sistema. Ela também permitirá que você adicione novas automações de processos diretamente nela. Depois que uma série é configurada, é possível gerenciá-la nesta lista. Você pode optar por editar toda a série, excluí-la, exibir todas as ocorrências em uma exibição de lista ou desabilitar a série se desejar pausar o trabalho agendado por um tempo. 

Qualquer processo desabilitado no gerenciamento de recursos não será exibido quando o recurso for desabilitado. Além disso, o mecanismo de plano de automação do processo não agendará ocorrências ou processos em segundo plano para um recurso desabilitado. A reabilitação do recurso levará qualquer ocorrência agendada ou processo em segundo plano no passado a ser executado imediatamente. O mecanismo de agendamento da automação de processos depende do trabalho em lotes do sistema, **Trabalho de sistema de sondagem de automação do processo** a ser executado. O trabalho não deve ser alterado ou adulterado a qualquer momento. 

## <a name="calendar-view"></a>Exibição de calendário

Uma das principais vantagens da automação de processos é a capacidade de ver o trabalho agendado em uma exibição de calendário simples.  Essa exibição permite ver o trabalho de uma semana por vez. Você verá essa exibição no lado direito da página **Automação de processos**. Ela será preenchida com o trabalho agendado para a série selecionada. 

[![Calendário da automação de processos.](./media/CalendarView2.png)](./media/CalendarView2.png)

## <a name="occurrence-changes"></a>Alterações de ocorrência

Cada ocorrência pode ser modificada sem afetar outras ocorrências definidas pela série que as originou. As ocorrências de trabalho agendado podem ser editadas na exibição de calendário selecionando o botão **Exibir/Editar** e selecionando **Ocorrência**. Esta página permite acessar todas as configurações originalmente exibidas no assistente de configuração da série e oferece a capacidade de fazer uma alteração única na ocorrência selecionada. Uma ocorrência de trabalho agendado também pode ser desativada selecionando o botão **Desabilitar** na exibição de calendário.

## <a name="developer-documentation"></a>Documentação do Desenvolvedor

A estrutura de automação de processos permite que os desenvolvedores estendam a estrutura de automação de processos. A documentação [Estrutura de automação de processos](../process-automation/process-automation-framework.md) fornecerá informações sobre como criar processos personalizados que precisam ser executados pelo servidor de lote agendado com o assistente de automação de processos e aparecem na exibição de calendário automaticamente.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
