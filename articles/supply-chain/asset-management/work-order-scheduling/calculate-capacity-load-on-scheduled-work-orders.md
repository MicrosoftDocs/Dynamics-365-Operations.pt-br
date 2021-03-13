---
title: Calcular a capacidade máxima em ordens de serviço agendadas
description: Este tópico explica como calcular a capacidade máxima em ordens de serviço agendadas no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7b7e4a20ed56b1eac29d16d527693d6e455cdc37
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021645"
---
# <a name="calculate-capacity-load-on-scheduled-work-orders"></a>Calcular a capacidade máxima em ordens de serviço agendadas

[!include [banner](../../includes/banner.md)]

 

Você pode calcular a capacidade máxima em ordens de serviço agendadas para obter uma visão geral da carga de trabalho nos recursos por um período específico. Os cálculos podem ser feitos para os seguintes recursos: trabalhadores de manutenção, grupos de trabalhadores, ferramentas e ativos.

1. Clique em **Gerenciamento de ativos** > **Consultas** > **Agendar** > **Capacidade máxima**.

2. No diálogo **Calcular a capacidade máxima** > campo **Mostrar**, selecione o tipo de carga que deseja calcular: **Capacidade**, **Reservado** ou **Pendência**.

3. Selecione **Sim** no botão de alternância **Ignorar zero** se não desejar exibir resultados contendo zero.

4. Selecione os tipos de recursos para os quais deseja calcular a capacidade máxima, selecionando **Sim** nos botões de alternância relevantes: **Trabalhador**, **Grupo de funcionários de manutenção**, **Ferramenta** e **Ativo**.

5. Selecione a data de início para o cálculo no campo **Data inicial**.

6. No campo **Tipo de intervalo**, selecione o intervalo para o cálculo: **Dia**, **Semana**, **Mês** ou **Trimestre**.

7. No campo **Frequência do período**, insira o número de intervalos que deseja calcular. Por exemplo, se você selecionou **Dia** como o tipo de intervalo e inseriu o número "5" nesse campo, será feito um cálculo de cinco dias a partir da data inicial.

8. Clique em **OK** para iniciar o cálculo.

A figura abaixo mostra o resultado de um cálculo que abrange três semanas para o tipo de carga **Reservado**.

![Figura 1](media/08-work-order-scheduling.png)

[!NOTE]
Se você selecionar os tipos de carga **Capacidade** ou **Pendente** para o cálculo, o mesmo resultado será exibido se nenhuma reserva tiver sido feita para os recursos no período selecionado.

Para obter informações sobre como calcular a capacidade máxima nas linhas de agendamento de manutenção e ordens de serviço não agendadas, consulte [Calcular a capacidade máxima](../capacity-planning/calculate-capacity-load.md).

