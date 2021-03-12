---
title: Solucionar problemas de trabalho do depósito
description: Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com trabalho de depósito no Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 3015ec777953cedb5a5d8eea873ed1043cac04cb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970222"
---
# <a name="troubleshoot-warehouse-work"></a>Solucionar problemas de trabalho do depósito

[!include [banner](../includes/banner.md)]

Este tópico descreve como corrigir problemas comuns que você pode encontrar ao trabalhar com trabalho de depósito no Microsoft Dynamics 365 Supply Chain Management.

## <a name="i-cant-move-license-plates-that-have-serial-number-items-when-blank-issue-and-blank-receipt-are-allowed-on-the-tracking-dimension-group"></a>Não consigo mover placas de licença com itens de número de série quando a emissão e o recebimento em branco são permitidos no grupo de dimensão de rastreamento.

### <a name="issue-description"></a>Descrição do problema

Você não consegue mover uma placa de licença usando um item de menu **Movimento** se o número de série tiver configurações de *Problema em branco permitido* e *Recibo em branco permitido* no grupo de dimensão de rastreamento e se houver várias placas no mesmo local, algumas das quais com números de série e outras sem.

### <a name="issue-resolution"></a>Resolução do problema

Esse problema será corrigido por mudanças que são implantadas no [KB 4571546](https://fix.lcs.dynamics.com/Issue/Details?kb=4571546&bugId=467880&dbType=3&qc=5b46d7faa9cc326cebfe9854cb30be8ea30b21ef33d3572c325fbb21202de687). Essas alterações tornarão o campo **Número de série** opcional quando recibo e emissão em branco forem permitidos.

## <a name="i-receive-the-following-error-message-in-the-warehouse-app-when-i-process-movements-the-inventory-owner-1-is-not-allowed-in-this-process"></a>Recebo a seguinte mensagem de erro no aplicativo de depósito quando processo movimentos: "O proprietário do estoque %1 não é permitido neste processo."

### <a name="issue-description"></a>Descrição do problema

A dimensão de rastreamento do **Proprietário** está ausente quando o aplicativo de depósito é usado para fazer movimentos. Um diário regular de transferência de estoque do cliente do Supply Chain Management parece funcionar conforme o esperado e pode ser lançado apenas se a dimensão do **Proprietário** for preenchida.

### <a name="issue-resolution"></a>Resolução do problema

A Microsoft avaliou esse problema e determinou que é uma limitação de recurso. Atualmente, os processos de gerenciamento de depósito oferecem suporte apenas ao estoque de propriedade da entidade legal.
