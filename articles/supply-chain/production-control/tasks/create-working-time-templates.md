--- 
title: "Criar modelos de produção"
description: "Os modelos de horário de trabalho definem as horas de trabalho ao longo de uma semana e são usados para gerar horários de trabalho para um período."
author: sorenva
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: ff1978f127a014e75619a4bbbb9b6ff3a3ad7c7a
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="create-working-time-templates"></a>Criar modelos de produção

[!include[task guide banner](../../includes/task-guide-banner.md)]

Os modelos de horário de trabalho definem as horas de trabalho ao longo de uma semana e são usados para gerar horários de trabalho para um período. Este procedimento mostra como definir um modelo de horário de trabalho usando propriedades de programação de horário de trabalho para categorizar intervalos de horário de trabalho. Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.

1. Vá para Todas áreas de trabalho > Gerenciamento de ciclo de vida de recurso.
2. Clique em Modelos de horário de trabalho.

## <a name="create-working-time-template"></a>Criar modelo de horário de trabalho
1. Clique em Novo.
2. No campo Modelo de horário de trabalho, digite um valor.
3. No campo Nome, digite um valor.
4. Expandir a seção Segunda-feira.
5. Clique em Adicionar.
6. No campo De, insira uma hora.
    * Especifique a hora em que o trabalho é iniciado na manhã.  
7. No campo Até, insira uma hora.
    * Especifique a hora em que trabalhadores param para o almoço.  
8. Clique em Adicionar.
9. No campo De, insira uma hora.
    * Especifique a hora em que o trabalho é retomado após o almoço.  
10. No campo Até, insira uma hora.
    * Especifique o fim do dia de trabalho.  

## <a name="replicate-working-times-to-all-week-days"></a>Replicar horários de trabalho para todos os dias da semana
1. Clique em Copiar dia.
    * Copie as definições de horários de trabalho de segunda-feira a terça-feira.  
2. Clique em OK.
3. Clique em Copiar dia.
    * Copie as definições de horários de trabalho de segunda-feira a quarta-feira.  
4. No campo Ao dia útil, selecione uma opção.
5. Clique em OK.
6. Clique em Copiar dia.
    * Copie as definições de horários de trabalho de segunda-feira a quinta-feira.  
7. No campo Ao dia útil, selecione uma opção.
8. Clique em OK.
9. Clique em Copiar dia.
    * Copie as definições de horários de trabalho de segunda-feira a sexta-feira.  
10. No campo Ao dia útil, selecione uma opção.
11. Clique em OK.

## <a name="define-time-slots-for-special-operations"></a>Definir alocações de tempo para operações especiais
1. Expanda a seção Sexta-feira.
2. Na lista, localize e selecione o PDV desejado.
3. No campo Propriedade, insira ou selecione um valor.
4. Na lista, localize e selecione o PDV desejado.
5. No campo Propriedade, insira ou selecione um valor.

## <a name="mark-weekend-days-as-closed-for-pickup"></a>Marcar dias do final de semana como fechados para a retirada
1. Expanda a seção Sábado.
2. Selecione Sim no campo Fechado para retirada.
3. Expanda a seção Domingo.
4. Selecione Sim no campo Fechado para retirada.


