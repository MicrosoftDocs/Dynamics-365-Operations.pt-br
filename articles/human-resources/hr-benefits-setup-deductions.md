---
title: Configurar deduções
description: Use deduções no Microsoft Dynamics 365 Human Resources para determinar, se houver, quanto deduzir do salário de um funcionário para cada benefício.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b4817cd6370166b6dfdf17b3d733b13374db8f49
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8694897"
---
# <a name="configure-deductions"></a>Configurar deduções


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Use deduções no Microsoft Dynamics 365 Human Resources para determinar, se houver, quanto deduzir do salário de um funcionário para cada benefício. As deduções têm data efetiva, para que você possa manter um registro histórico das informações de dedução. 

1. No espaço de trabalho **Gerenciamento de benefícios** em **Configuração**, selecione **Deduções**.

2. Selecione **Novo**.

3. Especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | **Dedução** | Uma ID exclusiva usada para identificar a dedução de benefícios. |
   | **Descrição** | Uma descrição para a dedução. |
   | **Efetivação** | A data de início. O valor padrão é a data atual do sistema. |
   | **Expiração** | A data de término. O valor padrão é 12/31/2154, o que significa nunca. |
   | **Cabeçalho** | O código de cabeçalho do sistema de folha de pagamento que essa dedução usará para a parte da dedução do funcionário ao processar os benefícios da folha de pagamento. Isso é usado quando você usa um provedor de folha de pagamento de terceiros. |
   | **Referência para dedução na folha de pagamento do funcionário** | O código de dedução do sistema de folha de pagamento que será usado por essa dedução para a parte do funcionário da dedução ao processar os benefícios na folha de pagamento. |
   | **Título do valor** | O código de cabeçalho do sistema de folha de pagamento que esse valor de dedução usará para a parte da dedução do funcionário ao processar os benefícios da folha de pagamento. Isso costuma ser usado quando você usa um provedor de folha de pagamento de terceiros. |
   | **Pode excluir** | Especifica se um valor exportado do Dynamics 365 for Finance and Operations pode fazer com que o valor seja excluído no sistema de folha de pagamento. |
   | **Colunas emparelhadas** | Especifica se o valor do cabeçalho e da dedução deve ser exportado em colunas adjacentes emparelhadas para o sistema da folha de pagamento. |
   | **Alterar a data de efetivação** | A data em que a alteração da dedução do benefício entrará em vigor. Nesta data, as alterações de dedução de benefícios e todos os planos de benefícios associados com essa dedução são atualizados, desde que você execute o processamento da **Atualização de alterações de dedução**. |
   | **Alteração da dedução concluída** | A caixa de seleção **Alteração de dedução concluída** será selecionada automaticamente assim que as alterações de dedução de benefícios forem concluídas pelo processamento de alterações da atualização de dedução. |
   
4. Para controlar e manter alterações na configuração das taxas de benefício, selecione **Ações** e **Manter versões**.

5. Selecione **Salvar**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
