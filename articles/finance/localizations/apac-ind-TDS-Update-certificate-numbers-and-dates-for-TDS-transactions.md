---
title: Atualizar números e datas de certificado para transações de TDS
description: Este tópico explica como atualizar os números e datas do certificado recuperável que foram registrados para contas de fornecedor, cliente e razão para Imposto Deduzido na Origem (TDS).
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
ms.openlocfilehash: b23f01f110009ba2f0cfe71c7bb995a4dc21ca3b
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8408271"
---
# <a name="update-certificate-numbers-and-dates-for-tds-transactions"></a>Atualizar números e datas de certificado para transações de TDS

[!include [banner](../includes/banner.md)]

Este tópico explica como atualizar os números e datas do certificado recuperável que foram registrados para contas de fornecedor, cliente e razão para Imposto Deduzido na Origem (TDS). Você pode exibir os certificados para transações de TDS na página **Certificados recuperáveis**. Você pode atualizar os certificados usando a página **Atualizar Certificados**.

Siga estas etapas para atualizar os números e datas dos certificados para transações de TDS.

1. Acesse **Imposto \> Declarações \> Imposto retido na fonte \> Atualizar certificado**.

    [![Página Atualizar certificado.](./media/apac-ind-TDS-45.png)](./media/apac-ind-TDS-45.png)

2. Na página **Atualizar certificado**, na seção **Selecionar** no campo **Tipo de imposto**, selecione **TDS**.
3. No campo **Número do certificado**, selecione o número do certificado TDS do cliente ou do fornecedor.

    > [!NOTE]
    > O campo **Número do certificado** lista somente os números de certificados de TDS para os quais a caixa de seleção **Fechada** está desmarcada na página **Certificados recuperáveis**.

    O campo **Data do certificado**, mostra a data do certificado. O campo **Tipo de conta** mostra o tipo de conta para a qual o número do certificado de TDS é recebido e o campo **Nome** mostra o nome da conta.

5. Nos campos **Data inicial** e **Data final** selecione as datas inicial e final do período para mostrar as transações TDS.
6. Selecione **Mostrar dados** para exibir as transações de TDS que foram lançadas durante o período selecionado.

    Na guia **Visão geral**, a grade no painel superior mostra as seguintes informações sobre cada transação de TDS que foi lançada para o fornecedor ou cliente durante o período selecionado:

    - **Comprovante** – O número do comprovante da transação de TDS.
    - **Data** – A data da transação de TDS.
    - **Valor** – O valor da fatura sobre o qual o TDS foi calculado.
    - **Valor do imposto** – O valor do imposto TDS calculado para a transação.

7. Para mover transações de TDS específicas da grade superior para a grade inferior, selecione as transações e, em seguida, selecione **Incluir**. Como alternativa, selecione **Incluir tudo** para mover todas as transações de TDS da grade superior para a grade inferior.

    Para mover transações de TDS específicas ou todas as transações de TDS da grade inferior para a grade superior, use o botão **Excluir** ou **Excluir tudo**.

8. Selecione **Atualizar** para atualizar os campos **Número do certificado** e **Data do certificado** para transações de TDS na grade inferior.
10. Acesse **Imposto \> Impostos indiretos \> Imposto retido na fonte \> Certificado recuperável** e selecione **Consulta** para exibir as linhas de transação atualizadas que têm os novos números de certificados na página **Transações do certificado**.

    [![Página Transações do certificado.](./media/apac-ind-TDS-46.png)](./media/apac-ind-TDS-46.png)
