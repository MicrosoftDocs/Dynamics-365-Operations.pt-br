---
title: "Importar taxas de câmbio de moeda"
description: "Se uma pessoa jurídica recebeu fiscais em moedas estrangeiras, é necessário converter a moeda estrangeira em moeda local. Isso significa que as taxas de câmbio atualizados para diferentes moedas são necessárias. Este tópico fornece uma visão geral das definições e de processamento necessários para importar as taxas de referência da moeda estrangeira publicadas Na Internet pelos provedores cambiais, como o Banco Central Europeu e o banco central em A Rússia."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ExchangeRateProviderConfiguration
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261374
ms.assetid: b2b22868-de68-439f-914c-78c6930b7340
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: bf66a1b1c9314b454223274810a21913d54b702d
ms.lasthandoff: 03/31/2017


---

# <a name="import-currency-exchange-rates"></a>Importar taxas de câmbio de moeda

Se uma pessoa jurídica recebeu fiscais em moedas estrangeiras, é necessário converter a moeda estrangeira em moeda local. Isso significa que as taxas de câmbio atualizados para diferentes moedas são necessárias. Este tópico fornece uma visão geral das definições e de processamento necessários para importar as taxas de referência da moeda estrangeira publicadas Na Internet pelos provedores cambiais, como o Banco Central Europeu e o banco central em A Rússia.

As seções a seguir descrevem as informações de circulação usada e configurando processando importação de taxas de câmbio estrangeiras.

## <a name="configure-an-exchange-rate-provider"></a>Configurar um provedor de taxa de câmbio
Antes de importar taxas de câmbio, você deve configurar as informações necessárias para configurar os provedores que fornece as taxas de câmbio. Use ** provedores cambial ** a página para selecionar os provedores cambial. Alguns provedores cambiais são incluídos com dados de demonstração no Microsoft Dynamics 365 para as operações. A tabela a seguir fornece descrições para os controles nessa página.

|           |                                                                                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Field** | **Description**                                                                                                                                                                                                             |
| **Name**  | O nome do provedor de taxa de câmbio.                                                                                                                                                                                     |
| ** Chave **   | O identificador exclusivo das informações de configuração necessárias ao provedor. Essa informações é adicionada automaticamente para cada fornecedor cambial adicionado quando você clica ** ** o botão adicionar. |
| **Value** | As informações sobre cada chave. Essa informação será adicionada para cada fornecedor cambial adicionado quando você clica ** ** o botão adicionar.                                                                                         |

## <a name="import-currency-exchange-rates"></a>Importar taxas de câmbio de moeda
Você pode importar taxas de câmbio de origem de provedores cambiais, e configurá-las ** taxas de câmbio ** na página. Use ** taxas de câmbio de importação ** a página para importar as taxas de câmbio. A tabela a seguir fornece descrições os campos necessários concluir com êxito o processo de importação.

|                                        |                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Field**                              | **Description**                                                                                                                                                                                                                                                                                                                                                             |
| **Exchange rate type**                 | Um tipo de taxa de câmbio.                                                                                                                                                                                                                                                                                                                                                      |
| **Exchange rate provider**             | Um provedor cambial.                                                                                                                                                                                                                                                                                                                                                  |
| **Import as of**                       | Se este parâmetro gerencia importar na data de hoje ou para um intervalo de datas. Se desejar usar um intervalo de data, insira ou selecione as datas inicial e final.                                                                                                                                                                                                                |
| **Create necessary currency pairs**    | Esta caixa de seleção para gerar a criação automática dos pares de moeda, se os pares de moeda serão importados que não existem. Esta opção pode não estar disponíveis para alguns provedores.                                                                                                                                                                                               |
| **Override existing exchange rates**   | Esta caixa de seleção para gerar a atualização cambial existente para uma trilha de moeda quando a taxa de câmbio para uma data específica já existe. Se você não selecionar esta caixa, a taxa de câmbio para datas específicas não será importada se outra taxa de câmbio já existe.                                                                                       |
| **Prevent import on national holiday** | Esta caixa de seleção para gerar a importação cambial para uma data que seja um feriado. Por exemplo, se você marcar esta caixa de seleção e usa o Banco Central Europeu como o provedor cambial, o sistema não atualizará a taxa de câmbio em um feriado que é relacionado à entidade legal atual. Esta opção pode não estar disponíveis para alguns provedores. |




