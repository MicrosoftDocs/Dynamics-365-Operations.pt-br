---
title: Lançamento de custo indireto
description: Este tópico explica como lançar custos indiretos, criar grupos de custos e adicionar nós à folha de custos para custos indiretos.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: CostSheetDesigner, BOMCostGroup, ProjCategory, CostingVersion, CostSheetCalculationFactor
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: d7f4753f69d83d172993e1c9b04be2220fdf253f
ms.sourcegitcommit: 1ea145dc606e243c7f51d91a5c0dd9e385bbda4a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "8804598"
---
# <a name="indirect-cost-posting"></a>Lançamento de custo indireto

Os custos indiretos são custos que não estão diretamente relacionados a uma atividade única no processo de produção. Exemplos incluem custos administrativos como salários, custos do departamento contábil e custos gerais como aluguel, utilitários e custos de maquinaria.

## <a name="calculating-indirect-costs"></a>Cálculo de custos indiretos

O Microsoft Dynamics 365 Finance não tem uma forma automatizada de calcular a taxa de custos indiretos. Você deve determinar os custos indiretos, criar códigos de custo indireto e manter a taxa para cada custo indireto na folha de custos.

O processo exato usado para calcular custos indiretos pode variar ligeiramente de uma empresa para outra. Mas, em geral, o processo consiste nas seguintes etapas básicas:

1. Crie uma lista de custos indiretos para reconhecer na produção. Essa lista pode incluir aluguel, despesas administrativas, taxas contábeis e taxas legais. Ela não deve incluir custos de matéria-prima ou de mão-de-obra que são reconhecidos em roteiros de produção.
2. Somar todos os custos indiretos. Você pode agrupar tipos semelhantes de custos indiretos ou mantê-los separados. Cada custo indireto configurado pode ter contas principais diferentes que são usadas para lançamento na contabilidade geral.
3. Compare os custos indiretos a um fator, que também é conhecido como base de absorção. O fator pode ser qualquer coisa que você escolher. Veja aqui alguns exemplos comuns:

    - Renda
    - Quantidade total produzida
    - Tempo de preparação
    - Tempo de execução

    Você pode selecionar o período para o qual deseja calcular os custos indiretos, como mensal, trimestral ou anual. A soma dos custos indiretos e a soma do fator deve ser para a mesma quantidade de tempo. A seguinte fórmula é usada para calcular a taxa de custo indireto:

    *Taxa de custo indireto* = *Total de despesas de custo indireto* &divide; *Fator total*

4. Crie grupos de custo indireto.
5. Configure a folha de custos com suas taxas.
6. Mantenha o custo dos custos indiretos na versão de custos.

> [!NOTE]
> Você pode usar o módulo de **Contabilização de custos** para acumular custos e determinar a sobrecarga de origens diferentes, como produção, projetos e contabilidade. Para maiores informações, consulte [Contabilização de custos](/cost-accounting/cost-accounting-home-page.md).

> [!IMPORTANT]
> Os diferentes estabelecimentos regulatórios publicaram diretrizes sobre os tipos de custos que podem ser incluídos como custos indiretos ou despesas gerais no custo dos bens acabados. Antes de começar a configurar custos indiretos, recomendamos que você consulte o contador e as leis locais para garantir sua conformidade.

## <a name="create-cost-groups-for-indirect-costs"></a>Criar grupos de custo para custos indiretos

Você deve criar pelo menos um grupo de custos para usar para custos indiretos. Não há um limite para o número de grupos de custos que podem ser usados. Considere a maneira como os custos são calculados e se há taxas diferentes para tipos diferentes de custos. Por exemplo, sua organização fabrica produtos alimentícios. Algumas matérias-primas e bens acabados são bens secos e têm um custo indireto para o warehousing. Outras matérias-primas e bens acabados são refrigerados e têm um custo indireto maior. Nesse caso, talvez você deseje criar dois grupos de custos: **Custos indiretos de material seco** e **Custos indiretos de material refrigerado**.

Para criar um grupo de custos para custos indiretos, siga estas etapas.

1. Vá para **Controle de produção &gt; Configuração &gt; Roteiros &gt; Grupos de custos**.
2. Selecione **Novo** para criar um grupo.
3. No campo **Grupo de custos**, insira um nome exclusivo para o grupo de custos, como **MATOVH**.
4. No campo **Nome**, insira uma descrição do grupo de custos, como **Custos indiretos de material**.
5. No campo **Tipo de grupo de custos**, selecione **Indireto**.
6. Opcional: no campo **Comportamento**, selecione **Custo fixo** ou **Custo variável**.

