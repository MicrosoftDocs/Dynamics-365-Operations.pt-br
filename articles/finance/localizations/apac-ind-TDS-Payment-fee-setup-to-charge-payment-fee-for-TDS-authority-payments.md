---
title: Configurar taxas de pagamento para pagamentos de autoridade TDS
description: Este tópico explica como configurar taxas de pagamento que são cobradas para pagamentos de autoridade de Imposto Deduzido na Origem (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: b52331bb1c7a1bc2c764008112f3df9cc0385995
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023043"
---
# <a name="set-up-payment-fees-for-tds-authority-payments"></a>Configurar taxas de pagamento para pagamentos de autoridade TDS

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar taxas de pagamento que são cobradas para pagamentos de autoridade de Imposto Deduzido na Origem (TDS).

1. Vá para **Contas a pagar \> Configurar pagamento \> Taxa de pagamento**.

    [![Página Taxa de pagamento](./media/apac-ind-TDS-28.png)](./media/apac-ind-TDS-28.png)

2. Selecione **Novo** para criar uma taxa de pagamento e insira os detalhes necessários.
3. No campo **Tipo de taxa**, selecione o tipo de taxa de pagamento:

    - **Nenhuma**
    - **Juros** – Os juros são cobrados sobre pagamentos atrasados feitos ao fornecedor da autoridade TDS.
    - **Outros** – Outros encargos são cobrados em pagamentos atrasados feitos ao fornecedor da autoridade TDS.

    Se você selecionar **Juros** ou **Outros**, o campo **Encargo** será automaticamente definido como **Razão**.

4. Se você selecionou **Juros** ou **Outros** no campo **Tipo de campo**, no campo **Conta principal**, selecione a conta contábil para lançar os juros ou outras cobranças.
5. Insira os outros detalhes necessários.
6. No Painel de Ações, selecione **Configuração de taxa de pagamento** para abrir a página **Configuração de taxa de pagamento**, onde você pode configurar taxas de pagamento para várias combinações de bancos, métodos de pagamento, especificações de pagamento, moedas e intervalos de data.

    [![Página Configuração de taxa de pagamento](./media/apac-ind-TDS-21.png)](./media/apac-ind-TDS-21.png)

7. Na guia **Visão geral**, no campo **Agrupamentos**, especifique para quais bancos você está configurando a taxa de pagamento:

    - **Tabela** – A taxa é válida para uma conta bancária específica.
    - **Grupo** – A taxa é válida para um grupo de bancos específico.
    - **Tudo** – A taxa é válida para todas as contas bancárias.

8. Se você selecionou **Tabela** ou **Grupo** no campo **Agrupamentos**, no campo **Relação do banco**, selecione a conta bancária específica ou grupo de bancos para o qual você está definindo a taxa de pagamento.
9. No campo **Método de pagamento**, selecione a forma de pagamento para o pagamento das taxas.
10. No campo **Especificação de pagamento**, selecione ou insira o código de especificação de pagamento que foi gerado na página **Especificação de pagamento**.
    - A especificação de pagamento é usada com métodos de transferência de fundo eletrônico de pagamento.
12. No campo **Moeda do pagamento**, selecione a moeda que ativa a taxa. Somente as transações que usam a moeda selecionada podem ativar a taxa. Se você deixar esse campo em branco, todas as moedas ativarão a taxa.
13. No campo **Porcentagem/valor**, selecione o método de cálculo. As opções são **Valor**, **Porcentagem** e **Intervalo**.
14. No campo **Valor da taxa**, especifique o valor da taxa como uma porcentagem do pagamento ou o valor de um pagamento.
15. No campo **Moeda da taxa**, especifique o código da moeda para a taxa.
16. Selecione a guia **Geral** para exibir ou modificar os detalhes da conta bancária selecionada.

    [![Guia Geral](./media/apac-ind-TDS-22.png)](./media/apac-ind-TDS-22.png)

16. No campo **Mínimo**, insira o valor mínimo da transação que ativa a taxa.
17. No campo **Máximo**, insira o valor máximo da transação que ativa a taxa.
18. Nos campos **De** e **Até**, defina um intervalo de datas para calcular as taxas.
19. No campo **Taxa mínima**, especifique o valor da taxa como uma porcentagem do pagamento ou o valor de um pagamento.
20. No campo **Grupo de impostos**, selecione o grupo de impostos a ser usado para calcular o imposto para o valor da taxa.
21. No campo **Grupo de impostos do item**, selecione o grupo de impostos do item a ser usado para calcular o imposto do item para o valor da taxa.
22. Selecione a guia **Intervalo**. 

    [![Guia Intervalo](./media/apac-ind-TDS-23.png)](./media/apac-ind-TDS-23.png)

23. No campo **Dias**, insira o número de dias entre a data de lançamento (data de desconto) do pagamento e a data de vencimento da nota promissória.
24. No campo **Porcentagem/valor**, selecione se a especificação é uma porcentagem ou um valor definido.
25. No campo **Valor da taxa**, insira o valor da taxa como uma porcentagem do pagamento ou o valor de um pagamento.
26. Feche a página **Configuração de taxa de pagamento**.
27. Feche a página **Taxa de pagamento**.
