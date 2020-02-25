---
title: Configurar deduções
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7ee9e8f3bc0e9027e41d3aa91bd097a3f046cbb4
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008112"
---
# <a name="configure-deductions"></a>Configurar deduções

[!include [banner](includes/preview-feature.md)]

Use deduções no Microsoft Dynamics 365 Human Resources para determinar, se houver, quanto deduzir do salário de um funcionário para cada benefício. As deduções têm data efetiva, para que você possa manter um registro histórico das informações de dedução. 

1. No espaço de trabalho **Gerenciamento de benefícios** em **Configuração**, selecione **Deduções**.

2. Selecione **Novo**.

3. Especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | Dedução | Uma ID exclusiva usada para identificar a dedução de benefícios. |
   | Descrição | Uma descrição para a dedução. |
   | Efetivação | A data de início. O valor padrão é a data atual do sistema. |
   | Expiração | A data de término. O valor padrão é 12/31/2154, o que significa nunca. |
   | Cabeçalho | O código de cabeçalho do sistema de folha de pagamento que essa dedução usará para a parte da dedução do funcionário ao processar os benefícios da folha de pagamento. Isso é usado quando você usa um provedor de folha de pagamento de terceiros. |
   | Referência para dedução na folha de pagamento do funcionário | O código de dedução do sistema de folha de pagamento que será usado por essa dedução para a parte do funcionário da dedução ao processar os benefícios na folha de pagamento. |
   | Título do valor | O código de cabeçalho do sistema de folha de pagamento que esse valor de dedução usará para a parte da dedução do funcionário ao processar os benefícios da folha de pagamento. Isso costuma ser usado quando você usa um provedor de folha de pagamento de terceiros. |
   | Pode excluir | Especifica se um valor exportado do Dynamics 365 for Finance and Operations pode fazer com que o valor seja excluído no sistema de folha de pagamento. |
   | Colunas emparelhadas | Especifica se o valor do cabeçalho e da dedução deve ser exportado em colunas adjacentes emparelhadas para o sistema da folha de pagamento. |
   | Alterar a data de efetivação | A data em que a alteração da dedução do benefício entrará em vigor. Nesta data, o sistema alterará automaticamente a dedução de benefícios e atualizará todos os planos de benefícios associados a essa dedução, desde que você execute o processamento da atualização de alterações de dedução. |
   | Alteração da dedução concluída | A caixa de seleção Alteração de dedução concluída será selecionada automaticamente assim que as alterações de dedução de benefícios forem concluídas pelo processamento de alterações da atualização de dedução. |
   
4. Para controlar e manter alterações na configuração das taxas de benefício, selecione **Ações** e **Manter versões**.

5. Selecione **Salvar**. 
