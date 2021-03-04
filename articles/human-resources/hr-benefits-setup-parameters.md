---
title: Definir parâmetros de gerenciamento de benefícios e autoatendimento para funcionários para todas as empresas
description: Configure parâmetros de gerenciamento de benefícios e autoatendimento para funcionários no Microsoft Dynamics 365 Human Resources.
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
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b50c4f71789c34f08ce810312f3c3198303b031e
ms.sourcegitcommit: fd097f6f76f0d8428038fa3655b3188bf093b517
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "4692688"
---
# <a name="set-benefits-management-and-employee-self-service-parameters-for-all-companies"></a>Definir parâmetros de gerenciamento de benefícios e autoatendimento para funcionários para todas as empresas

Antes de configurar planos de benefícios no Microsoft Dynamics 365 Human Resources, você precisa configurar os parâmetros de gerenciamento de benefícios. Esses parâmetros definem valores padrão, códigos de motivo e outras opções. 

## <a name="configure-general-parameters"></a>Configurar parâmetros gerais

1. No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Parâmetros Compartilhados do Human Resources**.

2. Na guia **Gerenciamento de benefícios**, especifique valores para os seguintes campos:

   | Campo | descrição |
   | --- | --- |
   | **País/região** | O campo **País/região** determina a ordem de exibição de CEPs/estados. O país/região selecionado é exibido primeiro na lista suspensa. |
   | **Código do motivo da inscrição** | Selecione um código de motivo padrão a ser usado quando os planos do funcionário forem criados durante o processamento do inscrição aberta. |
   | **Código do motivo do cancelamento** | O código de motivo a ser usado quando um plano de benefícios do funcionário é cancelado. Ele é exibido em uma caixa de diálogo durante o processo de cancelamento. Os usuários podem alterar o **Código de motivo do cancelamento**, se necessário. |
   | **Código de motivo de reabertura** | O código de motivo a ser usado quando um plano de benefícios do funcionário é reaberto. Ele é exibido em uma caixa de diálogo durante o processo de cancelamento. Os usuários podem alterar o **Código de motivo de reabertura**, se necessário. | 
   | **Código do motivo do evento de vida** | O código de motivo a ser usado quando ocorre um evento de vida. |
   | **Código de motivo da alteração da taxa** | O código de motivo a ser usado ao cancelar e reabrir um plano de benefícios do funcionário durante o processo de atualização de alteração de taxa. Ele indica quais registros foram alterados pelo processo de atualização da alteração de taxa. |
   | **Salário anual do benefício** | Permite definir um valor de **Salário de benefícios anual** para um funcionário. O Human Resources usará o valor do **Salário de benefícios anual** para determinar valores de cobertura em vez do valor anual da remuneração fixa. |
   | **Nova contratação qualificada** | Especifica se novas contratações estão qualificadas. |
   | **Período de inscrição de novas contratações** | O período de tempo em que a nova inscrição de contratação é permitida.</br></br>**Observação**: esta configuração substitui qualquer novo período de inscrição de contratação definido na regra de qualificação para o plano. |
   | **Frequência de pagamento padrão** | A frequência de pagamento padrão a ser usada quando novos trabalhadores são adicionados. |
   | **Eventos de vida habilitados** | Habilita eventos de vida. |
   | **Ocultar formulários de benefício herdados** | Permite ocultar formulários de benefícios herdados. |
   | **Verificação de benefício** | O texto de verificação a ser usado durante o check-out de benefícios de autoatendimento. |
   | **Seleção automática de representantes** | Especifica se os dependentes e os beneficiários devem ser selecionados automaticamente, com base na qualificação para opções de plano. |

3. Selecione **Salvar**.

## <a name="configure-employee-self-service-parameters"></a>Configurar parâmetros de autoatendimento para funcionários

1. No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Parâmetros do Human Resources**.

2. Na guia **Gerenciamento de benefícios**, especifique valores para os seguintes campos:

   | Campo | descrição |
   | --- | --- |
   | **Verificação de benefício** | O texto de verificação a ser usado durante o check-out de benefícios de autoatendimento. |
   | **Seleção automática de representantes** | Especifica se os dependentes e os beneficiários devem ser selecionados automaticamente com base na sua qualificação para opções de plano. |

3. Selecione **Salvar**.




[!INCLUDE[footer-include](../includes/footer-banner.md)]