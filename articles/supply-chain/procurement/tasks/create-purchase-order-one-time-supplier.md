---
title: Criar uma ordem de compra para um fornecedor ocasional
description: Este procedimento mostra como criar uma ordem de compra de um fornecedor ocasional.
author: FrankDahl
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 26c62aa72a7919c780bb709b185b48c97066c538
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1836303"
---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Criar uma ordem de compra para um fornecedor ocasional

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como criar uma ordem de compra de um fornecedor ocasional. O fornecedor é criado automaticamente com a ordem de compra, em vez de ter que criar manualmente a conta do vendedor. As ordens de compra geralmente são criadas com um agente de compra. O exemplo mostrado neste guia pode ser usado na empresa dos dados do programa demonstrativo de USMF. É uma condição prévia que uma única conta do vendedor estabeleceu na página dos parâmetros da conta a pagar.


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Criar uma ordem de compra para um fornecedor ocasional
1. Vá para Aquisição e fornecimento > Ordens de compra > Todas as ordens de compra.
2. Clique em Novo.
3. Selecione Sim no campo Fornecedor ocasional.
    * Uma conta do vendedor automaticamente é criada e atribuída à ordem de compra. A conta do vendedor é criada com base no molde que é especificado na aba geral na página dos parâmetros das contas a pagar.  
4. No campo Nome, digite um nome para o fornecedor.
5. Clique em OK.
    * A ordem de compra pode agora ser concluída e processada como toda a outra ordem. Não há nenhuma característica especial relativa a como isto é feito. A fatura explicará uma transação devida na conta do vendedor que foi criada com a ordem, e o pagamento será então processado. Quando isto é concluído, a conta do vendedor pode ser suprimida. Isto é feito tipicamente pelo departamento das contas a pagar.  

