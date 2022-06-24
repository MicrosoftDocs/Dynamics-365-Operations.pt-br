---
title: Parâmetros de integração da folha de pagamento
description: Este artigo descreve os parâmetros de integração da folha de pagamento do Dynamics 365 Human Resources.
author: marcelbf
ms.date: 06/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-17
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7d784909fc8c5fa05557566b62b19802cd2acece
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896087"
---
# <a name="payroll-integration-parameters"></a>Parâmetros de integração da folha de pagamento


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Para poder usar a integração de folha de pagamento do Dynamics 365 Human Resources, você deve configurar os parâmetros descritos neste artigo.

## <a name="enable-payroll-address"></a>Habilitar endereço da folha de pagamento

Para poder usar o endereço da folha de pagamento, você deve habilitá-lo no [formulário de parâmetros compartilhados](hr-setup-shared-parameters.md) na Guia integração da folha de pagamento.

## <a name="define-the-identification-type"></a>Definir o tipo de identificação

Para expor o ID do tipo de identificação na [entidade de funcionário da folha de pagamento](hr-admin-integration-payroll-api-payroll-employee.md), você deve [configurar os parâmetros de recursos humanos](hr-setup-shared-parameters.md) para cada empresa.

1. No espaço de trabalho **Gerenciamento de benefícios**, nos links, selecione **Parâmetros de Recursos Humanos**. 
2. Na guia **Integração de folha de pagamento**, especifique o valor dos campos a seguir.

| Campo | descrição |
| --- | --- |
| Use tipos de identificação no processamento da folha de pagamento | Quando esta opção é selecionada, o ID do tipo selecionado será exposta na entidade do funcionário da folha de pagamento. |
| Tipo de identificação | O tipo de identificação a ser exposto no campo **mshr_payrollemployeeentityid** da [entidade de funcionário da folha de pagamento](hr-admin-integration-payroll-api-payroll-employee.md). |

## <a name="see-also"></a>Consulte também

[Introdução à API de integração da folha de pagamento](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
