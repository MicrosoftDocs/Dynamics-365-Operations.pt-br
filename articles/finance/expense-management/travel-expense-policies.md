---
title: Definir políticas de despesas
description: Você pode definir políticas de despesas que seus trabalhadores devem seguir ao inserir e enviar relatórios de despesas e requisições de viagem no Microsoft Dynamics 365 Finance.
author: suvaidya
manager: AnnBe
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 22504e0e26c025d117f29dee3b59b41d508e7724
ms.sourcegitcommit: 4f90b9ddedf312e75a714e0ec7f7ee5fd43cac6a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/21/2020
ms.locfileid: "3389706"
---
# <a name="define-expense-policies"></a>Definir políticas de despesas

[!include [banner](../includes/banner.md)]

Você pode definir políticas que seus trabalhadores devem seguir ao inserir e enviar relatórios de despesas e requisições de viagem.         
A implementação de diretivas de despesas pode ajudá-lo a gerenciar as despesas de forma eficiente.         

Por exemplo, você pode definir uma política para despesas de hotel em Nova Iorque, que determina que as despesas com hotéis por noite não poderão exceder USD 250.       
Se um trabalhador enviar um relatório de despesas ou uma requisição de viagem em que a taxa de hospedagem exceda esse valor, o sistema notificará o        
trabalhador que o valor da política para a despesa foi excedido. É possível configurar a mensagem que o trabalhador receberá quando você        
definir a política.      
        
Você pode definir três tipos de política:         
        
- Aviso – permite que o trabalhador envie um relatório de despesas ou uma requisição de viagem, mas a despesa será marcada para todos os aprovadores e        
  para o relatório mais recente.        

- Erro – exige que o trabalhador revise a despesa para cumprimento da política antes do envio do relatório de despesas ou da requisição de viagem.       
 
 - Justificativa – exige que o trabalhador ou um gerente insira uma justificativa para o excedente do valor da política antes do envio do relatório de despesas ou da requisição de viagem.        

## <a name="policy-tips"></a>Dicas de política
Aqui estão algumas sugestões que podem ajudá-lo ao criar novas políticas para gerenciamento de despesas. 
* As políticas têm data de efetivação e não começarão a valer se a política for cria com uma data após a data que a despesa ocorreu. Por exemplo, se você estiver criando uma nova política hoje para reforçar uma despesa de refeição máxima de $50, então qualquer despesas existentes inseridas a partir de ontem não serão verificadas contra esta política.
* Ao criar uma política para uma categoria de despesa que pode ser especificada, considere adicionar uma condição para tipo de linha de despesa. Algumas políticas, como a necessidade de um recibo pode não fazer sentido para linhas especificadas e deve ser aplicado apenas a linha do cabeçalho ou a uma linha não especificada. 
* Por padrão, as diretivas de gerenciamento de despesas são avaliadas com base na entidade de origem. Para cenários intercompanhia, você pode definir a diretiva a ser avaliada em relação à entidade de destino (entidade emprestada). Para executar as diretivas em relação à entidade de destino, ative o recurso "Avaliar a diretiva de despesas em relação à entidade legal de empréstimo" no espaço de trabalho **Gerenciamento de recursos**.

## <a name="when-to-evaluate-policies"></a>Quando avaliar políticas

Nos parâmetros de gerenciamento de despesas, há uma opção para avaliar as políticas de gerenciamento de despesas quando uma linha é salva ou quando um relatório de despesa é enviado. Se você optar por avaliar quando uma linha é salva, isso garante que os usuários tenham uma visibilidade antecipada sobre o que precisam fazer para concluir seu relatório de despesas de uma só vez. Caso contrário, você pode atrasar a avaliação de política e economizar tempo se a validação ocorrer no final, durante envio ao fluxo de trabalho.
