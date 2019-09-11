---
title: Configurar os Parâmetros de varejo que afetam demonstrativos de varejo
description: Este tópico demonstra configurações dos parâmetros de varejo que afetam como as instruções de varejo foram criadas e lançadas.
author: josaw1
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b9a0386a4d61395903e82d988244dd131c1febaf
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867262"
---
# <a name="configure-retail-parameters-that-affect-retail-statements"></a>Configurar os Parâmetros de varejo que afetam demonstrativos de varejo

[!include[task guide banner](../includes/task-guide-banner.md)]

Este tópico demonstra configurações dos parâmetros de varejo que afetam como as instruções de varejo foram criadas e lançadas. Este procedimento usa a empresa de dados de demonstração USRT.

1. No painel de navegação, vá para **Módulos > Varejo e comércio > Configuração da sede > Parâmetros > Parâmetros de varejo**.
2. Selecione a guia **Lançamento**.
    - Selecione **Sim** se quiser lançar especificamente os valores de desconto periódico.  
    - Selecione **Padrão** para usar as contas padrão, ou selecione **Periódico** se quiser definir qual conta usar para cada desconto periódico.  
      - Selecione **Resumo** se as linhas de estoque tiverem que ser agregadas, sempre que possível.  
      - Selecione **Sim** se as notas fiscais e pagamentos retornarem liquidado automaticamente, como parte do processo de lançamento do demonstrativo.  
      - Selecione **Sim** se as transações do cofre de segurança forem agregadas.  
      - Selecione **Sim** se as transações de depósito bancário forem agregadas.  
      - Selecione **Sim** para ativar a agregação para o lançamento do demonstrativo.  
      - Selecione **Sim** para criar e processar ordens em paralelo quando as instruções forem lançadas.  
      - Insira as ordens máximas a serem processadas em cada tarefa do trabalho em lotes.  
3. Selecione **Salvar**.

