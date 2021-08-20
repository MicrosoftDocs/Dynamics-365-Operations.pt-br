---
title: Habilitar propostas de orçamento (versão prévia)
description: Este tópico explica como habilitar o recurso de proposta de orçamento no Finance Insights.
author: ShivamPandey-msft
ms.date: 07/16/2021
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
ms.openlocfilehash: cc7b06ee40553a254a939babc30e6f5c99f85507c1a3db4e916f480560cf8835
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768930"
---
# <a name="enable-budget-proposals-preview"></a>Habilitar propostas de orçamento (versão prévia)

[!include [banner](../includes/banner.md)]

Este tópico explica como habilitar o recurso de proposta de orçamento no Finance Insights.

1. Use as informações da página de ambiente no Microsoft Dynamics Lifecycle Services (LCs) para se conectar à instância principal do Azure SQL para esse ambiente. Execute o comando Transact-SQL (T-SQL) a seguir para ativar as versões piloto no ambiente de área restrita. (Talvez seja necessário ativar o acesso ao seu endereço IP no LCS antes de se conectar remotamente ao servidor de objetos de aplicativo \[AOS\].)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > Ignore esta etapa se você estiver usando a versão 10.0.20 ou posterior, ou se você estiver usando uma implantação do Service Fabric. A equipe do Finance Insights já deve ter ativado a versão piloto para você. Se você não vir o recurso no espalho de trabalho **Gerenciamento de recurso**, ou se você tiver problemas ao tentar ativá-lo, entre em contato com <fiap@microsoft.com>.

2. Abra o espaço de trabalho **Gerenciamento de recursos** e siga estas etapas:

    1. Selecione **Verificar se há atualizações**.
    2. Procure por **Propostas de orçamento** e ative esse recurso.

3. Acesse **Orçamento \> Configuração \> Orçamento básico \> Proposta de orçamento (versão prévia)** e selecione **Habilitar recurso**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
