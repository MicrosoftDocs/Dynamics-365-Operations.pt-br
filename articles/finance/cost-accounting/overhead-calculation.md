---
title: Cálculo de custos indiretos
description: Este tópico descreve processos comuns para calcular e alocar os custos gerais indiretos.
author: AndersGirke
manager: AnnBe
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMActualVersion, CAMBudgetVersion, CAMOverheadCalculation, CAMOverheadRateCalculationJournalEntry, CAMFormulaAllocationBase
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 272163
ms.assetid: 93119afb-47ed-4786-ba44-ba93576d3e28
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 923e6e38a664e17ec3349d839c4b77ec903c5dc2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440461"
---
# <a name="overhead-calculation"></a>Cálculo de custos indiretos

[!include [banner](../includes/banner.md)]

Este tópico descreve processos comuns para calcular e alocar os custos gerais indiretos.

<a name="term-definition"></a>Definição de termo
---------------

Os custos gerais indiretos são aqueles que foram incorridos para realizar um negócio, mas não podem ser diretamente atribuídos a qualquer atividade comercial, produto ou serviço específico. Os custos gerais indiretos fornecem suporte crítico para geração de atividades produtivas. Eis alguns exemplos de custos gerais:

-   Aluguel
-   eletricidade
-   Salários administrativos

## <a name="overhead-calculation-overview"></a>Visão geral do cálculo de custos gerais indiretos
O cálculo de custos gerais indiretos executa as políticas de contabilização de custos na ordem correta. Você pode executar o cálculo de custos gerais indiretos várias vezes para o mesmo período fiscal, se as políticas de contabilidade de custo foram modificadas ou foram detectados erros específicos. Cada execução do cálculo de custos gerais indiretos é armazenada e recebe um ID exclusivo de versão que permite comparar os cálculos em várias versões. As entradas de custo que o cálculo de custos indiretos gera recebe uma data contábil. Essa data contábil corresponde à data final do período fiscal que é usada no cálculo. A ID exclusiva de versão consiste nos seguintes elementos:

-   Tipo de versão
-   Data e hora
-   Razão de contabilização de custos
-   Ano fiscal
-   Período fiscal

O cálculo de custos gerais indiretos é executado independentemente da versão. Portanto, você pode calcular a versão de orçamento antes da versão atual. O cálculo de custos gerais indiretos consiste em quatro etapas, conforme mostrado na ilustração. Em cada etapa, um cabeçalho de diário é criado com entradas de diário. Esse cabeçalho de diário mantém dados de entrada para cada etapa de cálculo. As políticas e regras são aplicadas a cada linha do diário e as entradas de custo são geradas como saídas. Portanto, você sempre terá rastreabilidade total. 

[![Cálculo de custos gerais indiretos](./media/period-cost-calculation.png)](./media/period-cost-calculation.png)

## <a name="calculate-and-allocate-the-electricity-overhead-cost"></a>Calcular e alocar os custos gerais indiretos de Eletricidade
Na contabilidade financeira, alguns custos, como eletricidade, são registrados como um valor total. Portanto, a visão administrativa detalhada não é fornecida para a contabilização de custo. Na contabilização de custo, para fornecer a visão administrativa correta em todas as unidades organizacionais e níveis, os custos devem passar pelas unidades organizacionais. Este fluxo deve ser baseado em qualquer um registro exato do consumo ou de uma previsão justa. Na contabilidade, um custo de eletricidade pode ser lançado, conforme mostrado na tabela.

<table>
<thead>
<tr>
<th>Data contábil</th>
<th colspan="2">Centro de custos</th>
<th colspan="2">Conta principal</th>
<th>Valor na moeda contábil</th>
</tr>
</thead>
<tbody>
<tr>
<td>3 de janeiro, 2017</td>
<td>CC099</td>
<td>Centro de custos padrão</td>
<td>10001</td>
<td>eletricidade</td>
<td>10,000.00</td>
</tr>
</tbody>
</table>

### <a name="step-1-process-the-cost-behavior-calculation"></a>Etapa 1: Processar o cálculo do comportamento de custo

