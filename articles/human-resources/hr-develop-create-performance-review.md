---
title: Criar avaliações de desempenho
description: Este tópico explica como criar uma previsão dos resultados e descreve a finalidade de cada seção de revisão.
author: andreabichsel
ms.date: 05/05/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EssWorkspace, HcmDiscussionNewDialog, HcmDiscussion, HcmDiscussionChangeSettings, HcmDiscussionAddGoalDialog, HcmTopicCreate, HcmMeasurementDetailDialog, HcmPerfJournalAdd, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: acbfcadb32d3bfb66d290b89e3c90124f80a1be8
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805577"
---
# <a name="create-performance-reviews"></a>Criar avaliações de desempenho

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]


Este tópico explica como criar uma previsão dos resultados e descreve a finalidade de cada seção de revisão. Este procedimento foi criado usando a empresa de dados de demonstração USMF.

1. Na página inicial, selecione o espaço de trabalho **Autoatendimento para funcionários**.
2. Selecione **Nova revisão** para criar uma revisão.
3. No campo **Tipo de revisão**, insira ou selecione um valor.
4. No campo **Período de desempenho**, insira ou selecione um valor.
5. No campo **Data final**, insira uma data.
6. Selecione **OK**. Você também pode criar uma revisão a partir de um modelo. Essa é a melhor maneira de criar uma revisão, já que cada ação conterá as informações que você precisa para iniciar uma revisão.  
7. Você pode mostrar ou ocultar guias, como a guia de anexos:

    1. No Painel de Ações, selecione **Exibir seções** para abrir o menu de diálogo.
    1. Selecione **Sim** ou **Não** no campo **Exibir anexos** para mostrar ou ocultar a guia de anexos.
    1. Selecione **Salvar**.

8. Selecione **Adicionar meta para revisão** para adicionar uma meta. Selecione **OK** ao concluir.
9. Selecione **Adicionar competência** para abrir a caixa de diálogo suspensa.
10. No campo **Título**, digite um valor.
11. No campo **Descrição**, insira `Increase customer skills by working with the support team`.
12. Selecione **OK**.
13. Selecione **Recolher tudo**.
14. Selecione **Expandir tudo**.
15. Selecione **Adicionar comentário**.
16. Selecione **Lançar**.
17. Selecione a guia **Medições**.
18. Selecione **Adicionar medida** para abrir o menu de diálogo.
19. No campo **Medida**, insira ou selecione um valor.
26. No campo **Valor alvo**, insira um número.
20. Selecione **OK**.
21. Selecione a guia **Atividades**.
22. Selecione **Adicionar**.
23. No campo **Título**, digite um valor.
24. No campo **Descrição**, digite um valor.
25. No campo **Data inicial**, insira uma data.
26. No campo **Data de conclusão**, insira uma data.
27. Selecione **Sim** no campo **Plano de desenvolvimento**.
28. No campo **Palavras-chave**, digite um valor.
29. Selecione **Salvar**.
30. Selecione a guia **Classificações**.  

    - A Guia Rápida **Detalhes de classificação** permite que os funcionários se avaliem e que o gerente avalie os funcionários. Se pesos forem usados, o valor do peso dos pontos será calculado automaticamente.  
    - Para exibir essa seção, habilite as configurações de parâmetro para exibição das classificações do funcionário.  

31. Selecione a guia **Aprovações**. Se a revisão usar um fluxo de trabalho, as aprovações aparecerão só depois da conclusão do fluxo de trabalho. Se nenhum fluxo de trabalho for usado, o trabalhador e o gerente estarão listados aqui. A caixa de seleção necessária é selecionada com base nas configurações do tipo de revisão.  
32. Selecione a guia **Geral**.

    - O período de desempenho cria datas inicial e final padrão. Essas datas são editáveis.  
    - Os status controlam o acesso à revisão. O status **Não iniciado** permite que todos editem a revisão. O status **Em andamento** permite que o funcionário só exiba e edite a revisão. **Aprontar para revisão** permite que somente o gerenciador exiba e edite a revisão. Status **final da revisão** permite que o funcionário e gerente exibam a revisão e também editá-la configuração se o tipo de análise. Os status **Concluído** e **Cancelado** deixam a revisão apenas leitura. Se uma revisão for **Rejeitada** e enviada de volta ao funcionário, o funcionário e o gerente poderão fazer as edições necessárias para que o funcionário possa reenviar.

33. No campo **Visão geral**, digite um valor.
34. Selecione a guia **Revisão**. Como revisão se move com o status, o funcionário e gerente podem adicionar comentários ou para cada meta competência.  
35. Selecione a guia **Aprovações**. O trabalhador e o gerente podem aprovar a revisão. Quando todos os prazos de conexão exigidos for concluído, o status será alterado para **Concluído** e não poderá mais alteração ser feita.  



[!INCLUDE[footer-include](../includes/footer-banner.md)]