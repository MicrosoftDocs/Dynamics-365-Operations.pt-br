---
title: "Roteiros e operações"
description: "Este tópico fornece informações sobre roteiros e operações. Um roteiro definir o processo do roteiro ou uma grade de produto. Descreve cada estágio (operação) no processo de produção e ordem em que as etapas devem ser executadas em. Para cada etapa, roteiro também define os recursos necessários de operações, o tempo de configuração necessários e execução, e como os custos devem ser calculados."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMDesigner, BOMDesignerRouteVersion, Route, RouteInventProd, RouteOpr, RouteOprTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 268124
ms.assetid: f78d5836-3e71-42b7-a5d1-41f19228d9d2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 556b9859d0b162b11f0bcbfc6552f6fd9a900596
ms.lasthandoff: 03/31/2017


---

# <a name="routes-and-operations"></a>Roteiros e operações

Este tópico fornece informações sobre roteiros e operações. Um roteiro definir o processo do roteiro ou uma grade de produto. Descreve cada estágio (operação) no processo de produção e ordem em que as etapas devem ser executadas em. Para cada etapa, roteiro também define os recursos necessários de operações, o tempo de configuração necessários e execução, e como os custos devem ser calculados.

<a name="overview"></a>Visão Geral
--------

Um roteiro descreve a ordem das operações que é necessário para produzir um produto ou grade de produto. Para cada operação, roteiro também define os recursos de operações necessário, o tempo necessário para configurar e executar a operação, e como os custos devem ser calculados. Você pode usar o mesmo roteiro para gerar vários produtos, ou definir um roteiro exclusivo para cada produto ou grade de produto. Você mesmo poderá ter mais roteiros para os mesmos produto. Nesse caso, o roteiro usada varia, dependendo fatoras como quantidade que deve ser gerada. A definição de um roteiro em Microsoft Dynamics 365 para operações consiste em quatro elementos separados que descrevem, juntos, o processo de produção:

-   ** O roteiro ** um roteiro – define a estrutura do processo de produção. Ou seja define a ordem das operações.
-   ** ** A operação – uma operação identifica uma etapa chamado em um roteiro, como ** assembly **. A mesma operação podem ocorrer como mais roteiros e podem ter números de operações diferentes.
-   ** O relação de operação ** – uma relação de operação define as propriedades operacionais de uma operação, como o tempo de configuração e o tempo de execução, categorias de custo previsto, parâmetros de consumo, e requisitos de recursos. A relação de operação habilita operacionais as propriedades de uma operação para variar, dependendo do que a operação é usada dentro ou produtos produzidos.
-   ** A versão de roteiro ** – uma versão de roteiro no roteiro usada para produzir um produto ou grade de produto. As versões de roteiros habilitam roteiros a ser reutilizadas por um produto ou alteradas pelo tempo. Também permitem roteiros diferentes a serem usadas para produzir os mesmos produto. Nesse caso, o roteiro usado depende de fatoras como local ou a quantidade que devem ser geradas.

## <a name="routes"></a>Roteiros
Um roteiro descreve a ordem de operações usadas para produzir um produto ou grade de produto. Cada operação é atribuído um número de operação e uma operação de sucessor. O formulário ordem das operações uma rede roteiro que pode ser representada por um gráfico direcionado com um ou mais pontos inicial e uma única empresa. Em dynamics 365 para operações, roteiros diferem com o tipo de estrutura. Os dois tipos de roteiros são roteiros e simples redes de roteiro. Os parâmetros de controle de produção, você pode especificar se apenas roteiros simples podem ser usadas, ou se as mais complexas redes de roteiro podem ser usadas.

### <a name="simple-routes"></a>Roteiros simples

Um roteiro simples será sequencial, e só houver um ponto de partida para o roteiro.  

[roteiro simples![(]. /media/routes-and-operations-1-simple-route.png)](. /media/routes-and-operations-1-simple-route.png)  

Se você habilitar apenas roteiros simples em parâmetros de controle de produção, o dynamics 365 para operações gera automaticamente os números de operações (10, 20, 30, etc) quando você define o roteiro.

### <a name="route-networks"></a>Redes de roteiro

