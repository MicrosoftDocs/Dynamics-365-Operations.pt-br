--- 
title: "Configurações de pagamento para obter demonstrativos de varejo"
description: "Este procedimento demonstra configurações para os métodos de pagamento da loja de varejo que afetam como as instruções de varejo foram criadas e lançadas."
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 0ffd6dc5fff6d27ec3cfdcd68c53b2299c4100b9
ms.contentlocale: pt-br
ms.lasthandoff: 02/07/2018

---
# <a name="payment-configurations-for-retail-statements"></a>Configurações de pagamento para obter demonstrativos de varejo

[!INCLUDE [task guide banner](../includes/task-guide-banner.md)]

Este procedimento demonstra configurações para os métodos de pagamento da loja de varejo que afetam como as instruções de varejo foram criadas e lançadas.

Este registro usa a empresa de dados de demonstração USRT.

1. Vá para Varejo e comércio > Canais > Lojas de varejo > Todas as lojas de varejo.
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.
4. No Painel de Ação, clique em Configurar.
5. Clique em Métodos de pagamento.
6. Expandir ou recolher a seção Lançamento.
7. Clique em Editar.
    * Selecione se os valores recebidos para o método de pagamento devem ser lançados em uma conta contábil ou em uma conta bancária.  
    * Selecione a conta na qual os valores recebidos para o método de pagamento devem ser lançados.  
    * Selecione uma conta para lançar possíveis diferenças entre o valor total da transação recebida e o valor contado para este método de pagamento.  
    * Neste campo é possível inserir um valor para controlar quando o valor da diferença deverá ser lançado em outra conta de diferença. Você pode usar isso para rastrear as diferenças grandes.  
    * Selecione uma conta para lançar possíveis diferenças entre o valor total da transação recebida e o valor contado, quando ele excede o valor definido no campo "Valor de diferença máximo".  
    * Selecione "Sim" para lançar valores de depósito bancário em uma conta separada.  
    * Neste campo você pode selecionar se os valores de depósito bancário devem ser lançados para uma conta contábil ou para uma conta bancária.  
    * Selecione a conta para lançar valores de depósito bancário.  
    * Selecione o tipo de transação bancária a ser usado ao lançar valores de depósito bancário para a conta bancária.  
    * Selecione "Sim" para lançar valores de depósito bancário protegidos em uma conta separada.  
    * Selecione se os valores de depósito bancário protegidos devem ser lançados em uma conta contábil ou na conta bancária.  
    * Selecione a conta para lançar valores de depósito bancário protegidos.  
8. Clique em Salvar.


