---
title: Receita não faturada
description: Este tópico explica como configurar items e contas para usar o recurso de receita não faturada na Cobrança de assinatura.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 4a5bd016649957d90876d4eb50c358cd9d6fba80
ms.sourcegitcommit: 836695c0e95d366ba993f34eee30f57191f356d8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2022
ms.locfileid: "8629386"
---
# <a name="unbilled-revenue"></a>Receita não faturada

Este tópico descreve o recurso de receita não faturada que permite incluir os valores de todas as agendas de cobrança no balanço. Esses valores são incluídos em uma conta de receita não faturada e em uma contrapartida de receita não faturada, e o contrato é cobrado em prestações.

## <a name="set-up-unbilled-revenue"></a>Configurar receita não faturada

Para configurar a receita não faturada, siga estas etapas.

- Na página **Parâmetros de cobrança recorrente de contrato**, configure os campos na seção **Receita não faturada**.
- O recurso de receita não faturada pode ser usado para itens nos quais o campo **Tipo de item** está definido como **Padrão**. Ele também pode ser usado para itens de adiamento. Para usar a receita não faturada com a funcionalidade de curto prazo, configure as opções de curto prazo na página **Parâmetros de cobrança recorrente de contrato**.

Para configurar os itens para usar a receita não faturada, siga estas etapas.

1. Na página **Configuração de receita não faturada**, na guia **Itens**, selecione **Adicionar**.
2. Na nova linha, em **Código do item**, selecione o código do item.
3. No campo **Relação de item**, selecione a relação do item.
4. Repita essas etapas para adicionar mais linhas.
5. Selecione **Salvar**.

Para configurar os itens e as contas de receita não faturada, siga estas etapas.

1. Na página **Configuração de receita não faturada**, na guia **Contas**, selecione **Adicionar**.
2. Na nova linha, em **Código do item**, selecione o código do item.
3. No campo **Relação de item**, selecione a relação do item.
4. Selecione as contas para receita não faturada, desconto não faturado e compensação da receita não faturada. Para usar as contas de curto prazo, você deve definir o campo **Método não faturado de curto prazo** como **Períodos anteriores** ou **Ano fixo** na página **Parâmetros de cobrança de contrato recorrentes**.
5. Repita essas etapas para adicionar mais linhas.
6. Selecione **Salvar**.

## <a name="use-unbilled-revenue"></a>Usar receita não faturada

1. Na página **Todas as agendas de cobrança**, crie uma agenda de cobrança.
2. Se o item ainda não estiver configurado para usar receita não faturada, marque a caixa de seleção **Receita não faturada** na linha da agenda de cobrança.
3. Defina a opção **Receita não faturada** como **Sim**. Depois, revise e edite as contas de receita não faturada, desconto e compensação da receita não faturada, conforme necessário.
4. Na agenda de cobrança, em **Processamento de receita não faturada**, selecione **Criar entrada de diário** para criar a entrada de diário inicial para a receita não faturada. Esta etapa deve ser concluída antes que a agenda de cobrança seja faturada.
5. Depois que a entrada de diário inicial for criada, selecione **Gerar fatura** para criar ordens de venda e lançar as faturas para as agendas de cobrança.
6. Depois que as faturas são lançadas, você pode revisar as informações de auditoria na guia **Renovações** da página **Todas as agendas de cobrança**.

### <a name="milestone-billing"></a>Cobrança por etapa

A cobrança por etapa funciona com receita não faturada sob as seguintes condições:

- Se o item pai da etapa não estiver faturado (a caixa de seleção **Receita não faturada** está marcada) e os itens filho da etapa estiverem faturados (a caixa de seleção **Receita não faturada** está desmarcada), as datas de início e de término do item pai deverão ser especificadas. Essas datas são usadas para criar a entrada de diário inicial.
- Se o item pai da etapa não estiver faturado (a caixa de seleção **Receita não faturada** está desmarcada) e os itens filho da etapa estiverem faturados (a caixa de seleção **Receita não faturada** está marcada), a data de término deverá ser especificada somente para os itens filho para os quais você quer criar a entrada de diário inicial.

Cada item filho da etapa pode ser processado separadamente. As datas de término poderão ser especificadas quando você estiver pronto para criar a entrada de diário inicial.

> [!NOTE]
> Se a entrada de diário inicial para o item pai da etapa ou os itens filho já tiver sido criada ou uma fatura tiver sido gerada, as datas de início e término não poderão ser editadas.

### <a name="unbilled-revenue-with-straight-line-deferrals"></a>Receita não faturada com adiamentos lineares

Para usar a receita não faturada com agendas de adiamento linear, siga estas etapas.

