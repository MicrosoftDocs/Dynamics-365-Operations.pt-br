---
title: Introdução à administração de serviço do Faturamento eletrônico
description: Este tópico explica como começar a usar o Faturamento eletrônico.
author: gionoder
ms.date: 03/29/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: be9e823a0c70aebcfd5353f7b922f8f4b1aa3d73
ms.sourcegitcommit: cc49cf74bd5a34f97a02cdccd473a6479e175a5b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2022
ms.locfileid: "8493904"
---
# <a name="get-started-with-electronic-invoicing-service-administration"></a>Introdução à administração de serviço do Faturamento eletrônico

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a>Pré-requisitos

Antes de concluir os procedimentos neste tópico, é preciso ter os seguintes pré-requisitos em vigor:

- Você deve ter acesso à conta do Microsoft Dynamics Lifecycle Services (LCS).
- Você deve ter um projeto LCS que inclua a versão 10.0.17 ou posterior do Microsoft Dynamics 365 Finance ou Dynamics 365 Supply Chain Management. Além disso, esses aplicativos devem ser implantados em uma das seguintes regiões geográficas do Azure:

    - Estados Unidos
    - Europa
    - Reino Unido
    - Ásia

- Você deve ter acesso à conta do Dynamics 365 Regulatory Configuration Services (RCS).
- Você deve ativar o recurso Globalização para a conta RCS no Gerenciamento de recursos. Para obter mais informações, consulte [Regulatory Configuration Services (RCS) — Recursos de globalização](rcs-globalization-feature.md).
- Você deve criar um cofre de chaves e uma conta de armazenamento no Azure. Para obter mais informações, consulte [Criar uma conta de armazenamento do Azure e um cofre de chaves](e-invoicing-create-azure-storage-account-key-vault.md).

## <a name="install-the-add-in-for-microservices-in-lifecycle-services"></a>Instalar o suplemento para microsserviços no Lifecycle Services

1. Faça login na sua conta LCS e, no painel de projeto do LCS, selecione um projeto LCS.
2. No projeto, no painel **Ambientes**, selecione seu ambiente implantado. O ambiente selecionado deve estar em execução.
3. Na guia **Integração do Power Platform**, no grupo de campos **Complementos do ambiente**, selecione **Instalar novo complemento**.
4. Selecione **Fatura eletrônica**.
5. No campo **ID do aplicativo do AAD**, insira **091c98b0-a1c9-4b02-b62c-7753395ccabe**. Esse é um valor fixo.
6. No campo **ID de locatário AAD**, insira a ID do locatário da sua conta de assinatura do Azure. O locatário do Azure Active Directory (Azure AD) que você especifica deve ser o mesmo locatário usado para RCS.
7. Analise os termos e condições e depois marque a caixa de seleção.
8. Selecione **Instalar**. A instalação pode demorar vários minutos.


## <a name="set-up-the-parameters-for-rcs-integration-with-electronic-invoicing"></a>Configure os parâmetros da integração do RCS com o Faturamento eletrônico

1. Entre em sua conta do RCS.
2. No espaço de trabalho **Recursos de globalização**, na seção **Configurações relacionadas**, selecione **Parâmetros de relatório eletrônico**.
3. Na guia **Faturamento Eletrônico**, no campo **URI de ponto de extremidade de serviço**, insira o ponto de extremidade de serviço apropriado para sua geografia do Azure, conforme mostrado na tabela a seguir.

    | Geografia do data center Azure | URI do ponto de extremidade do serviço                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | Estados Unidos              | <p>`https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Europa                     | <p>`https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Reino Unido             | <p>`https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Ásia                       | <p>`https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Japão                      | <p>`https://gw.jp-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Suíça                | <p>`https://gw.ch-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Brasil                     | <p>`https://gw.br-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.br-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Emirados Árabes Unidos       | <p>`https://gw.ae-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Austrália                  | <p>`https://gw.au-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.au-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Canadá                     | <p>`https://gw.ca-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.ca-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | França                     | <p>`https://gw.fr-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Índia                      | <p>`https://gw.in-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |


