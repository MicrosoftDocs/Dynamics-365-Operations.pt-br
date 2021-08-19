---
title: Processar juros
description: Este procedimento mostra como criar, imprimir e lançar notas de juros.
author: ShivamPandey-msft
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, SysQueryForm, CustInterestNote, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3b97515e29d04866172216fc29af9a8d992568276c5e01acd67ad9d0028ea0c5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6764350"
---
# <a name="process-interest"></a>Processar juros

[!include [banner](../../includes/banner.md)]

Este procedimento mostra como criar, imprimir e lançar notas de juros. Esta tarefa usa a empresa de demonstração USMF.


## <a name="set-up-interest-on-the-posting-profile"></a>Configure o juros no perfil de lançamento
1. No **Painel de navegação**, Acesse **Módulos > Crédito e coleções > Configuração > Perfis de lançamentos de cliente**.
2. Clique em **Editar**.
3. Na **Guia Rápida Configuração**, no campo **Código de juros**, selecione um código de juros na lista suspensa. Se você não desejar que os juros sejam calculados para as transações com o perfil de lançamento, deixe o campo em branco. A guia rápida **Restrição de tabela** permite que você altere o modo como os juros são processados. Se este campo estiver definido como Sim, os juros serão calculados para este perfil de lançamento.  

## <a name="calculate-interest"></a>Calcular juros
1. No **Painel de navegação**, Acesse **Módulos > Crédito e coleções > Juros > Criar notas de juros**.
2. Você deve selecionar os tipos de transação para os quais calculará o juros. Todas as transações abertas para esses tipos serão incluídas no cálculo.  
3. Se você definir **Juros** como "Sim", você calculará juros em juros. Você pode optar por verificar as leis que regem o cálculo de juros em juros antes de incluir essas transações.  
4. No campo **A partir da data**, insira uma data a partir da qual os juros serão calculados. Se você não especificou uma **Data inicial**, então todas as notas de juros não lançadas serão canceladas e os juros serão recalculados da data da transação.
5. No campo **Até**, insira uma data para a qual os juros seriam calculados.
6. No campo **Usar perfil de lançamentos de**, selecione uma opção. Há três opções de perfil de lançamento:
    - Conta – use o perfil de lançamentos atribuído à conta de cliente para cada nota de juros. 
    - Seleção - use o perfil de lançamento selecionado no campo Perfil de lançamento.
    - Transação - use o perfil de lançamento individual de transações em que os juros são calculados para cada nota de juros. As transações que não têm um perfil de lançamento atribuído usarão o perfil de lançamento especificado na área Razão e imposto do formulário Parâmetros de conta recebida.  
7. Expanda a Guia Rápida **Registros a serem incluídos**.
8. Clique em **Filtrar**.
9. No campo **Critérios**, insira uma ID do Cliente. Por exemplo, insira 'US-001'.
6. Clique em **OK**.
7. Clique em **OK**.

## <a name="print-interest-notes"></a>Imprimir notas de juros
1. No **Painel de navegação**, Acesse **Módulos > Crédito e coleções > Juros > Revisar e processar notas de juros**.
2. No campo **Status**, selecione "Criado".
3. No campo **Impresso**, selecione "Não impresso".
4. Clique em **Imprimir**.
5. Expanda a Guia Rápida **Registros a serem incluídos**.
6. Clique em **OK**.
7. Feche a página.

## <a name="post-the-interest-note"></a>Lançar a nota de juros
1. Selecione uma nota de juros que está pronta para ser lançada (o status é criado).
2. Clique em **Enviar**.
3. Digite a data de lançamento para as notas de juros. Marque Sim para criar uma transação de contabilidade para cada nota de juros. Se não marcar Sim, os juros em todas as notas de juros ao cliente serão acumulados e lançados na contabilidade em uma transação.  
4. Expanda a Guia Rápida **Registros a serem incluídos**.
5. Clique em **OK**.
6. No campo **Status**, selecione "Lançado".



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]