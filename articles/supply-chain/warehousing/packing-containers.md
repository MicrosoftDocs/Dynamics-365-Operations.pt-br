---
title: Embalar contêineres para remessa
description: Este artigo descreve o processo de embalagem que permite que você valide itens de estoque e os embale em contêineres.
author: perlynne
ms.date: 7/13/2022
ms.topic: business-process
ms.search.form: WHSLocationType, WHSLocationProfile, WHSParameters, WHSContainerType, WHSPackProfile, WHSCloseContainerProfile, InventLocationIdLookup, UnitOfMeasureLookup, WHSPack, WHSContainerTable,
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 171b9f1dcb1d4ece63bc0beeb71f45b9f8ae7bba
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220517"
---
# <a name="pack-containers-for-shipment"></a>Embalar contêineres para remessa

[!include [banner](../../includes/banner.md)]

O processo de embalagem de contêiner permite que você valide itens de estoque e os embale em contêineres. Durante esse processo, os trabalhadores de depósito normalmente separam itens de estoque de áreas de armazenamento em massa e os movem para uma área de embalagem. Nesse ponto, vários trabalhadores de depósito verificam as quantidades e os tipos de itens e os atribuem a tamanhos de contêiner apropriados. Quando um contêiner é embalado totalmente, é fechado e transferido para a área de doca de saída onde é preparado para remessa.

Os contêineres representam as estruturas físicas nas quais os itens são reembalados, e você pode rastrear as informações do contêiner no sistema. Essas informações podem ser úteis durante o planejamento de transporte, especialmente se você calcular os encargos de remessa com base nos contêineres. Antes de enviar, você pode exibir o número de contêineres usados em uma remessa, os tipos de contêineres usados e as dimensões físicas de cada contêiner (como volume total e peso).

Vários recursos relacionados ao depósito de saída podem ser usados com contêineres. Para obter mais informações, consulte os seguintes artigos:

- [Conteinerização em ciclos](wave-containerization.md)
- [Classificação de saída](outbound-sorting.md)
- [Remessa de pacotes pequenos](small-parcel-shipping.md)
- [Confirmar e transferir](confirm-and-transfer.md)
- [Definir dimensões diferentes para embalagem e armazenamento](packing-vs-storage-dimensions.md)
- [Trabalho de embalagem para empacotar contêineres de saída e processar remessas](packing-work.md)
<!-- KFM: Add link to upcoming topic when available (10.0.31): [Manual packing on the Warehouse management mobile app](manual-packing-on-the-warehouse-management-mobile-app.md) -->

## <a name="set-up-your-warehouse-to-use-manual-packing-operations"></a>Configurar seu depósito para usar operações de embalagem manual

Há duas maneiras básicas de organizar suas operações de saída:

- **Criação e processamento em ciclos** – os trabalhadores separam itens com base no trabalho de depósito de saída. Em seguida, eles colocam os itens diretamente em uma localização de remessa de saída, onde estão prontos para a remessa imediata. Para obter informações sobre como configurar e usar esse processo, consulte [Criação e processamento em ciclos](wave-processing.md).
- **Embalagem manual em estações de embalagem** – esse processo tem uma operação adicional entre as operações de separação e remessa. Em vez de colocar o estoque em uma *localização de remessa do baydoor*, os funcionários o colocam em uma *localização de embalagem*. Em seguida, eles gerenciam o processo de embalagem na estação de embalagem usando a página **Embalar** no cliente Web. Para habilitar este processo, você deve configurar o sistema conforme descrito nesta seção.

### <a name="set-up-warehouse-locations-for-packing"></a>Configurar os locais de depósito para embalagem

Você deve ter pelo menos uma localização de embalagem em que os funcionários colocarão itens de estoque para que possam ser embalados em contêineres. Para obter mais informações sobre como criar locais de depósito, consulte [Configurar localizações em um depósito habilitado para WMS](tasks\configure-locations-wms-enabled-warehouse.md). As subseções a seguir descrevem como criar e configurar localizações de embalagem.