4. Verifique se o campo **ID do Aplicativo** está definido como **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Esse valor é um valor fixo.
5. No campo **ID de Ambiente do LCS**, insira a ID do ambiente do LCS.
6. Selecione **Salvar** e feche a página.

## <a name="create-key-vault-references"></a>Criar referências do Key Vault

1. Entre em sua conta do RCS.
2. No espaço de trabalho **Recurso de globalização**, na seção **Ambiente**, selecione o bloco **Faturamento eletrônico**.
3. Na página **Configurações de ambiente**, no Painel de Ações, selecione **Ambientes de serviço** e **Parâmetros de Key Vault**.
4. Selecione **Novo** para criar uma referência de cofre de chaves.
5. No campo **Nome**, insira o nome da referência de cofre de chaves. No campo **Descrição**, insira uma descrição.
6. No campo **URI do Key Vault**, cole o segredo de cofre de chaves do Azure Key Vault. Para obter mais informações, consulte [Criar uma conta de armazenamento do Azure e um cofre de chaves](e-invoicing-create-azure-storage-account-key-vault.md).
7. Selecione **Salvar**.

## <a name="create-storage-account-secret"></a>Criar segredo da conta de armazenamento

1. Na página **Configurações de ambiente**, no Painel de Ações, selecione **Ambiente de serviço** > **Parâmetros de Key Vault**.
2. Selecione uma **referência do Key Vault** e, na seção **Certificados**, selecione **Adicionar**.
3. No campo **Nome**, insira o nome do segredo da conta de armazenamento. Para obter mais informações, consulte [Criar uma conta de armazenamento do Azure e um cofre de chaves](e-invoicing-create-azure-storage-account-key-vault.md).
4. No campo **Descrição**, insira uma descrição.
5. No campo **Tipo**, selecione **Segredo**.
6. Selecione **Salvar** e feche a página.

## <a name="create-a-digital-certificate-secret"></a>Criar um segredo de certificado digital

1. Na página **Configurações de ambiente**, no Painel de Ações, selecione **Ambiente de serviço** e **Parâmetros de Key Vault**.
2. Selecione uma **referência do Key Vault** e, na seção **Certificados**, selecione **Adicionar**.
3. No campo **Nome**, insira o nome do segredo do certificado digital. Para obter mais informações, consulte [Criar uma conta de armazenamento do Azure e um cofre de chaves](e-invoicing-create-azure-storage-account-key-vault.md).
4. No campo **Descrição**, insira uma descrição.
5. No campo **Tipo**, selecione **Certificado**.
6. Selecione **Salvar** e feche a página.

## <a name="create-a-service-environment"></a>Criar um ambiente de serviço

1. Entre em sua conta do RCS.
2. No espaço de trabalho **Recurso de globalização**, na seção **Ambiente**, selecione o bloco **Faturamento eletrônico**.
3. Na página **Configurações de ambiente**, no Painel de Ações, selecione **Ambiente de serviço**.
4. Selecione **Novo** para criar um novo ambiente de serviço.
5. No campo **Nome**, insira o nome do ambiente de faturamento eletrônico. No campo **Descrição**, insira uma descrição.
6. No campo **Segredo de token SAS de armazenamento**, selecione o nome do segredo da conta de armazenamento que deve ser usado para autenticar o acesso à conta de armazenamento.
7. Na seção **Usuários**, selecione **Adicionar** para adicionar um usuário que tem permissão para enviar faturas eletrônicas pelo ambiente e também para se conectar à conta de armazenamento.
8. No campo **ID do Usuário**, insira o alias do usuário. No campo **Email**, insira o endereço de email do usuário.
9. Selecione **Salvar**.
10. Se as faturas específicas de país/região exigirem uma cadeia de certificados para aplicar assinaturas digitais, no Painel de Ações, selecione **Parâmetros de Key Vault**, selecione **Cadeia de certificados** e siga estas etapas:

    1. Selecione **Novo** para criar uma cadeia de certificados.
    2. No campo **Nome**, insira o nome da cadeia de certificados. No campo **Descrição**, insira uma descrição.
    3. Na seção **Certificados**, selecione **Adicionar** para adicionar um certificado à cadeia.
    4. Use o botão **Para cima** ou **Para baixo** para alterar a posição do certificado na cadeia.
    5. Selecione **Salvar** e feche a página.
    6. Feche a página.

