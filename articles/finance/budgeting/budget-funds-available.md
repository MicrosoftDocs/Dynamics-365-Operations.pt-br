---
title: Fundos de orçamentos disponíveis
description: Este artigo apresenta um recurso de fundos de orçamentos disponíveis e oferece informações que podem ajudar você a configurar o controle de orçamento para otimizar o gerenciamento de recursos financeiros da organização.
author: RyanCCarlson2
ms.date: 11/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetControlConfiguration
audience: Application User
ms.reviewer: kfend
ms.custom:
- "60493"
- intro-internal
ms.assetid: be964167-43bc-431d-9adb-48bff32d68d5
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2021-11-28
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: b6f94931ba3514c1c66d80b64846d882861d555c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898230"
---
# <a name="budget-funds-available"></a>Fundos de orçamentos disponíveis

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este artigo apresenta um recurso de fundos de orçamentos disponíveis e oferece informações que podem ajudar você a configurar o controle de orçamento para otimizar o gerenciamento de recursos financeiros da organização.

## <a name="enhanced-calculation-feature-for-budget-funds-available"></a>Recurso de cálculo avançado para fundos de orçamentos disponíveis

O recurso **Rastrear valores apenas de fundos de orçamento disponíveis para cálculo** permite rastrear as tabelas de controle de orçamento subjacentes para estados e tipos de documentos, com base nas configurações na página **Definir parâmetros de controle de orçamento**.

Algumas opções de configuração de controle de orçamento devem ter configurações específicas para o recurso funcionar corretamente. Essas opções são selecionadas ou desmarcadas na guia **Fundos de orçamentos disponíveis** na página **Definir parâmetros de controle de orçamento**. A tabela a seguir mostra as configurações necessárias para o recurso de fundos de orçamentos disponíveis.

| Se essa opção for selecionada | Esta opção também deverá ser selecionada |
| ------------------------- | -------------------------------- |
| Reservas orçamentárias para pré-ônus | Reservas de orçamento para ônus *e* Despesas reais |
| Reservas de orçamento para ônus | Despesas reais |
| Reservas de orçamento para ônus com documentos do tipo Requisição de compra | Reservas orçamentárias para pré-ônus |

Este recurso afeta somente documentos novos. Os valores para documentos existentes continuarão sendo rastreados e mostrados na consulta de estatísticas de controle de orçamento até que uma configuração de fundos de orçamentos disponíveis seja alterada e a nova configuração de controle de orçamento seja ativada. Nesse ponto, os dados de rastreamento de orçamento serão removidos para documentos que foram removidos do cálculo de fundos de orçamentos disponíveis.

É recomendável deixar a opção **Despesas reais não lançadas** desmarcada. Se estiver selecionada, um cálculo de controle de orçamento demorado será feito em documentos não lançados, como faturas do fornecedor pendentes.
