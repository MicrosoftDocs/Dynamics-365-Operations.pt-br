---
title: Trabalho da posição na folha de pagamento
description: Este tópico fornece detalhes e um exemplo de consulta da entidade Trabalho de posição na folha de pagamento no Dynamics 365 Human Resources.
author: jcart
manager: tfehr
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 72f3109f5bea36a390b04b7165fc3831d777b640
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881928"
---
# <a name="payroll-position-job"></a>Trabalho da posição na folha de pagamento

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico fornece detalhes e um exemplo de consulta da entidade Relacionamento de trabalho de posição na folha de pagamento no Dynamics 365 Human Resources.

## <a name="properties"></a>Propriedades

| Propriedade<br>**Nome físico**<br>**_Tipo_** | Uso | Descrição |
| --- | --- | --- |
| **ID do trabalho**<br>mshr_jobid<br>*Cadeia de caracteres* | Somente leitura<br>Obrigatório |A ID do trabalho. |
| **Válido a partir de**<br>mshr_validto<br>*Compensação de Data/Hora* | Somente leitura <br>Obrigatório | Data a partir da qual a posição e o relacionamento de trabalho são válidos. |
| **Válida até**<br>mshr_validto<br>*Compensação de Data/Hora* | Somente leitura <br>Obrigatório | Data até a qual a posição e o relacionamento de trabalho são válidos.  |
| **ID da posição**<br>mshr_positionid<br>*Sequência de caracteres* | Somente leitura<br>Obrigatório | A ID da posição. |
| **Campo principal**<br>mshr_primaryfield<br>*Sequência de caracteres* | Obrigatório<br>Gerado pelo sistema |  |
| **Valor de ID de trabalho da posição**<br>_mshr_fk_positionjob_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave externa: mshr_PayrollPositionJobEntity da mshr_payrollpositionjobentity |A ID do trabalho associado à posição.|
| **Valor da ID do plano de remuneração fixa**<br>_mshr_fk_fixedcompplan_id_value<br>*GUID* | Somente leitura<br>Obrigatório<br>Chave estrangeira: mshr_FixedCompPlan_id de mshr_payrollfixedcompensationplanentity  | A ID do plano de remuneração fixa associado à posição. |
| **ID da entidade de trabalho da posição na folha de pagamento**<br>mshr_payrollpositionjobentityid<br>*Guid* | Obrigatório<br>Gerado pelo sistema. | Um valor GUID gerado pelo sistema para identificar exclusivamente o trabalho.  |

