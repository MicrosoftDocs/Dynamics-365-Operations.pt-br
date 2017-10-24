---
title: "Registro de Horário e presença"
description: "Os trabalhadores de registro de tempo podem inserir diferentes tipos de registros de tempo, por exemplo, registro de entrada e de saída em atividades indiretas e registro de ausência. Este artigo descreve os registros, o cálculo, a aprovação e o uso do fluxo de trabalho para adicionar a estrutura e a aprovação automatizada ao processo de aprovação de folhas de ponto."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmWorker, JmgCalcApprovePickDialog, JmgGroupApprove, JmgGroupCalc, JmgGroupSigningTable, JmgRegistration, JmgTimeCalcParmeters, WorkflowTableListPageRnr
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 53351
ms.assetid: 885b0cdf-53d7-4cb4-92fe-da1b9e32b39f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 83603b1f8d20c18b7f10cd7224d491b558ee1b8b
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="time-and-attendance-registration"></a>Registro de Horário e presença

[!include[banner](../includes/banner.md)]


Os trabalhadores de registro de tempo podem inserir diferentes tipos de registros de tempo, por exemplo, registro de entrada e de saída em atividades indiretas e registro de ausência. Este artigo descreve os registros, o cálculo, a aprovação e o uso do fluxo de trabalho para adicionar a estrutura e a aprovação automatizada ao processo de aprovação de folhas de ponto. 

<a name="registrations"></a>Registros
-------------

Nas empresas que usam Horário e presença, os trabalhadores devem registrar o horário que passam no trabalho, bem como a presença. Algumas empresas só podem exigir que os trabalhador registrem a entrada e a saída. Em outras empresas, pode ser que os trabalhadores sejam obrigados a registrar o consumo de tempo em atividades reais que eles executam, bem como os intervalos. Os usuários destinados a Tempo e presença são:
-   Trabalhadores, que são obrigados a registrar tempo e presença em intervalos regulares, por exemplo, diariamente, semanalmente ou quinzenalmente.
-   Os supervisores, os gerentes e os responsáveis pela folha de pagamento que calculam, aprovam e transferem registros do trabalhador para processamento adicional.

| **Nota**                                                                                                                                                                                                                                                    |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Se você executar Horário e presença juntos com a execução da Fabricação, todos os registros em projetos, atividades de projeto, atividades indiretas, códigos de ausência e hora extra, e o horário flexível serão registrados e usados para calcular a folha de pagamento nos dois módulos. |

## <a name="time-registrations-workers"></a> Trabalhadores de registros de hora
Para conseguir registrar horário e presença, os trabalhadores devem ser configurados como trabalhadores com registro de tempo na empresa na qual eles estão empregados.

Depois da instalação, os trabalhadores podem inserir diferentes tipos de registros.

-   Registrar sua entrada e de saída ou chegada e saída do trabalho.
-   Tempo e consumo de itens em trabalhos de produção.
-   Tempo usado em uma máquina no chão de fábrica, se a máquina tiver sido definida como um recurso.

| **Nota**                                                                                                                                                                                                                      |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Um trabalhador pode ser atribuído automaticamente aos registros de horas que são feitos em uma máquina específica no chão de fábrica, se o trabalhador optar por trabalhar como assistente para a máquina quando ele iniciar o trabalho de produção. |

-   Registros de tempo em projetos e em atividades de projeto.
-   Registrando taxas e consumo de itens do projeto nos respectivos diários de taxas do projeto e diários de itens do projeto.
-   Ausência planejada.
-   Ausência ao chegar tarde para trabalhar ou sair mais cedo do que o planejado.
-   As interrupções de trabalho, registradas manualmente ou automaticamente calculadas pelo sistema.
-   As atividades indiretas, que são atividades não produtivas nas quais um trabalhador pode se envolver durante um dia útil. Exemplos dessas atividades são reuniões ou limpeza do espaço de trabalho.
-   Hora extra, que pode ser registrada como horas extras, horário flexível ou hora extra.

## <a name="adding-clockout-registrations"></a>Adicionando registros de saída
Se um trabalhador esquecer de registrar a saída no fim do dia de trabalho, o registro ausente poderá ser adicionado, executando um trabalho em lote. O sistema comparará a hora de entrada e a hora de saída, de acordo com o perfil do trabalhador associado, e inserirá automaticamente o registro de saída ausente para corresponder à hora final do perfil. Ambos os registros de entrada e de saída são essenciais para o cálculo e a aprovação subsequentes dos registros de horas antes que possam ser transferidos para a folha de pagamento.

## <a name="calculating-registrations"></a>Calculando registros
Quando um trabalhador do registro é atribuído a um grupo de cálculo que geralmente se relacione a uma equipe, a um turno, ou a um grupo de trabalho específico. O gerente da equipe ou o supervisor valida normalmente os registros feitos por trabalhadores e, portanto, também é a pessoa responsável por executar o cálculo dos grupos de cálculo respectivos, diariamente. Como parte do processo de cálculo, gerente de equipe ou o supervisor pode:
-   Corrigir registros incorretos. Por exemplo, alterar os códigos de alternância e ajustar comentários sobre trabalhos de produção.
-   Adicionar registros ausentes. Por exemplo, criar registros de saída e criar transações de ausência.
-   Excluir registros incorretos.

