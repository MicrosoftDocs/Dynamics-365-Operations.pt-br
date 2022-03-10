---
title: Definir dimensões diferentes para embalagem e armazenamento
description: Este tópico mostra como especificar para qual processo (embalagem, armazenamento ou embalagem aninhada) cada dimensão especificada é usada.
author: mirzaab
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResPhysicalProductDimensions, WHSPhysDimUOM
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 0e8ce576f21f1f5ea5f3acb7d43bbe68826e6f39
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580063"
---
# <a name="set-different-dimensions-for-packing-and-storage"></a>Definir dimensões diferentes para embalagem e armazenamento

[!include [banner](../../includes/banner.md)]

Alguns itens são embalados ou armazenados de forma que pode ser necessário rastrear dimensões físicas de forma diferente para cada processo. O recurso *Dimensões de produtos de embalagem* permite configurar um ou mais tipos de dimensões para cada produto. Cada tipo de dimensão oferece um conjunto de medidas físicas (peso, largura, profundidade e altura) e estabelece o processo em que esses valores de medida física se aplicam. Quando este recurso é habilitado, o sistema oferecerá suporte aos seguintes tipos de dimensões:

- *Armazenamento* – as dimensões de armazenamento são usadas com a volumetria da localização para determinar a quantidade de cada item que pode ser armazenada em diferentes localizações de depósito.
- *Embalagem* – as dimensões de embalagem são usadas durante o transporte em contêineres e o processo de embalagem manual para determinar a quantidade de cada item que caberá nos diferentes tipos de contêiner.
- *Embalagem aninhada* – as dimensões de embalagem aninhada são usadas quando o processo de embalagem contiver vários níveis.

As dimensões de *armazenamento* são compatíveis mesmo quando o recurso *Dimensões de produtos de embalagem* não está habilitado. Configure-as usando a página **Dimensão física** no Supply Chain Management. Essas dimensões são usadas por todos os processos nos quais as dimensões de embalagem e embalagem aninhada não são especificadas.

As dimensões de *embalagem* e *embalagem aninhada* são configuradas usando a página **Dimensões físicas do produto**, adicionada quando você habilita o recurso *Dimensões de produtos de embalagem*.
Este tópico oferece um cenário que mostra como usar esse recurso.

## <a name="turn-on-the-packaging-product-dimensions-feature"></a>Ativar o recurso de dimensões de produtos de embalagem

Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema. Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário. Nesse caso, o recurso é listado da seguinte maneira:

- **Módulo:** *Gerenciamento de Depósito*
- **Nome do recurso:** *Dimensões de produtos de embalagem*

## <a name="example-scenario"></a>Cenário de exemplo

### <a name="set-up-the-scenario"></a>Configurar o cenário

Antes de executar o cenário de exemplo, prepare o sistema conforme descrito nesta seção.

#### <a name="enable-demo-data"></a>Habilitar dados de demonstração

Para trabalhar nesse cenário usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados. Além disso, você deve selecionar a entidade legal *USMF* antes de começar.

#### <a name="add-a-new-physical-dimension-to-a-product"></a>Adicionar nova dimensão física a um produto

Adicione uma nova dimensão física a um produto da seguinte forma:

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Selecione o produto com **Número do item** *A0001*.
1. No Painel de Ação, abra a guia **Gerenciar estoque** e, no grupo **Depósito**, selecione **Dimensões físicas do produto**.
1. A página **Dimensões físicas do produto** é aberta. No Painel de Ações, selecione **Novo** para adicionar uma nova dimensão à grade com as seguintes configurações:
    - **Tipo de dimensão física** - *Embalagem*
    - **Unidade física** - *pçs*
    - **Peso** - *4*
    - **Unidade de peso** - *kg*
    - **Profundidade** - *3*
    - **Altura** - *4*
    - **Largura** - *3*
    - **Comprimento** - *cm*
    - **Unidade de volume** - *cm3*

O campo **Volume** é calculado automaticamente com base nas configurações de **Profundidade**, **Altura** e **Largura**.

#### <a name="create-a-new-container-type"></a>Criar um novo tipo de contêiner

Acesse **Gerenciamento de depósito \> Configuração \> Contêineres \> Tipos de contêiner** e crie um registro com as seguintes configurações:

- **Código do tipo de contêiner** - *Caixa Baixa*
- **Descrição** - *Caixa Baixa*
- **Peso líquido máximo** - *50*
- **Volume** - *144*
- **Extensão** - *6*
- **Largura** - *6*
- **Altura** - *4*

#### <a name="create-a-container-group"></a>Criar um grupo de contêineres

Acesse **Gerenciamento de depósito \> Configuração \> Contêineres \> Grupos de contêineres** e crie um registro com as seguintes configurações:

- **ID do grupo de contêineres** - *Caixa Baixa*
- **Descrição** - *Caixa Baixa*

Adicione uma nova linha à seção **Detalhes**. Defina o **Tipo de contêiner** como *Caixa Baixa*.

#### <a name="set-up-a-container-build-template"></a>Configurar um modelo de criação de contêiner

Acesse **Gerenciamento de depósito \> Configuração \> Contêineres \> Modelos de criação de contêiner** e selecione **Caixas**. Altere a **ID do grupo de contêineres** como *Caixa Baixa*.

### <a name="run-the-scenario"></a>Executar o cenário

Depois de preparar o sistema conforme descrito na seção anterior, você estará pronto para executar o cenário conforme descrito na próxima seção.

#### <a name="create-a-sales-order-and-create-a-shipment"></a>Criar uma ordem de venda e uma remessa

Neste processo, você criará uma remessa com base nas dimensões de *embalagem* do item, para o qual a altura é inferior a 3.

1. Acesse **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.
1. No Painel de Ações, selecione **Novo**.
1. Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:

    - **Conta de cliente:** *US-001*
    - **Depósito:** *63*

1. Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo.
1. A nova ordem de venda é aberta. Ele deve incluir uma nova linha vazia na grade da FastTab **Linhas de ordem de venda**. Nessa linha, defina os seguintes valores:

    - **Número de item:** *A0001*
    - **Quantidade:** *5*

1. Na FastTab **Linhas da ordem de venda**, selecione **Estoque \> Reserva**.
1. Na página **Reserva**, no Painel de Ação, selecione **Reservar lote** para reservar o estoque.
1. Feche a página.
1. No Painel de Ações, abra a guia **Depósito** e selecione **Liberar para depósito** para criar trabalho para o depósito.
1. Na FastTab **Linhas de ordem de venda**, selecione **Depósito \> Detalhes da remessa**.
1. No painel de ações, abra a guia **Transporte** e selecione **Exibir contêineres**. Confirme se o item foi incluído nos dois contêineres *Caixa Baixa*.

#### <a name="place-an-item-into-storage"></a>Colocar um item no armazenamento

1. Abra o dispositivo móvel para entrar no depósito 63 e acesse **Estoque \> Ajustar em**.
1. Insira **Loc** = *SHORT-01*. Crie uma placa de licença com **Item** = *A0001* e **Quantidade** = *1 pçs*.
1. Selecione **OK**. Você receberá o erro "Falha no local SHORT-01 porque o item A0001 não cabe nas dimensões especificadas do local". Isso ocorre porque as dimensões do tipo de *Armazenamento* do produto são maiores que as dimensões especificadas no perfil de localização.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]