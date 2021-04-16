---
title: Habilitar propostas de orçamento (versão prévia)
description: Este tópico explica como habilitar o recurso de proposta de orçamento no Finance Insights.
author: ShivamPandey-msft
ms.date: 07/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 7e90a1a2f2a8e7808f03ce9a6ee58c027bd48d8d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818695"
---
# <a name="enable-budget-proposals-preview"></a>Habilitar propostas de orçamento (versão prévia)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico explica como habilitar o recurso de proposta de orçamento no Finance Insights.

1. Use as informações da página de ambiente no Microsoft Dynamics Lifecycle Services (LCs) para se conectar à instância principal do Azure SQL para esse ambiente. Execute o comando Transact-SQL (T-SQL) a seguir para ativar as versões piloto no ambiente de área restrita. (Talvez seja necessário ativar o acesso ao seu endereço IP no LCS antes de se conectar remotamente ao servidor de objetos de aplicativo \[AOS\].)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > Se a sua implantação do Microsoft Dynamics 365 Finance for uma implantação do Service Fabric, você pode ignorar essa etapa. A equipe do Finance Insights já deve ter ativado a versão piloto para você. Se você não vir o recurso no espaço de trabalho **Gerenciamento de recursos** ou se tiver problemas ao tentar ativá-lo, envie um email para a [Equipe de versão prévia do aplicativo Finance Insights](mailto:fiap@microsoft.com).

2. Abra o espaço de trabalho **Gerenciamento de recursos** e siga estas etapas:

    1. Selecione **Verificar se há atualizações**.
    2. Procure por **Propostas de orçamento** e ative esse recurso.

3. Acesse **Orçamento \> Configuração \> Orçamento básico \> Proposta de orçamento (versão prévia)** e selecione **Habilitar recurso**.

#### <a name="privacy-notice"></a>Aviso de privacidade
As versões prévias (1) podem utilizar menos medidas de privacidade e segurança que o serviço do Dynamics 365 Finance and Operations, (2) não estão incluídas no contrato de nível de serviço (SLA) desse serviço, (3) não devem ser usadas para processar dados pessoais ou outros dados sujeitos a requisitos de conformidade legais ou regulatórios e (4) têm suporte limitado.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]