Como o tempo registrado devem corresponder ao perfil de tempo do trabalhador antes de calcular os registros, você deve substituir o perfil de tempo de trabalho de qualquer funcionário que tenha uma exceção ao perfil do período de trabalho. Nos casos, em que o perfil do trabalhador é turno diurno, e o trabalhador concordou em trabalhar em um turno noturno sem o pagamento de horas extras, o gerente da equipe ou o supervisor devem substituir o perfil do trabalhador padrão, para calcular o tempo de trabalho como taxa noturna padrão e não como hora extra. O cálculo também exibirá um erro, se um registro de ausência estiver ausente. Deve ser adicionado antes de o cálculo ser concluído.

## <a name="approving-registrations"></a>Aprovando registros
Da mesma forma que você atribui um grupo de cálculo ao trabalhador de registro de hora, pode dever atribuir um grupo de aprovação também. Geralmente, o grupo de cálculo será específico de uma equipe, turno ou grupo de trabalho. Você deve aprovar os registros de horas que foram calculados corretamente – isso significa fazer um cálculo sem erros – antes que os itens de pagamento possam ser gerados, que posteriormente poderão ser transferidos para um sistema de folha de pagamento. O administrador da folha de pagamento fará normalmente a aprovação dos registros, e antes da aprovação poderá:
-   Substituir os contratos de pagamento de determinados trabalhadores.
-   Adicionar gratificações manuais.
-   Digitar informações adicionais sobre registros de ausência.

| **Nota**                                                                                                                                                                             |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Caso tenha sido calculada para trabalhadores específicos, a hora extra pode ser alocada para trabalhos específicos durante o dia. Isso é relevante se o custo de trabalho for calculado com base no pagamento do trabalhador. |

## <a name="approving-registrations-using-workflow"></a>Aprovando registros usando o fluxo de trabalho
Você pode configurar um processo de aprovação do fluxo de trabalho que aprove automaticamente os registros que estejam de acordo com as regras do fluxo de trabalho, deixando somente os desvios para serem tratados manualmente. Se a aprovação do fluxo de trabalho estiver ativada, o gerente de equipe ou o supervisor envia os registros calculados para aprovação. O processo de fluxo de trabalho gerará as aprovações e tarefas apropriadas e, em seguida, as atribuirá a usuários e funções corretos, conforme identificadas no fluxo de trabalho. Há duas aprovações de fluxo de trabalho para a horário e presença.

| Fluxo de trabalho                                  | Finalidade                                                                                                   | Tipo de registro                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Total dos dias de horário e presença            | O fluxo de trabalho valida os registros, por exemplo, o número previsto de horas de trabalho para o dia. |                                                                                                                                                                                                                                                       |
| Registro do diário de horário e presença. | O fluxo de trabalho valida cada tipo de registro para a data do registro.                           | Horário e presença • Entrada • Saída • Ausência • Interrupção • Código de alternância • Projeto • Atividade de projeto • Trabalhos de produção da atividade indireta • Fila antes • Instalação • Processo • Sobreposição • Transporte • Fila • Iniciar assistência • Interromper assistência |

 

## <a name="transferring-approved-registrations"></a>Transferindo registros aprovados
Após a aprovação dos registros é possível transferi-los para um trabalho de folha de pagamento periódico. Um registro transferido é lançado em uma atividade ou trabalho ao qual esteja relacionado, por exemplo, a uma ordem de produção ou um projeto. As transações da folha de pagamento são geradas para cada trabalhador com base nos registros.  

## <a name="reversing-transferred-registrations"></a>Revertendo registros transferidos
A tarefa de reverter transações - revertendo-as de volta - pode ser realizada até o momento em que a transferência de pagamento do período da folha de pagamento é executada. Isso significa que os dados da folha de pagamento foram transferidos para um arquivo externo. Quando revertidos, todos os registros são retirados e todas as transações lançadas em ordens ou projetos de produção são compensadas e neutralizadas.

| **Nota**                                                 |
|----------------------------------------------------------|
| O arquivo externo pode ser importado para um sistema de folha de pagamento. |

## <a name="registrations-in-electronic-timecards"></a>Registros de cartões de ponto eletrônicos
Os trabalhadores com tarefas de trabalho não requerem comentário imediato, como é o caso em trabalhos de produção, mas que trabalham em atividades de projeto, podem tirar proveito de usar o cartão de ponto eletrônico. Os cartões de ponto eletrônicos oferecem a flexibilidade para inserir registros que a qualquer momento e da melhor maneira em seu plano de negócios – diariamente, semanalmente, ou quando um trabalhador estiver no escritório novamente após ficar ausente. Para usar cartões de ponto eletrônicos ou esses trabalhador, você deve especificar, Usar cartão de ponto, nos detalhes do trabalhador Os cartões de ponto eletrônicos habilitam o trabalhador para registrar:

-   Data
-   Tipo de registro
-   Referência de trabalho, como projeto, atividade indireta ou ordem de produção
-   Ident. do trabalho
-   Consumo de tempo
-   Taxas do projeto
-   Itens do projeto





