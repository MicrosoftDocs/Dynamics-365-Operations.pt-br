--- 
title: " Configurações de parâmetro para obter demonstrativos de varejo"
description: "Este procedimento demonstra configurações dos parâmetros de varejo que afetam como as instruções de varejo foram criadas e lançadas."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: ba3b528f8739e4e84ffdbeea5d0af5817f2d9c10
ms.contentlocale: pt-br
ms.lasthandoff: 07/28/2017

---
# <a name="parameter-configurations-for-retail-statements"></a> Configurações de parâmetro para obter demonstrativos de varejo

[!include[task guide banner](../includes/task-guide-banner.md)]

Este procedimento demonstra configurações dos parâmetros de varejo que afetam como as instruções de varejo foram criadas e lançadas. Este procedimento usa a empresa de dados de demonstração USRT.

1. Vá para Varejo e comércio > Configuração da sede > Parâmetros > Parâmetros de varejo.
2. Clique na guia Lançamento.
    * Selecione “Sim” se quiser lançar especificamente os valores de desconto periódico.  
    * Selecione "Padrão" para usar contas padrão, ou selecione “Periódico”, se você quiser definir qual conta usar para cada desconto periódico.  
    * Selecione "Resumo" se as linhas de estoque tiverem que ser agregadas, sempre que possível.  
    * Selecione “Sim” se as notas fiscais e pagamentos retornarem liquidado automaticamente, como parte do processo de lançamento do demonstrativo.  
    * Selecione “Sim” se as transações do cofre de segurança forem agregadas.  
    * Selecione “Sim” se as transações de depósito bancário forem agregadas.  
    * Selecione "Sim" para ativar a agregação para o lançamento do demonstrativo.  
    * Selecione “Sim” para criar e processar ordens em paralelo quando as instruções forem lançadas.  
    * Insira as ordens máximas a serem processadas em cada tarefa do trabalho em lotes.  
3. Clique em Salvar.