Por padrão, quando as entradas de custo previsto são importadas de dados de origem, elas recebem a classificação de comportamento de custo **Não classificado** na Contabilidade de custos. Aplicando regras da política de comportamento de custo, é possível reclassificar entradas de custo como **Custo fixo** ou **Custo variável**.

#### <a name="define-the-cost-behavior-rule"></a>Definir a regra de custo de comportamento

Em alguns casos, parte do custo é uma taxa fixa e o custos pendente é baseado no consumo. Geralmente, as contas de eletricidade correspondem a esta definição. Após você pagar uma taxa fixa específica, você paga por consumo, por hora de quilowatt (Kwh). Por exemplo, se a taxa de custo fixa for 1.000.00, veja aqui como a regra de comportamento de custo é definida:

-   Valor fixo 1.000,00
    -   0 &lt;= 1.000,00 = Fixo
    -   1000.01 &lt; N = Variável

##### <a name="journal"></a>Diário

<table>
<thead>
<tr>
<th>Diário</th>
<th>Tipo de diário</th>
<th colspan="3">Período do calendário fiscal</th>
<th>Versão</th>
</tr>
</thead>
<tbody>
<tr>
<td>00001</td>
<td>Diário de cálculo do comportamento de custo</td>
<td>fiscal</td>
<td>2017</td>
<td>Período 1</td>
<td>Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>Entradas de diário (entradas de diário do saldo de objeto de custo)

<table>
<thead>
<tr>
<th>Data contábil</th>
<th colspan="2">Objeto de custo</th>
<th colspan="2">Elemento de custo</th>
<th>Comportamento de custo</th>
<th>Valor</th>
</tr>
</thead>
<tbody>
<tr>
<td>3 de janeiro, 2017</td>
<td>CC099</td>
<td>Centro de custos padrão</td>
<td>10001</td>
<td>eletricidade</td>
<td>Não classificado</td>
<td>10,000.00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Entradas de custo

<table>
<thead>
<tr>
<th colspan="2">Objeto de custo</th>
<th colspan="2">Elemento de custo</th>
<th>Comportamento de custo</th>
<th>Valor</th>
<th>Data contábil</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC099</td>
<td>Centro de custos padrão</td>
<td>10001</td>
<td>eletricidade</td>
<td>Não classificado</td>
<td>10,000.00</td>
<td>3 de janeiro, 2017</td>
</tr>
<tr>
<td>CC099</td>
<td>Centro de custos padrão</td>
<td>10001</td>
<td>eletricidade</td>
<td>Não classificado</td>
<td>-10.000,00</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC099</td>
<td>Centro de custos padrão</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo fixo</td>
<td>1.000,00</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC099</td>
<td>Centro de custos padrão</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>9,000.00</td>
<td>31 de janeiro, 2017</td>
</tr>
</tbody>
</table>

Para obter mais informações, consulte [Criar e atribuir uma política de comportamento de custos a uma unidade de controle de custos](tasks/create-assign-cost-behavior-policy-cost-control-unit.md)
### <a name="step-2-process-the-cost-distribution-calculation"></a>Etapa 2: Processar o cálculo de distribuição de custo

A distribuição de custos é usada para redistribuir custo de um objeto de custo a um ou mais outros objetos de custo, aplicando uma base de alocação relevante. A distribuição de custos e a alocação de custo são diferentes na distribuição de custos, sempre que ocorrer em nível de elemento de custo principal do custo original.

#### <a name="define-the-cost-distribution-rule"></a>Definir a regra de distribuição de custos

Na contabilidade financeira, os custos de eletricidade geralmente são registrados como um valor total. Na contabilização de custo, esta abordagem não é suficientemente detalhada. O custo variável deve ser distribuído a objetos de custos individuais com base justa. A base de alocação mais lógica é o consumo de eletricidade (Kwh). O membro da dimensão estatística que é chamado Eletricidade é criado e o consumo de eletricidade é registrado. Por padrão, todos os membros estatísticos da dimensão se tornam disponíveis como bases de alocação.

<table>
<thead>
<tr>
<th colspan="2">Objeto de custo</th>
<th>Kwh</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>RH</td>
<td>1.000</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanças</td>
<td>6,000</td>
</tr>
<tr>
<td>CC003</td>
<td>Montagem</td>
<td>0</td>
</tr>
</tbody>
</table>

