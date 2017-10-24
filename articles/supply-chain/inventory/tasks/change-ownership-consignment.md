---
title: "Alterar a propriedade de estoque de consignação com base na demanda de produção"
description: "Este procedimento mostra como alterar o proprietário de estoque de remessa do fornecedor à entidade legal quando há uma demanda para o estoque na produção."
author: perlynne
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 5925f5423d596adc4326dfff4734de2afd80b5a8
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="change-the-ownership-of-consignment-inventory-based-on-production-demand"></a>Alterar a propriedade de estoque de consignação com base na demanda de produção

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como alterar o proprietário de estoque de remessa do fornecedor à entidade legal quando há uma demanda para o estoque na produção. Esta alteração de propriedade é feita criar e lançar um diário de alteração de propriedade do estoque. As linhas de diário da alteração de propriedade podem ser criadas manualmente ou, como mostra do registro, com base em demanda existente de produção. Normalmente, um supervisor de fábrica executa esta tarefa. Você pode usar esse procedimento na empresa de dados demonstrativos USMF ou nos seus próprios dados. Se estiver usando seus próprios dados, verifique se você tem os seguintes pré-requisitos: um nome de diário de estoque que é configurado para a alteração de propriedade de estoque, itens disponíveis fisicamente de lucros registrados, e uma ou mais linhas de ordem de produção para material. Este procedimento é para um recurso que foi adicionado à versão 1611 do Dynamics 365 for Operations.


## <a name="create-an-inventory-ownership-journal"></a>Criar um diário de propriedade de estoque
1. Vá para Gerenciamento de estoque > Entradas de diário > Itens > Alteração de propriedade de estoque.
2. Clique em Novo.
    * O diário da alteração de propriedade de estoque é usado para alterar o proprietário de estoque de remessa do fornecedor à entidade legal atual. Esta alteração de propriedade é feita liberando o estoque disponível que pertence o fornecedor e em seguida recebimento do estoque na entidade legal atual.  
3. No campo Nome, insira ou selecione um valor.
    * Você só pode selecionar os nomes de diário de estoque com um tipo de diário de alteração de propriedade.  
4. Clique em OK.
5. Clique em Funções.
6. Clique em Criar linhas de diário a partir de ordens de produção.
    * Você pode iniciar o processo a alteração de propriedade consultando todas as linhas de produção com a solicitação para o consumo de matéria-prima.  
7. Os status de saída de estoque para incluir o campo, selecione uma opção.
    * Esta opção permite filtrar por status de saída de transações de estoque. Por exemplo, você pode criar linhas de diário do estoque com os status físicas separados e reservados.  
8. Expanda os Registros para incluir a seção.
    * Esta seção permite aplicar filtros adicionais. Por exemplo, você pode selecionar uma data específica de matéria-prima.  
9. Clique em OK.

## <a name="post-the-inventory-ownership-change-journal"></a>Lançar o diário de alteração de propriedade de estoque
1. Clique em Lançar.
    * Quando o diário for lançado, o estoque pertencido ao fornecedor é liberado usando uma referência "Alteração de posse". O estoque é recebido em como disponíveis usando uma transação de estoque que é atualizada com um recebimento de produtos de ordem de compra. Observe que somente as transações relacionadas ao diário lançado serão criadas. Nenhuma transação de estoque foi criada.  
2. Clique em OK.
3. Feche a página.

