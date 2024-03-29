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
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-04-06
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d3b2d5d470e780c708941fd3d08eae1a042b4c03
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8689793"
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
