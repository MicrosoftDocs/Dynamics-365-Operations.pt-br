---
title: Falha ao acessar o serviço de imposto
description: Este artigo explica como solucionar problemas de falha ao acessar o serviço Cálculo de Imposto.
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
ms.openlocfilehash: 65d819b97be3d1238bc0ecfc201b4e24edac8616
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8861212"
---
# <a name="failed-to-access-tax-service"></a>Falha ao acessar o serviço de imposto

[!include [banner](../includes/banner.md)]


Este artigo explica como corrigir o erro "Falha ao acessar o serviço de imposto" do serviço Cálculo de Imposto.

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
