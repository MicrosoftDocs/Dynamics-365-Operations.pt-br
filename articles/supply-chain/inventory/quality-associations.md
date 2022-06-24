---
title: Associações de qualidade
description: Este artigo descreve como você pode usar associações de qualidade no Microsoft Dynamics 365 Supply Chain Management para gerar automaticamente ordens de qualidade relacionadas a seus processos de venda, compra e produção.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4e96f301d8dec255e57f0f0fbfa9c8e1a5922ae9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887505"
---
# <a name="quality-associations"></a>Associações de qualidade

[!include [banner](../includes/banner.md)]

Este artigo descreve como você pode usar associações de qualidade no Microsoft Dynamics 365 Supply Chain Management para gerar automaticamente ordens de qualidade relacionadas a seus processos de venda, compra e produção.

Uma associação de qualidade define todas as informações a seguir para uma ordem de qualidade que é gerada:

- O evento da transação
- O conjunto de testes que devem ser executados nos itens
- O nível de qualidade aceitável (AQL)
- O plano de amostragem

É necessário definir uma associação de qualidade para cada variação em um processo comercial que requer a geração automática de ordens de qualidade. Por exemplo, uma ordem de qualidade pode ser gerada nos processos comerciais para ordens de compra, ordens de quarentena, ordens de venda, e ordens de produção.

## <a name="working-with-quality-associations"></a>Trabalhando com associações de qualidade

O processo comercial que utiliza uma associação de qualidade pode estar relacionado a diversos documentos de origem, como ordens de compra, ordens de venda, ou ordens de produção.

Cada registro de associação de qualidade também define o conjunto de testes, o nível de qualidade aceitável (AQL) e o plano de amostragem que se aplicam às ordens de qualidade geradas. Um registro de associação de qualidade deve ser definido para cada variação em um processo de negócios. Por exemplo, você pode configurar uma associação de qualidade que gera uma ordem de qualidade quando um recebimento de produto da ordem de produção é atualizado. Dependendo da configuração do plano de execução, o próprio processo de disparo pode ser bloqueado enquanto houver uma ordem de qualidade aberta. Como alternativa, processos subsequentes, como o faturamento de ordens de compra, podem ser bloqueados.

> [!NOTE]
> Enquanto houver ordens de qualidade abertas, as quantidades de estoque serão automaticamente impedidas de serem fornecidas. Dependendo da configuração do campo **Bloqueio total** na página **Amostragens de item**, a quantidade será a quantidade na ordem de qualidade ou a quantidade na linha do documento de origem. Para obter mais informações, consulte [Amostragem de item de gerenciamento de qualidade](quality-item-sampling.md).

Para um determinado processo empresarial, o registro de associação de qualidade identifica o evento e as condições para os quais uma ordem de qualidade é gerada. As condições podem ser específicas para um site ou uma entidade legal. Uma ordem de qualidade que envolve testes destrutivos podem ser geradas somente quando existir um estoque para o evento.

Para trabalhar com associações de qualidade, Acesse **Gerenciamento de estoque \> Configuração \> Controle de qualidade \> Associações de qualidade**. Os exemplos a seguir mostram como um registro de associação de qualidade é definido para as variações em cada processo empresarial. Para cada exemplo, a tabela a seguir resume os eventos e as condições que são definidas por um registro de associação de qualidade.

