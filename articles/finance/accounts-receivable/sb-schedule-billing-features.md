---
title: Recursos de agenda de cobrança
description: Este tópico explica os recursos das agendas de cobrança, como métodos de precificação, escalonamentos e descontos, datas de alinhamento, rateio, tarifação reversa e grupos de itens divididos.
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
ms.openlocfilehash: 0ce323565a94e8e70d90a65b7a3143e984a1c159
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8700714"
---
# <a name="billing-schedule-features"></a>Recursos de agenda de cobrança

[!include [banner](../includes/banner.md)]

Este tópico explica os recursos de agendas de cobrança e linhas de agenda de cobrança. Ele descreve os diferentes métodos usados para definição de preços, como usar escalonamentos e descontos e como reverter um período de cobrança. Ele também inclui exemplos de cálculos de rateio e grupos de itens divididos.

## <a name="pricing-methods"></a>Métodos de precificação

Você pode usar um dos seguintes métodos de precificação para calcular o preço unitário de um item:

* Nivelado
* Padrão
* Camada
* Camada fixa

### <a name="flat-pricing"></a>Preço fixo

Quando o método de precificação simples é usado, o preço unitário de um item de linha da agenda de cobrança na página **Todas as agendas de cobrança** pode ser editado para qualquer valor que você desejar. O valor de **Preço unitário** é sempre **1**. Portanto, os valores **Preço unitário** e **Valor líquido** de um item são os mesmos.

### <a name="standard-pricing-without-a-trade-agreement"></a>Definição de preços padrão (sem um contrato comercial)

Quando o método de precificação padrão é usado sem um contrato comercial, você configura o preço unitário de um item de linha da agenda de cobrança. Para isso, selecione **Gerenciamento de informações sobre o produto** na página **Detalhes de produtos liberados**. O preço unitário é mostrado na seção **Preço de venda base**. Ele é calculado como *Preço* &divide; *Quantidade de preço*.

### <a name="standard-pricing-with-a-trade-agreement"></a>Definição de preços padrão (com um contrato comercial)

Os exemplos a seguir mostram os cálculos de definição de preços padrão quando há um contrato comercial. Você pode criar contratos comerciais na página **Detalhes de produtos liberados**.

Ambos os exemplos usam um item que tem as seguintes chaves de preço.

| Qtd. de origem | Qtd. de destino | U de M | Preço | Unidade de preço |
|---|---|---|---|---|
| 0 | 100 | Cada | 1,50 | 1 |
| 100 | 200 | Cada | 1.25 | 1 |
| 200 | 999999 | Cada | 1,00 | 1 |

**Exemplo 1**

A quantidade da fatura é 250, e o método de definição de preços padrão é usado. Como a quantidade está no intervalo de quantidade de preço 200 – 999.999, o preço unitário é 1,00. 

O valor líquido é calculado da seguinte maneira:

*Valor líquido* = (*Quantidade* &times; *Preço*) &divide; *Unidade de preço* = (250 &times; 1,00) &divide; 1 = 250

**Exemplo 2**

A quantidade da fatura é 100, e o método de definição de preços padrão é usado. Como a quantidade da fatura está no intervalo de quantidade de preço 0 – 100, o preço unitário é 1,50.

> [!NOTE]
> A quantidade da fatura está no intervalo de 0 a 100, e não no intervalo de 100 – 200 porque, no comportamento de correspondente de quantidade padrão, uma quantidade é correspondente se for *mais que ou igual* à quantidade "de" e *menor que* a quantidade "para".

O valor líquido é calculado da seguinte maneira:

*Valor líquido* = (100 &times; 1,50) &divide; 1 = 150

### <a name="tier-pricing"></a>Tipo de preço

No exemplo a seguir, um item tem as seguintes chaves de preço.

| Qtd. de origem | Qtd. de destino | U de M | Preço | Unidade de preço |
|---|---|---|---|---|
| 0 | 100 | Cada | 1,50 | 10 |
| 100 | 200 | Cada | 1.25 | 10 |
| 200 | 999999 | Cada | 1,00 | 10 |

Se a quantidade da fatura for 250 e o método de definição de preços da camada for usado, os preços dos itens serão calculados da seguinte maneira, com base nas chaves de preço:

