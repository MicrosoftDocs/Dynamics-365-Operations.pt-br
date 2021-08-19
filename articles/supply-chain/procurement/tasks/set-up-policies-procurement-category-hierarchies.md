---
title: Configurar políticas para hierarquias de categoria de compras
description: Use este procedimento para configurar regras para encomendar produtos em uma categoria.
author: kamaybac
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysPolicyListPage, SysPolicy, ProcCategoryAccessPolicyRule, ProcCategoryPolicyRule, EcoResCategorySingleLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 242dd46e8b54504924f5bd13404dd9780c112cff8339d0a645785b2d4243871a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6760433"
---
# <a name="set-up-policies-for-procurement-category-hierarchies"></a>Configurar políticas para hierarquias de categoria de compras

[!include [banner](../../includes/banner.md)]

Use este procedimento para configurar regras para encomendar produtos em uma categoria. As regras são definidas para uma política de compra específica. Os controles de regra de acesso a categoria aos quais os funcionários das categorias de aquisição têm acesso quando criam uma requisição. Quando uma requisição está sendo criada, a política de compras e a regra de acesso à categoria que devem ser aplicados são determinados pela entidade legal e a unidade operacional a qual o funcionário pertence. Você pode usar este procedimento na empresa USMF de dados de demonstração. Normalmente essa tarefa é realizada por um Gerente de compras.


## <a name="find-the-procurement-policy"></a>Encontre a política de obtenção
1. No Painel de navegação, Acesse **Módulos > Compras e fornecimento > Configuração > Políticas > Políticas de compras**.
2. Clique no link da política do 'USMF da política de aquisição'. Esta é a política que você adicionará a uma regra. Deve ser uma política ativa.  

## <a name="create-a-category-access-rule"></a>Criar uma regra de acesso de categoria
1. Expanda a Guia rápida **Regras de política**.
2. Na lista **Tipo de regra de política** , selecione **Regra de política de acesso de categoria**. Se o botão **Criar regra de política** estiver esmaecido, isso se dá porque já há uma regra de política ativa para o acesso à Categoria. Verifique os campos **Efetivação** e **Validade** para determinar qual é e então selecione-o, e clique em **Desativar regra de política**. Se o botão **Criar regra de política** estiver disponível, você não precisará fazer nada.  
3. Clique em **Criar regra de política**.
4. No campo **Data de efetivação**, insira uma data e hora. O tempo não deve sobrepor com uma outra regra que seja ativa.  
5. Selecione uma categoria a que a regra se aplique. Faça uma anotação de que a categoria é – você precisará disso mais tarde. Quando você seleciona uma categoria, todas as suas categorias pai também são adicionadas à lista de categorias Selecionada. Se você quiser que a regra seja aplicada a todas subcategorias da categoria selecionada, marque a caixa de seleção **Incluir subcategorias**.
6. Clique na seta para a direita para adicionar à lista **Categorias selecionadas**.  
4. Clique em **OK**. Se você definir a opção de **Incluir regra principal** como Sim, a regra de política definida para uma categoria pai também será atribuída a suas categorias secundárias se nenhuma regra de política for definida para as categorias secundárias.

## <a name="create-a-category-policy-rule"></a>Criar uma regra de política de categoria
1. Na lista **Tipo de regra de política** , selecione **Regra de política de categoria**. Se o botão **Criar regra da política** estiver esmaecido, selecione a regra de política ativa e clique em **Desativar regra de política**.  
2. Clique em **Criar regra de política**.
3. No campo **Data de efetivação**, insira uma data e hora.
4. Clique em **Adicionar**.
5. No campo **Categoria**, selecione a mesma categoria que você usou para a **Regra do acesso da categoria**.
6. No campo **Seleção do fornecedor**, selecione uma opção. Selecione uma regra para controlar quais tipos de vendedores podem ser selecionados para a categoria quando as requisições são criadas.  
7. Clique em **Fechar**. A regra de política que você definiu foi para requisições do tipo consumo. Se você quis definir políticas para requisições do tipo Reabastecimento, você criaria uma regra para o tipo de regra de política chamado "Regra de política para acessar reabastecimento de categoria".  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]