#### <a name="set-up-location-types-for-packing"></a>Configurar tipos de localização para embalagem

Você deve definir um *tipo de localização* para as localizações de embalagem. Os tipos de localização podem ser utilizados como opções de filtragem para controlar os diferentes processos de gerenciamento de depósito. O nome de cada tipo de localização normalmente descreve algo sobre como esse tipo de localização deve ser usado. O tipo de localização configurado aqui deve estar associado a cada localização usada para operações de embalagem.

Siga estas etapas para configurar um tipo de localização.

1. Acesse **Gerenciamento de depósito \> Configuração \> Depósito \> Tipos de localização**.
1. No Painel de Ações, selecione **Novo** para adicionar um tipo de localização à grade.
1. Defina os seguintes campos para o novo tipo de localização:

    - **Tipo de localização** – informe um nome para o tipo de localização. Cada nome deve ser exclusivo e deve descrever algo sobre como o tipo de localização deve ser usado.
    - **Descrição** – insira uma breve descrição do tipo de localização.

#### <a name="inform-the-system-about-the-packing-location-type"></a>Informar o sistema sobre o tipo de local de embalagem

Depois de criar um tipo de localização, você deve configurar o sistema para reconhecê-lo como o tipo de localização a ser usado para operações de embalagem.

Siga estas etapas para definir o tipo de localização usado para operações de embalagem.

1. Acesse **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**
2. Na guia **Geral**, **Tipos de localização**, defina o campo **Tipo de localização de embalagem** como o tipo de localização que será usado para identificar as estações de embalagem.

> [!NOTE]
> Se você estiver atualizando de uma versão do Microsoft Dynamics AX, o status *Embalagem* foi removido de remessas e cargas, pois ele não funcionou de modo consistente e gerou dados redundantes. Portanto, as páginas de lista **Em remessas** e **Cargas na embalagem** foram preteridas. Os contêineres que devem ser embalados são rastreados no nível da localização.
>
> Em versões anteriores, você definia a localização de embalagem usando o campo **ID do perfil para localização de embalagem** na guia **Embalagem** da página **Parâmetros de gerenciamento de depósito** para especificar um *perfil de localização*. Na versão atual, use o campo **Tipo de localização de embalagem** na guia **Geral** da página **Parâmetros de gerenciamento de depósito** para especificar um *tipo de localização*, conforme descrito neste artigo. O novo campo é mais bem alinhado com o processo de identificação dos locais de preparo e das localizações de remessa finais.
>
> Embora você possa continuar a usar o campo **IDo do perfil para localização de embalagem**, recomendamos que você comece a usar o novo campo **Tipo de localização de embalagem**, porque o campo antigo será preterido.
>
> Se você desmarcar a configuração do antigo campo **ID do perfil para localização de embalagem** e salvar a página, o campo será desativado permanentemente. Em instalações em que o campo **ID do perfil para localização de embalagem** nunca foi usado, ele sempre estará desativado. Depois de desmarcar a configuração do campo **ID do perfil para localização de embalagem**, use as configurações descritas neste artigo para configurar e identificar a localização de embalagem.

#### <a name="set-up-location-profiles-for-packing-locations"></a>Configurar perfis para localizações de embalagem

Cada *perfil de localização* estabelece informações e regras que se aplicam às localizações associadas. Como você precisa de pelo menos uma localização a ser usada para operações de embalagem, é necessário criar um perfil de localização para ela além de um tipo de localização. Cada perfil pode ser usado por qualquer número de localizações. As localizações usadas para a embalagem devem ser configuradas para rastrear placas de licença.

Siga estas etapas para configurar um perfil de localização para uma localização de embalagem.

