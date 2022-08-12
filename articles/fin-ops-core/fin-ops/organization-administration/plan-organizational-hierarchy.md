---
title: Planejar sua hierarquia organizacional
description: Antes de configurar organizações e hierarquias da organização, entenda como modelar melhor sua empresa.
author: sericks007
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: OMHierarchyManager, OMLegalEntity, OMOperatingUnit
audience: Application User
ms.reviewer: sericks
ms.custom: 17404
ms.assetid: babde0c6-bb5d-45ae-95ca-2af75a0ea292
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5bb0b306cca715cad64d62fff843987a8e98eb99
ms.sourcegitcommit: 3289478a05040910f356baf1995ce0523d347368
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2022
ms.locfileid: "9108754"
---
# <a name="plan-your-organizational-hierarchy"></a>Planejar sua hierarquia organizacional

[!include [banner](../includes/banner.md)]

Antes de configurar organizações e hierarquias organizacionais, certifique-se de planejar a forma como sua empresa será modelada. O modelo da organização tem efeito significativo na implementação e nos processos comerciais.

As hierarquias organizacionais representam os relacionamentos entre as organizações que compõem uma empresa. Portanto, a consideração mais importante ao modelar organizações é a estrutura de sua empresa. Recomendamos que você defina as estruturas da organização com base nos comentários de executivos e gerentes seniores das áreas funcionais, como finanças e contabilidade, recursos humanos, operações, compras, vendas e marketing.

Quando estiver planejando hierarquias, também é importante considerar a relação entre a hierarquia organizacional e as dimensões financeiras. É possível configurar várias hierarquias organizacionais para representar diferentes visões do negócio. Usando dimensões financeiras, é possível criar relatórios com base nas exibições. Trabalhe com seu parceiro para criar hierarquias que tratam as necessidades da organização e dos relatórios de impostos.

> [!NOTE]
> Embora seja possível usar dimensões financeiras para representar entidades legais sem criar entidades legais, as dimensões financeiras não são criadas para resolver as necessidades comerciais ou operacionais da entidade legal. A funcionalidade de contabilização interunidade foi criada para tratar somente as entradas contábeis que são criadas para cada transação.

> [!IMPORTANT]
> Não é necessário decidir como modelar as organizações com base apenas nas informações deste artigo. Esta documentação é um guia. Você pode trabalhar com seu parceiro para orientações adicionais. Seu parceiro obteve experiência em várias indústrias e em toda a base de clientes.

## <a name="decide-whether-to-model-internal-organizations-as-legal-entities-or-operating-units"></a>Decida se deseja modelar as organizações internas como entidades legais ou unidades operacionais

É necessário ter pelo menos uma entidade legal para representar a sua empresa. Uma entidade legal podem participar de contratos legais e são obrigadas a preparar demonstrativos financeiros que registram seu desempenho.

As entidades legais podem ser usadas para negócios transacionais ou consolidação. Isso significa que uma entidade legal no aplicativo de finanças e operações não necessariamente representa uma entidade real na sua empresa. Por exemplo, uma empresa que participa das transações pode possuir entidades legais subsidiárias. Nesse cenário, uma entidade legal é necessária para transações, e uma entidade legal virtual é necessária para consolidar os resultados e os saldos da entidade legal subsidiária.

As organizações internas da empresa, como os escritórios regionais, podem ser representadas como entidades legais adicionais ou como unidades operacionais da entidade legal principal. Uma unidade operacional não precisa ser uma organização legalmente definida. As unidades operacionais são usadas para controlar os recursos econômicos e os processos operacionais da empresa. Por exemplo, os departamentos e os centros de custo são unidades operacionais.

Algumas funcionalidades funcionam de forma diferente dependendo se a organização é uma entidade legal ou uma unidade operacional. Considere cuidadosamente a funcionalidade descrita abaixo ao tomar sua decisão.

