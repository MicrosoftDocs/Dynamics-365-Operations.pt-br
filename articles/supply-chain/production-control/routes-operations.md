---
title: Roteiros e operações
description: Este tópico fornece informações sobre roteiros e operações.
author: sorenva
manager: tfehr
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMDesigner, BOMDesignerRouteVersion, Route, RouteInventProd, RouteOpr, RouteOprTable
ms.author: sorenand
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 268124
ms.assetid: f78d5836-3e71-42b7-a5d1-41f19228d9d2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f2422dcec1fb222f1be7162d7c799a13046329b4
ms.sourcegitcommit: f0faa2929435cd1408c5925f0ee4d6636fec5da1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/13/2020
ms.locfileid: "3552908"
---
# <a name="routes-and-operations"></a>Roteiros e operações

[!include [banner](../includes/banner.md)]

Este tópico fornece informações sobre roteiros e operações. Um roteiro define o processo para produção de um produto ou grade de produto. Ele descreve cada estágio (operação) no processo de produção e a ordem em que essas etapas devem ser executadas. Para cada etapa, o roteiro também define os recursos de operações necessários, os tempos de configuração e execução necessários, e como o custo deve ser calculado.

<a name="overview"></a>Visão Geral
--------

Um roteiro descreve a ordem de operações necessárias para produzir um produto ou grade de produto. Para cada operação, o roteiro também define os recursos de operações necessários, o tempo necessário para configurar e realizar a operação, e como o custo deve ser calculado. Você pode usar o mesmo roteiro para produzir vários produtos, ou você pode definir um roteiro exclusivo para cada produto ou grade de produto. Você pode ainda ter vários roteiros para o mesmo produto. Nesse caso, o roteiro utilizado varia de acordo com fatores tais como a quantidade que deve ser produzida. A definição de um roteiro no Supply Chain Management consiste em quatro elementos distintos que, juntos, descrevem o processo de produção:

-   **Roteiro** – Um roteiro define a estrutura do processo de produção. Em outras palavras, ele define a ordem de operações.
-   **Operação** – Uma operação identifica uma etapa nomeada no roteiro, tal como **Montagem**. A mesma operação pode ocorrer em múltiplos roteiros e pode ter diferentes números de operação.
-   **Relação de operação** – Uma relação de operação define as propriedades operacionais de uma operação, tais como os tempos de configuração e execução, categorias de custo, parâmetros de consumo e requisitos de recursos. A relação de operação permite que as propriedades operacionais de uma operação varie, de acordo com o roteiro em que a operação é usada ou com os produtos que estão sendo produzidos.
-   **Versão do roteiro** – Uma versão do roteiro define o roteiro usado para produzir um produto ou grade de produto. As versões de roteiros permitem que os roteiros sejam reutilizados em diferentes produtos ou modificados com o passar do tempo. Elas também permitem que diferentes roteiros sejam utilizados para produzir o mesmo produto. Nesse caso, o roteiro utilizado varia de acordo com fatores tais como a localização ou a quantidade que deve ser produzida.

## <a name="routes"></a>Roteiros
Um roteiro descreve a ordem de operações usadas para produzir um produto ou grade de produto. Cada operação recebe um número de operação e uma operação sucessora. A ordem de operações forma uma rede de roteiros que pode ser representada por um gráfico direcionado que possui um ou mais pontos de início e um único ponto de término. No Supply Chain Management, os roteiros são diferenciados com base no tipo de estrutura. Os dois tipos de roteiros são roteiros simples e redes de roteiros. Nos parâmetros de Controle de produção, você pode especificar se apenas roteiros simples podem ser usados, ou se redes de roteiros mais complexas podem ser usadas.

### <a name="simple-routes"></a>Roteiros simples

Um roteiro simples é sequencial, e existe apenas um ponto de início para o roteiro.  

[![Roteiro simples](./media/routes-and-operations-1-simple-route.png)](./media/routes-and-operations-1-simple-route.png)  

Se você habilitar apenas roteiros simples nos parâmetros de Controle de produção, o Supply Chain Management vai gerar automaticamente os números de operações (10, 20, 30, e assim por diante) quando você definir o roteiro.

