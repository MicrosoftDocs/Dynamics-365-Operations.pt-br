---
title: Cálculo de TDS para pagamentos e notas promissórias
description: Este artigo fornece informações de referência sobre as diferentes transações de pagamento nas quais o imposto deduzido na fonte (TDS) é calculado.
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
ms.openlocfilehash: f5e9447924a17b96b7a4a5cdd1ef1547145d6ea1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906308"
---
# <a name="tds-calculation-on-payments-and-promissory-notes"></a>Cálculo de TDS para pagamentos e notas promissórias

[!include [banner](../includes/banner.md)]

Este artigo fornece informações de referência sobre as diferentes transações de pagamento nas quais o imposto deduzido na fonte (TDS) é calculado.

| Nº de série | Tipo de transação | Valor da transação | Nome da página e caminho | Tipo de conta e tipo de contrapartida |
|---------------|------------------|--------------------|--------------------|--------------------------------------|
| 1             | Adiantar pagamento/pagamento em fatura (TDS a pagar) | Débito ou crédito | <ul><li>Diário geral (**Contabilidade \> Entradas de diário \> Diários gerais**)</li><li>Diário de faturas (**Contas a pagar \> Faturas \> Diário de faturas**)</li><li>Diário de pagamentos (**Contas a pagar \> Pagamentos \> Diário de pagamentos do fornecedor**)</li></ul> | Fornecedor (Dr.), Banco (Cr.) |
| 2             | Adiantar o pagamento/pagamento em fatura (Compra feita pelo cliente – TDS a pagar) | Débito ou crédito | <ul><li>Diário geral (**Contabilidade \> Entradas de diário \> Diários gerais**)</li><li>Diário de faturas (**Contas a pagar \> Faturas \> Diário de faturas**)</li><li>Diário de pagamentos (**Contas a pagar \> Pagamentos \> Diário de pagamentos do fornecedor**)</li></ul> | Cliente (Dr.), Banco (Cr.) |
| 3             | Notas Promissórias | Débito | Emitir diário de notas promissórias (**Contas a pagar \> Pagamentos \> Notas promissórias \> Emitir diário de notas promissórias**) | Fornecedor (Dr.) Razão (Cr.) |
| 4             | Renda diversa (TDS a receber) | Débito ou crédito | Diário geral (**Contabilidade \> Entradas de diário \> Diários gerais**) | Banco (Dr.) Razão (Cr.) |
| 5             | Outras despesas (TDS a pagar) | Débito ou crédito | Diário geral (**Contabilidade \> Entradas de diário \> Diários gerais**) | Banco (Dr.) Razão (Cr.) |

Siga estas etapas para calcular o TDS em pagamentos e notas promissórias.

1. Nas páginas do diário, crie linhas de diário. Selecione o tipo de conta e o tipo de contrapartida.
2. Selecione **Funções \> Liquidação** para abrir a página **Edição de transação aberta**. Em seguida, selecione uma fatura específica que deve ser liquidada. Se o TDS já tiver sido calculado no nível da fatura, o campo **Origem do valor** mostrará o valor base no qual o TDS foi calculado. O campo **Valor do imposto** mostra o valor de TDS que foi calculado para a transação. O campo **Valor** mostra o valor do pagamento líquido (isto é, o valor do pagamento após o TDS ser deduzido).

    > [!NOTE]
    > Para um pagamento feito em uma fatura, as seguintes condições se aplicam:
    >
    > - Se o valor do pagamento e o valor da fatura forem iguais, o TDS não será calculado se já tiver sido calculado no nível da fatura.
    > - Se o valor da fatura depois do valor de TDS deduzido for maior do que o valor do pagamento, o TDS não será calculado.
    > - Se o valor da fatura depois do valor de TDS deduzido for menor do que o valor do pagamento, o TDS será calculado sobre o valor que excede o valor da fatura.

