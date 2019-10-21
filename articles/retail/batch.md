---
title: Manuseio aprimorado de itens de lote rastreados
description: Este tópico descreve os aprimoramentos feitos no manuseio de lotes para itens de lote rastreados durante o processo de lançamento de demonstrativo do Retail.
author: josaw1
manager: AnnBe
ms.date: 05/28/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: 10
ms.openlocfilehash: 35823efa2844898d3eecbf91624b3e37d308b63c
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2019
ms.locfileid: "2025785"
---
# <a name="improved-handling-of-batch-tracked-items"></a>Manuseio aprimorado de itens de lote rastreados

No ponto de venda (PDV) do Retail, os números de lotes não podem ser capturados para itens de lote rastreados no momento da venda. No entanto, para configurações específicas, quando as vendas lançadas na matriz por meio de ordens de cliente ou lançamento de demonstrativo, o sistema do Microsoft Dynamics espera que existam números de lote válidos para itens de lote rastreados e que eles sejam usados durante o processo de faturamento.

Se os números de lote válidos estiverem disponíveis para os produtos, eles serão usados pelo processo de faturamento da ordem do cliente e pelo processo de faturamento da ordem de venda do lançamento de demonstrativo. Caso contrário, processo de faturamento da ordem do cliente não poderá fazer o lançamento e o usuário do PDV receberá uma mensagem de erro. O lançamento do demonstrativo entrará então em um estado de erro. Esse estado de erro ocorrerá mesmo quando o estoque negativo tiver sido ativado para os produtos.

Os aprimoramentos feitos no Retail versão 10.0.4 e posterior ajudam a garantir que, quando o estoque negativo for ativado para itens de lote rastreados, o faturamento da ordem do cliente e o faturamento da ordem venda por meio do lançamento de demonstrativo não serão bloqueados para esses itens se o estoque for 0 (zero) ou se um número de lote não estiver disponível. A nova funcionalidade usa uma ID de lote padrão para as linhas de venda quando os números de lotes não estão disponíveis.

Para definir a ID padrão do lote usada para ordens de cliente, na página **Parâmetros de varejo** , na guia **Ordens do cliente**, na FastTab **Ordem**, defina o campo **ID de lote padrão**.

Para definir a ID de lote padrão usada para o faturamento da ordem do cliente por meio do lançamento de demonstrativo, na página **Parâmetros de varejo**, na guia **Lançamento**, na FastTab **Atualização de estoque**, defina o campo **ID de lote padrão**.

> [!NOTE]
> Esta funcionalidade ficará disponível somente quando o armazenamento avançado for ativado para os depósitos e o itens de específicos da loja. Em uma versão posterior, a funcionalidade também terá suporte para cenários em que o gerenciamento de armazenamento não é usado.
