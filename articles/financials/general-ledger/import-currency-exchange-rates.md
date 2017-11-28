---
title: "Importar taxas de câmbio de moeda"
description: "Se uma entidade legal recebeu faturas em moedas estrangeiras, é necessário converter a moeda estrangeira em moeda local. Isso significa que as taxas de câmbio atualizadas para diferentes moedas são necessárias. Este tópico fornece uma visão geral das definições e de processamento necessários para importar as taxas de referência da moeda estrangeira publicadas na Internet pelos provedores de taxa de câmbio, como o Banco Central Europeu e o Banco Central da Rússia."
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ExchangeRateProviderConfiguration
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 261374
ms.assetid: b2b22868-de68-439f-914c-78c6930b7340
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 270e0de2d58550e517417076b49a5a8bdc62bc64
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="import-currency-exchange-rates"></a>Importar taxas de câmbio de moeda

[!include[banner](../includes/banner.md)]


Se uma entidade legal recebeu faturas em moedas estrangeiras, é necessário converter a moeda estrangeira em moeda local. Isso significa que as taxas de câmbio atualizadas para diferentes moedas são necessárias. Este tópico fornece uma visão geral das definições e de processamento necessários para importar as taxas de referência da moeda estrangeira publicadas na Internet pelos provedores de taxa de câmbio, como o Banco Central Europeu e o Banco Central da Rússia.

As seções a seguir descrevem o fluxo de informações usadas para configurar e processar a importação de taxas de câmbio.

## <a name="configure-an-exchange-rate-provider"></a>Configurar um provedor de taxa de câmbio
Antes de importar taxas de câmbio, você deve configurar as informações necessárias para configurar os provedores que fornecem as taxas de câmbio. Use a página **Configurar provedores de taxa de câmbio** para selecionar os provedores de taxa de câmbio. Alguns provedores de taxa de câmbio estão incluídos nos dados de demonstração do Microsoft Dynamics 365 for Finance and Operations, Enterprise edition. A tabela a seguir fornece descrições dos controles desta página.

|           |                                                                                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Campo** | **Descrição**                                                                                                                                                                                                             |
| **Nome**  | O nome do provedor de taxa de câmbio.                                                                                                                                                                                     |
| **Chave**   | O identificador exclusivo das informações de configuração necessárias ao provedor. Essas informações são adicionadas automaticamente para cada fornecedor da taxa de câmbio que você adiciona quando clica no botão **Adicionar**. |
| **Valor** | As informações sobre cada chave. Essas informações são adicionadas a cada provedor da taxa de câmbio que você adiciona quando clica no botão **Adicionar**.                                                                                         |

## <a name="import-currency-exchange-rates"></a>Importar taxas de câmbio de moeda
Você pode importar taxas de câmbio de origem de provedores da taxa de câmbio, e configurá-las na página **Taxas de câmbio de moedas**. Use a página **Importar taxas de câmbio de moeda** para importar as taxas de câmbio. A tabela a seguir fornece descrições dos campos necessários para concluir com êxito o processo de importação.

|                                        |                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Campo**                              | **Descrição**                                                                                                                                                                                                                                                                                                                                                             |
| **Tipo de taxa de câmbio**                 | Um tipo de taxa de câmbio.                                                                                                                                                                                                                                                                                                                                                      |
| **Provedor de taxa de câmbio**             | Um do provedor de taxa de câmbio.                                                                                                                                                                                                                                                                                                                                                  |
| **Importar a partir de**                       | Este parâmetro gerencia se a importação deve ser feita na data de hoje ou para um intervalo de datas. Se quiser usar um intervalo de datas, insira ou selecione as datas de início e de término.                                                                                                                                                                                                                |
| **Criar os pares de moedas necessários**    | Esta caixa de seleção gerencia a criação automática dos pares de moeda, se os pares de moeda que são importados não existirem. Esta opção talvez não esteja disponível para alguns provedores.                                                                                                                                                                                               |
| **Substituir taxas de câmbio existentes**   | Esta caixa de seleção gerencia a atualização da taxa de câmbio existente para um par de moedas quando já existir a taxa de câmbio para uma data específica. Se você não marcar esta caixa de seleção, a taxa de câmbio para as datas específicas não será importada, se já existir outra taxa de câmbio.                                                                                       |
| **Evitar importação em feriado nacional** | Esta caixa de seleção gerencia a importação da taxa de câmbio para uma data que seja um feriado. Por exemplo, se você marcar esta caixa de seleção e usar o Banco Central Europeu como o provedor da taxa de câmbio, o sistema não atualizará a taxa de câmbio em um feriado que é relacionado à entidade legal atual. Esta opção talvez não esteja disponível para alguns provedores. |






