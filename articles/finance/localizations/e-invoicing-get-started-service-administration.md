---
title: Introdução à administração de serviço do complemento do faturamento eletrônico
description: Este tópico explica como começar a usar o complemento de faturamento eletrônico.
author: gionoder
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 111ec65aa826795125d4a9ce835f72e1a0f41b7b
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104343"
---
# <a name="get-started-with-electronic-invoicing-add-on-service-administration"></a>Introdução à administração de serviço do complemento do faturamento eletrônico

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

## <a name="prerequisites"></a>Pré-requisitos

Antes de concluir os procedimentos neste tópico, é preciso ter os seguintes pré-requisitos em vigor:

- Você deve ter acesso à conta do Microsoft Dynamics Lifecycle Services (LCS).
- Você deve ter um projeto LCS que inclua a versão 10.0.13 ou posterior do Microsoft Dynamics 365 Finance e o Dynamics 365 Supply Chain Management. Além disso, esses aplicativos devem ser implantados em uma das seguintes regiões geográficas do Azure:

    - Leste dos EUA
    - Oeste dos EUA
    - Norte da UE
    - Oeste da UE

- Você deve ter acesso à conta do Dynamics 365 Regulatory Configuration Services (RCS).
- Você deve ativar o recurso Globalização para a conta RCS no Gerenciamento de recursos. Para obter mais informações, consulte [Regulatory Configuration Services (RCS) — Recursos de globalização](rcs-globalization-feature.md).
- Você deve criar um cofre de chaves e uma conta de armazenamento no Azure. Para obter mais informações, consulte [Criar uma conta de armazenamento do Azure e um cofre de chaves](e-invoicing-create-azure-storage-account-key-vault.md).

## <a name="install-the-add-on-for-microservices-in-lifecycle-services"></a>Instalar o complemento para microsserviços no Lifecycle Services

1. Entre em sua conta do LCS.
2. Selecione o bloco **Gerenciamento de versão prévia do recurso**.
3. Na seção **Recursos da versão preliminar pública**, selecione **Serviço de faturamento eletrônico**.
4. Verifique se a opção **Versão prévia do recurso habilitada** está definida como **Sim**.

## <a name="set-up-the-parameters-for-rcs-integration-with-the-electronic-invoicing-add-on"></a>Configure os parâmetros da integração do RCS com o complemento de faturamento eletrônico

1. Entre em sua conta do RCS.
2. No espaço de trabalho **Relatório eletrônico**, na seção **Links relacionados**, selecione **Parâmetros de relatório eletrônico**.
3. Na guia **Serviço de faturamento eletrônico**, no campo **URI de ponto de extremidade de serviço**, insira o ponto de extremidade de serviço apropriado para sua geografia do Azure, conforme mostrado na tabela a seguir.

    | Geografia do data center Azure | URI do ponto de extremidade do serviço                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | Leste dos EUA                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | Oeste dos EUA                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | Norte da UE                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | Oeste da UE                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

4. Verifique se o campo **ID do Aplicativo** está definido como **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Esse valor é um valor fixo.
5. No campo **ID de Ambiente do LCS**, insira a ID da conta de assinatura do LCS.
6. Selecione **Salvar** e feche a página.

## <a name="create-key-vault-secret"></a>Criar segredo do Key Vault

1. Entre em sua conta do RCS.
2. No espaço de trabalho **Recurso de globalização**, na seção **Ambiente**, selecione o bloco **Faturamento eletrônico**.
3. Na página **Configurações de ambiente**, no Painel de Ações, selecione **Ambiente de serviço** e **Parâmetros de Key Vault**.
4. Selecione **Novo** para criar um segredo de cofre de chaves.
5. No campo **Nome**, insira o nome do segredo de cofre de chaves. No campo **Descrição**, insira uma descrição.
6. No campo **URI do Key Vault**, cole o segredo do Azure Key Vault.
7. Selecione **Salvar**.

## <a name="create-storage-account-secret"></a>Criar segredo da conta de armazenamento

1. Na página **Parâmetros do cofre de chaves**, na seção **Certificados**, selecione **Adicionar**.
2. No campo **Nome**, insira o nome do segredo da conta de armazenamento. No campo **Descrição**, insira uma descrição.
3. No campo **Tipo**, selecione **Certificado**.
4. Selecione **Salvar** e feche a página.

## <a name="create-an-electronic-invoicing-add-on-environment"></a>Criar um ambiente de Complemento de faturamento eletrônico

1. Entre em sua conta do RCS.
2. No espaço de trabalho **Recurso de globalização**, na seção **Ambiente**, selecione o bloco **Faturamento eletrônico**.

## <a name="create-a-service-environment"></a>Criar um ambiente de serviço

