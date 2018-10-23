---
title: "Dimensões financeiras"
description: "Este tópico descreve os vários tipos de dimensões financeiras e como elas são configuradas."
author: aprilolson
manager: AnnBe
ms.date: 08/24/2018
ms.topic: article
ems.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionDetails, DimensionValueDetails, SysTranslationDetail
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 25871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.1
ms.translationtype: HT
ms.sourcegitcommit: d6b7b1219974cb5de1a625d87c3bce2a4439470b
ms.openlocfilehash: 9973d03de031ad2fa5647bb167c12b9231633a22
ms.contentlocale: pt-br
ms.lasthandoff: 10/01/2018

---

# <a name="financial-dimensions"></a>Dimensões financeiras

[!include [banner](../includes/banner.md)]

Este tópico explica os vários tipos de dimensões financeiras e como elas são configuradas.

Use a página **Dimensões financeiras** para criar as dimensões financeiras que você pode usar como segmentos de conta para os gráficos de contas. Há dois tipos de dimensões financeiras: as dimensões personalizadas e as dimensões apoiadas por entidade. As dimensões personalizadas são compartilhadas pelas entidades legais, e os valores são inseridos e mantidos por usuários. Para as dimensões apoiadas por entidade, os valores são definidos em outro lugar no sistema, como em entidades das Lojas ou de Clientes. Algumas dimensões apoiadas por entidade são compartilhadas entre entidades legais, enquanto outras dimensões apoiadas por entidade são específicas da empresa.

Depois de ter criado as dimensões financeiras, use a página **Valores de dimensão financeira** para atribuir propriedades adicionais para cada dimensão financeira.

Você pode usar dimensões financeiras para representar entidades legais. Não é necessário criar as entidades legais no Microsoft Dynamics 365 for Finance and Operations. Entretanto, as dimensões financeiras não são criadas para atender aos requisitos comerciais ou operacionais de entidades legais. A funcionalidade de contabilidade interunidade no Finance and Operations foi criada para tratar somente as entradas de contabilidade criadas por cada transação.

Antes de configurar dimensões financeiras como entidades legais, avalie seus processos comerciais nas seguintes áreas para determinar se essa configuração funcionará para a sua organização:

- Estoque
- Vendas e compras entre dimensões financeiras e entidades legais
- Cálculo do imposto sobre vendas e relatórios
- Relatório operacional

Estas são algumas das limitações:

- Você pode usar a funcionalidade de imposto sobre vendas apenas com entidades legais, e não com dimensões financeiras.
- Alguns relatórios não incluem dimensões financeiras. Assim, para gerar relatório por dimensão financeira, você poderá ter que alterar os relatórios.

## <a name="custom-dimensions"></a>Dimensões personalizadas

Para criar uma dimensão financeira definida pelo usuário, no campo **Usar valores de**, selecione **&lt;&nbsp;Dimensão personalizada&nbsp;&gt;**.

