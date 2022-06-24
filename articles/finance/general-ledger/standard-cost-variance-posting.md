---
title: Lançamento de variação de custo padrão
description: Este artigo fornece informações sobre como configurar o lançamento de perfis para cálculo de custo padrão.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: e7b2d04f32b75dbd1354b3ef74a41ea1b6469c8a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894867"
---
# <a name="standard-cost-variance-posting"></a>Lançamento de variação de custo padrão

Ao usar o custo padrão para um ou mais produtos em sua organização, você deve configurar os [pré-requisitos de custo padrão](/supply-chain/cost-management/prerequisites-standard-costs.md). Este artigo explica as contas de lançamento necessárias para a etapa 3 dos pré-requisitos, "Atribuir contas contábeis a lançamentos de itens relacionados a variações de custo padrão".

Diferentes tipos de variações podem ocorrer para compras e ordens de produção. Para obter exemplos de variações de produção, consulte [Fontes comuns de variações de produção](/supply-chain/cost-management/common-sources-of-production-variances.md). As variações de preço do pedido de compra ocorrem quando você usa o custo padrão para um item comprado e há uma diferença entre o custo padrão do produto e o valor faturado no pedido de compra.

## <a name="sample-posting-profile-configuration"></a>Exemplo de configuração de perfil de lançamento

A tabela a seguir mostra exemplos dos tipos de lançamento padrão. Ela inclui descrições e contas principais de exemplo.

- A coluna "Débito/Crédito?" indica se a transação é normalmente um débito ou um crédito. Em alguns casos, a transação pode lançar débitos ou créditos.
- A coluna "Conta de compensação" indica que o tipo de lançamento é uma conta de compensação. Em outras palavras, o valor lançado nessa conta é revertido automaticamente quando uma transação posterior é lançada.
- A coluna "P/F" indica o tipo de lançamento. "P" representa lançamento físico e "F" representa lançamento financeiro.
- A coluna "Seguir" indica se a conta principal para o tipo de lançamento é normalmente a mesma que a conta principal para outro tipo de lançamento. Especificamente, indica o tipo de lançamento geralmente usado.

> [!NOTE]
> As contas principais e os nomes das contas principais na tabela são sugestões. Recomendamos que você trabalhe com o seu contador para determinar a melhor configuração para as necessidades de sua empresa.

| Tipo de lançamento | Exemplo de conta principal | Exemplo de nome de conta principal | Tipo de conta | Débito/Crédito? | Conta de compensação | P/F | Seguir | Descrição |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-----|--------|-------------|
| Variação de preços de compra | 510310 | Variação de preços de compra | Despesa | Ou | Número | S | Não aplicável | Esta conta é usada quando há uma variação entre o preço de compra e o custo padrão em um pedido de compra. |
| Reavaliação de custos de estoque | 510330 | Reavaliação de custos de estoque | Despesa | Ou | Número | S | Não aplicável | Esta conta é usada quando uma nova versão de cálculo de custos é ativada para um item de custo padrão para reavaliar o estoque disponível. |
| Variação de alteração de custo | 510320 | Variação de alteração de custo | Despesa | Ou | Número | S | Não aplicável | Esta conta é usada quando há uma diferença nos custos padrão entre os locais ou quando um item é devolvido e há uma alteração entre o custo padrão original e o custo padrão atual de um produto. |
| Variação de tamanho do lote de produção | 510370 | Variação de tamanho do lote de produção | Despesa | Ou | Número | S | Não aplicável | Esta conta é usada quando há diferenças entre a base de cálculo da lista de materiais (BOM) e a quantidade real para o cálculo de custo do pedido de produção. |
| Variação do preço de produção | 510340 | Variação do preço de produção | Despesa | Ou | Número | S | Não aplicável | Esta conta é usada quando há diferenças de preço entre o custo estimado e o custo real de um pedido de produção. |
| Variação de quantidade de produção | 510350 | Variação de quantidade de produção | Despesa | Ou | Número | S | Não aplicável | Esta conta é usada quando há diferenças de quantidade entre o custo estimado e os custos reais de um pedido de produção. |
| Variação de substituição de produção | 510360 | Variação de substituição de produção | Despesa | Ou | Número | S | Não aplicável | Esta conta é usada quando há consumo inesperado em um pedido de produção. |
| Variação de arredondamento | 618160 | Diferença de arredondamento | Despesa | Ou | Número | S | Não aplicável | Esta conta é utilizada quando há uma diferença de arredondamento quando os custos de produção são calculados a partir dos custos padrão. |
