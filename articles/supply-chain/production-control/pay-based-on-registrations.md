---
title: Pagamento com base em registros
description: Este tópico explica como o pagamento é calculado com base em registros de trabalhador.
author: johanhoffmann
ms.date: 03/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgCalcApproveWeekView, JmgProdStatusListPagePayrollCostDetails, JmgPayCountTable, JmgPayStatConfig, JmgOvertimeSlize, JmgPayAgreementOverride, JmgPayCountSum, JmgPayAdjustSetup, JmgPayAdjustCostType, JmgPayEmployee, JmgMESBreak, JmgPayAddTable, JmgPayAddTransSelectTransId, JmgPayrollCostDetailsPart, jmgProdStatusListPagePayrollCosts, JmgPayrollCostPart, JmgPayEvents, JmgTermRegPayStatSetup, JmgPayStatGroup, JmgPayAddTrans, JmgPayStatTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2018-03-20
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: c511558735e89db32e88f6efdd2d0cc88a04b61c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814817"
---
# <a name="pay-based-on-registrations"></a>Pagamento com base em registros

[!include [banner](../includes/banner.md)]

Este tópico explica, detalhadamente, como o pagamento é calculado com base em registros de trabalhador. Ele inclui exemplos para mostram como as várias combinações de opções de configuração disponíveis para o cálculo afetam o resultado. Estas são algumas das áreas que serão abordadas:

- Horário flexível
- Hora extra
- Intervalos
- Códigos de alternância
- Itens de pagamento
- Contratos de pagamento
- Parâmetros de cálculo de horário e presença
- Ausência

## <a name="the-use-of-flex-time"></a>O uso de horário flexível

Os períodos de horário flexível são configurados nos perfis de tempo usados em Horário e presença. Há dois tipos de perfil flexível: **Flex+** e **Flex-**. Quando um trabalhador registra o horário em um período Flex+, o saldo flexível do trabalhador é acrescido das horas trabalhadas. O trabalhador não recebe remuneração pelas horas trabalhadas durante o período Flex+. Entretanto, o trabalhador pode sair no período Flex- e ser compensado com as horas do saldo flexível. Assim, a folga nos períodos flexíveis é considerada uma ausência pelo sistema.

## <a name="scenarios-based-on-flex-periods"></a>Cenários baseados em períodos flexíveis

Os dois cenários a seguir se baseiam em um perfil flexível que representa um dia útil. Para ambos os cenários, o pagamento é calculado de acordo com o período flexível onde o trabalhador registra a entrada e a saída.

### <a name="flex-profile-for-one-workday"></a>Perfil flexível para um dia útil

| Tipo de perfil  | Início    | Fim      | Dia     |
|---------------|----------|----------|---------|
| Hora extra     | 00:00 | 06:00 | Segunda-feira  |
| Mais flexível         | 06:00 | 07:00 | Segunda-feira  |
| Registro de entrada      | 07:00 | 07:00 | Segunda-feira  |
| Período padrão | 07:00 | 14:30 | Segunda-feira  |
| Menos flexível         | 14:30 | 15:30 | Segunda-feira  |
| Registro de saída     | 15:30 | 15:30 | Segunda-feira  |
| Hora extra     | 15:30 | 06:00 | Terça-feira |

### <a name="scenario-1-a-worker-registers-clock-in-during-a-flex-period-and-clock-out-during-a-flex--period"></a>Cenário 1: um trabalhador entra durante um período Flex+ e sai durante um período Flex-

Veja a seguir a aparência dos registros do trabalhador para o dia.

| Tipo de registro do diário | Início    | Fim      |
|---------------------------|----------|----------|
| Registro de entrada                  | 06:30 | 06:30 |
| Trabalho de produção            | 06:30 | 14:45 |
| Registro de saída                 | 14:45 | 14:45 |

Os registros do trabalhador para o dia são calculados e transferidos para o pagamento na página **Aprovar** (**Horário e presença** &gt; **Revisar e aprovar** &gt; **Aprovar**). Após o cálculo dos registros, o resultado do cálculo pode ser exibido na guia **Horas** . 

Para compreender este cenário, consulte os campos a seguir.

| Flex + | Flex - | Hora | Pagar hora |
|--------|--------|------|----------|
| 0,50   | 0,75   | 8,25 | 8,50     |

#### <a name="calculation-of-flex"></a>Cálculo de Flex+

De acordo com o perfil flexível, o tempo entre 06:00 e 07:00 é um período Flex+. Portanto, se o trabalhador entra às 06:30, ele ganha 0,5 horas. Este valor de tempo é adicionado à conta flexível do trabalhador.

#### <a name="calculation-of-flex-"></a>Cálculo de Flex-

De acordo com o perfil flexível, o período Flex- começa às 14:30 e termina às 15:30. Portanto, se o trabalhador sai às 14:45, os 45 minutos (0,75 horas) restantes no período Flex- são registrados como período de pagamento, e a mesma quantidade de tempo é deduzida da conta flexível do trabalhador. Os 45 minutos são incluídos no período de pagamento pois o trabalhador receberá pagamento pelos 45 minutos restantes no período Flex-. Se o trabalhador estiver ausente durante o período Flex-, os 45 minutos serão deduzidos da sua conta flexível.

#### <a name="calculation-of-time"></a>Cálculo do tempo

O tempo é calculado como o tempo entre os horários de entrada e de saída, ou seja, de 06:30 até 14:45, totalizando 8,25 horas.

#### <a name="calculation-of-pay-time"></a>Cálculo do período de pagamento

