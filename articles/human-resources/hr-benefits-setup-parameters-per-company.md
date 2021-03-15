---
title: Configurar parâmetros de gerenciamento de benefícios por empresa
description: Configure parâmetros para o gerenciamento de benefícios por empresa no Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2943d0095e4c9421725b90e579b7cbb841038ab7
ms.sourcegitcommit: d02fae79d5c02a4bc4f4b16a410c2f5ce026c204
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "4984591"
---
# <a name="configure-benefits-management-parameters-per-company"></a>Configurar parâmetros de gerenciamento de benefícios por empresa

Para cada organização que ofereça benefícios, você deve definir configurações para emails de confirmação de benefícios.

## <a name="configure-confirmation-email-settings"></a>Definir configurações de email de confirmação

1. No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Parâmetros do Human Resources**.

2. Na guia **Gerenciamento de benefícios**, especifique valores para os seguintes campos: 

   | Campo | descrição |
   | --- | --- |
   | **Enviar email de confirmação** | Quando este recurso estiver ativado, um email de confirmação será enviado aos funcionários quando eles verificarem a experiência de registro de benefícios no autoatendimento para funcionários. |
   | **Modelo de email de confirmação** | Selecione o modelo de email da organização a ser usado quando enviar a confirmação do registro. Se você não selecionar um modelo, o seguinte email genérico será enviado:<br><br>%EmployeeFirstName%,<br><br>Parabéns! Você concluiu com êxito o registro de benefícios.<br><br>Obrigado,<br>Benefícios de <nome da empresa/organização> |
   | **Endereço de email padrão do remetente** | O endereço de email a ser usado quando enviar o email de confirmação. |

3. Selecione **Salvar**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]