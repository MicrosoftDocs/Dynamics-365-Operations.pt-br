---
title: Fórmulas e versões de fórmulas
description: Este tópico fornece informações sobre fórmulas e versões da fórmula. Uma fórmula define materiais, ingredientes e os resultados de um processo específico na fabricação de processo. As fórmulas são usados para planejar e produzir produtos na manufatura de processos.
author: cvocph
manager: tfehr
ms.date: 09/12/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PlanActivity, ReqSupplyDemandSchedule, EcoResProductProdTypeFormulaNoActiveFormulaFormPart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c7fb37483412fdd09fe3734ddb148b050ec02951
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986965"
---
# <a name="formulas-and-formula-versions"></a>Fórmulas e versões de fórmulas

[!include [banner](../includes/banner.md)]

Uma fórmula define materiais, ingredientes e os resultados de um processo específico na fabricação de processo. Com o roteiro correspondente, a fórmula define todo o processo na manufatura do processo. As fórmulas são usados para planejar e produzir produtos na manufatura de processos.

Uma fórmula consiste em ingredientes e quantidades necessários para produzir uma determinada quantidade de um item de fórmula. Dependendo da tarefa que você realizar, é possível acessar a funcionalidade da fórmula do Gerenciamento de estoque e de depósito ou do Gerenciamento de informações do produto.

## <a name="formulas-and-formula-lines"></a>Fórmulas e linhas da fórmula
Uma fórmula consiste em uma ou mais linhas da fórmula, que identificam os ingredientes ou itens que compõem a fórmula. Uma linha da fórmula pode conter itens de BOM, itens de fórmula, itens de peso variável, itens comprados, coprodutos ou subprodutos. Como vários itens são usados em vários produtos, um item pode ser usado em mais de uma fórmula.

Um exemplo de uma fórmula é uma fórmula de biscoito com gotas de chocolate. Os ingredientes para essa fórmula usam várias linhas, como farinha, açúcar, ovos, manteiga e as gotas de chocolate. A fórmula de biscoito com gotas de chocolate contém ingredientes que provavelmente são usados em outras fórmulas. Quando você faz os biscoitos com gotas de chocolate, é possível que haja sobras, como migalhas, ou alguns biscoitos podem assar demais ou pouco. Esses itens podem ser configurados como coprodutos ou subprodutos, dependendo das operações de produção.

Quando você cria uma linha da fórmula, você usa o tipo de linha para indicar como o sistema deve tratar a linha ao executar ordens de lote de planejamento e de produção. Cada tipo de linha gera um resultado diferente. A tabela a seguir descreve os diferentes tipos de linhas que você pode selecionar. 

| Tipo de linha     | descrição  |
|---------------|--------------|
| Item          | Selecione **Item** quando o item for uma matéria-prima ou um item semiacabado separado do estoque ou quando o item for um serviço. |
| Fantasma       | Selecione **Fantasma** quando quiser detalhar quaisquer itens de fórmula de nível inferior contidos nas linhas de fórmula. Quando você estimar a ordem de lote e os itens de fórmula forem detalhados, os itens de componente serão listados como linhas da fórmula na ordem de lote. Além de isso, os roteiros correspondentes serão adicionadas ao roteiro de produção. Os itens de fórmula são detalhados usando a configuração atual. Ao usar o tipo de linha **Fantasma**, você poderá tratar as configurações de produção e de medição que ocorrem em diferentes níveis da fórmula. Se você selecionar **Fantasma** para um produto na Guia Rápida **Engenharia** da página **Detalhes do produto liberado** e depois usar esse produto em uma fórmula, o tipo de linha da fórmula será alterado para **Fantasma**. Você não pode selecionar **Fantasma** para um item de peso variável ou para itens em que o tipo de produção é **Coproduto**, **Subproduto**, ou **Item de planejamento**. |
| Fornecimento vinculado | Selecione **Suprimento vinculado** para criar uma ordem de lotes, ordem de produção, um kanban, uma ordem de transferência, ou uma ordem de compra do ingrediente que estará contido na linha fórmula. A ordem relacionada é determinada com base nas configurações de ordem padrão e no tipo de produção de ingrediente, e será criada quando você estimar a ordem de lote. As quantidades necessárias do ingrediente serão reservadas para a ordem de lote. |
| Fornecedor        | Selecione **Fornecedor** se o processo de produção usar um subcontratado e você desejar criar uma subprodução ou uma ordem de compra para o subcontratado. O serviço ou trabalho realizado pelo subcontratado deve ser criado usando um item de fórmula ou um Item de serviço. Você poderá associar o item ao item principal como uma linha da fórmula. O roteiro deverá conter uma operação atribuída ao recurso de operações do subcontratado. Essa operação é associada à linha da fórmula usando o campo **Nº Oper.** . |