A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação para custos variáveis.

<table>
<thead>
<tr>
<th colspan="2">Objeto de custo</th>
<th>Magnitude</th>
<th>Fator de alocação</th>
<th>Valor</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>RH</td>
<td>1.000</td>
<td>(1.000 ÷ 7.000) × 9.000,00</td>
<td>1,285.71</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanças</td>
<td>6,000</td>
<td>(6.000 ÷ 7.000) × 9.000,00</td>
<td>7,714.29</td>
</tr>
<tr>
<td>CC003</td>
<td>Montagem</td>
<td>0</td>
<td>(0 ÷ 7.000) × 9.000,00</td>
<td>0,00</td>
</tr>
</tbody>
</table>

Os custos fixos devem ser distribuídos igualmente a objetos de custo individuais que têm a eletricidade consumida. Você pode obter esse resultado usando o membro estatístico de dimensão de eletricidade em uma base e alocação da fórmula: (Eletricidade &gt; 0,00) A tabela a seguir mostra o resultado quando o consumo de eletricidade é aplicado como uma base de alocação de custos variáveis.

<table>
<thead>
<tr>
<th colspan="2">Objeto de custo</th>
<th>Fórmula</th>
<th>Magnitude</th>
<th>Fator de alocação</th>
<th>Valor</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>RH</td>
<td>(1.000 &gt; 0,00)</td>
<td>1</td>
<td>(1 ÷ 2) × 1.000,00</td>
<td>500,00</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanças</td>
<td>(6.000 &gt; 0,00)</td>
<td>1</td>
<td>(1 ÷ 2) × 1.000,00</td>
<td>500,00</td>
</tr>
<tr>
<td>CC003</td>
<td>Montagem</td>
<td>(0 &gt; 0,00)</td>
<td>0</td>
<td>(0 ÷ 2) × 1.000,00</td>
<td>0,00</td>
</tr>
</tbody>
</table>

##### <a name="journal"></a>Diário

<table>
<thead>
<tr>
<th>Diário</th>
<th>Tipo de diário</th>
<th colspan="3">Período do calendário fiscal</th>
<th>Versão</th>
</tr>
</thead>
<tbody>
<tr>
<td>00002</td>
<td>Diário de cálculo de distribuição de custo</td>
<td>fiscal</td>
<td>2017</td>
<td>Período 1</td>
<td>Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>Entradas de diário (entradas de diário do saldo de objeto de custo)

<table>
<thead>
<tr>
<th>Data contábil</th>
<th colspan="2">Objeto de custo</th>
<th colspan="2">Elemento de custo</th>
<th>Comportamento de custo</th>
<th>Valor</th>
</tr>
</thead>
<tbody>
<tr>
<td>31 de janeiro, 2017</td>
<td>CC099</td>
<td>Centro de custos padrão</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo fixo</td>
<td>1.000,00</td>
</tr>
<tr>
<td>31 de janeiro, 2017</td>
<td>CC099</td>
<td>Centro de custos padrão</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>9,000.00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Entradas de custo

<table>
<thead>
<tr>
<th colspan="2">Objeto de custo</th>
<th colspan="2">Elemento de custo</th>
<th>Comportamento de custo</th>
<th>Valor</th>
<th>Data contábil</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC099</td>
<td>Centro de custos padrão</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo fixo</td>
<td>-1.000,00</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC001</td>
<td>RH</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo fixo</td>
<td>500,00</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanças</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo fixo</td>
<td>500,00</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC099</td>
<td>Centro de custos padrão</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>-9.000,00</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC001</td>
<td>RH</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>1,285.71</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanças</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>7,714.29</td>
<td>31 de janeiro, 2017</td>
</tr>
</tbody>
</table>

Para obter mais informações, consulte [Criar e atribuir uma política de distribuição de custos a uma unidade de controle de custos](tasks/create-assign-cost-distribution-policy-cost-control-unit.md) 

### <a name="step-3-process-the-overhead-rate-calculation"></a>Etapa 3: Processar o cálculo de taxa de custos indiretos

