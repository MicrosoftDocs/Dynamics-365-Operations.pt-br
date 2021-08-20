---
title: Restringir métodos de pagamento para devoluções sem recibos
description: Este tópico descreve como determinados tipos de pagamento podem ser restritos para o reembolso se as devoluções forem feitas sem recebimento.
author: rapraj
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2019-02-01
ms.dyn365.ops.version: AX 10.0.0, Retail Feb 2019 update
ms.openlocfilehash: 716b3a924da14d94061966d0d671003a6e2b90f88a3c0c4064191b47d8930f93
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773829"
---
# <a name="restrict-payment-methods-for-returns-without-a-receipt"></a>Restringir métodos de pagamento para devoluções sem recibos


[!include [banner](includes/banner.md)]

Cada tipo de pagamento que o varejista aceita deve ser configurado quando o sistema for configurado. Este tópico descreve como determinados tipos de pagamento podem ser restritos para o reembolso se as devoluções forem feitas sem recebimento.

## <a name="set-up-payment-methods"></a>Configurar métodos de pagamento

Para configurar métodos de pagamento, as seguintes tarefas devem ser concluídas.
1. Criar os métodos de pagamento aceitos pela organização inteira.
2. Criar tipos e números de cartão no nível da organização. Se cartões de crédito ou de débito forem aceitos, você deve criar um tipo de método de pagamento com cartões e os tipos e números de cartão no nível da organização.
3. Configurar métodos de pagamento da loja. Associe métodos de pagamento a cada loja e insira as configurações específicas da loja para cada método de pagamento.
4. Configurar métodos de pagamento de cartão para lojas. Para todos os métodos de pagamento de cartão que a loja aceita, conclua a configuração do cartão.

![Configuração de loja.](media/NoReceiptReturns1.png "Configuração de Loja de Varejo") 


## <a name="restrict-payment-methods-for-returns-without-a-receipt"></a>Restringir métodos de pagamento para devoluções sem recibos

Para cada método de pagamento da loja, na página **Gerenciamento de loja**, em **Devoluções sem recibos**, defina **Restringir para reembolsos sem recibo** como **Sim**. 

O valor padrão de alternância é **Não**, o que garante que o método de pagamento seja permitido para reembolsos. 

Quando **Restringir para reembolsos sem recibo** for definido como **Sim**, o método de pagamento selecionado não será permitido para reembolsos. 

![Método de pagamento da loja.](media/NoReceiptReturns3.png "Método de Pagamento da Loja de Varejo") 

> [!NOTE]
> Quando um caixa seleciona um método de pagamento que é restrito para o reembolso sem um recibo, será exibida uma mensagem para verificar os métodos de pagamento aceitáveis.

![Métodos de pagamento aceitáveis.](media/NoReceiptReturns4.png "Métodos de pagamento aceitáveis") 

Se uma transação tiver uma devolução com recibo e uma sem recibo, as condições de restrição não serão impostas porque a transação será um fluxo de trabalho de devolução com um recibo. 



[!INCLUDE[footer-include](../includes/footer-banner.md)]