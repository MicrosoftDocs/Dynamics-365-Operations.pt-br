---
title: Códigos de erro para a verificação de integridade do mapa de tabelas
description: Este tópico descreve os códigos de erro para a verificação de integridade do mapa de tabela.
author: nhelgren
ms.date: 10/04/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: nhelgren
ms.search.validFrom: 2021-10-04
ms.openlocfilehash: 916f3cfca3bae7a073ce4e956a12080ee01c8d31
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8061269"
---
# <a name="errors-codes-for-the-table-map-health-check"></a>Códigos de erro para a verificação de integridade do mapa de tabelas

[!include [banner](../../includes/banner.md)]



Este tópico descreve os códigos de erro para a verificação de integridade do mapa de tabela.

## <a name="error-100"></a>Erro 100

A mensagem de erro é "A versão mínima necessária da plataforma de Finanças e Operações é a PU 43 para executar as recomendações de Finanças e Operações".

O recurso requer atualizações de plataforma para a versão 10.0.19 ou posterior dos aplicativos de Finanças e Operações.

## <a name="error-400"></a>Erro 400

A mensagem de erro é "Não foram encontrados dados de registro de eventos de negócios para a entidade \{Finance and Operations UniqueEntityName\} o que significa que o mapa não está em execução ou que todos os mapeamentos de campos são unidirecionais."

## <a name="error-500"></a>Erro 500

A mensagem de erro é "Nenhuma configuração de projeto encontrada para o projeto \{nome do projeto\}. Isso pode ocorrer em decorrência de o projeto não estar habilitado ou todos os mapeamentos de campos serem unidirecionais de engajamento do cliente para Finanças e Operações."

Verifique os mapeamentos para o mapa de tabelas. Se eles forem unidirecionais de aplicativos de engajamento do cliente para aplicativos de Finanças e Operações, nenhum tráfego será gerado para sincronização dinâmica de aplicativos de Finanças e Operações para o Dataverse.

## <a name="error-900"></a>Erro 900

A mensagem de erro é, "Formato de filtro de origem inválido \{sourceFilter\} para a entidade \{Finance and Operations UniqueEntityName\}."

O filtro de origem especificado no mapa de tabelas para aplicativos de Finanças e Operações não está sintaticamente correto. Para validar os critérios de filtragem, consulte [Solucionar problemas de sincronização dinâmica](dual-write-troubleshooting-live-sync.md#live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps).

## <a name="error-1000"></a>Erro 1000

A mensagem de erro é, "A consulta da entidade \{Finance and Operations UniqueEntityName\} usada para a sincronização dinâmica da gravação dupla é \{Finance and Operations EntityFilterQueryString\}. Os registros que atendem aos critérios da consulta serão retirados para a sincronização dinâmica".

A consulta de entidade que foi retornada é a consulta SQL de backup da entidade. Verifique se há junções internas ou filtros na consulta que determinam os dados comerciais que estão sendo retirados para sincronização dinâmica. As junções internas e os filtros são condições obrigatórias que devem ser executadas para cada registro que está sendo retirado para a sincronização dinâmica de duas gravações.

## <a name="error-1300"></a>Erro 1300

A mensagem de erro é, "Os campos virtuais \{s.EntityFieldName\} da entidade \{Finance and Operations EntityMetadata.EntityProperties.LogicalEntityName\} talvez não sejam rastreados para a gravação dupla."

Os campos virtuais de tabelas de Finanças e Operações não estão habilitados para rastreamento. A sincronização dinâmica pode sincronizar os dados, mas não poderá retirar as alterações feitas nas colunas.

## <a name="error-1500"></a>Erro 1500

A mensagem de erro é "Deve haver pelo menos um campo mapeado para um campo que não é de pesquisa no Customer Engagement para habilitar o rastreamento na fonte de dados \{datasource.DataSourceName\}".

A fonte de dados da entidade não tem nenhum campo mapeado para gravação dupla. As alterações na tabela subjacente não serão rastreadas para gravação dupla.

## <a name="error-1600"></a>Erro 1600

A mensagem de erro é, "A fonte de dados: \{datasource.DataSourceName\} para a entidade \{Finance and Operations EntityMetadata.EntityProperties.LogicalEntityName\} tem um intervalo. Somente os registros que satisfazem a condição de intervalo são retirados para saída".

As entidades em aplicativos de Finanças e Operações podem ter fontes de dados nas quais os intervalos de filtros estão habilitados. Esses intervalos definem os registros que são retirados como parte da sincronização dinâmica. Se alguns registros forem ignorados de aplicativos de Finanças e Operações para o Dataverse, verifique se os registros atendem aos critérios de intervalo na entidade. Uma maneira simples de fazer isso é executar uma consulta SQL que se assemelhe ao exemplo a seguir.

```sql
select * from <EntityName> where <filter criteria for the records> on SQL.
```

## <a name="error-1700"></a>Erro 1700

A mensagem de erro é "A tabela: \{datasourceTable.Key.subscribedTableName\} for entity \{datasourceTable.Key.entityName\} é rastreada para a entidade \{origTableToEntityMaps.EntityName\}. As mesmas tabelas rastreadas para várias entidades podem afetar o desempenho do sistema para transações de sincronização dinâmica".

Se a mesma tabela for controlada por várias entidades, qualquer alteração na tabela irá disparar uma avaliação de gravação dupla para as entidades vinculadas. Embora as cláusulas de filtro enviem somente os registros válidos, a avaliação poderá causar um problema de desempenho se houver consultas de longa duração ou planos de consulta não otimizados. Esse problema pode não ser evitável da perspectiva comercial. No entanto, se houver muitas tabelas de interseção em várias entidades, considere a simplificação da entidade ou a verificação de otimizações para consultas a entidades.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]