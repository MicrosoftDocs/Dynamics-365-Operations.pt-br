---
title: Criar ordens de serviço automaticamente
description: É possível criar ordens de serviço para um ou vários contratos de serviço.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 914df1626b02110264b895e82dc9301f3aa0afce
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422371"
---
# <a name="create-service-orders-automatically"></a>Criar ordens de serviço automaticamente    

[!include [banner](../includes/banner.md)]


É possível criar ordens de serviço para um ou vários contratos de serviço. Depois de criá-los, exiba os contratos de serviço no formulário **Ordens de serviço**.

As ordens de serviço são criadas apenas pelo período válido do contrato de serviço. Se o intervalo especificado na caixa no formulário **Criar ordens de serviço** for anterior à data inicial ou posterior à data final do contrato de serviço, as ordens de serviço serão criadas apenas para a parte do intervalo que está dentro das datas do contrato de serviço.

Ao criar ordens de serviço manual ou automaticamente a partir da linha de contrato de serviço, a ordem de serviço deve estar dentro do intervalo de tempo definido pelas datas inicial e final da linha, a menos que você não especifique uma data final na linha.

## <a name="create-service-orders-automatically-for-a-service-agreement"></a>Criar ordens de serviço automaticamente para um contrato de serviço

1.  Clique em **Gerenciamento de serviços** \> **Comum** \> **Contratos de serviço** \> **Contratos de serviço**.

2.  Selecione um contrato de serviço.

3.  Clique na guia **Entregar** e depois clique em **Ordens de serviço planejadas**.

4.  Especifique as datas nos campos **Data inicial** e **Data final** para definir o período de serviço.

5.  Marque a caixa de seleção **Mostrar Log de Informações** para exibir uma lista de ordens de serviço criadas.

6.  Selecione os tipos de transação no grupo de campo **Incluir tipos de transação**. Os tipos de transação representam as linhas criadas no contrato de serviço, e cada tipo de transação selecionada gera várias ordens de serviço, dependendo do intervalo de serviço especificado na linha do contrato de serviço.

7.  Para criar todas as ordens de serviço ausentes da série contínua de ordens de serviço, marque a caixa de seleção **Contínuo**.

8.  Clique em **OK**.

## <a name="create-service-orders-automatically-for-several-service-agreements"></a>Criar ordens de serviço automaticamente para vários contratos de serviço

1.  Clique em **Gerenciamento de serviço** \> **Periódico** \> **Ordens de serviço** \> **Criar ordens de serviço**.

2.  Clique em **Selecionar** para fazer seleções para adicionar ou remover critérios usados para criar ordens de serviço.

3.  Clique em **OK**.

## <a name="see-also"></a>Consulte também

[Ordens de serviço](service-orders.md)

[Criar automaticamente ordens de serviço](auto-create-service-orders.md)

  


