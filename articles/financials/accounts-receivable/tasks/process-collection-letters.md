--- 
title: "Processar cartas de cobrança"
description: "Este procedimento mostra como criar, imprimir e lançar cartas de cobrança."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 12/04/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-12-01
ms.dyn365.ops.version: 8.1.3
ms.translationtype: HT
ms.sourcegitcommit: 075d0f5dc0c9dc4e46dc92a2da75da9f7a207472
ms.openlocfilehash: 33d9fd62a780ab109474eefa9e322a9c529f9e72
ms.contentlocale: pt-br
ms.lasthandoff: 12/06/2018

---
# <a name="process-collection-letters"></a>Processar cartas de cobrança

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../../includes/preview-banner.md)]

Este procedimento mostra como criar, imprimir e lançar cartas de cobrança. Esta tarefa usa a empresa de demonstração USMF.

## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a>Configurar uma sequência de carta de cobrança no perfil de lançamento
1. Vá para **Crédito e cobranças > Configuração > Perfis de lançamentos de cliente**.
2. Clique em **Editar**.
3. Selecione uma sequência de carta de cobrança na lista suspensa. Se você não quiser gerar cartas de cobrança para transações usando este perfil de lançamento, deixe o campo em branco.  
4. Expanda a guia de restrição de tabela para alterar a forma como as cartas de cobrança são processadas. Se este campo estiver definido como **Sim**, as cartas de cobrança serão criadas para este perfil de lançamento.  

## <a name="create-collection-letters"></a>Criar cartas de cobrança
1. Vá para **Crédito e cobranças > Carta de cobrança > Criar cartas de cobrança**.
2. Selecione os tipos de transação para os quais você usará cartas de cobrança. Todas as transações abertas para esses tipos serão incluídas no cálculo.  
2. No campo **Carta de cobrança**, selecione uma opção.
3. Insira a data da carta de cobrança.
4. Selecione um perfil de lançamentos se você tiver alterado **Usar perfil de lançamento de** para **Selecionar**. Há duas opções de perfil de lançamento:   
   - **Conta** – use o perfil de lançamentos atribuído à conta de cliente para cada nota de juros.   
   - **Selecionar** - use o perfil de lançamentos selecionado no campo **Perfil de lançamentos**.  
5. Expanda a seção **Registros a serem incluídos**.
6. Clique em **Filtrar**.
7. No campo **Critérios**, insira uma ID do Cliente. Por exemplo, insira 'US-001'.
8. Clique em **OK**.
9. Clique em **OK**.

## <a name="print-collection-letters"></a>Imprimir cartas de cobrança
1. Vá para **Crédito e cobranças > Carta de cobrança > Revisar e processar cartas de cobrança**.
2. No campo **Status**, selecione **Criado'**.
3. No campo **Impresso**, selecione **Não impresso'**.
4. Clique em **Imprimir**.
5. Clique em **Nota de carta de cobrança**.
6. Expanda a seção **Registros a serem incluídos**.
7. Insira a data de fechamento para lançamentos.
8. Clique em **OK** para imprimir a carta de cobrança.
9. Lance a carta de cobrança.
   1. Clique em **Enviar**.
   2. Inserir a nova data de lançamento para a carta de cobrança.
   3. Expanda a seção **Registros a serem incluídos**.
   4. Clique em **OK**.
   5. No campo **Status**, selecione **Lançado'**.
   6. No campo **Impresso**, selecione uma opção.

## <a name="control-collection-letters-at-the-customer-level"></a>Controle cartas de cobrança em nível de cliente
Você também pode configurar cartas de cobrança em nível de cliente para que o código da carta de cobrança para cada transação seja rastreado, mas o processamento da carta de cobrança será baseado em um único nível de carta de cobrança que é armazenado para o cliente. A única carta de cobrança conterá todas as transações que estão vencidas para o cliente. Como os dias de carência agora são rastreados em nível de cliente, a próxima carta de cobrança não será enviada até que o número de dias de carência passe para a próxima carta de cobrança na sequência, mesmo que as transações expirem após o envio da última carta de cobrança. Esta opção reduz o número de cartas de cobrança enviadas por cliente. 

### <a name="set-up-the-customer-to-control-collection-letters-at-the-customer-level"></a>Configure o cliente para controlar as cartas de cobrança em nível de cliente
1.  Vá para **Crédito e cobranças > Configuração > Parâmetros de contas a receber** e clique na guia **Cobranças**. 
2.  Altere o valor de **Criar carta de cobrança por** para **Cliente**. 
3.  Vá para **Crédito e cobranças > Carta de cobrança > Revisar e processar cartas de cobrança**. Apenas uma carta de cobrança será gerada para um cliente com todas as transações vencidas.

## <a name="ignore-payments-and-credit-memos-when-calculating-the-collection-letter-code"></a>Ignore pagamentos e memorandos de crédito ao calcular o código da carta de cobrança
Se você incluir pagamentos e memorandos de crédito nas transações que serão incluídas nas cartas de cobrança, talvez alguns pagamentos ou memorando de crédito disparem uma carta de cobrança. Você pode controlar como os pagamentos e os memorandos de crédito controlam o código de carta de cobrança alterando o valor do parâmetro **Ignore pagamentos e memorandos de crédito ao calcular o código da carta de cobrança**. 

Para ignore pagamentos e memorandos de crédito ao calcular o código da carta de cobrança, faça o seguinte:
1. Vá para **Crédito e cobranças > Configuração > Parâmetros de contas a receber** e clique na guia **Cobranças**. 
2. Altere o valor de **Ignore pagamentos e memorandos de crédito ao calcular o código da carta de cobrança** para **Sim**.