### <a name="master-data"></a>Dados mestres

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se a organização for modelada como uma entidade legal

Alguns dados mestres, como clientes, condições de pagamento, autoridades fiscais, e a ordem de estoque específica do site, devem ser configurados para cada entidade legal. Alguns dados mestres, como usuários, produtos, e a maioria dos dados dos recursos humanos, são compartilhados entre todas as entidades legais.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se a organização for modelada como uma unidade operacional

Os dados mestres são compartilhados entre as unidades operacionais.

### <a name="module-parameters"></a>Parâmetros do módulo

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se a organização for modelada como uma entidade legal

Os parâmetros dos módulos, como parâmetros de contas a receber, parâmetros de contas a pagar, e de gerenciamento de caixa e de bancos, devem ser definidos por entidade legal. Como a configuração do módulo para as entidades legais é separada, cada subsidiária pode estar em conformidade com as necessidades legais e as práticas comerciais. Por exemplo, uma entidade legal de serviços profissionais e uma entidade legal de fabricação podem ter diferentes parâmetros de módulo mesmo que reportem para a mesma empresa primária.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se a organização for modelada como uma unidade operacional

Os parâmetros de módulo são compartilhados entre as unidades operacionais.

### <a name="data-security"></a>Segurança de dados

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se a organização for modelada como uma entidade legal

A maioria dos dados são protegidos automaticamente pela identificação da empresa Uma identificação de empresa é um identificador exclusivo para os dados associados a uma entidade legal. Uma empresa pode ser associada somente a uma entidade legal, e uma entidade legal pode ser associada somente a uma empresa. Os usuários podem acessar somente os dados das empresas que têm acesso. Não é necessário personalizar para proteger os dados através da identificação da empresa

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se a organização for modelada como uma unidade operacional

Os dados podem ser protegidos de acordo com a unidade operacional criando diretivas de segurança de dados personalizadas. As diretivas de segurança de dados são usadas para limitar o acesso aos dados. Por exemplo, suponha que um usuário esteja autorizado a criar ordens de compra somente em uma unidade operacional específica. As diretivas de segurança dos dados podem ser criadas para evitar que o usuário acesse os dados da ordem de compra a partir de qualquer outra unidade operacional. O volume de transações e o número de diretivas de segurança podem afetar o desempenho. Ao criar diretivas de segurança, leve sempre o desempenho em consideração.

### <a name="ledgers"></a>Razões

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se a organização for modelada como uma entidade legal

Cada entidade legal requer um razão que fornece um plano de contas, moeda contábil, moeda de relatório e o calendário fiscal. Um balanço pode ser criado apenas para uma entidade legal. As contas principais, dimensões, estruturas de conta, plano de contas e regras de conta podem ser usados por mais de uma entidade legal.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se a organização for modelada como uma unidade operacional

Uma unidade operacional não pode ter suas próprias informações do razão. Se as organizações internas não exigirem razões exclusivos, é possível modelá-las como unidades operacionais. As informações do razão serão configuradas para a entidade legal primária na hierarquia. As declarações de imposto podem ser criadas para as unidades operacionais dentro de uma entidade legal ou para a entidade legal primária.

### <a name="fiscal-calendars"></a>Calendários fiscais

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se a organização for modelada como uma entidade legal

Cada entidade legal possui seu próprio calendário fiscal. Se as organizações internas usarem diferentes anos e calendários fiscais, será necessário modelar as organizações como entidades legais.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se a organização for modelada como uma unidade operacional

As unidades operacionais devem compartilhar um calendário fiscal. Se as organizações internas puderem usar os mesmos anos e calendários fiscais, é possível modelar as organizações como unidades operacionais.

### <a name="consolidation"></a>Consolidação

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se a organização for modelada como uma entidade legal

É necessário consolidar os resultados financeiros dos escritório regionais em uma única empresa consolidada, para preparar os demonstrativos financeiros.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se a organização for modelada como uma unidade operacional

