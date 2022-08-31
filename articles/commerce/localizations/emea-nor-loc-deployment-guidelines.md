---
title: Diretrizes de implantação para caixas registradoras da Noruega (herdado)
description: Este artigo é um guia de implantação que mostra como habilitar a localização do Microsoft Dynamics 365 Commerce para a Noruega.
author: EvgenyPopovMBS
ms.date: 08/23/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2018-2-28
ms.openlocfilehash: fb597add48ac3508a88142e63d80f405b6b5f8b4
ms.sourcegitcommit: 1dbff0b5fa1f4722a1720fac35cce94606fa4320
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/24/2022
ms.locfileid: "9346036"
---
# <a name="deployment-guidelines-for-cash-registers-for-norway-legacy"></a>Diretrizes de implantação para caixas registradoras da Noruega (herdado)

[!include [banner](../includes/banner.md)]

> [!WARNING]
> Esta amostra de funcionalidade de integração fiscal não aproveita a [estrutura de integração fiscal](./fiscal-integration-for-retail-channel.md) e será preterida em atualizações posteriores. Você deve usar a [funcionalidade baseada na estrutura de integração fiscal](./emea-nor-fi-deployment.md).

Este artigo é um guia de implantação que mostra como habilitar a localização do Microsoft Dynamics 365 Commerce para a Noruega. A localização consiste em várias extensões de componentes do Commerce. Por exemplo, as extensões permitem imprimir campos personalizados em recibos, registrar eventos de auditoria adicionais, transações de vendas e transações de pagamento no Ponto de Venda (PDV), assinar digitalmente transações de vendas e imprimir relatórios X e Z em formatos locais. Para obter mais informações sobre a localização para a Noruega, consulte [Funcionalidade de caixa registradora para a Noruega](./emea-nor-cash-registers.md).

Este exemplo faz parte do kit de desenvolvimento de software (SDK) do Retail. Para obter informações sobre o SDK, consulte [Arquitetura do kit de desenvolvimento de software (SDK) do Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md).

Este exemplo consiste em extensões do Commerce Runtime (CRT), Retail Server e PDV. Para executar este exemplo, você deve modificar e criar os projetos do CRT, Retail Server e PDV. É recomendável usar um SDK não modificado do Retail para fazer as alterações descritas neste artigo. Também é recomendável usar um sistema de controle do código-fonte, como o Microsoft Visual Studio Online (VSO), onde nenhum arquivo foi alterado ainda.

> [!NOTE]
> No Commerce 10.0.8 e superior, o Retail Server é conhecido como Commerce Scale Unit. Como este artigo se aplica a várias versões anteriores do aplicativo, o *Retail Server* é usado em todo o artigo.
>
> Algumas etapas nos procedimentos deste artigo são diferentes, dependendo da versão do Commerce que você está usando. Para obter mais informações, consulte [Novidades ou alterações do Dynamics 365 Retail](../get-started/whats-new.md).

### <a name="using-certificate-profiles-in-commerce-channels"></a>Usar perfis de certificado em canais do Commerce

No Commerce versões 10.0.15 e posterior, você pode usar o recurso [Perfis de certificado definidos pelo usuário para lojas de varejo](./certificate-profiles-for-retail-stores.md), que oferece suporte a failover para offline quando o Key Vault ou o Commerce headquarters não estiverem disponíveis. O recurso estende a funcionalidade [Gerenciar segredos para canais de varejo](../dev-itpro/manage-secrets.md).

Para aplicar essa funcionalidade à extensão do CRT, siga estas etapas.