### <a name="route-networks"></a>Redes de roteiros

Se você habilitar as redes de roteiros mais complexas nos parâmetros de Controle de produção, você pode definir roteiros com múltiplos pontos de início e operações que podem acontecer em paralelo.  

[![Rede de roteiro](./media/routes-and-operations-2-route-network.png)](./media/routes-and-operations-2-route-network.png)  

> [!NOTE]
> -   Cada operação pode ter apenas uma operação sucessora, e todo o roteiro deve terminar em uma única operação.
> -   Isso não garante que várias operações que tenham a mesma operação sucessora (por exemplo, as operações 30 e 40 na ilustração anterior) sejam executadas em paralelo. A disponibilidade e a capacidade de recursos pode colocar restrições no modo como as operações são agendadas.
> -   Você não pode usar 0 (zero) como número de operação. Esse número é reservado e utilizado para especificar que a última operação do roteiro não possui uma operação sucessora.

### <a name="parallel-operations"></a>Operações paralelas

Eventualmente, é necessária uma combinação de vários recursos de operações que têm características diferentes para realizar uma operação. Por exemplo, uma operação de montagem pode precisar de uma máquina, uma ferramenta e um trabalhador para cada duas máquinas, para supervisionar a operação. Esse exemplo pode ser modelado usando operações paralelas, onde uma operação é designada como operação primária e as demais como secundárias.  

[![Roteiro que possui operações primária e secundárias](./media/routes-and-operations-3-parallel-operations.png)](./media/routes-and-operations-3-parallel-operations.png)  

Normalmente, a operação primária representa o gargalo de recursos e impõe o tempo de execução para as operações secundárias. No entanto, durante o agendamento que envolve capacidade finita, os recursos agendados para ambas as operações primária e secundárias devem estar disponíveis e ter capacidade livre ao mesmo tempo.  

Tanto a operação primária como as secundárias devem possuir o mesmo número de operação (30 na ilustração anterior).  

