---
title: Definir políticas de despesas
description: Você pode definir políticas de despesas que seus trabalhadores devem seguir ao inserir e enviar relatórios de despesas e requisições de viagem no Microsoft Dynamics 365 for Finance and Operations.
author: ryansandness
manager: AnnBe
ms.date: 04/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9f0ff56f0ff106bc168b6a27612e08743a539a07
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1514430"
---
# <a name="expense-policies"></a>Diretivas de despesas

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

# <a name="policy-tips"></a>Dicas de política
Aqui estão algumas sugestões que podem ajudá-lo ao criar novas políticas para gerenciamento de despesas. 
* As políticas têm data de efetivação e não começarão a valer se a política for cria com uma data após a data que a despesa ocorreu. Por exemplo, se você estiver criando uma nova política hoje para reforçar uma despesa de refeição máxima de $50, então qualquer despesas existentes inseridas a partir de ontem não serão verificadas contra esta política.
* Ao criar uma política para uma categoria de despesa que pode ser especificada, considere adicionar uma condição para tipo de linha de despesa. Algumas políticas, como a necessidade de um recibo pode não fazer sentido para linhas especificadas e deve ser aplicado apenas a linha do cabeçalho ou a uma linha não especificada. 

# <a name="when-to-evaluate-policies"></a>Quando avaliar políticas

Nos parâmetros de gerenciamento de despesas, há uma opção para avaliar as políticas de gerenciamento de despesas quando uma linha é salva ou quando um relatório de despesa é enviado. Se você optar por avaliar quando uma linha é salva, isso garante que os usuários tenham uma visibilidade antecipada sobre o que precisam fazer para concluir seu relatório de despesas de uma só vez. Caso contrário, você pode atrasar a avaliação de política e economizar tempo se a validação ocorrer no final, durante envio ao fluxo de trabalho.
