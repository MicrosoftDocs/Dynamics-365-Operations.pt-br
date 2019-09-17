---
title: Novidades ou alterações no Dynamics 365 for Talent Core HR (23 de janeiro de 2019)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-01-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 4e492095d5269ec81c0c22145b7af356937c256b
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742507"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-january-23-2019"></a>Novidades ou alterações no Dynamics 365 for Talent Core HR (23 de janeiro de 2019)

[!include [banner](includes/banner.md)]

**Compilação 8.1.2121**

Este tópico descreve os recursos novos ou alterados no Core HR.

## <a name="changes"></a>Alterações

### <a name="import-of-employee-fixed-compensation-not-working-when-creating-new-fixed-compensation-records"></a>A importação de remuneração fixa do funcionário não está funcionando na criação de novos registros de remuneração fixa
Uma alteração foi feita na entidade de remuneração fixa do funcionário para recuperar o nível da remuneração na importação. Antes desta versão, uma mensagem era exibida indicando que o nível era necessário.

### <a name="remove-the-minimum-balance-field-from-the-time-off-request-dialog-box"></a>Remover o campo saldo mínimo usando a caixa de diálogo de solicitação de folga
O campo **Saldo mínimo** foi removido da caixa de diálogo **Solicitação de folga**. Esta alteração afeta todas as áreas em que a folga pode ser solicitada.

### <a name="data-upgrade-for-compensation-levels-not-updating-in-all-scenarios"></a>A atualização de dados dos níveis de remuneração não estão sendo atualizados em todos os cenários
Uma alteração foi feita para atualizar o nível de remuneração nos planos de remuneração fixa. Esta alteração preencherá o nível de remuneração nos planos fixos para os trabalhos atribuídos ao funcionário.

### <a name="payroll-information-in-the-manage-changes-page-is-only-available-when-logged-in-as-system-administrator"></a>As informações de folha de pagamento na página Gerenciar alterações só estão disponíveis quando se faz logon como administrador do sistema
Esta alteração permite aos funcionários com a função Administrador de folha de pagamento acessar informações de folha de pagamento na página **Linha do tempo das alterações > Gerenciar alterações** para a posição.

### <a name="job-fields-default-to-positions"></a>Os campos de trabalho são padronizados com posições
Ao alterar os trabalhos em uma posição, os campos de trabalho assumirão como padrão a posição. Uma mensagem de alerta aparecerá dando a opção de aceitar os valores padrão ou manter os valores existentes para esses campos.

### <a name="probation-period-and-calendar-are-not-displayed-for-future-hired-employees"></a>O período e o calendário de experiência não são exibidos para futuros funcionários contratados.
Com esta alteração, os campos **Período de experiência** e **Calendário** foram adicionados à página **Gerenciar alterações** para permitir a entrada de dados de funcionários futuros e passados.

### <a name="platform-update-23"></a>Update 23 para plataforma
Pequenas correções de bugs foram incluídas como parte da atualização 23 da Plataforma. Para obter mais informações, consulte [Novidades ou alterações na atualização 23 da plataforma do Dynamics 365 for Finance and Operations (janeiro de 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-23). 
