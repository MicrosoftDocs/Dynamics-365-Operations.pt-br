---
title: Importar taxas de câmbio de moeda
description: Este tópico fornece informações sobre os requisitos para importar taxas de referência de câmbio estrangeiras que são publicadas por provedores de taxa de câmbio.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ExchangeRateProviderConfiguration
audience: Application User
ms.reviewer: kfend
ms.custom: 261374
ms.assetid: b2b22868-de68-439f-914c-78c6930b7340
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: a5dbe0d822f7bdb1a62a99c43ef9f7170c889676
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4988868"
---
# <a name="import-currency-exchange-rates"></a>Importar taxas de câmbio de moeda

[!include [banner](../includes/banner.md)]

Se uma entidade legal tiver recebido faturas em moedas estrangeiras, a moeda estrangeira deverá ser convertida em moeda local. Isso significa que as taxas de câmbio atualizadas para diferentes moedas são necessárias. Este tópico fornece uma visão geral das definições e de processamento necessários para importar as taxas de referência da moeda estrangeira publicadas pelos provedores de taxa de câmbio, como o Banco Central Europeu e o Banco Central da Rússia.

As seções a seguir descrevem o fluxo de informações usadas para configurar e processar a importação de taxas de câmbio.

## <a name="configure-an-exchange-rate-provider"></a>Configurar um provedor de taxa de câmbio
Antes de importar taxas de câmbio, você deve configurar as informações necessárias para configurar os provedores que fornecem as taxas de câmbio. Use a página **Configurar provedores de taxa de câmbio** para selecionar os provedores de taxa de câmbio. Alguns provedores de taxa de câmbio são incluídos com dados de demonstração no Dynamics 365 Finance. A tabela a seguir fornece descrições dos controles desta página.

|           |                                                                                                                                                                                                                             |
|-----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Campo** | **Descrição**                                                                                                                                                                                                             |
| **Nome**  | O nome do provedor de taxa de câmbio.                                                                                                                                                                                     |
| **Chave**   | O identificador exclusivo das informações de configuração necessárias ao provedor. Essas informações são adicionadas automaticamente a cada fornecedor da taxa de câmbio que você adiciona. |
| **Value** | As informações sobre cada chave. Essas informações são adicionadas a cada fornecedor da taxa de câmbio que você adiciona.                                                                                         |

## <a name="import-currency-exchange-rates"></a>Importar taxas de câmbio de moeda
Você pode importar taxas de câmbio da origem de provedores da taxa de câmbio e adicioná-las à página **Taxas de câmbio de moedas**. Use a página **Importar taxas de câmbio de moeda** para importar as taxas de câmbio. A tabela a seguir fornece descrições de campos necessários para concluir com êxito o processo de importação.

|                                        |                                                                                                                                                                                                                                                                                                                                                                             |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Campo**                              | **Descrição**                                                                                                                                                                                                                                                                                                                                                             |
| **Tipo de taxa de câmbio**                 | Um tipo de taxa de câmbio.                                                                                                                                                                                                                                                                                                                                                      |
| **Provedor de taxa de câmbio**             | Um do provedor de taxa de câmbio.                                                                                                                                                                                                                                                                                                                                                  |
| **Importar a partir de**                       | Este parâmetro gerencia se a importação deve ser feita na data de hoje ou em um intervalo específico de datas. Se quiser usar um intervalo de datas, insira ou selecione as datas inicial e final.                                                                                                                                                                                                                |
| **Criar os pares de moedas necessários**    | Esta caixa de seleção gerencia a criação automática dos pares de moeda, se os pares de moeda que são importados não existirem. Esta opção talvez não esteja disponível para alguns provedores.                                                                                                                                                                                               |
| **Substituir taxas de câmbio existentes**   | Esta caixa de seleção gerencia a atualização da taxa de câmbio existente para um par de moedas quando já existir a taxa de câmbio para uma data específica. Se você não marcar esta caixa de seleção, a taxa de câmbio para as datas específicas não será importada, se já existir outra taxa de câmbio.                                                                                       |
| **Evitar importação em feriado nacional** | Esta caixa de seleção gerencia a importação da taxa de câmbio para a data de feriado público. Por exemplo, se você marcar esta caixa de seleção e usar o Banco Central Europeu como o provedor da taxa de câmbio, o sistema não atualizará a taxa de câmbio em um feriado que é relacionado à entidade legal atual. Esta opção talvez não esteja disponível para alguns provedores. |
| **Taxa do dia anterior** | Esta caixa de seleção estará disponível se você habilitar o recurso **Importação do ECB na data atual ou anterior** na página **Gerenciamento de recursos**. Esta caixa de seleção está disponível apenas para o fornecedor *Banco Central Europeu*. Marque esta caixa de seleção para importar a taxa de câmbio da moeda publicada pelo Banco Central Europeu no dia útil anterior aproximadamente às 16h00 CET. Por padrão, a caixa de seleção é selecionada. Desmarque esta caixa de seleção para importar a taxa de câmbio da moeda que for publicada no mesmo dia útil.  |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]