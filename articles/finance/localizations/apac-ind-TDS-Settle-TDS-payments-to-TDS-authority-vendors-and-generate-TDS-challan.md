---
title: Liquidar pagamentos TDS para fornecedores da autoridade TDS e gerar challan TDS
description: Este tópico explica como liquidar pagamentos de imposto deduzido na origem (TDS) para fornecedores de autoridade TDS.
author: kailiang
ms.date: 03/12/2021
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
ms.openlocfilehash: e9dcf2e9d5fc1a1f9eae9d93050b0831bd42f78c
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725529"
---
# <a name="settle-tds-payments-to-tds-authority-vendors-and-generate-tds-challan"></a>Liquidar pagamentos TDS para fornecedores da autoridade TDS e gerar challan TDS

[!include [banner](../includes/banner.md)]

Este tópico explica como liquidar pagamentos de imposto deduzido na origem (TDS) para fornecedores de autoridade TDS.

1. Acesse **Contas a pagar \> Pagamentos \> Diário de pagamentos do fornecedor**.

    [![Página do diário de pagamentos do fornecedor.](./media/apac-ind-TDS-51.png)](./media/apac-ind-TDS-51.png)

2. Na página **Diário de pagamentos do fornecedor**, selecione **Novo** para criar uma linha de diário.
3. No campo **Conta**, selecione o fornecedor de autoridade TDS para o qual liquidar os pagamentos TDS.
4. Selecione **Transações de liquidação** para abrir a página **Transações de liquidação**, onde você pode exibir as transações TDS liquidadas do fornecedor de autoridade TDS.

    As transações TDS liquidadas para um período de liquidação são mostradas da seguinte forma:

    - As transações TDS em que a natureza da categoria do avaliado é **Empresa** são mostradas como uma linha de transação.
    - Transações TDS em que a natureza da categoria do avaliado é **HUF**, **Firma**, **Individual**, **AOP**, **BOI**, **Autoridade local** ou **Outros** são mostrados como uma linha de transação.
    - O campo **Valor** mostra o valor total de TDS que deve ser pago ao fornecedor de autoridade TDS.

5. Selecione **Transações de retenção de imposto** para exibir as diferentes transações TDS incluídas no registro de liquidação. Você pode exibir a divisão de cada transação TDS que foi incluída no processo de liquidação para o período de liquidação nesta página.
6. Na guia **Visão geral**, marque a caixa de seleção **Marcar** para que as transações TDS sejam liquidadas com o fornecedor de autoridade TDS.

    A guia **Visão geral** mostra as seguintes informações para cada transação TDS aberta:

    - **Data** – A data da transação TDS.
    - **Comprovante** – O número do comprovante.
    - **Origem** – O módulo em que a transação TDS é publicada.
    - **Fornecedor/Cliente** – O número da conta do fornecedor ou cliente do qual o TDS é deduzido.
    - **Nome do deduzido/participante** – O nome do fornecedor ou cliente do qual o TDS é deduzido.
    - **Natureza do avaliado** – A natureza da categoria de avaliado à qual o deduzido pertence.
    - **Valor** – O valor da fatura sobre o qual o TDS foi calculado.
    - **Valor do imposto** – O valor de TDS que foi calculado para a transação.

    > [!NOTE]
    > Desmarque a caixa de seleção **Marcar** para qualquer transação TDS que não devam ser liquidadas para o fornecedor da autoridade TDS.

    Na guia **Geral**, o campo **PAN** mostra o número da conta permanente (PAN) do deduzido. O campo **Data** mostra a data do cálculo de TDS e o campo **Valor** mostra a porcentagem total que foi usada para o cálculo de TDS.

7. Selecione **Comprovante** para exibir as entradas de comprovante para a transação de TDS.
8. Feche a página.
10. Selecione **Componentes de imposto retido na fonte** para abrir a página **Componentes de imposto retido na fonte**, onde você pode exibir o TDS que foi calculado por componente do imposto TDS para um código de imposto TDS específico.

    Na guia **Visão geral**, o campo **Componente de imposto** mostra o componente de imposto TDS que foi usado para a transação. O campo **Valor** mostra o valor TDS que foi calculado para o componente de imposto TDS, na moeda base. O campo **Valor acumulado** mostra o valor total de TDS que foi calculado para o componente de imposto de TDS para todas as transações liquidadas.

    Na guia **Valor**, a seção **Moeda padrão** mostra o valor TDS que foi calculado para o componente de imposto TDS, na moeda padrão. A seção **Moeda secundária** mostra o valor na moeda secundária.

