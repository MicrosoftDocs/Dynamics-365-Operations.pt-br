---
title: Configuração de informações de remessa
description: Este tópico descreve como configurar informações de remessa para o módulo Custo de entrega.
author: sherry-zheng
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMGoodsDescriptionTable, ITMVesselTable, ITMExporterTable, ITMCommodityCodeTable, ITMCustomsDescription
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 74ac7e0eac545369eef1a48f0085c820a4728e75
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833680"
---
# <a name="shipping-information-setup"></a>Configuração de informações de remessa

[!include [banner](../../includes/banner.md)]

Este tópico descreve como configurar informações de remessa para o módulo **Custo de entrega**.

## <a name="description-of-goods"></a><a name="description-of-goods"></a>Descrição das mercadorias

As descrições de mercadorias ajudam a identificar uma viagem, um contêiner de remessa ou um fólio de mercadorias e as mercadorias contidas nele. É possível selecionar uma descrição de mercadorias no cabeçalho do contêiner de remessa ou no cabeçalho do fólio.

Para trabalhar com descrições de mercadorias, vá para **Custo de entrega \> Configuração de informações de remessa \> Descrição de mercadorias**. Lá, você pode exibir, abrir, criar e excluir registros de descrições de mercadorias. A tabela a seguir descreve os campos disponíveis para cada registro.

| Campo | descrição |
|---|---|
| Descrição das mercadorias | Insira um nome/número de identificação exclusivo para o tipo de mercadorias que usará esta descrição. |
| descrição | Insira uma descrição do tipo de mercadorias nesta categoria. |

## <a name="vessels"></a><a name="vessels"></a>Embarcações

Uma embarcação é o nome exclusivo de um navio ou embarcação que uma agência ou empresa de transporte usa. Ao criar uma viagem, você sempre deve selecionar ou inserir uma embarcação para ela. Se você costuma usar as mesmas embarcações, é possível agilizar e facilitar a criação de uma nova viagem criando um registro de embarcação para cada uma delas, permitindo, assim, que os usuários selecionem a embarcação em uma lista em vez de inserir o nome ou o número manualmente a cada vez.

Para trabalhar com embarcações, vá para **Custo de entrega \> Configuração de informações de remessa \> Embarcações**. Lá, você pode exibir, abrir, criar e excluir registros de embarcações. A tabela a seguir descreve os campos disponíveis para cada registro.

| Campo | descrição |
|---|---|
| Embarcação | Insira um nome/número de identificação exclusivo para o navio que será usado para transportar mercadorias em uma viagem. |
| descrição | Insira uma descrição da embarcação. Normalmente, essa descrição identifica o nome do navio e a empresa/agente de transporte. |
| Modo de entrega | Selecione o modo de entrega usado pela embarcação (como _Aéreo_, _Marítimo_ ou _Ferroviário_). |

## <a name="exporters"></a>Exportadores

Cada registro de exportador identifica um fornecedor ou exportador que pode ser definido como o fornecedor de uma viagem. O exportador pode ser associado a uma viagem e usado para relatórios.

Para trabalhar com exportadores, vá para **Custo de entrega \> Configuração de informações de remessa \> Exportadores**. Lá, você pode exibir, abrir, criar e excluir registros de exportadores. A tabela a seguir descreve os campos disponíveis para cada registro.

| Campo | descrição |
|---|---|
| Exportador | Insira um nome/número de identificação exclusivo para o exportador de mercadorias transportadas em uma viagem. |
| descrição | Insira uma descrição do exportador. Normalmente, essa descrição identifica o nome completo da empresa/agente de transporte. |

## <a name="commodity-codes"></a>Códigos de mercadoria

Você usa códigos de mercadoria para ajudar na identificação alfandegária e no cálculo de taxas de imposto para mercadorias em uma viagem. Você pode selecionar códigos de mercadoria na página **Produtos liberados**.

Para trabalhar com códigos de mercadoria, vá para **Custo de entrega \> Configuração de informações de remessa \> Códigos de mercadoria**. Lá, você pode exibir, abrir, criar e excluir registros de códigos de mercadoria. A tabela a seguir descreve os campos disponíveis para cada registro.

| Campo | descrição |
|---|---|
| Código da mercadoria | Insira um código exclusivo para este tipo de mercadoria. |
| descrição | Insira uma descrição do tipo de mercadoria. |

## <a name="customs-description"></a>Descrição alfandegária

As descrições alfandegárias ajudam a identificar mercadorias para fins alfandegários. Você pode selecionar uma descrição alfandegária na página **Produtos liberados** ou nas linhas da ordem de compra.

Para trabalhar com descrições alfandegárias, vá para **Custo de entrega \> Configuração de informações de remessa \> Descrição alfandegária**. Lá, você pode exibir, abrir, criar e excluir registros de descrições alfandegárias. A tabela a seguir descreve os campos disponíveis para cada registro.

| Campo | descrição |
|---|---|
| Descrição alfandegária | Insira um código exclusivo para este tipo de classificação alfandegária. Geralmente, esse código será a descrição oficial fornecida por uma autoridade alfandegária para a descrição e o valor qualitativo das mercadorias. |
| descrição | Insira uma descrição da classificação alfandegária. |
