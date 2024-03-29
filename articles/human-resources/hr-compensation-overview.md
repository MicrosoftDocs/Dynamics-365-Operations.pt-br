---
title: Planos de remuneração
description: Este artigo descreve como usar o gerenciamento de remuneração para gerenciar e processar planos de remuneração.
author: twheeloc
ms.date: 08/25/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: HcmCompensationLevel, HRCCompGrid, HRMCompFixedAction, HRMCompFixedBudget, HRMCompFixedPlanTable, HcmCompensationWorkspace
audience: Application User
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 39bb4419f18f2cc0da28b5527d261112b2ae74c5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859536"
---
# <a name="compensation-plans"></a>Planos de remuneração


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Os gerentes de remuneração e de benefícios que podem usar o **Gerenciamento de remuneração** para manter e processar planos de remuneração fixos e variáveis para os funcionários da organização.

### <a name="introduction"></a>Introdução

O gerenciamento de remuneração é usado para controlar o pagamento do salário base e de prêmios. Os aumentos no salário base fixo e nos prêmios de um funcionário são controlados por meio de planos de remuneração fixos. O pagamento de incentivos, como pagamentos de bônus, prêmios por desempenho, opções de ação e concessões, além de prêmios únicos, são controlados por meio de planos de remuneração variável. 

Os funcionários podem estar inscritos em um ou mais planos de ambos os tipos. Um funcionário deve atender aos requisitos a seguir para serem qualificados para a inscrição em um plano de remuneração:
-   O funcionário deve ter uma atribuição de posição ativa.
-   O funcionário deve atender aos critérios definidos pelas regras de qualificação para um plano de remuneração.

## <a name="compensation-setup"></a>Configuração da remuneração
A tabela a seguir lista os componentes do processo de remuneração que podem integrais ao configurar os planos de remuneração de sua empresa.