O período de pagamento é o tempo durante o qual é concedido pagamento a um trabalhador. Nesse cenário, o trabalhador está no trabalho por 8,25 horas (**Hora**). Entretanto, o **Período de pagamento** é calculado como 8,50 horas pois o trabalhador recebe pagamento no período Flex-, após o horário de saída. O período de pagamento equivale às horas planejadas de trabalho pois o período Flex+ é adicionado à conta flexível do trabalhador, e não ao período de pagamento. O período de ausência durante o período Flex- é compensado pelo período de pagamento e deduzido da conta flexível do trabalhador.

| Hora              | Tipo de registro | Período de pagamento (horas)      |
|-------------------|-------------------|-----------------------|
| 6:30 - 7:00 | Mais flexível             | 0                     |
| 7:00 – 14:45 | Período padrão     | 7,75                  |
| 14:45 – 15:30 | Menos flexível             | 0,75 (período de ausência) |
|                   | Total             | 8,50                  |

### <a name="scenario-2-a-worker-works-during-the-whole-flex--period-and-also-works-overtime"></a>Cenário 2: um trabalhador trabalha durante todo o período Flex- e também em horas extras

Veja a seguir a aparência dos registros do trabalhador para o dia.

| Tipo de registro do diário | Início    | Fim      |
|---------------------------|----------|----------|
| Registro de entrada                  | 06:30 | 06:30 |
| Trabalho de produção            | 06:30 | 17:00 |
| Registro de saída                 | 17:00 | 17:00 |

Após calcular os registros de diário na página **Aprovar**, você pode exibir o resultado do cálculo na guia **Hora**. Para compreender este cenário, consulte os campos a seguir.

| Flex + | Flex - | Hora  | Pagar hora | Pagar hora extra |
|--------|--------|-------|----------|--------------|
| 0,50   | 0,00   | R$ 10,50 | 10,00    | 1.50         |

#### <a name="calculation-of-flex"></a>Cálculo de Flex+

De acordo com o perfil flexível, o tempo entre 06:00 e 07:00 é um período Flex+. Portanto, se o trabalhador registra sua entrada às 06:30, ele ganha 0,5 horas de período Flex+ no saldo flexível.

#### <a name="calculation-of-flex-"></a>Cálculo de Flex-

Como o trabalhador está trabalhando no período Flex-, esse período não é calculado. O período Flex- é calculado apenas se o trabalhador está ausente no período Flex-. De uma perspectiva de pagamento, se o trabalhador trabalha no período Flex-, a taxa de pagamento concedida a ele é definida como a hora padrão. Se o trabalhador estiver ausente durante o período Flex-, os 45 minutos serão deduzidos da sua conta flexível.

#### <a name="calculation-of-time"></a>Cálculo do tempo

O tempo é calculado como o tempo entre o horário de entrada às 06:30 e o horário de saída às 17:00, ou 10,50 horas.

#### <a name="calculation-of-pay-time"></a>Cálculo do período de pagamento

Nesse cenário, o trabalhador trabalha por 10,50 horas (**Hora**). Entretanto, **Período de pagamento** é calculado como 10,00 horas pois o trabalhador não recebe pagamento no período Flex+.

#### <a name="calculation-of-pay-overtime"></a>Cálculo de hora extra de pagamento

| Hora               | Tipo de registro | Período de pagamento (horas) |
|--------------------|-------------------|------------------|
| 6:30 - 7:00  | Mais flexível             | 0                |
| 7:00 – 14:30  | Período padrão     | 7,50             |
| 14:30 – 15:30  | Menos flexível             | 1.00             |
| 15:30 – 17:00 | Hora extra          | 1.50             |
|                    | Total             | 10,00            |

### <a name="generation-of-pay-items"></a>Geração de itens de pagamento

Os registros do trabalhador para o dia podem ser transferidos da página **Aprovar**. Durante o processo de transferência, os itens de pagamento e os registros transferidos são gerados. Os itens de pagamento representam um detalhamento do tempo de pagamento em período padrão, horas extras, horas de interrupção pagas etc.

Para abrir a lista de itens de pagamento, selecione &gt; **Horário e presença** **Revisar e aprovar** &gt; **Aprovar**. Selecione **Consulta** &gt; **Registros transferidos**.

Os itens de pagamento são a base do pagamento de um trabalhador. Você pode gerar um arquivo que inclua as informações de itens de pagamento e transferir esse arquivo para um sistema de folha de pagamento.

Como parte do processo de transferência, o tempo e o custo das atividades de produção e projeto são transferidos para os diários de produção e projeto para contabilizar os gastos em tempo e custo. Os registros transferidos são a base de tempo e preço de custo por hora para ordens de produção e projetos. Você pode abrir os registros transferidos usando o menu **Consulta** na página **Aprovar**.

Por exemplo, para o cenário 2, os itens de pagamento a seguir são gerados.

| Tipo de salário     | Tipo de pagamento | Unidades de pagamento | Alíquota  | Custo total |
|---------------|----------|-----------|-------|------------|
| Período padrão | 1201     | 10,0      | 10    | 100        |
| Hora extra      | 1301     | 1.50      | 5     | 7,50       |
|               |          |           | Total | 107,50     |

O item de pagamento para período padrão tem uma unidade de pagamento de 10 horas que abrange período padrão, período Flex- e horas extras. Período padrão, período Flex- e horas extras são consolidados em um item de pagamento pois todos os tipos são calculados como período padrão, com base na configuração padrão de um parâmetro na página **Parâmetros de cálculo** (**Horário e presença** &gt; **Configuração** &gt; **Parâmetros de cálculo**). As horas extras são calculadas sobre o período padrão usando uma taxa adicional de 5.

Se você deseja distinguir bem período padrão e horas extras, para que as unidades de pagamento dos tipos de pagamento abranjam apenas o tempo real gasto em período padrão e horas extras, as unidades de pagamento do período padrão devem ser calculadas como 8,50, e as unidades de pagamento de horas extras devem ser calculadas como 1,50.