No exemplo anterior, o requisito de recurso para a operação primária (30) é a máquina, enquanto os requisitos de recursos para as operações secundárias (30' e 30'') são a ferramenta e o o trabalhador. Uma carga de cinquenta por cento ajuda a garantir que o trabalhador agendado possa supervisionar duas máquinas ao mesmo tempo.

### <a name="approval-of-routes"></a>Aprovação de roteiros

Um roteiro deve ser aprovado antes que possa ser usado no planejamento ou processo de fabricação. A aprovação indica que a criação do roteiro foi concluída. O mesmo produto lançado ou grade de produto lançada pode ter diversos roteiros aprovados. Normalmente, a aprovação de um roteiro acontece quando a primeira versão relevante do roteiro é aprovada. Porém, em alguns cenários comerciais, a aprovação do roteiro e da versão do roteiro são atividades distintas que podem envolver diferentes donos de processos.  

Cada roteiro pode ser aprovado ou reprovado separadamente. No entanto observe que, quando um roteiro é reprovado, todas as versões de roteiro relacionadas também são reprovadas. Nos parâmetros de Controle de produção, você pode especificar se os roteiros podem ser reprovados, e se os roteiros aprovados podem ser alterados.  

Caso precise manter um registro sobre quem aprova cada roteiro, você pode solicitar assinaturas eletrônicas para aprovação de roteiros. Os usuários terão que confirmar suas identidades utilizando uma [assinatura eletrônica](../../fin-and-ops/organization-administration/electronic-signature-overview.md).

## <a name="operations"></a>Operations
Uma operação é uma etapa no processo de produção. Cada operação tem uma ID e uma descrição simples. As tabelas a seguir mostram exemplos típicos de operações em uma oficina mecânica.

| Operação  | descrição        |
|------------|--------------------|
| PipeCut    | Corte de tubos       |
| TIGweld    | Solda TIG        |
| JigAssy    | Gabarito de montagem       |
| Inspeção | Inspeção de qualidade |

As propriedades operacionais da operação, tais como os tempos de configuração e execução, os requisitos de recursos, as informações de custo e o cálculo de consumo são especificadas na relação de operação. (Para obter mais informações sobre relações de operações, consulte a próxima seção.)

## <a name="operation-relations"></a>Relações de operação
As seguintes propriedades operacionais de uma operação são mantidas na relação de operação:

-   Categorias de custo
-   Parâmetros de consumo
-   Tempos de processamento
-   Quantidades de processamento
-   Requisitos de recursos
-   Observações e instruções

Você pode definir várias relações de operação para a mesma operação. No entanto, cada relação de operação é específica para uma operação, e armazena propriedades que são específicas de um roteiro, produto lançado ou um conjunto de produtos lançados relacionados a um grupo de itens. Portanto, a mesma operação pode ser usada em diversos roteiros com propriedades operacionais diferentes. Além disso, você pode preservar seus dados mestre com mais facilidade se usar operações padrão que possuam as mesmas propriedades operacionais, independentemente do roteiro utilizado e do produto produzido. O escopo da relação de operação é definido pelas propriedades **Código do item**, **Relação do item**, **Código do roteiro** e **Relação do roteiro**, como mostrado na tabela a seguir.

| Código do item | Relação de item         | Código de roteiro | Relação de roteiro   | Escopo da relação de operação                                                                                                                                                                                                                                                                              |
|-----------|-----------------------|------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tabela     | &lt;ID do Item&gt;       | Roteiro      | &lt;ID do roteiro&gt; | As propriedades operacionais de uma operação, quando é utilizada no roteiro onde **Número do roteiro**=&lt;ID do roteiro&gt; para produzir o produto lançado, onde **Número do item**=&lt;ID do item&gt;.                                                                                                                        |
| Tabela     | &lt;ID do Item&gt;       | Todas        |                  | As propriedades operacionais padrão de uma operação, quando usada para produzir o produto lançado onde **Número do item**=&lt;ID do item&gt;. Em outras palavras, essas propriedades operacionais se aplicam quando não existe uma relação de operação para um roteiro específico, para o produto lançado.                                     |
| Agrupar     | &lt;ID do grupo de itens&gt; | Roteiro      | &lt;ID do roteiro&gt; | As propriedades operacionais de uma operação, quando é usada em um roteiro onde **Número do roteiro**=&lt;ID do roteiro&gt; para produzir produtos lançados associados ao grupo de itens &lt;ID do grupo de itens&gt;, a menos que exista uma relação de operação de roteiro específico para o produto lançado.                         |
| Agrupar     | &lt;ID do grupo de itens&gt; | Todas        |                  | As propriedades operacionais padrão de uma operação, quando é usada para produzir produtos lançados associados ao grupo de itens &lt;ID do grupo de itens&gt;, a menos que exista uma relação de operação mais específica.                                                                                                  |
| Todas       |                       | Roteiro      | &lt;ID do roteiro&gt; | As propriedades operacionais padrão de operação, quando é usada em um roteiro onde **Número do roteiro**=&lt;ID do roteiro&gt;. Em outras palavras, essas propriedades operacionais se aplicam quando não existe uma relação de operação para esse roteiro, que é específico para o produto lançado ou para seu grupo de itens associado. |
| Todas       |                       | Todas        |                  | As propriedades operacionais padrão de uma operação. Essas propriedades operacionais se aplicam quando não existe uma relação de operação mais específica.                                                                                                                                                                |

Você também pode especificar se uma relação de operação é específica a um local. Assim, as propriedades operacionais de uma operação podem variar, de acordo com a localização (isto é, o local) onde a operação é executada. Para produtos configurados, também é possível especificar propriedades operacionais diferentes para cada configuração do produto.  

As relações de operações oferecem muita flexibilidade ao definir seus roteiros. Adicionalmente, a capacidade de definir propriedades padrão ajuda a reduzir a quantidade de dados mestre que você deve manter. No entanto, essa flexibilidade também significa que você deve estar ciente sobre o contexto no qual uma operação é modificada.  

> [!NOTE]
> Pelo fato de as propriedades operacionais serem armazenadas nas relações de operações por operação para cada roteiro, todas as ocorrências da mesma operação (por exemplo, Montagem) possuem os mesmos tempo de configuração, tempo de execução e requisitos de recursos. Portanto, se duas ocorrências de uma operação devem acontecer no mesmo roteiro, mas possuem tempos de execução diferentes, você deve criar duas operações separadas, por exemplo Montagem1 e Montagem2.

### <a name="modifying-product-specific-routes"></a>Modificando roteiros de produtos específicos

Ao abrir a página **Roteiro** através da página **Detalhes do produto lançado**, as versões de roteiro associadas ao produto lançado selecionado são exibidas. Nesse contexto, para cada operação, o Supply Chain Management mostra as propriedades operacionais da relação de operação que mais corresponde à versão do roteiro. Você irá perceber que a lista de operações inclui as propriedades **Código do item** e **Código do roteiro** da relação de operação. Portanto, você pode determinar qual relação de operação é exibida.  

Na página **Roteiro**, você pode modificar as propriedades operacionais da operação, como o tempo de execução ou as categorias de custo. As alterações são armazenadas na relação de operação específica ao roteiro e ao produto lançado referenciados na versão atual do roteiro. Se a relação de operação exibida não é específica ao roteiro e ao produto lançado, antes que as alterações sejam armazenadas, o sistema cria uma cópia da relação de operação. Essa cópia *é* específica ao roteiro e ao produto lançado. Portanto, suas alterações não afetarão outros roteiros ou produtos lançados. Para verificar qual relação de operação está sendo modificada na página **Roteiro**, observe os campos **Código do item** e **Código do roteiro**.  

Também é possível criar manualmente uma operação específica a um roteiro e a um produto lançado utilizando a função **Copiar e editar relação**.  

> [!NOTE]
> Se você adicionar uma nova operação em um roteiro na página **Roteiro**, uma relação de operação será criada apenas para o produto liberado atual. Portanto, se o roteiro também é usado para produzir outros produtos, não existirá uma relação de operação aplicável para esses produtos e o roteiro não poderá mais ser utilizado para esses produtos.

### <a name="maintaining-operation-relations-per-route"></a>Mantendo as relações de operações por roteiro

Ao abrir a página **Detalhes do roteiro** através da página de lista **Roteiros**, uma lista com todas as relações de operações que se aplicam ao roteiro selecionado é exibida. Portanto, você pode facilmente verificar quais propriedades operacionais são usadas para cada produto. Você pode alterar ambos os valores de propriedade padrão e os valores de propriedade específicos ao produto.  

Se você adicionar uma nova relação de operação na página **Detalhes do roteiro**, o campo **Código do roteiro** é automaticamente definido como **Roteiro**, e o campo **Relação do roteiro** é definido como o número de roteiro do roteiro atual.

### <a name="maintaining-operation-relations-per-operation"></a>Mantendo as relações de operações por operação

Na página **Operações**, você pode abrir a página **Relações de operações**. Nesta página, você pode alterar todas as relações de operações para uma operação específica. Você pode até modificar relações de operações que contêm valores padrão.  

Se sua empresa utiliza operações padrão, e se os parâmetros operacionais são os mesmos para todos os produtos e processos, a página **Relações de operações** oferece um modo conveniente para preservar as propriedades operacionais padrão dessas operações.

### <a name="applying-operation-relations"></a>Aplicando relações de operações

Em alguns casos, o Supply Chain Management deve encontrar as propriedades operacionais de uma operação. Por exemplo, quando uma ordem de compra é criada, as propriedades operacionais de cada operação devem ser copiadas das relações de operações para o roteiro de produção. Nessas situações, o Supply Chain Management busca as relações de operação relevantes desde a combinação mais específica até a menos específica.  

Quando o Supply Chain Management busca a relação de operação mais relevante para um produto lançado, uma relação de operação com a mesma ID do item do produto lançado tem preferência sobre uma relação de operação que corresponde à ID do grupo do item. Por sua vez, uma relação de operação com o mesmo ID do grupo de itens é preferida ao invés da relação de operação padrão. A busca é realizada na seguinte ordem:

1.  **Código do item**=**Tabela** e **Relação de item**=&lt;ID do item&gt;
2.  **Código do item**=**Grupo** e **Relação de item**=&lt;ID do grupo de itens&gt;
3.  **Código do item**=**Todos**
4.  **Código do roteiro**=**Roteiro** e **Relação de roteiro**=&lt;ID do roteiro&gt;
5.  **Código do roteiro**=**Todos**
6.  **Configuração**=&lt;ID da configuração&gt;
7.  **Configuração**=
8.  **Local**=&lt;ID do local&gt;
9.  **Local**=

Portanto, uma operação deve ser usada apenas uma vez em cada roteiro. Se a operação ocorre várias vezes no mesmo roteiro, todas as ocorrências dessa operação terão a mesma relação de operação, e não será possível ter propriedades diferentes (por exemplo, tempos de execução) para cada ocorrência.

## <a name="route-versions"></a>Versões de roteiro
As versões de roteiro são usadas para acomodar variações na produção de produtos ou proporcionar maior controle sobre o processo de produção. Elas definem qual roteiro deve ser usado quando um produto específico ou grade de produto específica é produzido(a). Você pode usar as seguintes restrições para definir qual roteiro é usado para um produto lançado:

-   Dimensões do produto (tamanho, cor, estilo ou configuração)
-   Quantidade de produção
-   Local de produção
-   Data de produção

Quando estiver produzindo o produto em um local específico, com uma quantidade específica, ou em um período específico, você pode designar uma versão de roteiro específica como a versão de roteiro padrão. No entanto, observe que é permitido apenas um roteiro ativo para um certo produto lançado e um certo conjunto de restrições.  

Nos parâmetros de Controle de produção, você pode solicitar que o prazo de validade de uma versão do roteiro sempre esteja especificado.

### <a name="approval-of-route-versions"></a>Aprovação de versões do roteiro

Antes que uma versão do roteiro possa ser utilizada no planejamento ou no processo de fabricação, ela deve ser aprovada. Quando uma versão do roteiro é aprovada, também é possível aprovar o roteiro relacionado. No entanto, observe que uma versão do roteiro somente pode ser aprovada se o roteiro relacionado também for aprovado.

### <a name="activating-the-default-route-version"></a>Ativando a versão do roteiro padrão

Ao ativar uma versão do roteiro, ela é designada como a versão do roteiro padrão que o planejamento mestre irá usar, ou que será utilizada para criar ordens de produção. Você pode ter apenas uma versão de roteiro ativa para um certo conjunto de restrições (por exemplo, período, local ou quantidade). Se a versão que estiver tentando ativar apresentar conflito com uma versão que esteja ativa, você receberá uma mensagem de erro. Para prevenir uma ativação ambígua, você deve desativar a versão que causa conflito ou modificar as restrições (geralmente o período) na versão do roteiro.

### <a name="electronic-signatures"></a>Assinaturas eletrônicas

Caso precise manter um registro sobre quem aprova e ativa cada versão do roteiro, você pode solicitar assinaturas eletrônicas para essas tarefas. Os usuários que aprovam e ativam versões de roteiros terão que confirmar suas identidades usando uma [assinatura eletrônica](../../fin-and-ops/organization-administration/electronic-signature-overview.md).

### <a name="product-change-that-uses-case-management"></a>Alteração de produto utilizando gerenciamento de caso

O caso de alteração de produto para aprovação ou ativação de roteiros ou versões de roteiros novos ou modificados oferece uma maneira fácil para visualizar um resumo das restrições da versão do roteiro. Você também pode aprovar e ativar todos os roteiros relacionadas a uma alteração específica em uma operação e documentar os resultados no caso de alteração de produto.

## <a name="maintaining-routes"></a>Mantendo roteiros
Dependendo das suas necessidades comerciais, você poderá reduzir o esforço necessário para manter suas definições de processo.

### <a name="making-routes-independent-of-resources"></a>Tornar os roteiros independentes dos recursos

Em vários sistemas, o recurso de operações ou grupo de recursos que deve realizar uma operação deve ser especificado no roteiro. No entanto, no Supply Chain Management, você pode definir um conjunto de requisitos que um recurso de operações deve atender para se tornar aplicável à operação. Portanto, o recurso de operações ou grupo de recursos específicos que devem ser usados não precisam ser determinados até que a operação esteja de fato agendada. Essa funcionalidade é especialmente útil quando existem muitos trabalhadores ou máquinas capazes de realizar a mesma operação.  

Por exemplo, você especifica que uma operação necessita de um recurso de operação do tipo **Máquina** com uma capacidade de **Estampagem** de 20 toneladas. O mecanismo de planejamento irá então resolver os requisitos para um recurso de operações ou grupo de recursos específico assim que a operação for agendada. Como é possível apenas especificar esses requisitos em vez de associar a operação a uma máquina específica, você terá muito mais flexibilidade. Adicionalmente, a manutenção será mais fácil quando os recursos forem movidos ou novos recursos forem adicionados.  

Para obter mais informações sobre os diversos tipos de requisitos de recurso e como utilizá-los, consulte Requisitos de recurso de operações e [Capacidades de recurso](resource-capabilities.md).

### <a name="sharing-routes-across-sites"></a>Compartilhando roteiros entre locais

Se você produz o mesmo produto em mais de um local de produção, e se as etapas para a produção do produto são as mesmas em todos os locais, é possível criar um roteiro compartilhado utilizado em todos os locais de produção. Para criar um roteiro compartilhado, não especifique um local no roteiro. No entanto, você deve ainda criar uma versão do roteiro que associa o roteiro compartilhado com o produto para cada local.  

Você também deve garantir que os requisitos de recurso para cada operação no roteiro não solicitem recursos de operações ou grupos de recursos específicos, mas que estejam expressos em termos das característica dos recursos necessários. O mecanismo de planejamento poderá então atribuir os recursos de operações apropriados a partir do local em que a produção está agendada. Por exemplo, se existem pequenas diferenças no tempo de execução, ou se o tempo de configuração para uma certa operação é específico para cada local, você pode especificar essa informação adicionando uma relação de operação adicional para aquele local.  

Para desfrutar de todas as vantagens dos roteiros compartilhados, você deve usar também o consumo de recurso na lista de materiais (BOM) correspondente. Quando você define a referência para o consumo de recurso na linha da BOM, o depósito e o local de onde as matérias-primas devem ser consumidas são inferidos a partir do recurso de operações em que a operação está agendada. Portanto, o depósito e o local não precisam ser determinados até que a produção esteja de fato agendada. Assim, você pode fazer com que tanto a BOM quanto o roteiro sejam independentes em relação ao local físico onde o produto é produzido.

### <a name="standard-operation-relations"></a>Relações de operações padrão

Se sua empresa usa operações padronizadas ao longo da produção, e se existe pouca ou nenhuma variação no tempo de configuração, tempo de execução, cálculo de consumo, cálculo de custo, e assim por diante, você pode se beneficiar ao criar relações de operações padrão para todas as operações. Nesse caso, evite criar relações de operações específicas para algum roteiro ou produto lançado.  

Se você também expressar requisitos de recurso em termos de habilidades e capacidades, e tornar seus roteiros independentes em relação ao local, é possível manter a manutenção contínua do seu processo comercial em um nível mínimo.  

Ao utilizar essa abordagem, a página **Relações de operações** se torna seu principal destino para manter os tempos de execução e outras propriedades.

### <a name="resource-specific-process-times"></a>Tempos de processo específicos para cada recurso

Se você não especificar um recurso de operações ou um grupo de recursos como parte dos requisitos de recurso para uma operação, os recursos aplicáveis podem operar em velocidades diferentes. Portanto, o tempo necessário para processar uma operação poderá variar. Para solucionar esse problema, você pode usar o campo **Fórmula** na relação de operação para especificar como o tempo de processo é calculado. As opções a seguir estão disponíveis:

-   **Padrão** – (Opção padrão) O cálculo utiliza apenas os campos da relação de operação e multiplica o tempo de execução pela quantidade da ordem.
-   **Capacidade** – O cálculo inclui o campo **Capacidade** do recurso de operações. Portanto, o tempo depende do recurso. O valor especificado no recurso de operações é a capacidade por hora. O **Tempo de processamento** é calculado como a **Quantidade da ordem** dividida pela **Capacidade**.
-   **Lote** – Uma capacidade de lote é calculada utilizando informação da relação de operações. O número de lotes e, consequentemente, o tempo de processo podem então ser calculados com base na quantidade da ordem.
-   **Lote de recursos** – Essa opção é basicamente a mesma opção que **Lote**. No entanto, o cálculo inclui o campo **Capacidade de lote** do recurso de operações. Portanto, o tempo depende do recurso.

### <a name="set-up-route-groups"></a>Configurar grupos de roteiros

Você pode definir os grupos de roteiro e a configuração para os tipos de roteiro ou de trabalho em **Controle de produção > Configuração > Roteiros > Grupos de roteiros**. Para cada tipo de roteiro/trabalho no grupo de roteiros, você pode selecionar ou desmarcar as seguintes opções:

- **Ativação** - Selecione esta opção para permitir cálculos e planejamento referentes ao tipo de trabalho selecionado e para receber comentários sobre o trabalho quando você executar o planejamento de trabalho. Você precisa selecionar esta opção para habilitar o tipo de trabalho e, em seguida, selecionar o restante das opções desse tipo de trabalho. Se a ativação não for selecionada, esse tipo de trabalho não será habilitado, independentemente da seleção das outras opções. 
- **Gerenciamento de trabalho** - Selecione esta opção para incluir o tipo de trabalho no gerenciamento de trabalho ao executar o planejamento de trabalho. 
- **Horário de trabalho** - Selecione esta opção para agendar o tipo de trabalho de acordo com o calendário de horário de trabalho definido para o recurso de operações; do contrário, será usado o calendário gregoriano. O horário de trabalho pode ser planejado de acordo com o calendário gregoriano ou com o calendário de trabalho definido. Se você selecionar esta opção, o planejamento será baseado no calendário de horário de trabalho definido. Além disso, o tipo de trabalho é planejado a partir da meia-noite na data que é definida como a data de início do trabalho.
- **Capacidade** - Selecione esta opção para reservar capacidade para o tipo de trabalho ao executar o planejamento de trabalho. Se você selecionar esta opção, a capacidade será reservada quando o planejamento for executado para o tipo de trabalho selecionado. Isso fornece uma visão geral de quais tipos de trabalho em cada grupo de roteiros usam os recursos de operações. Por exemplo, em uma situação na qual recursos de secagem são recursos de afunilamento, esses recursos devem ser especificados como afunilamentos. As operações de secagem atribuídas aos tipos de trabalho com tempo de espera permitirão recursos de secagem. 

Para cada um dos tipos de trabalho, primeiro você precisa ativá-lo ou desativá-lo. Quando desativados, nenhuma outra configuração (Gerenciamento de trabalho, Horário de trabalho e Capacidade) será considerada, porque o tipo de trabalho não estará ativo. 

Entre os tipos de trabalho está Sobreposição. A sobreposição permite que diferentes trabalhos sejam executados ao mesmo tempo. Quando trabalhos se sobrepõem, os recursos podem ser usados, mas não podem ser reservados para trabalhos específicos.
Portanto, quando a ativação é selecionada para sobreposição, o restante das configurações (Gerenciamento de trabalho, Horário de trabalho e Capacidade) não afetam o grupo de roteiros. 

> [!NOTE]
> Quando você atualiza versões, pode se deparar com o seguinte erro: **“Erro de CRL ao invocar o mecanismo de planejamento”**. Se você receber esse erro, vá para a página **Grupos de roteiros** e, para todos os roteiros nos quais ativou **Sobreposição**, desmarque as opções **Gerenciamento de trabalho**, **Horário de trabalho** e **Capacidade**. 

## <a name="additional-resources"></a>Recursos adicionais

- [Listas de materiais e fórmulas](bill-of-material-bom.md)

- [Categorias de custo usadas no roteiro de produção](../cost-management/cost-categories-used-production-routings.md)

- [Capacidades de recurso](resource-capabilities.md)

- [Visão geral das assinaturas eletrônicas](../../fin-and-ops/organization-administration/electronic-signature-overview.md)



