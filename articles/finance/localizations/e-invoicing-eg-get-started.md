---
title: Faturamento eletrônico para o Egito
description: Este artigo fornece informações que ajudarão você a começar a usar o Faturamento eletrônico para o Egito no Microsoft Dynamics 365 Finance e no Dynamics 365 Supply Chain Management.
author: gionoder
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.custom: 97423,  ""intro-internal
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: e603bcad4d6dc46bd2594cfdcdf8871eb1f49019
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269491"
---
# <a name="electronic-invoicing-for-egypt"></a>Faturamento eletrônico para o Egito

[!include [banner](../includes/banner.md)]

Este artigo fornece informações que ajudarão você a começar a usar o Faturamento eletrônico para o Egito. Ele orienta você pelas etapas de configuração que dependem do país/região para o Regulatory Configuration Service (RCS). Essas etapas complementam as etapas descritas em [Configuração do Faturamento eletrônico](e-invoicing-set-up-overview.md).

## <a name="prerequisites"></a>Pré-requisitos

Antes de começar os procedimentos neste artigo, conclua os seguintes pré-requisitos:

- Familiarize-se com o faturamento eletrônico, conforme descrito na [Visão geral do faturamento eletrônico](e-invoicing-service-overview.md).
- Inscreva-se no RCS e configure o Faturamento Eletrônico. Para obter mais informações, consulte os seguintes tópicos:

    - [Inscrever-se e instalar o serviço de Faturamento Eletrônico](e-invoicing-sign-up-install.md)
    - [Configurar recursos do Azure para Faturamento Eletrônico](e-invoicing-set-up-azure-resources.md)
    - [Instalar o suplemento para microsserviços no Lifecycle Services](e-invoicing-install-add-in-microservices-lcs.md)
    
