---
title: Cálculo de TDS em faturas da página Fatura de texto livre
description: Este artigo explica como calcular o Imposto Deduzido na Origem (TDS) em faturas usando a página Fatura de texto livre.
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
ms.openlocfilehash: b1cf0f5366315884e75a6fee25b88a3aac7d62de
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856601"
---
# <a name="tds-calculation-on-invoices-from-the-free-text-invoice-page"></a>Cálculo de TDS em faturas da página Fatura de texto livre

[!include [banner](../includes/banner.md)]

Este artigo explica como calcular o Imposto Deduzido na Origem (TDS) em faturas usando a **página Fatura de texto livre**.

1. Acesse **Contas recebíveis \> Faturas \> Todas faturas de texto livre**.

    [![Página de fatura de texto livre.](./media/apac-ind-TDS-57-1.png)](./media/apac-ind-TDS-57-1.png)

2. Selecione **Novo** para criar uma fatura de texto livre e insira os detalhes necessários.
3. Selecione a guia **Fatura**. Na seção **Grupo de impostos retidos na fonte**, o campo **Natureza do avaliado** mostra a natureza da categoria do avaliado do cliente.
4. No campo **Grupo de TDS**, revise ou altere o grupo de TDS padrão definido para o cliente.

    > [!NOTE]
    > Quando você seleciona um valor no campo **Grupo de TDS**, o campo **Grupo de TCS** fica indisponível. O TDS é calculado apenas se a opção **Calcular imposto retido na fonte** for definida como **Sim** para o cliente na página **Todos os clientes**.

5. Na guia **Informações sobre impostos**, na **Informações sobre a empresa**, no campo **Nome**, selecione o nome da empresa para um endereço alternativo configurado para a empresa.

    Na seção **Imposto retido na fonte**, o campo **Número da Conta de Imposto (TAN)** mostra o número da conta de imposto (TAN) para a empresa selecionada.

6. Na guia **Linhas da fatura**, crie linhas da fatura e insira os detalhes necessários.

    Na seção **Grupo de impostos retidos na fonte**, o campo **Número da Conta de Imposto (TAN)** mostra o TAN e o campo **Grupo de TDS** mostra o grupo de TDS.

7. Selecione **Imposto retido na fonte** para abrir a página **Transações de retenção temporária de impostos**. A parte superior desta página tem os seguintes campos:

    - **Valor do imposto retido na fonte no total** - O TDS total que foi calculado para a transação do grupo de TDS.
    - **Valor** - A porcentagem total que foi usada para calcular o TDS para a transação. A porcentagem total é baseada na fórmula definida para os códigos de imposto de TDS e anexados ao grupo de TDS.
    - **Valor do imposto retido na fonte ajustado no total** - O valor total de TDS ajustado para todos os códigos de imposto no grupo de TDS.
    - **TDS** – uma caixa de seleção marcada indica que um grupo de TDS está associado à transação.

    Os campos nas guias **Visão geral**, **Geral** e **Ajuste** mostram o valor do TDS calculado e os detalhes do valor do TDS ajustado para cada código de imposto TDS anexado ao grupo de TDS.

8. Selecione **Limite** para abrir a página **Limite**, na qual é possível revisar o limite definido para o componente de imposto TDS anexado a um código de imposto TDS específico.
9. Selecione **Designer de fórmulas** para abrir a página **Designer de fórmulas**, na qual você pode revisar a fórmula definida para um código de imposto TDS específico.
10. Lançar a fatura de texto livre. O valor de TDS que é calculado para a fatura de texto livre é lançado na conta a receber definida para cada código de imposto de TDS no grupo de TDS. As contas a receber para códigos de imposto TDS são definidas na página **Códigos de impostos retidos na fonte**.
11. Selecione **Imposto retido na fonte lançado** para abrir a página **Transações de retenção de imposto**. O campo **Valor** mostra a porcentagem total que foi usada para calcular o TDS para a transação.

    Os campos nas guias **Visão geral**, **Geral** e **Valor** mostram os valores de TDS que foram calculados nas linhas da fatura.

12. Revise as informações de cálculo do TDS para cada código de imposto de TDS que foi anexado ao grupo do TDS.