Para configurar o sistema para distinguir bem período padrão e horas extras, exclua horas extras do período padrão. Você também pode alterar a configuração do tipo de pagamento para horas extras de forma que a taxa de pagamento de horas extras abranja todos os pagamentos para as horas gastas em horas extras.

### <a name="exclude-overtime-from-the-standard-time"></a>Excluir horas extras do período padrão

Na página **Parâmetros de cálculo**, selecione **Hora extra** como o tipo de especificação do perfil, e defina a opção **Período de pagamento** como **Não**, conforme mostrado aqui.

| Especificação de reg. | Tipo de especificação de perfil | Cálculo   |     | Pagamento         |     |
|--------------------|----------------------------|---------------|-----|--------------|-----|
| Horário de trabalho       | Hora extra                   | Período padrão | Sim | Pagar hora     | Não  |
|                    |                            | Pagar hora      | Sim | Pagar hora extra | Sim |

Após você ajustar os parâmetros de cálculo, os itens de pagamento a seguir serão gerados.

| Tipo de salário     | Tipo de pagamento | Unidades de pagamento | Alíquota  | Custo total |
|---------------|----------|-----------|-------|------------|
| Período padrão | 1201     | 8,50      | 10    | 85,0       |
| Hora extra      | 1301     | 1.50      | 15    | 22,50      |
|               |          |           | Total | 107,50     |

> [!NOTE]
> Os parâmetros de cálculo têm uma configuração padrão recomendada. Tome cuidado ao alterar esses parâmetros. Para restaurar as configurações padrão recomendadas, na página **Parâmetros de cálculo**, selecione **Restaurar valores**.

### <a name="allow-a-deviation-from-the-standard-pay-profiles"></a>Permitir um desvio dos perfis de pagamento padrão

Na página **Perfis** (**Horário e presença** &gt; **Configuração** &gt; **Perfis de tempo** &gt; **Perfis**), você pode configurar os tipos de perfil que incluem interrupções e códigos de alternância.

### <a name="switch-codes"></a>Códigos de alternância

Você pode usar códigos de alternância para permitir que trabalhadores desviem do seu tipo de perfil alterando para um tipo de perfil diferente. Por exemplo, você pode permitir que um trabalhador altere de período Flex+ para horas extras. Um trabalhador pode adicionar um código de alternância durante o registro, ou você pode atribuir a tarefa de adicionar um código de alternância ao aprovador dos registros.

Antes de usar um código de alternância, você precisa defini-lo como um tipo de atividade indireta. Você deve adicionar o código de alternância ao perfil de tempo para o período em que deseja permitir uma alteração do tipo de perfil. Por exemplo, siga essas etapas para criar um código de alternância que permita alterar o período Flex+ de 06:00 para 07:00 para horas extras.

1. Crie um código de alternância denominado **OTBCI (converter flexível em horas extras antes da entrada)**. Selecione **Horário e presença** &gt; **Gerenciar atividades indiretas** &gt; **Atividades indiretas**.
2. Na coluna **Código de alternância**, adicione OTBCI à linha Flex+ no perfil de tempo.
3. Na coluna **Secundário**, adicione o tipo de perfil **Hora extra**.

Considere o perfil flexível a seguir que representa um dia útil.

| Tipo de perfil  | Início    | Fim      | Dia     |
|---------------|----------|----------|---------|
| Hora extra     | 00:00 | 06:00 | Segunda-feira  |
| Mais flexível         | 06:00 | 07:00 | Segunda-feira  |
| Registro de entrada      | 07:00 | 07:00 | Segunda-feira  |
| Período padrão | 07:00 | 14:30 | Segunda-feira  |
| Menos flexível         | 14:30 | 15:30 | Segunda-feira  |
| Registro de saída     | 15:30 | 15:30 | Segunda-feira  |
| Hora extra     | 15:30 | 06:00 | Terça-feira |

Veja a seguir os registros do trabalhador para o dia.

| Tipo de registro do diário | Início    | Fim      |
|---------------------------|----------|----------|
| Registro de entrada                  | 06:30 | 06:30 |
| Trabalho de produção            | 06:30 | 14:45 |
| Registro de saída                 | 17:00 | 17:00 |

Os itens de pagamento a seguir são geradas após a transferência.

| Tipo de salário     | Tipo de pagamento | Unidades de pagamento | Alíquota  | Custo total |
|---------------|----------|-----------|-------|------------|
| Período padrão | 1201     | 8,50      | 10    | 85,0       |
| Hora extra      | 1305     | 1.50      | 15    | 22,50      |
|               |          |           | Total | 107,50     |

Na página **Aprovar**, desfaça a transferência e use o menu **Código de alternância** para aplicar o código de alternância **OTBCI**. Quando você transfere os registros novamente, os itens de pagamento a seguir são gerados.

| Tipo de salário     | Tipo de pagamento | Unidades de pagamento | Alíquota  | Custo total |
|---------------|----------|-----------|-------|------------|
| Período padrão | 1201     | 8,50      | 10    | 80,0       |
| Hora extra      | 1305     | 2.00      | 15    | 30,0       |
|               |          |           | Total | 107,50     |

> [!NOTE]
> Quando você aplica o código de alternância, há um aumento de 0,5 nas horas extras, de 1,50 para 2,00. 0,5 horas é a conversão do período Flex+ registrado, de 6:30 para 07:00 para hora extra.

### <a name="breaks"></a>Intervalos

Interrupções no trabalho afetam o cálculo de pagamento do trabalhador. As interrupções são definidas como um tipo de atividade indireta. Elas podem ser definidas como **Paga**, para permitir que a interrupção seja adicionada ao pagamento do trabalhador, ou **Não paga**, para evitar que a interrupção seja adicionada ao pagamento do trabalhador. Uma interrupção pode ser definida como **Planejada** ou **Registrada**.

