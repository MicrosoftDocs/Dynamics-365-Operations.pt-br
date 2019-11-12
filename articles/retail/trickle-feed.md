---
title: Criação de ordens baseadas em um fluxo constante para transações de loja de varejo
description: Este tópico descreve a criação de ordens baseadas em um fluxo constante para transações de loja de varejo no Microsoft Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 10/14/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 80233a73dbffc7380503cf03703758b187824c2a
ms.sourcegitcommit: 0262a19e32b2c0c84c731d9f4fbe8ba91822afa3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "2622657"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions-public-preview"></a>Criação de ordens baseadas em um fluxo constante para transações de loja de varejo (Visualização pública)

[!include [banner](includes/banner.md)]

[!include [banner](includes/preview-banner.md)]

No Dynamics 365 Retail versões 10.0.4 e anteriores, o lançamento de demonstrativo de varejo é uma operação de fechamento do dia e todas as transações são lançadas nos registros no final do dia. As grandes transações devem ser processadas em uma janela de tempo limitado, ocasionalmente resultando em falhas no lançamento de demonstrativo e bloqueios de carga. Os varejistas também podem não reconhecer receitas e pagamentos em seu registros durante o dia.

Com a visualização pública criação de ordens baseadas em um fluxo constante apresentada no Retail versão 10.0.5, as transações são processadas durante o dia e somente a reconciliação financeira dos meios de pagamento e outras transações de gerenciamento de caixa são processadas no final do dia. Essa funcionalidade divide a carga de criação de ordens de venda, faturas e pagamentos durante o dia, proporcionando melhor desempenho percebido e a possibilidade de reconhecer receitas e pagamentos nos registros quase que em tempo real. 


## <a name="how-to-use-trickle-feed-based-posting"></a>Como usar o lançamento baseado em um fluxo constante
  
1. Para habilitar o lançamento baseado em um fluxo constante de transações de varejo, acesse **Administração do sistema > Configurar > Configuração da licença** e desabilite a chave **Demonstrativos de varejo**.

2. Na mesma página, habilite a chave de licença **Demonstrativos de varejo (fluxo constante) — Visualização**. Ao habilitar essa chave, verifique se não há nenhum demonstrativo pendente aguardando para ser lançado. 

> [!Important]
> Antes de habilitar a chave de licença **Demonstrativos de varejo (fluxo constante) — Visualização**, verifique se não há nenhum demonstrativo pendente aguardando para ser lançado.

3. O documento do demonstrativo atual será dividido em dois tipos diferentes: demonstrativo transacional e demonstrativo financeiro.

      - O demonstrativo transacional pegará todas as transações de varejo não lançadas validadas e criará ordens de venda, faturas de vendas, diários de pagamentos e de desconto e transações de receita/despesa na cadência que você configurar. Configure esse processo para ser executado com alta frequência para que os documentos sejam criados quando as transações de varejo forem carregadas no Retail Headquarters pelo trabalho P. Com o demonstrativo transacional que já cria ordens de venda e faturas de vendas, não há necessidade real de configurar o trabalho em lotes **Lançar estoque**. No entanto, você ainda poderá usá-lo para atender a necessidades comerciais específicas que possa ter.  
      
     - O demonstrativo financeiro foi projetado para ser criado no final do dia e oferece suporte somente ao método de fechamento **Turno**. Esse demonstrativo estará limitado à reconciliação financeira e criará somente os diários para os valores de diferenças entre o valor contado e o valor da transação dos diferentes meios de pagamento, juntamente com os diários para outras transações de gerenciamento de caixa.   

4. Para calcular o demonstrativo transacional, clique em **Varejo > TI de Varejo > Lançamento do PDV > Calcular demonstrativos transacionais em lote**. Para lançar os demonstrativos do demonstrativo transacional em lote, clique em **Varejo > TI de Varejo > Lançamento do PDV > Lançar demonstrativos financeiros em lote**.

5. Para calcular o demonstrativo financeiro, clique em **Varejo > TI de Varejo > Lançamento do PDV > Calcular demonstrativos financeiros em lote**. Para lançar os demonstrativos financeiros em lote, clique em **Varejo > TI de Varejo > Lançamento do PDV > Lançar demonstrativos financeiros em lote**.

> [!NOTE]
> Os itens de menu **Varejo > TI de Varejo > Lançamento do PDV > Calcular demonstrativos em lote** e **Varejo > TI de Varejo > Lançamento do PDV > Lançar demonstrativos em lote** foram removidos com este novo recurso.

Como alternativa, os tipos de demonstrativo transacional e financeiro podem ser criados manualmente. Acesse **Varejo > Canais > Lojas de varejo** e clique em **Demonstrativos de varejo**. Clique em **Novo** e escolha o tipo de demonstrativo que deseja criar. Os campos na página **Demonstrativos de varejo** e as ações no **Grupo de demonstrativos** da página mostrarão os dados relevantes e as ações baseadas no tipo de demonstrativo selecionado.
