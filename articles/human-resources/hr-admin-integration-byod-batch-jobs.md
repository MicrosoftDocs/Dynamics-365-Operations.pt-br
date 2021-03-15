---
title: Otimizar trabalhos em lote agendados de BYOD
description: Este tópico explica como otimizar o desempenho quando estiver usando o recurso Trazer seu próprio banco de dados (BYOD) com o Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 08/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-08-10
ms.dyn365.ops.version: Platform update 36
ms.openlocfilehash: 4b9cf4b4181b64ef4daf397edd852fb2f881424e
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5111410"
---
# <a name="optimize-byod-scheduled-batch-jobs"></a>Otimizar trabalhos em lote agendados de BYOD

Este tópico explica como otimizar o desempenho quando estiver usando o recurso Trazer seu próprio banco de dados (BYOD). Para obter mais informações sobre o BYOD, consulte [Trazer seu próprio banco de dados (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database?toc=/dynamics365/human-resources/toc.json).

## <a name="performance-considerations-for-data-export"></a>Considerações de desempenho para exportação de dados

Depois que as entidades são publicadas no banco de dados de destino, você pode usar a função de Exportação no espaço de trabalho **Gerenciamento de dados** para mover os dados. A função Exportar permite definir um trabalho de Movimentação de dados que contém uma ou mais entidades. Para obter mais informações sobre exportação de dados, consulte [Visão geral de trabalhos de importação e exportação de dados](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job?toc=/dynamics365/human-resources/toc.json).

Você pode usar a página **Exportar** para exportar dados para diferentes formatos de dados de destino, como um arquivo CSV (valores separados por vírgulas). Essa página também oferece suporte a bancos de dados SQL como outro destino.

Você pode criar um projeto de dados que tenha várias entidades e use um trabalho em lotes para programar o projeto de dados a ser executado. Se você selecionar a opção **Exportar no lote**, poderá agendar o trabalho de exportação de dados para ser executado periodicamente.

Para ajudar a preservar a confiabilidade geral da exportação do BYOD, você deve ter cuidado ao adicionar várias entidades a um projeto de exportação. Ao determinar o número de entidades a serem adicionadas ao mesmo projeto, considere os seguintes parâmetros:

- A complexidade das entidades
- O volume de dados esperado por entidade
- O tempo geral que será necessário para concluir a exportação no nível do trabalho

Para obter o melhor desempenho, evite adicionar centenas de entidades a um único projeto. É recomendável criar vários trabalhos, cada um com menos entidades.

## <a name="scheduling-byod-batch-jobs"></a>Agendando trabalhos em lote de BYOD

Para ajudar a reduzir o impacto sobre os usuários do Microsoft Dynamics 365 Human Resources, execute os trabalhos em lotes de BYOD à noite ou após horas. Verifique o fuso horário desses trabalhos em lotes recorrentes. Alguns trabalhos em lotes podem usar o Horário Padrão do Pacífico (PST).

Para ajudar a evitar problemas de desempenho, considere os seguintes fatores ao configurar a frequência de agendamento para trabalhos em lotes de BYOD:

- O tempo necessário para concluir cada trabalho em lotes
- A necessidade comercial dos dados no BYOD

Defina a frequência de cada trabalho em lotes para um valor que garanta que o trabalho pode ser concluído bem antes do próximo horário de execução agendado. Evite executar vários trabalhos em paralelo, pois essa abordagem pode afetar negativamente o desempenho de Recursos Humanos.

Para obter o melhor desempenho, use sempre a opção **Exportar no lote** na página **Exportar** para agendar trabalhos em lotes de BYOD. Evite agendar exportações recorrentes em **Gerenciar \> Gerenciar trabalhos de dados recorrentes**.

## <a name="incremental-export"></a>Exportação incremental

Ao adicionar uma entidade para exportação de dados, você pode fazer um push incremental (exportação) ou um push completo. Um push completo exclui todos os registros existentes de uma entidade do banco de dados do BYOD. Em seguida, o insere o conjunto atual de registros da entidade de Recursos Humanos.

Para fazer um envio incremental, você deve habilitar o controle de alterações para cada entidade na página **Entidades**. Para obter mais informações, consulte [Habilitar controle de alterações para entidades](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-change-track?toc=/dynamics365/human-resources/toc.json).

Se você selecionar um push incremental, o primeiro push será sempre um push completo. O SQL controla as alterações desse primeiro push completo. Quando um novo registro é inserido ou quando um registro é atualizado ou excluído, a alteração é refletida na entidade de destino.

## <a name="time-outs"></a>Tempo limite

Estes são os tempos limite padrão para exportações de BYOD:

- Dez minutos para operações de truncamento
- Uma hora para operações de inserção em massa

Quando os volumes são altos, essas configurações de tempo limite podem não ser suficientes. Para atualizá-los, vá para **Gerenciamento de dados \> Parâmetros de estrutura \> Trazer seu próprio banco de dados**. Esses tempos limites são específicos da empresa e devem ser definidos separadamente para cada empresa.

## <a name="known-limitations"></a>Limitações conhecidas

O recurso de BYOD tem as seguintes limitações:

- Não deve haver bloqueios ativos no seu banco de dados durante a sincronização. Bloqueios ativos podem causar gravações lentas ou até mesmo falhas na exportação de dados para o banco de dado SQL do Azure.
- Não é possível exportar entidades compostas para o seu próprio banco de dados. No momento, não há suporte para entidades compostas. Você deve exportar entidades individuais que compõem a entidade composta. No entanto, você pode exportar ambas as entidades no mesmo projeto de dados.
- Entidades que não têm chaves exclusivas não podem ser exportadas usando o push incremental. Você pode enfrentar essa limitação, especialmente ao tentar exportar incrementalmente registros de algumas entidades prontas. Como essas entidades foram criadas para habilitar a importação de dados, elas não têm uma chave exclusiva.

## <a name="troubleshooting"></a>Solução de problemas

### <a name="incremental-push-doesnt-work-correctly"></a>A expansão incremental não funciona corretamente

**Problema:** Quando um push completo ocorre para uma entidade, você vê um grande conjunto de registros no BYOD quando usa uma instrução **Select**. No entanto, ao fazer um push incremental, você verá apenas alguns registros no BYOD. Parece que o push incremental excluiu todos os registros e adicionou somente os registros alterados em BYOD.

**Solução:** As tabelas de controle de alterações do SQL podem não estar no estado esperado. Em casos desse tipo, recomendamos que você desative o controle de alterações para a entidade e ative-o novamente. Para obter mais informações, consulte [Habilitar controle de alterações para entidades](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-change-track?toc=/dynamics365/human-resources/toc.json).

## <a name="see-also"></a>Consulte também

[Visão geral do gerenciamento de dados](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities-data-packages?toc=/dynamics365/human-resources/toc.json)<br>
[Trazer seu próprio banco de dados (BYOD)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database?toc=/dynamics365/human-resources/toc.json)<br>
[Visão geral de trabalhos de importação e exportação de dados](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-import-export-job?toc=/dynamics365/human-resources/toc.json)<br>
[Habilitar o controle de alterações para entidades](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/entity-change-track?toc=/dynamics365/human-resources/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]