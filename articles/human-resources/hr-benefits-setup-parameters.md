---
title: Definir parâmetros de gerenciamento de benefícios
description: Configure parâmetros para o gerenciamento de benefícios no Microsoft Dynamics 365 Human Resources.
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
ms.openlocfilehash: ab9b1fc78ce42479d9265b80337adf899cec3866
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008099"
---
# <a name="set-benefits-management-parameters"></a>Definir parâmetros de gerenciamento de benefícios

[!include [banner](includes/preview-feature.md)]

Antes de configurar planos de licença no Microsoft Dynamics 365 Human Resources, você precisa configurar os parâmetros de gerenciamento de benefícios. Esses parâmetros definem valores padrão, códigos de motivo e outras opções.

## <a name="configure-general-parameters"></a>Configurar parâmetros gerais

1. No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Parâmetros**.

2. Na guia **Geral**, especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | **País/região** | O campo **País/região** determina a ordem de exibição de CEPs/estados. O país selecionado é exibido primeiro na lista suspensa. |
   | **Código do motivo da inscrição** | Selecione um código de motivo padrão a ser usado quando os planos do funcionário forem criados durante o processamento do inscrição aberta. |
   | **Código do motivo do cancelamento** | O código de motivo a ser usado quando um plano de benefícios do funcionário é cancelado. Ele é exibido em uma caixa de diálogo durante o processo de cancelamento. Os usuários podem alterar o **Código de motivo do cancelamento**, se necessário. |
   | **Código de motivo de reabertura** | O código de motivo a ser usado quando um plano de benefícios do funcionário é reaberto. Ele é exibido em uma caixa de diálogo durante o processo de cancelamento. Os usuários podem alterar o **Código de motivo de reabertura**, se necessário. | 
   | **Código do motivo do evento de vida** | O código de motivo a ser usado quando ocorre um evento de vida. |
   | **Código de motivo da alteração da taxa** | O código de motivo a ser usado ao cancelar e reabrir um plano de benefícios do funcionário durante o processo de atualização de alteração de taxa. Ele indica quais registros foram alterados pelo processo de atualização da alteração de taxa. |
   | **Nova contratação qualificada** | Especifica se novas contratações estão qualificadas. |
   | **Período de inscrição de novas contratações** | O período de tempo em que a nova inscrição de contratação é permitida.</br></br>**Observação**: esta configuração substitui qualquer novo período de inscrição de contratação definido na regra de qualificação para o plano. | 
   | **Aumento de salário anual** | Especifica se é necessário calcular automaticamente o valor do **Salário de benefício anual** em **Detalhes de benefícios do emprego**. Ele se baseia na **Taxa de pagamento de remuneração fixa**, **Média de horas** e **Frequência de pagamento**.</br></br>**Média de horas** x **Taxa de pagamento fixa** x **Frequência de pagamento** (nº de períodos de pagamento) = **Salário de benefício anual** </br></br>Se um dos valores nos campos **Média de horas**, **Taxa de pagamento de remuneração fixa** ou **Frequência de pagamento** for alterado, o sistema recalculará automaticamente o valor do **Salário de benefício anual** do funcionário com base nos valores alterados. O sistema cria um registro de **Data de efetivação** para identificar a data e a hora exatas da alteração. Você pode editar manualmente o valor de **Salário de benefício anual**, se necessário. |
   | **Eventos de vida habilitados** | Habilita eventos de vida. |
   | **Ocultar formulários de benefício herdados** | Permite ocultar formulários de benefícios herdados. |

3. Selecione **Salvar**.

## <a name="configure-employee-self-service-parameters"></a>Configurar parâmetros de autoatendimento para funcionários

1. No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Parâmetros**.

2. Na guia **Autoatendimento de funcionário**, especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | **Verificação de benefício** | O texto de verificação a ser usado durante o check-out de benefícios de autoatendimento. |
   | **Seleção automática de representantes** | Especifica se os dependentes e os beneficiários devem ser selecionados automaticamente com base na sua qualificação para opções de plano. |

3. Selecione **Salvar**.
