---
title: Criar uma ordem de venda intercompanhia para uso interno
description: Este tópico explica como Criar uma ordem de venda intercompanhia para uso interno
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 0718a1560ec42df2a0a12e8b81484aa3be46d2d8
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548098"
---
# <a name="create-an-intercompany-sales-order-for-internal-use"></a>Criar uma ordem de venda intercompanhia para uso interno

[!include [banner](../../includes/banner.md)]

Geralmente, uma ordem de venda intercompanhia é criada automaticamente com base em uma ordem de compra intercompanhia. Você também pode criar manualmente uma ordem de venda intercompanhia, que gera uma ordem de compra intercompanhia na entidade legal intercompanhia do cliente.

![Processo de vendas internas intercompanhia](media/intercompanyinternalsalesprocess.png)

## <a name="create-an-intercompany-sales-order-manually"></a>Criar uma ordem de venda intercompanhia manualmente

Execute estas etapas na entidade legal B conforme mostrado na ilustração.

1. Acesse **Contas a receber \> Ordens de venda \> Todas as ordens de venda**.
1. No Painel de Ações, selecione **Ordem de vendas** para criar uma ordem de venda.
1. Na página **Criar ordem de venda**, selecione uma conta de cliente. Na Guia Rápida **Geral**, verifique se a caixa de seleção **Intercompanhia** está marcada. Isso indica que o cliente selecionado é um cliente intercompanhia.
1. Insira ou modifique as informações, selecione **OK** e preencha as linhas da ordem normalmente.

    O valor do campo **Endereço de entrega** é copiado do cabeçalho da ordem de venda intercompanhia no cabeçalho da ordem de compra intercompanhia. O valor do campo **Número do item**, incluindo as dimensões do produto, e os valores dos campos **Data de entrega** e **Código de moeda** são copiados das linhas da ordem de venda intercompanhia nas linhas da ordem de compra intercompanhia.

1. No cabeçalho da ordem, selecione **Intercompanhia** para exibir a respectiva ordem de compra intercompanhia.
1. Nas linhas da ordem, selecione **Intercompanhia** para exibir informações sobre o estoque disponível para o comércio intercompanhia.

> [!TIP]
> Você pode exibir as ordens de venda intercompanhia na página **Ordens intercompanhia**.

> [!NOTE]
> Ao trabalhar com intercompanhia, recomendamos que você desmarque a caixa de seleção **Excluir ordem após faturamento** na página **Parâmetros de contas a receber**. Caso contrário, a ordem de compra relacionada será excluída. Nós também recomendamos que você desmarque a caixa de seleção **Excluir ordem de compra após faturamento** na página **Parâmetros de contas a pagar**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