1. Crie um novo projeto de extensão do CRT (tipo de projeto de biblioteca de classe C#). Use os modelos de exemplo do kit de desenvolvimento de software (SDK) do Retail (RetailSDK\SampleExtensions\CommerceRuntime).

2. Adicione o manipulador personalizado para CertificateSignatureServiceRequest no projeto SequentialSignatureRegister.

3. Para ler uma chamada secreta, `GetUserDefinedSecretCertificateServiceRequest` usando um construtor com o parâmetro ProfileId. Isso iniciará a funcionalidade trabalhando com configurações de perfis de certificado. Com base nas configurações, o certificado será recuperado do Azure Key Vault ou do armazenamento do computador local.

    ```csharp
    GetUserDefinedSecretCertificateServiceRequest getUserDefinedSecretCertificateServiceRequest = new GetUserDefinedSecretCertificateServiceRequest(profileId: "ProfileId", secretName: null, thumbprint: null, expirationInterval: null);
    GetUserDefinedSecretCertificateServiceResponse getUserDefinedSecretCertificateServiceResponse = request.RequestContext.Execute<GetUserDefinedSecretCertificateServiceResponse>(getUserDefinedSecretCertificateServiceRequest);

    X509Certificate2 Certificate = getUserDefinedSecretCertificateServiceResponse.Certificate;
    ```

4. Quando o certificado for recuperado, continue com a assinatura de dados.

5. Crie o projeto de extensão do CRT.

6. Copie a biblioteca de classe de saída e cole-a em ...\RetailServer\webroot\bin\Ext para teste manual.

7. No arquivo CommerceRuntime.Ext.config, atualize a seção de composição de extensão com as informações da biblioteca personalizada.

## <a name="development-environment"></a>Ambiente de desenvolvimento

Conclua esses procedimentos e configure um ambiente de desenvolvimento para poder testar e estender a amostra.

### <a name="the-crt-extension-components"></a>Os componentes da extensão do CRT

Os componentes de extensão do CRT são incluídos nos exemplos de CRT. Para concluir os procedimentos a seguir, abra a solução do CRT, **CommerceRuntimeSamples.sln**, em **RetailSdk\\SampleExtensions\\CommerceRuntime**.

#### <a name="receiptsnorway-component"></a>Componente ReceiptsNorway

1. Encontre o projeto **Runtime.Extensions.ReceiptsNorway** e crie-o.
2. Na pasta **Extensions.ReceiptsNorway\\bin\\Debug**, encontre o arquivo assembly **Contoso.Commerce.Runtime.ReceiptsNorway.dll**.
3. Copie o arquivo assembly para a pasta de extensões do CRT:

    - **Retail Server:** copie o assembly para a pasta **\\bin\\ext** no local do site do Retail Server do Serviços de Informações da Internet da Microsoft (IIS).
    - **CRT local no PDV moderno:** Copie o assembly para a pasta **\\ext** no local do agente do cliente CRT local.

4. Localize o arquivo de configuração da extensão do CRT:

    - **Retail Server:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Retail Server do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

5. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
    ```

    > [!WARNING]
    > **Não** edite os arquivos commerceruntime.config e CommerceRuntime.MPDVOffline.config. Esses arquivos não são destinados a personalizações.

#### <a name="salespaymenttransext-component"></a>Componente SalesPaymentTransExt

1. Encontre o projeto **Runtime.Extensions.SalesPaymentTransExt** e crie-o.
2. Na pasta **Extensions.SalesPaymentTransExt\\bin\\Debug**, encontre o arquivo assembly **Contoso.Commerce.Runtime.SalesPaymentTransExt.dll**.
3. Copie o arquivo assembly para a pasta de extensões do CRT:

    - **Retail Server:** copie o assembly para a pasta **\\bin\\ext** no local do site do Retail Server do IIS.
    - **CRT local no PDV moderno:** Copie o assembly para a pasta **\\ext** no local do agente do cliente CRT local.

4. Localize o arquivo de configuração da extensão do CRT:

    - **Retail Server:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Retail Server do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

5. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
    ```

    > [!WARNING]
    > **Não** edite os arquivos commerceruntime.config e CommerceRuntime.MPDVOffline.config. Esses arquivos não são destinados a personalizações.

#### <a name="xzreportsnorway-component"></a>Componente XZReportsNorway

1. Encontre o projeto **Runtime.Extensions.XZReportsNorway** e crie-o.
2. Na pasta **Extensions.XZReportsNorway\\bin\\Debug**, encontre o arquivo assembly **Contoso.Commerce.Runtime.XZReportsNorway.dll**.
3. Copie o arquivo assembly para a pasta de extensões do CRT:

    - **Retail Server:** copie o assembly para a pasta **\\bin\\ext** no local do site do Retail Server do IIS.
    - **CRT local no PDV moderno:** Copie o assembly para a pasta **\\ext** no local do agente do cliente CRT local.

4. Localize o arquivo de configuração da extensão do CRT:

    - **Retail Server:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Retail Server do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

5. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
    ```

    > [!WARNING]
    > **Não** edite os arquivos commerceruntime.config e CommerceRuntime.MPDVOffline.config. Esses arquivos não são destinados a personalizações.

# <a name="application-update-4"></a>[Atualização de aplicativo 4](#tab/app-update-4)

#### <a name="registerauditevent-sample-component"></a>Componente de exemplo RegisterAuditEvent

1. Encontre o projeto **Runtime.Extensions.RegisterAuditEventSample** e crie-o.
2. Na pasta **Extensions.RegisterAuditEventSample\\bin\\Debug**, encontre o arquivo assembly **Contoso.Commerce.Runtime.RegisterAuditEventSample.dll**.
3. Copie o arquivo assembly para a pasta de extensões do CRT:

    - **Retail Server:** copie o assembly para a pasta **\\bin\\ext** no local do site do Retail Server do IIS.
    - **CRT local no PDV moderno:** Copie o assembly para a pasta **\\ext** no local do agente do cliente CRT local.

4. Localize o arquivo de configuração da extensão do CRT:

    - **Retail Server:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Retail Server do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

5. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > **Não** edite os arquivos commerceruntime.config e CommerceRuntime.MPDVOffline.config. Esses arquivos não são destinados a personalizações.

#### <a name="salestransactionsignature-sample-component"></a>Componente de exemplo SalesTransactionSignature

1. Encontre o projeto **Runtime.Extensions.SalesTransactionSignatureSample** e crie-o.
2. Modifique o arquivo **App.config** especificando a impressão digital, o local de armazenamento e o nome de armazenamento para o certificado que deve ser usado para assinar transações de vendas.
3. Crie o projeto.
4. Na pasta **Extensions.SalesTransactionSignatureSample\\bin\\Debug** encontre os seguintes arquivos:

    - O arquivo assembly **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll**
    - O arquivo de configuração **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**

5. Copie os arquivos para a pasta de extensões do CRT:

    - **Retail Server:** copie o assembly para a pasta **\\bin\\ext** no local do site do Retail Server do IIS.
    - **CRT local no PDV moderno:** Copie o assembly para a pasta **\\ext** no local do agente do cliente CRT local.

6. Localize o arquivo de configuração da extensão do CRT:

    - **Retail Server:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Retail Server do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

7. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
    ```

    > [!WARNING]
    > **Não** edite os arquivos commerceruntime.config e CommerceRuntime.MPDVOffline.config. Esses arquivos não são destinados a personalizações.

# <a name="application-update-5-and-later"></a>[Atualização do aplicativo versão 5 e posteriores](#tab/app-update-5-and-later)

#### <a name="registerauditevent-sample-component"></a>Componente de exemplo RegisterAuditEvent

1. Encontre o projeto **Runtime.Extensions.RegisterAuditEventSample** e crie-o.
2. Na pasta **Extensions.RegisterAuditEventSample\\bin\\Debug**, encontre o arquivo assembly **Contoso.Commerce.Runtime.RegisterAuditEventSample.dll**.
3. Copie o arquivo assembly para a pasta de extensões do CRT:

    - **Retail Server:** copie o assembly para a pasta **\\bin\\ext** no local do site do Retail Server do IIS.
    - **CRT local no PDV moderno:** Copie o assembly para a pasta **\\ext** no local do agente do cliente CRT local.

4. Localize o arquivo de configuração da extensão do CRT:

    - **Retail Server:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Retail Server do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

5. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > **Não** edite os arquivos commerceruntime.config e CommerceRuntime.MPDVOffline.config. Esses arquivos não são destinados a personalizações.

#### <a name="salestransactionsignature-sample-component"></a>Componente de exemplo SalesTransactionSignature

1. Encontre o projeto **Runtime.Extensions.SalesTransactionSignatureSample** e crie-o.
2. Modifique o arquivo **App.config** especificando a impressão digital, o local de armazenamento e o nome de armazenamento para o certificado que deve ser usado para assinar transações de vendas.
3. Crie o projeto.
4. Na pasta **Extensions.SalesTransactionSignatureSample\\bin\\Debug** encontre os seguintes arquivos:

    - O arquivo assembly **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll**
    - O arquivo de configuração **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**

5. Copie os arquivos para a pasta de extensões do CRT:

    - **Retail Server:** copie o assembly para a pasta **\\bin\\ext** no local do site do Retail Server do IIS.
    - **CRT local no PDV moderno:** Copie o assembly para a pasta **\\ext** no local do agente do cliente CRT local.

6. Localize o arquivo de configuração da extensão do CRT:

    - **Retail Server:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Retail Server do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

7. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
    ```

    > [!WARNING]
    > **Não** edite os arquivos commerceruntime.config e CommerceRuntime.MPDVOffline.config. Esses arquivos não são destinados a personalizações.

#### <a name="salestransactionsignaturesamplemessages-component"></a>Componente SalesTransactionSignatureSample.Messages

1. Encontre o projeto **Runtime.Extensions.SalesTransactionSignatureSample.Messages** e crie-o.
2. Na pasta **Extensions.SalesTransactionSignatureSample.Messages\\bin\\Debug**, encontre o arquivo assembly **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll**.
3. Copie o arquivo assembly para a pasta de extensões do CRT:

    - **Retail Server:** copie o assembly para a pasta **\\bin\\ext** no local do site do Retail Server do IIS.
    - **CRT local no PDV moderno:** Copie o assembly para a pasta **\\ext** no local do agente do cliente CRT local.

4. Localize o arquivo de configuração da extensão do CRT:

    - **Retail Server:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Retail Server do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

5. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages" />
    ```

    > [!WARNING]
    > **Não** edite os arquivos commerceruntime.config e CommerceRuntime.MPDVOffline.config. Esses arquivos não são destinados a personalizações.

# <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

#### <a name="registerauditevent-sample-component"></a>Componente de exemplo RegisterAuditEvent

1. Encontre o projeto **Runtime.Extensions.RegisterAuditEventSample** e crie-o.
2. Na pasta **Extensions.RegisterAuditEventSample\\bin\\Debug**, encontre o arquivo assembly **Contoso.Commerce.Runtime.RegisterAuditEventSample.dll**.
3. Copie o arquivo assembly para a pasta de extensões do CRT:

    - **Retail Server:** copie o assembly para a pasta **\\bin\\ext** no local do site do Retail Server do IIS.
    - **CRT local no PDV moderno:** Copie o assembly para a pasta **\\ext** no local do agente do cliente CRT local.

4. Localize o arquivo de configuração da extensão do CRT:

    - **Retail Server:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Retail Server do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

5. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > **Não** edite os arquivos commerceruntime.config e CommerceRuntime.MPDVOffline.config. Esses arquivos não são destinados a personalizações.

#### <a name="salestransactionsignature-sample-component"></a>Componente de exemplo SalesTransactionSignature

1. Encontre o projeto **Runtime.Extensions.SalesTransactionSignatureSample** e crie-o.
2. Modifique o arquivo **App.config** especificando a impressão digital, o local de armazenamento e o nome de armazenamento para o certificado que deve ser usado para assinar transações de vendas.
3. Crie o projeto.
4. Na pasta **Extensions.SalesTransactionSignatureSample\\bin\\Debug** encontre os seguintes arquivos:

    - O arquivo assembly **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll**
    - O arquivo de configuração **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**

5. Copie os arquivos para a pasta de extensões do CRT:

    - **Retail Server:** copie o assembly para a pasta **\\bin\\ext** no local do site do Retail Server do IIS.
    - **CRT local no PDV moderno:** Copie o assembly para a pasta **\\ext** no local do agente do cliente CRT local.

6. Localize o arquivo de configuração da extensão do CRT:

    - **Retail Server:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Retail Server do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

7. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
    ```

    > [!WARNING]
    > **Não** edite os arquivos commerceruntime.config e CommerceRuntime.MPDVOffline.config. Esses arquivos não são destinados a personalizações.

#### <a name="sequentialsignatureregistercontracts-component"></a>Componente SequentialSignatureRegister.Contracts

1. Encontre o projeto **Runtime.Extensions.SequentialSignatureRegister.Contracts** e crie-o.
2. Na pasta **Extensions.SequentialSignatureRegister.Contracts\\bin\\Debug**, encontre o arquivo de montagem **Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll**.
3. Copie o arquivo assembly para a pasta de extensões do CRT:

    - **Retail Server:** copie o assembly para a pasta **\\bin\\ext** no local do site do Retail Server do IIS.
    - **CRT local no PDV moderno:** Copie o assembly para a pasta **\\ext** no local do agente do cliente CRT local.

# <a name="retail-732-and-later"></a>[Retail 7.3.2 e posterior](#tab/retail-7-3-2)

#### <a name="registerauditevent-sample-component"></a>Componente de exemplo RegisterAuditEvent

1. Encontre o projeto **Runtime.Extensions.RegisterAuditEventSample** e crie-o.
2. Na pasta **Extensions.RegisterAuditEventSample\\bin\\Debug**, encontre o arquivo assembly **Contoso.Commerce.Runtime.RegisterAuditEventSample.dll**.
3. Copie o arquivo assembly para a pasta de extensões do CRT:

    - **Retail Server:** copie o assembly para a pasta **\\bin\\ext** no local do site do Retail Server do IIS.
    - **CRT local no PDV moderno:** Copie o assembly para a pasta **\\ext** no local do agente do cliente CRT local.

4. Localize o arquivo de configuração da extensão do CRT:

    - **Retail Server:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Retail Server do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

5. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > **Não** edite os arquivos commerceruntime.config e CommerceRuntime.MPDVOffline.config. Esses arquivos não são destinados a personalizações.

#### <a name="sequentialsignatureregister-component"></a>Componente SequentialSignatureRegister

1. Encontre o projeto **Runtime.Extensions.SequentialSignatureRegister** e crie-o.
2. Modifique o arquivo **App.config** especificando a impressão digital, o local de armazenamento e o nome de armazenamento para o certificado que deve ser usado para assinar transações de vendas.
3. Crie o projeto.
4. Na pasta **Extensions.SequentialSignatureRegister\\bin\\Debug** encontre os seguintes arquivos:

    - O arquivo assembly **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll**
    - O arquivo de configuração **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**

5. Copie os arquivos para a pasta de extensões do CRT:

    - **Retail Server:** copie o assembly para a pasta **\\bin\\ext** no local do site do Retail Server do IIS.
    - **CRT local no PDV moderno:** Copie o assembly para a pasta **\\ext** no local do agente do cliente CRT local.

6. Localize o arquivo de configuração da extensão do CRT:

    - **Retail Server:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Retail Server do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

7. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
    ```

    > [!WARNING]
    > **Não** edite os arquivos commerceruntime.config e CommerceRuntime.MPDVOffline.config. Esses arquivos não são destinados a personalizações.

#### <a name="salestransactionsignaturenorway-component"></a>Componente SalesTransactionSignatureNorway

1. Encontre o projeto **Runtime.Extensions.SalesTransactionSignatureNorway** e crie-o.
2. Na pasta **Extensions.SalesTransactionSignatureNorway\\bin\\Debug**, encontre o arquivo de montagem **Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll**.
3. Copie o arquivo assembly para a pasta de extensões do CRT:

    - **Retail Server:** copie o assembly para a pasta **\\bin\\ext** no local do site do Retail Server do IIS.
    - **CRT local no PDV moderno:** Copie o assembly para a pasta **\\ext** no local do agente do cliente CRT local.

4. Localize o arquivo de configuração da extensão do CRT:

    - **Retail Server:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Retail Server do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

5. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
    ```

    > [!WARNING]
    > **Não** edite os arquivos commerceruntime.config e CommerceRuntime.MPDVOffline.config. Esses arquivos não são destinados a personalizações.

#### <a name="sequentialsignatureregistercontracts-component"></a>Componente SequentialSignatureRegister.Contracts

1. Encontre o projeto **Runtime.Extensions.SequentialSignatureRegister.Contracts** e crie-o.
2. Na pasta **Extensions.SequentialSignatureRegister.Contracts\\bin\\Debug**, encontre o arquivo de montagem **Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll**.
3. Copie o arquivo assembly para a pasta de extensões do CRT:

    - **Retail Server:** copie o assembly para a pasta **\\bin\\ext** no local do site do Retail Server do IIS.
    - **CRT local no PDV moderno:** Copie o assembly para a pasta **\\ext** no local do agente do cliente CRT local.

#### <a name="salespaymenttransextnorway-component"></a>Componente SalesPaymentTransExtNorway

1. Encontre o projeto **Runtime.Extensions.SalesPaymentTransExtNorway** e crie-o.
2. Na pasta **Extensions.SalesPaymentTransExtNorway\\bin\\Debug**, encontre o arquivo assembly **Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll**.
3. Copie o arquivo assembly para a pasta de extensões do CRT:

    - **Retail Server:** copie o assembly para a pasta **\\bin\\ext** no local do site do Retail Server do IIS.
    - **CRT local no PDV moderno:** Copie o assembly para a pasta **\\ext** no local do agente do cliente CRT local.

4. Localize o arquivo de configuração da extensão do CRT:

    - **Retail Server:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Retail Server do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

5. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
    ```

    > [!WARNING]
    > **Não** edite os arquivos commerceruntime.config e CommerceRuntime.MPDVOffline.config. Esses arquivos não são destinados a personalizações.

# <a name="retail-735-and-later"></a>[Retail 7.3.5 e posterior](#tab/retail-7-3-5)

#### <a name="registerauditeventnorway-component"></a>Componente RegisterAuditEventNorway

1. Localize o arquivo de configuração da extensão do CRT:

    - **Retail Server:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Retail Server do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

2. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
    ```

    > [!WARNING]
    > **Não** edite os arquivos commerceruntime.config e CommerceRuntime.MPDVOffline.config. Esses arquivos não são destinados a personalizações.

#### <a name="sequentialsignatureregister-component"></a>Componente SequentialSignatureRegister

1. Encontre o projeto **Runtime.Extensions.SequentialSignatureRegister** e crie-o.
2. Modifique o arquivo **App.config** especificando a impressão digital, o local de armazenamento e o nome de armazenamento para o certificado que deve ser usado para assinar transações de vendas.
3. Crie o projeto.
4. Na pasta **Extensions.SequentialSignatureRegister\\bin\\Debug** encontre os seguintes arquivos:

    - O arquivo assembly **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll**
    - O arquivo de configuração **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**

5. Copie os arquivos para a pasta de extensões do CRT:

    - **Retail Server:** copie o assembly para a pasta **\\bin\\ext** no local do site do Retail Server do IIS.
    - **CRT local no PDV moderno:** Copie o assembly para a pasta **\\ext** no local do agente do cliente CRT local.

6. Localize o arquivo de configuração da extensão do CRT:

    - **Retail Server:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Retail Server do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

7. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
    ```

    > [!WARNING]
    > **Não** edite os arquivos commerceruntime.config e CommerceRuntime.MPDVOffline.config. Esses arquivos não são destinados a personalizações.

#### <a name="salestransactionsignaturenorway-component"></a>Componente SalesTransactionSignatureNorway

1. Encontre o projeto **Runtime.Extensions.SalesTransactionSignatureNorway** e crie-o.
2. Na pasta **Extensions.SalesTransactionSignatureNorway\\bin\\Debug**, encontre o arquivo de montagem **Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll**.
3. Copie o arquivo assembly para a pasta de extensões do CRT:

    - **Retail Server:** copie o assembly para a pasta **\\bin\\ext** no local do site do Retail Server do IIS.
    - **CRT local no PDV moderno:** Copie o assembly para a pasta **\\ext** no local do agente do cliente CRT local.

4. Localize o arquivo de configuração da extensão do CRT:

    - **Retail Server:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Retail Server do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

5. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
    ```

    > [!WARNING]
    > **Não** edite os arquivos commerceruntime.config e CommerceRuntime.MPDVOffline.config. Esses arquivos não são destinados a personalizações.

#### <a name="sequentialsignatureregistercontracts-component"></a>Componente SequentialSignatureRegister.Contracts

1. Encontre o projeto **Runtime.Extensions.SequentialSignatureRegister.Contracts** e crie-o.
2. Na pasta **Extensions.SequentialSignatureRegister.Contracts\\bin\\Debug**, encontre o arquivo de montagem **Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll**.
3. Copie o arquivo assembly para a pasta de extensões do CRT:

    - **Retail Server:** copie o assembly para a pasta **\\bin\\ext** no local do site do Retail Server do IIS.
    - **CRT local no PDV moderno:** Copie o assembly para a pasta **\\ext** no local do agente do cliente CRT local.

#### <a name="salespaymenttransextnorway-component"></a>Componente SalesPaymentTransExtNorway

1. Encontre o projeto **Runtime.Extensions.SalesPaymentTransExtNorway** e crie-o.
2. Na pasta **Extensions.SalesPaymentTransExtNorway\\bin\\Debug**, encontre o arquivo assembly **Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll**.
3. Copie o arquivo assembly para a pasta de extensões do CRT:

    - **Retail Server:** copie o assembly para a pasta **\\bin\\ext** no local do site do Retail Server do IIS.
    - **CRT local no PDV moderno:** Copie o assembly para a pasta **\\ext** no local do agente do cliente CRT local.

4. Localize o arquivo de configuração da extensão do CRT:

    - **Retail Server:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Retail Server do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

5. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
    ```

    > [!WARNING]
    > **Não** edite os arquivos commerceruntime.config e CommerceRuntime.MPDVOffline.config. Esses arquivos não são destinados a personalizações.

# <a name="retail-811-and-later"></a>[Retail 8.1.1 e posterior](#tab/retail-8-1-1)

#### <a name="registerauditeventnorway-component"></a>Componente RegisterAuditEventNorway

1. Localize o arquivo de configuração da extensão do CRT:

    - **Retail Server:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Retail Server do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

2. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
    ```

    > [!WARNING]
    > **Não** edite os arquivos commerceruntime.config e CommerceRuntime.MPDVOffline.config. Esses arquivos não são destinados a personalizações.

#### <a name="sequentialsignatureregister-component"></a>Componente SequentialSignatureRegister

1. Encontre o projeto **Runtime.Extensions.SequentialSignatureRegister** e crie-o.
2. Modifique o arquivo **App.config** especificando a impressão digital, o local de armazenamento e o nome de armazenamento para o certificado que deve ser usado para assinar transações de vendas.
3. Crie o projeto.
4. Na pasta **Extensions.SequentialSignatureRegister\\bin\\Debug** encontre os seguintes arquivos:

    - O arquivo assembly **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll**
    - O arquivo de configuração **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**

5. Copie os arquivos para a pasta de extensões do CRT:

    - **Retail Server:** copie o assembly para a pasta **\\bin\\ext** no local do site do Retail Server do IIS.
    - **CRT local no PDV moderno:** Copie o assembly para a pasta **\\ext** no local do agente do cliente CRT local.

6. Localize o arquivo de configuração da extensão do CRT:

    - **Retail Server:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Retail Server do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

7. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
    ```

    > [!WARNING]
    > **Não** edite os arquivos commerceruntime.config e CommerceRuntime.MPDVOffline.config. Esses arquivos não são destinados a personalizações.

#### <a name="salestransactionsignaturenorway-component"></a>Componente SalesTransactionSignatureNorway

1. Encontre o projeto **Runtime.Extensions.SalesTransactionSignatureNorway** e crie-o.
2. Na pasta **Extensions.SalesTransactionSignatureNorway\\bin\\Debug**, encontre o arquivo de montagem **Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll**.
3. Copie o arquivo assembly para a pasta de extensões do CRT:

    - **Retail Server:** copie o assembly para a pasta **\\bin\\ext** no local do site do Retail Server do IIS.
    - **CRT local no PDV moderno:** Copie o assembly para a pasta **\\ext** no local do agente do cliente CRT local.

4. Localize o arquivo de configuração da extensão do CRT:

    - **Retail Server:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Retail Server do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

5. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
    ```

    > [!WARNING]
    > **Não** edite os arquivos commerceruntime.config e CommerceRuntime.MPDVOffline.config. Esses arquivos não são destinados a personalizações.

#### <a name="sequentialsignatureregistercontracts-component"></a>Componente SequentialSignatureRegister.Contracts

1. Encontre o projeto **Runtime.Extensions.SequentialSignatureRegister.Contracts** e crie-o.
2. Na pasta **Extensions.SequentialSignatureRegister.Contracts\\bin\\Debug**, encontre o arquivo de montagem **Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll**.
3. Copie o arquivo assembly para a pasta de extensões do CRT:

    - **Retail Server:** copie o assembly para a pasta **\\bin\\ext** no local do site do Retail Server do IIS.
    - **CRT local no PDV moderno:** Copie o assembly para a pasta **\\ext** no local do agente do cliente CRT local.

#### <a name="salespaymenttransextnorway-component"></a>Componente SalesPaymentTransExtNorway

1. Encontre o projeto **Runtime.Extensions.SalesPaymentTransExtNorway** e crie-o.
2. Na pasta **Extensions.SalesPaymentTransExtNorway\\bin\\Debug**, encontre o arquivo assembly **Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll**.
3. Copie o arquivo assembly para a pasta de extensões do CRT:

    - **Retail Server:** copie o assembly para a pasta **\\bin\\ext** no local do site do Retail Server do IIS.
    - **CRT local no PDV moderno:** Copie o assembly para a pasta **\\ext** no local do agente do cliente CRT local.

4. Localize o arquivo de configuração da extensão do CRT:

    - **Retail Server:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Retail Server do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

5. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
    ```

    > [!WARNING]
    > **Não** edite os arquivos commerceruntime.config e CommerceRuntime.MPDVOffline.config. Esses arquivos não são destinados a personalizações.

---

### <a name="the-retail-server-extension-components"></a>Os componentes de extensão do Retail Server

#### <a name="salestransactionsignature-retail-server-sample-component"></a>Componente de exemplo SalesTransactionSignature Retail Server

1. Na pasta **RetailSDK\\SampleExtensions\\RetailServer\\RetailServer.Extensions.SalesTransactionSignatureSample**, encontre o projeto **RetailServer.Extensions.SalesTransactionSignatureSample** e crie-o.
2. Na pasta **RetailServer\\Extensions.SalesTransactionSignatureSample\\bin\\Debug**, encontre o arquivo assembly **Contoso.RetailServer.SalesTransactionSignatureSample.dll**.
3. Copie o arquivo assembly para a pasta de extensões do Retail Server.

    # <a name="application-update-4"></a>[Atualização de aplicativo 4](#tab/app-update-4)

    A pasta é a pasta **\\bin** no local do site do Retail Server do IIS.

    # <a name="application-update-5-and-later"></a>[Atualização do aplicativo versão 5 e posteriores](#tab/app-update-5-and-later)

    A pasta é a pasta **\\bin** no local do site do Retail Server do IIS.

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    A pasta é a pasta **\\bin\\ext** no local do site do Retail Server do IIS.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 e posterior](#tab/retail-7-3-2)

    A pasta é a pasta **\\bin\\ext** no local do site do Retail Server do IIS.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 e posterior](#tab/retail-7-3-5)

    A pasta é a pasta **\\bin\\ext** no local do site do Retail Server do IIS.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 e posterior](#tab/retail-8-1-1)

    A pasta é a pasta **\\bin\\ext** no local do site do Retail Server do IIS.

    ---

4. Localize o arquivo de configuração do Retail Server. O nome do arquivo é **web.config**, e ele está na pasta raiz, no local do site do Retail Server do IIS.
5. Registre as extensões do Retail Server na seção **extensionComposition** do arquivo de configuração.

    ``` xml
    <add source="assembly" value="Contoso.RetailServer.SalesTransactionSignatureSample" />
    ```

6. Registre as dependências das extensões do Retail Server.

    # <a name="application-update-4"></a>[Atualização de aplicativo 4](#tab/app-update-4/)

    1. Na pasta **CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\bin\\Debug**, encontre os seguintes arquivos:

        - O arquivo assembly **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll**
        - O arquivo de configuração **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**

    2. Copie os arquivos para a pasta **\\bin** no local do site do Retail Server do IIS.
    3. Registre a alteração do CRT no arquivo de configuração da extensão do CRT. O nome desse arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin**, no local do site do Retail Server do IIS.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        ```

    # <a name="application-update-5-and-later"></a>[Atualização do aplicativo versão 5 e posteriores](#tab/app-update-5-and-later/)

    1. Na pasta **CommerceRuntime\\Extensions.SalesTransactionSignatureSample.Messages\\bin\\Debug**, encontre o arquivo assembly **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll**.
    2. Copie o arquivo para a pasta **\\bin** no local do site do Retail Server do IIS.
    3. Registre a alteração do CRT no arquivo de configuração da extensão do CRT. O nome desse arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin**, no local do site do Retail Server do IIS.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages" />
        ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Nenhuma ação é necessária.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 e posterior](#tab/retail-7-3-2)

    > [!NOTE]
    > Nenhuma ação é necessária.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 e posterior](#tab/retail-7-3-5)

    > [!NOTE]
    > Nenhuma ação é necessária.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 e posterior](#tab/retail-8-1-1)

    > [!NOTE]
    > Nenhuma ação é necessária.

    ---

### <a name="the-modern-pos-extension-components"></a>Os componentes da extensão do Modern PDV

#### <a name="implement-the-proxy-code-for-offline-mode"></a>Implementar o código proxy para o modo offline

Essa parte é equivalente ao controlador do Retail Server, mas estende o CRT local, que é usado quando o cliente não está conectado.

1. No arquivo **customization.settings**, altere a seção **@(RetailServerLibraryPathForProxyGeneration)** para que ela use o novo assembly do Retail Server para geração de proxy.
2. Implemente os seguintes métodos de interface na classe **StoreOperationsManager**. Para a primeira iteração, adicione o seguinte código:

    # <a name="application-update-4"></a>[Atualização de aplicativo 4](#tab/app-update-4)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady()
    {
        throw new NotImplementedException();
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        throw new NotImplementedException();
    }
    ```

    # <a name="application-update-5-and-later"></a>[Atualização do aplicativo versão 5 e posteriores](#tab/app-update-5-and-later)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady(string correlationId)
    {
        throw new NotImplementedException();
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        throw new NotImplementedException();
    }
    ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Essa etapa não se aplica a esta versão.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 e posterior](#tab/retail-7-3-2)

    > [!NOTE]
    > Essa etapa não se aplica a esta versão.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 e posterior](#tab/retail-7-3-5)

    > [!NOTE]
    > Essa etapa não se aplica a esta versão.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 e posterior](#tab/retail-8-1-1)

    > [!NOTE]
    > Essa etapa não se aplica a esta versão.

    ---

3. Para regenerar o código proxy, crie a pasta **Proxies** a partir da linha de comando usando o comando **msbuild /t:Rebuild**.
4. Resolva as dependências do projeto **Proxies.RetailProxy**:

    # <a name="application-update-4"></a>[Atualização de aplicativo 4](#tab/app-update-4)

    Abra **RetailSDK\\Proxies\\RetailProxy\\Proxies.RetailProxy.csproj**, adicione o projeto **RetailSDK\\SampleExtensions\\CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\CommerceRuntime.Extensions.SalesTransactionSignatureSample** à solução e adicione uma referência de projeto ao projeto **RetailProxy** para fazer referência a **SalesTransactionSignatureSample**.

    # <a name="application-update-5-and-later"></a>[Atualização do aplicativo versão 5 e posteriores](#tab/app-update-5-and-later)

    Abra **RetailSDK\\Proxies\\RetailProxy\\Proxies.RetailProxy.csproj**, adicione o projeto **RetailSDK\\SampleExtensions\\CommerceRuntime\\Extensions.SalesTransactionSignatureSample.Messages\\CommerceRuntime.Extensions.SalesTransactionSignatureSample.Messages** à solução e adicione uma referência de projeto ao projeto **RetailProxy** para fazer referência a **SalesTransactionSignatureSample.Messages**.

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Essa etapa não se aplica a esta versão.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 e posterior](#tab/retail-7-3-2)

    > [!NOTE]
    > Essa etapa não se aplica a esta versão.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 e posterior](#tab/retail-7-3-5)

    > [!NOTE]
    > Essa etapa não se aplica a esta versão.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 e posterior](#tab/retail-8-1-1)

    > [!NOTE]
    > Essa etapa não se aplica a esta versão.

    ---

5. Ajuste os métodos de interface na classe **StoreOperationsManager**:

    # <a name="application-update-4"></a>[Atualização de aplicativo 4](#tab/app-update-4)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady()
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<SalesTransactionSignatureServiceIsReadyResponse>(new SalesTransactionSignatureServiceIsReadyRequest(), null).IsReady);
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<GetLastFiscalTransactionResponse>(new GetLastFiscalTransactionRequest(), null).FiscalTransaction);
    }
    ```

    # <a name="application-update-5-and-later"></a>[Atualização do aplicativo versão 5 e posteriores](#tab/app-update-5-and-later)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady(string correlationId)
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<SalesTransactionSignatureServiceIsReadyResponse>(new SalesTransactionSignatureServiceIsReadyRequest(), null).IsReady);
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<GetLastFiscalTransactionResponse>(new GetLastFiscalTransactionRequest(), null).FiscalTransaction);
    }
    ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Essa etapa não se aplica a esta versão.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 e posterior](#tab/retail-7-3-2)

    > [!NOTE]
    > Essa etapa não se aplica a esta versão.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 e posterior](#tab/retail-7-3-5)

    > [!NOTE]
    > Essa etapa não se aplica a esta versão.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 e posterior](#tab/retail-8-1-1)

    > [!NOTE]
    > Essa etapa não se aplica a esta versão.

    ---

6. Atualize o arquivo **dllhost.exe.config** para que o agente do cliente carregue o novo assembly RetailProxy.

    ``` xml
    <add key="RetailProxyAssemblyName" value="Contoso.Commerce.RetailProxy" />
    <add key="AdaptorCallerFullTypeName" value="Contoso.Commerce.RetailProxy.Adapters.AdaptorCaller" />
    ```

#### <a name="retail-proxy-extension-component-retail-731-and-later"></a>Componente de extensão do proxy do Retail (Retail 7.3.1 e posterior)

Conclua o procedimento a seguir somente se estiver usando o Retail 7.3.1 e posterior.

1. Na pasta **RetailSDK\\SampleExtensions\\RetailProxy\\RetailProxy.Extensions.SalesTransactionSignatureSample**, encontre o projeto **RetailServer.Extensions.SalesTransactionSignatureSample** e crie-o.
2. Na pasta **RetailProxy\\RetailProxy.Extensions.SalesTransactionSignatureSample\\bin\\Debug**, encontre o arquivo assembly **Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample**.
3. Copie os arquivos assembly para a pasta **\\ext** no local do agente do cliente CRT local.
4. Registre a alteração do proxy do Retail no arquivo de configuração da extensão. O nome do arquivo é **RetailProxy.MPDVOffline.ext.config**, e ele está no local do agente do cliente CRT local.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
    ```