## <a name="configure-the-costing-sheet-for-indirect-costs"></a>Configurar a folha de custos para custos indiretos

Depois de criar um ou mais grupos de custos, você pode configurar a folha de custos com custos indiretos e definir o cálculo. Talvez você queira agrupar custos indiretos na folha de custos. Para agrupar custos indiretos, você pode criar um cabeçalho opcional na folha de custos. Você deve criar pelo menos um nó para cada grupo de custos na folha de custos. Para cada grupo de custos para custos indiretos, você pode adicionar mais um cálculo de custo indireto.

### <a name="indirect-cost-node-types"></a>Tipos de nós de custo indireto

Esta seção descreve os diferentes tipos de nós para custos indiretos.

#### <a name="surcharge"></a>Sobretaxa

**Sobretaxa** é um dos tipos mais comuns de custos indiretos. Ela calcula uma porcentagem de custo de uma base de absorção de custos na ordem de produção. Para definir a base de absorção, selecione os grupos de custos vinculados aos componentes de material ou de tempo na folha de custos.

Por exemplo, uma sobretaxa de 3% pode ser adicionada ao custo da produção para todas as matérias-primas em uma ordem de produção.

#### <a name="rate"></a>Alíquota

Um custo indireto do tipo **Taxa** é usado para adicionar um valor fixo de custo à ordem de produção de uma base de absorção de custos na ordem de produção. A taxa pode ser baseada em um dos três subtipos:

- **Processo** – a taxa se baseia no tempo de execução do roteiro.
- **Configuração** – a taxa se baseia no tempo de configuração do roteiro.
- **Quantidade** – a taxa se baseia na quantidade produzida.

Para definir a base de absorção, selecione os grupos de custos vinculados aos componentes de material ou de tempo na folha de custos.

Por exemplo, um valor fixo de USD 2,0 é adicionado a cada ordem de produção, com base no tempo de execução no roteiro do grupo de custos de trabalho na folha de custos.

#### <a name="output-unit-based"></a>Saída baseada em unidade

Um custo indireto do tipo baseado na **Saída baseada em unidade** é calculado multiplicando-se o valor especificado na FastTab **Taxa** da folha de custos pelo subtipo selecionado. Você pode selecionar a quantidade, o peso ou o volume da mercadoria concluída como o multiplicador do custo indireto.

Por exemplo, use a quantidade para calcular USD 1,50 da depreciação de máquina para cada quantidade produzida. Como outro exemplo, você usa o volume para calcular USD 2,00 de custos de refrigeração para o volume de espaço que os bens acabados ocupam nas unidades de refrigeração.

#### <a name="input-unit-based"></a>Entrada baseada em unidade

Um custo indireto do tipo **baseado em unidade de entrada** é calculado multiplicando-se a quantidade de matérias-primas consumidas em uma ordem de produção por um valor. Você pode usar o peso ou o volume das entradas na ordem de produção para calcular o total. Você pode limitar o cálculo a um subconjunto de materiais, selecionando um ou mais grupos de custos na FastTab **Base de absorção** da folha de custos.

Por exemplo, você usa o volume de entradas para um grupo de custos específico vinculado a produtos refrigerados para adicionar USD 1,00 à ordem de produção.

### <a name="create-a-total-node-for-indirect-costs-in-the-costing-sheet"></a>Criar um nó total para custos indiretos na folha de custos

Para criar um nó total para custos indiretos na folha de custos, siga estas etapas.

1. Vá para **Gerenciamento de custos &gt; Configuração de políticas contábeis de custos indiretos &gt; Folha de custos**.
2. Na árvore, selecione um nó que represente o custo de mercadorias que foram fabricadas.
3. Selecione **Novo** para criar um nó.
4. No campo **Selecionar tipo de nó**, selecione **Total**.
5. No campo **Código**, insira uma ID exclusiva para o nó, como **Custos Indiretos de Produção**.
6. Marque a caixa de seleção **Cabeçalho**.
7. Marque a caixa de seleção **Total**.
8. Selecione **OK**.

### <a name="create-an-indirect-cost-group-node-in-the-costing-sheet"></a>Criar um nó de grupo de custos indiretos na folha de custos

