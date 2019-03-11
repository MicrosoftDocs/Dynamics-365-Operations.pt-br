---
title: Adicionar dimensões financeiras ao espaço de trabalho do CFO
description: Este tópico explica como adicionar dimensões financeiras ao espaço de trabalho do CFO, para que possam ser usadas para relatórios do razão e de orçamento.
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: a15414eff99751d4e77e5b3bf315a556efb7ad5d
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "332670"
---
# <a name="add-financial-dimensions-to-the-cfo-workspace"></a>Adicionar dimensões financeiras ao espaço de trabalho do CFO

[!include [banner](../includes/banner.md)]

Este tópico explica como adicionar dimensões financeiras ao espaço de trabalho do CFO, para que possam ser usadas para relatórios do razão e de orçamento. O espaço de trabalho CFO tem uma guia **Visão geral** e uma guia **Financeiro**. Os relatórios dessas duas guias são apoiadas por duas medidas: LedgerActivityMeasure e BudgetActivityMeasure. No Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (julho de 2017), há uma relação entre essas duas medidas e a entidade DimensionCombinationEntity. Portanto, você pode selecionar dimensões.

1. No Finance and Operations, na página **Repositório de Entidades**, atualize as medidas **LedgerActivityMeasure** e **BudgetActivityMeasure**.
2. No Microsoft Visual Studio, abra o Explorador de Aplicativos e pesquise por **LedgerCFO**.
3. Em **Recursos**, abra **LedgerCFOWorkspacePBIX**.
4. Quando o recurso for aberto na área de trabalho do Microsoft Power BI, selecione **Obter dados**, **Banco de dados do SQL Server** e, em seguida, **Conectar**.
5. Insira o nome do servidor e insira **AxDW** como o banco de dados. Selecione **DirectQuery** e, em seguida, selecione **OK**.
6. Procure e selecione **LedgerActivityMeasure\_DimensionCombination** e, em seguida, selecione **Carregar**.

    > [!TIP]
    > Na lista de **Campos**, renomeie a tabela **Dimensões financeiras**, para que seja fácil identificá-la.

7. Selecione **Gerenciar relacionamentos** e, em seguida, selecione **Novo**.
8. No primeiro campo, selecione **Atividades da contabilidade** e, em seguida, selecione **LedgerDimension**.
9. No segundo campo, selecione **LedgerActivityMeasure\_DimensionCombination** (ou **Dimensões financeiras**, caso tenha renomeado a tabela). Selecione o cabeçalho **DimensionCombinationRECID**.
10. No campo **Cardinalidade**, selecione **Muitos para Um**.
11. Altere o valor de **Direção do filtro cruzado** para **Único**.
12. Selecione **Ativar este relacionamento** e **Pressuponha integridade referencial**, selecione **OK** e, em seguida, **Fechar**.

    [![Criar um relacionamento](./media/Create-relationship.png)](./media/Create-relationship.png)

13. Na lista de **Campos**, você verá a tabela e as dimensões financeiras disponíveis. Arraste as dimensões financeiras desejadas para os filtros no nível de relatório.
14. Salve as alterações.
15. Na árvore de objetos de aplicativo (AOT), clique com o botão direito do mouse no projeto e selecione **Sincronizar**.
16. Crie o projeto e abra o aplicativo para exibir os resultados.

    [![Espaço de trabalho concluído](./media/workspace.png)](./media/workspace.png)
