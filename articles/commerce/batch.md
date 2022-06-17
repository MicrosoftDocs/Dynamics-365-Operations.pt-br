---
title: Manuseio aprimorado de itens de lote rastreados
description: Este artigo descreve os itens de lote aprimorados rastreados durante o processo de lançamento de demonstrativo no Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 09/09/2021
ms.topic: index-page
ms.prod: ''
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
ms.openlocfilehash: 736ab8dd21f04d7119cca6d53bfeb5e408b8cbd2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8881868"
---
# <a name="improved-handling-of-batch-tracked-items"></a>Manuseio aprimorado de itens de lote rastreados

[!include [banner](includes/banner.md)]

Este artigo descreve os itens de lote aprimorados rastreados durante o processo de lançamento de demonstrativo no Microsoft Dynamics 365 Commerce.

No ponto de venda (PDV) do Dynamics 365 Commerce, os números de lote não podem ser capturados para itens de lote rastreados no momento da venda. No entanto, para configurações específicas, quando as vendas lançadas na matriz do Commerce por meio de ordens de cliente ou lançamento de demonstrativo, o Commerce espera que existam números de lote válidos para itens de lote rastreados e que eles sejam usados durante o processo de faturamento.

Se os números de lote válidos estiverem disponíveis para os produtos, eles serão usados pelo processo de faturamento da ordem do cliente e pelo processo de faturamento da ordem de venda do lançamento de demonstrativo. Se os números de lote válidos não estiverem disponíveis para os produtos, o processo de faturamento da ordem do cliente não será lançado e o usuário do PDV receberá uma mensagem de erro. O lançamento do demonstrativo entrará em um estado de erro, mesmo se o estoque negativo tiver sido ativado para os produtos.

Os aprimoramentos feitos no Commerce ajudam a garantir que, quando o estoque negativo for ativado para itens de lote rastreados, o faturamento da ordem do cliente e o faturamento da ordem venda por meio do lançamento de demonstrativo não serão bloqueados para esses itens se o estoque for 0 (zero) ou se um número de lote não estiver disponível. A funcionalidade aprimorada usa uma ID de lote padrão para as linhas de venda quando os números de lotes não estão disponíveis.

## <a name="define-the-default-batch-id-that-is-used-for-customer-orders"></a>Definir a ID de lote padrão que é usada para ordens do cliente

Para definir a ID de lote padrão que é usada para ordens do cliente, siga estas etapas:

1. Na matriz do Commerce, acesse **Retail e Commerce \> Configuração da sede \> Parâmetros \> Parâmetros do Commerce**.
1. Na guia **Ordens do cliente**, na Guia Rápida **Ordem**, insira um valor no campo **ID de lote padrão**.

## <a name="define-the-default-batch-id-that-is-used-for-sales-order-invoicing-through-statement-posting"></a>Definir a ID de lote padrão que é usada para o faturamento da ordem de venda por meio do lançamento de demonstrativos

Para definir a ID de lote padrão que é usada para o faturamento da ordem de venda por meio do lançamento de demonstrativos, siga estas etapas:

1. Na matriz do Commerce, acesse **Retail e Commerce \> Configuração da sede \> Parâmetros \> Parâmetros do Commerce**.
1. Na guia **Lançamento**, na Guia Rápida **Atualização de estoque**, insira um valor no campo **ID de lote padrão**.

> [!NOTE]
> - A funcionalidade ID de lote padrão ficará disponível somente quando o armazenamento avançado estiver habilitado para os depósitos e o itens de específicos da loja. Em uma versão futura, a funcionalidade ID de lote padrão também terá suporte para cenários em que o gerenciamento de depósito avançado não esteja habilitado.
> - O suporte ao manuseio aprimorado de itens de lote rastreados durante o lançamento de demonstrativo para cenários de gerenciamento de depósito não avançado foi apresentado no Commerce versão 10.0.5.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
