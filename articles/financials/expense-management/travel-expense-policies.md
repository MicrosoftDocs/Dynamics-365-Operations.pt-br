---
title: "Definir políticas de despesas"
description: "Você pode definir políticas que seus trabalhadores devem seguir ao inserir e enviar relatórios de despesas e requisições de viagem Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition."
author: saraschi2
manager: AnnBe
ms.date: 09/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi2
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 940d6f8c3d878c2c12806ad04a092856df2acb33
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="expense-policies"></a>Diretivas de despesas

[!include[banner](../includes/banner.md)]

Você pode definir políticas que seus trabalhadores devem seguir ao inserir e enviar relatórios de despesas e requisições de viagem. A implementação de diretivas de despesas pode ajudá-lo a gerenciar as despesas de forma eficiente. 

Por exemplo, você pode definir uma política para despesas de hotel em Nova Iorque, que determina que as despesas com hotéis por noite não poderão exceder USD 250. Se um trabalhador enviar um relatório de despesas ou uma requisição de viagem na qual a taxa do quarto excede esse valor, o sistema notificará o trabalhador de que o valor da política da despesa foi excedido. É possível configurar a mensagem que o trabalhador receberá quando você definir a política. 

Você pode definir três tipos de política: 

 - Aviso – permite que o trabalhador envie um relatório de despesas ou uma requisição de viagem, mas a despesa será marcada para todos os aprovadores e  
 para o relatório mais recente. 
 - Erro – exige que o trabalhador revise a despesa para cumprimento da política antes do envio do relatório de despesas ou da requisição de viagem. 
 - Justificativa – exige que o trabalhador ou um gerente insira uma justificativa para o excedente do valor da política antes do envio do relatório de despesas ou da requisição de viagem. 

Você também pode configurar um intervalo de datas no qual as políticas de despesas estão em vigor. Por exemplo, as tarifas aéreas para voos entre a Dinamarca e Nova Iorque podem ser caras durante a estação de pico de viagens de férias. Você pode definir uma regra de despesas com voos que restrinja o custo dos voos para Nova Iorque a um limite de DKK 5000 e pode especificar que essa regra estará em vigor entre 15 de março e 15 de setembro. 

