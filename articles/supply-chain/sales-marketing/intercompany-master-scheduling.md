---
title: Agendamento do planejamento mestre intercompanhia
description: Este tópico explica o planejamento mestre intercompanhia
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 02d1a3675cfe30f2e72237f69509398122d17f05
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8671860"
---
# <a name="intercompany-master-scheduling"></a>Agendamento do planejamento mestre intercompanhia

[!include [banner](../../includes/banner.md)]

O planejamento mestre intercompanhia é o meio pelo qual se pode calcular requisições e gerar ordens planejadas intercompanhia em diversas empresas internas. O planejamento mestre intercompanhia é realizado por meio do número de iterações que você especificar. Para permitir que o Microsoft Dynamics 365 Supply Chain Management realize o planejamento mestre intercompanhia, será preciso configurar o planejamento mestre em cada uma das empresas intercompanhia. Isso ocasiona diversas iterações nas quais o Microsoft Dynamics 365 Supply Chain Management cria automaticamente uma ordem de compra intercompanhia, levando à criação automática de uma ordem de venda intercompanhia que, novamente, leva a novas demandas.

Configure o plano mestre intercompanhia e a ordem de planejamento intercompanhia nos parâmetros de **Planejamento mestre** de cada uma das empresas intercompanhia.

A fim de propagar a demanda em todo o grupo intercompanhia, é preciso definir parâmetros para garantir que as ordens de compra planejadas sejam automaticamente confirmadas; ou seja, as ordens não podem ser alteradas em termos de tempo ou quantidade. Configure o **Limite de tempo de confirmação** no grupo Cobertura ou o **Limite de tempo de confirmação** no Planejamento mestre. Se nenhum **Limite de tempo de confirmação** for configurado, nenhuma ordem de compra intercompanhia será criada automaticamente. Somente a primeira execução do planejamento mestre resulta em ordens planejadas. No entanto, como nenhuma ordem de compra intercompanhia é criada, nenhuma ordem de venda intercompanhia é criada e, portanto, nenhuma outra ordem de compra intercompanhia é criada e assim por diante.

Quando você inicia o planejamento mestre intercompanhia, o Microsoft Dynamics 365 Supply Chain Management executa um planejamento mestre em cada empresa intercompanhia e, em seguida, realiza um segundo planejamento mestre em cada empresa intercompanhia e assim por diante, até que o número especificado de iterações seja alcançado. São possíveis, no máximo, 30 iterações; entretanto, quanto mais iterações você escolher, mais tempo demorará o agendamento.

Como o agendamento do planejamento mestre nas empresas é controlado pela sequência do agendamento intercompanhia, ou seja, a ordem na qual o programa prioriza os planejamentos mestre entre cada empresa intercompanhia, você poderá iniciar o agendamento do planejamento mestre intercompanhia de qualquer uma das empresas intercompanhia. Como a sequência de planejamento intercompanhia determina a ordem na qual o planejamento mestre é executado nas empresas, não é importante saber onde o planejamento mestre intercompanhia é iniciado. A cada iteração, a empresa atual é executada por último.

> [!NOTE]
> A prática recomendada é permitir que o planejamento mestre intercompanhia seja iniciado de uma empresa do Microsoft Dynamics 365 Supply Chain Management.

Na página **Planejamento mestre intercompanhia**, você pode iniciar uma sequência de planejamento mestre que execute um planejamento mestre na primeira vez com o princípio de atualização do cálculo de requisições que você selecionou para a primeira iteração em todas as empresas intercompanhia. As iterações subsequentes usam o princípio secundário que você selecionou para a próxima iteração e esse princípio é aplicado até que o número de iterações especificadas seja alcançado.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