1. Na página **Todas as agendas de cobrança**, crie uma agenda de cobrança.
2. Adicione um item às linhas da agenda de cobrança.
3. Selecione **Adiamentos** para a linha.
4. Na página **Adiamento de transação**, siga estas etapas:

    1. Defina a opção **Adiado** como **Sim**.
    2. Altere as contas conforme necessário.
    3. Na seção **Agenda**, selecione **Linear** e edite outros valores conforme necessário.
    4. Selecione **OK**.

5. Selecione **Receita não faturada** para a linha e siga estas etapas:

    1. Defina a opção **Receita não faturada** como **Sim**.
    2. Selecione as contas para usar para a receita, o desconto e a compensação da receita.

6. Na agenda de cobrança, em **Processamento de receita não faturada**, selecione **Criar entrada de diário**. Como alternativa, use a página **Processamento em massa de receita não faturada** para criar a entrada de diário.
7. A agenda de adiamento é criada. Você pode ver os detalhes na página **Todas as agendas de adiamento**. Depois que a agenda de adiamento é criada, você pode editar vários valores para o item de linha dela. Por exemplo, é possível editar o preço unitário, a quantidade ou as datas.

### <a name="unbilled-revenue-with-event-based-deferrals"></a>Receita não faturada com adiamentos baseados em eventos

Para usar a receita não faturada com agendas de adiamento baseadas em eventos, siga estas etapas.

1. Na página **Todas as agendas de cobrança**, crie uma agenda de cobrança.
2. Adicione um item às linhas da agenda de cobrança.
3. Selecione **Adiamentos** para a linha.
4. Na página **Adiamento de transação**, siga estas etapas:

    1. Defina a opção **Adiado** como **Sim**.
    2. Altere as contas conforme necessário.
    3. Na seção **Agenda**, selecione **Baseado em eventos**, **Modelo**, **Tipo de alocação** e **Conta de expiração**.
    4. Selecione **OK**.

5. Selecione **Receita não faturada** para a linha e siga estas etapas:

    - Defina a opção **Receita não faturada** como **Sim**.
    - Selecione as contas para usar para a receita, o desconto e a compensação da receita.

6. Na agenda de cobrança, em **Processamento de receita não faturada**, selecione **Criar entrada de diário**. Como alternativa, use a página **Processamento em massa de receita não faturada** para criar a entrada de diário.
7. A agenda de adiamento é criada. Você pode ver os detalhes na página **Todas as agendas de adiamento**. Depois que a agenda de adiamento é criada, você pode editar vários valores para o item de linha dela. Por exemplo, é possível editar o preço unitário, a quantidade ou as datas. A agenda de adiamento é recalculada com base nos novos valores.

As distribuições são recalculadas com base no tipo de alocação selecionado (**Porcentagem**, **Porcentagem de conclusão** ou **Valores iguais**). Para o tipo de alocação de **Valores variáveis**, a distribuição é recalculada com base na porcentagem equivalente do valor inicial do evento. Por exemplo, o preço unitário original é $100,00 e a porcentagem do valor inicial é $55,00 (55 por cento). Se o preço unitário for alterado para $200,00, o valor variável do evento se tornará $110,00 (ainda 55 por cento).

> [!NOTE]
> Se as linhas da agenda de adiamento tiverem sido reconhecidas, o item de linha da agenda de cobrança não poderá ser editado. Para editar o item de linha, você deve primeiro reverter as linhas reconhecidas. A linha da agenda de cobrança pode ser então atualizada.

### <a name="unbilled-revenue-and-top-billing"></a>Receita não faturada e cobrança principal

Uma agenda de cobrança é inserida por três anos, e as faturas são faturadas anualmente em um período de três anos. Todo o valor do contrato é registrado na conta de receita não faturada a partir da qual as faturas anuais são criadas. A contrapartida é a conta de receita ou a conta de receita adiada.

Observe que a cobrança principal e a receita não faturada não funcionam juntas, pois podem ocorrer problemas de reconciliação na contabilidade. Por exemplo, na página **Configuração de grupo de itens**, o grupo de itens A é configurado de forma que o campo **Número de linhas principais** seja definido como **2**. Na página **Agendas de cobrança**, três itens são adicionados. Todos os três itens pertencem ao grupo de itens A. Quando a entrada de diário inicial é criada para o recurso de receita não faturada, o valor dos três itens é processado para a conta não faturada. Quando a fatura da agenda de cobrança é criada, somente os valores dos dois itens principais são incluídos. Portanto, o valor da fatura não corresponde ao valor processado para a conta de receita não faturada, e problemas de reconciliação ocorrem na contabilidade.

