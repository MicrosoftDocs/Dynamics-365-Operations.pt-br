---
title: Configurar parâmetros de gerenciamento de benefícios por empresa
description: Este artigo descreve como configurar parâmetros para o Gerenciamento de benefícios por empresa no Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 8/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e9516977002280e17ee82bf7581d8d7c5060de2a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904207"
---
# <a name="configure-benefits-management-parameters-per-company"></a>Configurar parâmetros de gerenciamento de benefícios por empresa


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Para cada organização que ofereça benefícios, você deve definir configurações para emails de confirmação de benefícios.

## <a name="configure-confirmation-email-settings"></a>Definir configurações de email de confirmação

1. No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Parâmetros do Human Resources**.

2. Na guia **Gerenciamento de benefícios**, especifique valores para os seguintes campos: 

   | Campo | descrição |
   | --- | --- |
   | **Enviar email de confirmação** | Quando este recurso estiver ativado, um email de confirmação será enviado aos funcionários quando eles verificarem a experiência de registro de benefícios no **Autoatendimento para funcionários**. |
   | **Modelo de email de confirmação** | Selecione o modelo de email da organização a ser usado quando enviar a confirmação do registro. Se você não selecionar um modelo, o seguinte email genérico será enviado:<br><br>%EmployeeFirstName%,<br><br>Parabéns! Você concluiu com êxito o registro de benefícios.<br><br>Obrigado,<br>Benefícios de <nome da empresa/organização> |
   | **Endereço de email padrão do remetente** | O endereço de email a ser usado quando enviar o email de confirmação. |

3. Selecione **Salvar**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
