---
title: Habilitar o Power BI para Contabilidade de estoque global
description: Este tópico descreve como habilitar o Microsoft Power BI para a Contabilidade de estoque global.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d7979ed18b98ee6133774cd91bc866d6fca92d5f
ms.sourcegitcommit: eceae470f4ae58000ec33fea34db34b7a7a1af43
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2021
ms.locfileid: "6273113"
---
# <a name="enable-power-bi-for-global-inventory-accounting"></a>Habilitar o Power BI para Contabilidade de estoque global

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Você pode fixar blocos, painéis e relatórios de sua conta [PowerBI.com](https://powerbi.com/) para o espaço de trabalho do aplicativo Microsoft Dynamics 365.

## <a name="prerequisites"></a>Pré-requisitos

Os seguintes pré-requisitos devem ser atendidos para você habilitar o relatório do Power BI:

- Você deve ser um administrador de sistema no aplicativo Dynamics 365.
- Você deve ter uma conta do [PowerBI.com](https://powerbi.com/).
- Você deve ter pelo menos um painel e um relatório em sua conta do Power BI.
- Você deve ser um administrador da sua conta do Azure Active Directory (Azure AD).
- O domínio do Azure AD deve ser o mesmo domínio que você usou para sua conta do [PowerBI.com](https://powerbi.com/).

## <a name="setup"></a>Configurar

Siga estas etapas para configurar a integração do Power BI.

1. Entre no [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).
1. Vá para a **Biblioteca de ativos compartilhados**, selecione **Modelo de relatório do Power BI** como o tipo de ativo e baixe o pacote **Contabilidade de estoque global**. 
1. Entre no [PowerBI.com](https://app.powerbi.com/) e carregue o arquivo de relatório Power BI da **Contabilidade de estoque global** seguindo estas etapas:

    1. Selecione **Novo**.
    1. Selecione **Atualizar um arquivo**.
    1. Selecione o arquivo de relatório do Power BI da **Contabilidade de estoque global**.

1. Configure o relatório do Power BI da **Contabilidade de estoque global** seguindo estas etapas:

    1. Vá para **Meu espaço de trabalho**, encontre o conjunto de dados para Contabilidade de estoque global e, em seguida, no menu **Opções**, selecione **Configurações**.
    1. Em **Configurações da Contabilidade de estoque global**, expanda **Parâmetros** e atualize todos os parâmetros conforme necessário.

1. Registre o aplicativo conforme descrito em [Configurar integração do PowerBI.com](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md#registration-process).
1. Para integrar o arquivo de relatório do Power BI da **Contabilidade de estoque global** no Dynamics 365 Supply Chain Management, siga estas etapas:

    1. Vá para **Administração de sistema \> Configurar \> Configuração do PowerBI.com**.
    1. Selecione **Editar**.
    1. Selecione **Habilitar integração do PowerBI.Com**.
    1. No campo **ID do aplicativo**, insira o ID do aplicativo.
    1. No campo **Chave de aplicativo**, insira a chave do aplicativo.
    1. Selecione **Salvar**.

1. Atualize a página para que a caixa de diálogo de login no Power BI seja exibida.
1. Na guia **Opções**, selecione **Abrir catálogo de relatórios** e selecione o arquivo de relatório do Power BI da **Contabilidade de estoque global** que você carregou anteriormente.
1. Atualize a página. Você deverá ver que seu relatório foi adicionado.
1. Em link **Relatórios do Power BI**, selecione o link **Contabilidade de estoque global**.

Para obter mais informações, consulte [Configurar sua integração do PowerBI.com](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md).
