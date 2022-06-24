---
title: Planejamento de produção
description: Este artigo descreve o planejamento de produção e explica como modificar as ordens de produção planejadas usando a Otimização de Planejamento.
author: t-benebo
ms.date: 06/01/2021
ms.topic: article
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 151aa3688c570ea6ec282c297ed18288dd886131
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873772"
---
# <a name="production-planning"></a>Planejamento de produção

[!include [banner](../../includes/banner.md)]

A Otimização de Planejamento oferece suporte a vários cenários de produção. Se você estiver migrando do mecanismo de planejamento principal integrado já existente, é importante estar ciente de alteração no comportamento.

O vídeo a seguir apresenta uma breve introdução a alguns dos conceitos abordados neste artigo: [Dynamics 365 Supply Chain Management: aprimoramentos na Otimização de Planejamento](https://youtu.be/u1pcmZuZBTw).

## <a name="turn-on-this-feature-for-your-system"></a>Ative este recurso para o seu sistema

Se o sistema ainda não incluir os recursos descritos neste artigo, acesse [Gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative o recurso *Ordens de produção planejadas usando a Otimização de Planejamento*.

## <a name="planned-production-orders"></a>Ordens de Produção Planejadas

Quando o planejamento mestre cria ordens planejadas para atender a requisições, o tipo de ordem é determinado pelo valor do campo **Tipo de ordem planejada**. Se o campo **Tipo de ordem planejada** estiver definido como *Produção*, ordens de produção planejadas serão criadas. Essas ordens de produção planejadas incluem informações sobre a lista de materiais (BOM) ativa e a ID de roteiro da configuração de produção relacionada.

## <a name="requirements-from-boms"></a>Requisições de BOMs

As informações da BOM são respeitadas durante o planejamento mestre. A saída do plano inclui o fornecimento de materiais para cobrir a demanda de materiais relacionada para produção.

Durante o planejamento mestre, a BOM ativa atual é usada para determinar os materiais necessários para a produção. Essa etapa é realizada em todos os níveis da estrutura da BOM que está relacionada à ordem de produção necessária. A requisição de materiais é atendida usando estoque disponível, fornecimento sob encomenda existente e ordens planejadas aprovadas. Se materiais adicionais forem necessários em qualquer lugar, uma ordem planejada será criada para cobrir a demanda.

## <a name="scheduling-during-firming"></a>Agendamento durante a confirmação

As ordens de produção planejadas incluem a ID de roteiro necessária para o agendamento de produção. No entanto, o suporte ao agendamento durante a execução de planejamento de ordens planejadas está pendente. A ID de roteiro é usada para agendar ordens de produção planejadas durante a confirmação. Portanto, o prazo de entrega das ordens de produção planejadas pode ser diferente do prazo de entrega das ordens de produção agendadas e confirmadas relacionadas, que são geradas a partir delas, conforme descrito aqui:

- **Ordem de produção planejada** – o prazo de entrega baseia-se no prazo de entrega estático do produto liberado.
- **Ordem de produção confirmada** – o prazo de entrega baseia-se no agendamento que usa informações de roteiro e restrições de recursos relacionadas.

Para obter mais informações sobre a disponibilidade esperada de recursos, consulte [Análise de ajuste da Otimização de Planejamento](planning-optimization-fit-analysis.md).

Se você depender de uma funcionalidade de produção que ainda não está disponível para a Otimização de Planejamento, poderá continuar usando o mecanismo de planejamento mestre interno. Nenhuma exceção é necessária.

## <a name="delays"></a>Atrasos

Se o prazo de entrega dos materiais requisitados for maior do que o período entre a data de hoje e a data de requisição dos materiais, a ordem planejada dos materiais requisitados e a ordem de produção relacionada serão atrasadas. Para ordens planejadas, o atraso (em dias) é calculado com base no prazo de entrega do produto liberado. Em seguida, as informações sobre o atraso são propagadas por todos os níveis da estrutura da BOM. Portanto, você pode seguir o impacto de uma matéria-prima atrasada até a ordem de venda do cliente.

## <a name="modifying-planned-orders"></a>Modificar ordens planejadas

Ao alterar as informações em uma ordem planejada, você receberá a seguinte mensagem: "Observe que o impacto das alterações manuais feitas nas ordens planejadas não será refletido no restante do plano até a próxima execução do planejamento mestre."

Se você quiser alterar as informações em uma ordem planejada e ver o impacto sobre as requisições de materiais relacionadas, siga estas etapas.

1. Atualize a ordem planejada.
2. Aprove a ordem planejada.
3. Execute o planejamento mestre.

Ao executar o planejamento mestre, você não deverá usar filtros se ordens de produção planejadas forem incluídas. Para obter mais informações, consulte a seção [Filtros](#filters) posteriormente neste artigo.

> [!NOTE]
> Se a data de entrega da ordem planejada for alterada para uma data posterior, a demanda poderá ser vinculada a uma nova ordem planejada. Esse comportamento ocorre quando a nova data de fornecimento causa um atraso para a demanda vinculada, mas, de acordo com as configurações de prazo de entrega, o atraso pode ser evitado.

## <a name="explosion-page"></a>Página Detalhamento

Você pode usar a página **Detalhamento** para analisar a demanda necessária para uma ordem de produção específica ou ordem de produção planejada, a cobertura relacionada e as informações de vinculação. As informações na página **Detalhamento** são atualizadas durante o planejamento mestre. Não é possível atualizar as informações diretamente na página **Detalhamento**.

## <a name="filters"></a><a name="filters"></a>Filtros

Para garantir que a Otimização do Planejamento tenha as informações necessárias para calcular o resultado correto, você deve incluir todos os produtos que tenham qualquer relação com os produtos em toda a estrutura de BOM da ordem planejada. Por isso, para cenários de planejamento que incluam produção, recomendamos que você evite execuções filtradas do planejamento principal.

Embora os itens secundários dependentes sejam detectados automaticamente e incluídos nas execuções de planejamento principal quando o mecanismo de planejamento principal integrado está sendo usado, a Otimização do Planejamento não realiza esta ação no momento.

Por exemplo, se um único parafuso da estrutura da BOM do produto A também for usado para produzir o produto B, todos os produtos na estrutura da BOM dos produtos A e B deverão ser incluídos no filtro. Garantir que todos os produtos façam parte do filtro pode ser complexo. Por isso, recomendamos que você evite execuções filtradas de planejamento principal quando ordens de produção forem envolvidas. Caso contrário, o planejamento principal fornecerá resultados indesejáveis.

### <a name="reasons-to-avoid-filtered-master-planning-runs"></a>Motivos para evitar execuções planejadas do planejamento principal

Quando você executa o planejamento principal para um produto, a Otimização de Planejamento (não como o mecanismo de planejamento principal integrado) não detecta todos os subprodutos e matéria-prima na estrutura de BOM desse produto e, portanto, não os inclui na execução de planejamento principal. Embora a Otimização de Planejamento identifique o primeiro nível da estrutura de BOM do produto, ela não carrega configurações de produto (assim como o tipo de ordem padrão ou cobertura de item) no banco de dados.

Na Otimização de Planejamento, os dados para a execução são carregados antecipadamente e os filtros são aplicados. Isso significa que, se um subproduto ou matéria-prima incluído em um produto específico não for parte do filtro, as informações sobre ele não serão capturados para a execução. Além disso, se o subproduto ou matéria prima também for incluída em outro produto, uma execução filtrada que inclua somente o produto original e seus componentes removeria a demanda planejada existente que foi criada para aquele outro produto.

Esta lógica pode fazer com que as execuções filtradas do planejamento principal produzam resultados inesperados. As seções a seguir fornecem exemplos que ilustram os resultados inesperados que podem ocorrer.

### <a name="example-1"></a>Exemplo 1

Bens acabados no *FG* consistem nos seguintes componentes:

- Matéria-prima *R*
- O subproduto *S1*, que consiste no subproduto *S2*

Existe inventário em mãos para a matéria prima *R*, e o subproduto *S1* não está presente no inventário.

Quando você faz uma execução filtrada de planejamento principal para o bem acabado *FG*, você obterá uma ordem de produção planejada para o bem acabado *FG*, uma ordem de pesquisa planejada para a matéria-prima *R* e uma ordem de compra planejada para o subproduto *S1*. Esse é um resultado indesejável, pois a Otimização de Planejamento ignorou o suprimento existente da matéria-prima *R*, e o subproduto *S1* precisa ser produzido usando *S2*, e não pedido diretamente. Isso ocorreu porque a Otimização de Planejamento só tem a lista de componentes da mercadoria *FG* sem qualquer informação relacionada, assim como o suprimento existente de seus componentes ou suas configurações de ordem padrão.

### <a name="example-2"></a>Exemplo 2

Aproveitando o exemplo anterior, uma mercadoria acabada adicional, *FG2*, também usa o subproduto *S1*. Uma ordem planejada existe para a mercadoria *FG2* e a demanda planejada existe para todos os seus componentes, incluindo *S1*.

Após decidir corrigir os resultados indesejados da execução filtrada de planejamento principal do exemplo anterior, você adiciona todos os subprodutos e matérias-primas da estrutura BOM da mercadoria acabada *FG* ao filtro e então executa a regeneração completa.

Ao executar a regeneração completa, o sistema exclui todos os resultados existentes de todos os produtos inclusos e então recria os resultados com base nos novos cálculos. Isso significa que a demanda planejada existente para o produto *S1* é excluída e então recriada levando em conta somente os requisitos da mercadoria acabada *FG*, enquanto os requisitos da mercadoria acabada *FG2* são ignorados. Isso ocorre porque, quando você executa a Otimização de Planejamento, ela não inclui a demanda planejada das outras ordens de produção planejadas; somente a demanda planejada gerada durante a execução é usada.

> [!NOTE]
> Se a ordem planejada existente para a mercadoria acabada *FG2* estiver no status *Aprovado*, a demanda planejada aprovada será incluída, mesmo quando o produto principal não for adicionado ao filtro.

Portanto, a menos que você adicione todos os componentes das mercadorias acabadas *FG*, a mercadoria acabada *FG2* e todos os outros produtos de que esses componentes fazem parte (bem como seus componentes), a execução filtrada de planejamento principal fornecerá resultados indesejados.

Garantir que todos os produtos façam parte do filtro pode ser complexo. Por isso, recomendamos que você evite execuções filtradas de planejamento principal quando ordens de produção forem envolvidas.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
