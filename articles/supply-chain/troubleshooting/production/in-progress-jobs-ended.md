---
title: Os trabalhos em andamento são encerrados ao relatar a quantidade parcial no último trabalho
description: Ao usar o dispositivo de ficha de trabalho para relatar uma quantidade parcial do último trabalho em uma ordem de produção, todos os trabalhos anteriores com status Em andamento são encerrados.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 11511d4ac7524facdd0d647e9bc38fe09c282be1
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475622"
---
# <a name="previous-in-progress-jobs-are-ended-when-reporting-partial-quantity-on-last-job"></a>Os trabalhos em andamento anteriores são finalizados ao relatar a quantidade parcial no último trabalho

## <a name="symptoms"></a>Sintomas

Ao usar o dispositivo de ficha de trabalho para relatar uma quantidade parcial do último trabalho em uma ordem de produção, todos os trabalhos anteriores nessa ordem com status Em andamento são encerrados automaticamente.

## <a name="resolution"></a>Resolução

Esse comportamento é por design. Na página **Padrões de ordem de produção**, na guia **Relatar como concluído**, há uma opção chamada **Marcar fim de roteiro**. Se este tópico for definido como *Sim*, um diário de cartão de rota será lançado quando um trabalhador usar o dispositivo de cartão de trabalho ou terminal de cartão de trabalho para relatar a operação mais recente. Esse diário marca todas as operações como concluídas e encerra todos os trabalhos de produção. Quando a opção **Marcar fim de roteiro** é definida como *Sim*, o sistema não considera o status do trabalho que o trabalhador selecionou quando relatou a operação mais recente. O sistema também não considera se o trabalhador está relatando uma quantidade total ou parcial.
