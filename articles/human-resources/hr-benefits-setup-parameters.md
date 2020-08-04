---
title: Definir parâmetros de gerenciamento de benefícios
description: Configure parâmetros para o gerenciamento de benefícios no Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 07/16/2020
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
ms.openlocfilehash: 85bbe5d3b422f2f29f1d1fe8ee269b407da691c2
ms.sourcegitcommit: 9dc5c7dd5877cc6e7cd0059d173bcd8052ba13bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/16/2020
ms.locfileid: "3599347"
---
# <a name="set-benefits-management-parameters"></a>Definir parâmetros de gerenciamento de benefícios

Antes de configurar planos de licença no Microsoft Dynamics 365 Human Resources, você precisa configurar os parâmetros de gerenciamento de benefícios. Esses parâmetros definem valores padrão, códigos de motivo e outras opções.

## <a name="configure-general-parameters"></a>Configurar parâmetros gerais

1. No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Parâmetros Compartilhados do Human Resources**.

2. Na guia **Geral**, especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | **País/região** | O campo **País/região** determina a ordem de exibição de CEPs/estados. O país selecionado é exibido primeiro na lista suspensa. |
   | **Código do motivo da inscrição** | Selecione um código de motivo padrão a ser usado quando os planos do funcionário forem criados durante o processamento do inscrição aberta. |
   | **Código do motivo do cancelamento** | O código de motivo a ser usado quando um plano de benefícios do funcionário é cancelado. Ele é exibido em uma caixa de diálogo durante o processo de cancelamento. Os usuários podem alterar o **Código de motivo do cancelamento**, se necessário. |
   | **Código de motivo de reabertura** | O código de motivo a ser usado quando um plano de benefícios do funcionário é reaberto. Ele é exibido em uma caixa de diálogo durante o processo de cancelamento. Os usuários podem alterar o **Código de motivo de reabertura**, se necessário. | 
   | **Código do motivo do evento de vida** | O código de motivo a ser usado quando ocorre um evento de vida. |
   | **Código de motivo da alteração da taxa** | O código de motivo a ser usado ao cancelar e reabrir um plano de benefícios do funcionário durante o processo de atualização de alteração de taxa. Ele indica quais registros foram alterados pelo processo de atualização da alteração de taxa. |
   | **Salário anual do benefício** | Permite definir um valor de **Salário de benefícios anual** para um funcionário. O Human Resources usará o valor do **Salário de benefícios anual** ao determinar valores de cobertura em vez do valor anual da remuneração fixa. |
   | **Nova contratação qualificada** | Especifica se novas contratações estão qualificadas. |
   | **Período de inscrição de novas contratações** | O período de tempo em que a nova inscrição de contratação é permitida.</br></br>**Observação**: esta configuração substitui qualquer novo período de inscrição de contratação definido na regra de qualificação para o plano. |
   | **Frequência de pagamento padrão** | A frequência de pagamento padrão a ser usada quando novos trabalhadores são adicionados. |
   | **Eventos de vida habilitados** | Habilita eventos de vida. |
   | **Ocultar formulários de benefício herdados** | Permite ocultar formulários de benefícios herdados. |

3. Selecione **Salvar**.

## <a name="configure-employee-self-service-parameters"></a>Configurar parâmetros de autoatendimento para funcionários

1. No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Parâmetros do Human Resources**.

2. Na guia **Autoatendimento de funcionário**, especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | **Verificação de benefício** | O texto de verificação a ser usado durante o check-out de benefícios de autoatendimento. |
   | **Seleção automática de representantes** | Especifica se os dependentes e os beneficiários devem ser selecionados automaticamente com base na sua qualificação para opções de plano. |

3. Selecione **Salvar**.
