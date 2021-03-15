---
title: Solucionar problemas de cotações de venda
description: Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com as cotações de vendas.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationTable, SalesQuotationTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 98011dbf22ff55b7651ce63557fa4a360130b6af
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974751"
---
# <a name="troubleshoot-sales-quotations"></a>Solucionar problemas de cotações de venda

Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com as cotações de vendas.

## <a name="i-cant-change-the-sales-quantity-of-a-sales-quotation-for-a-service-item"></a>Não consigo alterar a quantidade de venda de uma cotação de venda para um item de serviço.

### <a name="issue-description"></a>Descrição do problema

Se você tentar definir uma quantidade de venda (**campo SalesQty**) para um item do tipo *Serviço* em uma linha da cotação de venda, você receberá a seguinte mensagem: "Atualização não permitida para o campo Quantidade".

### <a name="issue-resolution"></a>Resolução do problema

Não é possível definir uma quantidade de venda para produtos que são itens de serviço. Por exemplo, se você oferece um serviço para instalar um item, não faz sentido registrar uma quantidade porque não há um item físico. Há apenas um serviço.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]