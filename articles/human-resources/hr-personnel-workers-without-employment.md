---
title: Trabalhadores sem emprego
description: Os trabalhadores sem emprego futuro, ativo ou histórico com a sua organização aparecem na página Trabalhadores sem emprego.
author: twheeloc
ms.date: 11/03/2021
ms.topic: ''
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorkerV2, HRMMassHireProject, HRMMassHireLine, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-04-06
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d0b8fe7dd0818fa1c3cc4224e73035849f9dadfe
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070542"
---
# <a name="workers-without-employment"></a>Trabalhadores sem emprego


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Os trabalhadores sem emprego futuro, ativo ou histórico com a sua organização aparecem na página **Trabalhadores sem emprego**. Os trabalhadores desse tipo podem aparecer quando você importa trabalhadores sem um registro de emprego ou quando exclui um emprego de trabalhador por meio de **Trabalhadores \> Histórico de emprego**.

Por padrão, a página **Trabalhadores sem emprego** está disponível para as seguintes funções:

- Assistente de Recursos Humanos
- Gerente de Recursos Humanos
- Recrutador
- Gerente de remuneração e benefícios
- Administrador de folha de pagamento
- Gerente de folha de pagamento
- Gerente de treinamento

Na lista **Trabalhadores sem emprego**, você pode excluir as pessoas listadas. Por padrão, esse privilégio é dado à função assistente de Recursos Humanos. Você pode conceder esse privilégio a outras funções com as seguintes etapas:

1. Selecione **Administração do sistema** e, depois, **Configuração de segurança**.

2. Na guia **Privilégios**, filtre a lista **Privilégios** para **Manter trabalhadores**.

   [![Lista Filtrar Privilégios.](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)

3. Na coluna **Referências**, selecione **Exibir itens do menu**.

4. Em **Exibir itens do menu**, selecione **HcmWorkersWithoutEmployment**.

   [![Selecionar formulário.](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)

5. Defina a permissão **Excluir** para **Conceder**.

6. Selecione a guia **Objetos não publicados**.

7. Selecione **Publicar tudo**.

   [![Publicar alterações.](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