#### <a name="planned-breaks"></a>Interrupções planejadas

Se uma empresa tem um horário fixo de interrupção, como um intervalo fixo para almoço, a interrupção pode ser predefinida no perfil de tempo. Nesse caso, o trabalhador não precisa registrar a interrupção nas páginas de ficha de trabalho. A interrupção é contabilizada automaticamente quando os registros do trabalhador são calculados na página **Aprovar**.

#### <a name="registered-breaks"></a>Interrupções registradas

Se uma empresa não usa interrupções planejadas, os trabalhadores podem registrar interrupções durante o dia de trabalho. As interrupções registradas podem ser usadas, por exemplo, se um trabalhador trabalha em um perfil de horário flexível sem horários de entrada e de saída definidos. As interrupções registradas são um tipo de atividade indireta. O trabalhador registra a interrupção na página de terminal **Ficha de trabalho** ou na página de dispositivo **Ficha de trabalho**. Nessas duas páginas, o usuário pode selecionar o tipo de interrupção em uma lista de atividades de interrupção predefinidas.

#### <a name="paid-and-unpaid-breaks"></a>Interrupções pagas e não pagas

Atividades de interrupção podem ser configuradas como **Paga** ou **Não paga**. Uma interrupção paga é incluída no cálculo do período de pagamento. O sistema usa o tipo de pagamento definido no contrato de pagamento para o tipo do registro **Interrupção**.

### <a name="example-of-a-planned-break"></a>Exemplo de uma interrupção planejada

Considere o perfil de tempo a seguir que inclui uma interrupção para almoço não paga.

| Tipo de perfil  | Início    | Fim      | Dia     |
|---------------|----------|----------|---------|
| Hora extra     | 00:00 | 06:00 | Segunda-feira  |
| Mais flexível         | 06:00 | 07:00 | Segunda-feira  |
| Registro de entrada      | 07:00 | 07:00 | Segunda-feira  |
| Período padrão | 07:00 | 12:00 | Segunda-feira  |
| Interrupção         | 12:00 | 12:30 | Segunda-feira  |
| Período padrão | 12:30 | 14:30 | Segunda-feira  |
| Menos flexível         | 14:30 | 15:30 | Segunda-feira  |
| Registro de saída     | 15:30 | 15:30 | Segunda-feira  |
| Hora extra     | 15:30 | 06:00 | Terça-feira |

Veja a seguir os registros do trabalhador para o dia.

| Tipo de registro do diário | Início    | Fim      |
|---------------------------|----------|----------|
| Registro de entrada                  | 06:30 | 06:30 |
| Trabalho de produção            | 06:30 | 14:45 |
| Registro de saída                 | 17:00 | 17:00 |

Após calcular os registros de diário na página **Aprovar**, você pode exibir o resultado do cálculo na guia **Hora**. Para compreender este cenário, consulte os campos a seguir.

| Flex + | Flex - | Hora  | Pagar hora | Interrupção não paga | Pagar hora extra |
|--------|--------|-------|----------|---------------------|--------------|
| 0,50   | 0,00   | R$ 10,50 | 9,50     | 0,5                 | 1.50         |

> [!NOTE] 
> O sistema calculou 0,5 horas do tempo de interrupção não pago, e esse tempo não faz parte do tempo de pagamento.

### <a name="example-of-a-registered-break"></a>Exemplo de uma interrupção registrada

Considere o perfil de tempo a seguir que não inclui interrupções planejadas.

| Tipo de perfil  | Início    | Fim      | Dia     |
|---------------|----------|----------|---------|
| Hora extra     | 00:00 | 06:00 | Segunda-feira  |
| Mais flexível         | 06:00 | 07:00 | Segunda-feira  |
| Registro de entrada      | 07:00 | 07:00 | Segunda-feira  |
| Período padrão | 07:00 | 14:30 | Segunda-feira  |
| Menos flexível         | 14:30 | 15:30 | Segunda-feira  |
| Registro de saída     | 15:30 | 15:30 | Segunda-feira  |
| Hora extra     | 15:30 | 06:00 | Terça-feira |

Veja a seguir os registros do trabalhador para o dia.

| Tipo de registro do diário | Início    | Fim      |
|---------------------------|----------|----------|
| Registro de entrada                  | 06:30 | 06:30 |
| Trabalho de produção            | 06:30 | 17:00 |
| Interrupção                     | 12:03 | 12:32 |
| Registro de saída                 | 17:00 | 17:00 |

Quando os registros são calculados, o tempo das atividades é calculado.

| Tipo de registro do diário | Início    | Fim      | Hora  |
|---------------------------|----------|----------|-------|
| Registro de entrada                  | 06:30 | 06:30 |       |
| Trabalho de produção            | 06:30 | 17:00 | 10,00 |
| Interrupção                     | 12:03 | 12:32 | 0,50  |
| Registro de saída                 | 17:00 | 17:00 |       |

> [!NOTE]
> O tempo de interrupção ocorre em paralelo com o tempo da atividade (um trabalho de produção, neste exemplo) Esse comportamento é sempre usado para atividades de interrupção. Quando os registros são calculados, o tempo de interrupção é subtraído do tempo de atividade. Nesse caso, o trabalho de produção tem uma duração de 10,50 horas, mas o tempo é calculado como 10 porque 0,5 horas do tempo de interrupção são subtraídas do tempo de atividade.

Após calcular os registros de diário na página **Aprovar**, você pode exibir o resultado do cálculo na guia **Hora**. Para compreender este cenário, consulte os campos a seguir.

| Flex + | Flex - | Hora  | Pagar hora | Interrupção não paga | Pagar hora extra |
|--------|--------|-------|----------|---------------------|--------------|
| 0,50   | 0,00   | R$ 10,50 | 9,50     | 0,5                 | 1,50         |