Se você habilitar as mais complexas redes de roteiro nos parâmetros de controle de produção, você pode definir roteiros com vários pontos inicial e as operações que podem ser executados em paralelo.  

[![Route network](./media/routes-and-operations-2-route-network.png)](./media/routes-and-operations-2-route-network.png)  

**Observações:**

-   Cada operação pode ter somente uma sucessor, operação de roteiro e de todas deve terminar em uma única operação.
-   Não há garantia qual várias operações com a mesma operação de sucessor (operações por exemplo, 30 e 40 na ilustração anterior) serão executadas realmente em paralelo. A disponibilidade de capacidade e recursos podem ser colocadas restrições na forma como as operações são planejadas.
-   Você não pode usar 0 (zero) como o número de operação. O número que será reservado e usado para especificar que a última operação no roteiro não tenha nenhuma operação de sucessor.

### <a name="parallel-operations"></a>Operações paralelas

Ocasionalmente, uma combinação de vários recursos de operações que têm características diferentes é necessária para executar uma operação. Por exemplo, uma operação pode exigir de montagem, uma máquina e uma ferramenta, um trabalhador para cada dois computadores vigiem a operação. Esse exemplo puder ser modelado usando operações paralelas, na qual uma operação é designada como a operação principal e as outras serão secundário.  

[roteiro![com operações primárias e secundárias. (]/media/routes-and-operations-3-parallel-operations.png)](. /media/routes-and-operations-3-parallel-operations.png)  

Normalmente, a operação principal representa o recurso de afunilamento dita e o tempo de execução das operações secundárias. Entretanto, durante o plano que envolva a capacidade finita, os recursos que estão agendados para a operação principal e operações secundárias esteja disponível com a capacidade livre ao mesmo tempo.  

A operação principal e operações secundárias devem ter a mesma operação número 30 (na ilustração anterior).  

