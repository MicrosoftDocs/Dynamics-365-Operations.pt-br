---
title: Agenda de índice de preços ao consumidor
description: Este artigo explica como criar a lista de agendas de índice de preços do consumidor (IDC) obtidas na Internet para ajudar a determinar o encargo de escalonamento na cobrança de assinatura.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: f08b79ee00baab3713d9ccc24a7595b1de7a7768
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904863"
---
# <a name="consumer-price-index-schedule"></a>Agenda de índice de preços ao consumidor

[!include [banner](../includes/banner.md)]

Este artigo explica como criar, excluir, revisar e processar agendas de índices de preço do consumidor (IDC). Uma agenda de IDC pode ser usada para determinar os preços de bens de consumo e serviços que você adiciona como linhas de plano de cobrança. A agenda de IDC pode ser usada com a definição de preços de escalonamento e de descontos em uma programação de cobrança ou pode ser processada manualmente para atualizar os valores de cobrança nos planos de cobrança. Você pode inserir manualmente agendas de IDC ou importá-las usando a entidade composta de agenda de IDC.

Para adicionar uma agenda de IDC, siga estas etapas.

1. Na página **Agenda de índice de preço de consumo**, selecione **Novo**.
2. No campo **Agenda de índice de preço de consumo**, insira um nome exclusivo.
3. No campo **Descrição**, insira uma descrição.
4. Na guia **Agenda de índice de preço de consumo**, selecione **Adicionar**.
5. No campo **Data do índice de preço de consumo**, especifique a data em que a nova agenda de IDC se tornará ativa.
6. No campo **Agenda de índice de preço de consumo**, insira o nome que você inseriu na etapa 2.
7. Selecione **Salvar**.

Para excluir uma data de agenda de IDC, siga estas etapas.

1. Na página **Agenda do índice de preço de consumo**, selecione uma ou mais linhas que deseja excluir e, em seguida, selecione **Remover**.
2. Para excluir a agenda de IDC inteira, no painel de ações, selecione **Excluir**. Não é possível excluir a agenda de IDC selecionada quando ela está associada a qualquer agenda de cobrança.
3. No Painel de Ações, selecione **Processo** para atualizar as agendas de cobrança que usam a agenda de IDC selecionada. As últimas datas e valores de agenda de IDC serão usadas para atualizar os preços da agenda de cobrança.
4. Na Guia Rápida **Processo de índice de preço de consumo**, revise o **Número de agenda de cobrança** atualizado, o **Número do item**, a **Data de início da cobrança**, a **Data de término da cobrança**, a **Data de escalonamento** e os campos de **Frequência de escalonamento**.

Depois que as agendas de IDC são configuradas, elas podem ser usadas para alterações de escalonamento e preço de desconto em agendas de cobrança.

## <a name="cpi-calculation"></a>Cálculo de CPI

Para esses exemplos, o período é de 1º de janeiro de 2020 até 31 de dezembro de 2022. A taxa de IDC base (o valor de IDC quando o contrato é iniciado) é 105,65. Em 1º de janeiro de 2021, o IDC atual é 110,5. Em 1º de janeiro de 2022, o IDC atual é 114,25. O valor inicial é US$ 1.000.

**Exemplo 1**

Na página **Parâmetros de cobrança recorrente de contrato**, defina o campo **Cálculo de índice de preço de consumo** como **Índice de preço de consumo base**.

Para o período de 1 de janeiro de 2021, o primeiro valor de escalonamento é calculado da seguinte forma, com base no valor inicial:

1.000 + (110,5 – 105,65) &divide; 105,65 &times; 1.000 = 1.045,91

Para o período de 1 de janeiro de 2022, o valor de escalonamento é calculado da seguinte forma:

1.000 + (114,25 – 105,65) &divide; 105,65 &times; 1.000 = 1.081,40

**Exemplo 2**

Na página **Parâmetros de cobrança recorrente de contrato**, defina o campo **Cálculo de índice de preço de consumo** como **Índice de preço de consumo anterior**.

Para o período de 1 de janeiro de 2021, o primeiro valor de escalonamento é calculado da seguinte forma, com base no valor inicial:

1.000 + (110,5 – 105,65) &divide; 105,65 &times; 1.000 = 1.045,91

Para o período de 1 de janeiro de 2022, o primeiro valor de escalonamento é calculado da seguinte forma, com base no valor do primeiro escalonamento:

1.045,91 + (114,25 – 110,5) &divide; 110,5 &times; 1.045,91 = 1.081,40

> [!NOTE]
> O processo de escalonamento sempre usa o último valor de IDC, independentemente da data do índice. Por exemplo, se o escalonamento estiver em setembro, mas o valor IDC mais recente for para julho, o índice de julho será usado. Nenhum ajuste é feito depois que o índice de setembro é inserido.

## <a name="prorated-escalation"></a>Escalonamento com taxas

Se o escalonamento ocorrer no meio de um período de cobrança, o valor será rateado. Por exemplo, o período de cobrança é de 1º de agosto de 2020 até 31 de julho, 2021. Na data do IDC, 1º de setembro de 2019, o valor de CPI é 244. Na data do IDC, 1º de setembro de 2020, esse valor de CPI é 250. Se a taxa anterior for 1.000, as seguintes fórmulas serão usadas para calcular o valor de cobrança para o período:

* *Alterações de IDC* = (250 – 244) &divide; 244 = 2,459%
* *Taxa atual* = 1.000 &times; 2,459% = 1.024,59
* *Número de dias na taxa atual* = 31 de julho de 2021 – 1º de setembro de 2020 = 334
* *Taxa anterior* = 1.000
* *Número de dias na taxa anterior* = 31 de agosto de 2020 – 1º de agosto de 2020 = 31
* *Número total de dias no período de cobrança* = 31 de julho de 2021 – 1º de agosto de 2020 + 1 = 365
* *Valor de cobrança para este período* = (1.000 &times;31 &divide;365) + (1024,59 &times;334 &divide;365) = 1022,50

## <a name="escalation-that-uses-the-cpi-and-percentage"></a>Escalonamento que usa o IDC e a porcentagem

As escalonamentos podem ser feitos usando o IDC. O CPI mais um escalonamento de 3% começa em 1º de janeiro de 2020 e tem uma frequência anual.

- O valor cobrado em 1º de janeiro de 2019, até 31 de dezembro de 2020, é 4.000.
- O período de cobrança que será escalonado será 1 de janeiro de 2020 a até 31 de dezembro de 2020.
- Na data do IDC, 1º de dezembro de 2018, o valor de CPI é 205,3. Na data do IDC, 1º de dezembro de 2019, o valor de CPI é 219,6.

Se a taxa anterior for 4.000, o valor de cobrança para esse período é calculado da seguinte maneira:

- *Alterações de IDC* = (219,6 – 205,3) &divide; 205,3 = 6,965%
- *Taxa atual* = (4.000 &times; 6,965%) – 4.000 = 278,60
- *Alterações percentuais* = (4.000 &times; 1,03) – 4.000 = 120
- *Valor de cobrança* = 4.000 + 278,6 + 120 = 4398,6
