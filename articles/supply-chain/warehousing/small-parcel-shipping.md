---
title: Remessa de pacotes pequenos
description: Este tópico fornece informações sobre o recurso SPS (remessa de pacotes pequenos). Esse recurso permite que o Microsoft Dynamics 365 Supply Chain Management envie detalhes sobre um contêiner embalado para a transportadora e, em seguida, receba dessa transportadora uma etiqueta de remessa, uma taxa de remessa e um número de rastreamento.
author: Mirzaab
manager: tfehr
ms.date: 01/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSRateEngine, TMSCarrier, CustTable, TMSShippingCarrierCustomerAccount, TMSSmallParcelShippingFeature
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-08
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 37f07139853c30da25c067a3d736b4b9bf4eb361
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "5501165"
---
# <a name="small-parcel-shipping"></a>Remessa de pacotes pequenos

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

O recurso SPS (remessa de pacotes pequenos) permite que o Microsoft Dynamics 365 Supply Chain Management interaja diretamente com as transportadoras fornecendo uma estrutura para a comunicação por meio de APIs de transportadora. Essa funcionalidade é útil ao remeter ordens de venda individuais por meio de transportadoras comerciais em vez de usar a remessa de contêineres ou a remessa de carga parcial (LTL).

O recurso SPS interage com a transportadora por meio de um *mecanismo de taxa* dedicado. Sua organização deve desenvolver esse mecanismo de taxa em colaboração com a transportadora ou com o serviço de hub de transportadoras. O mecanismo de taxa permite que o Supply Chain Management envie detalhes sobre um contêiner embalado para a transportadora e, em seguida, receba dessa transportadora uma etiqueta de remessa, uma taxa de remessa e um número de rastreamento.

A taxa de remessa retornada é adicionada à ordem de venda associada como um encargo diverso. A etiqueta de remessa retornada pode então ser impressa automaticamente usando uma impressora ZPL (Linguagem de Programação Zebra) e aplicada à remessa. A transportadora verificará essa etiqueta de remessa quando retirar os pacotes no seu depósito.

## <a name="prepare-your-system-to-support-sps"></a>Preparar o sistema para oferecer suporte à SPS

Antes de começar a usar a funcionalidade de SPS, você deve ativar o recurso SPS no Gerenciamento de recursos, adicionar seu mecanismo de taxa e configurar os módulos **Gerenciamento de transporte** e **Gerenciamento de depósito** para oferecer suporte a ele.

### <a name="turn-on-the-sps-feature"></a>Ativar o recurso SPS

Para que você possa usar o recurso SPS, ele deverá ser ativado no sistema. Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo se necessário. Nesse caso, o recurso é listado da seguinte maneira:

- **Módulo:** *Gerenciamento de transporte*
- **Nome do recurso:** *Remessa de pacotes pequenos*

### <a name="deploy-and-set-up-rate-engines"></a>Implantar e configurar mecanismos de taxa

O Supply Chain Management não inclui nenhum mecanismo de taxa. Você deve obter ou criar os mecanismos de taxa necessários e adicioná-los ao sistema. No entanto, a Microsoft fornece um mecanismo de taxa de demonstração que pode ser usado para testes.

#### <a name="download-and-deploy-the-demo-rate-engine"></a>Baixar e implantar o mecanismo de taxa de demonstração

Siga estas etapas para obter o mecanismo de taxa de demonstração.

1. No GitHub, baixe a [biblioteca de vínculo dinâmico (DLL) para o mecanismo de taxa de demonstração](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/SCM/SPS).
1. No servidor do Supply Chain Management, salve a DLL na pasta **\\AOSService\\PackagesLocalDirectory\\ApplicationSuite\\bin**.

#### <a name="create-and-deploy-functional-rate-engines"></a>Criar e implantar mecanismos de taxa funcionais

Para obter informações sobre como criar e implantar mecanismos de taxa funcionais para que possam ser usados em um ambiente de produção ou de teste, consulte os seguintes tópicos:

- [​Criar um novo mecanismo de gerenciamento de transporte​](../transportation/create-new-transportation-management-engine.md)
- [Configurar mecanismos de gerenciamento de transporte](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-transportation-management-engines)

