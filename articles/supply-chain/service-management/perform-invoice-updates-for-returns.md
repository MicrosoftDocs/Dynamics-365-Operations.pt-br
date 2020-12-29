---
title: Executar atualizações de fatura para devoluções
description: Essa funcionalidade também dá suporte aos processos comerciais de organizações que optam por ter ordens de devolução e ordens de venda faturadas ao mesmo tempo e pela mesma pessoa.
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
ms.openlocfilehash: 5d60e29aec1ebdec939aaafc978ee4de04b96136
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4421951"
---
# <a name="perform-invoice-updates-for-returns"></a>Executar atualizações de fatura para devoluções 

[!include [banner](../includes/banner.md)]


Uma ordem de devolução é um tipo de ordem de venda marcada como um Item Devolvido. Portanto, a página de listagem de **Todas as ordens de venda** é usada para gerar faturas para ordens de devolução em vez do formulário de **Ordens de devolução**. Essa funcionalidade também dá suporte aos processos comerciais de organizações que optam por ter ordens de devolução e ordens de venda faturadas ao mesmo tempo e pela mesma pessoa.

Porque a fatura para um item devolvido é para um valor negativo, é chamada uma nota de crédito.

Ao configurar a atualização da nota fiscal para processamento em lotes, a ordem de venda do tipo **Ordem devolvida** deve ter o status de linha de devolução **Recebido**, que indica que a guia de remessa da ordem foi atualizada.

## <a name="post-an-invoice-for-a-return-order"></a>Lançar uma fatura para uma ordem de devolução

1.  Clique em **Contas a receber** \> **Comum** \> **Ordens de venda** \> **Todas as ordens de venda**.

2.  Selecione uma ordem de venda para a qual **Ordem devolvida** é exibido no campo de **Tipo de ordem**.

3.  No Painel de Ação, na guia **Fatura**, no grupo **Gerar**, clique em **Fatura**.

4.  Na guia **Parâmetros**, marque a caixa de seleção **Lançamento**.

5.  Reveja as informações no formulário e faça as alterações necessárias.

6.  Clique em **OK**. Uma nota de crédito é lançada.

## <a name="see-also"></a>Consulte também

[Atualizações de guia de remessa para devoluções](packing-slip-updates-returns.md)

  


