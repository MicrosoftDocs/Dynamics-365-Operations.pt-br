--- 
title: Configurar registros
description: "Este procedimento mostra a você como criar um novo registro de ativos fixos e associá-lo a um grupo de ativos fixos."
author: saraschi2
manager: AnnBe
ms.date: 10/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 668fea64810524e8ce0c3833d25656c026f2780a
ms.openlocfilehash: 7e57b26c17d3bf773a719f9725d5f47dce2af6f7
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2017

---
# <a name="set-up-books"></a>Configurar registros

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra a você como criar um novo registro de ativos fixos e associá-lo a um grupo de ativos fixos. Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.


## <a name="create-a-book"></a>Criar um registro
1. Vá para Ativos fixos > Configuração > Registros.
2. Clique em Novo.
3. No campo Registro, digite um valor.
4. No campo Descrição, digite um valor.
    * Se a opção Calcular a depreciação for selecionada, o registro de ativos associado será incluído nas propostas de depreciação. Se não estiver selecionado, o registro de ativos não será depreciado automaticamente.  
5. Selecione Sim no campo Calcular depreciação.
6. No campo Perfil de depreciação, insira ou selecione um valor.
    * Um perfil de depreciação alternativo também é conhecido como um método alternativo de depreciação. A proposta de depreciação alternará para esse perfil quando o perfil alternativo calcular um valor de depreciação que seja igual ou maior do que o perfil de depreciação padrão.  
    * O perfil de depreciação extraordinário é usado para depreciação adicional para um ativo em condições incomuns. Por exemplo, você pode usá-lo para registrar a depreciação que resulta de acidentes naturais.  
    * Se criar ajustes de depreciação com os ajustes de base for selecionado, os ajustes de depreciação serão criados automaticamente quando o valor do ativo fixo for atualizado. Se não estiver selecionado, o valor dos ativos atualizados afetará apenas os cálculos de depreciação seguintes.  
7. Selecione Sim no campo Criar ajustes de depreciação com ajustes de base.
    * Por padrão, as transações do registro de ativos serão lançadas na contabilidade. Você pode desabilitar o lançamento na contabilidade para o registro definindo o campo Lançar na contabilidade como Não. Os registros que não são lançados na contabilidade geralmente são usados para relatórios de imposto. Isso fornece flexibilidade adicional para excluir transações históricas do registro de ativos porque elas não foram confirmadas na contabilidade.  
    * O nível de lançamento usará como padrão a camada atual se o registro fizer lançamentos na contabilidade e Nenhuma se não fizer. Atualize o nível de lançamento se você necessitar que as transações desse registro sejam lançadas em uma camada diferente.  
8. No campo Calendário, insira ou selecione um valor.
    * Os registros derivados lançarão transações em registros diferentes ao mesmo tempo. Você cria as transações com o registro principal e, durante um lançamento, uma cópia exata da transação será lançada no registro derivado. Não há recálculo com transações derivadas do registro, portanto ele não deve ser usado para transações de depreciação.  

## <a name="associate-the-book-with-a-fixed-asset-group"></a>Associar o registro a um grupo de ativos fixos
1. Clique em Grupos de ativos fixos.
2. No campo Grupo de ativo fixo, insira ou selecione um valor.
3. No campo Vida útil, insira um número.
    * Observe que os períodos de depreciação são calculados depois de definir a vida útil.  
    * Você pode definir a convenção de depreciação conforme necessário para fins tributários.  


