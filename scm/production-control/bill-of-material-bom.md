---
title: "Listas de materiais e fórmulas"
description: "Este artigo fornece informações sobre as listas de materiais (BOMs) e fórmulas, que fazem parte central de definição de produto e grades de produto. BOMs e fórmulas especificam materiais ou os ingredientes necessários para um produto específico. As fórmulas também especifique co-produtos e subprodutos recebidos no contexto específico de produção."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMConsistOf, BOMDesigner, BOMTable, EcoResProductProcessManufacturingWorkspace
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19331
ms.assetid: c19b437a-2de2-4728-9477-2bcb0c2b1f5e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: a3d2d9d2d8dd518d04b289bb5326bcbf34f0cdc2
ms.lasthandoff: 03/31/2017


---

# <a name="bills-of-materials-and-formulas"></a>Listas de materiais e fórmulas

Este artigo fornece informações sobre as listas de materiais (BOMs) e fórmulas, que fazem parte central de definição de produto e grades de produto. BOMs e fórmulas especificam materiais ou os ingredientes necessários para um produto específico. As fórmulas também especifique co-produtos e subprodutos recebidos no contexto específico de produção. 

<a name="bills-of-materials"></a>Listas de Materiais
------------------

Uma lista de materiais (BOM) define os componentes necessários para produzir um produto. Os componentes podem ser matérias-primas, produtos semiacabados ou ingredientes. Em alguns casos, serviços podem ser mencionados em uma BOM. No entanto, BOMs geralmente descrevem os *recursos materiais* necessários.  

Quando combinada com um roteiro ou um fluxo de produção que descreve as operações e os recursos necessários para construir um produto, a BOM forma a base para o cálculo dos custos estimados do produto.  

Uma BOM é uma entidade individual que é descrita por seguintes informações:

-   ID da BOM
-   Nome de BOM
-   As linhas da BOM que descrevem os componentes e os ingredientes
-   As versões da BOM, que definem os produtos e o período em que a BOM pode ser utilizada.

Uma única BOM descreve um nível único que é identificado por um ID exclusivo. Componentes podem ter suas próprias BOMs que são indicadas por versões da BOM. Você pode exibir e editar a hierarquia completa das BOMs de um produto específico no designer da BOM.

### <a name="formulas-co-products-and-by-products"></a>Fórmulas, coprodutos e subprodutos

Uma fórmula é um subtipo de BOM que é tipicamente usado na manufatura de processo. Além dos componentes e ingredientes, uma fórmula descreve coprodutos e subprodutos. A versão atual, a definição de co-produtos e subprodutos para fórmula requerem a versão da fórmula. Uma fórmula é geralmente definida para um produto acabado específico (uma fórmula ou um item de planejamento) definido na versão da fórmula.

### <a name="boms-in-the-product-lifecycle"></a>BOMs no ciclo de vida do produto

No ciclo de vida do produto, vários tipos de BOM podem ser criados por diversos motivos:

