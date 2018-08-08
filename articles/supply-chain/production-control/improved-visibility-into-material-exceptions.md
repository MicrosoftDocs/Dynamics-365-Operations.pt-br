---
title: "Visibilidade de exceções materiais"
description: "Este tópico descreve como você pode obter melhor a visibilidade de exceções para matérias-primas para ordens de produção e ordens de lote."
author: johanhoffmann
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: JmgShopSupervisorWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.search.region: Global
ms.author: johanho
ms.search.validfrom: 2017-12-31
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: eca3141fc48aea24411524e5fc84686d9e4bfaa7
ms.contentlocale: pt-br
ms.lasthandoff: 03/08/2018

---
# <a name="visibility-into-material-exceptions"></a>Visibilidade de exceções materiais

[!include [banner](../includes/banner.md)]

No espaço de trabalho **Gerenciamento de piso de produção**, três blocos fornecem melhor visibilidade de exceções para matérias-primas para ordens de produção e ordens de lote:

- Linhas de material não liberado que precisam de atenção
- Ondas não processadas que precisam de atenção
- Abrir trabalho de depósito que precisa de atenção

Para todos os três blocos, a data da matéria-prima das linhas da BOM (lista de materiais) e das linhas da fórmula é comparada com a data do espaço de trabalho e também com os filtros da **Unidade de produção**, **Grupo de recursos** e **Recurso** que são definidos no menu **Configurar meu espaço de trabalho**. Por padrão, a data do espaço de trabalho é definida como a data atual, mas você pode ajustá-la.

Uma linha da BOM ou linha da fórmula não liberada requer atenção, se a data da matéria-prima da linha for igual ou anterior à data do espaço de trabalho e se atender aos critérios definidos pelos filtros no espaço de trabalho.

Na figura a seguir, a barra azul representa um trabalho de produção que foi programado em um recurso. O trabalho é programado para começar em 1º de maio de 2017 (01/05/2017). Esta é a data da matéria-prima. Em outras palavras, os materiais que são atribuídos ao trabalho nas linhas de BOM ou fórmula devem estar prontos nesta data. A outra data na figura, 6 de maio de 2017 (06/05/2017) representa a data do espaço de trabalho. Neste exemplo, a data da matéria-prima é anterior à data do espaço de trabalho. Portanto, a data em que o consumo de matéria-prima devia começar passou e as linhas de BOM e fórmula atendem aos critérios que exigem atenção.

![Exemplo de um trabalho de produção no qual a data da matéria-prima é anterior à data do espaço de trabalho.](./media/improved-visibility.png)

## <a name="unreleased-material-lines-needing-attention"></a>Linhas de material não liberado que precisam de atenção

Uma linha de BOM ou fórmula pode ser liberada para o depósito de três formas:

- Como parte de uma versão da ordem de produção ou ordem de lote
- Como uma liberação manual
- Automaticamente através de um trabalho em lotes

Para obter mais informações, consulte [Liberar linhas de BOM e fórmula para o depósito](releasing-bom-and-formula-lines-to-warehouse.md). 

Se uma linha de BOM ou fórmula não foi liberada ou só foi parcialmente liberada e se os critérios de data e filtro do espaço de trabalho foram atendido, a linha é incluída no cálculo do número que aparece no bloco **Linhas de material não liberado que precisam de atenção**.

Quando você seleciona o bloco, a página **Liberar para o depósito** é aberta. Esta página mostra o número de linhas de BOM e fórmula não liberadas que é indicada pelo número no bloco. As linhas não liberadas aparecem na grade superior. Esta grade mostra a quantidade que foi estimada originalmente para a linha, a quantidade que já foi liberada e a quantidade restante que ainda deve ser liberada. Você pode adicionar linhas da grade superior à grade inferior. Na grade inferior, você poderá liberar as linhas selecionadas para o depósito. Na grade inferior, você também pode ajustar a quantidade para liberação, de modo que apenas uma quantidade parcial seja liberada.

## <a name="unprocessed-waves-needing-attention"></a>Ondas não processadas que precisam de atenção

Quando uma BOM ou fórmula é liberada, ela é adicionada a uma nova onda de produção ou a uma onda aberta existente, dependendo da configuração de modelo da onda de produção. Através da configuração de modelo da onda, você também pode configurar uma onda, de forma que seja processada automaticamente quando uma linha de BOM ou fórmula é liberada. Quando a onda é processada, o trabalho de depósito para a separação de matéria-prima é gerada. Se o modelo da onda for configurado, de forma que as ondas não sejam processadas no momento de liberação, a onda permanecerá em um estado não processado. O bloco **Ondas não processadas que precisam de atenção** mostrará o número de Linhas de BOM e fórmula que foi liberado para o depósito nas ondas processadas, e que têm uma data da matéria-prima anterior a ou igual à data do espaço de trabalho. As linhas também devem ser consumidas por um recurso de operação que se aplique ao filtro do espaço de trabalho.

Quando o bloco for selecionado, a página **Todas as ondas de produção** será aberta. Essa página é filtrada pelo número de ondas abertas que contêm linhas de onda das linhas de BOM e fórmula liberadas que atendem aos critérios do bloco. Na página **Todas as ondas de produção**, você pode processar manualmente a onda.

## <a name="open-warehouse-work-needing-attention"></a>Abrir trabalho de depósito que precisa de atenção

O bloco **Abrir trabalho de depósito que precisa de atenção** mostrará o número de Linhas de BOM e fórmula liberadas para o depósito, que têm trabalho não processado, e que têm uma data da matéria-prima anterior a ou igual à data do espaço de trabalho. As linhas também devem ser consumidas por um recurso de operação que se aplique ao filtro do espaço de trabalho.

Quando o bloco for selecionado, a página **Todos os trabalhos** será aberta. Essa página é filtrada pelo número de cabeçalhos de trabalho que contêm linhas de trabalho das linhas de BOM e fórmula que atendem aos critérios do bloco. Na página **Todos os trabalhos**, você pode processar manualmente o trabalho.