A taxa de custos indiretos é usada para cobrar um ou mais objetos de custos específicos. O encargo se baseia em uma taxa de custo predeterminada e a magnitude da básica de alocação atribuída. 

#### <a name="define-the-overhead-rate"></a>Defina a taxa de custos indiretos

O objeto de custo CC001 HR contribui para um conjunto de projetos internos. Um membro de dimensão estatística que é chamado de projetos de RH foi criado para medir a magnitude consumida.

<table>
<thead>
<tr>
<th colspan="2">Objeto de custo</th>
<th>Horas</th>
</tr>
</thead>
<tbody>
<tr>
<td>Proj. 1</td>
<td>Projeto 1</td>
<td>3</td>
</tr>
<tr>
<td>Proj. 2</td>
<td>Projeto 2</td>
<td>1</td>
</tr>
</tbody>
</table>

Uma taxa de custo predeterminada da contribuição de projetos de custo foi definida.

<table>
<thead>
<tr>
<th colspan="2">Objeto de custo</th>
<th>Elemento de custo</th>
<th>Comportamento de custo</th>
<th>Unidades</th>
<th>Taxa</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>RH</td>
<td>10001</td>
<td>Custo variável</td>
<td>1</td>
<td>10</td>
</tr>
</tbody>
</table>

A tabela a seguir mostra o resultado quando projetos de RH são aplicados como base de alocação.

<table>
<thead>
<tr>
<th colspan="2">Objeto de custo</th>
<th>Magnitude</th>
<th>Elemento de custo</th>
<th>Fator de alocação</th>
<th>Valor</th>
</tr>
</thead>
<tbody>
<tr>
<td>Proj. 1</td>
<td>Projeto 1</td>
<td>3</td>
<td>10001</td>
<td>(3 ÷ 1) × 10,00</td>
<td>30,00</td>
</tr>
<tr>
<td>Proj. 2</td>
<td>Projeto 2</td>
<td>1</td>
<td>10001</td>
<td>(1 ÷ 1) × 10,00</td>
<td>10,00</td>
</tr>
</tbody>
</table>

##### <a name="journal"></a>Diário

<table>
<thead>
<tr>
<th>Diário</th>
<th>Tipo de diário</th>
<th colspan="3">Período do calendário fiscal</th>
<th>Versão</th>
</tr>
</thead>
<tbody>
<tr>
<td>00003</td>
<td>Diário de cálculo de taxa de custos indiretos</td>
<td>fiscal</td>
<td>2017</td>
<td>Período 1</td>
<td>Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-journal-entries-for-overhead-rate-calculation"></a>Entradas de diário (As entradas de diário para cálculo da taxa de custos indiretos)

<table>
<thead>
<tr>
<th>Data contábil</th>
<th colspan="2">Objeto de custo</th>
<th>Magnitude</th>
</tr>
</thead>
<tbody>
<tr>
<td>31 de janeiro, 2017</td>
<td>Proj. 1</td>
<td>Projeto interno 1</td>
<td>3,00</td>
</tr>
<tr>
<td>31 de janeiro, 2017</td>
<td>Proj. 2</td>
<td>Projeto interno 2</td>
<td>1.00</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Entradas de custo

<table>
<thead>
<tr>
<th colspan="2">Objeto de custo</th>
<th colspan="2">Elemento de custo</th>
<th>Comportamento de custo</th>
<th>Valor</th>
<th>Data contábil</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC0001</td>
<td>RH</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>-30,00</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>Proj. 1</td>
<td>Projeto interno 1</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>30,00</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC001</td>
<td>RH</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>-10,00</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>Proj. 2</td>
<td>Projeto interno 2</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>10,00</td>
<td>31 de janeiro, 2017</td>
</tr>
</tbody>
</table>

