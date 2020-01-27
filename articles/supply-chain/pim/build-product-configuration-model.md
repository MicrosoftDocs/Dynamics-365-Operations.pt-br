---
title: Visão geral de configuração do produto
description: A necessidade de configurar produtos para atender aos requisitos especiais está se tornando regra, e não exceção, em relações entre negócios e de negócio para consumidor.
author: cvocph
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 75083
ms.assetid: f08072b8-cb0b-43aa-9509-f5ec32caecd9
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7f05e119f02d2d5e7c76c554d6a8b3db97c86ab0
ms.sourcegitcommit: 4d77d06a07ec9e7a3fcbd508afdffaa406fd3dd8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934854"
---
# <a name="product-configuration-overview"></a>Visão geral de configuração do produto

[!include [banner](../includes/banner.md)]

A necessidade de configurar produtos para atender aos requisitos especiais está se tornando regra, e não exceção, em relações entre negócios e de negócio para consumidor.

Um fabricante que ofereça suporte a cenários configure para solicitar tem a oportunidade atentar às necessidades do cliente. Além disso, ao armazenar mercadorias semiacabadas na forma de componentes genéricos em vez de produtos acabados, o fabricante pode reduzir o capital vinculado ao estoque.  

Um movimento com êxito de uma configuração de fabricação-a-estoque para uma configuração de configure para solicitar requer uma análise cuidadosa das estruturas de produtos, a identificação das famílias de produtos e a criação de componentes. Para reduzir o número de partes e minimizar o número de mercadorias que estão em andamento, é muito importante que você compreenda as interfaces do produto, e que planeje a reusabilidade.  

Há diversos princípios de modelagem de configuração de produto, como a modelagem baseada em regras, baseada em dimensão e baseada em restrição. Os estudos mostram que a metodologia baseada em restrição pode reduzir em 50% o número de linhas de código em modelos em comparação a outros princípios de modelagem. Então, essa metodologia pode reduzir o custo total de propriedade (TCO). Ao mover de um modelo baseado em regras com base no código X++ para um modelo baseado em restrição, você não requer mais uma licença do desenvolvedor para manter modelos de produto.

## <a name="product-configuration"></a>Configuração do produto
O período de industrialização resultou em grandes conquistas na geração de produtos de alta qualidade e sofisticados, a preços acessíveis. As economias de escala tornaram possível para a maioria das pessoas no mundo industrializado comprar carros, TVs, aparelhos eletrodomésticos e outros bens que muitos consideram uma parte necessária da vida quotidiana.  

Como vários produtos se tornaram mercadorias, aumentou a necessidade de diferenciá-los. A resposta imediata de fabricantes para este desafio foi criar variantes de cada produto, de forma que os clientes tenham mais alternativas. Essa estratégia resultou em desafios acumulados de previsão, e também em um aumento no custo de estoque e em produtos não vendidos que se tornam obsoletos.  

Ao adotar uma filosofia de configure para solicitar, os fabricantes têm a oportunidade de atender à demanda dos clientes por produtos exclusivos, reduzindo ou eliminando itens de estoque obsoletos. Quando uma filosofia de fabricação para estoque muda para uma filosofia configure para solicitar, um desafio imediato que surge é que a necessidade de prazos de entrega menores deve ser equilibrada em relação a níveis baixos de estoque.  

O segredo do sucesso aqui é analisar cuidadosamente o portfólio de produtos, e procurar padrões em características do produto e processos. A meta é identificar os componentes genéricos que podem ser fabricados pelo mesmo equipamento e usados em todas as variantes.  

O novo conjunto de recursos de configuração de Produto inclui uma interface do usuário (UI) que fornece uma visão geral visual da estrutura do modelo de configuração do produto, e também uma sintaxe declarativa de restrição que não precisa ser compilada. Assim, as empresas que desejam dar suporte a uma prática de configuração podem começar com mais facilidade. Como as seções a seguir explicam, um designer do produto não precisa mais do suporte de um desenvolvedor para criar um modelo de configuração do produto, testá-lo e liberá-lo para a organização de vendas.

## <a name="building-a-product-configuration-model"></a>Criar um modelo de configuração de produto
Há diversas abordagens que um usuário pode adotar para criar um modelo de configuração do produto. Uma opção é seguir um fluxo sequencial, primeiro criando todos os dados de referência, como produtos mestre, produtos distintos e recursos operacionais. Em seguida, incluí-los como componentes, linhas da lista de materiais (BOM), operações de roteiro e outros elementos do modelo de configuração do produto. Como alternativa, você pode selecionar uma abordagem mais iterativa, primeiro criando o modelo e, depois, adicionando dados de referência conforme a necessidade.

### <a name="components"></a>Componentes

