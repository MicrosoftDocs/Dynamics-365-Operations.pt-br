---
title: Visão geral de tarefas de serviço
description: Use tarefas de serviço para descrever a tarefa a ser concluída durante uma ordem de serviço. Os técnicos e clientes podem consultar essas informações.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceTask
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b433632523bfd64119fda62f8e4b108ff9b5dccd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4421865"
---
# <a name="service-tasks-overview"></a>Visão geral de tarefas de serviço

[!include [banner](../includes/banner.md)]

Use tarefas de serviço para descrever a tarefa a ser concluída durante uma ordem de serviço.
Os técnicos e clientes podem consultar essas informações.

Crie tarefas de serviço na página **Tarefas de serviço** e associe tarefas de serviço a uma ordem de serviço ou a um contrato de serviço específico por meio da criação de relações de tarefa de serviço. Sempre que criar uma relação de tarefas de serviço, você poderá criar o seguinte:

-  Notas internas da tarefa, como solicitações técnicas detalhadas da tarefa que devem ser de conhecimento do técnico.

-  Notas externas que o cliente pode ver. Essas podem oferecer uma explicação menos técnica da tarefa que está sendo executada, de acordo com o contrato entre o cliente e a empresa de serviço.

Quando tiver configurado uma relação de tarefas de serviço entre uma tarefa de serviço e uma ordem de serviço ou um contrato de serviço, você poderá especificar essa tarefa de serviço quando criar linhas de ordem de serviço ou linhas de contrato de serviço para a ordem de serviço ou o contrato de serviço atual.

Ao gerar ordens de serviço de um contrato de serviço, você poderá usar as tarefas de serviço atribuídas a cada linha do contrato de serviço nas linhas da ordem de serviço em ordens de serviço.

## <a name="create-a-service-task"></a>Criar uma tarefa de serviço

1. Clique em **Gerenciamento de serviços** \> **Configuração** \> **Tarefas de serviços**.
2. Crie uma nova linha.
3. Insira a ID e a descrição do serviço.

## <a name="example"></a>Exemplo

Um técnico deve executar dois trabalhos em uma caixa de embreagens (objeto de serviço GB-1234) no site de um cliente. Um contrato de serviço é criado para o cliente, e várias transações são associadas aos trabalhos. O contrato de serviço e as linhas de contrato de serviço para os dois trabalhos são as seguintes:

### <a name="service-agreement"></a>Contrato de serviço

| Project | Contrato de serviço | descrição                                  | Agrupar   |
|---------|-------------------|----------------------------------------------|---------|
| 9012    | 000008\_001       | Inspeção e substituição de rotina - GB-1234 | Gratificação |

### <a name="service-agreement-lines"></a>Linhas do contrato de serviço

| Descrição             | Tipo de transação | Objeto de serviço | Tarefa de serviço |
|-------------------------|------------------|----------------|--------------|
| inspeção e limpeza | Hora             | GB-1234        | I/C - GB1234 |
| Viagem                  | Expense          | GB-1234        | I/C - GB1234 |
| Materiais               | Item             | GB-1234        | I/C - GB1234 |
| Substituição de rotina     | Hora             | GB-1234        | RR - GB1234  |
| GR-1                    | Item             | GB-1234        | RR - GB1234  |
| GR-5                    | Item             | GB-1234        | RR - GB1234  |

As linhas de contrato de serviço dos dois trabalhos têm duas tarefas de serviço anexadas a elas. As tarefas de serviço determinam as transações que pertencem a cada trabalho. No primeiro caso, tarefa de serviço I/C - GB1234 identifica todas as linhas de contrato de serviço envolvidas na inspeção e limpeza do objeto GB-1234. No segundo caso, a tarefa de serviço RR - GB1234 identifica todas as linhas de contrato de serviço envolvidas na realização de um trabalho de substituição de rotina.

As relações de tarefas de serviço que conectam as tarefas de serviço ao contrato específico são as seguintes:

### <a name="service-tasks"></a>Tarefas de serviço

| Tarefa de serviço | Descrição                             | Nota interna                                                                                                                 | Nota externa                 |
|--------------|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------|
| I/C - GB1234 | Inspeção da caixa de embreagens GB-1234           | Inspeção visual e mecânica da caixa de embreagens GB-1234                                                              | Inspeção de rotina da caixa de embreagens |
| RR - GB1234  | Substituição de peças de rotina do GB-1234 | Substituição de serviço de rotina dos componentes GR-1 e GR-5 (para caixas de embreagens fabricadas antes de 2002, substituir também o componente GR-2) | Substituição de peças de rotina  |

## <a name="group-service-orders"></a>Agrupar ordens de serviço

Quando você cria ordens de serviço automaticamente, pode usar tarefas de serviço como critérios de agrupamento. Para agrupar ordens de serviço por tarefas de serviço, defina no contrato de serviço que as ordens de serviço com base no contrato de serviço devem ser agrupadas por ID da tarefa de serviço como os critérios de agrupamento inicial.

**Agrupar por tarefa de serviço**

1. Clique em **Gerenciamento de serviços** \> **Comum** \> **Contratos de serviço** \> **Contratos de serviço**.
2. Na guia **Configuração**, selecione **Por tarefa de serviço** no campo **Combinar ordens de serviço**.


