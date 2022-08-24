---
title: Assine o arquivo MPOS .appx com um certificado de assinatura de código
description: Este artigo explica como assinar o MPOS com um certificado de autenticação de código.
author: josaw1
ms.date: 05/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-09-2019
ms.custom: 28021
ms.openlocfilehash: bcf558b4b375078ed24777417e92b1c852f4c0eb
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282797"
---
# <a name="sign-the-mpos-appx-file-with-a-code-signing-certificate"></a>Assine o arquivo MPOS .appx com um certificado de assinatura de código

[!include [banner](../includes/banner.md)]

Para instalar o Modern POS (MPOS), você deve assinar o aplicativo MPOS com um certificado de autenticação de código de um fornecedor confiável e instalar o mesmo certificado em todas as máquinas em que o MPOS está instalado na pasta raiz confiável para o usuário atual.

Para assinar o aplicativo do MPOS com um certificado, use uma das seguintes opções do arquivo **SDK do Retail\\Ferramenta de criação\\Customization.settings**:

- Adicione a parte da tarefa Arquivo Seguro das etapas da criação de Azure DevOps e carregue o certificado para proteger a tarefa de arquivo. Use a variável de caminho de saída da tarefa de arquivo seguro como um parâmetro no arquivo Customization.settings.

    > [!NOTE]
    > A tarefa Arquivo Seguro não dá suporte a um certificado protegido por senha. Você deve remover a senha antes de carregar essa tarefa. Como o certificado é carregado para a tarefa do sistema de arquivos seguro no Azure, você poderá remover a senha apenas desta etapa. No entanto, você deve discutir a remoção da senha com especialistas em segurança para determinar se essa é a ação correta para o seu projeto. Não remova a senha do certificado para outros cenários.
- Use um certificado que esteja no sistema de arquivos. Para isso, baixe ou gere um certificado e coloque-o no sistema de arquivos em que a compilação está sendo executada. O agente hospedado da Microsoft ou o usuário da compilação deve ter acesso a esse caminho e arquivo.
- Use a impressão digital para pesquisar no certificado do armazenamento e entre com esse certificado.

## <a name="use-a-secure-file-task-for-universal-windows-platform-app-signing"></a>Usar uma tarefa Arquivo Seguro para a assinatura do aplicativo da Plataforma Universal do Windows

