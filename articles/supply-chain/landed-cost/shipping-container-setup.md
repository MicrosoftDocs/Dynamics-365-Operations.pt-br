---
title: Contêineres de remessa
description: Este tópico descreve como configurar contêineres de remessa para o módulo Custo de entrega.
author: Weijiesa
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMContainerTypeTable, ITMContainerTable, ITMContainerUnitTypeTable, ITMRefrigerationTypeTable, ITMContainersListPage, ITMContainers
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 96710cf2b5a2e39f9492aadb0ba6f3241f0666f4
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690544"
---
# <a name="shipping-container-setup"></a>Configuração de contêineres de remessa

[!include [banner](../../includes/banner.md)]

Este tópico descreve como configurar contêineres de remessa para o módulo **Custo de entrega**.

## <a name="set-up-shipping-container-types"></a><a id="shipping-container-types"></a>Configurar tipos de contêineres de remessa

Os tipos de contêineres de remessa definem os tipos de contêineres de remessa disponíveis para uso durante remessas e viagens.

Para trabalhar com os tipos de contêineres de remessa, Acesse **Custo de entrega \> Configuração de contêineres \> Tipos de contêineres de remessa**. Lá, você pode exibir, adicionar e remover registros para os seus tipos de contêineres. A tabela a seguir descreve os campos disponíveis para cada registro.

| Campo | descrição |
|---|---|
| Tipo de contêiner de remessa | Insira um nome/número de identificação exclusivo para o tipo de contêiner de remessa. |
| descrição | Insira uma descrição do tipo de contêiner de remessa. |
| Volume | Insira o volume máximo permitido em contêineres de remessa deste tipo. |
| Peso | Insira o peso máximo permitido em contêineres de remessa deste tipo. |
| Retornável | Especifique se os contêineres de remessa deste tipo podem ser devolvidos ao fornecedor depois de serem usados durante uma viagem. Se essa opção for definida como *Sim*, custos adicionais poderão ser aplicados para a devolução de contêineres de remessa deste tipo ao porto de origem. |

## <a name="set-up-shipping-containers"></a>Configurar contêineres de remessa

Você usa registros de contêineres de remessa para identificar cada contêiner usado durante as viagens. Ao criar uma viagem, é possível selecionar um contêiner específico para ela na lista de todos os registros de contêineres de remessa que você definiu aqui. Esse recurso é especialmente útil se a empresa tiver seus próprios contêineres de remessa.

Não é necessário inserir números de contêineres de remessa para contêineres de remessa que serão usados apenas uma vez. Em vez disso, você pode adicionar o número do contêiner de remessa quando criar uma viagem.

Os registros dos contêineres de remessa são usados somente no Custo de entrega. Eles não estão disponíveis no módulo **Gerenciamento de transporte** (TMS) padrão.

Para trabalhar com contêineres de remessa, Acesse **Custo de entrega \> Configuração de contêineres \> Contêineres de remessa**. Lá, você pode exibir, adicionar e remover registros para os seus contêineres de remessa. A tabela a seguir descreve os campos disponíveis para cada registro.

| Campo | descrição |
|---|---|
| Contêiner de remessa | Insira um nome/número de identificação exclusivo para o contêiner de remessa. |
| Tipo de contêiner de remessa | Selecione o tipo de contêiner de remessa. Para obter mais informações, consulte a seção [Configurar tipos de contêineres de remessa](#shipping-container-types) anteriormente neste tópico. |

> [!NOTE]
> - A configuração de contêineres de remessa é opcional. Normalmente, ela será usada somente se a empresa tiver seus próprios contêineres de remessa ou reutilizar os mesmos contêineres de remessa com frequência.
> - Nenhum dígito de verificação é calculado para números de contêineres de remessa.

## <a name="set-up-unit-types"></a><a name="unit-types"></a>Configurar tipos de unidades

Os tipos de unidades estabelecem agrupamentos e métodos de identificação adicionais para contêineres de remessa. Normalmente, o tipo de unidade é usado para identificar o tipo de contêiner em que as mercadorias são embaladas, como paletes ou tambores. Você pode selecionar um tipo de unidade ao configurar um contêiner na página **Todos os contêineres de remessa**.

Os tipos de unidades são usados somente no Custo de entrega. Eles não estão disponíveis no TMS.

Para trabalhar com tipos de unidades, Acesse **Custo de entrega \> Configuração de contêineres \> Tipos de unidades**. Lá, você pode exibir, adicionar e remover registros para os seus tipos de unidades. A tabela a seguir descreve os campos disponíveis para cada registro.

| Campo | descrição |
|---|---|
| Tipo de Unidade | Insira um nome/número de identificação exclusivo para o tipo de unidade. |
| descrição | Insira uma descrição do tipo de unidade. |

## <a name="set-up-refrigeration-types"></a><a name="refrigeration-types"></a>Configurar tipos de refrigeração

Os tipos de refrigeração estabelecem agrupamentos e métodos de identificação adicionais para contêineres de remessa (normalmente contêineres refrigerados). Você pode selecionar um tipo de refrigeração ao configurar um contêiner na página **Todos os contêineres de remessa**.

Para trabalhar com tipos de refrigeração, Acesse **Custo de entrega \> Configuração de contêineres \> Tipos de refrigeração**. Lá, você pode exibir, adicionar e remover registros para os seus tipos de refrigeração. A tabela a seguir descreve os campos disponíveis para cada registro.

| Campo | descrição |
|---|---|
| Tipo de refrigeração | Insira um nome/número de identificação exclusivo para o tipo de refrigeração. |
| descrição | Insira uma descrição do tipo de refrigeração. |