-   **Esboço/Rascunho da BOM** – Esta BOM gera um rascunho da estimativa de materiais necessários em uma fase inicial de design e ajuda a realizar uma estimativa grosseira de custo e de atributos do produto. Essa BOM geralmente não é usada no planejamento de recurso da empresa (ERP).
-   **BOM da Engenharia** – Esta BOM é geralmente usada quando você projeta produtos que se baseiam em portfólios de produtos existentes. BOMs da Engenharia são estruturadas para simplificar o processo de design e agrupar produtos complexos em módulos de engenharia. Para produtos simples, talvez seja possível construir BOMs para o processo de produção real. No entanto, para outros produtos, a BOM de engenharia deve ser convertida para uma BOM de produção. BOMs de Engenharia são normalmente representadas por fantasmas na hierarquia da BOM. Embora as BOMs de Engenharia possam ser usadas no planejamento e execução das operações de fabricação, esta abordagem pode resultar em ineficiências, principalmente em operações repetitivas onde várias ordens são criadas.
-   **BOM de Planejamento** – Esta BOM é utilizada para planejar as requisições de materiais. A demanda de componentes e ingredientes é calculada com base na demanda dos produtos acabados. Como as BOMs de custo, BOMs de planejamento podem representar uma mistura específica de materiais utilizados em um certo período.
-   **BOM de Produção** – Esta é a BOM utilizada para uma produção específica. Uma BOM de produção deve levar em consideração os recursos que realmente são usados para produzir o produto. Quando uma ordem de produção, ordem de lote, ou kanban são criados, os vários níveis de BOMs representados por fantasmas são arrastados para um nível e distribuídos pelas operações para a ordem.
-   **BOM de Custo** – Esta BOM é usada para calcular o custo estimado de um produto. Por exemplo, você pode usar uma BOM de custo quando o custo padrão é utilizado ou quando o custo planejado estimado de um certo produto é calculado. BOMs de custo podem se referir a uma mistura específica de materiais e recursos que está prestes a ser utilizada. Consequentemente, você pode usar a BOM de custo para criar um custo estimado representativo para um período e ajudar a evitar variações ao longo do tempo.

Os tipos de BOM usado realmente uma implementação dependem de implementação, e também de cenários e requisitos comerciais. Em implementações simples, uma BOM de planejamento, uma BOM de produção, e uma BOM de custo podem ser modeladas como uma única BOM. Em ambientes que possuem alterações frequentes de engenharia e múltiplos roteiros alternativos, um conjunto maior de tipos de BOMs provavelmente será necessário.

### <a name="approval-of-boms-and-formulas"></a>Aprovação de BOMs e fórmulas

Cada BOM e fórmula pode ser aprovada ou reprovada separadamente. Normalmente, a aprovação de uma BOM ou fórmula ocorre quando a primeira versão relevante da BOM é aprovada. No entanto, em alguns cenários comerciais, essas aprovações podem ser etapas diferentes no processo e podem envolver diferentes proprietários de processo.  

Observe que, se uma BOM for reprovada, todas as versões da BOM relacionadas também são reprovadas.

## <a name="bom-and-formula-versions"></a>Versões de BOMs e fórmulas
Para relacionar uma BOM ou fórmula específica a uma variante de produto que pode ser produzida, você deve criar uma versão da BOM ou versão da fórmula. A validade das versões da BOM e das versões da fórmula podem ser restritas por período, quantidade, local, dimensões de produto específicas, entre outros critérios. Versões da fórmula possuem atributos adicionais importantes, como rendimento, definições de coproduto e subproduto, e as instruções de distribuição de custo para a fórmula.

### <a name="approval-of-bom-and-formula-versions"></a>Aprovação das versões da BOM e da fórmula

Antes que uma versão da BOM possa ser usada no processo de planejamento ou fabricação, ela deve ser aprovada. Quando uma versão da BOM é aprovada, a BOM relacionada também pode ser aprovada, dependendo dos direitos de seleção e autenticação do usuário. Observe que uma versão da BOM pode ser aprovada somente se a própria BOM relacionada for aprovada.

### <a name="activation-of-the-default-bom-or-formula-version"></a>Ativação da versão padrão da BOM ou da fórmula

Para definir uma BOM ou fórmula específica como a versão padrão da BOM ou da fórmula que será usada pelo planejamento mestre ou utilizada na criação de ordens de produção, você deve ativar a versão. Quando uma versão, será ativada a exclusividade de liberação para restrições determinadas (por exemplo, período, site, quantidade) ou será marcada. Você receberá uma mensagem de erro se a versão que você está tentando ativar conflitos com uma versão que esteja ativa. Você deve então desativar a versão conflitante ou modificar as restrições da versão (geralmente o período) para evitar uma ativação ambígua.

### <a name="product-change-with-case-management"></a>Alteração de produto com gerenciamento de caso