3. Na página **Comprovante de diário**, na guia **Visão geral**, no campo **Grupos de TDS**, revise ou altere o grupo de TDS padrão definido para o fornecedor ou cliente. O TDS que é calculado nas linhas do diário é baseado na fórmula que é definida para os códigos de imposto TDS no Grupo de TDS.

    > [!NOTE]
    > O TDS é calculado apenas se a opção **Calcular imposto retido na fonte** for definida como **Sim** para o fornecedor na página **Fornecedores**.

4. Na guia **Informações sobre impostos**, na seção **Informações sobre a empresa**, no campo **Nome**, você pode selecionar o nome da empresa para endereços alternativos que são configurados para a empresa.

    Na seção **Imposto retido na fonte**, o campo **Natureza do avaliado** mostra a natureza da categoria do avaliado do fornecedor ou do cliente. O campo **Número da conta de imposto (TAN)** mostra o número da conta de imposto (TAN) da empresa selecionada.

5. Selecione o **botão Imposto retido na fonte \> Imposto retido na fonte** para abrir a página **Transações de imposto retido na fonte temporárias**. A parte superior desta página tem os seguintes campos:

    - **Valor do imposto retido na fonte no total** - O TDS total que foi calculado para a transação do grupo de TDS.
    - **Valor** - A porcentagem total que foi usada para calcular o TDS para a transação. A porcentagem total é baseada na fórmula definida para os códigos de imposto de TDS e anexados ao grupo de TDS.
    - **Valor do imposto retido na fonte ajustado no total** - O valor total de TDS ajustado para todos os códigos de imposto no grupo de TDS.
    - **TDS** – uma caixa de seleção marcada indica que um grupo de TDS está associado à transação.

    Os campos nas guias **Visão geral**, **Geral** e **Ajuste** mostram o valor do TDS calculado e os detalhes do valor do TDS ajustado para cada código de imposto TDS anexado ao grupo de TDS.

6. Selecione **Limite** para abrir a página **Limite**, na qual é possível revisar o limite definido para o componente de imposto TDS anexado a um código de imposto TDS específico.
7. Selecione **Designer de fórmulas** para abrir a página **Designer de fórmulas**, na qual você pode revisar a fórmula definida para um código de imposto TDS específico.
8. Feche as páginas **Designer de fórmula** e **Transações de imposto retido na fonte temporárias** para retornar à página **Comprovante de diário**.
9. Valide e lance o diário. O valor do TDS que foi calculado é lançado na conta a pagar definida para cada código de imposto de TDS no grupo de TDS. As contas a receber para códigos de imposto TDS são definidas na página **Códigos de impostos retidos na fonte**.
10. Selecione **Imposto retido na fonte lançado** para abrir a página **Transações de retenção de imposto**. O campo **Valor** mostra a porcentagem total que foi usada para calcular o TDS para a transação.

    Os campos nas guias **Visão geral**, **Geral** e **Valor** mostram os valores de TDS que foram calculados para o grupo de TDS associado à transação.

11. Revise as informações de cálculo do TDS para cada código de imposto de TDS que foi anexado ao grupo do TDS.

## <a name="generate-payments"></a>Gerar pagamentos

Siga estas etapas para gerar os pagamentos.

1. Siga uma destas etapas:

    - Acesse **Contas a pagar \> Pagamentos \> Diário de pagamentos do fornecedor**.
    - Acesse **Contas a receber \> Pagamentos \> Diário de pagamento do cliente**.
    - Acesse **Contas a pagar \> Pagamentos \> Notas promissórias \> Emitir diário de notas promissórias**.
    - Acesse **Contas a receber \> Pagamentos \> Letra de câmbio \> Emitir diário de letras de câmbio**.
    - Acesse **Contas a receber \> Pagamentos \> Letra de câmbio \> Reemitir diário de letras de câmbio**.

2. Selecione **Linhas**.
3. Selecione **Funções \> Gerar pagamentos**.
