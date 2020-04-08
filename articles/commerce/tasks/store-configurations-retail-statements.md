---
title: Configurações de loja para obter demonstrativos de varejo
description: Este procedimento mostra configurações da loja de Varejo que afetam como as instruções de Commerce foram criadas e lançadas.
author: jashanno
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 57081b9e737373641cd9d884919d03dcf62a2ffe
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140646"
---
# <a name="store-configurations-for-retail-statements"></a>Configurações de loja para obter demonstrativos de varejo

[!include [banner](../includes/banner.md)]

Este procedimento mostra configurações da loja de Varejo que afetam como as instruções de Commerce foram criadas e lançadas. As dimensões financeiras em lojas são cobertas em outro procedimento. Este procedimento usa a empresa de dados de demonstração USRT.

1. No **Painel de navegação**, acesse **Módulos > Retail e Commerce > Canais > Lojas > Todas as lojas**.
2. Na lista, localize e selecione o registro desejado.
3. Na lista, clique no link na linha selecionada.
4. Clique em **Editar**.
5. As configurações na Guia Rápida **Demonstrativo/fechamento** afetam a criação, a validação e lançamento da seção para o armazenamento. Expanda a Guia Rápida **Demonstrativo/fechamento**.  
6. No campo **Método do demonstrativo**, selecione o método que deseja usar para agrupar as linhas do demonstrativo.  
7. Selecione “Sim” em **Um demonstrativo por dia**, se tiver que haver apenas uma instrução criada por dia ao criar demonstrativos do trabalho em lotes de criação do demonstrativo.  
8. O campo **Cálculo da declaração de meios de pagamento** define se as declarações de proposta devem ser adicionadas juntas ou se a última deve ser usada.  
9. No campo **Arredondamento**, selecione a conta contábil para lançar nas diferenças de arredondamento.  
10. No campo **Diferença máxima de arredondamento**, insira a diferença máxima de arredondamento permitida.
11. No campo **Lançamentos**, insira a diferença máxima total de lançamentos permitida para um demonstrativo.
12. No campo **Turno**, você pode inserir a diferença máxima total dentro de um turno em um demonstrativo.  
13. No campo **Transação**, insira a diferença total máxima em uma linha do demonstrativo.  
14. No campo **Método de fechamento**, defina se as transações que serão incluídas em um demonstrativo devem ser parte de um turno fechado ou se podem ser quaisquer transações no intervalo de data/hora definido.  
15. No campo **Fim do dia útil**, insira um horário, se as transações que ocorrem depois da meia-noite tiverem que ser lançadas com o dia anterior.  
16. Selecione “Sim” em **Lançar como dia útil**, se as transações que ocorrerem depois da meia-noite tiverem que ser lançadas como parte do dia anterior.  
17. Selecione "Sim" em **Método Dividir por Demonstrativo** para obter instruções criadas para cada método do demonstrativo definido. Isso pode ser útil se o desempenho de lançamentos precisar ser aprimorado para armazenamentos com volumes altos de transação, já que criará vários demonstrativos menores que podem ser processadas em paralelo.  
18. Na Guia Rápida **Gera**, no campo **Cliente padrão**, você pode selecionar a conta de cliente a ser usada para vendas para clientes sem marcação.  