<table>
<thead>
<tr>
<th>Tipo de referência</th>
<th>Tipo de evento</th>
<th>Execução</th>
<th>Bloqueio do evento</th>
<th>Referência de documento</th>
</tr>
</thead>
<tbody>
<tr>
<td>Estoque</td>
<td>Não aplicável</td>
<td>Não aplicável</td>
<td>Nenhum</td>
<td>Tudo</td>
</tr>
<tr>
<td rowspan="7">Venda</td>
<td rowspan="4">O processo de separação está agendado</td>
<td rowspan="4">Antes</td>
<td>Nenhum</td>
<td rowspan="22">ID específica, Grupo, ou Todos apenas</td>
</tr>
<tr>
<td>Processo de separação</td>
</tr>
<tr>
<td>Guia de remessa</td>
</tr>
<tr>
<td>Fatura</td>
</tr>
<tr>
<td rowspan="3">Guia de remessa</td>
<td rowspan="3">Antes</td>
<td>Nenhum</td>
</tr>
<tr>
<td>Guia de remessa</td>
</tr>
<tr>
<td>Fatura</td>
</tr>
<tr>
<td rowspan="15">Compra</td>
<td rowspan="7">Lista de recebimentos</td>
<td rowspan="4">Antes</td>
<td>Nenhum</td>
</tr>
<tr>
<td>Lista de recebimentos</td>
</tr>
<tr>
<td>Recebimento de produtos</td>
</tr>
<tr>
<td>Fatura</td>
</tr>
<tr>
<td rowspan="3">Depois</td>
<td>Nenhum</td>
</tr>
<tr>
<td>Recebimento de produtos</td>
</tr>
<tr>
<td>Fatura</td>
</tr>
<tr>
<td rowspan="3">Registro</td>
<td rowspan="3">Não aplicável</td>
<td>Nenhum</td>
</tr>
<tr>
<td>Recebimento de produtos</td>
</tr>
<tr>
<td>Fatura</td>
</tr>
<tr>
<td rowspan="5">Recebimento de produtos</td>
<td rowspan="3">Antes</td>
<td>Nenhum</td>
</tr>
<tr>
<td>Recebimento de produtos</td>
</tr>
<tr>
<td>Fatura</td>
</tr>
<tr>
<td rowspan="2">Depois</td>
<td>Nenhum</td>
</tr>
<tr>
<td>Fatura</td>
</tr>
<tr>
<td rowspan="8">Produção</td>
<td rowspan="3">Registro</td>
<td rowspan="3">Não aplicável</td>
<td>Nenhum</td>
<td rowspan="12">Tudo</td>
</tr>
<tr>
<td>Relatar como concluído</td>
</tr>
<tr>
<td>Encerrar</td>
</tr>
<tr>
<td rowspan="5">Relatar como concluído</td>
<td rowspan="3">Antes</td>
<td>Nenhum</td>
</tr>
<tr>
<td>Relatar como concluído</td>
</tr>
<tr>
<td>Encerrar</td>
</tr>
<tr>
<td rowspan="2">Depois</td>
<td>Nenhum</td>
</tr>
<tr>
<td>Encerrar</td>
</tr>
<tr>
<td rowspan="4">Quarentena</td>
<td rowspan="3">Relatar como concluído</td>
<td rowspan="2">Antes</td>
<td>Relatar como concluído</td>
</tr>
<tr>
<td>Encerrar</td>
</tr>
<tr>
<td>Depois</td>
<td>Encerrar</td>
</tr>
<tr>
<td>Encerrar</td>
<td>Antes</td>
<td>Encerrar</td>
</tr>
<tr>
<td rowspan="3">Operação do roteiro</td>
<td rowspan="3">Relatório de Conclusão</td>
<td rowspan="2">Antes</td>
<td>Nenhuma</td>
<td rowspan="3">ID específica, Grupo ou Todos, e Recurso específico, Grupo ou Todos</td>
</tr>
<tr>
<td>Relatório de Conclusão</td>
</tr>
<tr>
<td>Após</td>
<td>Nenhuma</td>
</tr>
<tr>
<td rowspan="3">Produção de coprodutos</td>
<td>Registro</td>
<td>Não Aplicável</td>
<td rowspan="3">Nenhuma</td>
<td rowspan="3">Todas</td>
</tr>
<tr>
<td rowspan="2">Relatório de Conclusão</td>
<td>Antes</td>
</tr>
<tr>
<td>Após</td>
</tr>
</tbody>
</table>

> [!NOTE]
> O recurso *Gerenciamento de qualidade para processos de depósito* adiciona funcionalidades para o processamento de ordens de qualidade para produção em que o campo **Tipo de evento** é definido como *Relatar como concluído* e o campo **Execução** é definido como *Depois*, e para compras em que o campo **Tipo de evento** é definido como *Registro*. Para obter mais informações, consulte [Gerenciamento de qualidade para processos de depósito](quality-management-for-warehouses-processes.md).

A tabela a seguir fornece mais informações sobre como as ordens de qualidade podem ser geradas para tipos específicos de processos.

