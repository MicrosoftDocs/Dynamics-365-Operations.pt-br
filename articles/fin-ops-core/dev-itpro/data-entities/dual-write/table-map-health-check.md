---
title: Códigos de erro para a verificação de integridade do mapa de tabelas
description: Este artigo descreve os códigos de erro para a verificação de integridade do mapa de tabela.
author: RamaKrishnamoorthy
ms.date: 05/31/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-10-04
ms.openlocfilehash: 16c79a788b66830b77b2cdfb33fd2416c530f7d2
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111556"
---
# <a name="errors-codes-for-the-table-map-health-check"></a>Códigos de erro para a verificação de integridade do mapa de tabelas

[!include [banner](../../includes/banner.md)]



Este artigo descreve os códigos de erro para a verificação de integridade do mapa de tabela.

## <a name="error-100"></a>Erro 100

A mensagem de erro é "A versão mínima necessária da plataforma de finanças e operações é a PU 43 para executar as recomendações de finanças e operações".

O recurso requer atualizações de plataforma para a versão 10.0.19 ou posterior dos aplicativos de finanças e operações.

## <a name="error-400"></a>Erro 400

A mensagem de erro é "Não foram encontrados dados de registro de eventos de negócios para a entidade \{finance and operations UniqueEntityName\} o que significa que o mapa não está em execução ou que todos os mapeamentos de campos são unidirecionais."

## <a name="error-500"></a>Erro 500

A mensagem de erro é "Nenhuma configuração de projeto encontrada para o projeto \{nome do projeto\}. Isso pode ocorrer em decorrência de o projeto não estar habilitado ou todos os mapeamentos de campos serem unidirecionais de engajamento do cliente para finanças e operações."

Verifique os mapeamentos para o mapa de tabelas. Se eles forem unidirecionais de aplicativos de engajamento do cliente para aplicativos de finanças e operações, nenhum tráfego será gerado para sincronização dinâmica de aplicativos de finanças e operações para o Dataverse.

## <a name="error-900"></a>Erro 900

A mensagem de erro é, "Formato de filtro de origem inválido \{sourceFilter\} para a entidade \{finance and operations UniqueEntityName\}."

