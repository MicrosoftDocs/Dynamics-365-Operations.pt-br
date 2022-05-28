---
title: Imposto retido na fonte em transações de compra
description: Para fornecedores que são responsáveis por retenção de imposto na fonte, você pode atribuir o **Grupo de imposto retido na fonte** padrão na página **Todos os fornecedores**.
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
ms.openlocfilehash: c2220159cef31bf3343bcf39325c7a0ff3e0cf47
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727192"
---
# <a name="withholding-tax-in-purchase-transactions"></a>Imposto retido na fonte em transações de compra

Para fornecedores que são responsáveis por retenção de imposto na fonte, você pode atribuir o **Grupo de imposto retido na fonte** padrão na página **Todos os fornecedores**.

1. Acesse **Painel de navegação > Módulos > Contas a pagar > Fornecedores > Todos os fornecedores**.

2. Clique na respectiva conta de fornecedor e clique em **Editar**.

3. Na guia **Fatura e entrega**, defina o campo **Calcular imposto retido na fonte** como **Sim**.

   > [!NOTE] 
   > O imposto retido na fonte não será calculado se **Calcular imposto retido na fonte** não estiver ativado para esse fornecedor nos dados.

4. Selecione um grupo de retenção de imposto na fonte no **Grupo de retenção de imposto na fonte**.

5. Clique em **Salvar**.

Para itens/serviços que são responsáveis por retenção de imposto, você pode atribuir o **Grupo de imposto retido na fonte** em **Produtos liberados**.

1. Acesse **Painel de Navegação > Módulos > Gerenciamento de informações do produto > Produtos > Produtos liberados**.

2. Clique no respectivo número do item e clique em **Editar**.

3. Na guia **Compra**, clique em **Calcular imposto retido na fonte**.

   > [!NOTE] 
   > O imposto retido na fonte não será calculado se **Calcular imposto retido na fonte** estiver definido como **Sim** para esse item na guia **Compra** na página **Produto liberado**.

4. Selecione um grupo de retenção imposto na fonte do item na lista **Grupos de retenção de imposto na fonte do item**.

5. Clique em **Salvar**.

Os grupos de retenção de imposto na fonte e os grupos de retenção de imposto na fonte do item podem ser atribuídos em páginas: 

- **Ordem de compra**
- **Fatura de fornecedor**
- **Diário de faturas**

O grupo de retenção de imposto na fonte padrão e o grupo de retenção de imposto na fonte do item serão transportados para as linhas ao criar **Ordens de compra** e/ou **Faturas de fornecedor pendentes**. Para o **Diário de faturas de fornecedores**, você pode alternar para **Calcular imposto retido na fonte** e selecionar **Grupo de retenção de imposto na fonte do item** na guia **Geral** do diário.

O valor temporário do imposto retido na fonte está disponível no campo **Imposto retido na fonte ajustado** da guia **Totais** na página **Ordem de compra**.

![O imposto retido na fonte está incluído na ordem de compra.](media/withholding-tax-adjusted.png)

O imposto retido na fonte é calculado no **Diário de pagamentos do fornecedor**. Você pode ajustar manualmente os códigos aplicáveis de retenção de imposto na fonte, bem como os valores reais do imposto retido na fonte na guia **Imposto retido na fonte** na página **Liquidar transações**.

![A retenção pode ser ajustada manualmente na página Liquidar transações.](media/withholding-tax-vendor-payment-tab.png)

O valor do imposto retido na fonte derivado será deduzido do pagamento do fornecedor e lançado na **Conta do imposto retido na fonte** em um comprovante relacionado.

![Conta do imposto retido na fonte mostrando um comprovante relacionado.](media/withholding-tax-adjusted.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
