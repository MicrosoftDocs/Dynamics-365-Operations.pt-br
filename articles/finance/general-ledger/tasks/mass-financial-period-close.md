---
title: Fechamento em massa do período financeiro
description: Este tópico mostra como colocar um período em espera ou fechar permanentemente um período ou mais de uma entidade legal de uma só vez.
author: aprilolson
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerCalendar, LedgerPeriodModuleAccessControlUpdate, SysLookupPicklist, LedgerFiscalCalendarPeriodStatus
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0acaad0d6e89fe7c81537e554b36ffb210e5abad
ms.sourcegitcommit: 602a319f4720b39a56b7660b530236912d484391
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2022
ms.locfileid: "8722056"
---
# <a name="mass-financial-period-close"></a>Fechamento em massa do período financeiro

[!include [banner](../../includes/banner.md)]

Este tópico mostra como colocar um período em espera ou fechar permanentemente um período ou mais de uma entidade legal de uma só vez. Além disso, ela mostra como restringir o grupo de usuários para lançar a módulos específicos.

1. No painel de navegação, acesse **Contabilidade > Fechamento de período > Calendários do razão**. Observe que a lista das entidades legais exibidas depende do calendário fiscal selecionado na página. Apenas as entidades legais que usam o calendário fiscal selecionado serão exibidas.
2. Selecione **Editar**.
3. Selecionar o período para o qual você deseja modificar o status.
4. Selecionar as entidades legais para o qual você deseja atualizar o status. Você poderá selecionar todas as entidades legais rapidamente selecionando a marca de seleção do lado superior esquerdo da grade.  
5. Selecione **Atualizar acesso ao módulo** para definir o acesso de postagem a um módulo selecionado. O status do módulo também pode ser atualizado ao editar os registros na grade. O botão é útil quando você deseja atualizar rapidamente várias registradoras de entidade legal.  
6. No módulo **Aplicativo**, selecione o módulo no qual deseja atualizar o status. Clique em **Selecionar**.
7. No nível de **Acesso**, selecione **Todos**, **Nenhum** ou um grupo de usuários específicos. Clique em **Selecionar**.  
- **Tudo** - todos os usuários com acesso de edição ao módulo podem lançar se o período estiver aberto. 
- **Nenhum** - os usuários não podem lançar nesse módulo se o período estiver aberto. Um grupo de usuários específicos apenas indica que os usuários no grupo são capazes de lançar nesse módulo se o período estiver aberto.  
8. Selecione **Atualizar**. 
9. Selecione outro período para atualizar o status.
10. Selecionar as entidades legais para o qual você deseja atualizar o status do período.
11. Selecione **Atualizar status do período** e defina o status de **Em espera**, **Aberto** ou **Permanentemente fechado**. **Aberto** indica o período em que o lançamento é possível, desde que o usuário tenha acesso. **Em espera** significa que o período não poderá ser lançado, mas o período pode ser reaberto. **Permanentemente fechado** significa que o período será fechado e nunca pode ser aberto. Ajustes não podem ser lançados. Não se recomenda definir um período como **Permanentemente fechado** até que todos os ajustes e auditorias estejam completos.  
12. Selecione **Atualizar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