#### <a name="modern-pos-extension-components"></a>Componentes da extensão do Modern PDV

1. Abra a solução em **RetailSdk\\PDV\\ModernPDV.sln** e verifique se ela pode ser compilada sem erros. Além disso, verifique se você pode executar o Modern PDV do Microsoft Visual Studio usando o comando **Run**.

    > [!NOTE]
    > O PDV Moderno não deve ser personalizado. Você deve habilitar o UAC (Controle de Conta de Usuário) e desinstalar instâncias instaladas anteriormente do PDV Moderno, conforme necessário.

2. Inclua as seguintes pastas de código-fonte existentes no projeto **Pos.Extensions**.

    # <a name="application-update-4"></a>[Atualização de aplicativo 4](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[Atualização do aplicativo versão 5 e posteriores](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 e posterior](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 e posterior](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 e posterior](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    ---

3. Habilite as extensões a serem compiladas no **tsconfig.json** removendo as seguintes pastas da lista de exclusões.

    # <a name="application-update-4"></a>[Atualização de aplicativo 4](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[Atualização do aplicativo versão 5 e posteriores](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 e posterior](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 e posterior](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 e posterior](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    ---

4. Habilite as extensões a serem carregadas em **extensions.json** adicionando as seguintes linhas no local apropriado.

    # <a name="application-update-4"></a>[Atualização de aplicativo 4](#tab/app-update-4)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="application-update-5-and-later"></a>[Atualização do aplicativo versão 5 e posteriores](#tab/app-update-5-and-later)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 e posterior](#tab/retail-7-3-2)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 e posterior](#tab/retail-7-3-5)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 e posterior](#tab/retail-8-1-1)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    ---

    > [!NOTE]
    > Para obter mais informações e para exemplos que mostram como incluir pastas de código-fonte e permitir que as extensões sejam carregadas, consulte as instruções no arquivo readme.md no projeto **Pos.Extensions**.

