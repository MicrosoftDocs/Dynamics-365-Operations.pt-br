---
title: "Convertendo a contabilidade ou as moedas de relatório"
description: 
author: RobinARH
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 78223
ms.assetid: 31c56f9a-9c64-40a2-90e3-1969a760614b
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 728af2fff6317c17e47d48ea07dbeb57068fbf3f
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="convert-accounting-or-reporting-currencies"></a>Convertendo a contabilidade ou as moedas de relatório

[!include[banner](../includes/banner.md)]




Uma empresa que deve alterar a moeda contábil ou moeda de relatório apresenta duas opções. A primeira opção é criar uma nova empresa e iniciar a atualização. A segunda opção é executar a contabilidade e o processo de conversão da moeda de relatório. Este é um processo muito longo que modifica cada transação no sistema. Alguma configuração também é necessária antes do processo ser executado.

## <a name="preparing-the-legal-entity-for-currency-conversion"></a>Preparando a entidade legal para uma conversão de moeda
Antes que você possa converter a moeda da entidade legal, você deve reverter quaisquer valores de reavaliação em moeda estrangeira para contas do cliente e do fornecedor e fechar os anos fiscais anteriores. Você também deve preparar o banco de dados para conversão, e fazer as alterações necessárias na conta da entidade legal que está sujeita à conversão de moeda. Depois de concluir uma conversão de moeda, você deverá concluir alguns procedimentos adicionais. Você deverá reconciliar as diferenças de arredondamento em valores convertidos, recalcular estatísticas comerciais, lançar transações do razão, restringir o acesso à ferramenta de conversão e reavaliar valores de moeda estrangeira para contas de cliente e de fornecedor.

## <a name="setting-up-accounts-for-automatic-transactions"></a>Configurando contas para transações automáticas
Durante o processo de conversão de moeda, os lucros ou perdas, ou as diferenças mínimas, são lançados nas contas definidas na página **Contas para transações automáticas**. As contas principais devem ser atribuídas aos seguintes tipos de transação antes do processo de conversão ser executado:

-   Ganho de conversão de moeda contábil
-   Perda por conversão de moeda contábil
-   Diferença mínima na moeda contábil
-   Diferença mínima na moeda de relatório
-   Resultado de fim de ano

## <a name="posting-rounding-differences-and-sum-recalculations"></a>Recálculos de soma e lançamento das diferenças no arredondamento
As informações a seguir explicam onde podem ocorrer diferenças no arredondamento:

-   Se os preços dos produtos tiverem sido convertidos em 0 (zero), um relatório será gerado mostrando o número do produto, o tipo de módulo, o preço antes da conversão e a unidade.
-   As diferenças de arredondamento entre o imposto e a contabilidade são lançadas no diário geral.
-   Os valores de reavaliação de moeda estrangeira são recalculados e os valores de transação do cliente e do fornecedor são recalculados.
-   Registros de liquidação do cliente e do fornecedor são criados para as diferenças de arredondamento em cada transação do cliente e do fornecedor.
-   As diferenças de arredondamento para clientes e fornecedores são lançadas no diário geral.
-   Os valores de custo liquidados e dos valores de ajuste de custo em transações de estoque fechado são recalculados.
-   As diferenças de arredondamento no Gerenciamento de estoque são lançadas no diário geral.
-   O estoque disponível é recalculado.
-   Os valores totais nos diários-razão são recalculados.
-   As folhas de fechamento do razão são recalculadas.
-   Os saldos do razão são recalculados.
-   As diferenças de arredondamento na contabilidade são lançadas no diário geral.
-   As transações do razão abertas são recalculadas.
-   O valor final em saldos do razão é calculado.

Se você estiver convertendo uma nova moeda contábil do razão e ocorrer um erro durante o recálculo dos valores totais ou durante o lançamento das diferenças de arredondamento, você deverá fechar a página **Conversão de moeda contábil do razão**. Os valores totais serão recalculados e as diferenças de arredondamento serão lançadas.

## <a name="processing-the-currency-conversion"></a>Processando a conversão da moeda
Quando você iniciar o processo de conversão de moeda, todos os usuários devem estar desconectados do sistema. Você deve definir a nova moeda do razão ou do relatório e as taxas de câmbio. Quando você clicar em **OK**, o processo será executado e atualizará cada transação do sistema. A conversão de moeda é um processo muito longo. Quando for concluída, você verá que a contabilidade ou a moeda de relatório será atualizada na página **Razão**.

## <a name="completing-the-currency-conversion"></a>Concluindo a conversão da moeda
Depois da conversão de moeda, você deverá gerar todos os relatórios de reconciliação novamente para garantir que todos os valores convertidos estão corretos.

-   Se a conversão da moeda contábil do razão causar diferenças de arredondamento, essas diferenças não serão lançadas usando o comprovante onde a diferença de arredondamento ocorreu. Em vez disso, as diferenças serão lançadas usando o comprovante que foi inserido para lançamentos de conversão. Após a conversão, todos os relatórios que efetuam a verificação por comprovante e data incluirão essas diferenças de arredondamento. Esse comportamento está correto e pode ser ignorado.
-   Se os relatórios de reconciliação de cliente e de fornecedor exibirem um valor de diferença na linha de total, e não houver nenhum valor de diferença antes da conversão, esse valor de diferença deverá ser lançado. A conta é a conta resumo para os clientes e fornecedores. A contrapartida é a conta contábil para a perda por conversão ou o lucro de conversão.

Quando todos os diários de transação do razão tiverem sido excluídos, você poderá lançar as transações do razão no diário. Clique em **Contabilidade** &gt; **Periódico** &gt; **Diários** &gt; **Lançamento em diário**. Você pode reavaliar os valores de moeda estrangeira depois da conversão de moeda, se a reavaliação for necessária. Você reavalia os valores de moeda estrangeira selecionando **Padrão** no campo **Método** da reavaliação.