- **Primeiros 100 itens:** 100 &times; 1,50 = 150,00
- **Segundos 100 itens:** 100 &times; 1,25 = 125,00
- **Itens restantes:** 50 &times; 1,00 = 50,00

O valor líquido é calculado da seguinte maneira:

*Valor líquido* = (150,00 &divide; 10) + (125,00 &divide; 10) + (50,00 &divide; 10) = 15,00 + 12,50 + 5,00 = 32,50

Depois que o valor líquido é calculado, o preço unitário é calculado pela divisão do valor líquido pela quantidade:

*Preço unitário* = 32,50 &divide; 250 = 0,13

### <a name="flat-tier-pricing"></a>Tipo de preço fixo

No exemplo a seguir, um item tem as seguintes chaves de preço.

| Qtd. de origem | Qtd. de destino | U de M | Valor de camada fixa | Unidade de preço |
|---|---|---|---|---|
| 0 | 50 | Cada | 100.00 | 50 |
| 50 | 200 | Cada | 150,00 | 200 |

A tabela a seguir mostra as faturas e os preços unitários para as diferentes quantidades compradas. O valor líquido é calculado primeiro e, depois, o preço unitário é calculado.

| Fatura | Quantidade comprada | Preço unitário | Valor líquido |
|---|---|---|---|
| 1 | 25 | 2,00 &divide; 25 = 0,08 | 100 &divide; 50 = 2,00 |
| 2 | 20 | 2,00 &divide; 20 = 0,10 | 100 &divide; 50 = 2,00 |
| 3 | 50 | 2,00 &divide; 50 = 0,04 | 100 &divide; 50 = 2,00 |
| 4 | 60 | 0,75 &divide; 60 = 0,0125 = 0,01 | 150 &divide; 200 = 0,75 |

## <a name="escalations-and-discounts"></a>Escalonamentos e descontos

Um *escalonamento* é um aumento de preço para um período de cobrança futuro para o qual a fatura ainda não foi criada. Um *desconto* é uma redução de preço para um período de cobrança futuro para o qual a fatura ainda não foi criada.

Na cobrança de assinatura, os escalonamentos e os descontos não podem ser aplicados retroativamente a uma agenda de cobrança. Por exemplo, não é possível aplicar um escalonamento a uma agenda de cobrança três meses no passado e processá-lo. Em outras palavras, não é possível aplicar um aumento de preço que ocorreu três meses atrás.

Você pode aplicar um escalonamento ou um desconto a uma agenda de cobrança ou uma linha de agenda de cobrança em um dos seguintes locais:

- A página de listagem **Todas/Agendas de cobrança ativas**
- Uma agenda de cobrança específica
- Uma linha de agenda de cobrança específica

### <a name="apply-an-escalation-or-discount"></a>Aplicar escalonamento ou desconto

Para aplicar um escalonamento ou um desconto a uma agenda de cobrança, siga estas etapas.

1. Selecione uma agenda de cobrança ou uma linha de agenda de cobrança.
2. Selecione **Escalonamento e desconto** na guia **Escalonamento e desconto** ou na linha da agenda de cobrança.
3. Se um índice de preço de consumidor for usado para calcular o escalonamento ou o desconto, selecione um valor no campo **cálculo de índice de preço de consumo**.
4. Selecione **Novo** para adicionar um escalonamento ou uma linha de desconto.
5. Para um desconto, marque a caixa de seleção **Desconto**. Para um escalonamento, deixe a caixa de seleção **Desconto** desmarcada.
6. Defina os campos **Data de início** e **Frequência**.
7. Para itens de adiamento que usam o recurso receita não cobrada, defina o campo **Data de término**.
8. Defina o campo **Porcentagem**, **Valor** ou **Agenda de índice de preço de consumo**.
9. Defina o campo **Data de término**.
10. Selecione **OK**.
11. Repita as etapas 4 a 10 para cada linha adicional de escalonamento ou desconto que você precisar.

### <a name="fields-on-the-billing-schedule-lines-page"></a>Campos na página Linhas da agenda de cobrança

A página **Linhas da agenda de cobrança** contém os campos a seguir.

