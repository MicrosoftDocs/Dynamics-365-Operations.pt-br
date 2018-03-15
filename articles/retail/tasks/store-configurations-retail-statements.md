--- 
title: "Configurações de loja para obter demonstrativos de varejo"
description: "Este procedimento mostra configurações da loja de Varejo que afetam como as instruções de Varejo foram criadas e lançadas."
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 441ba692f559f9966f3e2512c7760ad2f732b768
ms.contentlocale: pt-br
ms.lasthandoff: 02/07/2018

---
# <a name="store-configurations-for-retail-statements"></a>Configurações de loja para obter demonstrativos de varejo

[!include[task guide banner](../includes/task-guide-banner.md)]

Este procedimento mostra configurações da loja de Varejo que afetam como as instruções de Varejo foram criadas e lançadas. As dimensões financeiras em lojas de Varejo são cobertas em outro procedimento. Este procedimento usa a empresa de dados de demonstração USRT.

1. Vá para Varejo e comércio > Canais > Lojas de varejo > Todas as lojas de varejo.
2. Na lista, localize e selecione o PDV desejado.
3. Na lista, clique no link na linha selecionada.
    * As configurações na seção Demonstrativo/fechamento afetam a criação, a validação e lançamento da seção para o armazenamento.  Abra a seção Demonstrativo/fechamento.  
    * Selecione o método que deseja usar para agrupar as linhas do demonstrativo.  
    * Selecione “Sim”, se tiver que haver apenas uma instrução criada por dia ao criar demonstrativos do trabalho em lotes de criação do demonstrativo.  
    * O campo Cálculo da declaração de meios de pagamento define se as declarações de proposta devem ser adicionadas juntas ou se a última deve ser usada.  
    * Selecione a conta contábil para lançar nas diferenças de arredondamento.  
    * No campo Diferença máxima de arredondamento, você pode inserir a diferença máxima de arredondamento permitida.  
    * No campo Lançamentos, você pode inserir a diferença máxima total de lançamentos permitida para um demonstrativo.  
    * No campo Turno, você pode inserir a diferença máxima total dentro de um turno em um demonstrativo.  
    * No campo da transação, você pode inserir a diferença total máxima em uma linha do demonstrativo.  
    * No campo Método de fechamento, você pode definir se as transações que serão incluídas em um demonstrativo devem ser parte de um turno fechado ou se podem ser quaisquer transações no intervalo de data/hora definido.  
    * No campo Fim do dia útil, você pode inserir um horário, se as transações que ocorrem depois da meia-noite tiverem que ser lançadas com o dia anterior.  
    * Selecione “Sim”, se as transações que ocorrerem depois da meia-noite tiverem que ser lançadas como parte do dia anterior.  
    * Selecione "Sim" para obter instruções criadas para cada método do demonstrativo definido. Isso pode ser útil se o desempenho de lançamentos precisar ser aprimorado para armazenamentos com volumes altos de transação, já que criará vários demonstrativos menores que podem ser processadas em paralelo.  
    * No campo Cliente padrão, você pode selecionar a conta de cliente a ser usada para vendas para clientes sem marcação.  


