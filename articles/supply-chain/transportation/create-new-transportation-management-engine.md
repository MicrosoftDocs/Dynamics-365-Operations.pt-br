---
title: Criar um mecanismo de gerenciamento de transporte
description: Este tópico descreve como criar um novo mecanismo de gerenciamento de transporte no Dynamics 365 Supply Chain Management.
author: Weijiesa
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSGenericEngine, TMSRateEngine, TMSMileageEngine, TMSEngineParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: 51661
ms.assetid: 0473acef-755e-4b42-acf5-5e5aa902dc0e
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: be52c6afb66e88b36f3b2cdf5af14e17b3d3005f
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8678112"
---
# <a name="create-a-new-transportation-management-engine"></a>Criar um mecanismo de gerenciamento de transporte

[!include [banner](../includes/banner.md)]

Este tópico descreve como criar um novo mecanismo de gerenciamento de transporte no Dynamics 365 Supply Chain Management. 

Os mecanismos de gerenciamento de transporte (TMS) definem a lógica usada para gerar e processar taxas de transporte no Gerenciamento de transporte. O Supply Chain Management oferece vários tipos diferentes de mecanismos que calculam parâmetros diferentes, como taxas, tempos em trânsito e o número de zonas que percorridas durante o transporte. Este artigo explica como usar o ambiente de desenvolvimento do Microsoft Visual Studio em conjunto com ferramentas de desenvolvimento do Supply Chain Management para criar e implantar um novo mecanismo de TMS e como configurar o mecanismo em Operações. Para obter mais informações sobre os mecanismos, consulte o artigo [mecanismos de gerenciamento de transporte ](transportation-management-engines.md).

## <a name="create-a-new-tms-engine"></a>Criar um novo mecanismo de TMS

Esta seção explica como criar uma biblioteca de classes que tem uma implementação de mecanismo de TMS e como referenciá-la de um modelo do Supply Chain Management.

1. Para implantar os novos mecanismos, você deve ter um modelo que contenha mecanismos. No menu **Dynamics 365** &gt; **Gerenciamento de Modelos**, clique em **Criar modelo** para criar um modelo. Na primeira página do assistente **Criar modelo**, nomeie o modelo **TMSEngines**. 

   [![Como criar uma modelo.](./media/012.png)](./media/012.png)

2. Na página seguinte, selecione **Criar pacote**. 

   [![Criando um novo pacote.](./media/021.png)](./media/021.png)

3. Na página seguinte, selecione o modelo **ApplicationSuite** para referência. (O modelo **ApplicationPlatform** está pré-selecionado.) 

   [![Como selecionar o modelo para referência.](./media/032.png)](./media/032.png)

4. Na página seguinte, clique em **Concluir** para confirmar a criação de um novo modelo. 

   [![Como concluir a criação do modelo.](./media/042.png)](./media/042.png)

5. Em uma nova solução, crie um projeto no Supply Chain Management e nomeie-o **TMSThirdParty**. Nas propriedades do projeto, defina o modelo do projeto como **TMSEngines**.
6. Adicione uma nova biblioteca de classes C\# à solução e chame-a de **ThirdPartyTMSEngines**.
7. No projeto ThirdPartyTMSEngines, adicione referências aos assemblies específicos do Supply Chain Management:
   -   Assemblies de aplicativos que permitem que os tipos X++ sejam referenciados. Esses assemblies podem ser encontrados nestes locais. \[A raiz dos pacotes\] é o caminho do local em que todos os assemblies implantados são colocados, como C:\\Pacotes.

        ```xpp
        [Packages root]\ApplicationPlatform\bin\Dynamics.AX.ApplicationPlatform.dll
        [Packages root]\ApplicationFoundation\bin\Dynamics.AX.ApplicationFoundation.dll
        [Packages root]\ApplicationSuite\bin\Dynamics.AX.ApplicationSuite.dll
        ```
        
   -   Assemblies da estrutura que permitem acesso a dados, LINQ e funções auxiliares. Todas essas montagem podem ser encontradas no compartimento \[Raiz de pacotes\]\\.

        ```xpp 
        Microsoft.Dynamics.ApplicationPlatform.Environment.dll
        Microsoft.Dynamics.AX.Data.Core.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.AdoNet.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.Interface.dll
        Microsoft.Dynamics.AX.Framework.Linq.Data.Msil.dll
        Microsoft.Dynamics.AX.Server.Core.dll
        Microsoft.Dynamics.AX.Xpp.AxShared.dll
        Microsoft.Dynamics.AX.Xpp.Support.dll
        ```

   -   O assembly de TMS principal (que contém mecanismos) e o assembly base de TMS (que contém auxiliares, constantes, definições de classes de transferência de dados e assim por diante). Esses assemblies podem ser encontrados nestes locais.

        ```xpp
        [Packages root]\ApplicationSuite\bin\Microsoft.Dynamics.AX.Tms.dll
        [Packages root]\ApplicationSuite\bin\Microsoft.Dynamics.AX.Tms.Base.dll
        ```
