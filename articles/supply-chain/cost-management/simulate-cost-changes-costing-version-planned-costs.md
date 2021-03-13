---
title: Simular alterações de custo usando uma versão de custo para custos planejados
description: Este artigo explica como você pode simular os efeitos de alterações de custo nos custos calculados de um item fabricado usando uma versão de custo separada para custos planejados.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.custom: 78183
ms.assetid: 1e41953f-cdb9-4598-b776-46e49383a773
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 053709cb7a4ffb30e1e4968096ea4df5e67242e5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5011813"
---
# <a name="simulate-cost-changes-by-using-a-costing-version-for-planned-costs"></a>Simular alterações de custo usando uma versão de custo para custos planejados

[!include [banner](../includes/banner.md)]

Este artigo explica como você pode simular os efeitos de alterações de custo nos custos calculados de um item fabricado usando uma versão de custo separada para custos planejados.

Você pode simular os efeitos de alterações de custo nos custos calculados de um item fabricado usando uma versão de custo separada para custos planejados. Use a versão de custo separada para inserir registros de custos pendentes que refletem alterações de custo incrementais e para calcular o impacto de custo em itens fabricados. Como o princípio de fallback de custos ativos será usado em cálculos de BOM (lista de materiais), somente as alterações de custo incrementais devem ser inseridas.

## <a name="guidelines-for-defining-the-simulation-costing-version"></a>Diretrizes para definir a simulação de versão de avaliação de custo.
Use as diretrizes a seguir para definir a versão de avaliação de custo para simulações:

-   Atribua um tipo de custo de **Custos planejados**.
-   Atribua um identificador significativo para a versão de avaliação de custo, como **Simulação**.
-   Verifique se o conteúdo inclui registros de custo.
-   Permita a entrada de registros de custo. Não bloqueie a entrada de custos pendentes.
-   Permita a entrada de registros de custo para todos os sites. Se você especificar um site, limite a entrada de registros de custo a esse site.
-   Impeça a ativação de custos pendentes. Somente os custos pendentes devem ser inseridos para registros de custo na versão de avaliação de custo de simulação.
-   Não insira uma data "de início". Uma data de cálculo será inserida para cada cálculo de BOM que usa a simulação da versão de custo.
-   Indique o princípio de fallback do **Ativo atual**. O princípio de fallback permite a entrada de alterações de custo incrementais para fins de simulação enquanto usa os custos ativos atuais como fonte para todos os outros registros de custos. Presume-se que todos os custos ativos atuais existem para todos os outros registros de custo.
-   Especifique o modelo de preço de custo do **Preço de custo de versão**, mas não restrinja os cálculos. Por exemplo, as simulações também podem usar um modelo de preço de custo do **Grupo de cálculo de BOM** para indicar a fonte dos dados de contribuição de custo para itens comprados.
-   Indique um modo de detalhamento de **Vários níveis**, mas não restrinja os cálculos. As simulações podem usar outros modos de detalhamento.

## <a name="costing-versions"></a>Versões de custos
Os cenários a seguir ilustram o uso da simulação de versão de custo para simular o impacto das alterações de custo. Antes de inserir uma alteração de custo simulada, exclua os registros de custo pendentes na simulação de versão de custo, para ter um ponto de partida limpo. Use a página **Preço de item** para exibir e excluir os registros de custo pendentes relacionados aos preços de item e aos preços de categoria de custo.

-   Simule a alteração de custo para um item comprado. Por exemplo, a alteração de custo pode refletir um aumento ou uma redução esperada nos custos de materiais comprados críticos. Para definir o custo diferente para um item comprado, use a página **Preço de item** para inserir um registro de custo pendente na simulação de versão de custo.
-   Simule a alteração de custo para uma categoria de custo. Por exemplo, a alteração de custo pode refletir um aumento ou uma redução esperada nas taxas de trabalho ou nas taxas por hora dos recursos de operação. Para definir o custo diferente para uma categoria de custo, use a página **Preço de categoria de custo** para inserir um registro de custo pendente na simulação de versão de custo.
-   Simule a alteração de custo em uma fórmula de cálculo de custo indireto. Por exemplo, a alteração de custo pode refletir um aumento ou uma redução esperada dos custos gerais indiretos de fabricação. Para definir a alteração em uma fórmula de cálculo de custo indireto, use a página **Configuração de folha de custo** para inserir um registro de custo pendente na simulação de versão de custo e para validar e salvar a alteração.

Depois de inserir as alterações de custo simuladas, calcule os custos para os itens fabricados afetados pelas alterações de custo. Use a página **Cálculo** para a simulação de versão de custo e identifique os itens fabricados selecionados que serão afetados pelas alterações de custo. Os cálculos de BOM se aplicam a todos os itens fabricados a menos que você identifique os itens selecionados. Como alternativa, é possível usar a opção de cálculo de BOM para as atualizações usadas. Exiba os registros de custo na versão de avaliação de custo de simulação para analisar como as alterações de custo simuladas afetaram os custos dos itens fabricados selecionados. Use a página **Preço de item** e a página **Calcular custo de item** para ver e analisar os custos.