| Campo | Descrição |
|---|---|
| Número do item | O número de item da linha da agenda de cobrança. Este campo está disponível somente quando a página é aberta de um item de linha da agenda de cobrança. |
| Cálculo de índice de preços ao consumidor | <p>Selecione o método usado para calcular o escalonamento do índice de preço de consumo:</p><ul><li>**Índice de preço de consumo anterior**: use o valor anterior do índice de preço de consumo para o cálculo de escalonamento.</li><li>**Índice de preço de consumo base**: use o valor base do índice de preço de consumo para o cálculo de escalonamento.</li></ul> |
| Grade **Linha** | |
| Desconto | <p>Defina a caixa de seleção para especificar se a alteração no valor é um escalonamento ou um desconto:</p><ul><li>**Marcada**: a alteração aplica um desconto à linha da agenda de cobrança ou da agenda de cobrança.</li><li>**Desmarcada**: a alteração aplica um escalonamento a uma agenda de cobrança ou a uma linha de agenda.</li></ul><p>A configuração dessa caixa de seleção não pode ser alterada para itens que usam o recurso de receita não cobrada. Além disso, não é possível aplicar descontos a itens que usam divisão de receita.</p> |
| Data de início | Selecione a data de início do escalonamento ou do desconto. |
| Frequência | Selecione a frequência do escalonamento ou do desconto: **Nenhuma**, **Mensal**, **Trimestral**, **Semianual** ou **Anual**. |
| Porcentagem | Especifique a porcentagem do escalonamento ou do desconto. |
| Valor | Especifique o valor do escalonamento ou do desconto. |
| Agenda de índice de preços ao consumidor | Selecione a agenda de índice de preço de consumo usada para os cálculos. |
| Data final | <p>Selecione a data de término do escalonamento ou do desconto.</p><p>**Observação:** este campo é obrigatório para itens que usam o recurso de receita não cobrada.</p> |
| Número da agenda de adiamento | <p>O número da agenda de adiamento.</p><p>Este campo está disponível somente quando a página é aberta de uma linha da agenda de cobrança.</p> |
| Número do lote do diário | <p>Número do lote do diário.</p><p>Este campo está disponível somente quando a página é aberta de uma linha da agenda de cobrança.</p> |
| Valor do Desconto Total | <p>A soma dos valores de desconto para todas as linhas da grade.</p><p>Este campo está disponível somente quando a página é aberta de uma linha da agenda de cobrança.</p> |
| Valor de receita não cobrada atual de curto prazo | <p>O valor de receita não cobrada atual de curto prazo.</p><p>Esse valor é exibido quando um método de adiamento de curto prazo é selecionado na página **Parâmetros de cobrança de contratos recorrentes** e as contas do item de linha são configuradas na página **Configuração de receita não cobrada**.</p> |
| Valor de receita não cobrada atual de longo prazo | <p>O valor de receita não cobrada atual de longo prazo.</p><p>Esse valor é exibido quando um método de adiamento de curto prazo é selecionado na página **Parâmetros de cobrança de contratos recorrentes** e as contas do item de linha são configuradas na página **Configuração de receita não cobrada**.</p> |

## <a name="proration-examples"></a>Exemplos de rateio

Os cálculos de rateio podem ser baseados no número de dias ou de meses. O método usado para o cálculo do rateio é definido na página **Parâmetros de cobrança recorrente de contrato**. O método de rateio afeta como os valores são calculados para uma agenda de cobrança nas seguintes situações:

- Criação inicial
- Aplicativo de um escalonamento ou desconto
- Finalização
- Posicionamento ou remoção de uma retenção
- Adição de suporte ou renovação

O método de rateio também afeta os cálculos no relatório mensal recorrente de receita (MRR).

### <a name="example-1"></a>Exemplo 1

O valor anual de uma agenda de cobrança é US$ 5.000. A data de início é 12 de agosto de 2019, e a data de término é 22 de dezembro de 2019. A frequência de cobrança é anual. O valor rateado é calculado das seguintes maneiras, dependendo do método de cálculo diário ou mensal ser usado:

- **Diário**

    - *Número de dias* = *Data de término* – *Data de início* + 1 = 133 dias
    - *Número de dias no ano* = 11 de agosto de 2020 – 12 de agosto de 2019 + 1 = 366 dias
    - *Valor rateado* = 5.000 &times; (133 &divide; 366) = 1816,94

