--- 
title: "Configurar automatização de reconciliação de frete"
description: "Este procedimento mostra como definir dados para reconciliação automática de frete."
author: ShylaThompson
manager: AnnBe
ms.date: 10/16/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TMSFreightBillType, TMSFreightBillTypeAssignment, TMSCarrierCodeLookup, DefaultDashboard, TMSAuditMaster
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d990efd7c929b15d57d64e850bc3308349abb978
ms.openlocfilehash: b7772ad779495b36941a3dc86cc456d80a964467
ms.contentlocale: pt-br
ms.lasthandoff: 10/17/2018

---
# <a name="set-up-automatic-freight-reconciliation"></a>Configurar automatização de reconciliação de frete

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como definir dados para reconciliação automática de frete. Isso normalmente é feito por um gerente de depósito. Você pode usar este procedimento na empresa USMF de dados de demonstração.


## <a name="set-up-the-freight-bill-type"></a>Configurar o tipo de conta de frete
1. Vá para Gerenciamento de transporte > Configuração > Reconciliação de frete > Tipo de nota de frete.
    * O tipo de conta de fretes define como as contas de frete e faturas de transportadora devem ser correspondidas.  
2. Clique em Novo.
3. No campo Tipo de nota de frete, digite um valor.
4. No campo Assembly do mecanismo, digite 'Microsoft.Dynamics.Ax.Tms.dll'.
    * Esta é a biblioteca de códigos do mecanismo de gerenciamento de transporte padrão.  
5. No campo Classe do mecanismo, digite 'Microsoft.Dynamics.Ax.Tms.Bll.GenericNormalizer'.
    * Esta é a classe do mecanismo de gerenciamento de transporte padrão.  
6. Clique em Novo.
7. No campo Descrição, selecione o valor que deve coincidir na nota de frete e a fatura da transportadora.  
8. No campo Conciliação necessária, selecione "Sim".
    * Se você definir este campo como Sim, significa que o valor selecionado no campo Descrição precisa combinar com a nota de frete e a fatura da transportadora. Se for definido para Não, o campo pode estar em branco em um destes.  
9. Clique em Salvar.

## <a name="set-up-the-freight-bill-type-assignment"></a>Configurar a atribuição do tipo de conta de frete
1. Feche a página.
2. Vá para Gerenciamento de transporte > Configuração > Reconciliação de frete > Atribuições de tipo de nota de frete.
    * A atribuição do tipo de conta de frete é usada para especificar o tipo de conta de frete usado para uma transportadora específica.   
3. Clique em Novo.
4. No campo Modo, insira ou selecione um valor.
5. No campo Transportadora, insira ou selecione um valor.
6. No campo Tipo de nota de frete, selecione o tipo de nota de frete criado anteriormente.
7. Feche a página.

## <a name="set-up-the-audit-master"></a>Configure o planejamento de auditoria
1. Vá para Gerenciamento de transporte > Configuração > Reconciliação de frete > Auditoria mestre.
    * O planejamento de auditoria define limites de tolerância para reconciliação automática de frete. Especifique por quanto os valores monetários na conta de frete e na fatura de transportadora pode diferir e ainda conceder a reconciliação. Também define como cuidar de discrepâncias.  
2. Clique em Novo.
3. No campo ID da auditoria mestre, digite um valor.
4. No campo Transportadora, selecione a mesma transportadora utilizada anteriormente.
5. No campo Tipo de nota de frete, selecione o tipo de nota de frete criado anteriormente.
6. Expandir a seção Tolerância.
7. No campo Nível de tolerância mínimo, insira um número.
8. No campo Nível de tolerância máximo, insira um número.
9. Expandir a seção Resultado.
10. No campo Código de motivo de pagamento a maior, insira ou selecione um valor.
    * Se os valores monetários são diferentes na conta de frete e na nota fiscal da transportadora, os códigos de motivo de pagamento maior/menor especifica as contas que a diferença deve ser registrada sobre, como a diferença está dentro dos níveis de tolerância.  
11. No campo Código de motivo de pagamento a menor, insira ou selecione um valor.
12. Feche a página.