Se você quiser usar a receita não faturada, deixe a página **Configuração do grupo de itens** em branco ou configure todos os grupos de itens para que o campo **Número de linhas principais** seja definido como **0** (zero). Se você deseja usar a cobrança principal, não há nenhuma ação de receita não faturada disponível.

### <a name="examples"></a>Exemplos

A partir da versão 10.0.27, uma nova conta é inserida quando a receita não faturada é usada. Quando o processo de **criação de entrada de diário** é lançado, o crédito é feito para uma nova contrapartida de receita não faturada. Essa conta é usada no lugar da conta de receita, pois o mesmo valor deve ser revertido quando a agenda de cobrança é faturada. Se ocorrerem diferenças de taxa de câmbio ou de arredondamento, os valores calculados durante o processo de **geração de fatura** podem ser diferentes. Esse comportamento garante que o valor líquido das contas seja 0 (zero).

Esse exemplo mostra como usar a receita não faturada para reconhecer todo o valor de um contrato no balanço como receita não faturada. O outro lado da entrada é a contrapartida da receita não faturada. Quando você fatura o cliente, a receita não faturada e a contrapartida da receita não faturada são revertidas. O reconhecimento de receita ocorrerá no momento do faturamento ou de acordo com a agenda de reconhecimento de adiamento configurada.

#### <a name="assumptions"></a>Hipóteses

- Em 1º de Janeiro do ano atual, um cliente assina um contrato de três anos de $390.
- O contrato inclui duas partes: um contrato de licenciamento e um contrato de manutenção.
- O preço de venda da taxa de licença é $300, e o cliente terá uma cobrança de $100 em 1º de janeiro de cada ano do contrato. A taxa de licença de $300 será considerada como receita quando o contrato for assinado.
- O preço de venda da taxa de manutenção é $90, e o cliente terá uma cobrança de $30 em 1º de janeiro de cada ano do contrato. A taxa de manutenção de $90 será adiada, e o valor de $2,50 será reconhecido a cada mês da vigência do contrato.
- O cliente será faturado $130 no início (1º de janeiro) de cada um dos três anos do contrato.

#### <a name="steps"></a>Etapas

1. Configure os dois itens liberados como itens não faturados. Use a página **Configuração de receita não faturada** para configurar os itens e as contas que usam receita não faturada.
2. Neste exemplo, a taxa de manutenção é adiada. O item requer um modelo de adiamento, que é configurado na página **Modelos de adiamento**. O modelo tem uma frequência de período **Mensal** e um período de reconhecimento de 36 meses. Consequentemente, a receita por mês é $2,50.
3. Na página **Itens adiados por padrão**, defina o campo **Taxa de manutenção** como **Item adiável**. Esta etapa e a próxima farão com que o item de taxa de manutenção seja adiado quando vendido ou incluído em uma agenda de cobrança.
4. Selecione **Padrões de adiamento** \> **Modelo** e adicione o item para a taxa de manutenção e o modelo linear na etapa 2. O item de taxa de manutenção será vinculado a uma agenda de adiamento de 36 meses.
5. Crie uma agenda de cobrança que inclua os dois itens não faturados. A agenda de cobrança do contrato é configurada com os seguintes itens.

    | Item | Data inicial | Data final | Valor | Frequência de cobrança | Item de adiamento | Receita não faturada | Descrição |
    |---|---|---|---|---|---|---|---|
    | Licença | 1º de janeiro, AT | 31 de dezembro, AT+2 | $100,00 | Anualmente | Número | Sim | O cliente será faturado em $100,00 a cada ano. O total de $300,00 será registrado antecipadamente como receita não faturada no balanço e como receita nos lucros e perdas. Cada fatura reduzirá o valor não faturado. |
    | Manutenção | 1º de janeiro, AT | 31 de dezembro, AT+2 | $30,00 | Anualmente | Sim | Sim | O cliente será faturado em $30,00 a cada ano. O total de $90,00 será registrado antecipadamente como receita não faturada e receita adiada no balanço. Cada fatura reduzirá o valor não faturado. A receita adiada será reconhecida mensalmente durante 36 meses. |

6. Na página **Todas as agendas de cobrança**, use o processo de **criação de entrada de diário** para lançar o valor do contrato no balanço como receita não faturada.

Duas entradas de diário são criadas, uma para cada linha na agenda de cobrança.

| Conta de receita não faturada | Contrapartida de receita não faturada | Valor do débito | Valor de crédito |
|---|---|---|---|
| Conta de receita não faturada | | $300,00 | |
| | Contrapartida de receita não faturada | | $300,00 |

