---
title: Habilitar o cálculo de impostos atrasados nos diários
description: Este artigo explica como ativar o recurso Cálculo de impostos atrasados para ajudar a melhorar o desempenho dos cálculos de impostos quando o número de linhas do diário é muito grande.
author: EricWang
ms.date: 09/18/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 02a038318d4c0fb44b6fcc4bb159ea87c2e9368a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887909"
---
# <a name="enable-delayed-tax-calculation-on-journals"></a>Habilitar o cálculo de impostos atrasados nos diários
[!include [banner](../includes/banner.md)]


Este artigo explica como você pode adiar o cálculo do imposto sobre vendas nos diários. Esse recurso ajuda a melhorar o desempenho dos cálculos de impostos quando existem muitas linhas do diário.

Por padrão, os valores do imposto sobre vendas nas linhas do diário são calculados sempre que os campos relacionados ao imposto são atualizados. Esses campos incluem os campos para grupos de impostos e grupos de impostos sobre itens. Qualquer atualização em uma linha do diário faz com que os valores dos impostos sejam recalculados para todas as linhas do diário. Embora esse comportamento ajude o usuário a ver os valores dos impostos calculados em tempo real, também poderá afetar o desempenho se o número de linhas do diário for muito grande.

O recurso Cálculo de impostos atrasados permite adiar o cálculo de impostos em diários e, portanto, ajuda a corrigir problemas de desempenho. Quando esse recurso é ativado, os valores do imposto são calculados apenas quando um usuário seleciona **Imposto** ou lança o diário.

Você pode adiar o cálculo dos impostos em três níveis:

- Pessoa jurídica em geral
- Nome do diário
- Cabeçalho do diário

O sistema prioriza a configuração do cabeçalho do diário. Por padrão, essa configuração é obtida do nome do diário. Por padrão, a configuração para o nome do diário é obtida na página **Parâmetros da contabilidade** quando o nome do diário é criado. As seções a seguir explicam como ativar o cálculo de impostos atrasados para entidades legais, nomes de diários e cabeçalhos de diários.

## <a name="turn-on-delayed-tax-calculation-at-the-legal-entity-level"></a>Ativar cálculo de impostos atrasados no nível da entidade legal

1. Acesse **Contabilidade \> Configuração do razão \> Parâmetros da contabilidade**.
2. Na guia **Imposto**, na Guia Rápida **Geral**, defina a opção **Cálculo de impostos atrasados** como **Sim**.

![Imagem dos parâmetros da contabilidade.](media/delayed-tax-calculation-gl.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-name-level"></a>Ativar cálculo de impostos atrasados no nível do nome do diário

1. Acesse **Contabilidade \> Configuração do diário \> Nomes de diário**.
2. Na Guia Rápida **Geral**, na seção **Imposto**, defina a opção **Cálculo de impostos atrasados** como **Yes**.

![Imagem dos nomes de diário.](media/delayed-tax-calculation-journal-name.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-header-level"></a>Ativar cálculo de impostos atrasados no nível do cabeçalho do diário

1. Ir para **Contabilidade \> Entradas de diários \> Diários gerais**.
2. Selecione **Novo**.
3. Selecione um nome de diário.
4. Na guia **Setup**, defina a opção **Cálculo de impostos atrasados** como **Sim**.

![Imagem da página Diário geral.](media/delayed-tax-calculation-journal-header.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