A consolidação não é necessária, pois os dados já estão sendo compartilhados entre as unidades operacionais.

### <a name="centralized-payments"></a>Pagamentos centralizados

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se a organização for modelada como uma entidade legal

Os pagamentos centralizados devem ser configurados de modo que as faturas de todas as entidades legais secundárias possam ser pagas para ou a partir de uma entidade legal primária.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se a organização for modelada como uma unidade operacional

Os pagamentos centralizados não são necessários, pois todas as faturas são registradas em uma única entidade legal.

### <a name="intercompany-transactions"></a>Transações intercompanhia

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se a organização for modelada como uma entidade legal

As ordens de venda intercompanhia, ordens de compra, pagamentos, ou recebimentos podem ser aplicados uns aos outros. Não é necessário usar comprovantes de diário. É possível exibir transações intercompanhia no nível do sub-razão (contas a pagar, contas a receber). Os exemplos a seguir ilustram como as transações intercompanhia são tratadas.

##### <a name="example-1-headquarters-provides-services-to-regional-offices-and-must-charge-the-costs-of-those-services-to-the-regional-offices"></a>Exemplo 1: A matriz presta serviços aos escritórios regionais e deve cobrar os custos dos serviços dos escritórios regionais.

Se o escritório regional for modelado como uma entidade legal, você terá as seguintes opções:

- A matriz cria uma entrada de diário para cobrar a despesa do escritório regional. As transações não podem estar vencida.
- A matriz envia uma ordem de compra dos serviços ao escritório regional. Uma ordem de venda é criada automaticamente na entidade legal para o escritório regional, com as transações intercompanhia do sub-razão.

##### <a name="example-2-headquarters-procures-and-pays-for-service-that-is-delivered-to-a-regional-office"></a>Exemplo 2: A matriz adquire e paga pelo serviço que é prestado a um escritório regional

Se o escritório regional for modelado como uma entidade legal, você terá as seguintes opções:

- A fatura e o pagamento seguem os requisitos de regulamentação da matriz. A matriz pode criar uma entrada de diário para cobrar a despesa do escritório regional. As transações não podem estar vencida.
- A fatura e o pagamento seguem os requisitos de regulamentação da matriz. A matriz pode criar uma transação intercompanhia do sub-razão.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se a organização for modelada como uma unidade operacional

As transações intercompanhia entre as unidades operacionais são suportadas somente pelos comprovantes de diário. Uma unidade operacional não pode enviar ou receber uma ordem de compra, ordem de venda, ou uma fatura de outra unidade operacional na mesma entidade legal. Não é possível exibir transações intercompanhia no nível do sub-razão (contas a pagar, contas a receber). Os exemplos a seguir ilustram como as transações intercompanhia são tratadas.

##### <a name="example-1-headquarters-provides-services-to-regional-offices-and-must-charge-the-costs-of-those-services-to-the-regional-offices"></a>Exemplo 1: A matriz presta serviços aos escritórios regionais e deve cobrar os custos dos serviços dos escritórios regionais.

Se o escritório regional for modelado como uma unidade operacional, a matriz insere uma transação de despesa e a codifica para o escritório regional.

##### <a name="example-2-headquarters-procures-and-pays-for-service-that-is-delivered-to-a-regional-office"></a>Exemplo 2: A matriz adquire e paga pelo serviço que é prestado a um escritório regional

Se o escritório regional for modelado como uma unidade operacional, a fatura e o pagamento seguirão os requisitos de regulamentação da matriz. A fatura pode ser codificada para o escritório regional. No demonstrativo de renda, use uma dimensão financeira de balanceamento para relatar os custos para o escritório regional.

### <a name="local-tax-requirements"></a>Requisitos locais de imposto

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se a organização for modelada como uma entidade legal

