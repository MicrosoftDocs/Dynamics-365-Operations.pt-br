---
title: Configurações de pagamento para obter demonstrativos de varejo
description: Este procedimento demonstra configurações para os métodos de pagamento da loja do Commerce que afetam como as instruções são criadas e lançadas.
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
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b1fc042bff4d801ae893b0370b67cd8e11ba95f6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4982304"
---
# <a name="payment-configurations-for-retail-statements"></a>Configurações de pagamento para obter demonstrativos de varejo

[!include [banner](../includes/banner.md)]

Este procedimento demonstra configurações para os métodos de pagamento da loja do Commerce que afetam como as instruções são criadas e lançadas.

Este registro usa a empresa de dados de demonstração USRT.

1. Vá para Retail e Commerce > Canais > Lojas > Todas as lojas.
2. Na lista, localize e selecione o registro desejado.
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



[!INCLUDE[footer-include](../../includes/footer-banner.md)]