1. Acesse **Gerenciamento de depósito \> Configuração \> Depósito \> Perfis de localização**.
1. Selecione um perfil existente no painel de lista ou selecione **Novo** no Painel de Ações para criar um.
1. No cabeçalho do perfil novo ou selecionado, defina os seguintes campos:

    - **ID do perfil de localização** – insira um ID exclusivo para o perfil.
    - **Nome** – insira um nome descritivo para o perfil.

1. Na Guia Rápida **Geral**, defina os seguintes campos:

    - **Formato da localização** – selecione o formato de localização a ser usado para a localização atual. Formatos de localização são um sistema de nomenclatura utilizado para criar nomes únicos e consistentes para as diferentes localizações dos compartimentos usados em um depósito. Se você ainda não tiver o formato necessário, poderá criá-lo acessando **Gerenciamento de depósito \> Configuração \> Depósito \> Formatos de localização**. Para obter mais informações, consulte [Configurar localizações em um depósito habilitado para WMS](tasks/configure-locations-wms-enabled-warehouse.md).
    - **Tipo de localização** – selecione o tipo configurado como o tipo de localização de embalagem na página **Parâmetros de gerenciamento de depósito**, conforme descrito anteriormente neste artigo.
    - **Usar rastreamento da placa de licença** – para localizações de embalagem, defina esta opção como *Sim*. O sistema deve ser capaz de rastrear IDs de placa de licença em locais de embalagem, de forma que possa controlar o processo de embalagem.
    - **Permitir estoque negativo** – para locais de embalagem, defina essa opção como *Não*.
    - **Permitir itens mistos** – para locais de embalagem, defina esta opção como *Sim*. Essa configuração é necessária porque vários números de item diferentes normalmente são trazidos de forma simultânea para as localizações de embalagem.
    - **Permitir status de estoque mistos** – para locais de embalagem, defina essa opção como *Sim*. Essa configuração é necessária porque itens com diferentes status de estoque normalmente são trazidos de forma simultânea para as localizações de embalagem.
    - **Permitir lotes de estoque mistos** – para locais de embalagem, defina essa opção como *Sim*. Essa opção é definida automaticamente como *Sim* sempre que a opção **Permitir itens mistos** é definida como *Sim*.

#### <a name="set-up-packing-locations"></a>Configurar localizações de embalagem

Você deve ter pelo menos uma *localização* em que os funcionários colocarão itens de estoque que devem ser embalados em contêineres.

Siga estas etapas para adicionar uma localização de embalagem.

1. Acesse **Gerenciamento de depósito \> Configuração \> Depósito \> Localizações**.
1. No Painel de Ações, selecione **Novo** para adicionar uma localização.
1. Defina os seguintes campos para a nova localização:

    - **Depósito** – especifique o depósito onde a localização de embalagem deve existir.
    - **Localização** – forneça um nome para a nova localização.
    - **ID do perfil de localização** – especifique o ID que você criou na seção anterior.

## <a name="set-up-the-packing-process"></a>Configurar o processo de embalagem

Esta seção descreve como definir as configurações que ativam o processo de embalagem e permitem que os funcionários embalem o estoque em contêineres.

### <a name="set-up-container-packing-policies"></a><a name="packing-policy"></a>Configurar políticas de embalagem de contêiner

Cada *política de embalagem de contêiner* define como um contêiner deve ser processado. Toda vez que você criar um contêiner, também será possível selecionar uma política de embalagem de contêiner a ser aplicada.

Siga estas etapas para configurar uma política de embalagem de contêiner.

1. Acesse **Gerenciamento de depósito \> Configuração \> Contêineres \> Políticas de embalagem de contêiner**.
1. Selecione uma política existente no painel de lista ou selecione **Novo** no Painel de Ações para criar uma.
1. No cabeçalho da política nova ou selecionada, defina os seguintes campos:

    - **Política de embalagem de contêiner** – forneça um nome exclusivo para a política.
    - **Descrição** – forneça um nome descritivo para a política.

