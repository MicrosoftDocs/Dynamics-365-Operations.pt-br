---
title: Grupos flexíveis
description: Este tópico descreve como os grupos flexíveis são usados em Horário e presença.
author: johanhoffmann
manager: tfehr
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgFlexGroup, JmgFlexCorrection
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: c71ebab0788b6c5d7466a5d71e3c72a7e86e41db
ms.sourcegitcommit: 175f9394021322c685c5b37317c2f649c81a731a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/21/2020
ms.locfileid: "3826494"
---
# <a name="flex-groups"></a>Grupos flexíveis

[!include[banner](../includes/banner.md)]

As horas de trabalho flexíveis deixam as empresas minimizar pagamentos de horas extras ao oferecer para os trabalhadores tempo adicional de folga durante os períodos em que a carga de trabalho está baixa. Esse recurso é relevante, por exemplo, em segmentos que experimentam alterações sazonais na carga de trabalho.

Você pode usar grupos flexíveis para definir as seguintes regras e princípios para as horas flexíveis de um trabalhador:

- Regras para regulamentações flexíveis
- Princípio para cálculo do saldo flexível do trabalhador

## <a name="set-up-flexible-working-hours-in-flex-groups"></a>Configurar horas de trabalho flexíveis em grupos flexíveis

- Selecione **Horário e presença** \> **Configuração** \> **Grupos** \> **Grupos flexíveis** para configurar grupos flexíveis para horas flexíveis.

## <a name="associate-workers-with-flex-groups"></a>Associar trabalhadores a grupos flexíveis

- Selecione **Horário e presença** \> **Configuração** \> **Trabalhadores de registro de horas**.

## <a name="rules-for-flex-regulations"></a>Regras para regulamentações flexíveis

Você pode usar regras para regulamentações flexíveis para definir limites flexíveis, ou o número mínimo e máximo de horas permitidas na conta flexível do trabalhador. Os limites flexíveis são configurados no grupo flexível. Quando os limites flexíveis são excedidos, o saldo flexível e o pagamento de um trabalhador podem ser ajustados.

Se a flexibilidade mínima permitida de um trabalhador for excedida (ou seja, se o número de horas na conta flexível estiver abaixo do mínimo especificado), você poderá usar estes métodos para ajustar o saldo flexível do trabalhador fazendo uma regulamentação flexível:

- A conta flexível do trabalhador pode ser ajustada ao mínimo permitido especificado, mas sem deduzir do pagamento do trabalhador o número de horas que a conta flexível está abaixo do mínimo permitido.
- Pode ser deduzido do pagamento do trabalhador o número de horas que a conta flexível está abaixo do mínimo permitido. Essa dedução é feita por meio da geração de itens de pagamento para um tipo de pagamento específico com uma unidade de pagamento positiva ou negativa.

Se o máximo de flexibilidade permitida do trabalhador for excedido, você poderá usar estes métodos para ajustar o saldo flexível do trabalhador fazendo uma regulamentação flexível:

- A conta flexível do trabalhador pode ser ajustada ao máximo permitido especificado, mas sem compensar o pagamento do trabalhador pelo número de horas que ele trabalhou acima do máximo permitido.
- O número de horas que o trabalhador trabalhou acima do máximo permitido pode ser convertido em pagamento. Essa conversão é feita por meio da geração de itens de pagamento para um tipo de pagamento específico.

Você pode ajustar um saldo flexível nas seguintes ocasiões:

- Quando um arquivo de pagamento baseado em dados de folha de pagamento é exportado usando o trabalho **Transferir pagamento**. Os dados da folha de pagamento são gerados quando você transfere o registro do trabalhador da página **Aprovar**.
- Quando o trabalho **Ajustar saldo flexível** é processado.

> [!NOTE]
> As regulamentações flexíveis não ocorrem durante a aprovação e a transferência diárias de registros do trabalhador na página **Aprovar**.

## <a name="principle-for-calculating-a-workers-flex-balance"></a>Princípio para cálculo do saldo flexível de um trabalhador

O princípio para calcular as horas pelos quais o saldo flexível do trabalhador é ajustado é configurado no grupo flexível. Selecione **Horário e presença** \> **Configuração** \> **Grupos** \> **Grupos flexíveis**. 

Os dois princípios a seguir podem ser usados:

