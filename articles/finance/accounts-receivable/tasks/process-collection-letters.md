---
title: Processar cartas de cobrança
description: Este tópico mostra como criar, imprimir e lançar cartas de cobrança.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-12-01
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: a189bbdd360d07b2b5198fa357380fd9a89ac167
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992955"
---
# <a name="process-collection-letters"></a>Processar cartas de cobrança

[!include [banner](../../includes/banner.md)]

Este tópico mostra como criar, imprimir e lançar cartas de cobrança. Esta tarefa usa a empresa de demonstração USMF.

## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a>Configurar uma sequência de carta de cobrança no perfil de lançamento
1. Vá para **Painel de navegação > Módulos > Crédito e coleções > Configuração > Perfis de lançamentos de cliente**.
2. Clique em **Editar**.
3. Selecione uma sequência de carta de cobrança na lista suspensa. Se você não quiser gerar cartas de cobrança para transações usando este perfil de lançamento, deixe o campo em branco.  
4. Expanda a guia **Restrições da tabela** para alterar a forma como as cartas de cobrança são processadas. Se este campo estiver definido como **Sim**, as cartas de cobrança serão criadas para este perfil de lançamento.  

## <a name="create-collection-letters"></a>Criar cartas de cobrança
1. Vá para **Painel de navegação > Módulos > Crédito e coleções > Carta de cobrança > Criar cartas de cobrança**.
2. Selecione os tipos de transação para os quais você usará cartas de cobrança. Todas as transações abertas para esses tipos serão incluídas no cálculo.  
3. No campo **Carta de cobrança**, selecione uma opção.
4. No campo **Data da carta de cobrança**, insira a data da carta de cobrança.
5. Selecione um perfil de lançamentos se você tiver alterado **Usar perfil de lançamento de** para **Selecionar**. Há duas opções de perfil de lançamento:   

   - **Conta** – use o perfil de lançamentos atribuído à conta de cliente para cada nota de juros.   
   - **Selecionar** - use o perfil de lançamentos selecionado no campo **Perfil de lançamentos**.  

6. Expanda a seção **Registros a serem incluídos**.
7. Selecione **Filtro**.
8. No campo **Critérios**, insira uma ID do Cliente. Por exemplo, insira 'US-001'.
9. Selecione **OK**.
10. Selecione **OK**.

## <a name="print-collection-letters"></a>Imprimir cartas de cobrança
1. Vá para **Painel de navegação > Módulos > Crédito e coleções > Carta de cobrança > Revisar e processar cartas de cobrança**.
2. No campo **Status**, selecione **Criado'**.
3. No campo **Impresso**, selecione **Não impresso'**.
4. Selecione **Imprimir**.
5. Selecione **Nota de carta de cobrança**.
6. Na seção **Parâmetros**, insira a data de fechamento para lançamentos.
7. Expanda a seção **Registros a serem incluídos** e insira os detalhes de Nota de carta de cobrança.
8. Selecione **OK** para imprimir a carta de cobrança.
9. Lance a carta de cobrança.

    1. Selecione **Lançar**.
    1. Inserir a nova data de lançamento para a carta de cobrança.
    1. Expanda a seção **Registros a serem incluídos**.
    1. Selecione **OK**.
    1. No campo **Status**, selecione **Lançado'**.
    1. No campo **Impresso**, selecione uma opção.

## <a name="control-collection-letters-at-the-customer-level"></a>Controle cartas de cobrança em nível de cliente
Se as cartas de cobrança forem configuradas no nível da transação, várias letras poderão ser geradas para um cliente, com base na duração da transação. Se as transações aparecerem em sequências de cartas diferentes, as cartas de cobrança separadas serão geradas para cada grupo de transações vencidas para o cliente. Portanto, um cliente individual pode receber, por exemplo, uma carta de cobrança para transações que têm 60 dias de atraso e outra carta de cobrança para transações que estão vencidas a 90 dias. 

Cada carta de cobrança também é associada a um código de carta de cobrança. O código da carta de cobrança é associado a transações individuais e é usado para determinar quando a próxima carta de cobrança deve ser gerada para cada transação. Por exemplo, se uma transação tiver mais de 30 dias de atraso, o código da carta de cobrança determinará que a próxima carta de cobrança será enviada quando a transação estiver vencida a 60 dias e não tiver sido paga. 

As cartas de cobrança também podem ser configuradas no nível do cliente. Nesse caso, a carta de cobrança para cada transação é rastreada, mas o processamento da carta de cobrança será baseado em um único nível de carta de cobrança que é armazenado para o cliente. A única carta de cobrança conterá todas as transações que estão vencidas para o cliente. Como os dias de carência agora são rastreados em nível de cliente, a próxima carta de cobrança não será enviada até que o número de dias de carência passe para a próxima carta de cobrança na sequência, mesmo que as transações expirem após o envio da última carta de cobrança. Esta opção ajuda a reduzir o número de cartas de cobrança que você deve enviar para cada cliente.

### <a name="set-up-the-customer-to-control-collection-letters-at-the-customer-level"></a>Configure o cliente para controlar as cartas de cobrança em nível de cliente
1.  Vá para **Painel de navegação > Módulos > Crédito e coleções > Configuração > Parâmetros de contas a receber** e selecione a guia **Cobranças**. 
2.  Altere o valor de **Criar carta de cobrança por** para **Cliente**. 
3.  Vá para **Painel de navegação > Módulos > Crédito e coleções > Carta de cobrança > Revisar e processar cartas de cobrança**. Apenas uma carta de cobrança será gerada para um cliente com todas as transações vencidas.

## <a name="ignore-payments-and-credit-memos-when-calculating-the-collection-letter-code"></a>Ignore pagamentos e memorandos de crédito ao calcular o código da carta de cobrança
Se você incluir pagamentos e memorandos de crédito nas transações que serão incluídas nas cartas de cobrança, talvez alguns pagamentos ou memorando de crédito disparem uma carta de cobrança. Você pode controlar como os pagamentos e os memorandos de crédito controlam o código de carta de cobrança alterando o valor do parâmetro **Ignore pagamentos e memorandos de crédito ao calcular o código da carta de cobrança**. 

Para ignore pagamentos e memorandos de crédito ao calcular o código da carta de cobrança, faça o seguinte:

1. Vá para **Painel de navegação > Módulos > Crédito e coleções > Configuração > Parâmetros de contas a receber** e clique na guia **Cobranças**. 
2. Altere o valor de **Ignore pagamentos e memorandos de crédito ao calcular o código da carta de cobrança** para **Sim**.
