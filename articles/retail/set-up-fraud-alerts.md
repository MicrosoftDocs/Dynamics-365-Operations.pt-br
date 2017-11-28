---
title: Configurar alertas de fraude
description: "Este tópico explica como configurar regras para alertar representantes de atendimento ao cliente sobre informações potencialmente fraudulentas quando as ordens são processadas. Você também pode especificar códigos a serem usados para colocar ordens suspeitas manualmente ou manualmente em espera."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: f57cdb44d5ed3b078478cf47b74d1a79ba10323c
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-fraud-alerts"></a>Configurar alertas de fraude

[!include[banner](includes/banner.md)]

Este tópico explica como configurar critérios e regras para colocar ordens de venda potencialmente fraudulentas em espera para revisão adicional. A funcionalidade da revisão de fraude é usada para determinar a validade de informações em uma ordem de venda. Se as informações na ordem de venda parecem ser questionáveis com base em critérios e regras de fraude de uma organização, a ordem pode ser colocada em espera para revisão adicional por um administrador.

> [!NOTE]
> Esse recurso pode ser usado apenas com o processamento de ordens de vendas de canal do Retail Call Center. 

Quando o canal de Call Center é definido, **Habilitar Conclusão de Ordem** deve ser definido como **Sim**. Quando a conclusão de ordem está habilitada, os usuários podem exibir a recapitulação da ordem e clicar em **Enviar** para finalizar a ordem. Os usuários também terão opções para colocar manualmente em espera a ordem de venda da revisão de fraude. Ordens de venda inseridas por um usuário de Call Center são processadas através de regras e critérios da verificação de fraude durante o processo de envio.

Há dois tipos de critérios de fraude que o sistema referenciará para verificar se a ordem deve ser mantida para revisão de fraude:

-   **Regras estáticas** usam um valor específico, como um número de telefone, que foi inserido em uma lista de bloqueio, ou um endereço de email que foi sinalizado como usado nas últimas transações fraudulentas. Na página **Dados Estáticos de Fraude**, as informações de fraude podem ser adicionadas manualmente ou na importação de dados, com pontuações anexadas às informações fraudulentas. Se a verificação de fraude estiver ativada, cada ordem de venda inserida será comparada aos dados estáticos. Se os dados forem localizados no faturamento do cliente ou no endereço de entrega, ou se os dados forem localizados no endereço de entrega na linha de vendas, as pontuações de todas as correspondências exclusivas serão somadas.  
-   **Regras dinâmicas** são compostas de variáveis e condições definidas para essas variáveis. Com regras dinâmicas, outros critérios não definidos nas regras estáticas podem ser verificados. Instruções ”E/OU" mais complexas podem ser usadas para considerar várias condições para determinar se há uma correspondência positiva nos critérios de regras e na ordem de venda que estão sendo enviados. Por exemplo, se um usuário deseja manter para revisão de fraude todas as ordens para clientes que estejam ligados a um valor de grupo de cliente específico e que solicitaram um produto específico, as condições para validar o cliente e os produtos deverão ser definidas na página **Regras** com a condição “E”. A ordem só seria uma fraude se as duas condições fossem verdadeiras e se o valor de pontuação atribuído à regra colocasse a pontuação total de fraude da ordem em uma pontuação mínima de fraude, conforme definido em parâmetros do Call Center.

Um usuário de call center também pode inserir manualmente uma ordem na fila de bloqueio de fraude. Se o usuário que inserir a ordem acreditar que o cliente que fez o pedido pode ser suspeito e desejar que outra pessoa verifique a validade da ordem antes de processá-la, o usuário que inserir a ordem poderá escolher a opção **Bloqueio de Fraude Manual** no menu suspenso **Bloqueio** na página **Resumo da Ordem de Venda** (ela aparece após a função **Concluir** ser chamada). O usuário será solicitado a inserir uma nota para explicar como percebem que a ordem pode ser fraudulenta, de modo que o revisor tenha mais contexto.

Todas as ordens retidas por bloqueio manual de fraude ou por cálculo sistemático de contagens de fraude aparecerão na página **Bloqueios de ordem**, onde a ordem pode ser examinada e, depois, cancelada ou liberada para processamento.

> [!NOTE]
> O uso de várias regras ou de regras muito complexas resultará na queda de desempenho do sistema quando as ordens de venda forem enviadas. O recurso de alerta de fraude não foi otimizado para tratar um grande volume de entradas de dados estáticos de fraude e muitas regras ativas. Lembre-se de que cada regra é avaliada durante a função de envio da entrada de ordens de venda do call center. As regras são avaliadas no cabeçalho de ordem de venda e em todas as linhas da ordem. Quanto mais regras e mais complexas forem as instruções de regras, mais demorado será o processamento. Se você tem muitas linhas de item na ordem, e muitas entradas de dados de regras ativas e entradas de dados estáticos, esse processo sistemático de examinar e validar todos os dados e calcular uma contagem de fraude pode ter um sério impacto no desempenho.  As organizações que usam este recurso devem sempre testar e confirmar que o tempo de processamento do envio da ordem é aceitável antes de aplicar alterações às regras ou critérios estáticos de fraude no ambiente de produção.

