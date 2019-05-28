---
title: Contratos de serviço
description: Os contratos de serviço permitem definir os recursos usados em uma típica visita de serviços e como esses recursos são faturados para o cliente.
author: ShylaThompson
manager: AnnBe
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c6425dcf1c89f625d997be0dd4a52aaecb6e6d65
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568272"
---
# <a name="service-agreements"></a>Contratos de serviço

[!include [banner](../includes/banner.md)]

Os contratos de serviço permitem definir os recursos usados em uma típica visita de serviços e como esses recursos são faturados para o cliente.

Todo contrato de serviço é vinculado a um projeto pelo qual as transações são lançadas e faturadas. No entanto, também é possível faturar transações de ordem de serviço diretamente pelo projeto sem ter de associar primeiro a ordem de serviço a um contrato de serviço. Você pode decidir fazer isso se a ordem de serviço for para uma visita de serviço única e a necessidade de processar rapidamente as transações de serviço supere a necessidade de manter informações detalhadas do contrato de serviço sobre o cliente durante um período.

## <a name="service-agreement"></a>Contrato de serviço

Em cada contrato de serviço você deve especificar um projeto, uma ID de contrato de serviço e um grupo de contrato de serviço. O grupo de contrato de serviço pode ser usado para classificar e organizar contratos de serviço.

O cabeçalho de um contrato de serviço contém configurações que se aplicam a todas as linhas de contrato anexadas:

-  Se o contrato de serviço for suspenso. Se o contrato de serviço for suspenso, você não poderá gerar ordens de serviço do contrato de serviço.
-  A duração do contrato de serviço.
-  Como as linhas de ordem de serviço devem ser combinadas em ordens de serviço.
-  Se o contrato de serviço é um modelo.

No cabeçalho do contrato de serviço, é possível configurar todos os objetos e tarefas de serviço que podem ser usados com o contrato de serviço especificando as tarefas de serviço ou os objetos de serviço específicos que devem ser anexados a várias linhas do contrato.

Do cabeçalho do contrato de serviço você também poderá copiar linhas de contrato de serviço ou linhas de modelo de serviço no contrato de serviço atual.

Você pode suspender contratos de serviço e parar linhas de contratos de serviço individuais.

Se você marcar a caixa de seleção **Suspenso** em um contrato de serviço, você não poderá:

-    Criar ordens de serviço automaticamente ou manualmente a partir do contrato de serviço.

Se você marcar a caixa de seleção **Parado** em uma linha de contrato de serviço, você não poderá:

-    Criar ordens de serviço automaticamente ou manualmente a partir da linha de contrato de serviço.
-    Copiar a linha de contrato de serviço em outro contrato de serviço ou ordem de serviço.


> [!NOTE]
> Se um contrato de serviço for suspenso, todas as linhas anexadas serão paradas, não importando seus status individuais.

## <a name="service-agreement-lines"></a>Linhas do contrato de serviço

Cada linha do contrato de serviço descreve em detalhes o conteúdo do trabalho de serviço proposto. As linhas contêm as seguintes configurações:

-  O tipo de transação e a descrição do tipo de transação.
-  O funcionário que executa o serviço.
-  Os objetos nos quais o serviço deve ser executado para o contrato de serviço.
-  A freqüência com a qual o trabalho é executado e item, despesa e transações de taxa associados são registrados.
-  A janela de tempo dentro da qual as linhas de ordem de serviço podem ser agrupadas em uma ordem de serviço.
-  As tarefas de serviço usadas para agrupar conjuntos de linhas do contrato em tarefas de trabalho e para resumir aos técnicos de serviço e clientes qual a tarefa de serviço a ser fornecida.
-  Se uma linha for parada. Se uma linha for parada, não será possível criar ordens de serviço para aquela linha individual.
-  Configurações do projeto, como a categoria e a propriedade da linha.

## <a name="related-topics"></a>Tópicos relacionados

[Criar contratos de serviço](create-service-agreements.md)
