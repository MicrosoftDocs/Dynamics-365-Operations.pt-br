---
title: Criar e faturar uma ordem de compra intercompanhia para uso interno
description: Este tópico explica como criar e faturar uma ordem de compra intercompanhia para uso interno
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchLineOpenOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 88a14ff962c5cf0cd1cff24b16cc7a62e9e1c8ce
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548101"
---
# <a name="create-and-invoice-an-intercompany-purchase-order-for-internal-use"></a>Criar e faturar uma ordem de compra intercompanhia para uso interno

[!include [banner](../../includes/banner.md)]

Você pode criar uma ordem de compra intercompanhia para um fornecedor intercompanhia. Isso cria automaticamente uma ordem de venda intercompanhia no fornecedor intercompanhia.

![Processo de compra interna intercompanhia](media/intercompanypurchaseprocess.png)

## <a name="create-an-intercompany-purchase-order-and-a-corresponding-intercompany-sales-order"></a>Criar uma ordem de compra intercompanhia e uma ordem de venda intercompanhia correspondente

Execute estas etapas na entidade legal AAA, conforme mostrado na ilustração.

1. Selecione **Contas a pagar** \> **Ordens de compra** \> **Todas as ordens de compra**.
1. Na página de listagem **Todas as ordens de compra**, crie uma ordem de compra para um fornecedor intercompanhia. Os valores dos campos são copiados da conta do fornecedor para a ordem de compra.

    Como você esta trabalhando com um fornecedor intercompanhia, uma ordem de venda intercompanhia é criada na entidade legal que corresponde ao fornecedor. O número da ordem de venda intercompanhia pode ser o mesmo da ordem de compra intercompanhia e pode incluir a ID da entidade legal. A estrutura do número que é usada depende da seleção feita no campo **Numeração da ordem de venda** na página **Intercompanhia**. Por exemplo, se você criar a ordem de compra 00029\_064 na entidade legal AAA, o número da ordem de venda na entidade legal BBB é AAA00029\_64.

    Uma mensagem informativa avisa que uma ordem de compra intercompanhia e uma ordem de venda intercompanhia foram criadas e contêm links para estas ordens. A mensagem inclui o número da ordem de venda intercompanhia, para sua informação.

1. Adicione itens de linha à ordem de compra. Os itens de linha correspondentes são adicionados automaticamente à ordem de venda intercompanhia. Se um item não existir na outra entidade legal, será exibida uma mensagem e você não poderá adicionar o item à ordem de compra. Para solucionar este problema, alterne para a outra entidade legal e libere o produto para essa entidade legal. O item estará disponível para ser adicionado às ordens de venda nessa entidade legal. Em seguida, alterne novamente para a entidade legal da ordem de compra e continue a adicionar os itens de linha.
1. Quando tiver terminado de inserir as informações para a ordem de compra, confirme-as.

## <a name="process-the-intercompany-packing-slip-and-customer-invoice"></a>Processar a guia de remessa e a fatura de cliente intercompanhia

Execute estas etapas na entidade legal BBB, conforme mostrado na ilustração.

1. Acesse **Contas a receber \> Ordens de venda \> Todas as ordens de venda**.
1. Na página de listagem **Todas as ordens de venda**, selecione a ordem de venda intercompanhia.
1. No Painel de Ações, selecione a guia **Separar e empacotar** e, em seguida, selecione **Guia de remessa**.
1. Marque a caixa de seleção **Lançamento**.
1. Selecione **OK**. A guia de remessa é lançada na entidade legal BBB.
1. Na página de listagem **Todas as ordens de venda**, selecione a ordem de venda intercompanhia.
1. No Painel de Ações, selecione a guia **Fatura** e depois selecione **Fatura**.
1. Marque a caixa de seleção **Lançamento**.
1. Selecione **OK**.

    A fatura do cliente para a ordem de venda intercompanhia é lançada na entidade legal BBB.

## <a name="process-the-intercompany-product-receipt-and-vendor-invoice"></a>Processar o recebimento de produtos e a fatura do fornecedor intercompanhia

Execute estas etapas na entidade legal AAA, conforme mostrado na ilustração.

1. Acesse **Contas a pagar \> Ordens de compra \> Todas as ordens de compra**.
1. Na página de listagem **Todas as ordens de compra**, selecione a ordem de compra intercompanhia.
1. No Painel de Ações, selecione **Receber** e, em seguida, selecione **Recebimento de produtos**. O recebimento de produtos é criado. O número de recebimento de produtos é o mesmo que o número da guia de remessa intercompanhia.
1. Marque a caixa de seleção **Lançamento**.
1. Selecione **OK**.
1. Na página de listagem **Todas as ordens de compra**, selecione a ordem de compra intercompanhia.
1. No Painel de Ações, selecione **Fatura** e depois selecione **Fatura**. A fatura do fornecedor é criada. O número da fatura do fornecedor é igual ao da fatura de cliente intercompanhia.
1. Conclua a inserção da fatura do fornecedor e lance-a.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
