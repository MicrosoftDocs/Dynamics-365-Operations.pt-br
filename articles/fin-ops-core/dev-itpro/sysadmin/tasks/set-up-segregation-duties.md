---
title: Configurar a diferenciação de direitos
description: Você pode definir regras para separar tarefas que devem ser executadas por usuários diferentes.
author: peakerbl
manager: AnnBe
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1c1521d6bbbe12964fef0942fcc4943f12a4360a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562488"
---
# <a name="set-up-segregation-of-duties"></a>Configurar a diferenciação de direitos

[!include [banner](../../includes/banner.md)]

Você pode definir regras para separar tarefas que devem ser executadas por usuários diferentes. Este conceito é chamado de segregação de direitos. Por exemplo, talvez você não queira que a mesma pessoa confirme o recebimento de mercadorias e processe o pagamento ao fornecedor. Diferenciação de direitos ajuda a reduzir o risco de fraude, além de ajudar a detectar erros ou irregularidades. Você também pode usar a diferenciação de direitos para garantir o cumprimento das políticas de controle interno. Complete o procedimento a seguir para criar uma regra. Você deve ser um administrador do sistema para concluir o procedimento.

1. Vá para **Administração do sistema** > **Segurança** > **Diferenciação de direitos** > **Regras de diferenciação de direitos**.
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

> [!IMPORTANT] 
> A conformidade com as regras de diferenciação de direitos não é verificada quando você cria uma regra. Você pode criar uma regra que crie um conflito para as funções existentes. As atribuições de funções de usuário existentes também podem estar em conflito com a nova regra. Você deve validar a conformidade depois de criar ou modificar uma regra. Para obter mais informações, consulte [Identificar e resolver conflitos na diferenciação de direitos](identify-resolve-conflicts-segregation-duties.md)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]