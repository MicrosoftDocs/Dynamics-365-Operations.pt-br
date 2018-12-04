--- 
title: Processar juros
description: "Este procedimento mostra como criar, imprimir e lançar notas de juros."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustPosting, SysQueryForm, CustInterestNote, SrsReportViewerForm
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 543ac29ac1b1cbad52f1c155ac90b04d0c122a1f
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="process-interest"></a>Processar juros

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como criar, imprimir e lançar notas de juros. Esta tarefa usa a empresa de demonstração USMF.


## <a name="set-up-interest-on-the-posting-profile"></a>Configure o juros no perfil de lançamento
1. Vá para Crédito e coleções > Configuração > Perfis de lançamento de cliente.
2. Clique em Editar.
    * Selecione um código de juros na lista suspensa. Se você não desejar que os juros sejam calculados para as transações com o perfil de lançamento, deixe o campo em branco.  
    * A guia de restrição de tabela permite que você altere o modo como os juros são processados. Se este campo estiver definido como Sim, os juros serão calculados para este perfil de lançamento.  

## <a name="calculate-interest"></a>Calcular juros
1. Vá para Crédito e coleções > Juros > Criar notas de juros.
    * Você deve selecionar os tipos de transação para os quais calculará o juros. Todas as transações abertas para esses tipos serão incluídas no cálculo.  
    * Se você selecionar juros, você calculará juros em juros. Você pode optar por verificar as leis que regem o cálculo de juros em juros antes de incluir essas transações.  
    * Os juros serão calculados a partir dessa data até "Até data". Se você não especificou uma "Data de", então todas as notas de juros não serão canceladas e os juros serão recalculados da data da transação.  
2. Inserir a data da nota de juros.
    * Há três opções de perfil de lançamento: Conta – use o perfil de lançamento que é atribuído ao cliente para cada nota de juros.   Seleção - use o perfil de lançamento selecionado no campo Perfil de lançamento.   Transação - use o perfil de lançamento individual de transações em que os juros são calculados para cada nota de juros. As transações que não têm um perfil de lançamento atribuído usarão o perfil de lançamento especificado na área Razão e imposto do formulário Parâmetros de conta recebida.  
    * Selecione um perfil de lançamentos aqui se modificou "Usar um perfil de lançamento de" para "Selecionar".  
3. Expanda ou recolha a seção de Registros a serem incluídos.
4. Clique em Filtro.
5. No campo Critérios, insira um ID de cliente. Por exemplo, insira 'US-001'.
6. Clique em OK.
7. Clique em OK.

## <a name="print-interest-notes"></a>Imprimir notas de juros
1. Vá para Crédito e coleções > Juros > Revisar e processar notas de juros.
2. No campo Status, selecione 'Criado'.
3. No campo Impresso, selecione 'Não impresso'.
4. Clique em Imprimir.
5. Expanda ou recolha a seção de Registros a serem incluídos.
6. Clique em OK.
7. Feche a página.

## <a name="post-the-interest-note"></a>Lançar a nota de juros
1. Selecione uma nota de juros que está pronta para ser lançada (o status é criado).
2. Clique em Lançar.
3. Digite a data de lançamento para as notas de juros.
    * Marque Sim para criar uma transação de contabilidade para cada nota de juros.     Se não marcar Sim, os juros em todas as notas de juros ao cliente serão acumulados e lançados na contabilidade em uma transação.  
4. Expanda ou recolha a seção de Registros a serem incluídos.
5. Clique em OK.
6. No campo Status, selecione 'Lançado'.