Uma entidade legal está sujeita à legislação tributária da autoridade fiscal no país/região onde está registrada. Por exemplo, uma entidade legal que está registrada na Dinamarca está sujeita à legislação tributária e as regulamentações dinamarquesas. Uma entidade legal pode pertencer somente a um país/região. O país/região selecionado para o endereço principal da entidade legal controla os recursos específicos do país/região que estão disponíveis para essa entidade legal. Por exemplo, se o endereço principal da entidade legal estiver na Dinamarca, os recursos que estão relacionados à legislação tributária e às regulamentações dinamarquesas ficarão disponíveis. Portanto, se as organizações estiverem em diferentes países/regiões e precisarem de opções diferentes de imposto local, será necessário configurar as organizações como entidades legais independentes.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se a organização for modelada como uma unidade operacional

As unidades operacionais usam o contexto de país da entidade legal primária. As unidades operacionais na mesma entidade legal não podem ter requisitos específicos de país/região diferentes. Se as organizações estiverem no mesmo país/região e usarem as mesmas opções de imposto, será possível configurá-las como unidades operacionais.

### <a name="statutory-reporting-for-a-countryregion"></a>Relatório de impostos para um país/região

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se a organização for modelada como uma entidade legal

Para os países/regiões com suporte, a maioria dos relatórios de impostos podem ser criados. 

> [!NOTE]
> Um nível de lançamento na contabilidade permite que você faça entradas de ajuste em uma empresa pai que usa um padrão de contabilidade diferente da empresa filha. Por exemplo, para uma empresa que usa as práticas contábeis geralmente aceitas no Reino Unido (GAAP BRITÂNICO), é possível criar entradas de ajuste no nível de lançamento. Essas entradas podem ser consolidadas em uma empresa primária que usa os princípios contábeis geralmente aceitos (GAAP) nos Estados Unidos. As entradas de ajuste não afetam os relatórios de GAAP BRITÂNICOS.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se a organização for modelada como uma unidade operacional

Os relatórios de impostos devem ser criados usando outro aplicativo. É necessário verificar se os dados foram capturados nos aplicativos de finanças e operações para dar suporte aos requisitos de cada unidade operacional, onde eles diferem dos requisitos da matriz.

### <a name="currency"></a>Moeda

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se a organização for modelada como uma entidade legal

Se as organizações precisarem usar moedas funcionais diferentes, será necessário modelar as organizações como entidades legais. As moedas funcionais são configuradas por entidade legal. No entanto, é possível inserir transações em várias moedas.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se a organização for modelada como uma unidade operacional

Se as organizações puderem usar uma única moeda funcional, será possível modelar as organizações como unidades operacionais. As unidades operacionais devem compartilhar uma moeda funcional. No entanto, é possível inserir transações e criar relatórios em várias moedas.

### <a name="year-end-closing"></a>Fechamento do exercício

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se a organização for modelada como uma entidade legal

Se as leis e as práticas de contabilidade forem diferentes entre os países/regiões nos quais as organizações estão localizadas, serão necessários diferentes procedimentos de fechamento de exercício de acordo com cada organização. Isso significa que você deverá modelar as organizações como entidades legais. Cada entidade legal possui seus próprios procedimentos de encerramento de exercício.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se a organização for modelada como uma unidade operacional

Se as leis e as práticas de contabilidade forem as mesmas entre os países/regiões nos quais as organizações estão localizadas, será possível usar um único conjunto de procedimentos de encerramento de exercício. Isso significa que será possível modelar as organizações como unidades operacionais. Todas as unidades operacionais devem usar o mesmo procedimento de fechamento do exercício.

### <a name="number-sequences"></a>Sequências numéricas

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se a organização for modelada como uma entidade legal

As sequências numéricas para algumas referências podem ser configuradas por entidade legal. Algumas sequências numéricas podem ser compartilhadas.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se a organização for modelada como uma unidade operacional

As sequências numéricas para algumas referências podem ser configuradas por unidade operacional. Algumas sequências numéricas podem ser compartilhadas.

