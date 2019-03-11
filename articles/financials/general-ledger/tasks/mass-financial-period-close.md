---
title: Fechamento em massa do período financeiro
description: Este procedimento mostra como colocar um usuário coloca de período ou permanentemente fechar um período ou mais de uma entidade legal por vez.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerCalendar, LedgerPeriodModuleAccessControlUpdate, SysLookupPicklist, LedgerFiscalCalendarPeriodStatus
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a2988b7ab0837cc9a3e4f1c4eaf3fe6e219fa721
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "311372"
---
# <a name="mass-financial-period-close"></a>Fechamento em massa do período financeiro

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como colocar um usuário coloca de período ou permanentemente fechar um período ou mais de uma entidade legal por vez. Além disso, ela mostra como restringir o grupo de usuários para lançar a módulos específicos.

1. Vá para Contabilidade > Fechamento de período > Calendários do razão.
    * Observe que a lista das entidades legais exibidas depende do calendário fiscal selecionado na página. Apenas as entidades legais que usam o calendário fiscal selecionado serão exibidas.  
2. Clique em Editar.
3. Selecionar o período para o qual você deseja modificar o status.
4. Selecionar as entidades legais para o qual você deseja atualizar o status.
    * Você poderá selecionar todas rapidamente as entidades legais selecione a marca de seleção do lado superior esquerdo de grade.  
5. Selecionar o acesso do módulo de atualização para definir de postagem acesso a um módulo selecionado.
    * O status do módulo também pode ser atualizado ao editar os registros na grade. O botão é útil quando você deseja atualizar rapidamente várias registradoras de entidade legal.  
6. Em Módulo do aplicativo, selecione o módulo que deseja atualizar o status. Clique em Selecionar.
7. Em Nível de acesso, selecione Todos, Nenhum, ou um grupo de usuário específico. Clique em Selecionar.
    * Tudo indica que todos os usuários com acesso de edição ao módulo podem lançar se o período estiver aberto. Nenhum indica que os usuários não podem lançar nesse módulo se o período estiver aberto. Um grupo de usuários específicos apenas indica que os usuários no grupo são capazes de lançar nesse módulo se o período estiver aberto.  
8. Clique em Atualizar.
9. Selecione outro período para atualizar o status.
10. Selecionar as entidades legais para o qual você deseja atualizar o status do período.
11. Selecione o status de períodos atualizados e define o status de em espera, aberta, ou fechou-se permanentemente.
    * Aberto indica o período em que o lançamento é possível, desde que o usuário tenha acesso. Em espera significa que o período não poderá ser lançado, mas o período pode ser reaberto. Permanentemente o fechado significa que o período será fechada e nunca pode ser aberto. Ajustes não podem ser lançados. Não se recomenda definir um período como fechado permanentemente até que todos os ajustes e auditorias estejam completos.  
12. Clique em Atualizar.