1. Na guia **Visão geral**, defina os campos a seguir. Esses campos permitem que você especifique quais ações devem ser executadas quando o contêiner é fechado, se é necessário operar com ou sem a criação de trabalho e quando o contêiner deve ser liberado da estação de embalagem.

    - **Depósito** – selecione o depósito ao qual a política de embalagem é aplicável.
    - **Localização padrão para remessa final** – especifique a localização preferencial para o contêiner depois de fechá-lo. Esse campo está disponível somente quando o campo **Política de liberação de contêiner** está definido como *Disponibilizar na localização de remessa final*.
    - **Localização padrão para classificação** – esse campo é usado com o recurso [classificação de saída](outbound-sorting.md).
    - **Unidade de peso** – selecione a unidade de medida padrão a ser usada quando um contêiner é fechado e manifestado. Normalmente, essa unidade de medida será a unidade usada por uma escala na estação de embalagem. Esse campo é aplicável a políticas com ou sem a criação de trabalho.
    - **Política de fechamento de contêiner** – selecione uma das seguintes opções para definir o que deve ocorrer quando o contêiner é fechado:

        - *Liberação automática* – o contêiner será considerado liberado da estação de embalagem, e a ação especificada no campo **Política de liberação de contêiner** será acionada.
        - *Liberação em atraso* – o contêiner não será liberado imediatamente da estação de embalagem. Um trabalhador do depósito deverá liberá-lo manualmente mais tarde.
        - *Opcional* – enquanto um trabalhador está fechando o contêiner, ele poderá escolher se o contêiner deve ser liberado.

        Se a estação de embalagem trata principalmente de contêineres que são enviados diretamente aos clientes, a abordagem mais natural é liberar os contêineres imediatamente. Se a estação de remessa processa remessas que consistem em vários contêineres ou até paletes, provavelmente será melhor atrasar a liberação até que toda a remessa ou o palete tenha sido embalado e pronto para retirada.

    - **Política de liberação de contêiner** – selecione uma das seguintes opções para definir o que deve ocorrer quando o contêiner é liberado da localização de embalagem:

        - *Disponibilizar na localização de remessa final* – atualiza o contêiner para o local de remessa final. Se você selecionar essa opção, use o campo **Localização padrão para remessa final** para especificar uma localização preferencial para o contêiner depois de fechá-lo.
        - *Criar trabalho para mover contêiner da estação de embalagem* – crie trabalho para mover o contêiner da estação de embalagem para a área de preparo ou diretamente para o baydoor. Use o campo **Modelo do trabalho** para especificar o modelo do trabalho que deve ser aplicado quando o trabalho é criado para o contêiner.
        - *Atribuir contêiner para a posição de classificação de saída* – essa opção é usada com o recurso [classificação de saída](outbound-sorting.md).

        Na maioria dos casos, recomendamos que você crie trabalho para mover contêineres, porque essa abordagem representa melhor os processos manuais reais no depósito. No entanto, para cenários simples ou situações em que a estação de embalagem está localizada diretamente na área do baydoor, pode ser preferível que o contêiner fique imediatamente disponível na localização de remessa final.

    - **Modelo do trabalho** – selecione o modelo do trabalho que deve ser aplicado quando o trabalho é criado para o contêiner. Esse campo está disponível somente quando o campo **Política de liberação de contêiner** está definido como *Criar trabalho para mover contêiner da estação de embalagem* e está relacionado a um tipo de ordem de serviço chamado *Separação de contêineres embalados*. Para obter mais informações, consulte [Modelos de trabalho e diretivas de localização](control-warehouse-location-directives.md).

    Nas etapas restantes, você vai definir as configurações relacionadas ao *manifesto*. Manifesto é o processo de especificação do peso de um contêiner, grupo de contêineres ou remessa, com o ID de rastreamento recebido de um fornecedor de transporte. O Dynamics 365 Supply Chain Management não se integra com sistemas de fornecedores de transporte externos. Em vez disso, os trabalhadores de depósito devem imprimir rótulos recebidos do fornecedor de transporte e, depois, digitalizar um número de rastreamento ao concluir o procedimento de manifesto.

    Como os requisitos de manifesto variam de cliente para cliente e mesmo de remessa para remessa, as políticas de embalagem permitem uma flexibilidade significativa no fluxo de trabalho. Você pode configurar os manifestos para contêineres, grupos de contêineres e remessas em qualquer combinação.

    Se você estiver usando um procedimento de manifesto de vários níveis, os funcionários deverão manifestar todos os contêineres antes de manifestar o grupo de contêineres relacionado e devem manifestar todos os grupos de contêineres antes de manifestar a remessa relacionada.