- Ative a integração entre o aplicativo Microsoft Dynamics 365 Finance ou Dynamics 365 Supply Chain Management e o serviço de faturamento eletrônico, conforme descrito em [Ativar e configurar a integração com o faturamento eletrônico](e-invoicing-activate-setup-integration.md).
- Crie um segredo de certificado digital no Azure Key Vault e configure-o conforme descrito em [Certificados e segredos de cliente](e-invoicing-customer-certificates-secrets.md). Para fins de teste, a autoridade de impostos egípcia fornece certificados digitais de teste específicos que devem ser usados somente durante fases de validação de solução e teste. Para obter mais informações, vá para o site da autoridade fiscal egípcia usando o link fornecido em [SDK de faturamento eletrônico egípcio](https://sdk.invoicing.eta.gov.eg/faq/).

## <a name="country-specific-configuration-for-the-egyptian-electronic-invoice-eg-feature"></a>Configuração específica de país para o recurso de Faturamento eletrônico do Egito (EG)

Alguns dos parâmetros do recurso de **Fatura eletrônica do Egito (EG)** são publicados com valores padrão. Antes de implantar o recurso de faturamento eletrônico no ambiente de serviço, revise os valores padrão e atualize-os conforme necessário para que reflitam melhor sua operação de negócios.

1. Importe a versão mais recente do recurso globalização **Fatura eletrônica egípcia (EG)**, conforme descrito em [Importar Recursos de importação do repositório Global](e-invoicing-import-feature-global-repository.md).
2. Crie uma cópia do recurso de globalização importada e selecione seu provedor de configuração para ele, conforme descrito em [Criar um recurso de globalização](e-invoicing-create-new-globalization-feature.md).
3. Na guia **Versões**, verifique se a versão **Rascunho** está selecionada.
4. Na guia **Configurações**, na grade, selecione a configuração do recurso **Derivado da fatura de venda**.
5. Selecione **Editar**.
6. Na guia **Pipeline de processamento**, na seção **Pipeline de processamento**, selecione **Assinar documento json para autoridade fiscal egípcia**.
7. Na seção **Parâmetros**, selecione **Nome do certificado** e, em seguida, selecione o nome do certificado digital criado.
8. Na seção **Pipeline de processamento**, selecione **Integrar com o serviço ETA egípcio**. Repita essa etapa para as duas ocorrências dessa ação.
9. Na seção **Parâmetros**, selecione **URL do serviço Web** e **URL do serviço de login**. Em seguida, revise os parâmetros de URL. Para obter a URL de Testes e Produção, consulte o site da autoridade fiscal egípcia usando o link fornecido no [SDK de faturamento eletrônico egípcio](https://sdk.invoicing.eta.gov.eg/faq/).
10. Selecione **Salvar** e feche a página.
11. Repita as etapas 4 a 10 para a configuração do recurso **Derivado da fatura do projeto**.

## <a name="country-specific-configuration-for-the-egyptian-electronic-invoice-eg-application-setup"></a>Configuração específica de país para a configuração do aplicativo de Faturamento eletrônico do Egito (EG)

Há parâmetros que devem ser configurados no seu ambiente do Finance ou do Supply Chain Management. Você pode concluir essa configuração em um dos seguintes locais:

- Diretamente no seu ambiente do Finance ou do Supply Chain Management. Para obter mais informações, consulte [Configurar parâmetros do Faturamento eletrônico](e-invoicing-set-up-parameters.md).
- No RCS. No escopo da configuração do recurso de faturamento eletrônico, você pode definir todos os parâmetros e implantá-los diretamente no seu ambiente do Finance or Supply Chain Management ao ao implantar o recurso de faturamento eletrônico.

Para ambas as opções, os parâmetros são os mesmos. Se você estiver configurando seu primeiro recurso no serviço de faturamento eletrônico, recomendamos que siga estas etapas para configurar os parâmetros no RCS e, em seguida, implante-os no aplicativo conectado.

> [!NOTE]
> Algumas versões do recurso de faturamento eletrônico podem conter um conjunto predefinido de parâmetros específicos do aplicativo para o Finance ou Supply Chain Management. Nesse caso, você deve verificar se os dados estão corretos. Caso contrário, defina manualmente os parâmetros.

1. Localize a cópia do recurso de globalização **Fatura eletrônica egípcia (EG)** que você criou.
2. Na guia **Versões**, verifique se a versão **Rascunho** está selecionada.
3. Na guia **Configurações**, selecione **Configuração do aplicativo**.
4. No campo **Aplicativos conectados**, selecione o aplicativo onde deseja implantar os parâmetros.
5. Na página **Tipos de documentos eletrônicos**, selecione **Adicionar** para criar um registro.
6. No campo **Nome da tabela**, adicione **CustInvoiceJour**.
7. No campo **Contexto**, adicione uma referência ao nome de mapeamento **Contexto da fatura do cliente**. A configuração é **Modelo de contexto de fatura de cliente**.
8. No campo **Contexto**, adicione uma referência ao nome de mapeamento **Contexto da fatura do cliente**. A configuração é **Mapeamento de modelo de fatura**.
9. Selecione **Salvar**.
10. Na página **Tipos de resposta**, selecione **Adicionar**.
11. No campo **Tipo de resposta** , insira **Resposta**.
12. No campo **Descrição**, insira **Processar resposta**.
13. No campo **Status de envio**, selecione **Pendente**.
14. No campo **Mapeamento de modelos**, selecione **Importação de mensagem de resposta**. A configuração é **Importação de mensagens de resposta do Egito (EG)**.
15. Selecione **Salvar**.
16. Selecione **Adicionar**.
17. No campo **Tipo de resposta**, insira **ResponseData**.
18. No campo **Descrição**, insira **Processar dados de resposta**.
19. No campo **Status de envio**, selecione **Pendente**.
20. No campo **Nome da entidade de dados**, selecione **SalesInvoiceHeaderV2Entity**.
21. No campo **Mapeamento de modelos**, selecione **Importação de dados de resposta**. A configuração é **Importação de dados de resposta do Egito (EG)**.
22. Selecione **Salvar** e feche a página.
23. Feche a página.

Para implantar um recurso no ambiente de serviço e uma configuração de aplicativo para o aplicativo Finance ou Supply Chain Management, consulte [Concluir, publicar e implantar um recurso de globalização](e-invoicing-complete-publish-deploy-globalization-feature.md)

## <a name="privacy-notice"></a>Aviso de privacidade

Habilitar o recurso **Fatura eletrônica italiana do Egito (EG)** pode exigir o envio de dados limitados. Esses dados incluem a ID de registro de imposto da organização. Esses dados serão transmitidos a agências de terceiros que foram autorizadas pela autoridade fiscal para enviar faturas eletrônicas a essa autoridade fiscal no formato predefinido exigido para integração com o serviço Web do governo. Um administrador pode habilitar e desabilitar o recurso acessando **Administração da organização** \> **Configuração** \> **Parâmetros de documento eletrônico**. Na guia **Recursos**, selecione a linha que contém o recurso **Fatura eletrônica egípcia (EG)** e, em seguida, faça a seleção apropriada. Os dados importados dos sistemas externos neste serviço online do Dynamics 365 estão sujeitos à nossa [política de privacidade](https://go.microsoft.com/fwlink/?LinkId=512132). Para obter mais informações, consulte a seção "Aviso de privacidade" da documentação de recursos específicos do país.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral do Faturamento eletrônico](e-invoicing-service-overview.md)
- [Introdução à administração de serviço do Faturamento eletrônico](e-invoicing-get-started-service-administration.md)
- [Introdução ao Faturamento eletrônico](e-invoicing-get-started.md)
- [Faturas eletrônicas do cliente no Egito](emea-egy-e-invoices.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
