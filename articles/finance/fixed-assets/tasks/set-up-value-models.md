---
title: Configurar modelos de depreciação
description: Este procedimento mostra a você como criar um novo registro de ativos fixos e associá-lo a um grupo de ativos fixos.
author: moaamer
ms.date: 08/12/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, AssetGroupBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 46c26e5fad3c5c60d87c2fea2b29043c69b82b5d
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2021
ms.locfileid: "7344649"
---
# <a name="set-up-value-models"></a>Configurar modelos de depreciação

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../../includes/preview-banner.md)]


Este procedimento mostra a você como criar um novo registro de ativos fixos e associá-lo a um grupo de ativos fixos. Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.

## <a name="create-a-book"></a>Criar um registro
1. Acesse Ativos fixos > Configuração > Registros.
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

  - Os períodos de depreciação são calculados após a vida útil do ativo ser inserida.  
  - A convenção de depreciação pode ser definida conforme necessário para fins fiscais.
  - Para ativos fixos associados a arrendamentos, o valor no campo **Vida útil** será substituído pelo menor entre o prazo de arrendamento no livro de ativos ou a vida útil do ativo. Se o campo **Transferência de propriedade** estiver definido como **Sim** para o registro de arrendamento, o valor no campo **Vida útil** será sempre a vida útil do ativo.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
