---
title: Diretrizes de implantação para caixas registradoras da Noruega
description: Este tópico fornece diretrizes sobre como habilitar a funcionalidade de caixa registradora para a localização do Microsoft Dynamics 365 Commerce da Noruega.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: c7e64dbfe6a300c097b5b3711ac4310f3386df11
ms.sourcegitcommit: 0d2de52e12fdb9928556d37a4813a67b303695dc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2021
ms.locfileid: "7944731"
---
# <a name="deployment-guidelines-for-cash-registers-for-norway"></a>Diretrizes de implantação para caixas registradoras da Noruega

[!include[banner](../includes/banner.md)]

Este tópico fornece diretrizes sobre como habilitar a funcionalidade de caixa registradora para a localização do Microsoft Dynamics 365 Commerce da Noruega. A localização consiste em várias extensões de componentes. Essas extensões permitem executar ações como imprimir campos personalizados em recibos, registrar eventos de auditoria adicionais, transações de vendas e transações de pagamento no ponto de venda (PDV), assinar digitalmente transações de vendas e imprimir relatórios em formatos locais. Para obter mais informações sobre a localização para a Noruega, consulte [Funcionalidade de caixa registradora para a Noruega](./emea-nor-cash-registers.md). Para obter mais informações sobre como configurar o Commerce para a Noruega, consulte [Configurar o Commerce para a Noruega](./emea-nor-cash-registers.md#setting-up-commerce-for-norway).

> [!WARNING]
> Devido às limitações do [novo empacotamento independente e modelo de extensão](../dev-itpro/build-pipeline.md), ele não pode ser usado no momento para essa funcionalidade de localização. Você deve usar a versão do exemplo de assinatura digital da Noruega na versão anterior do software development kit (SDK) do Retail em uma máquina virtual (VM) de desenvolvedor no Microsoft Dynamics Lifecycle Services (LCS). Para obter mais informações, consulte [Diretrizes de implantação para caixas registradoras da Noruega (herdado)](./emea-nor-loc-deployment-guidelines.md).
>
> O suporte para o novo pacote independente e o modelo de extensão para os exemplo de integração fiscal está planejado para versões posteriores.

## <a name="set-up-fiscal-registration-for-norway"></a>Configurar processo de registro fiscal da Noruega

O exemplo de integração do serviço de registro fiscal da Noruega é baseado na [funcionalidade de integração fiscal](fiscal-integration-for-retail-channel.md) e faz parte do SDK do Retail. O exemplo está localizado na pasta **src\\FiscalIntegration\\SequentialSignatureNorway** do repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (por exemplo, [o exemplo na versão/9.34](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.34/src/FiscalIntegration/SequentialSignatureNorway)). O exemplo [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) em um provedor de documentos fiscais e um conector fiscal, que são extensões do Commerce Runtime (CRT). Para obter mais informações sobre como usar o SDK do Retail, consulte [arquitetura de SDK do Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md) e [Configurar um pipeline de build para o SDK de compactação independente](../dev-itpro/build-pipeline.md).

Conclua as etapas de configuração do registro fiscal descritas em [Configurar a integração da fiscal para os canais do Commerce](./setting-up-fiscal-integration-for-retail-channel.md):

1. [Configurar um processo de registro fiscal](./setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Lembre-se de anotar as configurações do processo de registro fiscal que são [específicas para a Noruega](#configure-the-fiscal-registration-process).
1. [Definir configurações de tratamento de erros](./setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Habilitar a execução manual do registro fiscal adiado](./setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Configurar os componentes de canal](#configure-channel-components).

### <a name="configure-the-fiscal-registration-process"></a>Configurar o processo de registro fiscal

Siga estas etapas para habilitar o processo de registro fiscal da Noruega na sede do Commerce.

1. Baixe arquivos de configuração para o provedor de documentos fiscais e o conector fiscal do SDK do Commerce:

    1. Abra o repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Abra a última ramificação de versão disponível (por exemplo, **[versão/9.34](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.34)**).
    1. Abra **src \> FiscalIntegration \> SequentialSignatureNorway \> CommerceRuntime**.
    1. Baixe o arquivo de configuração do provedor de documentos fiscais em **DocumentProvider.SequentialSignNorway \> Configuração \> DocumentProviderSequentialSignatureNorwaySample.xml** (por exemplo, [o arquivo para a versão/9.34](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.34/src/FiscalIntegration/SequentialSignatureNorway/CommerceRuntime/DocumentProvider.SequentialSignNorway/Configuration/DocumentProviderSequentialSignatureNorwaySample.xml)).
    1. Baixe o arquivo de configuração do conector fiscal em **Connector.SequentialSignNorway \> Configuração \> ConnectorSequentialSignatureNorwaySample.xml** (por exemplo, [o arquivo para a versão/9.34](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.34/src/FiscalIntegration/SequentialSignatureNorway/CommerceRuntime/Connector.SequentialSignNorway/Configuration/ConnectorSequentialSignatureNorwaySample.xml)).

1. Acesse **Varejo e Comércio \> Configuração da sede \> Parâmetros \> Parâmetros compartilhados**. Na guia **Geral**, defina a opção **Habilitar integração fiscal** como **Sim**.
1. Acesse **Retail e Commerce \> Configuração de canal \> Integração fiscal \> Conectores fiscais** e carregue o arquivo de configuração do conector fiscal baixado anteriormente.
1. Acesse **Retail e Commerce \> Configuração de canal \> Integração fiscal \> Provedores de documentos fiscais** e carregue o arquivo do provedor de documentos fiscais baixado anteriormente.
1. Acesse **Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Perfis funcionais do conector**. Crie um novo perfil funcional do conector e selecione o provedor de documentos e o conector carregados anteriormente.
1. Acesse **Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Perfis técnicos do conector**. Crie um novo perfil técnico do conector e selecione o conector carregado anteriormente. Defina o tipo de conector como **Interno**.
1. Acesse **Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Grupos de conectores fiscais** e crie um grupo de conectores fiscais para o perfil funcional do conector criado anteriormente.
1. Acesse **Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Processos de registro fiscal**. Crie um novo processo de registro fiscal e uma etapa do processo de registro fiscal e selecione o grupo do conector fiscal criado anteriormente.
1. Acesse **Retail e Commerce \> Configuração de canal \> Configuração do PDV \> Perfis de PDV \> Perfis de funcionalidade**. Selecione um perfil de funcionalidade vinculado à loja em que o processo de registro deve ser ativado. Na guia rápida **Processo de registro fiscal**, selecione o processo de registro fiscal criado anteriormente. Na guia rápida **Serviços fiscais**, selecione o perfil técnico do conector criado anteriormente. 
1. Acesse **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**. Abra a agenda de distribuição e selecione os trabalhos **1070** e **1090** para transferir dados para o banco de dados do canal.

### <a name="configure-the-digital-signature-parameters"></a>Configurar os parâmetros de assinatura digital

Você deve configurar certificados que serão usados para a assinatura digital de transações de vendas em uma loja. Um certificado digital armazenado no Azure Key Vault é usado para fazer a assinatura. Para o modo offline do PDV moderno, a assinatura também pode ser feita usando um certificado digital armazenado no armazenamento local da máquina em que o PDV moderno está instalado.

Para poder usar um certificado digital armazenado no armazenamento do Key Vault, as etapas a seguir devem ser concluídas.

1. O armazenamento do Key Vault deve ser criado. Recomendamos implantar o armazenamento na mesma região geográfica que o Commerce Scale Unit.
1. O certificado deve ser carregado no armazenamento do Key Vault como um segredo de cadeia de caracteres Base64.
1. O aplicativo AOS (Servidor de Objetos de Aplicativo) deve estar autorizado a ler segredos do armazenamento do Key Vault.

Para obter mais informações sobre como trabalhar com o Key Vault, consulte [Introdução do Azure Key Vault](/azure/key-vault/key-vault-get-started).

Em seguida, na página **Parâmetros do Key Vault**, você deve especificar os parâmetros para acessar o armazenamento do Key Vault:

- **Nome** e **Descrição** – O nome e a descrição do armazenamento do Key Vault.
- **URL do Key Vault** – A URL do armazenamento do Key Vault.
- **Cliente do Key Vault** – Uma ID do cliente interativo do aplicativo do Azure Active Directory (Azure AD) associado a um armazenamento do Key Vault para fins de autenticação. Esse cliente deve ter acesso para ler segredos do armazenamento.
- **Chave secreta do Key Vault** – Uma chave secreta associada ao aplicativo do Azure AD usado para autenticação no armazenamento do Key Vault.
- **Nome**, **Descrição** e **Referência secreta** – O nome, a descrição e a referência secreta do certificado.

Em seguida, você deve configurar um conector para os certificados armazenados no Key Vault ou no armazenamento local de certificados. Esse conector é usado para assinar o lado do canal.

1. Acesse **Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Perfis técnicos do conector**.
1. Na guia rápida **Configurações**, especifique os seguintes parâmetros para assinaturas digitais:

    - **Nome do segredo** – Selecione o nome do segredo configurado anteriormente na página **Parâmetros do Key Vault**.
    - **Impressão digital do certificado local** – Fornece uma impressão digital para um certificado armazenado localmente.
    - **Algoritmo de hash** – Especifique um dos algoritmos de hash criptográficos com suporte do Microsoft .NET, como **SHA1**.
    - **Nome do repositório de certificados** – Este campo é opcional. Use-o para especificar um nome de armazenamento padrão que deve ser usado para pesquisar certificados locais.
    - **Local do repositório de certificados** – Este campo é opcional. Use-o para especificar um local de armazenamento padrão que deve ser usado para pesquisar certificados locais.
    - **Tentar primeiro o certificado local** – Selecione esta opção para usar o certificado do armazenamento local por padrão para assinar dados, em vez do certificado do Key Vault.
    - **Ativar verificação de integridade** – ara obter mais informações sobre o recurso de verificação de integridade, consulte [Verificação de integridade do registro fiscal](./fiscal-integration-for-retail-channel.md#fiscal-registration-health-check).

> [!NOTE]
> - Somente o algoritmo de hash criptográfico **SHA1** é aceitável no momento para a Noruega.
> - O nome da loja e o local da loja padrão são adicionados para simplificar o processo de pesquisa de certificados locais no CRT. X509StoreProvider tem uma lista de pastas em que os certificados estão armazenados. Se o nome do armazenamento padrão e o local de armazenamento padrão não forem especificados, o X509StoreProvider tentará encontrar um certificado em todas as pastas da lista.

### <a name="configure-channel-components"></a>Configurar os componentes de canal

### <a name="development-environment"></a>Ambiente de desenvolvimento

Siga estas etapas e configure um ambiente de desenvolvimento para poder testar e estender a amostra.

1. Clone ou baixe o repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions). Selecione uma versão correta da ramificação de lançamento de acordo com a sua versão do SDK/aplicativo. Para obter mais informações, consulte [Baixar exemplos de SDK do Retail e pacotes de referência do GitHub e NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Abra a solução **SequentialSignatureNorway.sln** em **Dynamics365Commerce.Solutions\\FiscalIntegration\\SequentialSignatureNorway** e crie-a.
1. Instale as extensões do CRT:

    1. Localize o instalador de extensão do CRT:

        - **Commerce Scale Unit:** na pasta **SequentialSignatureNorway\\ScaleUnit\\ScaleUnit.SequentialSignNorway.Installer\\bin\\Debug\\net461**, encontre o instalador **ScaleUnit.SequentialSignNorway.Installer**.
        - **CRT local no PDV moderno:** na pasta **SequentialSignatureNorway\\ModernPOS\\ModernPos.SequentialSignNorway.Installer\\bin\\Debug\\net461**, encontre o instalador **ModernPos.SequentialSignNorway.Installer**.

    1. Inicie o instalador de extensão do CRT na linha de comando:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.SequentialSignNorway.Installer.exe install --verbosity 0
            ```

        - **CRT local no PDV moderno:**

            ```Console
            ModernPOS.SequentialSignNorway.Installer.exe install --verbosity 0
            ```

### <a name="production-environment"></a>Ambiente de produção

Siga as etapas em [Configurar um pipeline de build para um exemplo de integração fiscal](fiscal-integration-sample-build-pipeline.md) a fim de gerar e lançar os pacotes implantáveis de autoatendimento e do Cloud Scale Unit para o exemplo de integração fiscal. O arquivo YAML do modelo **SequentialSignatureNorway build-pipeline.yaml** pode ser encontrado na pasta **Pipeline\\YAML_Files** do repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

### <a name="enable-the-digital-signature-in-offline-mode-for-modern-pos"></a>Habilitar a assinatura digital no modo offline para o PDV Moderno

Para habilitar a assinatura digital no modo offline para o PDV Moderno, é necessário seguir estas etapas depois de ativar o PDV Moderno em um novo dispositivo.

1. Entre no POS.
1. Na página **Status da conexão do banco de dados**, verifique se o banco de dados offline está totalmente sincronizado. Quando o valor do campo **Downloads pendentes** for **0** (zero), o banco de dados será totalmente sincronizado.
1. Saia do PDV.
1. Aguarde até que o banco de dados offline seja totalmente sincronizado.
1. Entre no POS.
1. Na página **Status da conexão do banco de dados**, verifique se o banco de dados offline está totalmente sincronizado. Quando o valor do campo **Transações pendentes no banco de dados offline** for **0** (zero), o banco de dados será totalmente sincronizado.
1. Reabra o PDV moderno.
