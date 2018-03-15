---
title: Janelas de horas
description: "Você pode usar janelas de tempo para otimizar o agendamento das linhas de ordem de serviço."
author: YuyuScheller
manager: AnnBe
ms.date: 02/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMATimeAgreement
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 4ea10e4c0fbfd21538bba16d2b01deb3e4b3a10d
ms.openlocfilehash: b7268870aa9065e4e52d936e819107094bad3663
ms.contentlocale: pt-br
ms.lasthandoff: 02/20/2018

---

# <a name="time-windows"></a>Janelas de horas  

[!include[banner](../includes/banner.md)]

Você pode usar janelas de tempo para otimizar o agendamento das linhas de ordem de serviço. Você pode configurar o sistema de forma que criar automaticamente ordens de serviço. Com base nos critérios especificados por uma janela de tempo, você pode associar quantas linhas de ordem de serviço de possíveis à menor quantidade de ordens de serviço possíveis.

As janelas de tempo definem até que ponto uma linha de ordem de serviço pode se mover em relação à data de cálculo. Essa é a data na qual a linha da ordem de serviço foi programada para ocorrer. A data é baseada na configuração de intervalo e no período de serviço definidos na página **Criar ordens de serviço**. Defina uma janela de tempo usando os seguintes valores:

| Método | descrição                                                                                                                                                                                                                                                                                           |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Semana   | A data de execução da linha da ordem de serviço pode ser movida para qualquer dia aberto na mesma semana que a data inicial calculada.                                                                                                                                                                                    |
| Mês  | A data de execução da linha da ordem de serviço pode ser movida para qualquer dia aberto no mesmo mês que a data inicial calculada. Por exemplo, a data calculada para uma linha de ordem de serviço é 15 de fevereiro de 2017. A linha pode ser programada para qualquer dia útil entre 1º de fevereiro e 28 de fevereiro de 2017. |
| Manual | Defina o número máximo de dias antes ou depois da data inicial calculada em que a linha da ordem de serviço pode ser movida.                                                                                                                                                                           |

Se uma janela de tempo não for especificada para uma linha de contrato de serviço, a linha da ordem de serviço que deriva do contrato deverá ser executada na data exata em que foi programada inicialmente.

## <a name="related-topics"></a>Tópicos relacionados

[Criar janelas de horas](create-time-windows.md)