Você também pode especificar uma máscara de conta para limitar o valor e o tipo de informação que pode ser inserido para valores de dimensão. Você pode inserir os caracteres que permanecem iguais para cada valor de dimensão, como letras ou um hífen (-). Você também pode inserir sinais numéricos (\#) e o E comercial (&) como espaços reservados para caracteres que mudarão sempre que um valor de dimensão for criado. Use um sinal numérico (\#) como um espaço reservado para um número e um e comercial (&) como um espaço reservado para uma letra. O campo da máscara de formato está disponível somente quando você seleciona **&lt;&nbsp;Dimensão personalizada&nbsp;&gt;** no campo **Usar valores de** 

**Exemplo**

Para limitar o valor de dimensão às letras "CC" e a três números, insira **CC-\#\#\#** como a máscara de formato.

## <a name="entity-backed-dimensions"></a>Dimensões apoiadas por entidade

Para criar uma dimensão financeira apoiada por entidade, no campo **Usar valores de**, selecione uma entidade definida pelo sistema na qual a dimensão financeira será baseada. Valores de dimensão financeira são então criados a partir dessa entidade. Por exemplo, para criar valores de dimensão para projetos, selecione **Projetos**. Um valor de dimensão é então criado para cada nome de projeto. A página **Valores de dimensão financeira** mostra os valores da entidade. Se esses valores são específicos da empresa, a página também mostra a empresa.

## <a name="activating-dimensions"></a>Ativação da dimensão

Quando você ativa uma dimensão financeira, a tabela é atualizada de forma a incluir o nome da dimensão financeira. As dimensões excluídas são removidas. Você pode inserir valores de dimensão antes de ativar uma dimensão financeira. Entretanto, uma dimensão financeira não pode ser consumida em lugar algum até ser ativada. Por exemplo, você não pode adicionar uma dimensão financeira a uma estrutura de conta até a dimensão financeira ser ativada. Ao selecionar **Ativar**, todas as dimensões são atualizadas e mostrar status é alterado.

## <a name="translations"></a>Traduções

Na página **Tradução de texto**, você pode inserir textos em vários idiomas para a dimensão financeira selecionada. Na página **Tradução da conta principal**, você pode inserir textos em vários idiomas para a conta principal. 

## <a name="legal-entity-overrides"></a>Substituições de entidade legal

Nem todas as dimensões são válidas para todas as entidades legais. Além disso, algumas dimensões podem ser relevantes somente para um período específico Nesses casos, você pode usar a seção **Substituições da entidade legal** para especificar para quais empresas a dimensão deve ser suspensa, o proprietário e há quanto tempo a dimensão está ativa.

## <a name="deleting-financial-dimensions"></a>Excluir dimensões financeiras

Para ajudar a manter a integridade referencial dos dados, as dimensões financeiras raramente poderão ser excluídas. Se você tentar excluir uma dimensão financeira, os critérios a seguir serão avaliados:

- A dimensão financeira foi usada em alguma transação lançada ou não, ou em algum tipo de combinação de valor de dimensão?
- A dimensão financeira é usada em alguma estrutura de conta ativa, estrutura de regra avançada, ou algum conjunto de dimensão financeira?
- A dimensão financeira é parte de um formato padrão de integração da dimensão financeira?
- A dimensão financeira foi configurada como dimensão padrão?

Se algum dos critérios foi atendido, você não poderá excluir a dimensão financeira.

## <a name="default-dimension-values"></a>Valores de dimensão padrão

Você pode usar valores de registros mestres, como o cliente e fornecedor, como os valores padrão em novas dimensões. Quando novas dimensões são criadas, a ID de registro mestre será inserida nos valores de dimensões para os registros mestre. Por exemplo, quando você criar um novo cliente, o ID do cliente será inserido na dimensão do cliente. Quando você cria ordens de venda, faturas, ou outros documentos que exigem uma ID de cliente, as regras padrão existentes são usadas, e a ID de cliente é adicionada ao documento.

Este recurso é controlado por uma configuração da dimensão. Esta configuração é chamada **Copiar valores para essa dimensão em cada novo DimensionName criado**, no qual **DimensionName** é o nome da dimensão. Por padrão, o recurso será desativado. Entretanto, ele poderá ser ativado a qualquer momento.

Se já existem registros para a dimensão, os registros mestre serão atualizados quando você ativar o recurso. Porém, os documentos existentes e as transações não serão atualizados.

## <a name="derived-dimensions"></a>Dimensões derivadas

Você pode configurar uma dimensão, de forma que as informações de outras dimensões sejam inseridas automaticamente quando você inserir a dimensão em um documento. Por exemplo, se você inserir o centro de custos 10, um valor **20** poderá ser inserido automaticamente na dimensão de departamento.

Você pode configurar valores derivados na página de dimensões.

1. Selecione uma dimensão e depois selecione **Dimensões derivadas**.

    A página **Dimensões derivadas** inclui uma grade. O segmento da dimensão selecionada é a primeira coluna nessa grade.

2. Adicione os segmentos que devem ser derivados. Cada segmento aparecerá como uma coluna.

Insira combinações de dimensão que devem ser derivadas de dimensão na primeira coluna. Por exemplo, para usar o centro de custo como a dimensão da qual o departamento e a localização serão derivados, entre no centro de custos 10, departamento 20, e local 30. Em seguida, ao inserir o centro de custos 10 em um registro mestre ou em uma página da transação, o departamento 20 e o local 30 são inseridos por padrão.

O processo de dimensão derivada não substitui valores existentes para dimensões derivadas. Por exemplo, se você inserir o centro de custos 10, e nenhuma outra dimensão for inserida, o departamento 20 e o local 30 serão inseridos por padrão. Porém, se você alterar o centro de custo, os valores que foram já foram estabelecidos não serão alterados. Portanto, você pode estabelecer dimensões padrão nos registros mestre, e essas dimensões não serão alteradas por dimensões derivadas.

### <a name="derived-dimensions-and-entities"></a>Entidades e dimensões derivadas

Você pode configurar os segmentos e valores das dimensões derivadas usando as entidades.

- A entidade Dimensões derivadas configura as dimensões de controle e os segmentos que são usados para essas dimensões.
- A entidade de DerivedDimensionValue permite importar valores que devem ser derivados para cada dimensão de controle.

Quando você usa uma entidade para importar dados, se a entidade importar dimensões, regras de dimensão derivada serão aplicadas durante importação, a menos que a entidade substitua especificamente essas dimensões.

Para obter mais informações, consulte os seguintes tópicos:

- [Definir dimensões financeiras](tasks/define-financial-dimensions.md)
- [Manter modelos padrão de dimensão financeira](tasks/maintain-financial-dimension-default-templates.md)