## <a name="formula-versions"></a>Versões da fórmula
Ao criar uma nova fórmula, você deverá primeiro criar uma versão da fórmula antes de adicionar itens da linha da fórmula e suas características específicas. Toda fórmula deve ter pelo menos uma versão. O botão **Aprovado** em uma versão da fórmula se torna disponível apenas depois que um registro da versão for salvo com êxito. Cada registro da versão da fórmula é associado a um ou vários coprodutos e subprodutos que podem ser produzidos, conforme você produz o produto acabado. Diversos produtos podem ser feitos com os mesmos ingredientes em tamanhos de lote diferentes, múltiplos ou usando quantidades diferentes. Você pode criar quantas versões da fórmula forem necessárias.

Para gerenciar várias versões da fórmula ativas, use intervalos de datas efetivas ou dos campos de quantidade. Versões de fórmula ativas múltiplas poderão existir somente se o intervalo de datas e a quantidade "inicial" não se sobrepuserem.

Diferentemente de BOMs, onde um BOM é frequentemente associado a várias versões de BOM, apenas uma versão de fórmula existe por fórmula. Lembre-se que somente uma versão de fórmula pode ser ativada para as dimensões e quantidade da cobertura de determinado produto. Porém, várias versões de fórmula podem existir por outros motivos, e você pode selecioná-las manualmente quando criar uma ordem de lote.

## <a name="approve-and-activate-formulas-and-formula-versions"></a>Aprovar e ativar fórmulas e versões da fórmula
Fórmulas e versões da fórmula devem ser aprovadas antes de serem usadas para planejamento e produção. Geralmente as fórmulas são ativadas antes de serem usadas. Entretanto, durante a produção, é possível selecionar uma versão de fórmula que esteja aprovada, mas não esteja ativada.

Para ajudar a proteger uma fórmula ou versão da fórmula, você poderá definir os parâmetros **Bloquear edição** e **Bloquear remoção de aprovação** no formulário **Parâmetros de controle da produção**.

Se você selecionar **Bloquear edição** e a fórmula for aprovada, nenhum campo nas linhas da fórmula poderá ser excluído ou editado. No entanto, se você remover a aprovação da fórmula, você poderá excluir e modificar as linhas da fórmula. Você também pode criar novas fórmulas e novas versões da fórmula.

Se você selecionar **Bloquear remoção da aprovação**, você não poderá remover a aprovação de uma fórmula ou versão da fórmula aprovada. No entanto, você pode criar novas fórmulas e novas versões da fórmula e pode remover a ativação da versão da fórmula.

Você pode adicionar mais níveis de controle, usando a funcionalidade de assinatura eletrônica. Quando um usuário é configurado de forma que uma assinatura eletrônica seja necessária no momento de aprovação da fórmula, uma página **Assinatura** será exibida quando a fórmula estiver ativada. O usuário deve estar autorizado para assinar eletronicamente e o certificado deve ser validado com êxito antes que a alteração seja comprometida. Se a sua assinatura não puder ser autenticada, a aprovação ou a remoção da aprovação será negada e a alteração que a iniciou a aprovação ou remoção da aprovação voltará para seu estado original.

## <a name="use-the-scalable-feature"></a>Usar o recurso escalonável
O recurso Escalonável estará disponível somente se todos os componentes do item da fórmula forem definidos como **Consumo variável**. O recurso não está disponível se os componentes de itens forem  **Consumo fixo** ou **Consumo em etapas**. Quando o recurso Escalável for usado, se você alterar um ingrediente em uma fórmula, a quantidade dos outros ingredientes que você selecionar será ajustada. O tamanho da fórmula também será ajustado. Da mesma forma, se você alterar o tamanho da fórmula, a quantidade de todos os ingredientes escaláveis será alterada. Este recurso é criado especificamente para criação e manutenção da fórmula. Não indica se a quantidade de um ingrediente estará dimensionada para cima ou para baixo em uma ordem de lote.

## <a name="use-step-consumption"></a>Usar consumo em etapas
O consumo em etapas elimina a necessidade de inserir uma quantidade na guia **Linha da fórmula** de um ingrediente. Em vez de isso, o consumo da etapa é configurado para ter um valor **Da série** e **Quantidade**. As informações do registro de Consumo da etapa por série que atendem à quantidade na ordem do lote são selecionadas. O consumo da etapa é útil quando a taxa de consumo não é linear em relação ao tamanho da ordem de lote, e somente aumenta a necessidade quando um determinado limite de quantidade é atingido. Para habilitar esse recurso para uma nova fórmula, no grupo **Cálculo de consumo**, altere a configuração da fórmula para o ingrediente aplicável de  **Padrão** para **Etapa**. Você especifica esse método de consumo na guia **Configuração** da página **Linha da fórmula**.
