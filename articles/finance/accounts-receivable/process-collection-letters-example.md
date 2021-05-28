---
title: Processar exemplo de cartas de cobrança
description: Este tópico percorre um exemplo que mostra o processo de criação, impressão e lançamento de cartas de cobrança.
author: JodiChristiansen
ms.date: 02/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: fb2651644efd2cadfccb91e48c34dfddc8383e1f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021407"
---
# <a name="process-collection-letters-example"></a>Processar exemplo de cartas de cobrança

[!include [banner](../../includes/banner.md)]

Este tópico percorre um exemplo que mostra o processo de criação, impressão e lançamento de cartas de cobrança. O exemplo se baseia na opção **Ignorar pagamentos e memorandos de crédito ao calcular o código da carta de cobrança** em Crédito e cobranças. Ele usa os dados da empresa de demonstração de USMF e um novo cliente, EUA-045.

Para começar, vá para **Clientes de contas \> a receber \> Todos os clientes**, selecione **Novo** e insira as informações necessárias para criar um cliente US-045.

Quando terminar, siga estas etapas.

1. Vá para **Crédito e cobranças \> Carta de cobrança \> Configurar sequência de cartas de cobrança** e configure a sequência de carta de cobrança, conforme mostrado na tabela a seguir que é atribuída ao perfil de lançamentos do cliente.

|     Código de carta de cobrança      |     descrição                           |     Moeda      |     Conta principal        |     Taxa em moeda     |     Mínimo sobre        |     Bloco de Dias      |
|---------------------------------  |---------------------------------------    |-----------------  |-----------------------    |-------------------------- |-----------------------    |---------------------  |
|     Carta de cobrança 1         |     Segunda notificação com taxa        |     USD           |                           |     0,00                  |     0,00                  |     2                 |
|     Carta de cobrança 2         |     Segunda notificação com taxa        |     USC           |     403150                |     20.00                 |     10,00                 |     3                 |
|     Cobrança                    |     Notificação final com taxa         |     USD           |     403150                |     50.00                 |     100.00                |     15                |

A ilustração a seguir mostra as informações que estão na tabela como apareceriam na página **Cartas de cobrança**. 

[![Configurando uma sequência de cartas de cobrança](./media/Ignore-payments-creditmemos-1.PNG)](./media/Ignore-payments-creditmemos-1.PNG)

 Agora você deve definir os dois parâmetros necessários para este exemplo.

2. Vá para **Crédito e cobranças \> Configuração \> Parâmetros de contas a receber** e siga estas etapas:

    1. Na guia **Cobranças**, defina a opção **Ignorar pagamentos e memorandos de crédito ao calcular o código da carta de cobrança** como **Sim**.
    2. Verifique se o campo **Criar carta de cobrança por** foi definido como **Cliente**.

    [![Configurando parâmetros de contas a receber para Crédito e cobranças](./media/Ignore-payments-creditmemos-2.PNG)](./media/Ignore-payments-creditmemos-2.PNG)

3. Vá para **Contas a receber \> Faturas \> Todas as faturas de texto livre**, selecione **Novo** e siga estas etapas:

    1. No campo **Conta do cliente**, selecione **US-045**.
    2. No campo **Data da fatura**, digite **15/01/2021**.
    3. No campo **Data de conclusão**, digite **16/01/2021**.
    4. Na guia rápida **Linhas da fatura** no campo **Conta principal**, digite **401100**.
    5. No campo **Preço unitário**, insira **500.00**.
    6. Selecione **Lançar**.

    Agora, você deve inserir duas notas de crédito para o cliente.

4. Selecione **Novo** e siga estas etapas:

    1. No campo **Conta do cliente**, selecione **US-045**.
    2. No campo **Data da fatura**, digite **15/01/2021**.
    3. No campo **Data de conclusão**, digite **16/01/2021**.
    4. Na guia rápida **Linhas da fatura** no campo **Conta principal**, digite **401100**.
    5. No campo **Preço unitário**, digite **-100.00**.
    6. Selecione **Lançar**.

5. Repita a etapa 4, mas insira **-200,00** no campo **Preço unitário**.
6. Vá para **Contas a receber \> Clientes \> Todos os clientes** e selecione cliente **US-045**. Em seguida, no painel de ação, selecione **Transações \> Transações** para revisar as transações de cliente lançadas anteriormente.

    [![Analisando as transações do cliente lançadas](./media/Ignore-payments-creditmemos-3.PNG)](./media/Ignore-payments-creditmemos-3.PNG)

    Agora você precisa criar cartas de cobrança para um cliente US-045.

