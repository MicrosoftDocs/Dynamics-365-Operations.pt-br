---
title: Instalar o suplemento para microsserviços no Lifecycle Services
description: Este artigo explica como instalar o suplemento de Faturamento eletrônico no Microsoft Dynamics Lifecycle Services (LCS).
author: gionoder
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 938b00192acc0ff5534239f2f280792471181fad
ms.sourcegitcommit: 1ecfc1d8afb2201ab895ae6f93304ba2b120f14b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2022
ms.locfileid: "9710799"
---
# <a name="install-the-add-in-for-microservices-in-lifecycle-services"></a>Instalar o suplemento para microsserviços no Lifecycle Services

[!include [banner](../includes/banner.md)]

A autenticação no serviço de faturamento eletrônico requer que você registre seu ambiente do Microsoft Microsoft Dynamics 365 Finance ou Dynamics 365 Supply Chain Management na plataforma de serviços instalando o suplemento para o seu ambiente nos serviços de Microsoft Dynamics Lifecycle Services (LCS).

Para registrar um ambiente, siga estas etapas.

1. Entre em sua conta do LCS.
2. No painel de projetos LCS, selecione um projeto LCS.
2. No projeto, no painel **Ambientes**, selecione seu ambiente implantado. O ambiente selecionado deve estar em execução.
3. Na guia **Integração do Power Platform**, na seção **Complementos do ambiente**, selecione **Instalar novo complemento**.
4. Selecione **Fatura eletrônica**.
5. No campo **ID do aplicativo do AAD**, insira o valor fixo **091c98b0-a1c9-4b02-b62c-7753395ccabe**. Esse valor não muda nunca. Certifique-se de inserir somente um identificador global exclusivo (GUID). Não inclua outros símbolos, como espaços, vírgulas, pontos ou aspas.
6. No campo **ID de locatário AAD**, insira a ID do locatário da sua conta de assinatura do Azure. O locatário do Azure Active Directory (Azure AD) que você especifica deve ser o mesmo locatário usado para o Regulatory Configuration Service (RCS).
7. Analise os termos e condições e depois marque a caixa de seleção.
8. Selecione **Instalar**. Após alguns minutos, o status deve mudar de **Instalando** para **Instalado**. Pode ser necessário atualizar a página para ver esta alteração.

O faturamento eletrônico agora está pronto para ser usado.

> [!NOTE]
> Normalmente, as empresas têm vários ambientes do Finance ou Supply Chain Management. Esses ambientes incluem ambientes de produção, ambientes de teste de aceitação de usuários (UAT) e ambientes de desenvolvimento (Sandbox). Você deve concluir o procedimento anterior para todos os ambientes que deseja conectar ao Faturamento eletrônico.
