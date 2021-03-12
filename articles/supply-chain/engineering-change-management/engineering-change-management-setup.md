---
title: Estabelecer valores comuns para gerenciamento de alterações de engenharia
description: Este tópico descreve como estabelecer valores comuns usados para parâmetros em várias partes do gerenciamento de alterações de engenharia.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgProductParameters, EngChgEcmSeverityTable, EngChgEcmSeverityRuleSet, EngChgEcmSeverityLookup,EngChgEcmSeverityChart,EngChgEcmRequestSeverityChart,EngChgEcmPriorityTable, EngChgEcmPriorityLookup, EngChgEcmPriorityChart, EngChgEcmMaterialDisposition, EngChgEcmEH
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: b46bc10f8b75a58b8baefd88aa6a0b79c59d6544
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5005393"
---
# <a name="establish-common-values-for-engineering-change-management"></a>Estabelecer valores comuns para gerenciamento de alterações de engenharia

[!include [banner](../includes/banner.md)]

Ao configurar o gerenciamento de alterações de engenharia, você deve estabelecer várias coleções de valores que serão usadas para preencher listas suspensas em outras partes da interface do usuário (IU). Você deve especificar esses valores de acordo com os tipos de produtos produzidos e suas necessidades comerciais específicas.

## <a name="engineering-change-categories"></a>Categorias de alteração de engenharia

Use as categorias de alterações de engenharia para organizar ordens de alterações de engenharia, visando facilitar o gerenciamento e a revisão. Por exemplo, pode ser útil configurar um fluxo de trabalho em que, dependendo da categoria, um departamento específico deva revisar as alterações propostas. Portanto, a ordem de alteração da engenharia inclui um campo **Categoria**.

Para estabelecer a coleção de categorias de alterações de engenharia que é usada em sua empresa, acesse **Gerenciamento de alterações de engenharia \> Configuração \> Gerenciamento de alterações de engenharia \> Categorias de alterações de engenharia**. Você pode usar os botões no Painel de Ações para adicionar, remover e editar valores, e para organizá-los na ordem em que devem aparecer nas listas suspensas onde são exibidos.

## <a name="engineering-change-priorities"></a>Prioridades da alteração de engenharia

Use as prioridades de alterações de engenharia para indicar a importância ou a urgência de uma ordem de alterações de engenharia. Elas podem ajudá-lo a manter o controle da importância de uma ordem de alterações de engenharia, de forma que você possa identificar facilmente quais ordens devem ser processadas primeiro e com que rapidez.

Para estabelecer a coleção de prioridades de alterações de engenharia que é usada em sua empresa, acesse **Gerenciamento de alterações de engenharia \> Configuração \> Gerenciamento de alterações de engenharia \> Prioridades de alterações de engenharia**. Você pode usar os botões no Painel de Ações para adicionar, remover e editar valores, e para organizá-los na ordem em que devem aparecer nas listas suspensas onde são exibidos.

## <a name="engineering-change-reasons"></a>Motivos de alteração de engenharia

As razões da alterações da engenharia indicam a causa ou a natureza da alteração na ordem de alteração.

Para estabelecer a coleção de razões de alterações de engenharia que é usada em sua empresa, acesse **Gerenciamento de alterações de engenharia \> Configuração \> Gerenciamento de alterações de engenharia \> Razões de alterações de engenharia**. Você pode usar os botões no Painel de Ações para adicionar, remover e editar valores, e para organizá-los na ordem em que devem aparecer nas listas suspensas onde são exibidos.

## <a name="material-disposal-codes"></a>Códigos de disposição do material

Use códigos de disposição de material para categorizar materiais usados nos bens acabados ou os componentes que devem ser destruídos de forma específica ou exigem um tratamento antes que possam ser adicionados à lixeira normal. Ao adicionar um produto relevante a uma ordem de alterações de engenharia, você pode atribuir um código de disposição como parte dos detalhes da alteração.

Para estabelecer a coleção de códigos de alienação de material que é usada em sua empresa, acesse **Gerenciamento de alterações de engenharia \> Configuração \> Gerenciamento de alterações de engenharia \> Códigos de alienação de material**. Você pode usar os botões no Painel de Ações para adicionar, remover e editar valores, e para organizá-los na ordem em que devem aparecer nas listas suspensas onde são exibidos.

## <a name="received-customer-approval"></a>Aprovação do cliente recebida

Quando você cria produtos para um cliente específico, o projeto e as especificações geralmente devem ser validados para que o produto possa ser definido como pronto. O campo **Aprovação de cliente recebida** permite indicar em que ponto o produto está no processo de aprovação do cliente e/ou se a aprovação foi recebida.