1. Na página **Configurações de ambiente**, no Painel de Ações, selecione **Ambiente de serviço**.
2. Selecione **Novo** para criar um novo ambiente de serviço.
3. No campo **Nome**, insira o nome do ambiente de faturamento eletrônico. No campo **Descrição**, insira uma descrição.
4. No campo **Segredo de token SAS de armazenamento**, selecione o nome do certificado que deve ser usado para autenticar o acesso à conta de armazenamento.
5. Na seção **Usuários**, selecione **Adicionar** para adicionar um usuário que tem permissão para enviar faturas eletrônicas pelo ambiente e também para se conectar à conta de armazenamento.
6. No campo **ID do Usuário**, insira o alias do usuário. No campo **Email**, insira o endereço de email do usuário.
7. Selecione **Salvar**.
8. Se as faturas específicas de país/região exigirem uma cadeia de certificados para aplicar assinaturas digitais, no Painel de Ações, selecione **Parâmetros de Key Vault**, selecione **Cadeia de certificados** e siga estas etapas:

    1. Selecione **Novo** para criar uma cadeia de certificados.
    2. No campo **Nome**, insira o nome da cadeia de certificados. No campo **Descrição**, insira uma descrição.
    3. Na seção **Certificados**, selecione **Adicionar** para adicionar um certificado à cadeia.
    4. Use o botão **Para cima** ou **Para baixo** para alterar a posição do certificado na cadeia.
    5. Selecione **Salvar** e feche a página.
    6. Feche a página.
9. Na página **Ambiente de serviço**, no Painel de Ações, selecione **Publicar** para publicar o ambiente na nuvem. O valor do campo **Status** é alterado para **Publicado**.

## <a name="create-a-connected-application"></a>Crie um aplicativo conectado

1. Na página **Configurações de ambiente**, no Painel de Ações, selecione **Aplicativos conectados**.
2. Selecione **Novo** para criar um aplicativo conectado.
3. No campo **Nome**, insira o nome do aplicativo a ser conectado.
4. No campo **Aplicativo**, insira a URL do ambiente Finance e Supply Chain Management para conexão.
4. No campo **Locatário**, insira o locatário do ambiente Finance e Supply Chain Management.
5. Selecione **Salvar**.
6. No Painel de Ações, selecione **Verificar conexão** para testar a conexão com o ambiente. Depois feche a página.

## <a name="link-connected-applications-to-environments"></a>Vincular aplicativos conectados a ambientes

1. Na página **Configurações de ambiente**, selecione **Novo** para atribuir um aplicativo conectado a um ambiente.
2. No campo **Aplicativo conectado**, selecione um aplicativo conectado.
3. No campo **Ambiente de serviço**, selecione um ambiente de serviço.
4. Selecione **Salvar** e feche a página.

## <a name="set-up-the-electronic-invoicing-add-on-integration-in-finance-and-supply-chain-management"></a>Configurar a integração do Complemento de faturamento eletrônico no Finance e no Supply Chain Management

### <a name="turn-on-the-electronic-invoicing-add-on-integration-feature"></a>Ativar o recurso Integração do complemento de faturamento eletrônico

1. Entre na instância do Finance ou do Supply Chain Management.
2. No espaço de trabalho **Gerenciamento de recursos**, procure o recurso **Integração do complemento de faturamento eletrônico**. Se esse recurso não aparecer na página, selecione **Verificar se há atualizações**.
3. Selecione o recurso e **Habilitar agora**.

### <a name="set-up-the-service-endpoint-url"></a>Configurar a URL do ponto de extremidade de serviço

1. Vá para **Administração da organização \> Configuração \> Parâmetros de documentos eletrônicos**.
2. Na guia **Serviço de envio**, no campo **URL de ponto de extremidade de serviço**, insira o ponto de extremidade de serviço apropriado da geografia do Azure, conforme mostrado na tabela a seguir.

    | Geografia do data center Azure | URL do ponto de extremidade do serviço                                                       |
    |----------------------------|----------------------------------------------------------------------------|
    | Leste dos EUA                    | `https://electronicinvoicing.eus-il301.gateway.prod.island.powerapps.com/` |
    | Oeste dos EUA                    | `https://electronicinvoicing.wus-il301.gateway.prod.island.powerapps.com/` |
    | Norte da UE                   | `https://electronicinvoicing.neu-il301.gateway.prod.island.powerapps.com/` |
    | Oeste da UE                    | `https://electronicinvoicing.weu-il301.gateway.prod.island.powerapps.com/` |

3. No campo **Ambiente**, insira o nome do ambiente de complemento de faturamento eletrônico.
4. Selecione **Salvar** e feche a página.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]