1. Na guia rápida **Manifesto de contêiner**, defina os seguintes campos:

    - **Manifesto automático no fechamento do contêiner** – defina essa opção como *Sim* para aplicar informações de manifesto como parte do processo de fechamento do contêiner. Se você não estiver usando a integração de transporte, as informações deverão ser registradas manualmente.
    - **Requisitos de manifesto para contêiner** – selecione uma das seguintes opções:

        - *Nenhum* – nenhum processo de manifesto será usado.
        - *Manual* – o manifesto será necessário para o fluxo de trabalho de embalagem. O sistema não permite que um contêiner seja fechado nem liberado até que o manifesto seja concluído.
        - *Gerenciamento de transporte* – o manifesto será realizado por meio dos mecanismos de taxa de Gerenciamento de transporte (TMS). Como essa opção requer desenvolvimento personalizado para implementar um mecanismo específico para o fornecedor de transporte, ela não é predefinida na versão atual.

    - **Imprimir conteúdo do contêiner** – defina essa opção como *Sim* para imprimir automaticamente o relatório de conteúdo do contêiner quando um contêiner for registrado como fechado. O relatório também pode ser impresso sob demanda.

1. Na guia rápida **Manifesto do grupo de contêineres**, no campo **Requisitos de manifesto para grupo de contêineres**, selecione uma das seguintes opções:

    - *Nenhum* – o manifesto do grupo de contêineres não será incluído como um requisito no fluxo de trabalho de embalagem.
    - *Manual* – o manifesto do grupo de contêineres será incluído como um requisito no fluxo de trabalho de embalagem. Todos os contêineres incluídos no grupo devem ser fechados para o grupo ser manifestado. Selecione essa opção se for necessário concluir um manifesto para cada grupo de contêineres embalado na estação de embalagem. Normalmente, você selecionará esta opção se os contêineres estiverem embalados em um palete e o palete inteiro for manifestado.

    > [!NOTE]
    > A versão atual não é compatível com relatórios de manifesto para grupos de contêineres e não há suporte para o mecanismo de TMS para grupos de contêineres.

1. Na guia rápida **Manifesto de remessa**, defina os seguintes campos:

    - **Requisitos de manifesto para remessa** – selecione uma das seguintes opções:

        - *Nenhum* – o manifesto da remessa não será incluído como um requisito no fluxo de trabalho de embalagem.
        - *Manual* – o manifesto da remessa será incluído como um requisito no fluxo de trabalho de embalagem. Nenhum contêiner de uma remessa pode ser liberado até que o manifesto seja concluído.
        - *Gerenciamento de transporte* – o manifesto será feito por meio de mecanismos de taxa de TMS. Como essa opção requer desenvolvimento personalizado para implementar um mecanismo específico para o fornecedor de transporte, ela não é predefinida na versão atual.

        O manifesto de remessa deverá ser ativado se for necessário concluir um manifesto para toda a remessa embalada na estação de embalagem. Em geral, é usado quando um manifesto consolidado é necessário, embora a remessa seja formada por vários contêineres ou grupos de contêineres.

    - **Imprimir guia de remessa** – defina essa opção como *Sim* para imprimir automaticamente a guia de remessa como parte do manifesto da remessa. A guia de remessa também pode ser impressa sob demanda.

