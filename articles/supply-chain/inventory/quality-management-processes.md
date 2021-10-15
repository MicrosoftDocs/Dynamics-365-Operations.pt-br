---
title: Visão geral do gerenciamento de qualidade e não conformidade
description: Este tópico apresenta os recursos de gerenciamento de qualidade e não conformidade no Microsoft Dynamics 365 Supply Chain Management e explica como eles podem ajudar a melhorar a qualidade dos produtos na sua cadeia de suprimentos.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemSampling, InventNonConformanceHistory, InventNonConformanceTable, InventQualityOrderLineResults, InventQualityOrderTable, InventTestCorrection, InventTestDiagnosticType, InventTestInstrument, InventTestReportSetup, InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "11574"
- intro-internal
ms.assetid: 5ac8a059-5cb4-4cb5-ba14-b944bd08dae9
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4e61dd50eb3a91197937ab319479e398c03e0a05
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7568822"
---
# <a name="quality-and-nonconformance-management-overview"></a>Visão geral do gerenciamento de qualidade e não conformidade

[!include [banner](../includes/banner.md)]

Este tópico apresenta os recursos de gerenciamento de qualidade e não conformidade no Microsoft Dynamics 365 Supply Chain Management e explica como eles podem ajudar a melhorar a qualidade dos produtos na sua cadeia de suprimentos.

A garantia da qualidade envolve testes de produto e o gerenciamento de material de não conformidade. Os processos de gerenciamento de qualidade ajudam a garantir um alto nível de qualidade do produto em sua cadeia de suprimentos. Esses processos também ajudam a otimizar os processos da cadeia de suprimentos e a aumentar a satisfação do cliente. O gerenciamento de qualidade pode ajudar você a gerenciar o tempo de resposta ao lidar com produtos não conformes, independentemente do ponto de origem deles. Você pode vincular os resultados de diagnóstico às tarefas de correção. O sistema pode agendar tarefas para corrigir problemas e, portanto, ajuda a prevenir recorrências desses problemas no futuro. Gerenciamento de qualidade também permite acompanhar problemas (incluindo problemas internos) pelo tipo de problema, e permite identificar soluções de curto a longo prazo. As estatísticas sobre os principais indicadores de desempenho (KPIs) fornecem informações sobre os problemas de não conformidade ocorridos anteriormente e as soluções aplicadas para corrigi-los. Você pode usar os dados históricos para examinar a eficácia das medidas de qualidade adotadas anteriormente e para determinar as medidas apropriadas no futuro.

O gerenciamento de qualidade pode ajudar a gerenciar o tempo de resposta ao lidar com produtos fora de conformidade, independentemente do ponto de origem. Como os tipos de diagnóstico são vinculados ao relatório de correção, o Supply Chain Management pode agendar tarefas para corrigir problemas evitar que se repitam.

Além da funcionalidade para gerenciar a não conformidade, o gerenciamento de qualidade inclui uma funcionalidade para rastrear problemas por tipo (mesmo quando os problemas forem internos) e para identificar soluções como sendo de curto ou longo prazo. As estatísticas sobre os principais indicadores de desempenho (KPIs) fornecem ideias sobre o histórico de saídas anteriores de não conformidade e as soluções que foram usadas para corrigi-los. Você pode usar dados históricos para revisar a eficácia das medidas de qualidade anteriores e determinar as medidas apropriadas a serem usadas no futuro.

Ao configurar uma associação de qualidade, o Supply Chain Management pode gerar ordens de qualidade para vários processos comerciais, eventos, e condições. A associação de qualidade pode cobrir item específico, um grupo específico de itens ou todos os itens.

## <a name="examples-of-the-use-of-quality-management"></a>Exemplo de utilização do gerenciamento de qualidade

O gerenciamento de qualidade é flexível e pode ser implementado de várias maneiras para atender aos requisitos de níveis específicos das operações da cadeia de suprimento. Os exemplos a seguir ilustram as possíveis aplicações destes recursos:

- Iniciar automaticamente um processo de controle de qualidade com base em critérios pré-definidos (por exemplo, quando o registro do depósito de uma ordem de compra de um fornecedor específico ocorrer).
- Bloquear o estoque durante a inspeção para evitar que o estoque não aprovado seja utilizado (bloqueio total das quantidades da ordem de compra).
- Use a amostragem do item como parte de uma associação de qualidade para definir o valor de estoque físico atual que deve ser inspecionado. A amostragem pode se basear em quantidades fixas, em uma porcentagem ou em uma placa de licença completa.
- Crie ordens de qualidade para recebimentos parciais. Para criar uma ordem de qualidade baseada na quantidade fisicamente recebida com uma ordem, marque a caixa de seleção **Por quantidade atualizada** na página **Amostragem de item**.
- Crie tipos de teste que incluem valores de teste mínimos, máximos, e de destino, e realizar testes qualitativos versos quantitativos que possuem resultados de validação pré-definidos.
- Especifique um nível de qualidade aceitável (AQL) para controlar as tolerâncias da medição de qualidade.
- Especifique os recursos que uma operação de inspeção requer, como uma área de teste e instrumentos de teste.

