---
title: Restringir o acesso da entidade legal a trabalhadores
description: Este artigo explica como configurar o acesso do trabalhador por entidade legal.
author: twheeloc
ms.date: 11/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSharedParameters, HcmPersonnelManagementWorkspace
audience: Application User
ms.custom: 51891
ms.assetid: c7d8f58c-d78a-4035-abbf-2b0ce16109fe
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fadd2c34d31bbd259255596c06a8e7517f7a774b
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780384"
---
# <a name="restrict-access-to-workers-by-legal-entity"></a>Restringir o acesso da entidade legal a trabalhadores

Este artigo explica como configurar o acesso do trabalhador por entidade legal.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Os funcionários são empregados em entidades legais. Veja alguns exemplos:

- Aaron Con está empregado na entidade legal USSI.
- Ahmed Barnett está empregado na entidade legal USMF.
- Alicia Thornber está empregada nas entidades legais GLSI e USMF.

Dependendo da função de um usuário na empresa, talvez eles precisem de acesso para exibir todos os funcionários em todas as entidades legais. Como alternativa, um usuário talvez precise ser restringido para poder exibir somente funcionários na entidade legal à qual ele tem acesso. Para controlar quais funcionários um usuário pode exibir, selecione o parâmetro **Restringir acesso a informações do trabalhador** na página **Parâmetros compartilhados de Recursos Humanos**.

Por exemplo, um usuário tem acesso à página do **Trabalhador** e tem acesso somente à entidade legal USMF. Nesse caso, o usuário pode exibir as seguintes informações para os funcionários na lista anterior:

- Se o recurso para restringir o acesso a informações de trabalhador não estiver habilitado, o usuário poderá exibir informações para Aaron, Ahmed e Alicia.
- Se o recurso estiver habilitado, o usuário poderá exibir informações somente para Alicia e Ahmed, pois eles também são empregados na entidade legal USMF.

As informações mostradas variam de acordo com o aplicativo que você está usando.

## <a name="dynamics-365-human-resources-stand-alone"></a>Dynamics 365 Human Resources autônomo

Se o recurso para restringir o acesso a informações de trabalhador estiver habilitado, o usuário restrito verá um valor em branco em algumas listas que contêm o nome do trabalhador.

Por exemplo, um usuário que tem acesso apenas à entidade legal USMF verá o seguinte comportamento:

- Na lista **Posições ativas**, a coluna **Trabalhador** ficará em branco para a posição de Aaron, porque o usuário não tem acesso aos funcionários da entidade legal USSI.
- Se o usuário detalhar o nome do trabalhador, será exibida uma página do **Trabalhador** em branco.

## <a name="dynamics-365-human-resources-on-finance-infrastructure"></a>Dynamics 365 Human Resources na infraestrutura de Finanças

Se o recurso para restringir o acesso a informações de trabalhador estiver habilitado, o usuário restrito verá o nome do trabalhador em algumas listas.

Por exemplo, um usuário que tem acesso apenas à entidade legal USMF verá o seguinte comportamento:

- Na lista **Posições ativas**, a coluna **Trabalhador** mostrará o nome de Aaron. Se o usuário passar o mouse sobre o nome do trabalhador, somente o nome e o cargo serão exibidos.
- Se o usuário detalhar o nome do trabalhador, será exibida uma página do **Trabalhador** em branco.

> [!TIP]
> Se você estiver usando o Dynamics 365 Human Resources na infraestrutura de Finanças e quiser que os usuários restritos vejam os valores em branco para os nomes dos trabalhadores, você pode adicionar o privilégio de segurança **Restringir acesso aos trabalhadores** às funções de usuário na página **Configuração de segurança**.

Depois de habilitar esse recurso, você deve seguir estas etapas a mais para definir as permissões para cada usuário cujo modo de exibição deve ser restrito.

1. Na página **Usuários**, selecione um usuário.
2. Selecione uma função para o usuário. A opção **Atribuir organizações** é disponibilizada.
3. Selecione **Atribuir organizações**.
4. Na nova página, selecione **Conceder acesso a organizações específicas individualmente** e selecione as organizações às quais o usuário deve ter acesso.
5. Repita as etapas 2 a 4 para cada função do usuário, incluindo a função de usuário do sistema.

> [!NOTE]
> As entidades legais às quais um usuário tem acesso devem coincidir com todas as funções do usuário.
