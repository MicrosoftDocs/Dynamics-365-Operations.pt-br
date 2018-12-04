--- 
title: "Configurar registros de depreciações (maio de 2016)"
description: "Esse guia da tarefa criará um novo registro de depreciações e irá associá-lo com um grupo de ativo fixo."
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepBookTable, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 1fd53ea1dff9b116d19c525c5d6967ece0993b6f
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="set-up-depreciation-books-may-2016"></a>Configurar registros de depreciações (maio de 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esse guia da tarefa criará um novo registro de depreciações e irá associá-lo com um grupo de ativo fixo.  Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.


## <a name="create-a-depreciation-book"></a>Crie um registro de depreciação
1. Vá para Ativos fixos > Configuração > Registros de depreciação.
2. Clique em Novo.
3. No campo de registro de depreciação, insira um valor.
4. No campo Descrição, digite um valor.
5. Marcar ou desmarcar a caixa de seleção Calcular depreciação.
6. No campo Perfil de depreciação, clique no botão suspenso para abrir a pesquisa.
7. Na lista, localize e selecione o perfil de depreciação desejado.
8. Na lista, clique no link na linha selecionada.
9. No campo Perfil de depreciação alternativa, clique no botão suspenso para abrir a pesquisa.
10. Na lista, selecione o perfil de depreciação desejado.
11. Na lista, clique no link na linha selecionada.
    * O perfil de depreciação extraordinário é usado para depreciação adicional para um ativo em condições incomuns. Por exemplo, você pode usá-lo para registrar a depreciação que resulta de acidentes naturais.  
12. Marque ou desmarque a caixa de seleção Criar ajustes de depreciação com ajustes de base.
13. No campo Calendário, clique no botão suspenso para abrir a pesquisa.
14. Na lista, clique no link na linha selecionada.

## <a name="associate-the-depreciation-book-with-a-fixed-asset-group"></a>Associar o registro de depreciação a um grupo de ativo fixo
1. Clique em Grupos de ativos fixos.
2. No campo Grupo de ativo fixo, clique no botão suspenso para abrir a pesquisa.
3. Na lista, localize e selecione o registro desejado.
4. Na lista, clique no link na linha selecionada.
5. No campo Convenção de depreciação, selecione uma opção.
6. No campo Vida útil, insira um número.
    * Observe que o valor do campo de períodos de depreciação será calculado depois de definir a vida útil.  


