---
title: Executar o processo de liquidação de TDS periódico
description: Este tópico explica como liquidar o Imposto Deduzido na Origem (TDS) periódico.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 5b4c3a83f3fed0907dacd415f5aff9fad3c10bc6
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8408371"
---
# <a name="run-the-periodic-tds-settlement-process"></a>Executar o processo de liquidação de TDS periódico

[!include [banner](../includes/banner.md)]

Este tópico explica como liquidar o Imposto Deduzido na Origem (TDS) periódico.

1. Acesse **Imposto \> Declarações \> Imposto retido na fonte \> Pagamento de imposto retido na fonte**.

    [![Caixa de diálogo Pagamento de imposto retido na fonte.](./media/apac-ind-TDS-47.png)](./media/apac-ind-TDS-47.png)

2. Na caixa de diálogo **Pagamento de imposto retido na fonte**, no campo **Tipo de imposto**, selecione **TDS**.
3. No campo **Número da Conta de Imposto (TAN)**, selecione o Número da Conta de Imposto (TAN) para o qual executar o processo de liquidação.
4. No campo **Grupo de componentes do imposto retido na fonte**, selecione o grupo de componentes TDS para o qual executar o processo de liquidação.
5. No campo **Período de liquidação**, selecione o período de liquidação de TDS para o qual executar o processo de liquidação.

    > [!NOTE]
    > O processo de liquidação de TDS é executado para todos os períodos configurados para o período de liquidação do TDS na guia **Períodos** da página **Período de liquidação de imposto retido na fonte** (**Imposto \> Impostos indiretos \> Imposto retido na fonte \> Períodos de liquidação de imposto retido na fonte**).

6. No campo **Data inicial**, selecione a data de início a partir da qual executar o processo de liquidação de TDS.

    Para um período específico dentro do período de liquidação, a data de início definida para o período é considerada a data "inicial". Por exemplo, o período de liquidação de TDS tem dois períodos: 1º de abril a 30 de abril de 2009 e 1º de maio a 31 de maio de 2009. Se você selecionar **06/04/2009** (6 de abril de 2009) como a data de início no campo **Data inicial**, o processo de liquidação ainda será executado a partir de 1º de abril de 2009.

    Se você inserir um período posterior no campo **Data inicial**, mas sem liquidar um período anterior dentro do período de liquidação, a liquidação não ocorrerá para os períodos anteriores. Por exemplo, o período de liquidação do TDS tem três períodos: 1º de abril a 30 de abril de 2009, 1º de maio a 31 de maio de 2009 e 1º de junho a 30 de junho de 2009. Se você selecionar **01/05/2009** (1º de maio de 2009) como a data de início no campo **Data inicial**, o processo de liquidação será executado apenas de 1º de maio a 31 de maio de 2009. A liquidação não ocorrerá de 1º de abril a 30 de abril de 2009.

7. No campo **Data da transação**, selecione a data para lançar a transação de liquidação de TDS.
8. No campo **Versão de pagamento de imposto retido na fonte**, selecione a versão de liquidação de TDS:

     - **Original** – Use esta opção para executar o processo de liquidação de TDS pela primeira vez. A versão de pagamento original é usada apenas uma vez para executar o processo de liquidação do TDS para uma combinação de um TAN, um grupo de componentes de imposto retido na fonte e um período de liquidação de imposto retido na fonte.
    - **Versões mais recentes** – Use esta opção se o processo de liquidação de TDS já tiver sido executado para o período especificado. Inclui transações com datas anteriores que foram lançadas depois que o processo de liquidação foi executado anteriormente para o período. Você pode usar esta opção para executar o processo de liquidação qualquer número de vezes.

9. Marque a caixa de seleção **Atualizar** para executar o processo de liquidação de TDS e lançar os valores nas contas contábeis. Se essa caixa de controle estiver desmarcada, o processo de liquidação não será executado e os lançamentos financeiros não serão gerados.
10. Selecione **OK** para executar o processo de liquidação de TDS e gerar o relatório de pagamento do imposto retido na fonte. O status das transações TDS que estão incluídas no processo de liquidação é mostrado como **Liquidado** na página **Liquidação** (acesse **Contas a pagar \> Pagamentos \> Diário de pagamentos do fornecedor**, selecione **Linhas**, selecione **Funções** e depois selecione **Liquidação**).

### <a name="important-points"></a>Pontos importantes

- Se um grupo de componentes de imposto retido na fonte não for selecionado durante o processo de liquidação, a liquidação ocorre para todos os grupos de componentes de imposto retido na fonte para o TAN selecionado e o período de liquidação. Uma linha separada é criada para cada grupo de componentes de imposto retido na fonte na página **Edição de transação aberta**.
- O processo de liquidação é baseado na natureza da categoria do avaliado para um período de liquidação. As transações em que a natureza da categoria do avaliado é **Empresa** são liquidadas e são mostradas como uma linha na página **Edição de transação aberta**. As transações em que a natureza do avaliado é algo diferente de **Empresa** são liquidadas e são mostradas como uma linha na página **Edição de transação aberta**.
- A data de conclusão para as linhas de transação de TDS liquidadas na página **Edição de transação aberta** é baseada nas condições de pagamento que são definidas para o fornecedor de autoridade TDS na página **Fornecedores**. Se as condições de pagamento não forem definidas para o fornecedor da autoridade TDS, o último dia do período de liquidação é mostrado como a data de conclusão.