- **Mensalmente**

    - *Parte inicial do mês* = (31 – 12 + 1) &divide; 31 = 20 &divide; 31
    - *Meses do meio* = 3
    - *Parte final do mês* = 22 &divide; 31
    - Valor rateado = 5.000 &divide; 12 &times; \[(20 &divide; 31) + 3 + (22 &divide; 31)\] = 1814,52

### <a name="example-2"></a>Exemplo 2

O valor anual de uma agenda de cobrança é US$ 12.000. A data de início é 1 de agosto de 2019, e a data de término é 31 de dezembro de 2019. A frequência de cobrança é anual. O valor rateado é calculado das seguintes maneiras, dependendo do método de cálculo:

- **Diário**

    - *Número de dias* = *Data de término* – *Data de início* + 1 = 153 dias
    - *Número de dias no ano* = 31 de julho de 2020 – 1 de agosto de 2019 + 1 = 366 dias
    - *Valor rateado* = 12.000 &times; (153 &divide; 366) = 5016,39

- **Mensal (mês inteiro)**

    - *Número de meses* = 5
    - *Total de meses* = 12
    - *Valor rateado* = (12.000 &times; 5) &divide; 12 = 5.000

## <a name="reversing-a-period-billing"></a>Revertendo uma cobrança de período

Neste exemplo, uma agenda de cobrança tem apenas uma linha:

- A cobrança é feita mensalmente por 12 meses, de janeiro a dezembro.
- As faturas foram criadas para todos os períodos até abril.

Você deseja reverter a fatura para o período de faturamento de abril.

Se uma fatura de venda ainda não tiver sido criada para o período de cobrança de abril, você poderá excluir a ordem de venda. Nesse caso, o status **Cobrado** para o detalhe será removido. No entanto, como uma fatura foi criada para o período de cobrança, o status **Cobrado** para o detalhe não poderá ser apagado. Portanto, para reverter a cobrança de abril, você deve criar uma nota de crédito de compensação para a linha.

1. Na página **Todas as agendas de cobrança**, crie uma linha de agenda para o mesmo item.
2. Altere o valor de **Quantidade** do item para o negativo da quantidade original.
3. Defina o campo **Frequência da cobrança** como **Uma vez**.
4. Atualize as datas de início e término para que correspondam às datas de linha de detalhe de cobrança para as quais você deseja criar uma nota de crédito. Para este exemplo, defina a data de início como 1º de abril de 2019 e a data de término como 30 de abril de 2019.
5. Salve as alterações.
6. Abra a página **Gerar fatura** e crie a ordem de venda que contém a nota de crédito para o período especificado.
7. Opcional: envie a fatura.

Ao analisar as linhas da agenda de cobrança, você notará que a nova linha tem um link para a nota de crédito. A linha original ainda terá um link para a fatura de abril original.

## <a name="split-item-group-examples"></a>Exemplos de grupos de itens divididos

Para esse exemplo, a seguinte configuração está em vigor:

- Na página **Parâmetros de cobrança recorrente de contrato**, a opção **Dividir por grupo de itens** está selecionada, e o campo **Tipo de agenda única** é definido como **Cliente**.
- Três grupos de itens foram criados: **PREFIX**, **DATAHUB** e **SPP**.
- O cliente US-001 tem várias agendas de cobrança nas quais o grupo de itens é prefixo ou DATAHUB.
- O cliente US-002 tem várias agendas de cobrança nas quais o grupo de itens é prefixo ou SPP.

| Número de agenda de cobrança | Cliente | Grupo de itens |
|---|---|---|
| SCH001 | US-001 | PREFIX |
| SCH002 | US-001 | DATAHUB |
| SCH003 | US-002 | PREFIX |
| SCH004 | US-002 | SPP |

O cliente US-001 compra um item de renovação que pertence ao grupo de itens PREFIX. Essa transação é uma nova ordem de venda.

| Nº da ordem de venda | Cliente | Item principal | Item de renovação | Grupo de itens de renovação | Número de agenda de cobrança |
|---|---|---|---|---|---|
| SO0001 | US-001 | D0001 | D0002 | PREFIX | SCH001 |

