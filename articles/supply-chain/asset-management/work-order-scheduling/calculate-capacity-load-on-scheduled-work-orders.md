---
title: Calcular a capacidade máxima em ordens de serviço agendadas
description: Este artigo explica como calcular a capacidade máxima em ordens de serviço agendadas no Gerenciamento de Ativos.
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 53b147198f6aa9e0254312e5ea48b9ae616a79a9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8857943"
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

![Figura 1.](media/08-work-order-scheduling.png)

[!NOTE]
Se você selecionar os tipos de carga **Capacidade** ou **Pendente** para o cálculo, o mesmo resultado será exibido se nenhuma reserva tiver sido feita para os recursos no período selecionado.

Para obter informações sobre como calcular a capacidade máxima nas linhas de agendamento de manutenção e ordens de serviço não agendadas, consulte [Calcular a capacidade máxima](../capacity-planning/calculate-capacity-load.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]