O caso de alteração de produto para aprovação e ativação de BOMs e versões da BOM novas ou alteradas fornece uma maneira simples de visualizar um resumo das restrições da versão da BOM. Você também pode aprovar e ativar todas as BOMs e fórmulas que estão relacionadas a uma alteração específica para uma data de ativação.

### <a name="alternative-bom-versions"></a>Versões alternativas da BOM

As vezes, a versão ativa da BOM ou da fórmula não deve ser utilizada em previsões, vendas ou em um produto pai. Nesse caso, você pode selecionar uma BOM específica aprovada como parte dos requisitos (linha de previsão, linha de vendas, ou linha da BOM) se existe uma versão aprovada da BOM ou da fórmula para a BOM ou fórmula alternativa.  

Quando ordens planejadas, ordens de produção, ou kanbans são criadas, o planejador ou supervisor de chão de fábrica pode utilizar qualquer versão aprovada da BOM que seja válida na data de produção planejada solicitada para planejar ou produzir um produto específico. A versão da BOM usada não precisa ser ativada como a versão padrão da BOM.

## <a name="bom-and-formula-lines"></a>Linhas da BOM e da fórmula
Uma linha da BOM é criada para cada material, serviço ou ingrediente. A linha define o consumo planejado da variante de produto especificada e também define os diversos atributos que estão relacionados ao consumo planejado.  

As linhas da BOM podem ter os seguintes tipos de linha: **Item**, **Fantasma**, **Fornecimento vinculado**, **Fornecedor**.

### <a name="item"></a>Item

Selecione o tipo de linha **Item** para materiais ou serviços que são consumidos diretamente, e que não necessitam de detalhamento adicional ou fornecimento vinculado.

### <a name="phantom"></a>Fantasma

Selecione o tipo de linha **Fantasma** quando desejar detalhar qualquer item de baixo nível da BOM contido na linha da BOM. Em Planejamento mestre, em cálculo do custo planejado, ou na estimativa de uma ordem de produção que utiliza linhas da BOM do tipo **Fantasma**, a linha da BOM mãe que se refere a uma variante de produto que possui uma BOM fantasma é substituída pelos itens componentes que estão listados como linhas da BOM dentro daquela BOM, como determinado pela versão ativa aplicável da BOM daquela variante de produto. Se a variante de produto possui um roteiro ativo aplicável, as operações desse roteiro serão mescladas ao roteiro pai.  

Observe que fantasmas são normalmente utilizados para simplificar o processo de engenharia. O uso extensivo de BOMs fantasma em vários níveis tem um efeito sobre o desempenho, principalmente em cenários de fabricação altamente repetitivos. Para melhorar o desempenho, você deve evitar hierarquias profundas de fantasmas. Em vez disso, utilize BOMs de produção e roteiros pré-detalhados.

### <a name="pegged-supply"></a>Fornecimento vinculado

Selecione o tipo de linha** Fornecimento vinculado** quando desejar criar uma subprodução, um evento kanban da linha BOM, ou uma ordem de compra direta para qualquer variante de produto referenciada pela linha da BOM. A subprodução, o evento kanban, ou a ordem de compra são criados quando você estimar a ordem de produção. As quantidades de item necessárias são reservadas automaticamente para a ordem de produção consumidora.

### <a name="vendor"></a>Fornecedor

Selecione o tipo de linha **Fornecedor** se o processo de produção utiliza um subempreiteiro, e você desejar que uma subprodução ou ordem de compra seja criada automaticamente para o subempreiteiro.  

**Observação sobre operações terceirizadas em uma BOM:** O serviço ou trabalho executado pelo subempreiteiro deve ser criado como item de serviço rastreado no estoque. Você deve anexar o item de serviço ao item pai como uma linha da BOM. O roteiro deverá conter uma operação atribuída ao recurso de operações do subcontratado.


