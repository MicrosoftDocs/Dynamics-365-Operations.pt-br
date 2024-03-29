---
title: Lançar com registros de depreciações derivados
description: Este artigo descreve como usar registros de registros derivadas.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: kfend
ms.custom: 3421
ms.assetid: f5187c21-eec5-4148-b178-b8a5feff7f23
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d0270ad1e66193832fb1139fca4439b36b5ffb84
ms.sourcegitcommit: dca54dd3afc7c94795d89c63050b105df2c48e3f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2022
ms.locfileid: "9682848"
---
# <a name="post-with-derived-books"></a>Lançar com registros de depreciações derivados

[!include [banner](../includes/banner.md)]

Este artigo descreve como usar registros de registros derivadas.

Quando você lança transações para um registro que contém registros derivados, as transações do registro de depreciações derivadas são lançadas automaticamente a partir dos diários, das ordens de compra ou do faturamento de texto livre. Entretanto, se as transações primárias do registro forem preparadas no diário de Ativos fixos, você poderá exibir e modificar os valores das transações derivadas antes de lançá-las.
-   Certas contas, como as contas de impostos sobre vendas, de cliente ou de fornecedor, são atualizadas apenas uma vez pelos lançamentos do método de depreciação primário. As transações de registro derivado são lançadas nas contas definidas para o registro derivado na página Perfis de lançamento de ativo fixo.
-   A aquisição geralmente é usada como o tipo de transação para o registro derivado. Use essa opção quando o registro e o registro de depreciações derivadas devem ser aplicados ao ativo fixo a partir do momento da aquisição desse ativo.
-   Outros valores do tipo de transação também podem ser aplicados. Por exemplo, se o registro principal e os registros de depreciações derivadas tiverem os mesmos intervalos relativos à venda ou à alienação, todos os tipos de transação de ativo fixo estarão disponíveis para a configuração de um registro derivado.

> [!WARNING]
> A depreciação lançada no registro derivado terá o mesmo valor que foi lançado para o registro principal. Se os métodos de depreciação forem diferentes, as transações de registros não devem ser geradas usando o processo derivado. 

## <a name="example"></a>exemplo 
As informações a seguir descrevem como configurar transações de aquisição com a funcionalidade do registro derivado.

1.  Crie os registros na página de registros.
    -   O registro para contabilidade: VM 1, Nível de lançamento atual
    -   O registro para fins de tributação: VM 2, Nível de lançamento de imposto

2.  Em VM 1, clique na guia Registros derivados. Selecione VM 2 no campo Registro e Aquisição no campo Tipo de transação.

Em seguida, os registros poderão ser anexados a ativos fixos específicos. 

Quando uma aquisição for lançada para um ativo fixo com o livro VM 1, a aquisição não será lançada somente em VM 1, mas também no registro do livro derivado VM 2. O status dos livros de ativo fixo é atualizado para Aberto.

> [!NOTE]                                                                                                         
> Se você não usar registros derivados, será necessário lançar a aquisição do ativo fixo tanto para o método VM 1 como para o registro VM 2.

Para obter mais informações, consulte [Registros derivados](derived-books.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
