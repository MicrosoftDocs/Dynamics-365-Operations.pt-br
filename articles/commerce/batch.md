---
title: Manuseio aprimorado de itens de lote rastreados
description: Este tópico descreve os aprimoramentos feitos no manuseio de lotes para itens de lote rastreados durante o processo de lançamento de demonstrativo.
author: josaw1
manager: AnnBe
ms.date: 11/04/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: 10
ms.openlocfilehash: ef946df30c68373b83660fce98b472dc94b42719
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5114701"
---
# <a name="improved-handling-of-batch-tracked-items"></a>Manuseio aprimorado de itens de lote rastreados


[!include [banner](includes/banner.md)]


No ponto de venda (PDV), os números de lote não podem ser capturados para itens de lote rastreados no momento da venda. No entanto, para configurações específicas, quando as vendas lançadas na matriz por meio de ordens de cliente ou lançamento de demonstrativo, o sistema do Microsoft Dynamics espera que existam números de lote válidos para itens de lote rastreados e que eles sejam usados durante o processo de faturamento.

Se os números de lote válidos estiverem disponíveis para os produtos, eles serão usados pelo processo de faturamento da ordem do cliente e pelo processo de faturamento da ordem de venda do lançamento de demonstrativo. Caso contrário, processo de faturamento da ordem do cliente não poderá fazer o lançamento e o usuário do PDV receberá uma mensagem de erro. O lançamento do demonstrativo entrará então em um estado de erro. Esse estado de erro ocorrerá mesmo quando o estoque negativo tiver sido ativado para os produtos.

Os aprimoramentos feitos no Retail versão 10.0.4 e posterior ajudam a garantir que, quando o estoque negativo for ativado para itens de lote rastreados, o faturamento da ordem do cliente e o faturamento da ordem venda por meio do lançamento de demonstrativo não serão bloqueados para esses itens se o estoque for 0 (zero) ou se um número de lote não estiver disponível. A nova funcionalidade usa uma ID de lote padrão para as linhas de venda quando os números de lotes não estão disponíveis.

Para definir a ID padrão do lote usada para ordens de cliente, na página **Parâmetros do Commerce**, na guia **Ordens do cliente**, na FastTab **Ordem**, defina o campo **ID de lote padrão**.

Para definir a ID de lote padrão usada para o faturamento da ordem de venda por meio do lançamento de demonstrativo, na página **Parâmetros do Commerce**, na guia **Lançamento**, na FastTab **Atualização de estoque**, defina o campo **ID de lote padrão**.

> [!NOTE]
> Esta funcionalidade ficará disponível somente quando o armazenamento avançado for ativado para os depósitos e o itens de específicos da loja. Em uma versão posterior, a funcionalidade também terá suporte para cenários em que o gerenciamento de armazenamento não é usado.

> [!NOTE]
> O suporte ao manuseio aprimorado de itens de lote rastreados durante o lançamento de demonstrativo a cenários de gerenciamento de depósito não avançado foi apresentado no Retail versão 10.0.5.


[!INCLUDE[footer-include](../includes/footer-banner.md)]