### <a name="set-up-container-types"></a>Configure tipos de contêiner

Durante o processo de embalagem manual, os contêineres devem ser criados para que os itens possam ser incluídos neles. Cada contêiner deve ser baseado em um *tipo de contêiner*, que define o volume físico máximo do contêiner e a capacidade de peso.

Siga estas etapas para criar um tipo de contêiner.

1. Acesse **Gerenciamento de depósito \> Configuração \> Contêineres \> Tipos de contêiner**.
1. No Painel de Ações, selecione **Novo** para adicionar um tipo de contêiner.
1. Defina os seguintes campos para o novo tipo de contêiner:

    - **Código do tipo de contêiner** – insira um ID exclusivo para o tipo de contêiner.
    - **Descrição** – insira uma descrição do novo tipo de contêiner.
    - **Tara** – insira o peso real ou previsto do contêiner.
    - **Peso líquido máximo** – insira o peso máximo que o contêiner pode ter.

1. Na seção **Dimensões do contêiner**, nos campos **Comprimento**, **Largura**, **Altura** e **Volume**, insira as dimensões físicas do próprio contêiner.
1. Na seção **Valores máximos**, nos campos **Comprimento**, **Largura**, **Altura** e **Volume**, insira as dimensões físicas máximas que o contêiner pode suportar.
1. Você pode definir atributos adicionais para tipos de contêiner associados a outras operações que usam contêineres. Para obter mais informações, consulte [Conteinerização](wave-containerization.md).

> [!NOTE]
> Para o processo de embalagem manual, o sistema usa somente o valor do campo **Peso líquido máximo** e o valor do campo **Volume** na seção **Valores máximos**.

### <a name="set-up-packing-profiles"></a>Configurar perfis de embalagem

Os *perfis de embalagem* são obrigatórios para o processo de embalagem. Eles podem ser selecionados ou definidos por padrão quando você inicia uma operação de embalagem na página **Embalar**.

Siga estas etapas para configurar um perfil de embalagem.