> [!NOTE]
> Você também pode usar o Azure Key Vault para armazenar o certificado e usar a ferramenta de assinatura do Azure para assinar o arquivo .appx e os instaladores de autoatendimento do Modern POS. Para obter informações adicionais e scripts de pipeline de exemplo, consulte [Configurar um pipeline de compilação no Azure DevOps para gerar pacotes de autoatendimento do Retail](build-pipeline.md#set-up-a-build-pipeline-in-azure-devops-to-generate-retail-self-service-packages).

O uso de uma tarefa Arquivo Seguro é a abordagem recomenda para a assinatura de aplicativos UWP (Plataforma Universal do Windows). Para obter mais informações sobre assinatura de pacote, consulte [Configurar assinatura de pacote](/windows/uwp/packaging/auto-build-package-uwp-apps#configure-package-signing). Esse processo é mostrado na imagem a seguir.

![Fluxo de assinatura do aplicativo do MPOS.](media/POSSigningFlow.png)

> [!NOTE]
> No momento, o pacote OOB oferece suporte apenas para assinar o arquivo .appx, os diferentes instaladores de autoatendimento como MPOIS, RSSU e HWS não são assinados por esse processo. Você precisa assiná-lo manualmente usando SignTool ou outras ferramentas de assinatura. O certificado usado para assinar o arquivo .appx deve ser instalado no computador em que o Modern POS está instalado.

## <a name="steps-to-configure-the-certificate-for-signing-in-azure-pipelines"></a>Etapas para configurar o certificado para assinatura no Azure Pipelines

### <a name="certificate-in-the-file-systemsecure-location"></a>Certificado no sistema de arquivos/local seguro

Baixe a [tarefa DownloadFile](/visualstudio/msbuild/downloadfile-task) e adicione-a como a primeira etapa no processo de compilação. A vantagem de usar a tarefa Arquivo Seguro é que o arquivo é criptografado e colocado no disco durante a compilação, não importa se o pipeline de build for bem-sucedido, falhar ou for cancelado. O arquivo é excluído do local de download após a conclusão do processo de compilação.

1. Baixe e adicione a tarefa Arquivo Seguro como a primeira etapa do pipeline de build do Azure. Você pode baixar a tarefa Arquivo Seguro de [DownloadFile](https://marketplace.visualstudio.com/items?itemName=automagically.DownloadFile).
1. Carregue o certificado para a tarefa Arquivo Seguro e defina o Nome de referência em Variáveis de Saída, conforme mostrado na imagem a seguir.
    > [!div class="mx-imgBorder"]
    > ![Tarefa Arquivo Seguro.](media/SecureFile.png)
1. Crie uma nova variável no Azure Pipelines ao selecionar **Nova Variável** na guia **Variáveis**.
1. Forneça um nome para a variável no campo de valor, por exemplo, **MySigningCert**.
1. Salve a variável.
1. Abra o arquivo **Customization.settings** de **RetailSDK\\BuildTools** e atualize **ModernPOSPackageCertificateKeyFile** com o nome da variável criada no pipeline (etapa 3). Por exemplo:

    ```Xml
    <ModernPOSPackageCertificateKeyFile Condition="'$(ModernPOSPackageCertificateKeyFile)' ==''">$(MySigningCert)</ModernPOSPackageCertificateKeyFile>
    ```
    Essa etapa será necessária se o certificado não estiver protegido por senha. Se o certificado for protegido por senha, continue com as etapas a seguir.
    
1. Se você quiser marcar a data e hora do arquivo MPOS .appx ao assiná-lo com um certificado, abra o arquivo **SDK do Retail\\Ferramenta de compilação\\Customization.settings** e atualize a variável **ModernPOSPackageCertificateTimestamp** com o provedor de carimbo de data e hora (por exemplo, `http://timestamp.digicert.com`).
1. Na guia **Variáveis** do pipeline, adicione uma nova variável de texto secure-text. Defina o nome como **MySigningCert.secret** e defina o valor da senha do certificado. Selecione o ícone de cadeado para proteger a variável.
1. Adicione uma tarefa **Script do Powershell** ao pipeline (após Baixar Arquivo Seguro e antes da etapa Compilar). Forneça o **Nome para exibição** e defina o Tipo como **Em linha**. Copie e cole o seguinte na seção do script.

    ```powershell
    Write-Host "Start adding the PFX file to the certificate store."
    $pfxpath = '$(MySigningCert.secureFilePath)'
    $secureString = ConvertTo-SecureString "$(MySigningCert.secret)" -AsPlainText -Force
    Import-PfxCertificate -FilePath $pfxpath -CertStoreLocation Cert:\CurrentUser\My -Password $secureString
    ```

1. Abra o arquivo **Customization.settings** de **RetailSDK\\BuildTools** e atualize **ModernPOSPackageCertificateThumbprint** com o valor da impressão digital do certificado.

    ```Xml
       <ModernPOSPackageCertificateThumbprint Condition="'$(ModernPOSPackageCertificateThumbprint)' == ''"></ModernPOSPackageCertificateThumbprint>
    ```
 
Para obter detalhes sobre como obter a impressão digital de um certificado, consulte [recuperar a impressão digital de um certificado](/dotnet/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate#to-retrieve-a-certificates-thumbprint). 

## <a name="download-or-generate-a-certificate-to-sign-the-mpos-app-manually-using-msbuild-in-sdk"></a>Baixar ou gerar um certificado para assinar o aplicativo do MPOS manualmente usando msbuild no SDK

Se um certificado baixado ou gerado for usado para assinar o aplicativo do MPOS, a atualização do nó **ModernPOSPackageCertificateKeyFile** no arquivo **BuildTools\\Customization.settings** para apontar para a localização do arquivo pfx (**$(SdkReferencesPath)\\appxsignkey.pfx**). Por exemplo:

```xml
<ModernPOSPackageCertificateKeyFile Condition="'$(ModernPOSPackageCertificateKeyFile)' ==''">$(SdkReferencesPath)\appxsignkey.pfx</ModernPOSPackageCertificateKeyFile>
```

Nesse caso, o nome do arquivo do certificado é **appxsignkey.pfx**, localizado na pasta **SDK do Retail\\Referência**.

## <a name="use-thumbprint-to-sign-the-mpos-app"></a>Usar a impressão digital para assinar o aplicativo do MPOS

Se você usar a impressão digital para assinar o aplicativo do MPOS, instale o certificado localmente. Atualize o valor da impressão digital no nó **ModernPOSPackageCertificateThumbprint** no arquivo **BuildTools\\Customization.settings**.

Esta opção funcionará se o usuário de compilação for um usuário local. No entanto, se você estiver usando os agentes do Azure DevOps para gerar a compilação, talvez o agente não tenha permissão para acessar o armazenamento de certificados para usar o certificado para assinatura ou a máquina de compilação não terá o certificado instalado. Nesse caso, a solução alternativa é alterar o usuário de compilação para usuário local e instalar o certificado na caixa. No entanto, essa opção não funcionará se você não tiver acesso administrativo à caixa.

> [!NOTE]
> Se a opção de arquivo .pfx ou tarefa Arquivo Seguro for usada para assinar o aplicativo, deixe o nó **ModernPOSPackageCertificateThumbprint** em **Customization.settings** vazio. Se a opção de impressão digital for usada, deixe **ModernPOSPackageCertificateKeyFile** vazio. Se ambos os valores forem atualizados, a compilação falhará.

### <a name="certification-renewal"></a>Renovação de certificação

### <a name="renew-a-certificate-from-trusted-ca"></a>Renovar um certificado de CA confiável

Contate a CA (autoridade de certificação) para o processo de renovação do certificado. Para um certificado confiável, nenhuma ação é necessária no lado do MPOS.

### <a name="renew-a-self-signed-certificate"></a>Renovar um certificado autoassinado

Não use o certificado de exemplo disponível no SDK do Retail para produção. Pode ser usado somente para fins de desenvolvimento. O certificado da Contoso de exemplo não pode ser renovado e o certificado de exemplo incluído no SDK do Retail versão 10.0.16 ou anterior expira em 31 de dezembro de 2020. Se esse certificado, ou um certificado autoassinado, tiver sido usado para assinar um Modern POS personalizado, há uma forte possibilidade de que o Modern POS não funcione corretamente após essa data.
 
### <a name="impact"></a>Impacto
 
Se o que estiver acima for verdadeiro para você, o problema encontrado é que o instalador não poderá ser executado após 31 de dezembro de 2020. Dependendo das políticas de TI corporativa usadas, pode ser que o Modern POS não funcione. É fundamental que você teste isso alterando a data temporariamente para uma data futura, a fim de determinar o impacto em sua organização.
 
### <a name="steps-to-determine-the-issue"></a>Etapas para determinar o problema
 
1.  Use as configurações do Windows para alterar o relógio do computador para uma data e hora no ano 2021.
2.  Verifique se o Modern POS pode ser aberto, se a entrada pode ocorrer e uma transação pode ser concluída.
3.  Verifique se o instalador de Autoatendimento do Modern POS pode ser executado e, nesse caso, se a instalação será concluída com êxito.
4.  Retorne as configurações de relógio do Windows para a data e a hora corretas.
 
Se for possível concluir todas essas etapas sem problemas, você poderá operar no certificado atual após 31 de dezembro de 2020.  
 
### <a name="steps-going-forward"></a>Etapas a partir de agora 

É altamente recomendável que você renove o certificado usado anteriormente. É altamente recomendável que você obtenha um novo certificado. Para isso, você deverá executar uma das seguintes ações:
 
- **Preferencial** - obtenha um certificado de autenticação de código de uma autoridade de certificação confiável.

- **Não Preferencial** - gere um certificado de autenticação de código autoassinado a ser usado. Isso é geralmente usado apenas para fins de desenvolvimento dentro de um domínio e não é recomendado para produção. 

- **Disponível como Solução temporária** - use o certificado de autenticação de código renovado da Contoso. Isso é normalmente usado para fins de teste, por isso não é recomendável que seja implantado em produção.
 
Em seguida, gere um novo pacote do Modern POS personalizado que é assinado usando este certificado obtido de uma das ações acima. Dependendo do certificado, uma das etapas a seguir deverá ser seguida:
 
- Se usar um certificado novo e confiável (ou um certificado novo e autoassinado), você será obrigado a instalar um novo certificado em cada dispositivo. Depois disso, você precisará pegar o recém-criado Pacote do Modern POS (instalador), desinstalar o aplicativo existente e, em seguida, reinstalar o novo pacote do Modern POS. Você precisará realizar uma ativação de dispositivo do Modern POS em todos os dispositivos.

- Se utilizar o certificado renovado da Contoso, será necessário instalar o novo certificado em cada dispositivo e instalar o Pacote do Modern POS (instalador). Você não é obrigado a desinstalar, mas deverá reinstalar no dispositivo. Observe que a ativação do dispositivo do Modern OS não será necessária. Esta opção é uma solução temporária. Use esta opção somente para evitar a reativação e resolver o problema antes de obter um novo certificado confiável.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