O filtro de origem especificado no mapa de tabelas para aplicativos de finanças e operações não está sintaticamente correto. Para validar os critérios de filtragem, consulte [Solucionar problemas de sincronização dinâmica](dual-write-troubleshooting-live-sync.md#live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps).

## <a name="error-1000"></a>Erro 1000

A mensagem de erro é, "A consulta da entidade \{finance and operations UniqueEntityName\} usada para a sincronização dinâmica da gravação dupla é \{finance and operations EntityFilterQueryString\}. Os registros que atendem aos critérios da consulta serão retirados para a sincronização dinâmica".

A consulta de entidade que foi retornada é a consulta SQL de backup da entidade. Verifique se há junções internas ou filtros na consulta que determinam os dados comerciais que estão sendo retirados para sincronização dinâmica. As junções internas e os filtros são condições obrigatórias que devem ser executadas para cada registro que está sendo retirado para a sincronização dinâmica de duas gravações.

## <a name="error-1300"></a>Erro 1300

A mensagem de erro é, "Os campos virtuais \{s.EntityFieldName\} da entidade \{finance and operations EntityMetadata.EntityProperties.LogicalEntityName\} talvez não sejam rastreados para a gravação dupla."

Os campos virtuais de tabelas de finanças e operações não estão habilitados para rastreamento. A sincronização dinâmica pode sincronizar os dados, mas não poderá retirar as alterações feitas nas colunas.

## <a name="error-1500"></a>Erro 1500

A mensagem de erro é "Deve haver pelo menos um campo mapeado para um campo que não é de pesquisa no Customer Engagement para habilitar o rastreamento na fonte de dados \{datasource.DataSourceName\}".

A fonte de dados da entidade não tem nenhum campo mapeado para gravação dupla. As alterações na tabela subjacente não serão rastreadas para gravação dupla.

## <a name="error-1600"></a>Erro 1600

A mensagem de erro é, "A fonte de dados: \{datasource.DataSourceName\} para a entidade \{finance and operations EntityMetadata.EntityProperties.LogicalEntityName\} tem um intervalo. Somente os registros que satisfazem a condição de intervalo são retirados para saída".

As entidades em aplicativos de finanças e operações podem ter fontes de dados nas quais os intervalos de filtros estão habilitados. Esses intervalos definem os registros que são retirados como parte da sincronização dinâmica. Se alguns registros forem ignorados de aplicativos de finanças e operações para o Dataverse, verifique se os registros atendem aos critérios de intervalo na entidade. Uma maneira simples de fazer isso é executar uma consulta SQL que se assemelhe ao exemplo a seguir.

```sql
select * from <EntityName> where <filter criteria for the records> on SQL.
```

## <a name="error-1700"></a>Erro 1700

A mensagem de erro é "A tabela: \{datasourceTable.Key.subscribedTableName\} for entity \{datasourceTable.Key.entityName\} é rastreada para a entidade \{origTableToEntityMaps.EntityName\}. As mesmas tabelas rastreadas para várias entidades podem afetar o desempenho do sistema para transações de sincronização dinâmica".

Se a mesma tabela for controlada por várias entidades, qualquer alteração na tabela irá disparar uma avaliação de gravação dupla para as entidades vinculadas. Embora as cláusulas de filtro enviem somente os registros válidos, a avaliação poderá causar um problema de desempenho se houver consultas de longa duração ou planos de consulta não otimizados. Esse problema pode não ser evitável da perspectiva comercial. No entanto, se houver muitas tabelas de interseção em várias entidades, considere a simplificação da entidade ou a verificação de otimizações para consultas a entidades.

## <a name="error-1800"></a>Erro 1800
A mensagem de erro é, "Fonte de dados: {} para a entidade CustCustomerV3Entity inclui um valor de intervalo. O registro de entrada que faz upsert do Dataverse para finanças e operações pode ser afetado por valores de intervalo na entidade. Teste atualizações de registros do Dataverse para finanças e operações com registros que não correspondam aos critérios de filtro para validar suas configurações."

Se houver um intervalo especificado na entidade em aplicativos de finanças e operações, a sincronização de entrada de aplicativos do Dataverse para finanças e operações deverá ser testada para o comportamento de atualização nos registros que não correspondem a este critério de intervalo. Qualquer registro que não seja compatível com o intervalo será tratado como uma operação de inserção pela entidade. Se houver um registro existente na tabela subjacente, a inserção falhará. É recomendável testar esse caso de uso para todos os cenários antes de implantá-lo na produção.

## <a name="error-1900"></a>Erro 1900
A mensagem de erro é "Entidade: contém {} fontes de dados que não estão sendo rastreadas para gravação dupla de saída. Isso pode afetar o desempenho das consultas de sincronização dinâmica. Remodele a entidade em finanças e operações para remover fontes de dados e tabelas não usadas ou implementar getEntityRecordIdsImpactedByTableChange para otimizar as consultas em tempo de execução.

Se houver várias fontes de dados que não estiverem sendo usadas para rastreamento na sincronização dinâmica real dos aplicativos de finanças e operações, há uma possibilidade de que o desempenho da entidade possa afetar a sincronização dinâmica. Para otimizar as tabelas rastreadas, use o método getEntityRecordIdsImpactedByTableChange.

## <a name="error-5000"></a>Erro 5000
A mensagem de erro é: "Os plug-ins síncronos são registrados para eventos de gerenciamento de dados para contas de entidade. Eles podem afetar o desempenho da importação da sincronização dinâmica e sincronização inicial no Dataverse. Para obter melhor desempenho, altere os plug-ins para processamento assíncrono. Lista de plug-ins registrados {}."

Os plug-ins síncronos em uma entidade do Dataverse podem afetar o desempenho da sincronização inicial e da sincronização dinâmica, uma vez que adicionam dados ao carregamento da transação. A abordagem recomendada é desativar os plug-ins ou torná-los assíncronos se estiver enfrentando tempos de carregamento lentos na sincronização inicial ou sincronização dinâmica para uma entidade específica.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

