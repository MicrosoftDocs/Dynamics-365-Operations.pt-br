---
title: Restringir métodos de pagamento para devoluções sem recibos
description: Este tópico descreve como determinados tipos de pagamento podem ser restritos para o reembolso se as devoluções forem feitas sem recebimento.
author: rapraj
manager: AnnBe
ms.date: 01/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2019-02-01
ms.dyn365.ops.version: AX 10.0.0, Retail Feb 2019 update
ms.openlocfilehash: 1f84a6382453c0ba7540e618ad90ae1d3c684a2b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "315903"
---
# <a name="restrict-payment-methods-for-returns-without-a-receipt"></a>Restringir métodos de pagamento para devoluções sem recibos

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Cada tipo de pagamento que o varejista aceita deve ser configurado quando o sistema for configurado. Este tópico descreve como determinados tipos de pagamento podem ser restritos para o reembolso se as devoluções forem feitas sem recebimento.

## <a name="set-up-payment-methods"></a>Configurar métodos de pagamento

Para configurar métodos de pagamento, as seguintes tarefas devem ser concluídas.
1. Criar os métodos de pagamento aceitos pela organização inteira.
2. Criar tipos e números de cartão no nível da organização. Se cartões de crédito ou de débito forem aceitos, você deve criar um tipo de método de pagamento com cartões e os tipos e números de cartão no nível da organização.
3. Configurar métodos de pagamento da loja. Associe métodos de pagamento a cada loja e insira as configurações específicas da loja para cada método de pagamento.
4. Configurar métodos de pagamento de cartão para lojas. Para todos os métodos de pagamento de cartão que a loja aceita, conclua a configuração do cartão.

![Configuração de Loja de Varejo](media/NoReceiptReturns1.png "Configuração de Loja de Varejo") 


## <a name="restrict-payment-methods-for-returns-without-a-receipt"></a>Restringir métodos de pagamento para devoluções sem recibos

Para cada método de pagamento da loja, na página **Gerenciamento de loja de Varejo** , em **Devoluções sem recibos**, defina **Restringir métodos de pagamento para devoluções sem recibos** como **Sim**. 

O valor padrão de alternância é **Não**, o que garante que o método de pagamento seja permitido para reembolsos. 

Quando **Restringir para reembolsos sem recibo** for definido como **Sim**, o método de pagamento selecionado não será permitido para reembolsos. 

![Método de pagamento da Loja de Varejo](media/NoReceiptReturns3.png "Método de pagamento da Loja de Varejo") 

> [!NOTE]
> Quando um caixa seleciona um método de pagamento que é restrito para o reembolso sem um recibo, será exibida uma mensagem para verificar os métodos de pagamento aceitáveis.

![Métodos de pagamento aceitáveis](media/NoReceiptReturns4.png "Métodos de pagamento aceitáveis") 

Se uma transação tiver uma devolução com recibo e uma sem recibo, as condições de restrição não serão impostas porque a transação será um fluxo de trabalho de devolução com um recibo. 