8. Renomeie a classe C\# que é gerada automaticamente no projeto ThirdPartyTMSEngines para **SampleRatingEngine**.
9. Implemente o mecanismo. Como estamos criando um mecanismo de taxa neste exemplo, herdamos da classe base para mecanismos de taxa. A classe base implementa a maioria da interface do mecanismo de taxa (**TMSFwkIRateEngine**). Precisamos apenas implementar o método rate. Para manter este exemplo simples, tornaremos esse método de registro em uma taxa de código de 100. Você pode criar mecanismos que implementam qualquer uma das interfaces de mecanismo, como **TMSFwkIAccessorialEngine**. Todas as interfaces de mecanismo são definidas no X++.

    ```xpp
    namespace ThirdPartyTMSEngines
    {
        using Dynamics.AX.Application;
        using Microsoft.Dynamics.Ax.Tms.Base.Data;
        using Microsoft.Dynamics.Ax.Tms.Base.Utility;
        using Microsoft.Dynamics.Ax.Tms.Bll;
        using System.Xml.Linq;
        public class SampleRatingEngine : BaseRateEngine
        {
            public override RatingDto rate(TmsTransactionFacade transactionFacade, XElement shipment, TMSRateMasterCode rateMasterCode)
            {
               XElement re = shipment.RetrieveOrCreateRatingEntity(this.RatingDto);
               re.AddRate(TmsRateType.Rate, 100);
               return this.RatingDto;
            }
        }
    }
    ```

10. Crie a solução.
11. Adicione uma nova referência ao projeto TMSThirdParty. A referência deve apontar para o projeto ThirdPartyTMSEngines. Quando terminar, a sua solução deverá ter ser assim. 

    [![A solução, que inclui uma referência ao projeto TMSThirdParty.](./media/052.png)](./media/052.png)

12. Crie a solução. Verifique se a nova biblioteca é exibida no nó **Referências** no aplicativo Explorer. 

    [![A nova biblioteca no nó Referências do aplicativo Explorer.](./media/061.png)](./media/061.png)

## <a name="deploy-the-tms-engine-as-a-package"></a>Implantar o mecanismo de TMS como um pacote

Uma forma de implantar mecanismos de TMS de terceiros é por meio de um pacote de implantação. Essa abordagem é recomendada em um ambiente de produção. Em um ambiente de desenvolvimento, você pode copiar manualmente os assemblies, conforme descrito na próxima seção, "Configurar um mecanismo de TMS no Supply Chain Management". Para implantar o mecanismo como um pacote, siga estas etapas.

1. No menu **Dynamics 365** &gt; **Implantar**, clique em <strong>Criar pacote de implantação</strong>.
2. Na caixa de diálogo **Criar pacote de implantação**, selecione o modelo TMSEngines e insira o caminho em que deseja armazenar os arquivos de pacote. 

   [![Como selecionar o modelo TMSEngines.](./media/071.png)](./media/071.png)

3. Agora você pode implantar o pacote no ambiente de destino. Para ver um tutorial, consulte o artigo [Instalar um pacote implantado](../../fin-ops-core/dev-itpro/deployment/install-deployable-package.md).

## <a name="set-up-the-tms-engine-in-supply-chain-management"></a>Configurar um mecanismo de TMS no Supply Chain Management

Esta seção explica como configurar o Supply Chain Management para usar um mecanismo de TMS e mostra como o novo mecanismo que criamos é usado em comparação de taxas. O exemplo nesta seção usa a empresa de dados demo USMF.

1. Crie um mecanismo, conforme descrito na seção "Criar um mecanismo de TMS".
2. Crie a solução.
3. Copie o assembly resultante para a localização binária do servidor do Supply Chain Management, compartimento \[AOSWebRoot\]. **Observação:** esta etapa é relevante apenas em um ambiente de desenvolvimento. Em um ambiente de produção, você deve implantar por meio de um pacote de implantação. Para obter instruções, consulte a seção anterior "Implantar o mecanismo de TMS como um pacote".
4. No Supply Chain Management, na página **Mecanismos de taxa**, crie um novo mecanismo de classificação. O mecanismo deve apontar para o conjunto de mecanismos que é produzido criando a biblioteca de classes de mecanismo e a classe de mecanismo que você implementou. 

   [![Como criar um mecanismo de classificação na página Mecanismos de taxa.](./media/081.png)](./media/081.png)

5. Crie uma transportadora que use o mecanismo de taxa de exemplo. Como nosso mecanismo não usa dados, você não precisa atribuir uma taxa mestra. 

   [![Como criar uma nova transportadora.](./media/092.png)](./media/092.png)

6. Na página **Bancada de roteiro de taxa**, clique em **Comparação de taxas**. Você verá uma taxa de 100,00 de SampleCarrier, conforme mostrado na captura de tela a seguir. Neste exemplo, estamos classificando as taxas de um roteiro do depósito 24 para o cliente US-004. No entanto, como a taxa é em códigos, você sempre verá uma taxa de 100,00.

   [![Bancada do roteiro de taxa.](./media/101.png)](./media/101.png)

## <a name="tips-and-tricks"></a>Dicas e truques

- Se você estiver usando ferramentas do Supply Chain Management, é útil adicionar um novo projeto à sua solução. Se você definir este projeto como seu projeto de inicialização e iniciar uma sessão de depuração, poderá depurar os códigos X++ e C\# na mesma sessão de depuração.
- Toda vez que você alterar e recompilar seu projeto ThirdPartyTMSEngines, deverá copiar manualmente o assembly resultante para o local binário ou implantá-lo por meio de um pacote de implantação. Caso contrário, você pode executar usando um assembly obsoleto.
- Depois de executar as operações específicas do TMS no Supply Chain Management, o processo de trabalho dos Serviços de Informações da Internet pode bloquear o assembly ThirdPartyTMSEngines para que ele não possa ser atualizado. Nesse caso, reinicie o processo W3SVC.

### <a name="whitepaper"></a>White paper

Para obter mais informações, baixe o white paper a seguir (escrito para dar suporte a AX2012, mas ainda é aplicável ao Dynamics 365 Supply Chain Management)

- [Implementação de mecanismos de gerenciamento de transporte](https://download.microsoft.com/download/b/5/f/b5ff8fef-3918-4c1d-92d5-b67eb0971684/ImplementingAndDeployingTransportationManagementEnginesInAX.pdf)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]