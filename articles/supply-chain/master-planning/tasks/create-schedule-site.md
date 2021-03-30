---
title: Criar uma agenda para um site
description: Este procedimento mostra como planejar ordens de produção que ainda não foram iniciadas para um site.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f9e188c5059b3957f3c0291bc4b8c525aac4d399
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5214265"
---
# <a name="create-a-schedule-for-a-site"></a>Criar uma agenda para um site

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como planejar ordens de produção que ainda não foram iniciadas para um site.  A empresa de dados demo USMF é usada para completar este procedimento.


## <a name="identify-production-orders-that-are-not-started"></a>Identificar ordem de produção que não foram iniciadas
1. Vá para Controle de produção > Ordens de produção > Todas as ordens de produção.
2. Use o Filtro Rápido para localizar registros. Por exemplo, filtre o campo Site com um valor de '1'.
    * 1 representa um site em USMF. Se você não estiver usando USMF, selecione um site em sua própria empresa.  
3. Abra o filtro da coluna Status.
4. Aplicar um filtro no campo "Status", com um valor de "Agendado", usando o operador de filtro "é exatamente".

## <a name="create-a-schedule"></a>Criar uma agenda
1. Na lista, marque ou desmarque todas as linhas.
2. No Painel de Ação, clique em Agenda.
3. Clique em Agendar trabalhos.
4. No campo Direção do plano, selecione 'Voltar a partir da data de entrega'.
5. Selecione Não no campo Capacidade finita.
6. Selecione Não no campo Material finito.
7. Clique em OK.
    * Isso pode levar algum tempo.  

## <a name="view-the-result-of-scheduled-production-orders"></a>Exibe o resultado das ordens de produção programadas
1. Na lista, marque a linha selecionada.
    * Você pode marcar todas as linhas.  
2. No Painel de Ação, clique em Ordem de produção.
3. Clique em Todos os trabalhos.
    * Nessa página, você pode ver a lista de trabalho. Na guia de programação, você pode ver as datas de início e fim de um trabalho.  
4. Clique em Materiais.
    * Nessa página, você pode ver o consumo de material previsto para as operações na ordem de produção e de estoque disponível atualmente.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]