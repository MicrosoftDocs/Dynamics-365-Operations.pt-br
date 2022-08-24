---
title: Trabalho de embalagem para empacotar contêineres de saída e processar remessas
description: Este artigo descreve o tipo de ordem de serviço "Embalagem", que gerencia o trabalho de embalar contêineres e dá suporte a remessas parciais de contêineres embalados relacionados a cargas em que os itens de estoque permanecem desembalados.
author: perlynne
ms.date: 7/13/2022
ms.topic: article
ms.search.form: WHSPackingWorkLocationSetup, WHSPack, WHSContainerTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 34a7087df7e7768d0012ea4f534aa109654af8fa
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/02/2022
ms.locfileid: "9220515"
---
# <a name="packing-work-for-packing-outbound-containers-and-processing-shipments"></a>Trabalho de embalagem para empacotar contêineres de saída e processar remessas

[!include [banner](../../includes/banner.md)]

Este artigo descreve o tipo de ordem de serviço *Embalagem*, que gerencia o trabalho de embalar contêineres e dá suporte a remessas parciais de contêineres embalados relacionados a cargas em que os itens de estoque permanecem desembalados. O trabalho de embalagem permite usar o recurso [confirmar e transferir](confirm-and-transfer.md) para confirmar remessas de saída associadas a contêineres.

O trabalho de embalagem é criado automaticamente quando o estoque relacionado ao trabalho de documento de origem é colocado em localizações do tipo *Localização de embalagem*. O trabalho consiste em duas linhas, uma para *Separação* e outra para *Colocação* e é automaticamente mantido como parte de um processo de fechamento/reabertura do contêiner.

Para obter mais informações sobre como configurar e usar o processo de embalagem do contêiner, consulte [Embalar contêineres para remessa](packing-containers.md).

## <a name="turn-on-the-feature"></a>Ativar o recurso

Se o sistema ainda não incluir os recursos descritos neste artigo, acesse [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative os seguintes recursos nesta ordem. Os dois recursos fazem parte do módulo **Gerenciamento de depósito**.

1. *Confirmar e transferir*
1. *Trabalho de embalagem para estações de embalagem*

## <a name="set-up-a-location-for-packing-work"></a>Configurar uma localização para o trabalho de embalagem

Use o procedimento a seguir para configurar localizações de embalagem. Para cada localização, você pode selecionar se o sistema criará automaticamente o trabalho de embalagem.

1. Acesse **Gerenciamento de depósito \> Configuração \> Embalagem \> Configuração de estação de embalagem**.
1. No Painel de Ações, selecione **Novo** para adicionar um registro de configuração de estação de embalagem.
1. No novo registro, defina os seguintes campos:

    - **Depósito** – selecione ou insira o depósito onde está a localização de embalagem.
    - **Localização** – selecione ou insira a localização de embalagem. Essa localização deve ser atribuída a um perfil que use o tipo que está configurado como o tipo de localização de embalagem de sua empresa na página **Parâmetros de gerenciamento de depósito**. Para obter mais informações, consulte [Embalar contêineres para remessa](packing-containers.md).
    - **Criar trabalho de embalagem** – marque essa caixa de seleção para criar um trabalho de remessa sempre que os itens forem entregues ao local de embalagem. O trabalho incluirá links para linhas de carregamento relacionadas, de forma que as cargas parciais possam ser embaladas e enviadas.

## <a name="example-scenario"></a>Cenário de exemplo

Este cenário de exemplo mostra como processar um fluxo de ordem de venda de saída, embalando um contêiner e enviando uma carga parcial.

### <a name="make-sample-data-available"></a>Disponibilizar dados de exemplo

Para trabalhar nesse cenário usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/fin-ops/get-started/demo-data.md) padrão estejam instalados. Além disso, você deve selecionar a entidade legal **USMF** antes de começar.

Você também pode usar este cenário como orientação para usar o recurso em um sistema de produção. No entanto, nesse caso, você deve substituir seus valores por cada configuração descrita aqui.

### <a name="configure-packing-work-for-warehouse-packing-location"></a>Configurar trabalho de embalagem para localização de embalagem de depósito

Para começar, você deve configurar o processo de trabalho *Embalagem* para um depósito e localização específicos.

1. Acesse **Gerenciamento de depósito \> Configuração \> Embalagem \> Configuração de estação de embalagem**.
1. No Painel de Ações, selecione **Novo** para adicionar um registro de configuração.
1. No novo registro, defina os seguintes valores:

    - **Depósito:** *62*
    - **Local:** *Embalar*
    - **Criar trabalho de embalagem:** *Sim*

1. Feche a página **Configuração da estação de embalagem**.

### <a name="create-a-load-template-that-allows-partial-shipping"></a>Criar um modelo de carga que permita a remessa parcial

Para que uma carga possa ser entregue por várias remessas, você deve associá-la a um modelo de carregamento que permita a remessa parcial. Siga estas etapas para criar o modelo necessário.

1. Acesse **Gerenciamento de depósito \> Configuração \> Carga \> Modelos de carga**.
1. No Painel de Ações, selecione **Novo** para adicionar um registro de configuração.
1. No novo registro, defina os seguintes valores:

    - **ID do modelo de carga:** *Parcial*
    - **Permitir divisão de carga durante confirmação de remessa:** *Sim*

1. Feche a página **Modelos de carga**.

Para obter mais informações, consulte [Confirmar e transferir](Confirm-and-transfer.md).

### <a name="process-a-sales-order"></a>Processar uma ordem de venda

Siga estas etapas para processar uma ordem de venda e enviá-la parcialmente.

1. Conclua o [cenário de exemplo](packing-containers.md#scenario) fornecido em [Embalar contêineres para remessa](packing-containers.md). Durante esse cenário, você criará uma ordem de venda para duas partes de um item. Em seguida, você criará apenas uma das partes em um contêiner e o fechará. Você deve anotar o ID da remessa criada, conforme instruído no cenário.
1. Acesse **Gerenciamento de depósito \> Trabalho \> Todos os trabalhos**.
1. Na área do filtro, marque a caixa de seleção **Mostrar trabalho fechado**. Em seguida, insira o ID da remessa no campo **Filtrar** e escolha filtrar pelo valor **ID da remessa**. Agora, você deve ver três cabeçalhos de trabalho. Uma é para o trabalho de separação da ordem de venda e tem o status *Fechado*. Dois são para o processo de embalagem: um está relacionado ao contêiner fechado e tem o status *Fechado*, e o outro está relacionado ao item desembalado e tem o status *Em aberto*.
1. Selecione o valor **ID da carga** de qualquer um dos cabeçalhos de trabalho para abrir a página **Detalhes da carga**.
1. Alterne para a exibição do **Cabeçalho**.
1. Na guia rápida **Geral**, selecione o botão **Editar** para o campo **ID do modelo de carga**. Em seguida, selecione o modelo de carga de remessa parcial criado para esse cenário (*Parcial*).
1. No Painel de Ações, na guia **Enviar e receber**, no grupo **Confirmar**, selecione **Remessa de saída**.
1. Na caixa de diálogo **Confirmação de remessa**, selecione a opção **Dividir quantidade para nova carga**.
1. Selecione **OK**.

Agora, você enviou um contêiner que está relacionado à carga original e o sistema criou uma carga para os itens restantes que ainda devem ser embalados em contêineres.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