Caso a interrupção planejada tenha sido paga, em vez de não paga, o resultado do cálculo terá a aparência a seguir.

| Flex + | Flex - | Hora  | Pagar hora | Interrupção paga | Pagar hora extra |
|--------|--------|-------|----------|-----------------|--------------|
| 0,50   | 0,00   | R$ 10,50 | 10,00    | 0,5             | 1,50         |

### <a name="pay-items-and-paid-breaks"></a>Itens de pagamento e interrupções pagas

Quando você transfere registros na página **Aprovar**, itens de pagamento são gerados. Um item de pagamento separado é gerado para interrupções pagas.

A taxa de pagamento de uma interrupção paga é determinada pelo tipo de pagamento configurado nos contratos de pagamento da interrupção. Em vez de usar um tipo de pagamento, você pode configurar o preço de custo por hora na interrupção para um intervalo de datas definido.

Considere o perfil de tempo a seguir.

| Tipo de perfil  | Início    | Fim      | Dia     |
|---------------|----------|----------|---------|
| Hora extra     | 00:00 | 06:00 | Segunda-feira  |
| Mais flexível         | 06:00 | 07:00 | Segunda-feira  |
| Registro de entrada      | 07:00 | 07:00 | Segunda-feira  |
| Período padrão | 07:00 | 14:30 | Segunda-feira  |
| Menos flexível         | 14:30 | 15:30 | Segunda-feira  |
| Registro de saída     | 15:30 | 15:30 | Segunda-feira  |
| Hora extra     | 15:30 | 06:00 | Terça-feira |

Veja a seguir os registros do trabalhador para o dia.

| Tipo de registro do diário | Início    | Fim      | Hora |
|---------------------------|----------|----------|------|
| Registro de entrada                  | 07:00 | 07:00 |      |
| Trabalho de produção            | 07:00 | 15:00 | 7,5  |
| Interrupção (paga)              | 12:00 | 12:30 | 0,5  |
| Registro de saída                 | 15:00 | 15:00 |      |

Para este exemplo, o tipo de pagamento para hora padrão é definido como **1201**, e uma taxa de pagamento de **10** é configurada no contrato de pagamento. A interrupção paga tem um tipo de pagamento de **1301** e uma taxa de pagamento de **8**. Quando os registros são transferidos, os itens de pagamento a seguir são gerados.

| Tipo de salário     | Tipo de pagamento | Unidades de pagamento | Alíquota |
|---------------|----------|-----------|------|
| Período padrão | 1201     | 7,50      | 10   |
| Menos flexível         | 1201     | 0,50      | 10   |
| Interrupção (paga)  | 1301     | 0,50      | 8    |

## <a name="how-the-cost-of-paid-breaks-is-allocated-to-projects-and-production-orders"></a>Como o custo de interrupções pagas é alocado a projetos e ordens de produção

O custo por hora em atividades do projeto e trabalhos de produção pode ser configurado de forma que isso seja determinado por taxas de pagamento que são calculadas em Horário e presença ou pelas categorias de custo que são definidas para as atividades.

Para configurar a categoria de custo, selecione **Controle de produção** &gt; **Configuração** &gt; **Execução de fabricação** &gt; **Padrões da ordem de produção**, e defina o campo **Categoria de custo** como **Sim** ou **Não**.

- **Não** – o custo é calculado com base em taxas de pagamento que são definidas para tipos de registro Horário e presença.
- **Sim** – o custo é calculado com base em categorias de custo para atividades de projeto e produção.

### <a name="cost-calculation-based-on-pay-rates-that-are-calculated-in-time-and-attendance"></a>Cálculo de custo com base em taxas de pagamento que são calculadas em Horário e presença

O exemplo a seguir mostra como o custo por hora é calculado quando o custo é configurado de forma que o cálculo se baseie em taxas de pagamento.

A taxa de custo por hora é usada para ordens de produção, e projetos são calculados durante o processo de transferência. Para exibir o preço por hora por atividade, abra a página **Aprovar** em Horário e presença. Depois, selecione **Consulta** &gt; **Registros transferidos**. Você pode encontrar a taxa de custo por hora por registro na guia **Preços de custo**.

Considere os registros a seguir que usam o mesmo perfil de tempo que o exemplo anterior.

| Tipo de registro do diário | Início    | Fim      | Hora |
|---------------------------|----------|----------|------|
| Registro de entrada                  | 07:00 | 07:00 |      |
| Processo (ordem: 4711)     | 07:00 | 11:00 | 4    |
| Processo (ordem: 4712)     | 11:00 | 15:00 | 3,50 |
| Interrupção (paga)              | 12:00 | 12:30 | 0,50 |
| Registro de saída                 | 15:00 | 15:00 |      |

Após a transferência dos registros, os registros transferidos a seguir são gerados.

| Tipo de registro     | Hora | Preço de custo por hora |
|-----------------------|------|---------------------|
| Registro de entrada              | 0,00 | 0,00                |
| Processo (ordem: 4711) | 4.00 | 10,00               |
| Processo (ordem: 4712) | 3,50 | 11,14               |
| Interrupção (paga)          | 0,50 | 0,00                |
| Registro de saída             | 0,00 | 0,00                |

O cálculo do preço de custo por hora da interrupção paga depende de uma configuração de custos diretos da folha de pagamento. Selecione **Horário e presença** &gt; **Configuração** &gt; **Parâmetros de horário e presença**. Na guia **Preço de custo**, em **Custos diretos da folha de pagamento**, no campo **Período padrão**, selecione **Sim**, **Não** ou **Alocação**.

