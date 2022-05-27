---
title: O imposto é lançado na conta contábil errada no comprovante
description: Este tópico fornece informações sobre como solucionar problemas que podem ajudar quando o imposto é lançado na conta contábil errada no comprovante.
author: qire
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 9c9f3fc63374b185a795977566cf73c8c29ee5d3
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686425"
---
# <a name="tax-is-posted-to-the-wrong-ledger-account-in-the-voucher"></a>O imposto é lançado na conta contábil errada no comprovante

[!include [banner](../includes/banner.md)]

Durante o lançamento, o imposto pode ser lançado na conta contábil errada no comprovante. Para solucionar esse problema, siga as etapas nas seguintes seções, conforme necessário. Os exemplos neste tópico usam uma ordem de venda como documento comercial.

## <a name="find-the-tax-code-of-the-incorrectly-posted-tax-transaction"></a>Localizar o código de imposto da transação de imposto lançada incorretamente

1. Na página **Transações de comprovante**, selecione a transação com a qual você deseja trabalhar e, em seguida, selecione **Imposto lançado**.

    [![Botão Imposto lançado na página Transações de comprovante.](./media/tax-posted-to-wrong-ledger-account-Picture1.png)](./media/tax-posted-to-wrong-ledger-account-Picture1.png)

2. Revise o valor no campo **Código do imposto**. Neste exemplo, é **IVA 19**.

    [![Campo Código do imposto na página Imposto lançado.](./media/tax-posted-to-wrong-ledger-account-Picture2.png)](./media/tax-posted-to-wrong-ledger-account-Picture2.png)

## <a name="check-the-ledger-posting-group-of-the-tax-code"></a>Verificar o grupo de lançamentos contábeis do código de imposto

1. Acesse **Imposto** \> **Impostos indiretos** \> **Imposto** \> **Códigos de imposto**.
2. Localize e selecione o código de imposto e, em seguida, revise o valor no campo **Grupo de lançamentos contábeis**. Neste exemplo, é **IVA**.

    [![Campo Grupo de lançamentos contábeis na página Códigos de imposto.](./media/tax-posted-to-wrong-ledger-account-Picture3.png)](./media/tax-posted-to-wrong-ledger-account-Picture3.png)

3. O valor no campo **Grupo de lançamentos contábeis** é um link. Para exibir os detalhes da configuração do grupo, selecione o link. Como alternativa, selecione e segure ou clique com o botão direito do mouse no campo e, em seguida, selecione **Exibir detalhes**.

    [![Comando Exibir detalhes.](./media/tax-posted-to-wrong-ledger-account-Picture4.png)](./media/tax-posted-to-wrong-ledger-account-Picture4.png)

4. No campo **Imposto a pagar**, verifique se o número da conta está correto, de acordo com o tipo de transação. Se não estiver, selecione a conta correta para o lançamento. Neste exemplo, o imposto da ordem de venda deve ser lançado na conta de imposto a pagar 222200.

    [![Campo Imposto a pagar na página Grupos de lançamentos contábeis.](./media/tax-posted-to-wrong-ledger-account-Picture5.png)](./media/tax-posted-to-wrong-ledger-account-Picture5.png)

    A tabela a seguir fornece informações sobre cada campo na página **Grupos de lançamentos contábeis**.

    | Campo                  | descrição |
    |------------------------|-------------|
    | Imposto a pagar      | A conta principal para impostos de saída que são pagos para a autoridade fiscal. |
    | Imposto a receber   | A conta principal para impostos de entrada que são recebidos da autoridade fiscal. |
    | Despesas de imposto sobre o uso        | A conta principal usada para lançar impostos sobre o uso dedutíveis que os fornecedores não reclamam nem relatam para a autoridade fiscal como parte do Imposto sobre Bens e Serviços (GST)/Imposto Harmonizado (HST) de encargos revertidos da União Europeia (UE). **Imposto sobre o uso** deve ser selecionado para o código de imposto no grupo de impostos usado na transação. Esse campo não estará disponível se a opção **Aplicar regras de taxação de impostos** estiver selecionada na página **Parâmetros da contabilidade**. |
    | Imposto sobre o uso a pagar        | A conta principal usada para lançar impostos sobre o uso de entrada que são pagos para autoridades fiscais. |
    | Conta de liquidação     | A conta principal usada para lançar o saldo líquido das contas contábeis especificadas nos campos **Imposto sobre o uso a pagar** e **Imposto a receber**. |
    | Desconto à vista do fornecedor   | A conta principal usada para lançar um desconto à vista para os códigos de imposto associados a este grupo de lançamentos contábeis. |
    | Desconto de caso de cliente | A conta principal usada para lançar um desconto à vista para os códigos de imposto associados a este grupo de lançamentos contábeis. |

    Para obter mais informações, consulte [Configurar Grupos de lançamentos contábeis para impostos](tasks/set-up-ledger-posting-groups-sales-tax.md)

## <a name="debug-in-code-to-check-ledger-dimensions"></a>Depurar código para verificar dimensões contábeis

No código, a conta de lançamento é determinada pela dimensão contábil. A dimensão contábil salva a ID de registro de uma conta no banco de dados.

1. Para uma ordem de venda, adicione um ponto de interrupção nos métodos **Tax::saveAndPost()** e **Tax::post()**. Preste atenção ao valor de **\_ledgerDimension**.

    [![Exemplo de código de ordem de venda com um ponto de interrupção.](./media/tax-posted-to-wrong-ledger-account-Picture6.png)](./media/tax-posted-to-wrong-ledger-account-Picture6.png)

    Para uma ordem de compra, adicione um ponto de interrupção nos métodos **TaxPost::saveAndPost()** e **TaxPost::postToTaxTrans()**. Preste atenção ao valor de **\_ledgerDimension**.

    [![Exemplo de código de ordem de compra com um ponto de interrupção.](./media/tax-posted-to-wrong-ledger-account-Picture7.png)](./media/tax-posted-to-wrong-ledger-account-Picture7.png)

2. Execute a consulta SQL a seguir para localizar o valor de exibição da conta no banco de dados, com base na ID de registro salva pela dimensão contábil.

    ```sql
    select * from DIMENSIONATTRIBUTEVALUECOMBINATION where recid={the value of _ledgerDimension}
    ```

    [![Valor de exibição da ID de registro.](./media/tax-posted-to-wrong-ledger-account-Picture8.png)](./media/tax-posted-to-wrong-ledger-account-Picture8.png)

3. Examine a pilha de chamadas para saber onde o valor **_ledgerDimension** foi atribuído. Normalmente, o valor é de **TmpTaxWorkTrans**. Nesse caso, você deve adicionar um ponto de interrupção em **TmpTaxWorkTrans::insert()** e **TmpTaxWorkTrans::update()** para saber onde o valor foi atribuído.

## <a name="determine-whether-customization-exists"></a>Determinar se há personalização

Se você concluiu as etapas nas seções anteriores, mas não encontrou nenhum problema, determine se há personalização. Se não houver personalização, crie uma solicitação de serviço da Microsoft para obter suporte adicional.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
