---
title: Criação de ordens baseadas em um fluxo constante para transações de loja de varejo
description: Este tópico descreve a criação de ordens baseadas em um fluxo constante para transações de loja no Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 09/04/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1f864fd6e3aa62cabd039922ed55ad5f7714f0ce
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5114703"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions"></a>Criação de ordens baseadas em um fluxo constante para transações de loja de varejo

[!include [banner](includes/banner.md)]

No Dynamics 365 Retail versões 10.0.4 e anteriores, o lançamento de demonstrativo de varejo é uma operação de fechamento do dia e todas as transações são lançadas nos registros no final do dia. As grandes transações devem ser processadas em uma janela de tempo limitado, ocasionalmente resultando em falhas no lançamento de demonstrativo e bloqueios de carga. Os varejistas também podem não reconhecer receitas e pagamentos em seu registros durante o dia.

Com a criação de ordens baseadas em um fluxo constante apresentada no Retail versão 10.0.5, as transações são processadas durante o dia e somente a reconciliação financeira dos meios de pagamento e outras transações de gerenciamento de caixa são processadas no final do dia. Essa funcionalidade divide a carga de criação de ordens de venda, faturas e pagamentos durante o dia, proporcionando melhor desempenho percebido e a possibilidade de reconhecer receitas e pagamentos nos registros quase que em tempo real. 


## <a name="how-to-use-trickle-feed-based-posting"></a>Como usar o lançamento baseado em um fluxo constante
  
1. Para habilitar o lançamento de transações de varejo baseado em um fluxo constante, habilite o recurso chamado **Demonstrativos de varejo — Fluxo constante** usando o gerenciamento de recursos.

    > [!IMPORTANT]
    > Antes de habilitar o recurso, verifique se não há nenhum demonstrativo pendente aguardando para ser lançado.

2. O documento do demonstrativo atual será dividido em dois tipos: demonstrativo transacional e demonstrativo financeiro.

      - O demonstrativo transacional pegará todas as transações de varejo não lançadas e validadas e criará ordens de venda, faturas de vendas, diários de pagamentos e de desconto e transações de receita/despesa na cadência que você configurar. Configure esse processo para ser executado com alta frequência para que os documentos sejam criados quando as transações forem carregadas no Headquarters pelo trabalho P. Com o demonstrativo transacional que já cria ordens de venda e faturas de vendas, não há necessidade real de configurar o trabalho em lotes **Lançar estoque**. No entanto, você ainda poderá usá-lo para atender a necessidades comerciais específicas que possa ter.  
      
     - O demonstrativo financeiro foi projetado para ser criado no final do dia e oferece suporte somente ao método de fechamento **Turno**. Esse demonstrativo estará limitado à reconciliação financeira e criará somente os diários para os valores de diferenças entre o valor contado e o valor da transação dos diferentes meios de pagamento, juntamente com os diários para outras transações de gerenciamento de caixa.   

3. Para calcular o demonstrativo transacional, acesse **Retail e Commerce > TI de Retail e Commerce > Lançamento do PDV > Calcular demonstrativos transacionais em lote**. Para lançar os demonstrativos transacionais em lote, acesse **Retail e Commerce > TI de Retail e Commerce > Lançamento do PDV > Lançar demonstrativos financeiros em lote**.

4. Para calcular o demonstrativo financeiro, acesse **Retail e Commerce > TI de Retail e Commerce > Lançamento do PDV > Calcular demonstrativos financeiros em lote**. Para lançar os demonstrativos financeiros em lote, acesse **Retail e Commerce > TI de Retail e Commerce > Lançamento do PDV > Lançar demonstrativos financeiros em lote**.

> [!NOTE]
> Os itens de menu **Retail e Commerce > TI de Retail e Commerce > Lançamento do PDV > Calcular demonstrativos em lote** e **Retail e Commerce > TI de Retail e Commerce > Lançamento do PDV > Lançar demonstrativos em lote** foram removidos com este novo recurso.

Como alternativa, os tipos de demonstrativo transacional e financeiro podem ser criados manualmente. Acesse **Retail e Commerce > Canais > Lojas** e clique em **Demonstrativos**. Clique em **Novo** e escolha o tipo de demonstrativo que deseja criar. Os campos na página **Demonstrativos** e as ações no **Grupo de demonstrativos** da página mostrarão os dados relevantes e as ações baseadas no tipo de demonstrativo selecionado.