<div class="tableSection">
<table>
<thead>
<tr>
<th>Tipo de processo</th>
<th>Quando as ordens de qualidade podem ser geradas automaticamente</th>
<th>Quando as ordens de qualidade podem ser geradas se o teste destrutivo for exigido</th>
<th>Informações de condição</th>
<th>Informações de geração manual</th>
</tr>
</thead>
<tbody>
<tr>
<td>Ordem de compra</td>
<td>Antes ou depois de uma lista de recebimentos ou de um recebimento de produtos para o material recebido é lançado</td>
<td>Após o recebimento de produtos para o material recebido é lançado, porque o material deve estar disponível para testes destrutivos</td>
<td>O requisito para uma ordem de qualidade pode refletir um site, item ou fornecedor específico ou uma combinação dessas condições.</td>
<td>Uma ordem de qualidade gerada manualmente que se refere a uma ordem de compra pode usar as informações em um registro de associação, como o planejamento de amostragem de teste.</td>
</tr>
<tr>
<td>Ordem de quarentena</td>
<td>Antes ou depois, a ordem de quarentena é relatada como concluída ou terminada</td>
<td>Ordens de qualidade que exigem testes destrutivos não podem ser geradas. Presume-se que a funcionalidade da ordem de quarentena controla a disposição do material destruído.</td>
<td>O requisito para uma ordem de qualidade pode refletir um site, item ou fornecedor específico ou uma combinação dessas condições.</td>
<td>Uma ordem de qualidade gerada manualmente que se refere a uma ordem de quarentena pode usar as informações em um registro de associação, como o planejamento de amostragem de teste.</td>
</tr>
<tr>
<td>Ordem de venda</td>
<td>Antes de uma atualização programada do processo de separação ou da guia de remessa dos itens que estão sendo enviados</td>
<td>Em qualquer etapa</td>
<td>O requisito para uma ordem de qualidade pode refletir um site, item ou cliente específico ou uma combinação dessas condições.</td>
<td>Uma ordem de qualidade gerada manualmente que se refere à ordem de compra pode usar informações em um registro de associação de qualidade, como o planejamento de amostragem de teste.</td>
</tr>
<tr>
<td>Ordem de produção</td>
<td>Antes ou depois, a quantidade concluída para a ordem de produção é relatada</td>
<td>Depois que a quantidade concluída para a ordem de produção é relatada</td>
<td>O requisito para uma ordem de qualidade pode refletir um site ou item específico ou uma combinação dessas condições.</td>
<td>Uma ordem de qualidade gerada manualmente que se refere a uma ordem de produção em um registro de associação de qualidade, como o plano de amostragem de teste.</td>
</tr>
<tr>
<td>Ordem de produção que tem uma operação de rota</td>
<td>Antes ou depois da conclusão do relatório para uma operação</td>
<td>Depois da conclusão de produção de relatório para a última operação</td>
<td>O requisito para uma ordem de qualidade pode refletir um site, item ou recurso de operações específico ou uma combinação dessas condições.</td>
<td>Uma ordem de qualidade gerada manualmente que se refere a uma operação de rota em um registro de associação de qualidade, como o plano de amostragem de teste.</td>
</tr>
<tr>
<td>Inventário</td>
<td>Uma ordem de qualidade não pode ser gerada automaticamente para uma transação em um diário de estoque ou para transações de ordem de transferência.</td>
<td></td>
<td></td>
<td>Uma ordem de qualidade deve ser criada manualmente para a quantidade em estoque de um item. O estoque físico disponível do item é necessário.</td>
</tr>
</tbody>
</table>
</div>

## <a name="examples-of-automatic-generation-of-quality-orders"></a>Exemplos de geração automática de ordens de qualidade

### <a name="purchasing"></a>Comprando

Na compra, se você definir o campo **Tipo de evento** como *Recebimento de produtos* e o campo **Execução** como *Após* na página **Associações de qualidade**, você obterá os seguintes resultados:

- Se a opção **Quantidade por atualização** for definida como *Yes*, uma ordem de qualidade é gerada para cada recebimento em relação à ordem de qualidade, com base na quantidade e nas configurações recebidas na amostra do item. Sempre que uma quantidade é recebida em relação à ordem de compra, novos pedidos de qualidade são gerados com base na quantidade recém-recebida.
- Se a opção **Quantidade por atualização** for definida como *Não*, uma ordem de qualidade será gerada para o primeiro recebimento em relação à ordem de qualidade, com base na quantidade recebida. Além disso, uma ou mais ordens de qualidade são criadas com base na quantidade restante, dependendo das dimensões de rastreamento. Os pedidos de qualidade não são gerados para recebimentos subsequentes em relação à ordem de compra.

### <a name="production"></a>Produção

Na produção, se você definir o campo **Tipo de evento** como *Relatar como concluído* e o campo **Execução** como *Após* na página **Associações de qualidade**, você obterá os seguintes resultados:

- Se a opção **Quantidade por atualização** for definida como *Yes*, uma ordem de qualidade é gerada com base em todas as quantidades e configurações finalizadas na amostra do item. Sempre que uma quantidade é relatada como concluída em relação à ordem de produção, novas ordens de qualidade são geradas com base na quantidade recém-concluída. Essa lógica de geração é consistente com a compra.
- Se a opção **Quantidade por atualização** for definida como *Não*, uma ordem de qualidade é gerada na primeira vez que uma quantidade é relatada como concluída, com base na quantidade concluída. Além disso, uma ou mais ordens de qualidade são criadas com base na quantidade restante, dependendo das dimensões de rastreamento da amostra do item. As ordens de qualidade não são geradas para quantidades concluídas subsequentes.