No exemplo acima, a necessidade de recursos para a operação principal (30) no computador, enquanto os requisitos de recursos para as operações secundárias ('30 e 30 ") são a ferramenta e o trabalhador. Ajuda da carga de cinquenta- porcentagem garantem o trabalhador planejado pode vigiar dois computadores ao mesmo tempo.

### <a name="approval-of-routes"></a>Aprovação de roteiros

Um roteiro deve ser aprovada para ser usada no planejamento ou no processo de fabricação. Aprovação indica que a criação de roteiros for concluído. Os produtos lançados mesma ou grade liberada de produto podem ter mais roteiros aprovadas. Normalmente, a aprovação de um roteiro ocorre quando a primeira versão de roteiro é aprovada. Porém, algumas em cenários comerciais, aprovação de roteiro e a versão de roteiro são atividades separadas que podem envolver proprietários diferentes de processo.  

Cada roteiro pode ser aprovada ou reprovado separadamente. Entretanto, para que, quando um roteiro for reprovada, todas as versões de roteiro relacionadas também são reprovada. Os parâmetros de controle de produção, você pode especificar se os roteiros podem ser reprovada, e se os roteiros aprovadas podem ser alteradas.  

Se você deve manter um log que registros quem aprova cada roteiro, você poderá solicitar assinaturas eletrônicas para aprovação de roteiro. Os usuários que terão em confirmar sua identidade usando [] assinatura eletrônica (/dynamics365/operations/organization-administration/electronic-signature-overview).

## <a name="operations"></a>Operações
Uma operação é uma etapa no processo de produção. Em dynamics 365 para operações, cada operação tiver uma ID e uma descrição simples. As tabelas a seguir mostram típicos exemplos de operações de uma loja de construção mecânica.

| Operação  | descrição        |
|------------|--------------------|
| PipeCut    | Corte de pipe       |
| TIGweld    | Soldadura de TIG        |
| JigAssy    | Montagem de gabarito       |
| Inspeção | Inspeção de qualidade |

As propriedades operacionais de operação, como o tempo de configuração e o tempo de execução, requisitos de recursos, informações de custo, e cálculo de consumo, especificadas na relação de operação. (Para obter mais informações sobre as relações de operação, consulte a seção a seguir.)

## <a name="operation-relations"></a>Relações de operação
As seguintes propriedades operacionais de uma operação são mantidas na relação de operação:

-   Categorias de custo
-   Parâmetros de consumo
-   Tempo de processamento
-   Quantidades de processamento
-   Requisitos de recursos
-   Notas e instruções

Você pode definir várias relações de operação para a mesma operação. Entretanto, todos relação de operação é específica a uma operação, armazenar as propriedades que são específicas a um roteiro, a um produto, liberados ou um conjunto de produtos lançados relacionados a um grupo de itens. Portanto, a mesma operação pode ser usada em mais roteiros com propriedades operacionais diferentes. Além disso, você pode facilmente mais manter os dados mestres se você usa operações padrão que têm as mesmas propriedades operacionais, independentemente de roteiro usada de produto e que são gerados. O escopo de relação de operação definido por ** código de item, ** ** relação de itens, ** ** código de roteiro ** ** e relação de roteiros ** propriedades, conforme mostrado na tabela.

| Código do item | Relação de item         | Código de roteiro | Relação de roteiro   | Escopo de relações de operação                                                                                                                                                                                                                                                                              |
|-----------|-----------------------|------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tabela     | &lt;ID do Item&gt;       | Roteiro      | &lt;ID do roteiro&gt; | As propriedades operacionais da operação quando usar em ID de roteiro do=de roteiro em ** número&lt;de roteiro **&gt; gerar os produtos lançados onde ** número ** ID&lt;de item do=&gt;.                                                                                                                        |
| Tabela     | &lt;ID do Item&gt;       | Todas        |                  | As propriedades operacionais padrão da operação quando usar para gerar os produtos lançados onde ** número ** ID&lt;de item do=&gt;. Ou seja essas propriedades operacionais se aplicam quando não houver relação específica roteiros da operação dos produtos lançados.                                     |
| Agrupar     | &lt;ID de grupo de itens&gt; | Roteiro      | &lt;ID do roteiro&gt; | As propriedades operacionais da operação quando usar roteiro onde ** número de roteiro ** a ID&lt;de roteiro do=&gt; liberou produzir o produto ao ID de grupo &lt;de itens do grupo de&gt;itens, a menos que haja uma relação específica roteiros da operação dos produtos lançados.                         |
| Agrupar     | &lt;ID de grupo de itens&gt; | Todas        |                  | As propriedades operacionais padrão da operação quando usar para gerar os produtos lançados associado à ID de grupo &lt;de itens do grupo de&gt;itens, a menos que uma relação de operação específico mais necessário.                                                                                                  |
| Todas       |                       | Roteiro      | &lt;ID do roteiro&gt; | As propriedades operacionais padrão de operação quando usar roteiro onde ** número de roteiro ** ID&lt;de roteiro do=&gt;. Ou seja essas propriedades operacionais se aplicam quando não houver relação de operação para esse roteiro específicas para produtos lançados ou ao grupo de itens associado. |
| Todas       |                       | Todas        |                  | As propriedades operacionais padrão de uma operação. Essas propriedades operacionais se aplicam quando uma relação mais específica da operação não existe.                                                                                                                                                                |

Você também pode especificar se uma relação de operação é específica a um site. Assim, as propriedades operacionais de uma operação podem variar, dependendo do local (isto é, o site) em que a operação é executada. Para produtos configurados, é possível especificar propriedades operacionais diferentes para cada configuração de produto.  

As relações de operação apresentam lotes a flexibilidade ao definir suas roteiros. Adicionalmente, a capacidade de definir os padrões propriedades reduz o valor dos dados mestre que você deve manter. Entretanto, essa flexibilidade também significa que esteja ciente o contexto que você alterar uma relação de operação em.  

** Observação: ** Porque as propriedades operacionais armazenado em relações de operação por operação por roteiro, todas as ocorrências a mesma operação (por exemplo, montagem) têm os mesmos tempo de instalação, tempo de execução, requisitos de recursos, etc. Portanto, se duas ocorrências de uma operação deve ocorrer no mesmo roteiro mas que o tempo de entrega diferente, você deve criar duas operações diferentes, como Assembly1 e Assembly2.

### <a name="modifying-product-specific-routes"></a>Roteiros específicos de produtos de alteração

Quando você abre ** roteiro ** o página ** detalhes lançados de produto ** de página, as versões de roteiro associadas com os produtos lançados selecionados serão mostradas. Neste contexto, para cada operação, o dynamics 365 para operações mostra as propriedades operacionais de relação de operação do melhor corresponde a versão de roteiro. Você observará a lista de operações inclui ** código de item e ** ** código de roteiro ** propriedades da relação de operação. Portanto, você pode determinar qual a relação de operação é mostrada.  

** Roteiro ** na página, você pode modificar as propriedades operacionais de operação, como o tempo de entrega ou categorias de custo previsto. As alterações são armazenadas na relação de operação específicas ao roteiro e os produtos lançados que são referidos na versão de roteiro atual. Se a relação de operação que será mostrada não é específico ao roteiro e os produtos lançados, antes que as alterações sejam armazenadas, o sistema cria uma cópia da relação de operação. Este centro de *is* de impressão a roteiro e os produtos lançados. Portanto, as alterações não afetarão outros roteiros ou produtos lançados. Para verificar se a relação da operação está sendo alterado ** roteiro ** na página, o aspecto ** o código de item e ** ** o código de roteiro ** campos.  

Você também pode criar manualmente uma operação que seja específico a um roteiro a um produto e liberados usando ** relação de impressão e de edição ** a função.  

** Observação: ** Se você adicionar uma nova operação a um roteiro ** roteiro ** na página, uma relação de operação será criada apenas aos produtos lançados atual. Portanto, se o roteiro também é usada para gerar outros produtos lançados, nenhuma relação de operação aplicável existirá desses produtos lançados, roteiro e pode não ser usada para os produtos lançados.

### <a name="maintaining-operation-relations-per-route"></a>Relações mantendo a operação por roteiro

Quando você abre ** roteiro detalha ** o página ** roteiros ** página de listagem, uma lista de todas as relações de operação que se aplicam ao roteiro selecionada será exibida. Portanto, você pode facilmente verificar quais propriedades operacionais são usadas de produto. Você pode alterar os valores de propriedade padrão e valores de propriedade do produto.  

Se você adicionar uma nova relação de operação ** roteiro detalha ** na página, ** código de roteiro ** o campo é definido automaticamente ** ** roteiro, e ** relação de roteiros ** o campo é definido como o número de roteiro de roteiro atual.

### <a name="maintaining-operation-relations-per-operation"></a>Relações mantendo a operação por operação

** Operações ** de página, é possível abrir ** relações de operação ** a página. Nesta página, você poderá alterar todas as relações de operação para uma operação específica. Você mesmo poderá alterar as relações de operação que contêm valores padrão.  

Se sua empresa usar operações padrão, e se os parâmetros operacionais forem iguais em todos os processos, produtos e ** relações de operação ** o página fornece uma maneira conveniente de manter as propriedades operacionais padrão das operações.

### <a name="applying-operation-relations"></a>Aplicando relações de operação

Em alguns casos, o dynamics 365 para operações devem localizar as propriedades operacionais de uma operação. Por exemplo, quando uma ordem de compra é criada, as propriedades operacionais de cada operação devem ser copiadas das relações de operação para o roteiro de produção. Nessas situações, o dynamics 365 operações pesquisa para as relações de operação correspondentes da combinação mais específica a combinação menos específica.  

Quando o dynamics 365 para pesquisas de operações para o parceiro mais relevante na operação de um produto, liberados uma relação de operação que corresponda ID do item de produto for liberado preferida sobre uma relação de operação que corresponda a ID de grupo. Por sua vez, a relação de operação que corresponda a ID de grupo de itens é preferível padrão sobre a relação de operação. A pesquisa for feita na seguinte ordem:

1.  ** Código de item **=** tabela ** ** e relação de itens ** ID&lt;de item do=&gt;
2.  ** Código de item ** **=grupo ** ** e relação de itens ** ID&lt;de grupo de itens do=&gt;
3.  ** Código de item tudo **=** **
4.  ** Código de roteiro **=** roteiro ** ** e relação de roteiros ** ID&lt;de roteiro do=&gt;
5.  ** Código de roteiro **=** tudo **
6.  ** Configuração ** ID&lt;=configuração do=&gt;
7.  **Configuration**=
8.  ** Site ** ID&lt;do site do=&gt;
9.  **Site**=

Portanto, uma operação seja usada apenas uma vez para cada roteiro. Se a operação ocorre várias vezes no mesmo roteiro, todas as ocorrências da operação terá a mesma relação de operação, e você não poderá ter propriedades diferentes (por exemplo, tempo de execução) para cada ocorrência.

## <a name="route-versions"></a>Versões de roteiro
As versões de roteiro são usadas para acomodar variações na produção de produtos ou fornecer maior controle sobre o processo de produção. Defina o roteiro deve ser usada quando um determinado produto ou liberou a variante de produto for liberado gerada. Você pode usar restrições estas para definir que o roteiro é usada para um produto liberadas:

-   Dimensões de produtos (, tamanho, cor, estilo e configuração)
-   Quantidade de produção
-   Site de produção
-   Datas de produção

Quando estiver gerando produtos em um site específico, uma quantidade específica, ou um período específico, você pode designar uma versão de roteiro específica como a versão de roteiro padrão. Entretanto, para que apenas um roteiro ativo será permitida produto liberados dados e um conjunto específico de restrições.  

Os parâmetros de controle de produção, você pode exigir que o período de validade de uma versão de roteiro seja especificado sempre.

### <a name="approval-of-route-versions"></a>Aprovação de versões de roteiro

Antes que uma versão de roteiro pode ser usada no planejamento ou no processo de fabricação, deve ser aprovada. Quando você aprova uma versão de roteiro, você também pode aprovar o roteiro relacionadas. Entretanto, para que uma versão de roteiro pode ser aprovada somente se o roteiro relacionadas também é aprovada.

### <a name="activating-the-default-route-version"></a>Ativando a versão de roteiro padrão

Quando você ativa uma versão de roteiro, você designa-a como a versão de roteiro padrão em que o planejamento mestre usará, ou que será usada para criar ordens de produção. Você só pode ter uma versão de roteiro ativa para um conjunto específico de restrições (por exemplo, período, site, ou quantidade.) Se a versão que você está tentando ativar conflitos com uma versão que esteja ativa, você receberá uma mensagem de erro. Para impedir a ativação ambígua, é necessário em desativar a versão em conflito ou alterar as restrições (normalmente o período) na versão de roteiro.

### <a name="electronic-signatures"></a>Assinaturas eletrônicas

Se você deve manter um log que registros que aprovar e ativar cada versão de roteiro, você poderá solicitar assinaturas eletrônicas para estas tarefas. Os usuários que aprovam e ativar versões de roteiros que terão em confirmar sua identidade usando [] assinatura eletrônica (/dynamics365/operations/organization-administration/electronic-signature-overview).

### <a name="product-change-that-uses-case-management"></a>Alteração de produto usando gerenciamento case

Exemplos de alteração de produto para a aprovação e a ativação de novas ou alteradas roteiros e versões de roteiro apresentam uma maneira fácil ver uma visão geral das restrições da versão de roteiro. Você também pode aprovar e ativar todos os roteiros relacionadas a uma alteração específica em uma operação e documentar os resultados em exemplos de alteração de produto.

## <a name="maintaining-routes"></a>Roteiros de manutenção
Dependendo das suas necessidades comerciais, você pode reduzir o poder esforço necessário para manter as definições de processo.

### <a name="making-routes-independent-of-resources"></a>Nota fiscal sem roteiros de recursos

Em vários sistemas, o recurso de operações ou o grupo de recursos que devem realizar uma operação devem ser especificados no roteiro. Entretanto, em dynamics 365 para operações, você pode definir um conjunto de requisições que um recurso de operações deve atender para ser qualificado para a operação. Portanto, o recurso de operações ou o grupo de recursos específicos que devem ser usados não precisam ser definido quando a operação está programada realmente. Essa funcionalidade é especialmente útil quando você tiver vários funcionários ou máquinas que podem ser a mesma operação.  

Por exemplo, especificar que uma operação requer um recurso de operações de computador ** ** digita que tem a carimbando ** ** um recurso toneladas de 20. O mecanismo de planejamento resolverá nesses requisitos a um recurso de operações ou a um grupo de recursos específicos quando a operação está programada. Como é possível apenas especificar esses requisitos em vez de associar a um computador específico, você terá muito mais flexível. Adicionalmente, manutenção será mais fácil quando os recursos são movidos ou os recursos novos são adicionados.  

Para obter mais informações sobre os vários tipos de requisitos de recursos e usá-los como, consulte requisitos de recursos de operações e recursos [] do recurso (resource-capabilities.md).

### <a name="sharing-routes-across-sites"></a>O compartilhamento roteiros entre sites

Se você gera os mesmos produto em mais de um site de produção e, se as etapas para produzir os produtos forem iguais em todos os locais, você pode criar um roteiro normalmente compartilhada usada em todas sites de produção. Para criar um roteiro compartilhada, não especificar um site no próprio. Entretanto, você ainda deve criar uma versão de roteiro que o roteiro compartilhada associe com os produtos em cada site.  

Você também deve garantir que os requisitos de recursos para cada operação no roteiro não chamam para recursos de operações ou grupos de recursos específicos, mas é expresso vez em termos das características dos recursos necessários. O mecanismo de planejamento pode atribuir os recursos de operações apropriados de local que a produção será planejada sobre. Por exemplo, se houver pequenas diferenças o tempo de execução, ou se o tempo de configuração para uma determinada operação são específicos do site, você pode especificar essas informações adicionais adicionando uma relação de operação para esse site.  

Para tomar vantagem total de benefícios compartilhadas de roteiros, você também pode usar o recurso consumo da lista de materiais correspondente (BOM). Quando você define o sinalizador para o consumo de recursos EM a linha de BOM, o depósito no local e as matérias-primas que devem ser consumidas for inferido do recurso de operações que a operação está programada. sobre Portanto, o depósito e o local não devem ser determinados até que a produção seja efetivamente programada. Assim, você pode fazer a BOM e o roteiro independentemente do local físico produtos onde são gerados.

### <a name="standard-operation-relations"></a>Relações de operação padrão

Se sua empresa usar estandardizadas operações na produção, além se houver nenhuma quase variação no tempo de instalação, tempo de execução, cálculo de consumo, cálculo de custo estimado, etc, é possível aproveitar a padrões de criar relações de operação para as operações. Nesse caso, não crie criar relações de operação que são específicas para qualquer roteiro ou produtos lançados.  

Se também expressa requisitos de recursos em termos de habilidades e recursos, fazer roteiros site suas independentes, poderá ajudar a manter a manutenção em curso dos processos ao mínimo.  

Quando você usa esta abordagem, ** relações de operação ** o página se tornar o alvo principal para o tempo de execução e mantendo outras propriedades.

### <a name="resource-specific-process-times"></a>tempo Recurso- específicos de processo

Se você não especificar um recurso de operações ou um grupo de recursos como parte dos requisitos de recursos para uma operação, os recursos aplicáveis podem operar em velocidades diferentes. Portanto, o tempo necessário para processar uma operação poderá variar. Para resolver esse problema, você pode usar ** fórmula ** coloca na relação de operação para especificar como o tempo de processo é calculado. As opções a seguir estão disponíveis:

-   ** O padrão ** – (opção padrão) o cálculo usa somente os campos da relação de operação e multiplicar o tempo de entrega especificado pela quantidade da ordem.
-   ** Capacidade ** – o cálculo incluirá ** capacidade ** campo de recursos de operações. Portanto, o tempo é recurso- dependente. O valor especificado no recurso de operações é capacidade por hora. Esse valor é multiplicado pela quantidade da ordem e fatora ** ** o valor da relação de operação.
-   ** O lote – ** uma capacidade de lotes são calculados usando as informações de relação de operação. O número de lotes e, assim, os tempos de processamento podem ser calculados com base na ordem.
-   ** O lote de recurso ** – esta opção é basicamente idêntico ** lote ** a opção. Entretanto, o cálculo incluirá ** capacidade de lote ** campo de recursos de operações. Portanto, o tempo é recurso- dependente.


<a name="see-also"></a>Consulte também
--------

[Bills of materials and formulas](bill-of-material-bom.md)

[Cost categories used in production routing](../cost-management/cost-categories-used-production-routings.md)

[Resource capabilities](resource-capabilities.md)

[Electronic signature overview](/dynamics365/operations/organization-administration/electronic-signature-overview)


