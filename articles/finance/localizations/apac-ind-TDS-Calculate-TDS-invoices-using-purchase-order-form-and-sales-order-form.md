---
title: Calcular faturas de TDS usando formulário de ordem de compra e formulário de ordem de venda
description: Este tópico lista as etapas para calcular o Imposto Deduzido na Origem (TDS) em vários tipos de faturas.
author: kailiang
ms.date: 02/12/2021
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
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 6a7e670c38a1bce6b8f6771b4be49e56e3aa785a
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8711938"
---
# <a name="calculate-tds-invoices-using-purchase-order-form-and-sales-order-form"></a>Calcular faturas de TDS usando formulário de ordem de compra e formulário de ordem de venda

[!include [banner](../includes/banner.md)]

Este tópico lista as etapas para calcular o Imposto Deduzido na Origem (TDS) em vários tipos de faturas usando as páginas **Ordem de compra**, **Diário de compras**, **Ordem ampla** e **Ordem de venda**.

1. Crie uma ordem de compra, diário de compras, ordem de compra ampla ou ordem de venda usando a página listada. Insira os detalhes necessários.

2. Selecione a guia **Configuração** para ver a natureza do avaliado do fornecedor ou cliente. Essas informações estão listadas no campo **Natureza do avaliado**, no grupo do campo **Grupo de impostos retidos na fonte**.

3. No campo **Grupo de TDS**, exibe ou modifique o grupo de TDS padrão definido para o fornecedor ou cliente.

   > [!NOTE]
   > O campo **Grupo de TCS** não está disponível quando você seleciona um grupo de TDS no campo **Grupo de TDS**. O TDS é calculado apenas se a caixa de seleção **Calcular imposto retido na fonte** estiver marcada para o fornecedor ou cliente na página **Todos os fornecedores** ou **Todos os clientes**.  

4. Crie linhas de itens na guia **Linhas** e insira os detalhes necessários.

5. Selecione a guia **Configuração** (nível de linha) para exibir ou alterar o grupo de TDS definido no nível de cabeçalho. O grupo de TDS é exibido no campo **Grupo de TDS**, que está no grupo do campo **Grupo de impostos retidos na fonte**.

6. Selecione a guia **Informações sobre impostos** e selecione endereços alternativos que são configurados para o nome da empresa que é exibido neste campo. O nome da empresa é exibido no campo **Nome**, que está no grupo do campo **Informações sobre a empresa**. 

   O TAN do nome da empresa selecionada é exibido no campo **Número da Conta de Imposto** (**TAN**), no grupo do campo **Imposto retido na fonte**. 

7. Selecione **Imposto retido na fonte** para abrir a página **Transações de retenção temporária de impostos**. Exiba os seguintes campos no painel superior da página **Transações de retenção temporária de impostos**.

   - **Valor** **do imposto retido** **na fonte** **no** **total** - O TDS total calculado para a transação do grupo de TDS.

   - **Valor** - A porcentagem total usada para calcular o TDS para a transação. A porcentagem total é baseada na fórmula definida para os códigos de imposto TDS anexados ao grupo de TDS.

   - **Valor do imposto retido na fonte ajustado no total** - O valor total de TDS ajustado para todos os códigos de imposto no grupo de TDS.

   - **TDS** - Se selecionado, um grupo de TDS é anexado à transação.

Os campos nas guias **Visão geral**, **Geral** e **Ajuste** na página **Transações de retenção temporária de impostos** exibem o valor do TDS calculado e os detalhes do valor do TDS ajustado para cada código de imposto TDS anexado ao grupo de TDS.

8. Selecione **Limite** para abrir a página **Limite**. Exiba o limite definido para o componente de imposto TDS anexado a um código de imposto TDS específico nesta página.

9. Selecione **Designer de fórmulas** para abrir a página **Designer de fórmulas**. Exiba a fórmula definida para um código de imposto TDS específico nesta página. 

10. Lance a fatura. O valor do TDS calculado nas notas fiscais de compra é lançado na conta a pagar e o valor do TDS calculado nas notas fiscais de vendas é lançado na conta a receber que é definida para cada código de imposto TDS no grupo de TDS. As contas a pagar ou contas a receber para códigos de imposto TDS são definidas na página **Códigos de impostos retidos na fonte**.

11. Selecione o botão **Consulta** e o botão **> Fatura > Imposto retido na fonte lançado** para abrir a página **Transações de retenção de imposto**. Você pode ver a porcentagem total usada para calcular o TDS para a transação no campo **Valor**.

Os campos nas guias **Visão geral**, **Geral** e **Valor** na página **Transações de retenção de imposto** exibem as informações do TDS calculado para a transação. Exiba as informações de cálculo do TDS para cada código de imposto TDS anexado ao grupo do TDS.