<table>
<thead>
<tr class="header">
<th>Componente</th>
<th>Mais informações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Ações de remuneração fixa</td>
<td>As ações de remuneração fixa têm duas finalidades:
<ul>
<li>As ações podem especificar o tipo de informação que deve ser registrada quando a remuneração de um funcionário é alterada. Por exemplo, você pode exigir que o motivo para uma alteração, como uma promoção ou um rebaixamento, seja registrado.</li>
<li>Ações que podem garantir que o cálculo seja aplicado quando os planos de remuneração fixa são processados.  Por exemplo, ações do tipo Capital próprio irão comparar o pagamento dos funcionários com o ponto de referência mínimo deles e garantirão que estejam recebendo pelo menos o mínimo.</li>
</ul></td>
</tr>
<tr class="even">
<td>Níveis</td>
<td>Os níveis são associados ao trabalho e às posições relacionadas a uma referência de trabalho. Você pode criar níveis distintos para os três tipos de planos de remuneração: pontuação, faixa e etapa.</td>
</tr>
<tr class="odd">
<td>Matriz de utilização da faixa salarial</td>
<td>A matriz de utilização de faixa salarial ajuda você a fazer a transição de funcionários para o ponto de controle de suas funções. Você também pode usar a utilização da faixa salarial para controlar o capital próprio da taxa de pagamento da empresa sem considerar o desempenho individual de um funcionário ou o desempenho geral da empresa. Por exemplo, os funcionários que recebem salários mais baixos da faixa obtêm percentuais maiores de aumento que os funcionários que recebem salários maiores. Assim, você pode compensar as diferenças de capital próprio sistematicamente. A utilização da faixa salarial é calculada da seguinte maneira: (Taxa de pagamento fixo - mínimo da faixa) ÷ (máximo da faixa - mínimo da faixa).</td>
</tr>
<tr class="even">
<td>Configurações de pontos de referência</td>
<td>A configuração do ponto de referência inclui um conjunto de pontos de referência que representam faixas de uma matriz. Cada faixa pode ser associada a uma taxa de pagamento. Por exemplo, os planos de classificação normalmente terão pontos de referência de mínimo, médio e máximo.</td>
</tr>
<tr class="odd">
<td>Matriz de remuneração</td>
<td>Uma matriz de remuneração consiste em um conjunto de pontos de referência e níveis usados para criar uma estrutura de remuneração.</td>
</tr>
<tr class="even">
<td>Estrutura de remuneração</td>
<td>Uma estrutura de remuneração é uma matriz de remuneração que tem taxas de pagamento associadas aos pontos de referência para cada nível.</td>
</tr>
<tr class="odd">
<td>Regras de qualificação</td>
<td>As regras de qualificação são usadas para identificar funcionários em tarefas específicas, funções, tipos de trabalho, departamentos, associações sindicais ou em regiões de remuneração cobertas por planos de remuneração específicos. Você deve criar regras de qualificação para planos de remuneração variável e fixa para inserir os funcionários no plano. Depois de ter especificado as regras de qualificação para um plano de remuneração, você pode definir os níveis que devem ser aplicados às funções cobertas pelo plano.</td>
</tr>
<tr class="even">
<td>Frequências de pagamento</td>
<td>As frequências de pagamento são usadas para definir o período de tempo durante o qual a remuneração é especificada.  Por exemplo, a ajuda da frequência de pagamento ajuda você a compreender se o valor de remuneração é especificado como um salário anual versos taxa de pagamento por hora. As frequências de pagamento também são usadas para configurar fatores de conversão para converter valores de remuneração de frequências de pagamento por hora, mensal, semanal, quinzenal para uma frequência de pagamento anual.</td>
</tr>
<tr class="odd">
<td>Regiões de remuneração</td>
<td>As regiões de remuneração são usadas para especificar a remuneração do funcionário com base na localização do local de trabalho.</td>
</tr>
<tr class="even">
<td>Ponto de controle</td>
<td>O ponto de controle define o que você considera ser a taxa de pagamento ideal para todos os funcionários em um nível de remuneração. Para estruturas de plano graduais, os pontos de controle são, em geral, o ponto intermediário das faixas. As estruturas de faixa raramente usam pontos de controle. Você pode especificar o ponto de controle para um plano de remuneração fixa na página **Planos de remuneração fixa**.</td>
</tr>
<tr class="odd">
<td>Funções de trabalho</td>
<td>As funções de trabalho são usadas para classificar e filtrar os planos de remuneração para trabalhos específicos.</td>
</tr>
<tr class="even">
<td>Tipos de trabalho</td>
<td>Os tipos de trabalho são usados para classificar e filtrar os planos de remuneração para trabalhos específicos.</td>
</tr>
<tr class="odd">
<td>Tipos de remuneração variável</td>
<td>Tipos de remuneração variáveis, como ações ou bônus em dinheiro, são aplicados em planos de remuneração variáveis.</td>
</tr>
<tr class="even">
<td>Grades de remuneração</td>
<td>As grades de remuneração contêm a estrutura de remuneração.  As grades de remuneração podem ser usadas por um ou mais planos de remuneração.</td>
</tr>
<tr class="odd">
<td>Planos de desempenho</td>
<td>Os planos de desempenho são usados para associar o desempenho a uma matriz de alocação, para que você possa usar o plano em uma estratégia de pagamento por desempenho.</td>
</tr>
<tr class="even">
<td>Avaliações de desempenho</td>
<td>As avaliações de desempenho são usadas em planos de desempenho para determinar o valor de um prêmio por mérito ou por desempenho.</td>
</tr>
</tbody>
</table>

## <a name="process-events"></a>Eventos de processo
Um evento de processo calcula as informações de remuneração de um determinado período para todos os funcionários que estão inscritos em um ou mais planos de remuneração fixa ou variável. Você pode executar um evento de processo repetidamente para testar ou atualizar os resultados de remuneração calculados.

## <a name="compensation-events"></a>Eventos de remuneração

Toda vez que um processo de evento é executado, um evento de remuneração é criado.  Quando os cálculos estão corretos, você pode carregar o evento de remuneração para atualizar os registros de remuneração para os funcionários afetados pelo evento de processo.  Quando os cálculos estão corretos, você pode carregar o evento de remuneração para atualizar os registros de remuneração para os funcionários afetados pelo evento de processo.

## <a name="recommendations"></a>Recomendações
Depois de executar um evento de processo, você pode recomendar ajustes no aumento de um funcionário por mérito ou no valor do prêmio, com base nas diretrizes calculadas do evento de processo. Para fazer recomendações para funcionários, você deve habilitar as recomendações quando configurar planos de remuneração ou quando configurar o evento de processo.





[!INCLUDE[footer-include](../includes/footer-banner.md)]