| Conta de receita não faturada | Receita adiada | Valor do débito | Valor de crédito |
|---|---|---|---|
| Conta de receita não faturada | | $90,00 | |
| |Receita de manutenção adiada | | $90,00 |

A primeira entrada de diário é lançada em uma contrapartida de receita não faturada e a segunda é lançada em uma conta de receita adiada. Se a linha de cobrança tiver receita não faturada e receita adiada, a conta de receita adiada será usada, e não a contrapartida de receita não faturada. O contrato requer que a fatura do cliente seja criada no início de cada ano. Use o processo de **geração de fatura** para criar a fatura. Quando a fatura é criada, as seguintes entradas de diário são geradas.

| Conta principal | Conta de receita não faturada | Valor do débito | Valor de crédito |
|---|---|---|---|
| Contrapartida de receita não faturada | | $100,00 | |
| | Conta de receita não faturada | | $100,00 |
| Contas a Receber | | $100,00 | |
| | Conta de receita | | $100,00 |

| Conta principal | Conta de receita não faturada | Valor do débito | Valor de crédito |
|---|---|---|---|
| Conta de receita de manutenção adiada | | $30,00 | |
| | Conta de receita não faturada | | $30,00 |
| Contas a Receber | | $30,00 | |
| | Conta de receita de manutenção adiada | | $30,00 |

Essa mesma entrada de diário será criada por faturas lançadas no início dos dois próximos anos. O valor líquido da conta de receita adiada será 0 (zero), pois não há diferenças de arredondamento ou taxa de câmbio. A receita adiada deve ser revertida exatamente como foi creditada durante o processo de **criação de entrada de diário**. Como a receita ainda é adiada e será reconhecida posteriormente, o crédito na conta de receita adiada ocorrerá novamente.

Na última etapa, a entrada de diário de reconhecimento é criada a cada mês para reconhecer a receita da taxa de manutenção adiada. A entrada de diário pode ser criada usando a página **Processamento de reconhecimento**. Como alternativa, é possível criá-la selecionando **Reconhecer** para as linhas nas páginas **Agenda de adiamento**.

| Conta de receita adiada | Conta de receita | Valor do débito | Valor de crédito |
|---|---|---|---|
| Receita de manutenção adiada | | $2,50 | |
| | Receita de manutenção | | $2,50 |

Esta entrada de diário será criada toda vez que o processo de reconhecimento for executado para esse item adiado (um total de 36 vezes).

#### <a name="short-term-fixed-year"></a>Curto prazo: ano fixo

Você pode usar a receita não faturada com a funcionalidade de curto prazo configurando o campo **Faturado de curto prazo** na página **Parâmetros de cobrança recorrente de contrato**. O exemplo a seguir mostra os cálculos feitos quando a receita não faturada é usada junto com o método não faturado de curto prazo de **Ano fixo**.

Uma agenda de cobrança que tem os seguintes critérios é criada:

- **Data de início:** 1º de junho de 2020
- **Data de término:** 31 de dezembro de 2021
- **Preço unitário:** $100
- **Frequência:** Mensal

Na página **Todas as agendas de cobrança**, a entrada de diário inicial é criada pelo processo de **criação de entrada de diário**. Os valores atuais de curto e longo prazo são calculados da seguinte maneira:

- **Valor de receita não faturada atual de curto prazo**: $700
- **Valor de receita não faturada atual de longo prazo**: $1.200

A fatura é criada para o período de cobrança de 1º de junho até 30 de novembro de 2020. Os valores atuais de curto e longo prazo são calculados da seguinte maneira:

- **Valor de receita não faturada atual de curto prazo**: $100
- **Valor de receita não faturada atual de longo prazo**: $1.200

A fatura é criada para o período de cobrança de 1º de dezembro até 31 de dezembro de 2020. Os valores atuais de curto e longo prazo são calculados da seguinte maneira:

- **Valor de receita não faturada atual de curto prazo**: $1.200
- **Valor de receita não faturada atual de longo prazo**: $0

#### <a name="short-term-rolling-periods"></a>Curto prazo: períodos anteriores

Você pode usar a receita não faturada com a funcionalidade de curto prazo configurando o campo método não faturado de curto prazo na página **Parâmetros de cobrança recorrente de contrato**. O exemplo a seguir mostra os cálculos feitos quando a receita não faturada é usada junto com o método não faturado de curto prazo de **Períodos anteriores**.

Uma agenda de cobrança que tem os seguintes critérios é criada:

- **Data de início:** 1º de junho de 2020
- **Data de término:** 31 de dezembro de 2021
- **Preço unitário:** $100
- **Frequência:** Mensal