Um modelo de configuração do produto consiste em um ou mais componentes que são associados através de relações de subcomponente. Os componentes são definidos uma vez, e podem ser usados várias vezes em um ou mais modelos de configuração do produto. Os componentes são os principais blocos de construção de um modelo de configuração do produto. Quase todas as informações sobre o modelo estão relacionadas a eles.

### <a name="attributes"></a>Atributos

Cada componente tem um ou mais atributos que identificam suas propriedades. Os atributos são o que os usuários escolherão durante o processo de configuração. Os atributos controlam relacionamentos inter e intracomponentes através da inclusão em restrições ou cálculos. Com as condições aplicadas às linhas da BOM, os atributos podem ser usados para determinar as partes físicas que constituem o produto configurado. Além disso, um atributo pode controlar a propriedade de uma linha BOM através de um mecanismo de mapeamento. Existe funcionalidade semelhante para as operações de roteiro, relativas às configurações de inclusão e propriedade.

>[!NOTE]
> Ao criar tipos de atributo, evite criar um grande número de valores para o tipo de atributo de domínio. Isso pode causar lentidões no configurador de produtos. 

### <a name="expression-constraints"></a>Restrições de expressão

O uso de um modelo de configuração do produto baseado em restrição implica que existem algumas limitações quando o usuário seleciona valores para os diversos atributos. Essas restrições podem ser implementadas como restrições da expressão usando a OML (Optimization Modeling Language). Como alternativa, uma restrição pode ser implementada sob a forma de uma restrição de tabela.

### <a name="table-constraints"></a>Restrições de tabela

As restrições de tabela podem ser definidas pelo usuário ou pelo sistema.  

Uma restrição de tabela definida pelo usuário é criada pelo usuário. O usuário seleciona uma combinação dos tipos de atributo para representar as colunas da tabela e insere valores dos domínios dos tipos de atributo selecionados para formar as linhas na restrição de tabela.  

Para determinar uma restrição de tabela definida pelo sistema, selecione a tabela a ser usada como referência e os campos dessa tabela para formar as colunas na restrição. As linhas de restrição da tabela são as linhas da tabela do Supply Chain Management que estão presentes no período de configuração.  

Uma restrição de tabela é incluída em um modelo de configuração do produto, referenciando a definição de restrição de tabela e mapeando os atributos relevantes no modelo para as colunas na restrição da tabela.

### <a name="calculations"></a>Cálculos

Os cálculos representam um mecanismo para executar operações aritméticas em um modelo de configuração. Por exemplo, um cálculo pode determinar o período de uma parte específica da matéria-prima ou o tempo de processamento para uma operação de polimento. Os cálculos são obrigatórios e definem o valor para um atributo de destino após a disponibilização de todos os valores de atributo incluídos na expressão de cálculo.

### <a name="subcomponents"></a>Subcomponentes

Os subcomponentes representam os nós na estrutura do modelo de configuração de produto. Para cada relacionamento de subcomponente, deve ser especificada uma referência a um produto mestre que tenha a tecnologia de configuração de variante definida como a configuração baseada em restrição.

### <a name="user-requirements"></a>Requisitos de usuário

Um requisito de usuário tem todos os componentes de um subcomponente. A única diferença é que um requisito de usuário não está associado a um produto mestre. O efeito prático dessa diferença é que qualquer linha de BOM ou operação de roteiro definida no contexto de uma requisição do usuário são recolhidas na estrutura ou roteiro de BOM do componente pai. Esse comportamento é parecido com o comportamento de um fantasma BOM.

### <a name="bom-lines"></a>Linhas de BOM

As linhas de BOM são incluídas para identificar a BOM de fabricação para cada componente. Uma linha de BOM deve fazer referência a um item, e todas as propriedades do item podem ser definidas como um valor fixo ou mapeadas para um atributo.

### <a name="route-operations"></a>Operações de roteiro

As operações de roteiro são incluídas para identificar o roteiro de fabricação. Uma operação de roteiro deve fazer referência a uma operação definida, e todas as propriedades da operação podem ser definidas como um valor fixo. Todas as propriedades, exceto as requisições de recursos, podem ser mapeadas para um atributo em vez de um valor.

## <a name="validating-and-testing-a-product-configuration-model"></a>Validação e teste de um modelo de configuração de produto
A validação de um modelo de configuração de produto pode ocorrer em vários níveis no modelo e podem abranger vários escopos. O nível mais baixo é de uma única restrição de expressão. Nesse caso, a validação costuma ser executada no designer do produto para verificar se a sintaxe da expressão está correta.  

Da mesma forma, uma condição de uma linha de BOM ou uma operação de roteiro pode ser validada separadamente.  

