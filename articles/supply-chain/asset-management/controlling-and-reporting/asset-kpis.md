---
title: KPIs do ativo
description: Este tópico explica KPIs de ativo no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectKPI
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8741ad9c70182c0f4f9d4d5272a023a3627340f6
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5253797"
---
# <a name="asset-kpis"></a>KPIs do ativo

[!include [banner](../../includes/banner.md)]

 

No Gerenciamento de Ativos, é possível calcular vários KPIs (indicadores chave de desempenho) para ativos e tipos de ativos. Use KPIs para obter uma visão geral do desempenho dos ativos em relação a, por exemplo, tempo de atividade, tempo de inatividade, tempo de reparo e tempo médio entre falhas (Mean Time Between Failure, MTBF).

1. Clique em **Gerenciamento de ativos** > **Consultas** > **Ativos** > **KPIs do ativo**.

2. Na caixa de diálogo **Calcular KPIs de ativo**, selecione a **Escala de tempo** a ser usada no cálculo e um período nos campos **Data inicial** e **Data final**. 

3. Na Guia Rápida **Registros a serem incluídos**, você pode selecionar ativos e tipos de ativos específicos a serem incluídos no cálculo, se necessário.

4. Clique em **OK** para iniciar o cálculo.

5. Na Guia Rápida **Visão Geral**, os resultados do cálculo são exibidos na exibição de grade. Cada ativo é exibido em uma linha separada.

6. Na Guia Rápida **KPIs da linha selecionada**, você vê os cálculos do ativo selecionado na Guia Rápida **Visão Geral**. Os valores de KPI são categorizados em **Hora**, **Disponibilidade**, **Ordens de serviço**, **Manutenção**, **Falhas**, **Tempo de inatividade de manutenção** e **Custo**.

Na tabela abaixo, você encontrará uma descrição dos campos na página **KPIs do ativo**.

