---
title: "Definir políticas de despesas"
description: "Você pode definir políticas de despesas que seus trabalhadores devem seguir ao inserir e enviar relatórios de despesas e requisições de viagem no Microsoft Dynamics 365 for Finance and Operations."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 3b2a28fe6acf03e52c292048a797ce997f58bcce
ms.contentlocale: pt-br
ms.lasthandoff: 03/26/2018

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
 
  Você também pode configurar um intervalo de datas no qual as políticas de despesas estão em vigor. Por exemplo, tarifas aéreas para voos entre a Dinamarca      
  e a cidade de Nova Iorque podem ser dispendiosas durante a estação de pico de viagens de férias. É possível definir uma regra de despesas com voos que restrinja o      
  custo dos voos para a cidade de Nova Iorque a um limite de DKK 5000, e você pode especificar que essa regra esteja em vigor entre 15 de março e      
  15 de setembro.

