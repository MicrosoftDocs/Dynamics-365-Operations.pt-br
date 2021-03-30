---
title: Criar uma ordem de compra para um fornecedor ocasional
description: Este procedimento mostra como criar uma ordem de compra de um fornecedor ocasional.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d1abd942da608bc221a7a66e03b5269fa30e2c20
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5212021"
---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Criar uma ordem de compra para um fornecedor ocasional

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar uma ordem de compra de um fornecedor ocasional. O fornecedor é criado automaticamente com a ordem de compra, em vez de ter que criar manualmente a conta do vendedor. As ordens de compra geralmente são criadas com um agente de compra. O exemplo mostrado neste guia pode ser usado na empresa dos dados do programa demonstrativo de USMF. É uma condição prévia que uma única conta do vendedor estabeleceu na página dos parâmetros da conta a pagar.


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Criar uma ordem de compra para um fornecedor ocasional
1. Vá para Aquisição e fornecimento > Ordens de compra > Todas as ordens de compra.
2. Clique em Novo.
3. Selecione Sim no campo Fornecedor ocasional.
    * Uma conta do vendedor automaticamente é criada e atribuída à ordem de compra. A conta do vendedor é criada com base no molde que é especificado na aba geral na página dos parâmetros das contas a pagar.  
4. No campo Nome, digite um nome para o fornecedor.
5. Clique em OK.
    * A ordem de compra pode agora ser concluída e processada como toda a outra ordem. Não há nenhuma característica especial relativa a como isto é feito. A fatura explicará uma transação devida na conta do vendedor que foi criada com a ordem, e o pagamento será então processado.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]