- **Hora** – as horas flexíveis são calculadas apenas por meio do horário registrado do trabalhador para o dia. Quando os registros diários do trabalhador são calculados, o número de horas do máximo e do mínimo de horas flexíveis para o dia será calculado com base nas zonas Flex+ e Flex- definidas no perfil de horário do trabalhador.
- **Tipos de pagamento** – as horas flexíveis do trabalhador são calculadas com base ganhos dos tipos de pagamento para o máximo e o mínimo de horas flexíveis definidos no contrato de pagamento do trabalhador. O contrato de pagamento é associado ao trabalhador de registro de tempo. Talvez você queira usar os tipos de pagamento para gerenciar as contas flexíveis se, por exemplo, seja necessário aumentar a conta flexível de um trabalhador por um fator específico em uma ou mais zonas flexíveis.

### <a name="scenario-1-adjusting-a-workers-pay-and-flex-account-because-the-allowed-flex-minimum-is-exceeded"></a>Cenário 1: ajuste do pagamento e da conta flexível de um trabalhador porque o mínimo flexível permitido foi excedido

Um trabalhador que pode trabalhar horas flexíveis tem uma conta flexível negativa.

- **Conta flexível:** -4

O trabalhador está associado a um grupo flexível com a seguinte configuração:

- **Limite mínimo flexível:** -0,5
- **Tipo de pagamento mínimo:** 1302
- **Fator de tipo de pagamento:** -1,00

Como indica a diferença entre a conta flexível do trabalhador e seu mínimo flexível permitido, o trabalhador excedeu seu mínimo flexível permitido em 3,5 horas.

Quando o administrador da pagamento de pagamento transferir os dados de pagamento do trabalhador ao executar o trabalho **Transferir para pagar** ou **Ajuste flexível** , serão feitos estes ajustes:

- A conta flexível do trabalhador será ajustada em 3,5 horas. Portanto, o saldo flexível de -4,0 horas é ajustado para o mínimo flexível do trabalhador de -0,5 horas.
- Um item de pagamento para o tipo de pagamento 1302 é criado. Esse item de pagamento tem uma unidade de pagamento de -3,5 horas que será deduzida do pagamento do trabalhador. Nesse caso, a unidade de pagamento é um número negativo, já que o ajuste positivo de 3,5 horas é multiplicado pelo fator de tipo de pagamento negativo -1,0 definido no grupo flexível. Esse item de pagamento fará parte do arquivo de pagamento gerado pelo trabalho **Transferir para pagamento**.

### <a name="scenario-2-adjusting-a-workers-pay-and-flex-account-because-the-allowed-flex-maximum-is-exceeded"></a>Cenário 2: ajuste do pagamento e da conta flexível de um trabalhador porque o máximo flexível permitido foi excedido

Um trabalhador que pode trabalhar horas flexíveis tem uma conta flexível positiva.

- **Conta flexível:** 6

O trabalhador está associado a um grupo flexível com a seguinte configuração:

- **Limite flexível máximo:** 2,0
- **Tipo de pagamento mínimo:** 1302
- **Fator de tipo de pagamento:** -1,0

Como indica a diferença entre a conta flexível do trabalhador e seu máximo flexível permitido, o trabalhador excedeu seu máximo flexível permitido em 4,0 horas.

Quando o administrador da pagamento de pagamento transferir os dados de pagamento do trabalhador ao executar o trabalho **Transferir para pagar** ou **Ajuste flexível** , serão feitos estes ajustes:

- A conta flexível do trabalhador será ajustada em -4,0 horas. Portanto, o saldo flexível de 6,0 horas é ajustado para o máximo flexível do trabalhador de 2,0 horas.
- Um item de pagamento para o tipo de pagamento 1302 é criado. Esse item de pagamento tem uma unidade de pagamento de 4,0 horas que será adicionada ao pagamento do trabalhador. Nesse caso, a unidade de pagamento é um número positivo, já que o ajuste negativo de 4,0 horas é multiplicado pelo fator de tipo de pagamento negativo -1,0 definido no grupo flexível. Esse item de pagamento fará parte do arquivo de pagamento gerado pelo trabalho **Transferir para pagamento**.

### <a name="scenario-3-managing-a-workers-flex-balance-based-on-pay-types"></a>Cenário 3: gerenciamento do saldo flexível de um trabalhador com base em tipos de pagamento

Como nós explicamos anteriormente, as contas flexíveis podem ser gerenciadas com base na hora de registro nas zonas Flex+ e Flex- definidas no perfil de horário do trabalhador ou nos tipos de pagamento definidos nos contratos de pagamento do trabalhador. Se os tipos de pagamento forem usados, a conta flexível de um trabalhador será ajustada pelos itens de pagamento gerados quando você transfere o registro do trabalhador da página **Aprovar** . Talvez você queira usar os tipos de pagamento para gerenciar as contas flexíveis se, por exemplo, seja necessário aumentar a conta flexível de um trabalhador por um fator específico em uma ou mais zonas flexíveis.

