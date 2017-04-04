---
title: "Lançar com livros derivados"
description: Este artigo descreve como usar registros de registros derivadas.
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3421
ms.assetid: f5187c21-eec5-4148-b178-b8a5feff7f23
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: ca077727910059878fb16a3f78c5b9133c6c741f
ms.lasthandoff: 03/31/2017


---

# <a name="post-with-derived-books"></a>Lançar com livros derivados

Este artigo descreve como usar registros de registros derivadas.

Quando você lança transações para um registro que contém registros derivados, as transações do registro de depreciações derivadas são lançadas automaticamente a partir dos diários, das ordens de compra ou do faturamento de texto livre. Entretanto, se as transações primárias do registro forem preparadas no diário de Ativos fixos, você poderá exibir e modificar os valores das transações derivadas antes de lançá-las.
-   Certas contas, como as contas de impostos sobre vendas, de cliente ou de fornecedor, são atualizadas apenas uma vez pelos lançamentos do método de depreciação primário. As transações de registro derivado são lançadas nas contas definidas para o registro derivado na página Perfis de lançamento de ativo fixo.
-   A aquisição geralmente é usada como o tipo de transação para o registro derivado. Use essa opção quando o registro e o registro de depreciações derivadas devem ser aplicados ao ativo fixo a partir do momento da aquisição desse ativo.
-   Outros valores do tipo de transação também podem ser aplicados. Por exemplo, se o registro principal e os registros de depreciações derivadas tiverem os mesmos intervalos relativos à venda ou à alienação, todos os tipos de transação de ativo fixo estarão disponíveis para a configuração de um registro derivado.

> [!WARNING]
> A depreciação lançada no registro de depreciações derivadas terá o mesmo valor que foi lançado para o registro principal. Se os métodos de depreciação forem diferentes, as transações de registros não devem ser geradas usando o processo derivado. |

## <a name="example"></a>Exemplo 
As informações a seguir descrevem como configurar transações de aquisição com a funcionalidade do registro derivado.

1.  Crie os registros na página de registros.
    -   O registro para contabilidade: VM 1, Nível de lançamento atual
    -   O registro para fins de tributação: VM 2, Nível de lançamento de imposto

2.  Em VM 1, clique na guia registro derivados. Selecione VM 2 no campo registro e Aquisição no campo Tipo de transação.

Em seguida, os registros poderão ser anexados a ativos fixos específicos. 

Quando uma aquisição é lançada para um ativo com registro VM 1, a aquisição é lançada não só em VM 1, mas também no livro derivado VM 2. O status de ambos corrigidos - os registros de ativos são atualizados para abrir.

> [!NOTE]                                                                                                         
> Se você não usar registros derivados, será necessário lançar a aquisição do ativo fixo tanto para o método VM 1 como para o registro VM 2.

Para obter mais informações, consulte o white [] derivados (derived-books.md)


