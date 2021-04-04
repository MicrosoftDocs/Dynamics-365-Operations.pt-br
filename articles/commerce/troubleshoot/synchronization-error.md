---
title: Erro de sincronização da ordem relacionado ao serviço de pagamento padrão
description: Este tópico fornece orientações de solução de problemas que podem ajudar a corrigir um erro que pode ocorrer quando uma ordem online é sincronizada.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: dd7c400f26b6fc7fbe1d4fec43a52295eb363333
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585189"
---
# <a name="order-synchronization-error-related-to-the-default-payment-service"></a>Erro de sincronização da ordem relacionado ao serviço de pagamento padrão

[!include [banner](../../includes/banner.md)]

Este tópico fornece orientações de solução de problemas que podem ajudar a corrigir um erro que pode ocorrer quando uma ordem online é sincronizada.

## <a name="description"></a>descrição

Ao sincronizar uma ordem online, você recebe a seguinte mensagem de erro: "deve haver um serviço de pagamento padrão para processar transações de cartão de crédito".

![Erro de serviço de pagamento padrão ausente](media/default-payment-method-error.jpg)

## <a name="resolution"></a>Resolução

### <a name="confirm-or-set-the-default-payment-service-in-commerce-headquarters"></a>Confirmar ou definir o serviço de pagamento padrão na matriz do Commerce

Para confirmar ou definir o serviço de pagamento padrão na matriz do Commerce, siga estas etapas.

1. Vá para **Contas a receber \> Configuração de pagamento \> Serviços de pagamento**.
1. Verifique se a opção **Processador padrão para novos cartões de crédito** está definida como **Sim** para um serviço de pagamento.

## <a name="additional-resources"></a>Recursos adicionais

[Configuração, autorização e captura de cartão de crédito](https://docs.microsoft.com/dynamics365/finance/accounts-receivable/credit-card-authorizations)