- **Sim** – este valor é usado para o exemplo anterior. O custo é alocado para a atividade de produção ou de projeto executado em paralelo à atividade de interrupção paga. No exemplo, essa atividade é o trabalho de produção da ordem 4712. Como você pode perceber, o preço de custo por hora da interrupção paga é 0 (zero), e ele é alocado para o trabalho que é executado em paralelo com a interrupção.

    A interrupção paga tem a duração de 0,5 horas, e a taxa de pagamento é de 8. Portanto, o custo total da interrupção paga é de 4. O custo total é alocado para o trabalho de processo de 3,5 horas. Portanto, a interrupção paga contribui 1,14 por hora para o custo (4 ÷ 3,5 = 1,14).

- **Alocação** – a interrupção paga é distribuída igualmente para os trabalhos registrados para o dia. Se esse valor for usado para o exemplo anterior, os registros transferidos a seguir serão gerados.

    | Tipo de registro     | Hora | Preço de custo por hora |
    |-----------------------|------|---------------------|
    | Registro de entrada              | 0,00 | 0,00                |
    | Processo (ordem: 4711) | 4.00 | 10,53               |
    | Processo (ordem: 4712) | 3,50 | 10,53               |
    | Interrupção (paga)          | 0,50 | 0,00                |
    | Registro de saída             | 0,00 | 0,00                |

    O tempo total de processo para os dois trabalhos de produção é de 7,5 horas, e o custo total da interrupção paga é de 4. Portanto, o custo da interrupção é calculado como 0,53 (= 4 ÷ 7,5).

- **Não** – o custo da interrupção paga não aumenta o custo por hora das atividades do processo.

    | Tipo de registro     | Hora | Preço de custo por hora |
    |-----------------------|------|---------------------|
    | Registro de entrada              | 0,00 | 0,00                |
    | Processo (ordem: 4711) | 4.00 | 10,00               |
    | Processo (ordem: 4712) | 3,50 | 10,00               |
    | Interrupção (paga)          | 0,50 | 0,00                |
    | Registro de saída             | 0,00 | 0,00                |

## <a name="absence"></a>Ausência

Um código de ausência é usado para registrar o período de ausência de um trabalhador. Assim como interrupções e códigos de alternância, o código de ausência é um tipo de atividade indireta. O período de ausência pode ser planejado ou registrado, e a ausência pode ser legal ou ilegal. Exemplos de ausência legal incluem uma consulta médica, um seminário ou participação em júri. Ausência ilegal é a ausência que não possui um bom motivo. Um exemplo é quando um trabalhador se atrasa para o trabalho. Normalmente, a ausência legal não causa dedução no pagamento de um trabalhador, enquanto a ausência ilegal causa dedução.

### <a name="planned-absence"></a>Ausência planejada

Você pode criar a ausência planejada para trabalhadores na página **Criar ausência planejada** (**Horário e presença** &gt; **Criar ausência planejada**). Ali, a ausência planejada é registrada como um trabalho de ausência para um intervalo especificado de data e hora.

O trabalho se baseia em uma consulta. Assim, você pode criar a ausência planejada para vários trabalhadores, como trabalhadores que pertencem ao mesmo grupo de cálculo. Se a ausência planejada se destina a um único trabalhador, o registro pode ser inserido na página **Presença** ou na página **Trabalhadores de registro de tempo**.

- Para inserir um registro de ausência da página **Presença**, selecione **Horário e presença** &gt; **Consultas e relatórios** &gt; **Presença** &gt; **Presença** e **Registro de ausência**.
- Para inserir um registro de ausência da página *<strong><em>Trabalhadores de registro de tempo</em></strong>*, selecione <strong>Horário e presença</strong> &gt; <strong>Configuração</strong> &gt; <strong>Trabalhadores de registro de tempo</strong> e, em seguida, na guia <strong>Hora</strong>, na <strong>Atribuição de tempo</strong>, selecione <strong>Registros de ausência</strong>.

Você pode usar o relatório **Ausências planejadas** para exibir uma visão geral das ausências planejadas para trabalhadores. Para abrir esse relatório, selecione **Horário e presença** &gt; **Consultas e relatórios** &gt; **Relatórios de ausência** &gt; **Ausências planejadas**.

### <a name="registered-absence"></a>Ausência registrada

Em geral, os trabalhadores são considerados ausentes se não estão no trabalho em qualquer período entre o horário de entrada planejado e o horário de saída planejado. Se os trabalhadores registram entrada após o horário planejado, ou se registram saída antes do horário planejado, eles são solicitados a selecionar um código de ausência para indicar o motivo da ausência. Um código de ausência pode ser configurado de forma que seja aplicável ao registro. Apenas códigos aplicáveis estarão disponíveis para seleção na lista.

## <a name="scenarios-based-on-various-combinations-of-work-hour-registrations"></a>Cenários baseados em várias combinações de registros de hora de trabalho

Os cenários a seguir mostram os itens e as entradas de pagamento para aprovação que são gerados para trabalhadores com base em seus registros. Todos os cenários se baseiam no perfil de tempo a seguir.

| Tipo de perfil  | Início    | Fim      | Dia     |
|---------------|----------|----------|---------|
| Hora extra     | 00:00 | 06:00 | Segunda-feira  |
| Mais flexível         | 06:00 | 07:00 | Segunda-feira  |
| Registro de entrada      | 07:00 | 07:00 | Segunda-feira  |
| Período padrão | 07:00 | 14:30 | Segunda-feira  |
| Menos flexível         | 14:30 | 15:30 | Segunda-feira  |
| Registro de saída     | 15:30 | 15:30 | Segunda-feira  |
| Hora extra     | 15:30 | 06:00 | Terça-feira |

### <a name="scenario-1-the-worker-clocks-in-later-than-planned"></a>Cenário 1: o trabalhador registra entrada após o planejado

