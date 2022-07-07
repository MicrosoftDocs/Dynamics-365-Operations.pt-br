---
title: Executar atualizações de fatura para devoluções
description: Essa funcionalidade também dá suporte aos processos comerciais de organizações que optam por ter ordens de devolução e ordens de venda faturadas ao mesmo tempo e pela mesma pessoa.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 32a108694c11a2ebd922a71d5c82691584bbb397
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/15/2022
ms.locfileid: "9014739"
---
# <a name="perform-invoice-updates-for-returns"></a>Executar atualizações de fatura para devoluções 

[!include [banner](../includes/banner.md)]


Uma ordem de devolução é um tipo de ordem de venda marcada como um Item Devolvido. Portanto, a página de listagem de **Todas as ordens de venda** é usada para gerar faturas para ordens de devolução em vez do formulário de **Ordens de devolução**. Essa funcionalidade também dá suporte aos processos comerciais de organizações que optam por ter ordens de devolução e ordens de venda faturadas ao mesmo tempo e pela mesma pessoa.

Porque a fatura para um item devolvido é para um valor negativo, é chamada uma nota de crédito.

Ao configurar a atualização da nota fiscal para processamento em lotes, a ordem de venda do tipo **Ordem devolvida** deve ter o status de linha de devolução **Recebido**, que indica que a guia de remessa da ordem foi atualizada.

## <a name="post-an-invoice-for-a-return-order"></a>Lançar uma fatura para uma ordem de devolução

1.  Clique em **Contas a receber** \> **Ordens** \> **Todas as ordens de vendas**.

2.  Selecione uma ordem de venda para a qual **Ordem devolvida** é exibido no campo de **Tipo de ordem**.

3.  No Painel de Ação, na guia **Fatura**, no grupo **Gerar**, clique em **Fatura**.

4.  Na guia **Parâmetros**, marque a caixa de seleção **Lançamento**.

5.  Reveja as informações no formulário e faça as alterações necessárias.

6.  Clique em **OK**. Uma nota de crédito é lançada.

## <a name="see-also"></a>Consulte também

[Atualizações de guia de remessa para devoluções](packing-slip-updates-returns.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]