Para estabelecer a coleção de valores de aprovação de cliente recebida que é usada em sua empresa, acesse **Gerenciamento de alterações de engenharia \> Configuração \> Gerenciamento de alterações de engenharia \> Aprovação de cliente recebida**. Você pode usar os botões no Painel de Ações para adicionar, remover e editar valores, e para organizá-los na ordem em que devem aparecer nas listas suspensas onde são exibidos.

## <a name="engineering-change--environmental-health-and-safety-codes"></a>Alteração na engenharia – códigos de integridade e segurança ambientais

Se regulamentações de integridade e de segurança ambientais padrão, ou normas ou procedimentos específicos da empresa, precisam ser consideradas na fabricação de um produto, você pode usar os códigos de integridade e de segurança ambientais para defini-las. Na ordem de alterações de engenharia, você pode indicar quais códigos se aplicam à fabricação de um produto enquanto edita os detalhes do produto afetado.

Para estabelecer a coleção de valores de integridade e segurança que é usada em sua empresa, acesse **Gerenciamento de alterações de engenharia \> Configuração \> Gerenciamento de alterações de engenharia \> Alterações de engenharia - códigos de integridade e segurança ambientais**. Você pode usar os botões no Painel de Ações para adicionar, remover e editar valores, e para organizá-los na ordem em que devem aparecer nas listas suspensas onde são exibidos.

## <a name="engineering-change-severities"></a>Gravidades de alterações de engenharia

As gravidades de alterações de engenharia são usadas para indicar o nível de impacto que se aplica aos produtos em uma ordem de alterações de engenharia.

Para estabelecer a coleção de gravidades de alterações de engenharia que é usada em sua empresa, acesse **Gerenciamento de alterações de engenharia \> Configuração \> Gerenciamento de alterações de engenharia \> Gravidades de alterações de engenharia**. Você pode usar os botões no Painel de Ações para adicionar, remover e editar valores, e para organizá-los na ordem em que devem aparecer nas listas suspensas onde são exibidos.

Você pode estabelecer regras que se aplicam a cada nível de gravidade criado. Para obter mais informações sobre como atribuir essas regras, consulte a próxima seção.

## <a name="engineering-change-severity-rule-sets"></a>Conjuntos de regras de severidade da alteração de engenharia

Você usa conjuntos de regras de gravidade de alterações de engenharia para estabelecer um grupo de regras que pode ser usado para calcular automaticamente a gravidade da ordem de alterações, com base no tipo de alteração nos produtos afetados. Para usar as regras de gravidade, abra a página **Parâmetros de gerenciamento de alterações de engenharia** e defina o campo **Regra de gravidade** como *Calcular* ou *Calcular automaticamente*.

Quando o sistema avalia a gravidade, ele processa as regras na ordem em que aparecem na página, de cima para baixo. Para que uma regra seja selecionada e tenha sua prioridade estabelecida, todas as regras de um conjunto de regras devem ser atendidas.

Para configurar as regras que se aplicam a cada nível de gravidade de alteração que você definiu, acesse **Gerenciamento de alterações de engenharia \> Configuração \> Gerenciamento de alterações de engenharia \> Conjuntos de regras de gravidade de alteração de engenharia**. Siga uma destas etapas.

- Para criar um novo conjunto de regras, selecione **Novo** no Painel de Ações e defina os campos conforme descrito mais adiante nesta seção.
- Para editar um conjunto de regras existente, selecione-o no painel de lista, selecione **Editar** no Painel de Ações e defina os campos conforme descrito mais adiante nesta seção.
- Para excluir um conjunto de regras existente, selecione-o no painel de lista e, em seguida, selecione **Excluir** no Painel de Ações.
- Para reorganizar a lista de conjuntos de regras, selecione um conjunto de regras no painel de lista e use os botões **Para cima** e **Para baixo** no Painel de Ações para reposicioná-lo.

Em cada conjunto de regras, defina o seguinte campo:

- **Gravidade** – selecione o nível de gravidade para estabelecer regras. Use a página **Gravidades de alterações de engenharia** para criar e nomear os níveis. (Para obter mais informações, consulte a seção anterior).

Use os botões da FastTab **Regras** para adicionar ou remover uma regra para a configuração de gravidade atual. Cada regra tem um campo **Regra** e um campo **Nome**. As regras são estabelecidas pelo sistema e indicam os tipos de alterações que um produto pode ter. O nome indica o tipo de alteração.
