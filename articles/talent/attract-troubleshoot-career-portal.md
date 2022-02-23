---
title: Os usuários do Attract não podem se candidatar a empregos pelo portal de carreiras
description: Este tópico explica como solucionar um problema em que usuários do Attract não podem se candidatar a empregos pelo portal de carreiras.
author: andreabichsel
manager: AnnBe
ms.date: 09/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-09-23
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: e1d72bef6d8bbe15e27326f66341915ba44a09b4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4460295"
---
# <a name="attract-users-cant-apply-for-jobs-from-career-portal"></a>Os usuários do Attract não podem se candidatar a empregos pelo portal de carreiras

[!include [banner](includes/banner.md)]

## <a name="issue"></a>Problema

Os usuários do Attract não podem se candidatar a empregos no portal de carreiras. Ao tentarem se candidatar a um trabalho criado no Dynamics 365 Talent: Attract, o navegador carrega a página continuamente e não conclui a ação.

## <a name="cause"></a>Causa

Esse problema ocorre quando a equipe de relacionamento de talento não tem a função de usuário de talento.

## <a name="resolution"></a>Resolução

Atribua a função de usuário de talento à equipe de relacionamento de talento.

1. Entre na [central de administração do Power Platform](https://admin.powerplatform.microsoft.com) com uma das seguintes credenciais de administrador:

   - Administrador do Dynamics 365
   - Administrador global
   - Administrador do Power Platform

2. No painel de navegação, selecione **Ambientes** e selecione o ambiente em que você atribuirá a função de usuário de talento à equipe de relacionamento de talento.

   ![Selecionar ambiente](./media/attract-troubleshoot-career-portal-select-environment.png)

3. No painel **Ambientes**, selecione a **URL de ambiente** e entre no portal de administração do ambiente (por exemplo, https:<orgname>. crm.dynamics.com).

4. Selecione **Configurações**, **Sistema** e **Segurança**.

   ![Navegue até Segurança](./media/attract-troubleshoot-career-portal-security.png)

5. Selecione **Equipes**.

   ![Selecione Equipes](./media/attract-troubleshoot-career-portal-security-teams.png)

6. Procure **Equipe de relacionamento de talento** na caixa de pesquisa e selecione a equipe nos resultados de pesquisa.

7. Selecione **GERENCIAR FUNÇÕES** na faixa de opções.

8. Na caixa de diálogo **Gerenciar Funções da Equipe**, selecione **Usuário de talento** na lista de funções disponíveis e, em seguida, selecione **OK** para aplicar a função.

   ![Aplicar função](./media/attract-troubleshoot-career-portal-apply-role.png)

9. Teste as alterações:

   1. Entre no portal de carreira em uma nova janela do navegador.
   2. Candidatar-se ao emprego no portal de carreiras. 