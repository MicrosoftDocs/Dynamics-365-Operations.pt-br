---
title: Criar modelos de produção
description: Os modelos de horário de trabalho definem as horas de trabalho ao longo de uma semana e são usados para gerar horários de trabalho para um período.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkTimeTable, WorkTimeCopyDayDialog, WorkPeriodTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 130a21d08e4e720f8bf803a5d4b03d315cefc26f
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580663"
---
# <a name="create-working-time-templates"></a>Criar modelos de produção

[!include [banner](../../includes/banner.md)]

Os modelos de horário de trabalho definem as horas de trabalho ao longo de uma semana e são usados para gerar horários de trabalho para um período. Este procedimento mostra como definir um modelo de horário de trabalho usando propriedades de programação de horário de trabalho para categorizar intervalos de horário de trabalho. Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.

1. Acesse **Espaços de trabalho > Gerenciamento de ciclo de vida de recurso**.
1. Selecione **Modelos de horário de trabalho**.

## <a name="create-working-time-template"></a>Criar modelo de horário de trabalho

1. Selecione **Novo**.
1. No campo **Modelo de horário de trabalho**, digite um valor.
1. No campo **Nome**, digite um valor.
1. Expanda a seção **Segunda-feira**.
1. Selecione **Adicionar**.
1. No campo **De**, digite um horário.
    * Especifique a hora em que o trabalho é iniciado na manhã.  
1. No campo **Até**, digite um horário.
    * Especifique a hora em que trabalhadores param para o almoço.  
1. Selecione **Adicionar**.
1. No campo **De**, digite um horário.
    * Especifique a hora em que o trabalho é retomado após o almoço.  
1. No campo **Até**, digite um horário.
    * Especifique o fim do dia de trabalho.  

## <a name="replicate-working-times-to-all-week-days"></a>Replicar horários de trabalho para todos os dias da semana

1. Selecione **Copiar dia**.
    * Copie as definições de horários de trabalho de segunda-feira a terça-feira.  
1. Selecione **OK**.
1. Selecione **Copiar dia**.
    * Copie as definições de horários de trabalho de segunda-feira a quarta-feira.  
1. No campo **Ao dia útil**, selecione uma opção.
1. Selecione **OK**.
1. Selecione **Copiar dia**.
    * Copie as definições de horários de trabalho de segunda-feira a quinta-feira.  
1. No campo **Ao dia útil**, selecione uma opção.
1. Selecione **OK**.
1. Selecione **Copiar dia**.
    * Copie as definições de horários de trabalho de segunda-feira a sexta-feira.  
1. No campo **Ao dia útil**, selecione uma opção.
1. Selecione **OK**.

## <a name="define-time-slots-for-special-operations"></a>Definir alocações de tempo para operações especiais

1. Expanda a seção **Sexta-feira**.
1. Na lista, localize e selecione o PDV desejado.
1. No campo **Propriedade** insira ou selecione um valor.
1. Na lista, localize e selecione o PDV desejado.
1. No campo **Propriedade** insira ou selecione um valor.

## <a name="mark-weekend-days-as-closed-for-pickup"></a>Marcar dias do final de semana como fechados para a retirada

1. Expanda a seção **Sábado**.
1. Selecione *Sim* no campo **Fechado para retirada**.
1. Expanda a seção **Domingo**.
1. Selecione *Sim* no campo **Fechado para retirada**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]