| Campo                   | Descrição                                                                                                                                                                                                                                                                                           |
|-------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ativo                   | ID do Ativo.                                                                                                                                                                                                                                                                                             |
| Tempo total              | Tempo total configurado no calendário usado no cálculo. Se o ativo estiver relacionado a um recurso, o calendário do recurso relacionado será usado. Se o ativo não estiver relacionado a um recurso, será utilizado o calendário selecionado no campo **Calendário padrão** em **Parâmetros de gerenciamento de ativos**. |
| Tempo de atividade                  | Tempo total menos tempo de inatividade.                                                                                                                                                                                                                                                                            |
| Tempo de inatividade                | Registros de tempo de inatividade de manutenção feitos no ativo no período selecionado.                                                                                                                                                                                                                              |
| Tempo de reparo             | Número total de horas de trabalho consumidas em ordens de serviço de reparo.                                                                                                                                                                                                                                            |
| % de disponibilidade          | Tempo de atividade dividido pelo tempo total e multiplicado por 100.                                                                                                                                                                                                                                                   |
| Número de falhas        | Número de causas de falha registradas nos sintomas de falha no ativo no período selecionado.                                                                                                                                                                                                             |
| MTBF                    | Tempo médio entre falhas, que é o tempo total dividido pelo número de falhas registradas no ativo no período selecionado. Se o número de falhas for zero, o MTBF será definido como tempo total.                                                                                                                   |
| Taxa de falha               | 1 dividido pelo MTBF.                                                                                                                                                                                                                                                                                    |
| MRT                     | Tempo médio de reparo, que é o tempo de reparo dividido pelo número de falhas registradas no ativo no período selecionado. Se o número de falhas for zero, o MRT será definido como tempo de reparo.                                                                                                                           |
| Número de interrupções         | Número de registros de tempo de inatividade de manutenção criados no ativo.                                                                                                                                                                                                                                     |
| MTBS                    | Tempo médio entre paradas, que é o tempo total dividido pelo número de registros de tempo de inatividade de manutenção. Se o número de registros de tempo de inatividade de manutenção for zero no período selecionado, o valor de MTBS será definido como tempo total.                                                                                      |
| Custo preventivo         | Custos lançados no ativo relacionados ao tipo de custo "Preventivo" no período selecionado. Os tipos de custo são configurados nos tipos de ordem de serviço.                                                                                                                                                                       |
| Custo corretivo         | Custos lançados no ativo relacionados ao tipo de custo "Corretivo" no período selecionado. Os tipos de custo são configurados nos tipos de ordem de serviço.                                                                                                                                                                       |
| Valor de substituição       | Valor definido no ativo como o custo de substituição.                                                                                                                                                                                                                                                  |
| Tipo de ativo             | Identificação do tipo de ativo selecionado no ativo.                                                                                                                                                                                                                                             |
| Fabricante           | Identificação do fabricante selecionado no ativo.                                                                                                                                                                                                                                                 |
| Modelo                   | Identificação do modelo do fabricante selecionado no ativo.                                                                                                                                                                                                                                           |
| De               | Data de início do cálculo do KPI. Se o ativo foi criado após a data de início selecionada para o cálculo, a data de início do ativo é mostrada neste campo.                                                                                                                                  |
| Até                 | Data final do cálculo do KPI. Se o ativo foi registrado como inativo antes da data final selecionada para o cálculo, a data a partir da qual o ativo não estava mais ativo é mostrada neste campo.                                                                                               |
| Escala de tempo              | Durante o cálculo dos KPIs, você seleciona uma escala de tempo a ser usada: Horas, Dias ou Semanas.                                                                                                                                                                                                            |
| Disponibilidade            | Tempo de atividade dividido pelo tempo total.                                                                                                                                                                                                                                                                         |
| Ordens de serviço             | Número total de ordens de serviço incluídas no cálculo do KPI.                                                                                                                                                                                                                                          |
| Hora da ordem de serviço         | Número total de horas de trabalho consumidas nas ordens de serviço.                                                                                                                                                                                                                                               |
| Ordens de serviço primárias     | Número de ordens de serviço principais incluídas no cálculo do KPI.                                                                                                                                                                                                                                        |
| Ordens de serviço secundárias   | Número de ordens de serviço secundárias incluídas no cálculo do KPI.                                                                                                                                                                                                                                      |
| Ordens de serviço de manutenção | Número de ordens de serviço de manutenção incluídas no cálculo do KPI. Uma ordem de serviço de manutenção é uma ordem de serviço sem causas de falha relacionadas.                                                                                                                                                             |
| Tempo de manutenção        | Número total de horas de trabalho consumidas em ordens de serviço de manutenção.                                                                                                                                                                                                                                       |
| Reparar ordens de serviço      | Número de ordens de serviço de reparo incluídas no cálculo do KPI. Uma ordem de serviço de reparo é uma ordem de serviço com uma causa de falha relacionada.                                                                                                                                                                        |
| % de confiabilidade           | Cálculo com base no desenvolvimento exponencial esperado nos registros de falhas de um ativo, o que significa que, com o tempo, o ativo se torna menos confiável por causa de desgaste. O cálculo desse KPI é baseado no MTBF e no tempo total.                                                            |
| MTPS                    | Tempo médio de paradas de produção, que é o tempo de inatividade de manutenção dividido pelo número de registros de tempo de inatividade de manutenção. Se o número de registros de tempo de inatividade de manutenção for zero no período selecionado, o valor de MTPS será definido como zero.                                                                               |
| Custo total              | Custos totais lançados no ativo no período selecionado.                                                                                                                                                                                                                                              |
| Custo do investimento         | Custos lançados no ativo relacionados ao tipo de custo "Investimento" no período selecionado. Os tipos de custo são configurados nos tipos de ordem de serviço.                                                                                                                                                                       |

A figura abaixo mostra uma captura de tela de um cálculo de KPI para quatro ativos.

![Captura de tela de um cálculo de KPI para quatro ativos](media/11-controlling-and-reporting.png)

- Você pode selecionar vários ativos em **Todos os ativos** e clicar no botão **KPIs do ativo** na guia **General**. Em seguida, clique em **OK** na caixa de diálogo **Calcular KPIs de ativo** para calcular KPIs para os ativos selecionados.  
- Os resultados de um cálculo de KPI podem ou não incluir [registros de tempo de inatividade de manutenção](../work-orders/maintenance-downtime.md), dependendo da configuração e do uso dos códigos de motivo de tempo de inatividade de manutenção. 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]