O trabalhador registra entrada às 08:30. Como o horário de entrada planejado é 07:00, ele está 1,50 horas atrasado para o trabalho. Como 1,50 horas são consideradas período de ausência, o trabalhador é solicitado a selecionar um código de ausência. O trabalhador sai do trabalho às 15:30, que é o horário planejado de saída. Quando os registros do trabalhador são calculados e aprovados, o registro de ausência, junto com o código de ausência selecionado na entrada, aparecem para o horário entre 07:00 e 08:30.

No perfil de tempo, é possível configurar o tipo de registro **Registro de entrada** para que haja uma tolerância quando trabalhadores estiverem atrasados para o trabalho. Por exemplo, se você configurar uma tolerância de 5, o trabalhador será solicitado a fornecer um código de ausência apenas se ele registrar entrada após 07:05.

Nesse caso, como o trabalhador não tem um bom motivo para o atraso no trabalho, ele seleciona um código de ausência que é definido para a ausência ilegal. Um código de ausência é considerado aplicável para a ausência ilegal se a configuração da dedução de horas extras está habilitada para o grupo de ausências ao qual pertence o código de ausência. Para definir a configuração, selecione **Horário e presença** &gt; **Configuração** &gt; **Grupos** &gt; **Grupos de ausências** e a caixa de seleção **Deduzir hora extra**.

Veja como os registros do trabalhador para o dia aparecem na página **Aprovar** após o cálculo.

| Tipo de registro do diário         | Início    | Fim      | Hora |
|-----------------------------------|----------|----------|------|
| Ausência (ilegal - atrasado para o trabalho) | 07:00 | 08:30 | 1.5  |
| Registro de entrada                          | 08:30 | 08:30 |      |
| Trabalho de produção                    | 07:30 | 15:30 | 7.0  |
| Registro de saída                         | 15:30 | 15:30 |      |

Veja o item de pagamento resultante após a transferência dos registros.

| Tipo de salário     | Tipo de pagamento | Unidades de pagamento | Alíquota |
|---------------|----------|-----------|------|
| Período padrão | 1201     | 7:00      | 10   |

### <a name="scenario-2-the-worker-clocks-out-before-the-planned-clock-out-time-during-a-standard-time-period"></a>Cenário 2: o trabalhador registra saída antes do horário de saída planejado durante um período de tempo padrão

O trabalhador entra às 07:00 e sai cedo, às 13:00. Como 13:00 é antes do registro de saída planejado, às 15:30, e 01:00 é um período de tempo padrão, o trabalhador é solicitado a selecionar um código de ausência. O trabalhador seleciona um código de ausência para uma consulta médica, que é definida como ausência legal. A taxa de pagamento para ausência legal é definida nos contratos de pagamento para o tipo de registro **Ausência** (**Horário e presença** &gt; **Configuração** &gt; **Folha de pagamento** &gt; **Contratos de pagamento**).

Veja como os registros do trabalhador para o dia aparecem na página **Aprovar** após o cálculo.

| Tipo de registro do diário              | Início    | Fim      | Hora |
|----------------------------------------|----------|----------|------|
| Registro de entrada                               | 07:00 | 07:00 |      |
| Trabalho de produção                         | 07:00 | 13:00 | 4.0  |
| Registro de saída                              | 13:00 | 13:00 |      |
| Ausência (legal – consulta médica) | 13:00 | 15:30 | 3.5  |

Veja o item de pagamento resultante após a transferência dos registros.

| Tipo de salário     | Tipo de pagamento | Unidades de pagamento | Alíquota |
|---------------|----------|-----------|------|
| Período padrão | 1201     | 7,50      | 10   |

### <a name="scenario-3-the-worker-clocks-out-before-the-planned-clock-out-time-during-a-flex--period"></a>Cenário 3: o trabalhador registra saída antes do horário de saída planejado durante um período Flex-

O trabalhador entra às 07:00 e sai às 14:15, que está no período Flex- planejado. O tempo entre a hora de saída real e a hora de saída planejada não é considerado ausência, e o trabalhador não é solicitado a selecionar um código de ausência. O valor é deduzido da conta flexível do trabalhador, e o trabalhador recebe o pagamento durante a parte restante do período Flex-, entre 14:15 e 15:30.

Veja como os registros do trabalhador para o dia aparecem na página **Aprovar** após o cálculo.

| Tipo de registro do diário | Início    | Fim      | Hora |
|---------------------------|----------|----------|------|
| Registro de entrada                  | 07:00 | 07:00 |      |
| Trabalho de produção            | 07:00 | 14:15 | 7,25 |
| Registro de saída                 | 14:15 | 14:15 |      |

Veja o item de pagamento resultante após a transferência dos registros.

| Tipo de salário     | Tipo de pagamento | Unidades de pagamento | Alíquota |
|---------------|----------|-----------|------|
| Período padrão | 1201     | 8,50      | 10   |

### <a name="scenario-4-the-worker-clocks-in-late-and-clocks-out-after-the-planned-clock-out-time-during-an-overtime-period"></a>Cenário 4: o trabalhador entra tarde e sai após o horário de saída planejado durante um período de hora extra

O trabalhador entra às 09:30 e, para compensar seu atraso, ele trabalha horas extras e sai às 17:00. Como o trabalhador entrou tarde e compensou trabalhando mais tempo, a empresa não deseja pagar horas extras a ele pelas horas trabalhadas entre a saída planejada às 15:30 e a saída real às 17:00, apesar de esse período ser definido como hora extra no perfil de tempo.

Para lidar com esse cenário, o código de ausência pode ser configurado para reduzir horas extras do número de horas de ausência ilegal do trabalhador no mesmo dia. Selecione **Horário e presença** &gt; **Configuração** &gt; **Grupos** &gt; **Grupos de ausências** e a caixa de seleção **Deduzir hora extra** para deduzir horas extras das horas de ausência ilegal.

