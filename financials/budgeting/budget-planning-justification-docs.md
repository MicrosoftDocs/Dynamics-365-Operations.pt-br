---
title: Budget planning justification documents
description: "Os documentos da justificativa fornecem uma narrativa para os quais um orçamento explicar como um orçamento específico é necessário."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 259594
ms.assetid: 52576fad-32b9-48f2-8197-c11ec313fc29
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: c86d01fec3d8d7c210c7e73a034f4e9e384a0dcf
ms.lasthandoff: 03/31/2017


---

# <a name="budget-planning-justification-documents"></a>Budget planning justification documents

Os documentos da justificativa fornecem uma narrativa para os quais um orçamento explicar como um orçamento específico é necessário. 

Um modelo de plano de orçamento é criada pelo gerente de orçamento no Microsoft Word e atribuído ao processo de planejamento de orçamento atual. De orçamento proprietários poderá abrir o modelo e ter os dados automaticamente preenchidos em O Word com base em sua solicitação de orçamento. Podem então adicionar texto ou os dados antes da economia e de anexar o documento personalizada justificação ao plano de orçamento.

##### <a name="set-up-microsoft-dynamics-office-add-in-for-microsoft-word"></a>Manuais suplementam instalação do Microsoft Dynamics para o Microsoft Office Word

1.  Abrir um novo documento do Microsoft Word.
2.  Clique ** inserção ** em fita, e clique ** ** armazenamento.
3.  Procure o manuais suplementam a Microsoft Dynamics Office e clique em adicionar. ** **
4.  Em O Word, no painel direito, clique ** adicionar informações do servidor. **
5.  Digite ou cole a URL do servidor e clicar em OK ** **.

##### <a name="define-the-justification-template-in-microsoft-word"></a>Defina o modelo justificação no Microsoft Word

1.  Clique ** Design ** manuais suplementam na Microsoft Dynamics Office depois que você fizer logon.
2.  Para informações de cabeçalho, use ** adicionar campos ** o botão.
3.  Selecione a fonte de dados de BudgetPlanJustification entidade, clique ** Adiantar **. ** Observação: ** A entidade é necessária para qualquer documento justificação. Outras entidades podem ser usadas mas o carregamento em Microsoft Dynamics 365 para operações falhará se a entidade não está incluída.
4.  Adicionar o BudgetPlanName, o BudgetPlanPreparer, o ResponsibilityCenter, os rótulos e valores de DocumentNumber no documento de O Word. ** Observação: ** Você pode usar sua própria rótulos personalizados, em vez dos rótulos padrão, se necessário.
5.  Clique ** feito ** conclua a seção de cabeçalho.
6.  Para a linha de detalhes de nível valores de plano de orçamento, clique ** adicionar ** a tabela.
7.  Além disso, selecione a fonte de dados de BudgetPlanJustification entidade, clique ** Adiantar **.
8.  Para adicionar campos EffectiveDate, ScenarioName, AccountDisplayValue, e AccountingCurrencyExpenseAmount. ** Observação: ** Se os comentários são disponíveis para adicionar nas linhas individuais de plano de orçamento, estes podem ser adicionados à tabela aqui.
9.  Adicione todas as instruções adicionais para fornecer ao usuário final, e executar qualquer formatação necessário ou denominação ao documento.
10. Salve o documento ao computador local e feche o arquivo antes de continuar.

##### <a name="set-up-the-budget-planning-process-to-use-the-justification-template"></a>Configurar o processo de planejamento de orçamento para usar o modelo da

1.  No Microsoft Dynamics 365 para operações, vá ** para orçar ** &gt; ** de instalação ** &gt; ** planejamento de orçamento ** &gt; ** justificação documentem ** modelos.
2.  ** ** Clique em novo e consulta a recém-criada o documento do Microsoft Word.
3.  Insira um nome para exibição e uma descrição do modelo. Click **OK**.
4.  ** Vá para orçar ** &gt; ** de instalação ** &gt; ** orçamento ** ** planejamento ** &gt; ** de orçamento o processo de planejamento. **
5.  Selecione o processo o modelo em justificação, deve ser usado e clique ** ** edição.
6.  ** O modelo de documento da justificativa ** campo, selecione o modelo apropriado e salvar.

##### <a name="edit-and-save-personalized-justification-documents"></a>Editar e salvar documentos personalizados justificação

1.  Em dynamics 365 para operações, crie um novo plano de orçamento ou abra um plano existente de orçamento.
2.  ** Justificativa ** no menu suspenso, selecione novo ** crie a justificativa **.
3.  Após preencher os detalhes, selecione para carregar o documento personalizada ** justificativa ** do menu suspenso.