5. Recrie a solução.
6. Execute o PDV Moderno no depurador e teste a funcionalidade.

### <a name="cloud-pos-extension-components"></a>Componentes da extensão do PDV em Nuvem

1. Abra a solução em **RetailSdk\\POS\\CloudPOS.sln** e verifique se ela pode ser compilada sem erros.
2. Inclua as seguintes pastas de código-fonte existentes no projeto **Pos.Extensions**.

    # <a name="application-update-4"></a>[Atualização de aplicativo 4](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[Atualização do aplicativo versão 5 e posteriores](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 e posterior](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 e posterior](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 e posterior](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    ---

3. Habilite as extensões a serem compiladas no **tsconfig.json** removendo as seguintes pastas da lista de exclusões.

    # <a name="application-update-4"></a>[Atualização de aplicativo 4](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[Atualização do aplicativo versão 5 e posteriores](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 e posterior](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 e posterior](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 e posterior](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    ---

4. Habilite as extensões a serem carregadas em **extensions.json** adicionando as seguintes linhas no local apropriado.

    # <a name="application-update-4"></a>[Atualização de aplicativo 4](#tab/app-update-4)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="application-update-5-and-later"></a>[Atualização do aplicativo versão 5 e posteriores](#tab/app-update-5-and-later)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 e posterior](#tab/retail-7-3-2)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 e posterior](#tab/retail-7-3-5)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 e posterior](#tab/retail-8-1-1)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    ---

    > [!NOTE]
    > Para obter mais informações e para exemplos que mostram como incluir pastas de código-fonte e permitir que as extensões sejam carregadas, consulte as instruções no arquivo readme.md no projeto **Pos.Extensions**.

