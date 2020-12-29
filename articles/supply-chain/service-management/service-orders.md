---
title: Ordens de serviço
description: Uma ordem de serviço representa uma visita de um técnico de serviço a um local de cliente em uma data específica.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3b049b166edf2b5a318a4b1af85e7f74cfe433f2
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4421868"
---
# <a name="service-orders"></a>Ordens de serviço   

[!include [banner](../includes/banner.md)]


Uma ordem de serviço representa uma visita de um técnico de serviço a um local de cliente em uma data específica. Cada ordem de serviço consiste em uma ou mais linhas de ordem de serviço. As linhas da ordem de serviço representam as horas de trabalho que deve ser executadas pelo técnico de serviço e os itens, despesas, e taxas relacionados.

Você pode anexar tarefas e objetos a uma linha de ordem de serviço. Você poderá agrupar linhas de ordem de serviço por tarefa ou por objeto. Também é possível anexar itens listados no estoque a linhas de ordem de serviço.

## <a name="create-service-orders"></a>Criar ordens de serviço

Você pode criar ordens de serviço baseadas em um contrato de serviço e as linhas que estão contidas nesse contrato. No entanto, você pode criar ordens de serviço associadas a um contrato de serviço somente no período especificado no contrato. Por exemplo, se um contrato de serviço é válido para o ano civil de 2011, você pode criar ordens de serviço para o contrato a partir do dia 1 de janeiro de 2011 ao dia 31 de dezembro de 2011.

Você também pode criar ordens de serviço individualmente, sem para associá-las a um contrato. Essas ordens de serviço podem ser usadas para manusear visitas não programadas ou ocasionais de serviço. Por exemplo, no mês de março, seu cliente deseja que um serviço seja realizado em duas máquinas, além das máquinas que são especificadas no contrato de serviço. Para essa tarefa, você cria ordens de serviço mas não as associa a um contrato.


> [!NOTE]
> <P>Para criar ordens de serviço que não estão associadas a um contrato de serviço, você deve marcar a caixa de seleção <STRONG>Permitir sem contrato de serviço</STRONG> no formulário <STRONG>Parâmetros de gerenciamento de serviços</STRONG>.</P>

**Cenário**

O cenário a seguir descreve outra situação na qual é útil criar uma ordem de serviço que não esteja associada a um contrato de serviço.

A despachante da empresa recebe uma chamada de solicitação de serviço de emergência em um elevador. Não há tempo para configurar um contrato de serviço e um projeto do serviço. Portanto, o despachante cria uma ordem de serviço diretamente no formulário **Ordens de serviço**, anexa a ordem de serviço a um projeto existente, e cria as linhas da ordem de serviço. O despachante também cria uma tarefa ou relação de objeto para uma ordem de serviço existente, para registrar o servo que não é relacionado ao contrato de serviço. Para obter mais informações, consulte [Criar ordens de serviço manualmente](create-service-orders-manually.md) e [Criar relações de tarefa de serviço](create-service-task-relations.md).

## <a name="monitor-the-progress-of-service-orders"></a>Monitorar o progresso das ordens de serviço

Para monitorar o progresso da ordem de serviço nas diferentes equipes e processos de trabalho, você pode configurar um sistema de etapas e códigos de motivos para as ordens de serviço. Para cada fase, você pode especificar as ações que serão permitidas. Para obter mais informações, consulte [Criar códigos de motivo](create-reason-codes.md).

**Exemplo**

Uma ordem de serviço é aprovada pelo despachante. O despachante atualiza a fase da ordem de serviço e especifica um código de motivo que indica que a ordem de serviço foi liberada para o técnico de serviço. O técnico vai para o local do cliente e executa o serviço.

## <a name="specify-item-requirements-for-service-orders"></a>Especificar requisições de itens para ordens de serviço

Você pode especificar os itens de estoque que são necessários para as ordens de serviço. No entanto, a ordem de serviço deve estar associada a um projeto. As requisições de itens para ordens de serviço são processadas através de um projeto. 

**Exemplo**

As ordens de serviço que são criadas do contrato de serviço são processadas pelo despachante. Na primeira ordem de serviço, o despachante percebe que o técnico de serviço exige uma peça sobressalente importante que não está disponível no estoque. Assim, ele cria uma requisição de item para a peça diretamente da ordem de serviço.

## <a name="move-and-post-lines"></a>Mover e lançar linhas

Um técnico de serviço retorna de uma visita e depois altera e atualiza as linhas da ordem de serviço. Durante a visita de serviço, o técnico realiza um serviço que estava agendado para a próxima visita. Então, o técnico move as linhas da próxima visita de serviço para a visita de serviço atual. Depois, o técnico posta a ordem de serviço. Para obter mais informações, consulte [Mover linhas da ordem de serviço](move-service-order-lines.md).

## <a name="cancel-service-orders"></a>Cancelar ordens de serviço

Uma das outras ordens de serviço que foram geradas para o mês de janeiro fica obsoleta porque o trabalho foi cancelado. Portanto, o despachante do serviço cancela a ordem de serviço. Para obter mais informações, consulte [Cancelar ordens de serviço](cancel-service-orders.md).

## <a name="post-from-projects"></a>Lançar de projetos

No final de cada semana, o despachante quer lançar todas as ordens de serviço que são anexadas a um projeto específico. Portanto, a despachante localiza o projeto relevante no formulário **Projetos** e lança as ordens de serviço que foram concluídas. Para obter mais informações, consulte [Lançar ordens de serviço (formulário de classe)](https://technet.microsoft.com/library/aa574685\(v=ax.60\)).

## <a name="delete-service-orders"></a>Excluir ordens de serviço

Na segunda metade do ano, o cliente decide que as visitas de serviço são pouco frequentes. Você deve criar uma nova série de visitas de serviço mais frequentes para o tempo que resta no contrato de serviço. Então, você deve excluir as ordens de serviço existentes e criar novas. Para obter mais informações, consulte [Excluir ordens de serviço](delete-service-orders.md).

## <a name="see-also"></a>Consulte também

[Ordens de serviço (formulário)](https://technet.microsoft.com/library/aa554361\(v=ax.60\))

  