Veja como os registros do trabalhador para o dia aparecem na página **Aprovar** após o cálculo.

| Tipo de registro do diário         | Início    | Fim      | Hora |
|-----------------------------------|----------|----------|------|
| Ausência (ilegal - atrasado para o trabalho) | 07:00 | 09:30 | 1.5  |
| Registro de entrada                          | 09:30 | 09:30 |      |
| Trabalho de produção                    | 09:30 | 17:00 | 7,5  |
| Registro de saída                         | 17:30 | 17:30 |      |

Se a caixa de seleção **Deduzir hora extra** estiver marcada para o código de ausência selecionado, o pagamento de horas extras será deduzido das horas em que o trabalhador estava ilegalmente ausente. Nesse caso, os itens de pagamento a seguir são gerados após os registros serem transferidos.

| Tipo de salário     | Tipo de pagamento | Unidades de pagamento | Alíquota |
|---------------|----------|-----------|------|
| Período padrão | 1201     | 9:00      | 10   |
| Hora extra      | 1301     | 0,5       | 15   |

Aqui, 1,5 horas de ausência ilegal, das 07:00 às 09:30, deduzem as 2,0 horas extras, das 15:30 às 17:30. O resultado do registro é 1,5 horas do período padrão e 0,5 de horas extras.

Em contraste, se a caixa seleção **Deduzir hora extra** for desmarcada para o código de ausência selecionado, o pagamento de horas extras será concedido ao trabalhador, mesmo que ele esteja atrasado e tenha uma ausência ilegal. Nesse caso, os itens de pagamento a seguir são gerados após os registros serem transferidos.

| Tipo de salário     | Tipo de pagamento | Unidades de pagamento | Alíquota |
|---------------|----------|-----------|------|
| Período padrão | 1201     | 7,50      | 10   |
| Hora extra      | 1301     | 2.0       | 15   |

### <a name="scenario-5-the-worker-clocks-out-before-the-planned-clock-out-time-and-can-convert-the-absence-period-to-a-flex--period"></a>Cenário 5: o trabalhador sai antes do horário de saída planejado e pode converter o período de ausência em um período Flex-

O exemplo a seguir mostra como a conta flexível de um trabalhador pode ser reduzida convertendo o período de ausência em um período Flex-.

O trabalhador entra às 07:00 e sai às 13:00. Ele chegou a um acordo com a supervisora de folgar no fim de semana desde que deduza essas horas da sua conta flexível. Quando o trabalhador sai às 13:00, ele é solicitado a selecionar um código de ausência, pois o período de ausência referente ao restante do dia de trabalho que é afetado não faz parte de um período Flex- planejado. Para converter o restante do dia de trabalho em um período Flex-, o trabalhador pode selecionar um código de ausência que está configurado para reduzir sua conta flexível.

Para reduzir o saldo de horas flexíveis dos trabalhadores que registram a ausência em um dia de trabalho, selecione **Horário e presença** &gt; **Configuração** &gt; **Grupos** &gt; **Grupos de ausência** e a caixa de seleção **Reduzir limite flexível**.

Veja como os registros do trabalhador para o dia aparecem na página **Aprovar** antes do cálculo.

| Tipo de registro do diário | Início    | Fim      | Hora |
|---------------------------|----------|----------|------|
| Registro de entrada                  | 07:00 | 07:00 |      |
| Trabalho de produção            | 07:00 | 13:00 | 6,0  |
| Registro de saída                 | 13:00 | 13:00 |      |

Se o trabalhador selecionar um código de ausência para a ausência ilegal, veja a aparência do item de pagamento resultante após o registro ser transferido.

| Tipo de salário     | Tipo de pagamento | Unidades de pagamento | Alíquota |
|---------------|----------|-----------|------|
| Período padrão | 1201     | 6,00      | 10   |

Se o trabalhador selecionar um código de ausência para a ausência legal, e o código de ausência estiver configurado para reduzir sua conta flexível, veja a aparência dos itens de pagamento resultantes após a transferência dos registros.

| Tipo de salário     | Tipo de pagamento | Unidades de pagamento | Alíquota |
|---------------|----------|-----------|------|
| Período padrão | 1201     | 8,50      | 10   |

Nesse caso, há redução de horas no saldo flexível do trabalhador entre o horário de saída real e o horário de saída planejado (2,5 horas das 13:00 às 15:30).

> [!NOTE]
> Não é recomendável marcar as caixas de seleção **Deduzir limite flexível** e **Deduzir hora extra** para um código de ausência, porque essa configuração deduzirá horas ilegais de horas extras do trabalhador e, ao mesmo tempo, reduzirá a conta flexível do trabalhador.

### <a name="scenario-6-there-is-no-planned-absence-for-the-day-and-no-worker-attendance-for-the-day"></a>Cenário 6: não há ausência planejada para o dia, nem presença do trabalhador para o dia

Se o trabalhador não aparece para trabalhar em um dia útil, e não há ausência planejada para ele nesse dia, um código de ausência padrão é usado no cálculo dos registros do trabalhador. Para definir códigos de ausência padrão, selecione **Horário e presença** &gt; **Parâmetros de horário e presença**. Você pode selecionar um código de ausência nestes campos:

- Inserção automática de Flex-
- Inserção automática de ausência

Quando os registros diários são calculados para um trabalhador que está habilitado para horas flexíveis, o código de ausência especificado no campo **Inserção automática de flex-** é usado como um código de ausência padrão. Se o trabalhador não está habilitado para horas flexíveis, o código de ausência especificado no campo **Inserção automática de ausência** é usado. Se uma empresa tem uma combinação de trabalhadores habilitados para horas flexíveis e trabalhadores não habilitados para horas flexíveis, ambos os parâmetros devem ser definidos.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]