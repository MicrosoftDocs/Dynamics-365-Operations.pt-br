---
title: Configurar a diferenciação de direitos
description: Você pode definir regras para separar tarefas que devem ser executadas por usuários diferentes.
author: maertenm
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 47747cba7f83d0b43a284750cff232824e00053a
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982397"
---
# <a name="set-up-segregation-of-duties"></a>Configurar a diferenciação de direitos

[!include [banner](../../includes/banner.md)]

Você pode definir regras para separar tarefas que devem ser executadas por usuários diferentes. Este conceito é chamado de segregação de direitos. Por exemplo, você pode não querer que a mesma pessoa confirme o recebimento de mercadorias e processe o pagamento ao fornecedor. Diferenciação de direitos ajuda a reduzir o risco de fraude, além de ajudar a detectar erros ou irregularidades. Você também pode usar a diferenciação de direitos para garantir o cumprimento das políticas de controle interno. Complete o procedimento a seguir para criar uma regra. Você deve ser um administrador do sistema para concluir o procedimento. A empresa de dados demonstrativos utilizada para criar esse procedimento é a DAT. 

1. Vá para **Painel de navegação > Módulos > Administração do sistema > Segurança > Diferenciação de direitos > Regras da diferenciação de direitos**.
2. Clique em **Novo**.
3. No campo **Nome**, digite um valor para a regra.
4. No campo **Primeiro direito**, clique no botão suspenso para abrir a pesquisa.
5. Na lista, localize e selecione o registro desejado. Selecione a primeira tarefa que é controlada pela regra.
6. No campo **Segundo direito**, clique no botão suspenso para abrir a pesquisa. 
7. Na lista, localize e selecione o PDV desejado. Selecione a segunda tarefa que é controlada pela regra.
10. No campo **Gravidade**, selecione uma opção. Selecione a gravidade do risco que ocorre quando o mesmo usuário ou função executam ambas as tarefas.  
11. No campo **Risco de segurança**, digite um valor. Insira uma descrição do risco de segurança.  
12. No campo **Atenuação de segurança**, digite um valor. Insira uma descrição das ações que você toma para atenuar o risco de segurança. Por exemplo, você pode atenuar o risco conduzindo revisões mais detalhadas do processo, conduzindo uma revisão administrativa mensal, ou compartilhando recursos com outros departamentos.     
13. Clique em **Salvar**.

