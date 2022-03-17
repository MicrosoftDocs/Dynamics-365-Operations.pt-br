---
title: Lista de recursos de impostos vazia nos parâmetros de Cálculo de imposto
description: Este tópico explica como solucionar um problema no qual a lista de recursos de imposto na página Parâmetros de cálculo de imposto está vazia.
author: wangchen
ms.date: 03/04/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 5b87499042c9c4bfe76e182b170adf4f1cfeac4b
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2022
ms.locfileid: "8388546"
---
# <a name="empty-tax-feature-list-in-tax-calculation-parameters"></a>Lista de recursos de impostos vazia nos parâmetros de Cálculo de imposto

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="symptom"></a>Sintoma

Você publicou um recurso no RCS (Regulatory Configuration Service) para que possa usá-lo no Microsoft Dynamics 365 Finance. Quando você abrir o Finance, vá para **Imposto** \> **Configuração** \> **Configuração de imposto** \> **Parâmetros de cálculo de imposto** e tente selecionar um valor no campo **Nome de configuração do recurso**; a lista de valores está vazia.

## <a name="reason"></a>Motivo

Esse problema geralmente ocorre porque o ambiente do Finance e o ambiente RCS não estão no mesmo locatário.

### <a name="rcs-tenant"></a>Locatário RCS

Siga estas etapas para encontrar a ID do seu locatário RCS.

1. Copie a URL completa do RCS. Por exemplo, a URL pode ser `https://rcs-rts-sf-ed22b5aeea8-int-westus2.configure.global.int.dynamics.com/namespaces/817ff7a0-0d77-4aba-9360-3c9749e2c5de/?cmp=dat&mi=RCSFeatureDomainsWorkspace`.
2. Abra uma janela do navegador InPrivate, cole a URL do RCS na barra de endereços e selecione **Enter**. Você é direcionado para a página de entrada, na qual é possível encontrar a ID de locatário RCS. Por exemplo, se a URL da página de entrada for `https://login.microsoftonline.com/d335a570-a05b-4bc5-8eb3-c42c65f9560d`, a ID do locatário será a informação que aparece após `https://login.microsoftonline.com/` ou **d335a570-a05b-4bc5-8eb3-c42c65f9560d**.

### <a name="finance-environment-tenant-id"></a>ID de locatário do ambiente do Finance

Para encontrar a ID de locatário do ambiente do Finance, siga as mesmas etapas que seguiu para encontrar o locatário RCS. No entanto, copie e cole a URL completa do ambiente do Finance em vez da URL completa do RCS.

## <a name="resolution"></a>Resolução

Se as duas IDs de locatários forem diferentes, você encontrará o problema descrito neste tópico. Se elas forem iguais, você encontrará um problema não relacionado. Nesse caso, é recomendável contactar o Suporte da Microsoft.

### <a name="solution-1"></a>Solução 1

Assine o ambiente RCS no mesmo locatário ao qual o seu ambiente do Finance está conectado. Crie e publique o recurso de imposto.

### <a name="solution-2"></a>Solução 2

Compartilhe o recurso de imposto com o locatário do Finance no RCS.

1. No RCS, acesse **Recursos de globalização** \> **Cálculo de Imposto**.
2. Selecione o recurso a ser compartilhado e, na guia **Organizações**, selecione **Compartilhar com**.
3. No campo **Nome do domínio da organização**, insira um nome. Por exemplo, insira **contoso.onmicrosoft.com**.
4. Selecione **Compartilhar**.

![Caixa de diálogo suspensa Compartilhar com organização externa.](media/ShareTaxFeature.png)