Para criar um nó de grupo de custos indiretos na folha de custos, siga estas etapas.

1. Vá para **Gerenciamento de custos &gt; Configuração de políticas contábeis de custos indiretos &gt; Folha de custos**.
2. Na árvore, selecione o nó em que você deseja criar o custo indireto. Por exemplo, selecione o nó total para **Custos indiretos de produção**.
3. Selecione **Novo** para criar um nó.
4. No campo **Selecionar tipo de nó**, selecione **Grupo de custos**.
5. No campo **Código**, insira uma ID exclusiva para o nó, como **TRANSP**.
6. No campo **Descrição** insira uma breve descrição, como **Custos indiretos de transporte**.
7. Selecione **OK**.
8. No campo **Grupo de custos**, selecione o grupo de custos, como **OVH1: custos indiretos de transporte**.

### <a name="create-a-surcharge-indirect-cost"></a>Criar um custo indireto de sobretaxa

Para criar um custo indireto de sobretaxa na folha de custos, siga estas etapas.

1. Vá para **Gerenciamento de custos &gt; Configuração de políticas contábeis de custos indiretos &gt; Folha de custos**.
2. Na árvore, selecione o nó do grupo de custos indiretos em que você deseja criar o custo indireto. Por exemplo, selecione o nó total para **TRANSP - Custos Indiretos de Transporte**.
3. Selecione **Novo** para criar um nó.
4. No campo **Selecionar tipo de nó**, selecione **Sobretaxa**.
5. No campo **Código**, insira uma ID exclusiva para o nó, como **Sobretaxa de Transporte**.
6. Selecione **OK**.
7. No campo **Subtipo**, selecione **Total**.
8. Na FastTab **Base de absorção**, selecione **Novo** para criar um código de custo.
9. No campo **Código**, selecione um grupo de custos a ser usado para calcular a sobretaxa.
10. Opcional: Repita as etapas de 8 a 9 para cada grupo de custos adicional que deseje usar no cálculo.
11. Na FastTab **Sobretaxa**, selecione **Novo** para criar uma taxa.
12. No campo **Versão**, selecione a versão de custos na qual a sobretaxa deve ser adicionada.
13. Opcional: no campo **Site**, insira um site ao qual aplicar a sobretaxa.
14. No campo **Porcentagem**, insira a porcentagem a ser calculada em ordens de produção a partir de grupos de custos definidos na FastTab **Base de absorção**.
15. Na FastTab **Lançamentos contábeis**, selecione a conta principal a ser usada para os campos **Custos indiretos estimados absorvidos**, **Custo estimado de custos indiretos consumidos, WIP**, **Custo indireto absorvido** e **Custo de custo indireto consumido, WIP**.
16. Opcional: na FastTab **Dimensões financeiras**, especifique todas as dimensões financeiras a serem inseridas por padrão em transações quando elas forem lançadas na contabilidade.

O procedimento anterior mostra como criar um custo indireto do tipo **Sobretaxa**. Etapas semelhantes são usadas para criar outros tipos de custos indiretos. As seções a seguir descrevem as diferenças para cada tipo.

#### <a name="rate"></a>Alíquota

- Na etapa 4, selecione **Taxa** em vez de **Sobretaxa**.
- Na etapa 7, selecione **Processo**, **Configuração** ou **Quantidade** em vez de **Total**.
- Na etapa 11, use a FastTab **Taxa** em vez da FastTab **Sobretaxa**.
- Na etapa 14, insira um valor no campo **Valor**, em vez de uma porcentagem no campo **Porcentagem**.

#### <a name="output-unit-based"></a>Saída baseada em unidade

- Na etapa 4, selecione **Saída baseada em unidade** em vez de **Sobretaxa**.
- Na etapa 7, selecione **Quantidade**, **Peso** ou **Volume** em vez de **Total**.
- Ignore as etapas 8 a 10.
- Na etapa 11, use a FastTab **Taxa** em vez da FastTab **Sobretaxa**.

#### <a name="input-unit-based"></a>Entrada baseada em unidade

- Na etapa 4, selecione **Entrada baseada em unidade** em vez de **Sobretaxa**.
- Na etapa 7, selecione **Peso** ou **Volume** em vez de **Total**.
- Na etapa 11, use a FastTab **Taxa** em vez da FastTab **Sobretaxa**.
