---
title: Instalar a solução Invoice Capture
description: Este artigo fornece informações sobre como instalar a solução Invoice Capture e integrá-la ao Microsoft Dynamics 365 Finance.
author: sunfzam
ms.date: 09/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: zezhangzhao
ms.search.validFrom: 2022-09-28
ms.dyn365.ops.version: ''
ms.openlocfilehash: d853e347c833345f34b65760fd7ee35cbb38c9a3
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691128"
---
# <a name="install-the-invoice-capture-solution"></a>Instalar a solução Invoice Capture

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!IMPORTANT]
> Se você tiver instalado a solução na versão prévia privada, deverá desinstalar a solução antiga antes de continuar.

## <a name="prerequisites"></a>Pré-requisitos

Antes de instalar a solução Invoice Capture, você precisa preencher os seguintes pré-requisitos:

1. Registre um aplicativo e adicione um segredo do cliente ao Microsoft Azure Active Directory (Azure AD) em sua assinatura do Azure. Para mais informações, consulte [Registrar um aplicativo Web com o AAD](../../dev-itpro/data-entities/services-home-page.md#register-a-web-application-with-aad).

    > [!NOTE]
    > Anote os valores de **ID do aplicativo (cliente)**, **Segredo do cliente** e **ID do Locatário** porque você precisará deles mais tarde.

2. Registre o aplicativo Azure em um ambiente do Dynamics 365 Finance Para obter mais informações, consulte [Registrar seu aplicativo externo](../../dev-itpro/data-entities/services-home-page.md#register-your-external-application).

## <a name="install-and-set-up-the-solution"></a>Instalar e configurar a solução

Para instalar a solução Invoice Capture, vá para AppSource e selecione o link da versão preliminar do [Dynamics 365 Invoice Capture](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics365-invoice-capture-preview?flightCodes=invoicecapture). Depois de concluída a instalação, você verá a solução instalada no ambiente selecionado no Power Apps.

Para concluir a configuração, siga essas etapas.

1. Baixe a [solução do assistente](https://github.com/InvoiceCapture/InstallationTools/releases/download/latest/msdyn_InvoiceCaptureIntallationTools.zip) para configurar os seguintes detalhes:

    - A comunicação entre o Microsoft Power Platform e o ambiente do Finance
    - A referência de conexão para o Dataverse e o Office 365 Outlook que serão usados pelo canal

2. No Power Apps, vá para o seu ambiente e selecione **Importar solução**.
3. Selecione **Procurar**, escolha o pacote da solução do assistente baixado e, em seguida, selecione **Avançar**.
4. Selecione **Avançar**.
5. Atribua uma conexão existente ou crie uma nova, selecionando **Nova conexão**.
6. Depois que o pacote for importado com êxito, abra o **Dynamics 365 Invoice capture – Ferramentas de Instalação**.
7. Execute o fluxo da nuvem para configurar a conexão entre a solução do Invoice Capture no Microsoft Power Platform and Finance.
8. Selecione **Executar** e especifique os seguintes parâmetros:

    - **Dynamics 365 Finance Url** – A URL do ambiente do Finance à qual você deseja se integrar.
    - **ID de Locatário** – A ID do locatário para o ambiente do Finance.
    - **ID do Cliente** – a ID do aplicativo do Azure registrada.
    - **Segredo do Cliente** – o segredo do cliente que foi gerado para o aplicativo do Azure.
