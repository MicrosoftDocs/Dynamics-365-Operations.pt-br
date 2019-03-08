---
title: Configurações de pagamento para obter demonstrativos de varejo
description: Este procedimento demonstra configurações para os métodos de pagamento da loja de varejo que afetam como as instruções de varejo foram criadas e lançadas.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8f49a3ae05d35b0f0ca6a08007f5b05321c1f5ab
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "314454"
---
# <a name="payment-configurations-for-retail-statements"></a>Configurações de pagamento para obter demonstrativos de varejo

[!include[task guide banner](../includes/task-guide-banner.md)]

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