Para obter mais informações sobre como criar um mecanismo de taxa de SPS, consulte a seguinte postagem de blog: [Remessa de pacotes pequenos: como aproveitar a funcionalidade de remessa de pacotes pequenos no Microsoft Dynamics 365](https://hub.bhsolutions.com/creating-a-mock-parcel-engine-in-d365?submissionGuid=46a1fccf-80b0-4b70-a6a0-4bf45a8756b5).

#### <a name="set-up-a-rate-engine-in-supply-chain-management"></a>Configurar um mecanismo de taxa no Supply Chain Management

Depois de criar e implantar um mecanismo de taxa na SPS, siga estas etapas para configurá-lo.

1. Vá para **Gerenciamento de transporte \> Configuração \> Mecanismos \> Mecanismo de taxa**.
1. No Painel de Ação, selecione **Novo** para adicionar uma linha à grade.
1. Na nova linha, defina os seguintes campos:

    - **Mecanismo de taxa** – Insira um nome exclusivo para o mecanismo de taxa. Se você estiver usando o mecanismo de taxa de demonstração, insira *Mecanismo de taxa de demonstração*.
    - **Nome** – Insira uma breve descrição do mecanismo de taxa. Se você estiver usando o mecanismo de taxa de demonstração, insira *Mecanismo de taxa de demonstração*.
    - **ID de metadados de classificação** – Selecione a base que deve ser usada para calcular a taxa. Por exemplo, sua taxa pode ser calculada com base na distância. Se você estiver usando o mecanismo de taxa de demonstração, poderá deixar este campo em branco.
    - **Assembly do mecanismo** – Insira o nome do arquivo do pacote de DLL implantado. Se você estiver usando o mecanismo de taxa de demonstração, insira *TMSSmallParcelShippingEngine.dll*.
    - **Classe do mecanismo** – Insira o nome da classe que foi estabelecido para o mecanismo de taxa. Se você estiver usando o mecanismo de taxa de demonstração, insira *TMSSmallParcelShippingEngine.SmallParcelShippingRateEngine*.

## <a name="example-scenario"></a>Cenário de exemplo

Este cenário de exemplo mostra como configurar e usar a SPS depois de preparar o sistema, conforme descrito anteriormente neste tópico. Ele usa o mecanismo de taxa de demonstração mencionado anteriormente.

### <a name="make-demo-data-available"></a>Disponibilizar dados de demonstração

Para trabalhar nesse cenário usando os registros e valores de demonstração especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados. Além disso, você deve selecionar a entidade legal **USMF** antes de começar.

### <a name="set-up-the-scenario"></a>Configurar o cenário

Para este cenário de exemplo, você deve ter uma transportadora de demonstração, um grupo de transportadoras, uma política de embalagem e um perfil de embalagem. As subseções a seguir explicam como preparar os registros necessários para o cenário. Em um cenário de produção, o processo de configuração normalmente se assemelha ao processo descrito aqui. No entanto, você definirá valores diferentes.

#### <a name="set-up-carriers"></a>Configurar transportadoras

Siga estas etapas para configurar uma transportadora.

1. Vá para **Gerenciamento de transporte \> Configurar \> Transportadoras \> Transportadoras**.
1. No Painel de Ações, selecione **Novo** para adicionar uma transportadora.
1. No cabeçalho, defina os seguintes valores:

    - **Transportadora:** *Transportadora de demonstração*
    - **Nome:** *Transportadora de demonstração*
    - **Modo:** *Terrestre*

1. Na FastTab **Visão geral**, defina os seguintes valores:

    - **Ativar transportadora:** *Sim*
    - **Ativar classificação de transportadora:** *Sim*

1. Na FastTab **Serviços**, selecione **Novo** para adicionar um serviço à grade.
1. Defina os seguintes valores para o novo serviço:

    - **Serviço de transportadora:** *Serviço de transportadora de demonstração*
    - **Nome:** *Serviço de transportadora de demonstração*
    - **Método de transporte:** *Terrestre*

    Insira valores arbitrários para todos os outros campos, conforme necessário. (Quando você salvar o novo registro de transportadora, um novo modo de entrega será criado e o campo **Modo de entrega** será definido automaticamente.)

1. Na FastTab **Perfis de classificação**, selecione **Novo** para adicionar um perfil de classificação à grade.
1. Defina os seguintes valores para o novo perfil:

    - **Perfil de classificação:** *Serviço de transportadora de demonstração*
    - **Nome:** *Serviço de transportadora de demonstração*
    - **Mecanismo de taxa:** *Mecanismo de taxa de demonstração*

    Insira valores arbitrários para todos os outros campos, conforme necessário.

1. No Painel de ações, selecione **Salvar**.

Para obter mais informações sobre como configurar transportadoras, consulte [Configurar transportadoras](../transportation/tasks/set-up-shipping-carriers.md).

#### <a name="set-up-carrier-service-accounts"></a>Configurar contas de serviço de transportadora

Siga estas etapas para configurar uma conta de serviço de transportadora.

1. Vá para **Gerenciamento de transporte \> Configuração \> Classificação \> Conta de serviço de transportadora**.
1. No Painel de Ações, selecione **Novo** para adicionar uma conta de serviço de transportadora.
1. Defina os seguintes valores para a nova conta:

    - **Transportadora:** *Transportadora de demonstração*
    - **Serviço de transportadora:** *Serviço de transportadora de demonstração*
    - **Número da conta de cliente de transportadora:** o número da conta de cliente de transportadora usado para verificar e autenticar a conexão com a transportadora. A transportadora fornecerá esse valor. Se você estiver usando o serviço de demonstração, poderá inserir um valor arbitrário.
    - **Local:** *6*
    - **Depósito:** *62*

    > [!NOTE]
    > Geralmente, o valor **Número da conta de cliente de transportadora** é o único valor necessário para autenticar a conexão. No entanto, se a transportadora exigir parâmetros de autenticação adicionais, sua organização deverá personalizar esta página para adicionar campos extras, conforme apropriado.

#### <a name="set-up-a-container-packing-policy"></a>Configurar uma política de embalagem de contêiner

Siga estas etapas para configurar uma política de embalagem de contêiner.

1. Se você ainda não configurou uma definição de impressora ZPL, use o aplicativo Agente de Roteamento de Documentos para configurá-la. Para obter mais informações, consulte [Visão geral da impressão de documentos](../../fin-ops-core/dev-itpro/analytics/print-documents.md) e tópicos relacionados.
1. Vá para **Gerenciamento de depósito \> Configuração \> Contêineres \> Políticas de embalagem de contêiner**.
1. No Painel de Ações, selecione **Novo** para adicionar uma política de embalagem de contêiner.
1. No cabeçalho da nova política, defina os seguintes valores:

    - **Política de embalagem de contêiner:** *Política de embalagem de demonstração*
    - **Descrição:** uma descrição da política

1. Na FastTab **Visão geral**, defina os seguintes valores:

    - **Depósito:** *62*
    - **Local padrão para remessa final:** *Baydoor*
    - **Unidade de peso:** *Kg*
    - **Política de fechamento de contêiner:** *Liberação automática*
    - **Política de liberação de contêiner:** *Disponibilizar no local da remessa final*

1. Na FastTab **Manifesto de contêiner**, defina os seguintes valores:

    - **Manifesto automático no fechamento do contêiner:** *Sim*
    - **Requisitos de manifesto para contêiner:** *Gerenciamento de transporte*
    - **Imprimir conteúdo de contêiner:** *Não*

1. Na FastTab **Impressão de etiqueta de transportadora**, defina os seguintes valores:

    - **Imprimir etiqueta de remessa de contêiner:** *Sempre*
    - **Nome da impressora:** o nome da impressora ZPL que deve imprimir etiquetas de remessa

#### <a name="set-up-a-packing-profile"></a>Configurar um perfil de embalagem

Siga estas etapas para configurar um perfil de embalagem.

1. Vá para **Gerenciamento de depósito \> Configuração \> Embalagem \> Perfis de embalagem**.
1. No Painel de Ações, selecione **Novo** para adicionar um perfil de embalagem à grade.
1. Defina os seguintes valores para o novo perfil:

    - **ID do perfil de embalagem:** *Perfil de embalagem de demonstração*
    - **Descrição:** uma descrição do perfil
    - **Política de embalagem de contêiner:** *Política de embalagem de demonstração*
    - **Modo de ID do Contêiner:** *Automático*
    - **Tipo de contêiner:** *SmallBox*

#### <a name="set-up-a-customer-to-use-the-sps-carrier"></a>Configurar um cliente para usar a transportadora de SPS

Siga estas etapas para configurar um cliente de modo que ele possa usar a transportadora que você criou.

1. Vá para **Contas a receber \> Clientes \> Todos os clientes**.
1. Na grade, localize e selecione o cliente *US-027*.
1. No Painel de Ações, na guia **Geral**, no grupo **Configurar**, selecione **Contas de cliente de transportadora**.
1. Na página **Contas de cliente de transportadora**, no Painel de Ações, selecione **Novo** para adicionar uma conta à grade.
1. Defina os seguintes valores para a nova conta:

    - **Transportadora:** *Transportadora de demonstração*
    - **Número da conta de cliente de transportadora:** *12345* (O valor não é importante para este cenário, mas ele será referenciado na próxima seção.)

### <a name="go-through-the-example-scenario"></a>Executar o cenário de exemplo

Depois de configurar todos os dados de exemplo conforme descrito na seção anterior, você estará pronto para executar o cenário de exemplo.

#### <a name="create-a-sales-order-and-process-the-work"></a>Criar uma ordem de venda e processar o trabalho

Siga estas etapas para criar uma ordem de venda.

1. Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. Selecione **Novo** para criar uma ordem de venda.
1. Na caixa de diálogo **Criar ordem de venda**, defina o campo **Conta de cliente** como *US-027*.
1. Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo.
1. A nova ordem de venda é aberta. Na FastTab **Cabeçalho da ordem de venda**, defina o campo **Número da conta de cliente de transportadora** como o valor que você selecionou para esse cliente anteriormente (*12345*).
1. Na seção **Linhas da ordem de venda**, adicione uma linha de venda e defina os seguintes valores para ela:

    - **Número de item:** *A0002*
    - **Quantidade:** *1*
    - **Local:** *6*
    - **Depósito:** *62*

1. Alterne para a exibição do **Cabeçalho**.
1. Na FastTab **Entrega**, defina os seguintes valores:

    - **Transportadora:** *Transportadora de demonstração*
    - **Serviço de transportadora:** *Serviço de transportadora de demonstração*

1. Alterne novamente para a exibição **Linhas**. Se for solicitada a atualização do modo de entrega para as linhas de venda, selecione **Sim**.
1. Na seção **Linhas da ordem de venda**, selecione a linha da ordem que você configurou anteriormente e, em seguida, selecione **Estoque \> Reserva**.
1. Na página **Reserva**, selecione **Reservar lote** para reservar a quantidade total da linha selecionada no depósito.
1. Feche a página **Reserva** para retornar à ordem de venda.
1. No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**.

    O trabalho é criado para mover itens do local de separação para a estação de embalagem.

1. Na seção **Linhas da ordem de venda**, selecione **Depósito \> Detalhes da remessa**.
1. Na página **Detalhes da remessa**, anote a ID da remessa. Você precisará dela ao embalar a remessa na estação de embalagem.
1. Feche a página **Detalhes da remessa** para retornar à ordem de venda.
1. Anote o número da ordem de venda e, em seguida, vá para **Gerenciamento de depósito \> Trabalho \> Todos os trabalhos**.
1. Use o número da ordem de venda para localizar e selecionar o trabalho criado para a ordem.
1. No Painel de Ações, na guia **Trabalho**, selecione **Concluir trabalho**.
1. Na página **Conclusão do trabalho**, no campo **ID de Usuário**, selecione uma ID de usuário. Em seguida, no Painel de Ações, selecione **Validar trabalho**.
1. Se o trabalho for aprovado na validação, selecione **Concluir trabalho** no Painel de Ações.

    O trabalho é marcado como concluído para simular a movimentação de itens para a estação de embalagem.

#### <a name="pack-the-shipment"></a>Embalar a remessa

Siga estas etapas para embalar a remessa.

1. Vá para **Gerenciamento de depósito \> Configuração \> Trabalhador** e verifique se a sua conta de usuário está associada a uma conta de trabalhador para gerenciamento de depósito.
1. Vá para **Gerenciamento de depósito \> Separação e transporte em contêineres \> Embalar**.
1. Na caixa de diálogo **Selecionar estação de embalagem**, defina os seguintes valores:

    - **Local:** *6*
    - **Depósito:** *62*
    - **Local:** *Embalar*
    - **ID do perfil de embalagem:** *Perfil de embalagem de demonstração*

1. Selecione **OK**.
1. A página **Embalar** será exibida. Em um cenário de produção, um trabalhador verificará uma placa de licença ou uma ID de remessa. No entanto, para este cenário, abra a página **Todas as remessas** e procure o número da remessa que você acabou de criar. Em seguida, insira esse valor no campo **Placa de licença ou remessa** na página **Embalar**. Como alternativa, insira a ID de remessa que você anotou anteriormente.
1. No Painel de Ação, selecione **Novo contêiner**.
1. A caixa de diálogo exibida mostra detalhes sobre o novo contêiner. Mantenha os valores padrão e selecione **OK**.
1. Na página **Embalar**, na FastTab **Embalagem de item**, no campo **Identificador**, selecione *A0002* para embalar o item. O item é adicionado ao contêiner.
1. No Painel de Ações, selecione **Contêineres para remessa**.

    A página **Contêineres para remessa** exibida tem uma linha para o contêiner que você acabou de criar. No entanto, o campo **ID de manifesto de contêiner** nessa linha está em branco no momento, pois você ainda não recebeu a etiqueta de remessa e o número de rastreamento da transportadora.

1. No Painel de Ação, selecione **Fechar contêiner**.
1. Na caixa de diálogo **Fechar contêiner**, defina o campo **Peso bruto** como *1 kg* e, em seguida, selecione **OK**.

    A etiqueta de remessa será impressa agora na impressora ZPL selecionada anteriormente. Ela deve se assemelhar ao seguinte exemplo.

    ![Exemplo de etiqueta de remessa](media/sps-label-example.png "Exemplo de etiqueta de remessa")

1. Observe que os valores **ID de manifesto de contêiner** e **Frete total** foram adicionados como recebidos da transportadora.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]