Para obter mais informações, consulte [Realizar cálculo de custos indiretos](cost-rollup.md#perform-overhead-calculation).

### <a name="step-4-process-the-cost-allocation-calculation"></a>Etapa 4: Processar o cálculo de alocação de custo

A alocação é usada para alocar o saldo de um objeto de custo a outros objetos de custo pela aplicação de uma base de alocação. O Finance oferece suporte ao método de alocação recíproco. No método de alocação recíproco, os serviços mútuos que os objetos de custo auxiliar trocam são totalmente reconhecidos. O sistema determina automaticamente a ordem correta realizar as alocações. O saldo de um objeto de custo é alocado por uma base de alocação única. As alocações entre as dimensões de objetos de custo e os respectivos membros são suportadas. A ordem de alocação é controlada pela unidade de controle de custo. 

[![Método recíproco](./media/reciprocal-method.png)](./media/reciprocal-method.png)

#### <a name="define-the-cost-allocation"></a>Defina a alocação de custo

Aqui está um exemplo simples que explica como você pode rastrear o fluxo de custo. O objeto de custo previsto CC001 HR contribui a vários objetos de custo previsto. Um membro de dimensão estatística que é chamado de serviços de RH foi criado para medir a magnitude consumida.

<table>
<thead>
<tr>
<th colspan="2">Objeto de custo</th>
<th>Serviços de RH</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC002</td>
<td>Finanças</td>
<td>35</td>
</tr>
<tr>
<td>CC003</td>
<td>Montagem</td>
<td>55</td>
</tr>
<tr>
<td>CC004</td>
<td>Embalagem</td>
<td>10</td>
</tr>
</tbody>
</table>

O objeto de custo CC002 Finanças contribui para vários objetos de custo. Um membro de dimensão estatística que é chamado de serviços de Finanças foi criado para medir a magnitude consumida.

<table>
<thead>
<tr>
<th colspan="2">Objeto de custo</th>
<th>Serviços financeiros</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC003</td>
<td>Montagem</td>
<td>65</td>
</tr>
<tr>
<td>CC004</td>
<td>Embalagem</td>
<td>35</td>
</tr>
</tbody>
</table>

O objeto de custo CC003 Montagem contribui para vários objetos de custo. Um membro de dimensão estatística que é chamado de serviços de Montagem foi criado para medir a magnitude consumida.

<table>
<thead>
<tr>
<th colspan="2">Objeto de custo</th>
<th>Serviços de montagem (horas)</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod. 1</td>
<td>Produto 1</td>
<td>60</td>
</tr>
<tr>
<td>Prod. 2</td>
<td>Produto 2</td>
<td>20</td>
</tr>
</tbody>
</table>

O objeto de custo CC004 Embalagem contribui para vários objetos de custo. Um membro de dimensão estatística que é chamado de serviços de Embalagem foi criado para medir a magnitude consumida.

<table>
<thead>
<tr>
<th colspan="2">Objeto de custo</th>
<th>Serviços de embalagem (horas)</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod. 1</td>
<td>Produto 1</td>
<td>80</td>
</tr>
<tr>
<td>Prod. 2</td>
<td>Produto 2</td>
<td>15</td>
</tr>
</tbody>
</table>

> [!NOTE]
> Medidas estatísticas, como as horas de produção que um produto consome, podem ser derivadas dos dados de origem. Para obter mais informações, consulte [Modelo de provedor de medidas estatísticas](statistical-measure-provider-template.md#statistical-measure-provider-template). A tabela a seguir mostra o resultado quando os serviços de RH são aplicados como base de alocação para custos totais (custos fixos e custos variáveis.)

<table>
<thead>
<tr>
<th colspan="2">Objeto de custo</th>
<th>Magnitude</th>
<th>Fator de alocação</th>
<th>Valor</th>
<th>Comportamento de custo</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC002</td>
<td>Finanças</td>
<td>35</td>
<td>(35 ÷ 100) × 500,00</td>
<td>175.00</td>
<td>Custo fixo</td>
</tr>
<tr>
<td>CC003</td>
<td>Montagem</td>
<td>55</td>
<td>(55 ÷ 100) × 500,00</td>
<td>275.00</td>
<td>Custo fixo</td>
</tr>
<tr>
<td>CC004</td>
<td>Embalagem</td>
<td>10</td>
<td>(10 ÷ 100) × 500,00</td>
<td>50,00</td>
<td>Custo fixo</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanças</td>
<td>35</td>
<td>(35 ÷ 100) × 1.245,71</td>
<td>436.00</td>
<td>Custo variável</td>
</tr>
<tr>
<td>CC003</td>
<td>Montagem</td>
<td>55</td>
<td>(55 ÷ 100) × 1.245,71</td>
<td>685.14</td>
<td>Custo variável</td>
</tr>
<tr>
<td>CC004</td>
<td>Embalagem</td>
<td>10</td>
<td>(10 ÷ 100) × 1.245,71</td>
<td>124.57</td>
<td>Custo variável</td>
</tr>
</tbody>
</table>

A tabela a seguir mostra o resultado quando os serviços financeiros são aplicados como base de alocação de custos total (custos fixos e custos variáveis.)

<table>
<thead>
<tr>
<th colspan="2">Objeto de custo</th>
<th>Magnitude</th>
<th>Fator de alocação</th>
<th>Valor</th>
<th>Comportamento de custo</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC003</td>
<td>Montagem</td>
<td>65</td>
<td>(65 ÷ 100) × (500,00 + 175,00)</td>
<td>438.75</td>
<td>Custo fixo</td>
</tr>
<tr>
<td>CC004</td>
<td>Embalagem</td>
<td>35</td>
<td>(35 ÷ 100) × (500,00 + 175,00)</td>
<td>236.25</td>
<td>Custo fixo</td>
</tr>
<tr>
<td>CC003</td>
<td>Montagem</td>
<td>65</td>
<td>(65 ÷ 100) × (7.714,29 + 436,00)</td>
<td>5,297.69</td>
<td>Custo variável</td>
</tr>
<tr>
<td>CC004</td>
<td>Embalagem</td>
<td>35</td>
<td>(35 ÷ 100) × (7.714,29 + 436,00)</td>
<td>2,852.60</td>
<td>Custo variável</td>
</tr>
</tbody>
</table>

A tabela a seguir mostra o resultado quando os serviços de Montagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)

<table>
<thead>
<tr>
<th colspan="2">Objeto de custo</th>
<th>Magnitude</th>
<th>Fator de alocação</th>
<th>Valor</th>
<th>Comportamento de custo</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod. 1</td>
<td>Produto 1</td>
<td>60</td>
<td>(60 ÷ 80) × (275,00 + 438,75)</td>
<td>535.31</td>
<td>Custo fixo</td>
</tr>
<tr>
<td>Prod. 2</td>
<td>Produto 2</td>
<td>20</td>
<td>(20 ÷ 80) × (275,00 + 438,75)</td>
<td>178.44</td>
<td>Custo fixo</td>
</tr>
<tr>
<td>Prod. 1</td>
<td>Produto 1</td>
<td>60</td>
<td>(60 ÷ 80) × (5.297,69 + 685,14)</td>
<td>4,487.12</td>
<td>Custo variável</td>
</tr>
<tr>
<td>Prod. 2</td>
<td>Produto 2</td>
<td>20</td>
<td>(20 ÷ 80) × (5.297,69 + 685,14)</td>
<td>1,495.71</td>
<td>Custo variável</td>
</tr>
</tbody>
</table>

A tabela a seguir mostra o resultado quando os serviços de Embalagem são aplicados como uma base de alocação de custos total (custos fixos e custos variáveis.)

<table>
<thead>
<tr>
<th colspan="2">Objeto de custo</th>
<th>Magnitude</th>
<th>Fator de alocação</th>
<th>Valor</th>
<th>Comportamento de custo</th>
</tr>
</thead>
<tbody>
<tr>
<td>Prod. 1</td>
<td>Produto 1</td>
<td>80</td>
<td>(80 ÷ 95) × (50,00 + 236,25)</td>
<td>241.05</td>
<td>Custo fixo</td>
</tr>
<tr>
<td>Prod. 2</td>
<td>Produto 2</td>
<td>15</td>
<td>(15 ÷ 95) × (50,00 + 236,25)</td>
<td>45.20</td>
<td>Custo fixo</td>
</tr>
<tr>
<td>Prod. 1</td>
<td>Produto 1</td>
<td>80</td>
<td>(80 ÷ 95) × (2.852,60 + 124,57)</td>
<td>2,507.09</td>
<td>Custo variável</td>
</tr>
<tr>
<td>Prod. 2</td>
<td>Produto 2</td>
<td>15</td>
<td>(15 ÷ 95) × (2.852,60 + 124,57)</td>
<td>470.08</td>
<td>Custo variável</td>
</tr>
</tbody>
</table>

##### <a name="journal-entries-cost-object-balance-journal-entries"></a>Entradas de diário (entradas de diário do saldo de objeto de custo)

<table>
<thead>
<tr>
<th>Diário</th>
<th>Tipo de diário</th>
<th colspan="3">Período do calendário fiscal</th>
<th>Versão</th>
</tr>
</thead>
<tbody>
<tr>
<td>00004</td>
<td>Diário de alocação de custos</td>
<td>fiscal</td>
<td>2017</td>
<td>Período 1</td>
<td>Cálculo de custos gerais indiretos / 01-02-2017 11:51:00 PM / Razão/2017 / Período 1</td>
</tr>
</tbody>
</table>

##### <a name="journal-lines"></a>Linhas do diário

<table>
<thead>
<tr>
<th>Data contábil</th>
<th colspan="2">Objeto de custo</th>
<th colspan="2">Elemento de custo</th>
<th>Comportamento de custo</th>
<th>Valor</th>
</tr>
</thead>
<tbody>
<tr>
<td>31 de janeiro, 2017</td>
<td>CC001</td>
<td>RH</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo fixo</td>
<td>500,00</td>
</tr>
<tr>
<td>31 de janeiro, 2017</td>
<td>CC001</td>
<td>RH</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>1,245.71</td>
</tr>
<tr>
<td>31 de janeiro, 2017</td>
<td>CC002</td>
<td>Finanças</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo fixo</td>
<td>675.00</td>
</tr>
<tr>
<td>31 de janeiro, 2017</td>
<td>CC002</td>
<td>Finanças</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>8,150.29</td>
</tr>
<tr>
<td>31 de janeiro, 2017</td>
<td>CC003</td>
<td>Montagem</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo fixo</td>
<td>713.75</td>
</tr>
<tr>
<td>31 de janeiro, 2017</td>
<td>CC003</td>
<td>Montagem</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>5,982.83</td>
</tr>
<tr>
<td>31 de janeiro, 2017</td>
<td>CC003</td>
<td>Embalagem</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo fixo</td>
<td>286.25</td>
</tr>
<tr>
<td>31 de janeiro, 2017</td>
<td>CC003</td>
<td>Embalagem</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>2,977.17</td>
</tr>
<tr>
<td>31 de janeiro, 2017</td>
<td>Prod. 1</td>
<td>Produto 1</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo fixo</td>
<td>776.36</td>
</tr>
<tr>
<td>31 de janeiro, 2017</td>
<td>Prod. 1</td>
<td>Produto 1</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>6,994.21</td>
</tr>
<tr>
<td>31 de janeiro, 2017</td>
<td>Prod. 2</td>
<td>Produto 1</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo fixo</td>
<td>223.64</td>
</tr>
<tr>
<td>31 de janeiro, 2017</td>
<td>Prod. 2</td>
<td>Produto 1</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>1,965.79</td>
</tr>
</tbody>
</table>

##### <a name="cost-entries"></a>Entradas de custo

<table>
<thead>
<tr>
<th colspan="2">Objeto de custo</th>
<th colspan="2">Elemento de custo</th>
<th>Comportamento de custo</th>
<th>Valor</th>
<th>Data contábil</th>
</tr>
</thead>
<tbody>
<tr>
<td>CC001</td>
<td>RH</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo fixo</td>
<td>-500,00</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanças</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo fixo</td>
<td>175.00</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Montagem</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo fixo</td>
<td>275.00</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC004</td>
<td>Embalagem</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo fixo</td>
<td>50,00</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC001</td>
<td>RH</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>-1.245,71</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanças</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>436.00</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Montagem</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>685.14</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC004</td>
<td>Embalagem</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>124.57</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanças</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo fixo</td>
<td>-675,00</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Montagem</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo fixo</td>
<td>438.75</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC004</td>
<td>Embalagem</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo fixo</td>
<td>236.25</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC002</td>
<td>Finanças</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>-8.150,29</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Montagem</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>5,297.69</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC004</td>
<td>Embalagem</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>2,852.60</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Montagem</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo fixo</td>
<td>-713,75</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>Prod. 1</td>
<td>Produto 1</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo fixo</td>
<td>535.31</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>Prod. 2</td>
<td>Produto 2</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo fixo</td>
<td>178.44</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Montagem</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>-5.982,83</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>Prod. 1</td>
<td>Produto 1</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>4,487.12</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>Prod. 2</td>
<td>Produto 2</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>1,495.71</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Montagem</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo fixo</td>
<td>-286,25</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>Prod. 1</td>
<td>Produto 1</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo fixo</td>
<td>241.05</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>Prod. 2</td>
<td>Produto 2</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo fixo</td>
<td>45.20</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>CC003</td>
<td>Montagem</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>-2.977,17</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>Prod. 1</td>
<td>Produto 1</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>2,507.09</td>
<td>31 de janeiro, 2017</td>
</tr>
<tr>
<td>Prod. 2</td>
<td>Produto 2</td>
<td>10001</td>
<td>eletricidade</td>
<td>Custo variável</td>
<td>470.08</td>
<td>31 de janeiro, 2017</td>
</tr>
</tbody>
</table>

## <a name="conclusion"></a>Conclusão
Na contabilidade financeira, um custo de 10,000.00 para a eletricidade é lançado para um ID fictício de centro de custos. Portanto, os contadores de custo saberão que esses custos devem ser alocados. Na contabilização de custo, os custos fluem nas unidades organizacionais e nos níveis, com base nas políticas e regras que são aplicadas. Cada custo foi associado a uma base de alocação que fornece a melhor apuração para a alocação de custos.

<table>
<thead>
<tr>
<th colspan="2" rowspan="2">Elemento de custo</th>
<th colspan="9">Objeto de custo</th>
<th rowspan="2">Total</th>
</tr>
<tr>
<th>CC099</th>
<th>CC001</th>
<th>CC002</th>
<th>CC003</th>
<th>CC004</th>
<th>Proj. 1</th>
<th>Proj. 2</th>
<th>Prod. 1</th>
<th>Prod. 2</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2">10001 Eletricidade</td>
<td style="text-align: right;"><strong>0,00</strong></td>
<td style="text-align: right;"><strong>0,00</strong></td>
<td style="text-align: right;"><strong>0,00</strong></td>
<td style="text-align: right;"><strong>0,00</strong></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"><strong>30.00</strong></td>
<td style="text-align: right;"><strong>10.00</strong></td>
<td style="text-align: right;"><strong>7,770.57</strong></td>
<td style="text-align: right;"><strong>2,189.43</strong></td>
<td style="text-align: right;"><strong>10,000.00</strong></td>
</tr>
<tr>
<td></td>
<td style="text-align: left;">Não classificado</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;">Custo fixo</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;"></td>
<td style="text-align: right;"></td>
<td style="text-align: right;">776.36</td>
<td style="text-align: right;">223.64</td>
<td style="text-align: right;"><strong>1,000.00</strong></td>
</tr>
<tr>
<td style="text-align: right;"></td>
<td style="text-align: left;">Custo variável</td>
<td style="text-align: right;">000</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">0,00</td>
<td style="text-align: right;">30,00</td>
<td style="text-align: right;">10,00</td>
<td style="text-align: right;">6,994.21</td>
<td style="text-align: right;">1,965.79</td>
<td style="text-align: right;"><strong>9,000.00</strong></td>
</tr>
</tbody>
</table>

> [!NOTE]
> Esse tópico mostra como um elemento de custo principal, 10001 Eletricidade flui pelos objetos de custo. Portanto, esse custo geral indireto é alocado no nível mais baixo na organização. Em outras palavras, os objetos de custo no nível mais baixo assumem o custo. Se você exigir um fluxo visual de custo entre objetos de custo, é possível usar as regras de política de acúmulo de custos para visualizar o fluxo de custo. Para obter mais informações, consulte [Política de acúmulo de custo e cálculo de custos indiretos](cost-rollup.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]