11. Na página **Ambiente de serviço**, no Painel de Ações, selecione **Publicar** para publicar o ambiente na nuvem. O valor do campo **Status** é alterado para **Publicado**.

## <a name="create-a-connected-application"></a>Crie um aplicativo conectado

1. Na página **Configuração de ambientes**, no Painel de Ações, selecione **Aplicativos conectados**.
2. Selecione **Novo** para criar um aplicativo conectado.
3. No campo **Nome**, insira o nome do aplicativo a ser conectado.
4. No campo **Aplicativo**, insira a URL do ambiente Finance e Supply Chain Management para conexão.
4. No campo **Locatário**, insira o locatário do ambiente Finance e Supply Chain Management.
5. Selecione **Salvar**.
6. No Painel de Ações, selecione **Verificar conexão** para testar a conexão com o ambiente. Depois feche a página.

## <a name="link-connected-applications-to-environments"></a>Vincular aplicativos conectados a ambientes

1. Na página **Configuração de ambientes**, selecione **Novo** para atribuir um aplicativo conectado a um ambiente.
2. No campo **Aplicativo conectado**, selecione um aplicativo conectado.
3. No campo **Ambiente de serviço**, selecione um ambiente de serviço.
4. Selecione **Salvar** e feche a página.

## <a name="set-up-electronic-invoicing-integration-in-finance-and-supply-chain-management"></a>Configurar a integração do Faturamento eletrônico no Finance e no Supply Chain Management

### <a name="turn-on-the-electronic-invoicing-integration-feature"></a>Ativar o recurso Integração do Faturamento eletrônico

1. Entre na instância do Finance ou do Supply Chain Management.
2. No espaço de trabalho **Gerenciamento de recursos**, procure o recurso **Integração do Faturamento eletrônico**. Se esse recurso não aparecer na página, selecione **Verificar se há atualizações**.
3. Selecione o recurso e **Habilitar agora**.

### <a name="set-up-the-service-endpoint-url"></a>Configurar a URL do ponto de extremidade de serviço

1. Acesse **Administração da organização \> Configuração \> Parâmetros de documentos eletrônicos**.
2. Na guia **Faturamento Eletrônico**, no campo **URL de ponto de extremidade**, insira o ponto de extremidade de serviço apropriado para sua geografia do Azure, conforme mostrado na tabela a seguir.

    | Geografia do data center Azure | URI do ponto de extremidade do serviço                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | Estados Unidos              | <p>`https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Europa                     | <p>`https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Reino Unido             | <p>`https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Ásia                       | <p>`https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Japão                      | <p>`https://gw.jp-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Suíça                | <p>`https://gw.ch-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Brasil                     | <p>`https://gw.br-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.br-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Emirados Árabes Unidos       | <p>`https://gw.ae-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Austrália                  | <p>`https://gw.au-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.au-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Canadá                     | <p>`https://gw.ca-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.ca-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | França                     | <p>`https://gw.fr-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Índia                      | <p>`https://gw.in-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |

3. No campo **Ambiente**, insira o nome do ambiente de serviço publicado no Faturamento eletrônico.
4. Selecione **Salvar** e feche a página.

### <a name="enable-flighting-keys-for-finance-or-supply-chain-management-version-10017"></a>Habilitar chaves da liberação de versões de pré-lançamento para o Supply Chain Management versão 10.0.17

1. Execute o seguinte comando SQL:

    INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BusinessDocumentSubmissionServiceEnabled', 1)
    
    INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('ElectronicInvoicingServiceIntegrationFeature', 1)

2. Executa um comando IISreset para todos os AOS.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
