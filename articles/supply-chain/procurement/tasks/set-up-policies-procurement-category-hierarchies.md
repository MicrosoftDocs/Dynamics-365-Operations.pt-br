--- 
title: "Configurar políticas para hierarquias de categoria de compras"
description: Use este procedimento para configurar regras para encomendar produtos em uma categoria.
author: mkirknel
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysPolicyListPage, SysPolicy, ProcCategoryAccessPolicyRule, ProcCategoryPolicyRule, EcoResCategorySingleLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 50764f99be04d27e04047824f870e724336cb452
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-policies-for-procurement-category-hierarchies"></a>Configurar políticas para hierarquias de categoria de compras

[!include [task guide banner](../../includes/task-guide-banner.md)]

Use este procedimento para configurar regras para encomendar produtos em uma categoria. As regras são definidas para uma política de compra específica. Os controles de regra de acesso a categoria aos quais os funcionários das categorias de aquisição têm acesso quando criam uma requisição. Quando uma requisição está sendo criada, a política de compras e a regra de acesso à categoria que devem ser aplicados são determinados pela entidade legal e a unidade operacional a qual o funcionário pertence. Você pode usar este procedimento na empresa USMF de dados de demonstração. Normalmente essa tarefa é realizada por um Gerente de compras.


## <a name="find-the-procurement-policy"></a>Encontre a política de obtenção
1. Vá para Compras > Configuração > Políticas > Políticas de compras.
2. Clique no link da política do USMF da política de aquisição.
    * Esta é a política que você adicionará a uma regra. Deve ser uma política ativa.  

## <a name="create-a-category-access-rule"></a>Criar uma regra de acesso de categoria
1. Selecione a regra de política de acesso à categoria.
    * Se o botão Criar regra de política é escurecido, isso se dá porque já há uma regra de política ativa para o acesso à Categoria. Verifique os campos Eficaz e Data de validade para determinar qual é, a seguir selecione-os, e clique em Retirar regra de política. Se o botão da regra da política da criação está disponível, você não precisa fazer nada.  
2. Clique em Criar regra de política.
3. No campo de data efetiva, insira uma data e hora.
    * O tempo não deve sobrepor com uma outra regra que seja ativa.  
    * Selecione uma categoria a que a regra se aplique. Faça uma anotação de que a categoria é – você precisará disso mais tarde. Quando você seleciona uma categoria, todas as suas categorias pai também são adicionadas à lista de categorias Selecionada.  
    * Se você quiser que a regra seja aplicada a todas subcategorias da categoria selecionada, selecione a caixa de seleção Incluir subcategorias.  
4. Clique em Adicionar.
    * Se você definir a opção de Incluir regra principal para Sim, a regra de diretiva definida para uma categoria pai será atribuída a categorias secundárias se nenhuma regra de diretiva for definida para as categorias secundárias.  
5. Clique em OK.

## <a name="create-a-category-policy-rule"></a>Criar uma regra de política de categoria
1. Selecione a regra de política da categoria
    * Se o botão da regra da política da criação é escurecido, selecione a regra da política ativa, e clique então para retirar a regra da política.  
2. Clique em Criar regra de política.
3. No campo de data efetiva, insira uma data e hora.
4. Clique em Adicionar.
5. Selecione a mesma categoria que você usou para a regra do acesso da categoria.
6. No campo Seleção do fornecedor, selecione uma opção.
    * Selecione uma regra para controlar quais tipos de vendedores podem ser selecionados para a categoria quando as requisições são criadas.  
7. Clique em Fechar.
    * A regra de política que você definiu foi para requisições do tipo consumo. Se você quis definir políticas para requisições do tipo Reabastecimento, você criaria uma regra para o tipo de regra de política chamado "Regra de política para acessar reabastecimento de categoria".  