1. Acesse **Gerenciamento de depósito \> Configuração \> Embalagem \> Perfis de embalagem**.
1. Selecione um perfil existente no painel de lista ou selecione **Novo** no Painel de Ações para criar um.
1. No cabeçalho do perfil novo ou selecionado, defina os seguintes campos:

    - **ID do perfil de embalagem** – insira um ID curto para o perfil.
    - **Descrição** – insira uma descrição do perfil de embalagem.
    - **Política de embalagem de contêiner** – selecione a política de embalagem aplicável ao perfil. Para obter mais informações, consulte a seção [Configurar políticas de embalagem de contêiner](#packing-policy) deste artigo.
    - **Modo de ID do contêiner** – determine se um ID de contêiner deve ser gerado automaticamente quando um contêiner é criado ou se ele deve ser criado manualmente.
    - **Tipo de contêiner** – selecione o tipo de contêiner usado por padrão quando um contêiner é criado.
    - **Criar automaticamente contêiner no fechamento do contêiner** – marque essa caixa de seleção para criar automaticamente um contêiner se o contêiner anterior for fechado e uma ou mais linhas permanecerem na remessa atual.

### <a name="set-up-warehouse-workers"></a>Configurar trabalhadores de depósito

Cada usuário ou trabalhador que embala os contêineres usando a página **Embalar** do cliente Web ou o código de atividade *Embalar* no aplicativo móvel Warehouse Management deve ter uma conta de usuário associada a um registro de *trabalhador/pessoa* ao qual os direitos de acesso de segurança necessários são atribuídos. (Para obter mais informações sobre como configurar usuários, consulte [Criar usuários](../../fin-ops-core/dev-itpro/sysadmin/tasks/create-new-users.md).)

Siga estas etapas para configurar um registro de *trabalhador/pessoa* para o processo de embalagem.

1. Acesse **Gerenciamento de depósito \> Configuração \> Trabalhador**.
1. No Painel de Ações, selecione **Novo** para adicionar um usuário de trabalho.
1. Defina o campo **Trabalhador** como o registro de trabalhador existente definido no módulo **Recursos humanos** para o usuário que concluirá o processo de embalagem.
1. Na Guia Rápida **Perfil**, defina os seguintes campos:

    - **Política de embalagem de contêiner** — selecione uma política de embalagem de contêiner que define como os contêineres na estação de embalagem devem ser processados. A política de embalagem de contêiner selecionada será selecionada previamente para o trabalhador quando ele abrir a estação de embalagem. Para obter mais informações, consulte a seguinte publicação no blog: [Funcionalidade de embalagem aprimorada](https://cloudblogs.microsoft.com/dynamics365/no-audience/2016/12/01/improved-packing-functionality-dynamics-365-for-operations-1611).
    - **ID do perfil de embalagem** — selecione um ID do perfil de embalagem que defina as configurações da política de embalagem e do contêiner que deverão ser usadas. Se o ID do perfil de embalagem selecionado estiver associado a uma política de embalagem de contêiner, você não poderá alterar a configuração do campo **Política de embalagem de contêiner** nessa página.

1. Na guia rápida estação **Estação de embalagem padrão**, selecione o site, o depósito e a localização padrão que se aplicam ao trabalhador.
1. Se o trabalhador usar o aplicativo móvel Warehouse Management para gerenciar e registrar seu trabalho de embalagem do contêiner, na guia rápida **Usuários**, configure uma ou mais contas que o trabalhador pode usar para fazer login no aplicativo. Para obter mais informações, consulte [Contas de usuário de dispositivo móvel](mobile-device-work-users.md).

## <a name="example-scenario"></a><a name="scenario"></a>Cenário de exemplo

Esta seção fornece um cenário de exemplo que mostra como criar uma ordem e embalar os itens.

### <a name="make-sample-data-available"></a>Disponibilizar dados de exemplo

Para trabalhar nesse cenário usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/fin-ops/get-started/demo-data.md) padrão estejam instalados. Além disso, você deve selecionar a entidade legal **USMF** antes de começar.

Você também pode usar este cenário como orientação para usar o recurso em um sistema de produção. No entanto, nesse caso, você deve substituir seus valores por cada configuração descrita aqui.

### <a name="sign-in-as-a-user-that-can-do-packing-work"></a>Faça login como um usuário que pode fazer o trabalho de embalagem

Faça login no Supply Chain Management usando uma conta de usuário que tenha as permissões necessárias para embalar contêineres. O usuário *Julia Funderburk* é incluído como parte dos dados de demonstração e tem as permissões necessárias. Esse usuário tem o ID de usuário *Administrador*.

### <a name="create-a-sales-order-and-complete-the-work"></a>Criar uma ordem de venda e concluir o trabalho

Siga estas etapas para criar uma ordem de venda e concluir o trabalho de mover os itens encomendados para a estação de embalagem.

1. Acesse **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. No Painel de Ações, selecione **Novo**.
1. Na caixa de diálogo **Criar ordem de venda**, no campo **Conta do cliente**, selecione *US-005*.
1. Selecione **OK** para fechar a caixa de diálogo.
1. A nova ordem de venda é aberta e inclui uma única linha vazia na guia rápida **Linhas da ordem de venda**. Defina os seguintes valores para a nova linha de ordem:

    - **Número de item:** *A0001*
    - **Quantidade:** *2*
    - **Local:** *6*
    - **Depósito:** *62*

1. Com a linha da ordem ainda selecionada, selecione **Estoque \> Reserva** na barra de ferramentas da guia rápida **Linhas da ordem de venda**.
1. Na página **Reserva**, no Painel de Ações, selecione **Reservar lote** para reservar a quantidade total da linha selecionada no depósito.
1. Feche a página **Reserva** para retornar à ordem de venda.
1. No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**.

    Uma mensagem mostra os IDs de remessa e de ciclo da ordem.

1. Com a linha da ordem ainda selecionada, selecione **Depósito** \> **Detalhes do trabalho** na barra de ferramentas da guia rápida **Linhas da ordem de venda**. Se você usar o processamento em lotes para executar os ciclos, talvez seja necessário aguardar um curto período para que o trabalho seja criado.
1. Na página **Trabalho**, no Painel de Ações, na guia **Trabalho**, selecione **Concluir trabalho**.
1. Na página **Conclusão do trabalho**, defina o campo **ID do usuário** como *62*.
1. No Painel de Ações, selecione **Validar trabalho**.
1. Ao receber uma mensagem que indica que o seu trabalho é válido, selecione **Concluir trabalho** para concluir o processo de separação dos itens de estoque e colocá-los na localização *Embalar*.
1. Anote o valor **ID da remessa** mostrado para o trabalho na grade superior.

### <a name="pack-the-ordered-items-into-a-container"></a>Embalar os itens encomendados em um contêiner

Os itens de estoque agora foram trazidos para a área de embalagem e estão prontos para serem incluídos em contêineres. Siga estas etapas para criar um contêiner no sistema e embalá-lo.

1. Acesse **Gerenciamento de depósito \> Remessa e transporte em contêineres \> Embalar**.
1. Na caixa de diálogo **Selecionar estação de embalagem**, defina os seguintes valores:

    - **Local:** *6*
    - **Depósito:** *62*
    - **Local:** *Embalar*
    - **ID do perfil da embalagem:** *WH62*

1. Selecione **OK**.
1. Na página **Embalar**, no campo **Placa de licença ou remessa**, insira o ID da remessa que você anotou anteriormente. Agora, você deve ver os itens desembalados restantes na guia rápida **Linhas em aberto**.
1. No Painel de Ações, selecione **Novo contêiner** para criar um contêiner no sistema.
1. Na caixa de diálogo **ID do novo contêiner**, defina o campo **Tipo de contêiner** como *SmallBox*.
1. Selecione **OK** para criar o contêiner.
1. Selecione **OK** para retornar à página **Embalar**. A guia rápida **Abrir contêineres** agora mostra o valor **ID do contêiner** do contêiner que você criou.
1. Neste cenário, você embalará apenas um dos itens encomendados por enquanto. Dessa forma, na guia rápida **Embalagem de item**, defina os seguintes valores:

    - **Quantidade:** *1.00*
    - **Identificador:** *A0001*

    Logo após selecionar o valor **Identificador**, a página atualizará as guias rápidas **Linhas em aberto** e **Todas as linhas** para indicar que um item foi embalado. Agora, você deve ter embalado uma das duas partes do item *A0001*.

1. No Painel de Ação, selecione **Fechar contêiner**.
1. Na caixa de diálogo **Fechar contêiner**, selecione **Obter peso do sistema** para preencher o valor **Peso bruto** padrão.
1. Selecione **OK** para fechar o contêiner.

> [!TIP]
> Há várias maneiras de exibir contêineres com base no contexto. Por exemplo, ao embalar uma remessa, geralmente é útil exibir os contêineres que fazem parte da remessa ou todos os contêineres que estão fisicamente em uma estação de embalagem. A página **Estação de embalagem** tem botões que podem ser usados para exibir todos os contêineres abertos e fechados em uma estação de embalagem. Essas exibições não são restritas a uma remessa específica. Elas podem ser muito úteis em situações nas quais um trabalhador está embalando um contêiner e outro trabalhador está manifestando e liberando o contêiner.
>
> Também está disponível uma exibição consolidada de todos os contêineres. Esse modo de exibição é útil principalmente para usuários que trabalham fora do contexto de uma única estação de embalagem. Para vê-lo, acesse **Gerenciamento de depósito \> Embalagem e conteinerização \> Contêineres**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