Na página **Todas as agendas de cobrança**, a entrada de diário inicial é criada pelo processo de **criação de entrada de diário**. Os valores atuais de curto e longo prazo são calculados da seguinte maneira:

- **Valor de receita não faturada atual de curto prazo**: $1.200
- **Valor de receita não faturada atual de longo prazo**: $700

A fatura é criada para o período de cobrança de 1º de junho até 30 de novembro de 2020. Os valores atuais de curto e longo prazo são calculados da seguinte maneira:

- **Valor de receita não faturada atual de curto prazo**: $1.200
- **Valor de receita não faturada atual de longo prazo**: $100

A fatura é criada para o período de cobrança de 1º de dezembro até 31 de dezembro de 2020. Os valores atuais de curto e longo prazo são calculados da seguinte maneira:

- **Valor de receita não faturada atual de curto prazo**: $1.200
- **Valor de receita não faturada atual de longo prazo**: $0

### <a name="items-with-revenue-allocation"></a>Itens com alocação de receita

Dois itens com frequências de cobrança diferentes são adicionados a uma agenda de cobrança. Ambos usam receita não faturada e são adiáveis.

- **Número de itens 1.000:** Surface Pro 128 GB

    - **Frequência de cobrança:** Única
    - **Preço unitário:** $1.500
    - **Preço de venda autônomo:** $1.600
    - **Receita do contrato:** $1.465,26

- **Número de itens S0021:** seguro vendido junto com o número de item 1.000

    - **Frequência de cobrança:** mensalmente durante 12 meses
    - **Preço unitário:** $20 por mês
    - **Preço de venda autônomo:** $25
    - **Receita do contrato:** $264,74

Como os dois itens usam receita não faturada e alocação de receita, o valor do contrato total na linha de renovação é 0 (zero). A coluna **Receita do contrato** é adicionada e mostra o valor da receita do contrato.

A tabela a seguir mostra a entrada de diário inicial para os itens e a fatura.

| Conta de receita não faturada | Conta de receita adiada | Valor do débito | Valor de crédito |
|---|---|---|---|
| **Entrada de diário item 1.000** | | | |
| Conta de receita não faturada de débito (401250) | | $1.465,26 | |
| | Conta de receita adiada de crédito (250600) | | $1.465,26 |
| **Entrada de diário item 0021** | | | |
| Conta de receita não faturada de débito (401250) | | $274,74 | |
| | Conta de receita adiada de crédito (250600) | | $274,74 |
| **Fatura** | | | |
| | Conta de receita não faturada de crédito | | $1.465,26 |
| | Conta de receita não faturada de crédito | | $274,74 |
| Conta de RA de débito (130100) | | $1.488,16 | |

#### <a name="changes-to-the-billing-schedule-line-billing-detail-line-or-revenue-allocation"></a>Alterações na linha da agenda de cobrança, linha de detalhe de cobrança ou alocação de receita

Quando o preço unitário ou a quantidade é alterada, o valor da receita do contrato para cada item que faz parte da alocação de receita deve ser atualizado. Portanto, a entrada de diário é recalculada.

Por exemplo, o preço unitário do item 1.000 é alterado de $1.500 para $1.600. Nesse caso, o valor da receita do contrato será automaticamente recalculado como $1.549,47. A receita do contrato para o item S0021 é recalculada como $290,53.

Quando a alteração é confirmada, as entradas de diário iniciais para os dois itens são revertidas e novas entradas de diário são criadas:

- **Item 1.000:** a entrada de diário inicial original de $1.465,26 é revertida. Uma nova entrada de diário de $1.549,47 será criada.
- **Item S0021:** a entrada de diário inicial original de $274,74 é revertida. Uma nova entrada de diário de $290,53 será criada.

#### <a name="termination"></a>Finalização

O item S0021 tem uma data de início em janeiro de 2020 e uma data de término em dezembro de 2020, mas é encerrado em junho de 2020. O valor da receita do contrato para ambos os itens deve ser recalculado:

- **Item 1.000:** a receita do contrato é recalculada como $1.567,67.
- **Item S0021:** a receita do contrato é recalculada como $124,00.

Uma entrada de diário de ajuste é criada para a linha que é encerrada. A entrada de diário para a linha que pertence ao mesmo número de organização de vários elementos (MEA) é revertida e uma nova entrada de diário é criada:

- **Item 1.000:** a entrada de diário inicial original de $1.465,26 é revertida. Uma entrada de diário de ajuste de $1.549,47 será criada.
- **Item S0021:** a entrada de diário inicial original de $274,74 é revertida. Uma nova entrada de diário de $124,00 será criada.