Quando a fatura da ordem de venda é lançada, o item de renovação é adicionado ao plano de cobrança existente (SCH001) do cliente. Esta agenda de cobrança usa o grupo de itens PREFIX. Todos os itens de renovação que pertencem ao mesmo grupo de itens são colocados na mesma agenda de cobrança.

**Cabeçalho**
 
| Número de agenda de cobrança | Cliente | Grupo de itens |
|---|---|---| 
| SCH001 | US-001 | PREFIX |

**Linha**

| Número de agenda de cobrança | Cliente | Grupo de itens |
|---|---|---|
| SCH001 | US-001 | D0002 |

O cliente US-001 agora compra um item de renovação que pertence ao grupo de itens SPP. Essa transação é uma nova ordem de venda.

| Nº da ordem de venda | Cliente | Item principal | Item de renovação | Grupo de itens de renovação | Número de agenda de cobrança |
|---|---|---|---|---|---|
| SO0002 | US-001 | D0003 | D0004 | SPP | |

No momento, o cliente US-001 não tem uma agenda de cobrança que usa o grupo de itens SPP. Portanto, uma nova agenda de cobrança é criada.

**Cabeçalho**

| Número de agenda de cobrança| Cliente | Grupo de itens |
|---|---|---|
| SCH005 | US-001 | SPP |

**Linha**

| Número de agenda de cobrança | Cliente | Grupo de itens |
|---|---|---|
| SCH005 | US-001 | D0004 |

### <a name="multiple-billing-schedules-for-the-same-end-user-and-customer"></a>Várias agendas de cobrança para o mesmo usuário final e cliente

Para esse exemplo, a seguinte configuração está em vigor:

- Na página **Parâmetros de cobrança recorrente de contrato**, a opção **Dividir por grupo de itens** está selecionada, e o campo **Tipo de agenda única** é definido como **Usuário final**.
- Na página **Usuários finais**, a seguinte relação cliente e usuário final é configurada.

    | Conta do cliente | Conta de usuário final |
    |---|---|
    | US-001 | US-221 |

Várias agendas de cobrança são criadas para a mesma combinação de cliente e usuário final e cliente. Como a opção **Dividir por grupo de itens** está selecionada na página **Parâmetros de cobrança recorrente de contrato**, várias agendas de cobrança podem ser criadas para o mesmo cliente e para o relacionamento de usuário final.

| Número de agenda de cobrança | Cliente | Conta de usuário final | Grupo de itens de cabeçalho |
|---|---|---|---|
| SCH005 | US-001 | US-221 | IG1 |
| SCH006 | US-001 | US-221 | IG2 |
| SCH007 | US-001 | US-221 | IG3 |

Na página **Configuração de item**, você pode criar relacionamentos de itens de suporte e renovação.

| Código do item | Relação de item | Item de suporte | Item de renovação | Grupo de itens de renovação |
|---|---|---|---|---|
| Tabela | D001 | ITEM27 | D007 | IG1 |
| Tabela | D002 | ITEM28 | D005 | IG2 |
| Tabela | D003 | ITEM29 | D006 | IG3 |

Agora você pode criar uma ordem de venda para o cliente US-001. Essa ordem de venda tem itens da página **Configuração do item**. Ao criar a ordem de venda, abra a página **Processo de suporte e renovação** e defina o campo **Conta do usuário final** e quaisquer outras informações necessárias para o item de renovação.

Quando a fatura da transação é criada e lançada, diferentes agendas de cobrança são criadas para a combinação de cliente/usuário final e grupo de itens. Mais de uma linha na mesma ordem de venda pode ser atribuída à mesma agenda de cobrança.

| Nº da ordem de venda | Cliente | Conta de usuário final | Item principal | Item de suporte | Item de renovação | Número de agenda de cobrança |
|---|---|---|---|---|---|---|
| SO0001 | US-001 | US-221 | D001 | ITEM27 | D007 | SCH005 |
| SO0001 | US-001 | US-221 | D002 | ITEM28 | D005 | SCH006 |
| SO0001 | US-001 | US-221 | D003 | ITEM29 | D006 | SCH005 |
