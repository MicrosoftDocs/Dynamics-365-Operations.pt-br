---
title: Registro de ausência em Horário e presença
description: Este tópico explica como tratar registros de ausência em Horário e presença.
author: johanhoffmann
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JMGParameters, JmgAbsenceCalendar
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 961b87fb066018f9f6ecc3dcc3cc88e64574bb64
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5246540"
---
# <a name="absence-registration-in-time-and-attendance"></a>Registro de ausência em Horário e presença

[!include [banner](../includes/banner.md)]

Este tópico descreve os conceitos de ausência e explica como tratar ausências em Horário e presença.

## <a name="absence-that-is-based-on-regular-work-hours"></a>Ausência que é baseada em horas normais de trabalho

Os funcionários são considerados ausentes pelas horas que não trabalharem durante as horas normais de trabalho. As horas normais de trabalho são definidas no perfil de horário padrão de um trabalhador.

Por exemplo, um trabalhador está trabalhando em um perfil diurno com entrada às 7:00 e saída às 15:00. Se o trabalhador entrar às 9:00, considera-se que ele esteve ausente das 7:00 às 9:00 nesse dia.

Neste caso, é solicitado que os trabalhadores insiram um motivo para a ausência. É possível especificar um motivo selecionando um código de ausência.

## <a name="absence-codes"></a>Códigos de ausência

Os códigos de ausência definem vários tipos de ausência. Os códigos de ausência são definidos pela empresa.

Várias regras podem ser aplicadas aos códigos de ausência. Por exemplo, um código de ausência pode ser configurado para conceder ou deduzir o pagamento.

Por exemplo, a empresa define um código de ausência **Atraso** que os trabalhadores usarão se chegarem atrasados e não tiverem um bom motivo. A empresa também define um código de ausência **Curso interno** que os funcionários usam para horas usadas para a participação em cursos internos. Esses códigos de ausência podem ser configurados de forma que **Atraso** seja deduzido do pagamento de um trabalhador mas **Curso interno** não seja deduzido.

Você pode configurar códigos de ausência automáticos. Esses códigos de ausência podem ser usados para calcular o horário de um trabalhador quando não houver ausências registradas. O perfil de horário do trabalhador determina se o código de ausência para horário padrão ou horário flexível será usado.

### <a name="set-up-standard-time-and-flex-time"></a>Configurar horário padrão e horário flexível

- Configure os parâmetros para horário padrão e horário flexível usando as opções **Inserção automática de ausência** e **Inserção automática de flex-** na página **Parâmetros de horário e presença**.

## <a name="absence-groups"></a>Grupos de ausências

Os códigos de ausência são colocados em grupos de ausência. Você usa grupos de ausência para agrupar códigos de ausência com características em comum. Exemplos incluem códigos de ausência para uma ausência legal ou uma ausência por causa de uma consulta médica, convocação para ser membro de júri ou um filho doente.

## <a name="planned-absence"></a>Ausência planejada

Se souber que um trabalhador estará ausente por um período, como futuras férias, você poderá usar a ausência planejada. Você configura a ausência planejada definindo o código de ausência para que ele considere a ausência planejada. Ao configurar uma ausência planejada, não será solicitado que você insira um código de ausência durante o período de ausência em que os registros de horas do usuário serão calculados. A ausência planejada pode ser definida para um único trabalhador, ou você pode definir um trabalho em lotes para atualizar em massa as ausências planejadas de trabalhadores.

### <a name="set-up-planned-absence"></a>Configurar ausência planejada

1. Selecione **Recursos Humanos** &gt; **Trabalhadores** &gt; **Funcionários** e selecione um funcionário.
2. Selecione **Tempo** &gt; **Atribuição de Tempo** &gt; **Registro de tempo de ausência** e configure a ausência planejada.

## <a name="interrupted-planned-absence"></a>Ausência planejada interrompida

Se você aplicar a opção **Interromper** quando tiver configurado uma ausência planejada, ela será interrompida se o trabalhador se conectar durante o período de ausência planejada. A ausência planejada será marcada como **Interrompida** e não terá nenhum efeito sobre os cálculos futuros.

### <a name="set-up-a-planned-absence-for-interruption"></a>Configurar uma ausência planejada para interrupção

1. Abra a página **Registro de tempo de ausência** conforme descrito no procedimento para configurar a ausência planejada.
2. Selecione **Interromper**.

A opção **Interromper** é aplicada quando as horas são registrados pelo terminal ou pelo dispositivo da loja. A opção não se aplica se os registros forem inseridos nas páginas de aprovação e cálculo, ou na página **Cartão de ponto eletrônico**.

## <a name="examples-of-the-use-of-absence-in-a-flex-profile"></a>Exemplo de uso de ausências em um perfil flexível

Os três exemplos a seguir mostram como a ausência é calculada em um perfil com períodos flexíveis.

Os exemplos usam o perfil a seguir.

| Registro de entrada | Período padrão    | Interrupção             | Período padrão | Menos flexível        | Registro de saída | Mais flexível        |
|----------|------------------|-------------------|---------------|--------------|-----------|--------------|
| 8:00     | 9:00 às 11:30 | 11:30 às 12:00 | 12:00 às 15:00 | 15:00 às 16:00 | 16:00      | 16:00 às 18:00 |

### <a name="example-1-signing-out-during-a-flex--period"></a>Exemplo 1: Desconectar-se durante um período Flex-

O trabalhador entra às 8:00 e sai às 15:30. Nesse caso, como o trabalhador registra a saída durante um período Flex-, nenhuma ausência é calculada, e meia hora é deduzida do saldo flexível do trabalhador.

### <a name="example-2-signing-out-in-during-standard-time-period"></a>Exemplo 2: Desconectar-se durante o período de tempo padrão

O trabalhador entra às 8:00 e sai às 14:30. Nesse caso, como o trabalhador registra a saída durante o período de tempo padrão, a ausência é calculada das 14:30 às 16:00, e um período de ausência de 1,5 hora é registrado. Um código de ausência para esse período é obrigatório.

### <a name="example-3-signing-out-during-a-flex-period"></a>Exemplo 3: Desconectar-se durante um período Flex+

O trabalhador entra às 8:00 e sai às 16:30. Nesse caso, como o trabalhador registra a saída durante um período Flex+, nenhuma ausência é calculada, e meia hora é adicionada do saldo flexível do trabalhador.

## <a name="absence-in-the-calculation-and-approval-process"></a>Ausência no processo de cálculo e de aprovação

Os registros de horas do trabalhador devem ser calculados e aprovados antes de serem transferidos para um sistema de folha de pagamento como itens de pagamento.

Um aprovador pode modificar os registros de horas do trabalhador. Ele poderá alterar até mesmo as ausências que o trabalhador registrou. Se ele inserir manualmente um período de tempo que tenha um código de ausência, o código de ausência para o período não será substituído pelo código padrão de ausência dos parâmetros de Horário e presença.

Por exemplo, um trabalhador entra às 10:00 e seleciona um código de ausência que indica que ele está atrasado. Depois, o trabalhador informa seu supervisor que esteve em consulta médica das 8:00 às 10:00. Uma consulta médica não deve causar dedução no pagamento do trabalhador. Portanto, nesse caso, o supervisor poderá ajustar as duas horas de ausência de 8:00 às 10:00 inserindo manualmente um código de ausência que indique doença por essas duas horas.

### <a name="calculate-and-approve-absence"></a>Calcular e aprovar a ausência

- Selecione **Horário e presença** &gt; **Revisar e aprovar** &gt; **Aprovar ou Calcular**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]