11. Feche a página **Componentes de imposto retido na fonte**.
12. Na página **Edição de Transação Aberta**, no campo **Valor**, observe que o valor total a ser liquidado para o fornecedor de autoridade TDS para o período de liquidação é atualizado.
13. Para liquidar as transações TDS de diferentes períodos de liquidação TDS para o fornecedor de autoridade TDS, marque a caixa de seleção **Marcar** para as transações.
14. Feche a página **Edição de Transação Aberta**.

    > [!NOTE]
    > Se apenas algumas transações forem selecionadas para liquidação na página **Transações de retenção de imposto**, o valor total de TDS das transações selecionadas é atualizado no campo **Correção** na página **Edição de Transação Aberta**. O valor da correção é atualizado na linha do diário na página **Comprovante de diário** e a página **Edição de transação aberta** é fechada.

    Na página **Comprovante de diário**, o campo **Débito** mostra o valor total a ser pago ao fornecedor de autoridade TDS.

15. Insira os detalhes da contrapartida.

    > [!NOTE]
    > Se as transações TDS tiverem Números da Conta de Imposto (TANs) diferentes, as linhas do diário serão criadas por TAN na página **Comprovante de diário**.

16. Na guia **Taxa de pagamento**, no campo **ID da taxa**, selecione uma ID de taxa que tenha um tipo de taxa **Juros** ou **Outros** para cobrar a taxa de pagamento para pagamentos atrasados que são feitos ao fornecedor de autoridade TDS.

    Na guia **Informações sobre impostos**, na seção **Informações sobre a empresa**, o campo **Nome** mostra o nome da empresa. Na seção **Imposto retido na fonte**, o campo **Número da Conta de Imposto (TAN)** mostra o TAN que está anexado à linha de transação.

17. Valide e lance o diário.
18. Selecione **Imposto retido na fonte \> Informações challan** para inserir os detalhes do desafio para a transação.

    O campo **Comprovante** mostra o número do comprovante da transação.
    
19. Marque a caixa de seleção **TDS depositado por entrada de registro** se o valor de TDS for depositado por meio de uma entrada de registro.
20. No campo **Número de challan**, insira o número de challan que é usado para fazer o pagamento ao fornecedor de autoridade TDS.
21. No campo **Data**, insira a data do challan.
22. No campo **Nome do banco**, selecione o nome do banco para o qual o valor de TDS a ser pago ao fornecedor de autoridade TDS deve ser depositado. Este campo lista todas as contas bancárias que foram configuradas para o fornecedor de autoridade TDS em **Contas a pagar \> Todos os fornecedores \> Configurar \> Contas bancárias**.
23. No campo **Código BSR**, insira o código BSR (Basic Statistical Return) do banco.
24. Feche a página.

### <a name="example"></a>Exemplo

O período de 01/04/2009 é liquidado para o grupo de componentes de TDS **Aluguel** usando o processo de liquidação TDS periódico. O valor total de TDS de 141.625,00 é lançado na conta de autoridade do fornecedor de TDS para o período de liquidação de TDS. Você pode exibir esse valor no campo **Valor** na página **Edição de Transação Aberta** para o fornecedor de autoridade TDS.

Se você selecionar **Transações de retenção de imposto** para exibir as diferentes transações TDS que foram liquidadas no período, as informações a seguir serão mostradas.

| Valor do TDS |
|------------|
| 16,995.00  |
| 22,660.00  |
| 28,325.00  |
| 16,995.00  |
| 28,325.00  |
| 16,995.00  |
| 11,330.00  |

Para um valor de TDS específico, você pode selecionar **Componentes de imposto retido na fonte** para exibir o TDS que foi calculado por componente de imposto de TDS para um código de imposto de TDS específico. Para este exemplo, você seleciona **Componentes de imposto retido na fonte** para o valor de TDS 16.995,00. O valor do imposto que foi calculado por componente para a transação é mostrado.

| Componente de imposto | Valor    | Valor acumulado |
|---------------|-----------|--------------------|
| TDS           | 1,5000.00 | 125,000.00         |
| Sobretaxa     | 1,500.00  | 12,500.00          |
| PE-Cess       | 330.00    | 2,750.00           |
| SHE Cess      | 165.00    | 1,375.00           |

Se você selecionou apenas os valores de TDS 16.995,00, 22.660,00 e 2.8325,00 para liquidação na página **Transações de retenção de imposto**, o valor total para liquidação é mostrado como **67.980,00** no campo **Correção** na página **Edição de Transação Aberta**. Se esta transação for marcada para liquidação e a página **Edição de Transação Aberta** for fechada, o valor **67.980,00** é mostrado no campo **Débito** na página **Comprovante de diário**.

Agora você pode postar o diário e gerar o challan TDS.

### <a name="adjustment-of-advance-payments-that-are-made-to-tds-authority-vendors"></a>Ajuste de pagamentos antecipados que são feitos a fornecedores de autoridade TDS

Para ajustar um pagamento adiantado que foi feito ao fornecedor da autoridade TDS para um pagamento real, acesse **Contas a pagar \> Fornecedores \> Todos os fornecedores \> Edição de transações**. Se o pagamento real feito exceder o pagamento antecipado, dois números de desafio são gerados para a transação. Contudo, apenas o primeiro número de challan é mostrado na consulta TDS.
