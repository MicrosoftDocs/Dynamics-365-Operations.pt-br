---
title: Agendar uma ordem de produção
description: Este procedimento mostra como agendar uma ordem de produção.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob, WrkCtrCapResSum, ProdRouteJobSched, ProductionOrderScheduleDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8b3fe8f6890c7d8ac8835503091642faa773f7f6
ms.sourcegitcommit: 175f9394021322c685c5b37317c2f649c81a731a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/21/2020
ms.locfileid: "3826037"
---
# <a name="schedule-a-production-order"></a>Agendar uma ordem de produção

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como agendar uma ordem de produção. A empresa de dados demo usada para criar este procedimento é USMF. Este é o terceiro procedimento de sete que explica o ciclo de vida da ordem de produção.


## <a name="schedule-a-production-order"></a>Agendar uma ordem de produção
1. Vá para Controle de produção > Ordens de produção > Todas as ordens de produção.
    * Selecione uma ordem de produção com o status Estimado.  
2. No Painel de Ação, clique em Agenda.
3. Clique em Agendar trabalhos.
    * Os parâmetros para agendar são configurados nessa página. Você pode configurar os parâmetros para usuários específicos ou todos os usuários.  
4. No campo Direção do plano, selecione 'Avançar a partir de hoje'.
5. No campo Data de planejamento, insira uma data.
6. Marque ou desmarque a caixa de seleção Capacidade finita.
7. Marque ou desmarque a caixa de seleção Material finito.
8. Clique em OK.

## <a name="view-the-scheduling-results"></a>Exiba os resultados do agendamento
1. No Painel de Ação, clique em Ordem de produção.
2. Clique em Todos os trabalhos.
    * Essa página exibe os trabalhos programados que você acabou de gerar.  
3. Expanda ou recolha a seção Plano.
    * Na Guia Rápida Programação, você pode exibir a data e a hora programadas.  
4. Clique em Consultas.
5. Clique em Capacidade máxima.
    * A página Capacidade máxima exibe a capacidade reservada com o agendamento do trabalho, o número total de horas que está reservado no recurso atualmente, e o número de horas que permanece disponível para o planejamento de trabalho do recurso.  
6. Feche a página.
7. Feche a página.