<table>
<thead>
<tr>
<th>Especificação de qualidade</th>
<th>Quantidade por atualização</th>
<th>Por dimensão de rastreamento</th>
<th>Resultado</th>
</tr>
</thead>
<tbody>
<tr>
<td>Porcentagem: 10%</td>
<td>Sim</td>
<td>
<p>Nº do lote: não</p>
<p>Número de série: não</p>
</td>
<td>
<p>Quantidade da ordem: 100</p>
<ol>
<li>Relatar como concluído para 30
<ul>
<li>Ordem de qualidade 1 para 3 (10% de 30)</li>
</ul>
</li>
<li>Relatar como concluído para 70
<ul>
<li>Ordem de qualidade 2 para 7 (10% da quantidade restante da ordem, que é 70 neste caso)</li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td>Quantidade fixa: 1</td>
<td>Não</td>
<td>
<p>Nº do lote: não</p>
<p>Número de série: não</p>
</td>
<td>Quantidade da ordem: 100
<ol>
<li>Relatar como concluído para 30
<ul>
<li>Ordem de qualidade 1 para 1 (para a primeira quantidade relatada como concluída, que tem um valor fixo de 1)</li>
<li>Ordem de qualidade 2 para 1 (para a quantidade restante, que ainda possui um valor fixo de 1)</li>
</ul>
</li>
<li>Relatar como concluído para 10
<ul>
<li>Nenhuma ordem de qualidade é criada.</li>
</ul>
</li>
<li>Relatar como concluído para 60
<ul>
<li>Nenhuma ordem de qualidade é criada.</li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td>Quantidade fixa: 1</td>
<td>Sim</td>
<td>
<p>Nº do lote: sim</p>
<p>Número de série: sim</p>
</td>
<td>
<p>Quantidade da ordem: 10</p>
<ol>
<li>Relatar como concluído para 3: 1 para número de lote b1, número de série s1; 1 para número de lote b2, número de série s2; e 1 para número de lote b3, número de série s3
<ul>
<li>Ordem de qualidade 1 para 1 do número de lote b1, número de série s1</li>
<li>Ordem de qualidade 2 para 1 do número de lote b2, número de série s2</li>
<li>Ordem de qualidade 3 para 1 do número de lote b3, número de série s3</li>
</ul>
</li>
<li>Relatar como concluído para 2: 1 para número de lote b4, número de série s4; e 1 para número de lote b5, número de série s5
<ul>
<li>Ordem de qualidade 4 para 1 do número de lote b4, número de série s4</li>
<li>Ordem de qualidade 5 para 1 do número de lote b5, número de série s5</li>
</ul>
</li>
</ol>
<p><strong>Observação:</strong> o lote pode ser reutilizado.</p>
</td>
</tr>
<tr>
<td>Quantidade fixa: 2</td>
<td>Não</td>
<td>
<p>Nº do lote: sim</p>
<p>Número de série: sim</p>
</td>
<td>
<p>Quantidade da ordem: 10</p>
<ol>
<li>Relatar como concluído para 4: 1 para número de lote b1, número de série s1; 1 para número de lote b2, número de série s2; 1 para número de lote b3, número de série s3; e 1 para número de lote b4, número de série s4
<ul>
<li>Ordem de qualidade 1 para 1 do número de lote b1, número de série s1</li>
<li>Ordem de qualidade 2 para 1 do número de lote b2, número de série s2</li>
<li>Ordem de qualidade 3 para 1 do número de lote b3, número de série s3</li>
<li>Ordem de qualidade 4 para 1 do número de lote b4, número de série s4</li>
</ul>
<ul>
<li>Ordem de qualidade 5 para 2, sem referência a um número de lote e um número de série</li>
</ul>
</li>
<li>Relatar como concluído para 6: 1 para número de lote b5, número de série s5; 1 para número de lote b6, número de série s6; 1 para número de lote b7, número de série s7; 1 para número de lote b8, número de série s8; 1 para número de lote b9, número de série s9; e 1 para número de lote b10, número de série s10
<ul>
<li>Nenhuma ordem de qualidade é criada.</li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Recursos adicionais

- [Processos de gerenciamento de qualidade](quality-management-processes.md)
- [Habilitar gerenciamento de qualidade e não conformidade](enable-quality-management.md)
- [Gerenciamento de qualidade para processos de depósito](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
