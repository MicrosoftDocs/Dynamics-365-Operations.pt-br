---
title: Introdução ao complemento de faturamento eletrônico para a França
description: Este artigo fornece informações que ajudarão você a começar a usar o complemento de faturamento eletrônico para a França.
author: dkalyuzh
ms.date: 07/07/2022
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2022-00-02
ms.dyn365.ops.version: AX 10.0.29
ms.openlocfilehash: 365316b204b6d76fa6ee6b2402fefee50c8ff3ef
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220639"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-france"></a>Introdução ao complemento de faturamento eletrônico para a França

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Este artigo fornece informações que ajudarão você a começar a usar o faturamento eletrônico para a França. Ele orienta você pelas etapas de configuração que dependem do país/região para o Regulatory Configuration Service (RCS). Essas etapas complementam as etapas descritas em [Introdução ao complemento de faturamento eletrônico](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-french-chorus-pro-submission-fr-electronic-invoicing-feature"></a>Configuração específica de país para o recurso de faturamento eletrônico para submissão no Chorus Pro da França (FR)

Algumas etapas são necessárias para configurar o recurso de faturamento eletrônico para submissão no **Chorus pro da França (FR)**. Alguns parâmetros de configuração são publicados com valores padrão. Esses valores devem ser revisados e atualizados para que eles reflitam melhor suas operações comerciais.

### <a name="prerequisites"></a>Pré-requisitos

Antes de começar os procedimentos neste artigo, conclua os seguintes pré-requisitos:

- Familiarize-se com o faturamento eletrônico. Para obter mais informações, consulte [a visão geral do faturamento eletrônico](e-invoicing-service-overview.md).
- Inscreva-se no RCS e configure o Faturamento Eletrônico. Para obter mais informações, consulte os seguintes artigos:

    - [Inscrever-se e instalar o serviço de Faturamento Eletrônico](e-invoicing-sign-up-install.md)
    - [Configurar recursos do Azure para Faturamento Eletrônico](e-invoicing-set-up-azure-resources.md)
    - [Instalar o suplemento para microsserviços no Lifecycle Services](e-invoicing-install-add-in-microservices-lcs.md)
    - [Ative e configure a integração com o faturamento eletrônico](e-invoicing-activate-setup-integration.md) - Use a informação deste artigo para ativar a integração entre o Microsoft Dynamics 365 Finance ou o aplicativo Dynamics 365 Supply Chain Management e o serviço de faturamento eletrônico.
    - [Códigos NAF e números Siret](emea-fra-naf-codes-siret-numbers.md) e [configurar códigos NAF e números Siret](tasks/fr-00003-naf-codes-siret-numbers.md) – use as informações desses artigos para configurar códigos NAF e números de Siret em suas entidades legais. 

- Sua organização deve estar registrada para operar com o Chorus pro. A Microsoft oferece integração com o Chorus Pro no modo OAuth2 por meio de uma interface de programação de aplicativo (API). Para obter informações detalhadas sobre o registro do Chorus Pro e a ativação de aplicativos, consulte a [documentação oficial](https://communaute.chorus-pro.gouv.fr/documentation/help-for-api-developers-in-oauth2-mode/).

    Siga estas etapas para se registrar no Chorus Pro.

    1. Acesse o [Portal PISTE](https://piste.gouv.fr/en/component/apiportal/registration) para iniciar o registro. 
    2. Registre um aplicativo e ative as credenciais de Open Authorization (OAuth).
    3. Copie e salve a ID de cliente das credenciais OAuth e a chave secreta. Essas informações serão usadas nas etapas posteriores.
    4. Acesse o portal [Chorus Pro](https://portail.chorus-pro.gouv.fr/aife_csm/?id=aife_enrollment) para registro. 
    5. Crie uma conta técnica para acesso à API. Para obter mais informações, consulte a opção [Criação de uma conta técnica para acesso à API na produção](https://communaute.chorus-pro.gouv.fr/documentation/creation-of-a-technical-account-for-an-api-access-in-production/).
    6. Copie a ID de usuário da conta técnica e a senha. Essas informações serão usadas nas etapas posteriores.

## <a name="country-specific-configuration-of-the-application-setup-for-the-french-chorus-pro-submission-fr-electronic-invoicing-feature"></a>Configuração específica do país da configuração do aplicativo para o recurso de fatura eletrônica com submissão pelo Chorus Pro da França (FR)

Alguns dos parâmetros do recurso de **faturamento eletrônico com submissão pelo Chorus Pro da França (FR)** são publicados com valores padrão. Antes de implantar o recurso de faturamento eletrônico no ambiente de serviço, revise e atualize os valores padrão conforme necessário para que reflitam melhor suas operações comerciais.

1. No Azure Key Vault crie segredos e as referências correspondentes a eles. Para obter mais informações, consulte [os certificados e segredos do cliente](e-invoicing-customer-certificates-secrets.md).
2. Importe a versão mais recente do recurso de globalização **para submissão no Chorus Pro da França (FR)**, conforme descrito em [Importar recursos do repositório Global](e-invoicing-import-feature-global-repository.md).
3. Crie uma cópia do recurso de globalização importado e selecione seu provedor de configuração. Para obter mais informações, consulte a opção [Criar um recurso de globalização](e-invoicing-create-new-globalization-feature.md).
4. Na guia **Versões**, verifique se a versão **Rascunho** está selecionada.
5. Na guia **Configurações**, na grade, selecione a configuração do recurso **Derivado da fatura de venda UBL**.
6. Selecione **Editar** e, em seguida, na guia **Pipeline de processamento**, na seção **Pipeline de processamento**, selecione **(Versão preliminar) Integrar ao francês Chorus Pro** com o nome da ação **Submeter por meio do Chorus Pro francês**.
7. Na seção **Parâmetros**, no campo para o nome do segredo da **ID do cliente**, selecione o nome do segredo criado para a ID do cliente no cofre de chaves.
8. No campo **Nome do segredo do cliente**, selecione o nome do segredo criado para o segredo do cliente no cofre de chaves.
9. No campo **Nome do segredo do login técnico**, selecione o nome do segredo criado para credenciais da conta técnica no cofre de chaves.
10. No campo **Nome do segredo da senha técnica**, selecione o nome do segredo criado para a senha da conta técnica no cofre de chaves.
11. Na guia **Pipeline de processamento**, na seção **Pipeline de processamento**, selecione **Integrar ao francês Chorus Pro** com o nome da ação **Status de solicitação do Chorus Pro francês**.
12. Na seção **Parâmetros**, no campo para o nome do segredo da **ID do cliente**, selecione o nome do segredo criado para a ID do cliente no cofre de chaves.
13. No campo **Nome do segredo do cliente**, selecione o nome do segredo criado para o segredo do cliente no cofre de chaves.
14. No campo **Nome do segredo do login técnico**, selecione o nome do segredo criado para credenciais da conta técnica no cofre de chaves.
15. No campo **Nome do segredo da senha técnica**, selecione o nome do segredo criado para a senha da conta técnica no cofre de chaves.
16. Selecione **Salvar** e feche a página.
17. Repita as etapas 6 a 16 para a configuração do recurso derivado **da fatura do projeto UBL**, **configuração do recurso derivado da nota de crédito de vendas UBL** e configuração do recurso derivado da **nota de crédito do projeto UBL**.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral de faturamento eletrônico](e-invoicing-service-overview.md)
- [Introdução à administração de serviço do complemento do Faturamento eletrônico](e-invoicing-get-started-service-administration.md)
- [Introdução ao complemento do faturamento eletrônico](e-invoicing-get-started.md)