> [!NOTE]
> O recurso _Gerenciamento de qualidade para processos de depósito_ estende as possibilidades de gerenciamento de qualidade. Se você estiver usando esse recurso, consulte [Gerenciamento de qualidade para processos de depósito](quality-management-for-warehouses-processes.md) para obter exemplos que mostram como o gerenciamento de qualidade funciona quando habilitado.

## <a name="controlling-the-quality-management-process"></a>Controlando o processo de gerenciamento de qualidade

Veja a seguir algumas das maneiras a qual você pode controlar o processo de gerenciamento de qualidade:

- Crie ordens de qualidade baseadas em pontos de gatilho, como “no recebimento de produtos” para operações de entrada ou “na coleta de produtos” para operações de saída.
- Documente os resultados do teste e determine se eles atendem aos critérios de teste estabelecidos e aos AQLs.
- Use o gerenciamento de documentos para especificações detalhadas de produtos e anotações específicas do usuário como parte do relatório durante o processo de inspeção.
- Mantenha os produtos que não estão em conformidade e correlacione esses produtos a informações adicionais de não conformidade para rastrear a causa original de um problema.
- Documente o custo de gerenciamento de uma não conformidade. Esse custo pode incluir os itens (como as peças sobressalentes), os encargos diversos e as horas da folha de ponto necessárias para corrigir a não conformidade.
- Agente os processos de correção de erros usando o tratamento de correção vinculado a ordens de qualidade.

[![Processo de gerenciamento de qualidade.](media/quality-management-process-diagram.png)](media/quality-management-process-diagram.png)

## <a name="product-testing-and-quality-orders"></a>Testes de produto e ordens de qualidade

Os testes de produto geralmente são chamados de controle de qualidade e usam ordens de qualidade. Usando a funcionalidade de controle de qualidade, você pode fazer o seguinte:

- Defina os testes que devem ser realizados para o material. Esses testes incluem as especificações de qualidade, o instrumento de teste aplicável, os documentos que descrevem o teste, um plano de amostragem e os AQLs.
- Crie uma ordem de qualidade que identifique os testes que devem ser realizados para uma ordem específica, como uma ordem de compra ou de produção, ou para uma quantidade de estoque específica. Você pode criar manualmente uma ordem de qualidade ou ela pode ser gerada de forma automática com base em diretrizes de qualidade.
- Defina as diretrizes de qualidade relacionadas a ordens de compra, de quarentena, de produção ou de venda em cada processo empresarial, de forma que uma ordem de qualidade que identifique os requisitos de teste para materiais de entrada ou de saída possa ser gerada automaticamente.
- Registre os resultados do teste em uma ordem de qualidade, valide os resultados do teste em relação ao AQL e imprima um certificado de análise que mostre os resultados do teste.

## <a name="nonconformance"></a>Não conformidade

Uma não conformidade descreve um item com um problema de qualidade. O processo de não conformidade permite que você crie uma ordem de não conformidade que descreve uma quantidade de material de não conformidade, a origem do problema, o tipo de problema e as notas explicativas. Você pode definir uma classificação de tipos de problema para facilitar a análise de materiais não conformes. Você também pode imprimir uma marca de não conformidade e um relatório de não conformidade para orientar a disposição de materiais não conformes. Por exemplo, a etiqueta e o relatório podem indicar uma condição **Inutilizável** ou **Uso restrito**.

A tabela a seguir lista os seis tipos padrão de não conformidade e descreve as informações que devem ser registradas para cada tipo.

| Tipo de não conformidade | Informações de origem |
|---|---|
| Cliente | O número da conta de cliente, o número da ordem de venda ou o número do lote de uma transação de ordem de venda. Por exemplo, a não conformidade pode estar relacionada a uma remessa de uma ordem de venda específica ou a comentários do cliente sobre a qualidade do produto. |
| Solicitação de serviço | O número da conta de cliente, o número da ordem de venda ou o número do lote de uma transação de ordem de venda. Por exemplo, a não conformidade pode estar relacionada a uma remessa de uma ordem de venda específica ou a reclamações de um cliente sobre a qualidade do item. |
| Fornecedor | O número da conta de fornecedor, número da ordem de compra ou o número do lote de uma transação de ordem de compra. Por exemplo, a não conformidade por estar relacionada a um recebimento de ordem de compra ou a uma preocupação do fornecedor sobre uma peça que ele fornece. |
| Produção | O número da ordem de produção ou o número de um lote de uma transação de ordem de produção. Por exemplo, a não conformidade pode estar relacionada a um lote produzido específico. |
| Interno | O número da ordem de qualidade ou o número de um lote de uma transação de ordem de qualidade. Por exemplo, a não conformidade pode estar relacionada aos testes realizados como parte de uma ordem de qualidade ou à preocupação de um funcionário a respeito da qualidade do produto. |
| Produção de coprodutos | Uma não conformidade da ordem de produção de coproduto que esteja relacionada em lotes para processar ordens de produção. |