Este cenário usa o perfil flexível a seguir, que representa um dia útil.

| Tipo de perfil  | Início    | Fim      |
|---------------|----------|----------|
| Mais flexível         | 12:00 | 08:00 |
| Registro de entrada      | 08:00 | 08:00 |
| Menos flexível         | 08:00 | 09:00 |
| Período padrão | 09:00 | 11:30 |
| Interrupção paga    | 11:30 | 12:00 |
| Menos flexível         | 12:00 | 04:00 |
| Registro de saída     | 04:00 | 04:00 |
| Mais flexível         | 04:00 | 12:00 |

Nesse caso, você quer gerenciar o saldo flexível do trabalhador com base em tipos de pagamento. Portanto, você deve definir a opção **Baseado em tipos de pagamento** como **Sim** no grupo flexível do trabalhador.

Para contabilizar as horas flexíveis, você também deve definir um novo tipo de pagamento. Para este cenário, o tipo de pagamento é chamado de **FlexCnt**.

| Tipo de pagamento | descrição  |
|----------|--------------|
| FlexCnt  | Contador flexível |

Em seguida, siga estas etapas para configurar um tipo de pagamento e adicionar linhas do novo tipo a um perfil de pagamento.

1. Selecione **Horário e presença** \> **Configuração** \> **Grupos** \> **Grupos flexíveis** e então selecione **Novo**.
2. No campo **Flex+** e no campo **Flex-** , especifique o novo tipo de pagamento, **FlexCnt**.
3. Selecione **Horário e presença** \> **Configuração** \> **Contratos de pagamento** e então **Linhas do contrato**.
4. Para **Segunda-feira**, para o tipo de perfil **Flex+** , adicione as três linhas a seguir.

    | Tipo de pagamento | descrição  | Hora inicial | Hora final  | Mínimo | Máximo | Fator |
    |----------|--------------|-----------|----------|---------|---------|--------|
    | FlexCnt  | Contador flexível | 12:00  | 06:00 | 00:00   | 00:00   | 1.00   |
    | FlexCnt  | Contador flexível | 06:00  | 12:00 | 00:00   | 02.00   | 1,50   |
    | FlexCnt  | Contador flexível | 06:00  | 12:00 | 02.00   | 06.00   | 2.00   |

    > [!NOTE]
    > Cada linha é usada para um intervalo de tempo diferente e tem um fator diferente. As horas flexíveis em que o trabalhador trabalha em um intervalo de tempo são multiplicadas pelo fator daquela linha. Por exemplo, as horas trabalhadas das 18h às 20h são multiplicadas por 1,50. O fator é especificado no campo **Fator** na guia **Geral** da página **Linhas de contrato de pagamento**.

O trabalhador insere os registros do dia a seguir.

| Tipo de registro do diário | Início    | Fim      |
|---------------------------|----------|----------|
| Registro de entrada                  | 07:00 | 07:00 |
| Trabalho de produção            | 07:00 | 09:00 |
| Registro de saída                 | 09:00 | 09:00 |

O valor a ser pago é calculado na página **Aprovar** , com base no registro do trabalhador. Após o cálculo do registro, você poderá exibir o resultado na guia **Horas**. Para este cenário, você está interessado nos campos a seguir.

| Flex + | Flex - | Hora  | Pagar hora |
|--------|--------|-------|----------|
| 6,00   | 0,00   | 13,50 | 08.00    |

O valor do horário Flex+ é de seis horas, e o cálculo se baseia nas zonas flexíveis do perfil de horário. Esse valor consiste em uma hora do período Flex+ das 7h às 8h e cinco horas do horário Flex+ das 16h às 21h.

Quando você transferir os registros, observará que o valor do período Flex+ é alterado de 6,0 horas para 8,0 horas.

| Flex + | Flex - | Hora  | Pagar hora |
|--------|--------|-------|----------|
| 8,00   | 0,00   | 13,50 | 08,00    |

Essa alteração ocorre após a transferência porque as horas flexíveis foram calculadas com base nos tipos de pagamento em vez de no tempo. A tabela a seguir mostra como as oito horas são calculadas.

| De     | Para       | Hora | Fator    | Conta flexível |
|----------|----------|------|-----------|--------------|
| 07:00 | 08:00 | 1    | 1         | 1            |
| 04:00 | 06:00 | 2    | 1         | 2            |
| 06:00 | 08:00 | 2    | 1.5       | 3            |
| 08:00 | 09:00 | 1    | 2         | 2            |
|          |          |      | **Total** | **8**        |
