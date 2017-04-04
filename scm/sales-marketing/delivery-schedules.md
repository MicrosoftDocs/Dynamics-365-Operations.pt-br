---
title: Agendas de entrega
description: "As agendas de entrega permitem que você rastreie a quantidade da linha da ordem quando estiver usando várias entregas para uma única ordem de venda, cotação de venda ou ordem de compra."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: PurchDeliverySchedule, SalesDeliverySchedule, SalesQuotationDeliverySchedule
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 213984
ms.assetid: 44cac104-c36c-4371-a992-9178b3fd65e9
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: fbada697060c823b0afdb72d1c0cfd8703f4d527
ms.lasthandoff: 03/31/2017


---

# <a name="delivery-schedules"></a>Agendas de entrega

As agendas de entrega permitem que você rastreie a quantidade da linha da ordem quando estiver usando várias entregas para uma única ordem de venda, cotação de venda ou ordem de compra.

Use uma agenda de entrega na quantidade total em uma linha de ordem ou cotação deve ser entregue em várias remessas. Remessas individuais são representadas por linhas de entrega. Duas ou mais linhas de entrega compõem uma agenda de entrega. As linhas de entrega podem ter datas de entrega, quantidades, modos de entrega e dimensões de armazenamento diferentes, como o local e o depósito.  

**Exemplo de uma agenda de entrega**

|                                   |                                          |
|-----------------------------------|------------------------------------------|
| Ordem total (linha da ordem original) | 600 cadeiras                               |
| Agenda de entrega solicitada       | 100 cadeiras por mês                     |
| Período solicitado para entrega | 6 meses, no primeiro dia de cada mês |

Neste cenário, o cliente solicita uma entrega de 600 cadeiras em lotes de 100 cadeiras durante um período de seis meses. Para controlar os requisitos de entrega, você cria uma agenda de entrega. Na página da agenda de entrega, você cria seis linhas de entrega separadas. Cada linha de entrega contem 100 cadeiras e indica a data de entrega para essas 100 cadeiras. Neste caso, cada linha é compensada no primeiro dia do mês, por seis meses consecutivos.  

Quando você cria uma agenda de entrega, o tipo da linha da ordem original será alterado automaticamente para **Linha da ordem com várias entregas**. Uma linha deste tipo é mencionada como uma linha comercial e é marcada por um ícone. A linha de entrega é marcada por um ícone diferente. Se você alterar a quantidade em uma linha de entrega, a linha de negócios é atualizada à quantidade total da agenda de entrega. Se um contrato comercial definido um desconto total da ordem, o plano de entrega garante que a ordem foi qualificado para a ordem total, mesmo quando a ordem for dividido em entregas separadas.  

Ordens que tenham uma agenda de entrega são processadas em relação às linhas de entrega. O processamento inclui o lançamento de guias de remessa, recebimentos de produtos e faturamento.  

Impressões de documento de ordens e cotações que têm uma agenda de entrega mostram apenas as linhas de entrega. Não mostram as linhas originais (linhas comerciais). **Observação:** Além disso, apenas as linhas de entrega serão exibidas quando você executar estas ações:

-   Lançar
-   Copiar páginas
-   Procurar páginas de lista e relatórios

Quando você confirmar as cotações de venda, as ordens de venda resultantes mostrarão a agenda de entrega completa, até mesmo as linhas de ordem que têm várias entregas. Além disso, a agenda de entrega inteira é exibida em todas as páginas principais, como ordens de venda, cotações de venda e ordens de compra.


