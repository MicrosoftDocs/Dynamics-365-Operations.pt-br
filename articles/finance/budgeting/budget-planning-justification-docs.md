---
title: Documentos de justificativa para planejamento de orçamento
description: Documentos de justificativa fornecem uma narrativa àqueles solicitando um orçamento para explicar por que um orçamento específico é necessário.
author: panolte
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetPlanJustificationTemplate
audience: Application User
ms.reviewer: roschlom
ms.custom: 259594
ms.assetid: 52576fad-32b9-48f2-8197-c11ec313fc29
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5eb74b5d2b71372f99dd927ff6e2bee96e199a6f75b3ae920607e5ec37a4241a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6752957"
---
# <a name="budget-planning-justification-documents"></a>Documentos de justificativa para planejamento de orçamento

[!include [banner](../includes/banner.md)]

Documentos de justificativa fornecem uma narrativa àqueles solicitando um orçamento para explicar por que um orçamento específico é necessário. 

Um modelo de plano de orçamento é criado pelo gerente de orçamento no Microsoft Word e atribuído ao processo de planejamento de orçamento atual. Proprietários de orçamento podem então abrir o modelo e ter dados automaticamente preenchidos no Word com base em sua solicitação de orçamento. Eles podem adicionar mais texto ou dados antes de salvar ou anexar seu documento de justificativa personalizado ao seu plano de orçamento.

##### <a name="set-up-microsoft-dynamics-office-add-in-for-microsoft-word"></a>Configurar o Suplemento do Office do Microsoft Dynamics para Microsoft Word

1.  Abra um novo documento do Microsoft Word.
2.  Clique em **Inserir** na faixa de opções e, depois, clique em **Armazenar**.
3.  Procure o Suplemento do Office do Microsoft Dynamics e clique em **Adicionar**.
4.  No Word, no painel direito, clique em **Adicionar informações do servidor**.
5.  Digite ou cole a URL do servidor e clique em **OK**.

##### <a name="define-the-justification-template-in-microsoft-word"></a>Definir o modelo de justificativa no Microsoft Word

1.  Clique em **Design** no Suplemento do Office do Microsoft Dynamics depois de ter feito logon.
2.  Para informações de cabeçalho, use o botão **Adicionar campos**.
3.  Selecione a fonte de dados da entidade de BudgetPlanJustification e clique em **Avançar**. **Observação:** essa entidade é necessária para qualquer documento. É possível usar outras entidades, mas ocorrerá uma falha ao carregar novamente no Microsoft Dynamics 365 Finance se essa entidade não estiver incluída.
4.  Adicione as etiquetas e valores BudgetPlanName, BudgetPlanPreparer, ResponsibilityCenter e DocumentNumber no documento do Word. **Observação:** é possível usar suas próprias etiquetas, em vez de etiquetas padrão, se necessário.
5.  Clique em **Concluído** para concluir a seção de cabeçalho.
6.  Para detalhes de nível de linha dos valores de plano de orçamento, clique em **Adicionar tabela**.
7.  Selecione novamente a fonte de dados da entidade de BudgetPlanJustification e clique em **Avançar**.
8.  Adicione campos para EffectiveDate, ScenarioName, AccountDisplayValue e AccountingCurrencyExpenseAmount. **Observação:** se comentários estiverem disponíveis para adição nas linhas de plano de orçamento individuais, eles podem ser adicionados à tabela aqui.
9.  Adicione qualquer instrução adicional para fornecer ao usuário final e realize qualquer formatação ou estilização no documento.
10. Salve o documento no seu computador local e feche o arquivo antes de continuar.

##### <a name="set-up-the-budget-planning-process-to-use-the-justification-template"></a>Configurar o processo de planejamento de orçamento para usar o modelo de justificativa

1.  Acesse **Orçamento** &gt; **Configuração** &gt; **Planejamento de orçamento** &gt; **Modelos de documento de justificativa**.
2.  Clique em **Novo** e acesse o documento recém-criado do Microsoft Word.
3.  Insira nome e descrição de exibição de modelo. Clique em **OK**.
4.  Acesse **Orçamento** &gt; **Configuração** &gt; **Planejamento do** **orçamento** &gt; **Processo de planejamento de orçamento**.
5.  Selecione o processo no qual o modelo de justificativa deve ser usado e clique em **Editar**.
6.  No campo **Modelo de documento de justificativa**, selecione o modelo apropriado e salve-o.

##### <a name="edit-and-save-personalized-justification-documents"></a>Editar e salvar documentos de justificativa personalizados

1.  Crie um novo plano de orçamento ou abra um plano de orçamento existente.
2.  No menu suspenso **Justificativa**, selecione **Criar nova justificativa**.
3.  Após preencher os detalhes, selecione para carregar os documentos personalizados no menu suspenso **Justificativa**.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]