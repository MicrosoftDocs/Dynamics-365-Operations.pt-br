---
title: Falha ao acessar o serviço de imposto
description: Este tópico explica como solucionar problemas de falha ao acessar o serviço de Cálculo de Imposto.
author: hangwan
ms.date: 03/04/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: hangwan
ms.search.validFrom: 02/16/2022
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: f4682b83405071b4ad7647958122ab2b4e082133
ms.sourcegitcommit: 2977e92a76211875421e608555311c363cfbdc25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2022
ms.locfileid: "8612306"
---
# <a name="failed-to-access-tax-service"></a>Falha ao acessar o serviço de imposto

[!include [banner](../includes/banner.md)]


Este tópico explica como corrigir o erro "falha ao acessar o serviço de imposto" do serviço Cálculo de Imposto.

## <a name="symptoms"></a>Sintomas

No Microsoft Dynamics 365 Finance, acesse **Imposto** \> **Configuração** \> **Configuração de imposto** \> **Parâmetros do serviço de imposto**. Na guia **Geral**, ative a opção **Habilitar cálculo de imposto**. Se você tentar selecionar um valor no campo **Nome de configuração do recurso**, ocorrerá um erro. A mensagem de erro informa "Falha ao acessar o serviço de imposto".

## <a name="cause"></a>Causa

Este erro ocorre porque o Finance não pode acessar o serviço Cálculo de Imposto.

## <a name="resolution"></a>Resolução 

1. Entre Microsoft Dynamics Lifecycle Services (LCS).
2. Na página **Ambiente**, na guia **Suplementos de ambiente**, localize o item **Cálculo de Imposto** e revise o status. O status deve ser **Instalando** ou **Instalado**. Se o suplemento de serviço Cálculo de Imposto não estiver instalado, você receberá o erro.

## <a name="mitigation"></a>Redução

1. Em LCS, na página **Finance**, na seção **Integração do Power Platform**, selecione **Instalar um novo suplemento**.
2. Role até a parte inferior da página e selecione o suplemento **Cálculo de Imposto** para instalá-lo.
3. Volte ao seu ambiente do Finance e tente acessar o serviço Cálculo de Imposto.

> [!NOTE]
> Antes de instalar o serviço Cálculo de Imposto, revise os [pré-requisitos do Serviço de Cálculo de Imposto](global-get-started-with-tax-calculation-service.md#prerequisites).
> 
> Se você não conseguir instalar o suplemento porque a seção **Integração do Power Platform** não está disponível, consulte [Visão geral do suplemento](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Se o erro persistir após você instalar o suplemento, contate o administrador do sistema.