As não conformidades são associadas a um tipo de problema. Os tipos de problema são definidos na página **Tipos de problema**, onde você especifica quais tipos de problema podem ser associados a cada tipo de não conformidade. Por exemplo, os tipos de problema para não conformidades do tipo **Solicitação de serviço** podem refletir uma classificação de reclamações de clientes, enquanto os tipos de problema para não conformidades do tipo **Interno** podem representar uma classificação de códigos de defeito.

Quando você cria uma nova não conformidade, seleciona o tipo de não conformidade e o tipo de problema. O status de aprovação inicial é **Novo**, que representa uma solicitação de ação. A próxima etapa será alterar o status de aprovação para **Aprovado** ou **Recusado** para indicar que você tomará ou não ações em relação à não conformidade. Também é possível fechar uma não conformidade (ao marcar por uma caixa de seleção separada) para indicar que a concluiu ou você pode reabrir uma não conformidade para indicar que ela exige mais atenção.

Você pode inserir comentários para uma não conformidade ao anexar um documento. É recomendável definir um tipo de documento exclusivo para não conformidades usando a página **Tipo de documento**. Você pode então usar a página **Configuração de relatório** para definir se os comentários para esse tipo de documento devem ser impressos na etiqueta do relatório de não conformidade e de não conformidade. O relatório de conformidade e a etiqueta de não conformidade podem ajudar na disposição do material. Você pode gerar seletivamente relatórios e etiquetas com base nos critérios de seleção associados a uma não conformidade. Esses critérios incluem o número, o item, o cliente, o fornecedor, e o status da não conformidade.

O relatório de não conformidade exibe o número, o item, e o tipo de problema da não conformidade. Dependendo da política de configuração de relatório, o relatório também pode exibir anotações relacionadas sobre a não conformidade. A etiqueta de não conformidade exibe informações semelhantes, além de incluir a zona e o tipo de quarentena (como **Uso restrito** ou **Inutilizável**) atribuídos à não conformidade para ajudar a orientar a disposição do material defeituoso.

## <a name="approved-nonconformance"></a>Não conformidade aprovada

Opcionalmente, você pode definir uma ou mais operações relacionadas para uma não conformidade aprovada. Uma operação relacionada descreve o trabalho que deve ser executado, e contém uma lista de operações de qualidade definidas por você e texto descritivo sobre o motivo do trabalho. Depois de definir uma operação, você pode definir os encargos diversos, os itens e horas de mão-de-obra de folha de ponto necessários para realizar o trabalho. Os custos calculados são mostrados para a operação relacionada e os custos calculados totais são mostrados para a não conformidade. Os custos calculados e os detalhes subjacentes (sobre itens, horas de trabalho, encargos diversos) representam informações de referência e são usados somente em função de gerenciamento de qualidade.

Você pode, opcionalmente, criar uma ordem de qualidade de uma não conformidade fazendo, primeiro, uma consulta sobre ordens de qualidade e, depois, criando a nova ordem de qualidade. Por exemplo, uma ordem de qualidade poderia identificar a necessidade de testar (ou de repetir testes) o material defeituoso. A ordem de qualidade recém-criada exibe o link para a não conformidade original.

Você pode vincular uma não conformidade a outra e criar uma nova não conformidade a partir de uma existente. Por exemplo, o link pode refletir a interconexão entre os problemas de qualidade.

## <a name="correction-handling"></a>Manuseio de correção

A página **Correções** permite criar uma lista de não conformidades que devem ser corrigidas. Cada item da correção é associado ao tipo de diagnóstico que causou a identificação do problema. A página **Correções** também contém informações sobre quem deve realizar uma ação corretiva e quando. Você pode descrever os detalhes do problema e da ação corretiva necessária anexando um documento à correção. Depois que a não conformidade tiver sido tratada ou corrigida, você "fechará" o item de correção ao selecionar a opção **Concluído**. Você também pode indicar que a solução foi uma solução de curto prazo.

É recomendável definir um tipo de documento exclusivo para correões usando a página **Tipo de documento**. Você pode então usar a página **Configuração de relatório** para definir se os comentários para esse tipo de documento serão impressos no relatório de correção. Um relatório impresso de correção exibe informações sobre a não conformidade e as anotações relacionadas de não conformidade. O relatório também inclui informações de correção, como o tipo de diagnóstico, e as anotações de correção relacionadas.

## <a name="additional-resources"></a>Recursos adicionais

- [Habilitar gerenciamento de qualidade e não conformidade](enable-quality-management.md)
- [Bloqueio de estoque](inventory-blocking.md)
- [Ordens de quarentena](quarantine-orders.md)
- [Verificar a qualidade de mercadorias](tasks/inspect-quality-goods.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
