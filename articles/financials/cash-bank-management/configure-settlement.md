---
title: "Configurar liquidação"
description: "Como e quando as transações são liquidadas podem ser assuntos complexos, é essencial que você insira corretamente e defina os parâmetros para atender às suas necessidades comerciais. Este artigo descreve os parâmetros usados para pagamento de contas a pagar e contas a receber."
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustOpenTrans, CustParameters, VendOpenTrans, VendParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14601
ms.assetid: 6b61e08c-aa8b-40c0-b904-9bca4e8096e7
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 89a13ad5a1d3cb7f93a469d33530ec99b39160da
ms.contentlocale: pt-br
ms.lasthandoff: 03/26/2018

---

# <a name="configure-settlement"></a>Configurar liquidação

[!include[banner](../includes/banner.md)]


Como e quando as transações são liquidadas podem ser assuntos complexos, é essencial que você insira corretamente e defina os parâmetros para atender às suas necessidades comerciais. Este artigo descreve os parâmetros usados para pagamento de contas a pagar e contas a receber. 

Os parâmetros a seguir afetam como as liquidações são processadas no Microsoft Dynamics 365 for Finance and Operations. A liquidação é o processo de liquidar uma fatura em relação a um pagamento ou nota de crédito. Esses parâmetros estão alocados na área **Liquidação** das páginas **Parâmetros de contas a receber** e das páginas **Parâmetros das contas a pagar**.

-   **Liquidação automática** – Defina esta opção como **Sim** se uma transação for liquidada automaticamente em relação a outras transações abertas quando ela é lançada. Se esta opção estiver definida como **Não**, os usuários podem liquidar transações ao inserir pagamentos, ou posteriormente, usando a página **Liquidar transações**.
-   **Administração de descontos à vista** – Especifique como [o desconto à vista é realizado quando uma fatura é paga em excesso](cash-discount-handling-overpayments.md). Para um pagamento em excesso, o desconto à vista pode ser reduzido, pode ser tratada como uma diferença ou pode continuar sobre a conta do fornecedor ou cliente.
    -   **Não específico** - O valor do desconto à vista é reduzido pelo valor do pagamento excedente. Esse comportamento é usado sempre, independentemente se o valor do pagamento excedente seja maior ou menor do que o valor inserido no campo **Pagamento excedente/faltante** no campo.
    -   **Específico** - O valor do pagamento excedente é lançado em uma conta contábil da diferença do desconto da conta, ou continuará um salda conta do cliente ou do fornecedor. O comportamento específico depende do fato de o valor do pagamento excedente estar entre 0,00 e o valor inserido no campo **Pagamento excedente ou faltante** ou se o valor de pagamento for maior que o valor **Pagamento excedente ou faltante máximo**.
-   **Diferença de centavos máxima** - Insira a diferença de centavos permitida para as transações liquidadas. Se a diferença for igual ou menor do que a diferença de centavos especificada neste campo, ela será lançada na conta contábil da diferença de centavos especificada na página **Contas para transações automáticas**.
-   **Pagamento excedente ou faltante** – Insira o valor que é aceito para pagamentos excedentes e faltantes. Para calcular os impostos em pagamentos a maior ou a menor, na página **Parâmetros da contabilidade**, clique em **Impostos** e selecione a opção **Impostos sobre pagamentos excedentes e faltantes**.
    -   Se o pagamento excedente ou faltante produzir uma diferença menor que a diferença definida no campo **Máxima diferença mínima**, o valor da diferença de centavos será lançado na conta de diferença de centavos.
    -   Se o pagamento excedente ou faltante produzir uma diferença maior que a diferença definida no campo **Diferença máxima de centavos**, o valor da diferença de centavos será lançado na conta de diferença selecionada para o tipo de lançamento **Desconto à vista do cliente** ou **Desconto à vista do fornecedor** na página **Contas para transações automáticas**.