A validação também pode ser feita para uma definição de restrição de tabela definida pelo usuário. Nesse caso, o usuário pode verificar se os valores que são inseridos para cada campo estão no domínio dos tipos de atributos correspondentes.  

Finalmente, a validação pode ser feita para que um modelo de configuração do produto completo verifique se a sintaxe completa está correta, e que todas as convenções de nome e modelagem foram respeitadas.

### <a name="testing"></a>Testando

Testar um modelo é semelhante a executar uma sessão de configuração real. O usuário pode percorrer as páginas de configuração e verificar se a estrutura do modelo dá suporte ao processo de configuração. O usuário pode verificar se os valores de atributos estão corretos, e se as descrições de atributos orientam o usuário para selecionar os valores corretos. Finalmente, depois que uma sessão de teste é concluída, o sistema tenta criar a BOM e o roteiro que corresponde aos valores de atributo selecionados, e apresenta uma mensagem de erro se algo dá errado.

### <a name="the-configuration-page"></a>A página de configuração

Para navegar entre componentes, clique em **Avançar** ou em um componente na árvore de modelo de configuração do produto para se concentrar nele.

## <a name="finalizing-a-model-for-configuration"></a>Finalização de um modelo para configuração
Quando um modelo de configuração do produto está pronto para ser usado em cenários configure para solicitar, uma versão deve ser criada. No entanto, há várias opções que podem melhorar a experiência de modelagem.

### <a name="user-interface"></a>Interface do usuário

A interface de usuário de configuração pode ser alterada apresentando grupos de atributos em um ou mais subcomponentes. Um agrupamento assim pode destacar os relacionamentos entre atributos específicos e ajudar o usuário da configuração a identificar a área do produto que está em foco no momento.

### <a name="templates"></a>Modelos

Um ou mais modelos de configuração podem ser criados para acelerar o processo de configuração. Como alternativa, os modelos podem ser criados para promover combinações de atributos específicos, como quando uma campanha de venda foca um conjunto específico de características do produto.

### <a name="translations"></a>Traduções

Se o produto for vendido em diferentes países/regiões, as traduções poderão ser criadas para todo o texto que aparece na interface do usuário da configuração. Esse texto inclui não apenas os campos de nome e descrição, mas também valores de atributo para texto.

### <a name="versions"></a>Versões

A última e mais importante etapa no processo de finalização é criar uma versão do modelo de configuração do produto. A versão representa o relacionamento entre o produto mestre, que pode ser selecionado para configuração em uma ordem ou em uma linha da cotação, e o modelo de configuração do produto. Uma versão deve ser aprovada e ativada antes de ser usada em uma sessão de configuração.

## <a name="extending-a-product-configuration-model-through-the-api"></a>Extensão de um modelo de configuração do produto através da API
Uma API (interface de programação de aplicativos) dedicada foi implementada, de modo que parceiros e outras pessoas com uma licença de desenvolvedor possam estender os recursos de um modelo de configuração do produto. O objetivo principal foi estabelecer um mecanismo que permita a parceiros e clientes que usam o configurador de produtos existente migrar o código inserido em modelos do Configurador de Produtos para a API. Dessa forma, eles podem migrar os modelos do Configurador de Produtos para uma configuração de produto. No entanto, os novos clientes e parceiros também podem aproveitar o uso da API para estender modelos de configuração de novos produtos.

### <a name="pcadaptor-class"></a>Classe PCAdaptor

A API foi implementada usando um conjunto de classes **PCAdaptor** que expõem a estrutura de dados dos modelos de configuração de produtos. Uma instância da classe **PCAdaptor** deve ser criada para cada modelo que será estendido. Após a conclusão de uma sessão de configuração, o sistema verifica se há uma instância dessa classe e executa-a quando localizada.  

O diagrama de fluxo a seguir esboça o processo.  

[![Diagrama de fluxo](./media/product_configuration_2.png)](./media/product_configuration_2.png)  

Diagrama de fluxo da API de configuração do produto

## <a name="product-configuration"></a>Configuração do produto
A configuração de produto pode ser executada dos seguintes locais:

-   Linha da ordem de venda
-   Linha de cotação de venda
-   Linha da ordem de compra
-   Linha de ordem de produção
-   Linha de requisição do item (projeto)

A finalidade da configuração é criar uma variante diferente do produto que atenda ao requisito do cliente. Uma ID exclusiva de configuração é criada para cada configuração nova. Essa ID habilita o rastreamento no estoque.

### <a name="multiple-sites-and-intercompany"></a>Vários sites e intercompanhia

Se a configuração for feita em um site, ou mesmo em uma empresa, isso será diferente do site ou da empresa onde ocorre a produção. A BOM e o roteiro serão criados e colocado no site do fornecedor na empresa fornecedora. A variante de produto será liberada em todas as empresas que participam da cadeia de suprimentos.