### <a name="products"></a>Produtos

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se a organização for modelada como uma entidade legal

As definições de produto são compartilhadas e devem ser disponibilizadas para entidades legais individuais antes que possam ser incluídas nas transações. Cada entidade legal possui seu próprio conjunto de produtos liberados que pode ser incluído nos documentos da transação. Se as organizações internas precisarem usar conjuntos de produtos diferentes, será necessário modelar as organizações como entidades legais.

> [!NOTE]
> Mesmo que as definições de produto sejam compartilhadas, em cada entidade legal que um produto tiver sido liberado, será possível especificar parâmetros de venda, compra e de estoque para o item em cada site de estoque.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se a organização for modelada como uma unidade operacional

Todas as unidades operacionais compartilham o mesmo conjunto de produtos. Se as organizações internas puderem compartilhar o mesmo conjunto de produtos, será possível modelar as organizações como unidades operacionais.

### <a name="inquiry-and-reporting"></a>Consulta e relatórios

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se a organização for modelada como uma entidade legal

É necessário alterar manualmente as empresas para inserir transações e executar consultas em várias entidades legais. Devido aos limites de segurança de dados, a consulta consolidada e a geração de relatórios podem ser demoradas e utilizar muitos recursos.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se a organização for modelada como uma unidade operacional

Não é necessário alterar as empresas para acessar os dados de várias unidades operacionais. A consulta consolidada, a geração de relatórios e a consulta regional individual mais são fáceis e mais rápidas.

## <a name="best-practices-for-modeling-organizations-and-hierarchies"></a>Práticas recomendadas para modelar organizações e hierarquias

Considere estas práticas recomendadas quando implementar uma hierarquia organizacional:

- Crie um departamento para modelar a interseção entre uma entidade legal e uma unidade de negócios. Você poderá então acumular dados de um departamento para uma entidade legal para relatório estatutário, e de um departamento para uma unidade de negócios para relatório interno. Os departamentos podem servir como centros de lucro. Se você usar departamentos, não será necessário usar entidades legais e unidades de negócios como dimensões na estrutura de conta. Você pode usar apenas departamentos como uma dimensão. No entanto, você deve usar centros de custos e departamentos como dimensões na estrutura da conta se os centros de custo forem usados somente como acumuladores de custo, e os departamentos forem usados para reconhecimento de receita.
- Modele várias hierarquias para unidades operacionais se você tiver requisitos complexos para relatar lucros e perdas.
- Em uma única entidade legal, não modele várias hierarquias para a mesma finalidade de hierarquia.
- Não crie uma hierarquia para cada finalidade. Geralmente, você pode usar uma hierarquia para várias finalidades. Por exemplo, uma hierarquia de unidades operacionais pode ser atribuída a todas as finalidades relacionadas a políticas.
- Crie hierarquias equilibradas. Em uma hierarquia, todos os nós que estão à mesma distância do nó raiz são definidos como um nível. Em uma hierarquia equilibrada, somente um tipo de unidade operacional pode ocorrer em cada nível, e a distância do nó raiz a cada nível é consistente. Se houver níveis intermediários entre um departamento e uma entidade legal ou uma unidade de negócios, as organizações do espaço reservado podem precisar criar uma hierarquia equilibrada.
- Não modele uma hierarquia diferente de unidades operacionais se a estrutura das entidades legais também for sua estrutura organizacional. Uma hierarquia misturada da entidades legais e unidades operacionais pode servir às duas finalidades.
- Antes que você modele grandes cenários de reestruturação, use as datas efetivas da hierarquia para realizar uma análise de impacto e um teste de validação.
- Use o modo de rascunho para alterar uma hierarquia antes de publicar uma nova versão em um ambiente de produção.
- Limite o número de pessoas que têm permissões para adicionar ou remover organizações de uma hierarquia em um ambiente de produção. Um número menor reduz a chance de ocorrência de erros e a necessidade de correções.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