5. Recrie a solução.
6. Execute a solução usando o comando **Run** e seguindo as etapas no manual do SDK do Retail.
7. Teste a funcionalidade.

### <a name="set-up-required-parameters-in-headquarters"></a>Configurar os parâmetros obrigatórios no headquarters

Para obter mais informações, consulte [Funcionalidade de caixa registradora para a Noruega](./emea-nor-cash-registers.md).

## <a name="production-environment"></a>Ambiente de produção

Siga estas etapas para criar pacotes implantáveis que contenham componentes do Commerce e para aplicar esses pacotes em um ambiente de produção.

1. Conclua as etapas na seção [Componentes da extensão do PDV em Nuvem](#cloud-pos-extension-components) ou [Componentes da extensão do Modern POS](#modern-pos-extension-components) anteriormente neste artigo.
2. Faça as alterações a seguir nos arquivos de configuração do pacote na pasta **RetailSdk\\Assets**:

    1. Nos arquivos de configuração **commerceruntime.ext.config** e **CommerceRuntime.MPOSOffline.Ext.config**, adicione as seguintes linhas à seção **composição**:

        # <a name="application-update-4"></a>[Atualização de aplicativo 4](#tab/app-update-4)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="application-update-5-and-later"></a>[Atualização do aplicativo versão 5 e posteriores](#tab/app-update-5-and-later)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 e posterior](#tab/retail-7-3-2)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 e posterior](#tab/retail-7-3-5)

        ``` xml
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 e posterior](#tab/retail-8-1-1)

        ``` xml
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        ---

    2. Habilite a personalização do proxy do Commerce:

        # <a name="application-update-4"></a>[Atualização de aplicativo 4](#tab/app-update-4)

        No arquivo de configuração **dllhost.exe.config**, adicione as seguintes linhas à subseção **appSettings** da seção **Configuração**.

        ``` xml
        <add key="RetailProxyAssemblyName" value="Contoso.Commerce.RetailProxy"/>
        <add key="AdaptorCallerFullTypeName" value ="Contoso.Commerce.RetailProxy.Adapters.AdaptorCaller"/>
        ```

        # <a name="application-update-5-and-later"></a>[Atualização do aplicativo versão 5 e posteriores](#tab/app-update-5-and-later)

        No arquivo de configuração **dllhost.exe.config**, adicione as seguintes linhas à subseção **appSettings** da seção **Configuração**.

        ``` xml
        <add key="RetailProxyAssemblyName" value="Contoso.Commerce.RetailProxy"/>
        <add key="AdaptorCallerFullTypeName" value ="Contoso.Commerce.RetailProxy.Adapters.AdaptorCaller"/>
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        No arquivo de configuração **RetailProxy.MPOSOffline.ext.config**, adicione as seguintes linhas à seção **composição**:

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 e posterior](#tab/retail-7-3-2)

        No arquivo de configuração **RetailProxy.MPOSOffline.ext.config**, adicione as seguintes linhas à seção **composição**:

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 e posterior](#tab/retail-7-3-5)

        No arquivo de configuração **RetailProxy.MPOSOffline.ext.config**, adicione as seguintes linhas à seção **composição**:

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 e posterior](#tab/retail-8-1-1)

        No arquivo de configuração **RetailProxy.MPOSOffline.ext.config**, adicione as seguintes linhas à seção **composição**:

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        ---

3. Faça as alterações a seguir no arquivo de configuração de personalização de pacote **Customization.settings**:

    1. Habilite a personalização do proxy do Retail.

        # <a name="application-update-4"></a>[Atualização de aplicativo 4](#tab/app-update-4)

        Adicione as seguintes linhas à seção **&lt;ItemGroup Condition="'@(RetailServerLibraryPathForProxyGeneration)' == ''"&gt;**.

        ``` xml
        <RetailServerLibraryPathForProxyGeneration Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll"/>
        ```

        # <a name="application-update-5-and-later"></a>[Atualização do aplicativo versão 5 e posteriores](#tab/app-update-5-and-later)

        Adicione as seguintes linhas à seção **&lt;ItemGroup Condition="'@(RetailServerLibraryPathForProxyGeneration)' == ''"&gt;**.

        ``` xml
        <RetailServerLibraryPathForProxyGeneration Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll"/>
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        Adicione as seguintes linhas à seção **ItemGroup** para incluir a extensão do proxy do Retail nos pacotes implantáveis:

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 e posterior](#tab/retail-7-3-2)

        Adicione as seguintes linhas à seção **ItemGroup** para incluir a extensão do proxy do Retail nos pacotes implantáveis:

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 e posterior](#tab/retail-7-3-5)

        Adicione as seguintes linhas à seção **ItemGroup** para incluir a extensão do proxy do Retail nos pacotes implantáveis:

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 e posterior](#tab/retail-8-1-1)

        Adicione as seguintes linhas à seção **ItemGroup** para incluir a extensão do proxy do Retail nos pacotes implantáveis:

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        ---

    2. Adicione as seguintes linhas à seção **ItemGroup** para incluir as extensões do CRT nos pacotes implantáveis:

        # <a name="application-update-4"></a>[Atualização de aplicativo 4](#tab/app-update-4)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="application-update-5-and-later"></a>[Atualização do aplicativo versão 5 e posteriores](#tab/app-update-5-and-later)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 e posterior](#tab/retail-7-3-2)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 e posterior](#tab/retail-7-3-5)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 e posterior](#tab/retail-8-1-1)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        ---

    3. Adicione as seguintes linhas à seção **ItemGroup** para incluir a extensão do Retail Server nos pacotes implantáveis:

        # <a name="application-update-4"></a>[Atualização de aplicativo 4](#tab/app-update-4)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        ```

        # <a name="application-update-5-and-later"></a>[Atualização do aplicativo versão 5 e posteriores](#tab/app-update-5-and-later)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll" />
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 e posterior](#tab/retail-7-3-2)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 e posterior](#tab/retail-7-3-5)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 e posterior](#tab/retail-8-1-1)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        ---

4. Modifique os seguintes arquivos para incluir os arquivos de recursos para a Noruega em pacotes implantáveis:
    - Packages\_SharedPackagingProjectComponents\Sdk.ModernPos.Shared.csproj
    - Packages\RetailServer\Sdk.RetailServerSetup.proj
  
  - Para o arquivo **Sdk.ModernPos.Shared.csproj** 
    - Adicione uma linha à seção **ItemGroup**
    
        ``` xml
        <<File_name> Include="$(SdkReferencesPath)\nb-NO\*" />
        ```
    > [!Note]
    > Em vez de <File_name>, especifique o nome do arquivo de recurso. O mesmo é relevante para os outros exemplos mostrados abaixo.
 
    - Adicione uma linha à seção **Target Name="CopyPackageFiles"**
       ``` xml
        <Copy SourceFiles="@(<File_name>)" DestinationFolder="$(OutputPath)content.folder\CustomizedFiles\ClientBroker\ext\nb-NO" SkipUnchangedFiles="true" />
        ```
  
  - Para o arquivo **Sdk.RetailServerSetup.proj** 
    - Adicione uma linha à seção **ItemGroup**
        ``` xml
        <<File_name> Include="$(SdkReferencesPath)\nb-NO\*" />
        ```    
    - Adicione uma linha à seção **Target Name="CopyPackageFiles"**
         ``` xml
        <Copy SourceFiles="@(<File_name>)" DestinationFolder="$(OutputPath)content.folder\RetailServer\Code\bin\ext\nb-NO" SkipUnchangedFiles="true" />
        ```    

5. Modifique o arquivo de configuração do certificado especificando a impressão digital, o local de armazenamento e o nome de armazenamento para o certificado que deve ser usado para assinar transações de vendas. Em seguida, copie o arquivo de configuração para a pasta **Referências**.

    # <a name="application-update-4"></a>[Atualização de aplicativo 4](#tab/app-update-4)

    O nome do arquivo é **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**, e ele está em **CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\bin\\Debug**.

    # <a name="application-update-5-and-later"></a>[Atualização do aplicativo versão 5 e posteriores](#tab/app-update-5-and-later)

    O nome do arquivo é **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**, e ele está em **CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\bin\\Debug**.

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    O nome do arquivo é **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**, e ele está em **CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\bin\\Debug**.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 e posterior](#tab/retail-7-3-2)

    O nome do arquivo é **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**, e ele está em **Extensions.SequentialSignatureRegister\\bin\\Debug**.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 e posterior](#tab/retail-7-3-5)

    O nome do arquivo é **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**, e ele está em **Extensions.SequentialSignatureRegister\\bin\\Debug**.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 e posterior](#tab/retail-8-1-1)

    O nome do arquivo é **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**, e ele está em **Extensions.SequentialSignatureRegister\\bin\\Debug**.

    ---

6. Atualize o arquivo de configuração do Retail Server. No arquivo **RetailSDK\\Packages\\RetailServer\\Code\\web.config**, adicione as seguintes linhas à seção **extensionComposition**.

    ``` xml
    <add source="assembly" value="Contoso.RetailServer.SalesTransactionSignatureSample" />
    ```

7. Execute **msbuild** para o SDK do Retail completo para criar pacotes implantáveis.
8. Aplique os pacotes via Microsoft Dynamics Lifecycle Services (LCS) ou manualmente. Para obter mais informações, consulte [Criar pacotes implantáveis](../dev-itpro/retail-sdk/retail-sdk-packaging.md).

### <a name="enable-the-digital-signature-in-offline-mode-for-modern-pos"></a>Habilitar a assinatura digital no modo offline para o PDV Moderno

Para habilitar a assinatura digital no modo offline para o PDV Moderno, é necessário seguir estas etapas depois de ativar o PDV Moderno em um novo dispositivo.

1. Entre no POS.
2. Na página **Status da conexão do banco de dados**, verifique se o banco de dados offline está totalmente sincronizado. Quando o valor do campo **Downloads pendentes** for **0** (zero), o banco de dados será totalmente sincronizado.
3. Saia do PDV.
4. Aguarde um pouco até que o banco de dados offline seja totalmente sincronizado.
5. Entre no POS.
6. Na página **Status da conexão do banco de dados**, verifique se o banco de dados offline está totalmente sincronizado. Quando o valor do campo **Transações pendentes no banco de dados offline** for **0** (zero), o banco de dados será totalmente sincronizado.
7. Reinicie o PDV Moderno.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