-   **Calcule descontos à vista para pagamentos parciais** – Defina esta opção como **Yes** para permitir que os descontos à vista sejam calculados automaticamente para pagamentos parciais.
    -   Este efeito dessa opção depende do campo **Usar desconto à vista** na página **Liquidar transações**. Se essa opção estiver definida como **Yes**, o desconto será executado quando o campo **Use o desconto à vista** estiver definido como **Normal**. Quando o campo **Use o desconto à vista** estiver definido como **Sempre**, o desconto à vista será sempre considerado, independente das definições deste campo. Quando o campo **Use o desconto à vista** estiver definido como **Sempre**, o desconto à vista nunca será considerado, independente das definições deste campo.
    -   Se essa opção estiver selecionada como **Sim** e um usuário alterar o valor no campo **Valor a ser liquidado** na página **Liquidar transações abertas**, o desconto será calculado automaticamente e exibido como a entrada padrão no campo **Valor do desconto à vista a ser obtido**.
    -   Se essa opção estiver definida como **Não**, e um usuário alterar o valor no campo **Valor a ser liquidado** na página **Liquidar transações**, a entrada padrão no campo **Valor do desconto à vista a ser obtido** é **0**.
-   **Calcular descontos à vista para notas de crédito** – Defina esta opção como **Yes** para calcular automaticamente um desconto à vista para notas de crédito. Em Contas a receber, uma transação de nota de crédito é uma transação negativa que tem um valor no campo **fatura** na página **fatura de texto livre** ou um retorno na página **Ordem de venda**.
    -   O efeito dessa opção depende do valor no campo **Usar desconto à vista** na página **Liquidar transações**. Se essa opção estiver definida como **Sim**, o desconto será executado quando o campo ****Usar o desconto à vista**** estiver definido como **Normal**. Quando o campo ****Usar o desconto à vista**** estiver definido como **Sempre**, o desconto à vista será sempre considerado, independentemente das definições desse campo. Quando o campo ****Usar desconto à vista**** está definido como **Nunca**, o desconto à vista não é aplicado, independentemente da definição desse campo.
    -   Se esta opção estiver definida como **Sim** e uma nota de crédito for inserida na página **Liquidar transações**, o desconto é calculado automaticamente e exibido conforme a inserção padrão no campo **Valor do desconto à vista a ser obtido**.
    -   Se esta opção estiver definida como **Não** e uma nota de crédito for marcada na página **Liquidar transações**, a inserção padrão no campo **Valor do desconto à vista a ser obtido** será **0** (zero).
-   **Contas de contrapartidas de desconto (somente AP)** – Defina a conta contábil padrão do desconto à vista que deve ser usada para a entrada contábil para os descontos à vista.
    -   **Usar a conta principal para descontos de fornecedores** – O desconto à vista é lançado na conta principal que é definida na página **Configuração de desconto à vista**.
    -   **Contas nas linhas da fatura** – O desconto à vista é lançado nas contas contábeis na fatura original.
-   **Marcar linhas nas faturas de texto livre e notas de juros (somente AR)** – Defina esta opção como **Sim** para habilitar o botão **Marcar linhas na fatura** nas páginas **Inserir pagamentos do cliente**, **Comprovante do diário de pagamentos** e **Liquidar transações**. Este botão permite que os usuários marquem linhas individuais para a liquidação.
-   **Priorizar a liquidação (somente AR)** – Defina esta opção como **Sim** para permitir o botão **Marcar pro prioridade** nas páginas **Inserir pagamentos do cliente** e **Liquidar transações**. Este botão permite que os usuários atribuam a ordem predeterminada de liquidação às transações.  Depois que a ordem de pagamento foi aplicada a uma transação, a ordem e a alocação de pagamento podem ser alteradas antes do lançamento.
-   **Use a prioridade para liquidações automáticos** – Defina esta opção como **Sim** para usar a ordem de prioridade definida quando as transações forem liquidadas automaticamente. Este campo só estará disponível se as opções **Priorizar liquidação** e **Liquidação automática** estiverem definidas como **Sim**.