7. Vá para **Crédito e cobranças \> Carta de cobrança \> Criar cartas de cobrança** e siga estas etapas:

    1. Defina as **Fatura** e **Nota de crédito** como **Sim**.

        Por padrão, o campo **Carta de cobrança** deve ser definido como **Coleção por cliente**.

    2. No campo **Data da carta de cobrança**, digite **19/01/2021**.
    3. Na guia rápida **Registros a serem incluídos**, selecione **Filtrar** e, em seguida, no campo **Conta de cliente**, adicione o cliente **US-045**.
    4. Selecione **OK**.
    5. Selecione **OK** para criar cartas de cobrança.

8. Vá para **Crédito e cobranças \> Carta de cobrança \> Revisar e processar cartas de cobrança** e siga estas etapas:

    1. Observe que o código da carta de cobrança no cabeçalho e nas linhas de transação é **Carta de cobrança 1**, pois essa carta de cobrança é a primeira carta de cobrança na sequência. (Para exibir as linhas de transação, talvez seja necessário selecionar a guia rápida **Transações**.)

   [![Verificando se o mesmo código de carta de cobrança aparece no cabeçalho e nas linhas](./media/Ignore-payments-creditmemos-4.PNG)](./media/Ignore-payments-creditmemos-4.PNG)

    2. No Painel de Ação, selecione **Lançar**.
    3. No campo **Data do lançamento**, digite **19/01/2021**.

    Agora você precisa criar cartas de cobrança novamente para um cliente US-045.

9. Vá para **Crédito e cobranças \> Carta de cobrança \> Criar cartas de cobrança** e siga estas etapas:

    1. Defina as **Fatura** e **Nota de crédito** como **Sim**.

        Por padrão, o campo **Carta de cobrança** deve ser definido como **Coleção por cliente**.

    2. No campo **Data da carta de cobrança**, digite **23/01/2021**.
    3. Na guia rápida **Registros a serem incluídos**, selecione **Filtrar** e, em seguida, no campo **Conta de cliente**, adicione o cliente **US-045**.
    4. Selecione **OK**.
    5. Selecione **OK** para criar cartas de cobrança.

10. Vá para **Crédito e cobranças \> Carta de cobrança \> Revisar e processar cartas de cobrança** e siga estas etapas:

    1. Observe que o código da carta de cobrança no cabeçalho é **Carta de cobrança 1**. No entanto, o código nas linhas de transação é **Carta de cobrança 2**.

   [![Verifica se os diferentes códigos de carta de cobrança aparece no cabeçalho e nas linhas](./media/Ignore-payments-creditmemos-5.PNG)](./media/Ignore-payments-creditmemos-5.PNG)

  Os códigos diferem porque a opção **Ignorar pagamentos e memorandos de crédito ao calcular o código da carta de cobrança** é definida como **Sim**.

  2. Não lançar a carta de cobrança.

11. Vá para **Crédito e cobranças \> Configuração \> Parâmetros de contas a receber** e na guia **Cobranças**, defina a opção **Ignorar pagamentos e memorandos de crédito ao calcular o código da carta de cobrança** como **Não**.

    [![Defina a opção Ignorar pagamentos e memorandos de crédito ao calcular o código da carta de cobrança como Não](./media/Ignore-payments-creditmemos-6.PNG)](./media/Ignore-payments-creditmemos-6.PNG)

    Agora você precisa criar cartas de cobrança novamente para um cliente US-045.

12. Vá para **Crédito e cobranças \> Carta de cobrança \> Criar cartas de cobrança** e siga estas etapas:

    1. Defina as **Fatura** e **Nota de crédito** como **Sim**.

        Por padrão, o campo **Carta de cobrança** deve ser definido como **Coleção por cliente**.

    2. No campo **Data da carta de cobrança**, digite **23/01/2021**.
    3. Na guia rápida **Registros a serem incluídos**, selecione **Filtrar** e, em seguida, no campo **Conta de cliente**, adicione o cliente **US-045**.
    4. Selecione **OK**.
    5. Selecione **OK** para criar cartas de cobrança.

13. Vá para **Crédito e cobranças \> Carta de cobrança \> Revisar e processar cartas de cobrança** e observe que o código da carta de cobrança no cabeçalho e nas linhas de transação é **Carta de cobrança 2**.

    [![Mostrando novamente que o mesmo código de carta de cobrança aparece no cabeçalho e nas linhas](./media/Ignore-payments-creditmemos-7.PNG)](./media/Ignore-payments-creditmemos-7.PNG)

    O mesmo código aparece nos dois locais porque a opção **Ignorar pagamentos e memorandos de crédito ao calcular o código da carta de cobrança** agora foi definida como **Não**.
