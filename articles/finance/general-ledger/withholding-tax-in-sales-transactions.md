---
title: Imposto retido na fonte em transações de venda
description: Este tópico lista as etapas para evitar o cálculo da imposto retido na fonte para clientes selecionados. Para clientes que especificam o imposto retido na fonte em seus pagamentos, você pode atribuir o grupo de retenção de imposto na fonte padrão.
author: kailiang
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 72d659004a1f61b63d6a782ba6b45bb99030bae9
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727416"
---
# <a name="withholding-tax-in-sales-transactions"></a>Imposto retido na fonte em transações de venda

Este tópico lista as etapas para evitar o cálculo da imposto retido na fonte para clientes selecionados. Para clientes que especificam o imposto retido na fonte em seus pagamentos, você pode atribuir o **Grupo de retenção de imposto na fonte** padrão na página **Clientes**. 

1. Acesse **Painel de Navegação > Módulos > Contas a receber > Clientes > Todos os clientes**.

2. Clique na respectiva conta de cliente e clique em **Editar**.

3. Na guia **Fatura e entrega**, defina o campo **Calcular imposto retido na fonte** como **Sim**.

   > [!NOTE] 
   > O imposto retido na fonte não será calculado se **Calcular imposto retido na fonte** não estiver ativado para esse cliente nos dados mestres.

4. Selecione um grupo de retenção de imposto na fonte no **Grupo de retenção de imposto na fonte**.

5. Clique em **Salvar**.

Para itens/serviços que são responsáveis por retenção de imposto, você pode atribuir o **Grupo de imposto retido na fonte** em **Produtos liberados**.

1. Acesse **Painel de Navegação > Módulos > Gerenciamento de informações do produto > Produtos > Produtos liberados**.

2. Clique no respectivo número do item e clique em **Editar**.

3. Na guia **Vender**, clique em **Calcular imposto retido na fonte**.

   > [!NOTE] 
   > O imposto retido na fonte não será calculado se **Calcular imposto retido na fonte** estiver definido como **Sim** para esse item na guia **Vender** na página **Produto liberado**.

4. Selecione um grupo de retenção imposto na fonte do item na lista **Grupos de retenção de imposto na fonte do item**.

5. Clique em **Salvar**.

Os grupos de retenção de imposto na fonte e os grupos de retenção de imposto na fonte do item podem ser atribuídos usando a página **Ordem de venda**. 

O grupo de retenção de imposto na fonte padrão e o grupo de retenção de imposto na fonte do item serão usados como entradas padrão nas linhas da ordem de venda quando você criar uma nova ordem de venda.

O imposto retido na fonte é calculado e lançado com o **Diário de pagamentos do cliente**. Você pode ajustar manualmente o código aplicável de retenção de imposto na fonte, bem como o valor real do imposto retido na fonte na guia **Imposto retido na fonte** na página **Liquidar transações**.

O valor do imposto retido na fonte calculado será deduzido do pagamento do cliente e lançado na conta de **Contrapartida do imposto retido na fonte** em um comprovante relacionado.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
