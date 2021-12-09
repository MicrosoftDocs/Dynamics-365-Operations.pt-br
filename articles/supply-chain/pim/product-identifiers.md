---
title: Identificadores do produto
description: Este tópico fornece informações sobre os vários tipos de identificadores de produtos e explica como adicioná-los aos dados de produtos.
author: t-benebo
ms.date: 03/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductEntityIdentifierCode, EcoResProductListPage, EcoResProductDetailsExtended, EcoResProductVariantsPerCompany
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2017-12-31
ms.openlocfilehash: 1a311b4a304984044a1c3bd3924c129821afbbb9
ms.sourcegitcommit: f11ad8d7ee8a4d2ee1a1bb601622b50e14955c4a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2021
ms.locfileid: "7825345"
---
# <a name="product-identifiers"></a>Identificadores do produto

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

[!include [banner](../includes/banner.md)]

Este tópico fornece informações sobre os vários tipos de identificadores de produtos e explica como adicioná-los aos dados de produtos.

Ao trabalhar com produtos no chão de fábrica ou em um depósito no Microsoft Dynamics ERP ou no Microsoft Dynamics CRM, você deve ter uma boa estratégia para identificar esses produtos e grades de produtos.

## <a name="unique-product-numberproduct-id"></a>Número do produto/ID do produto exclusivos

No Dynamics 365 Supply Chain Management, o principal identificador de um produto é o número do produto (isto é, a ID exclusiva do produto). Esse número pode ser gerado automaticamente por uma sequência numérica ou associado manualmente a um produto. No caso das grades de produtos, os números podem ser definidos por meio do modelo de nomenclatura de produtos.

Em muitos casos, o número do produto não é criado originalmente no Dynamics 365 Supply Chain Management. Em vez disso, é associado a um produto em um sistema de gerenciamento do ciclo de vida do produto (PLM) ou em um sistema de gerenciamento de dados do produto (PDM). Nesse caso, você usa entidades de dados para importar os produtos e as grades de produtos. O Supply Chain Management depois usa os números em todas as operações.

Ao implementar o Supply Chain Management, você deve dar atenção especial à sua estratégia de números de produto. Um bom sistema de numeração melhora os fluxos de logística e ajuda a evitar erros. Uma boa identificação do produto geralmente deve ter 20 caracteres ou menos, mas geralmente é recomendável usar menos de 10 caracteres e incluir, no máximo, 5 caracteres de classificação. Você também pode usar nomes de pesquisa para habilitar pesquisas rápidas. Um nome de pesquisa é um nome extra que representa as classificações de um produto.

Ao usar o Microsoft Dataverse, o número do produto no Supply Chain Management também será o número do produto no Microsoft Dataverse. As grades de produtos são sincronizadas com o Dataverse como produtos distintos.

## <a name="item-number-and-product-dimensions"></a>Número do item e dimensões do produto

O número do item é o identificador do produto usado por uma entidade legal específica. O ideal é que o número do item seja idêntico ao número do produto. Se a nomenclatura difere de acordo com a entidade legal, torna-se difícil rastrear um produto por toda a cadeia de fornecimento, e os onerosos processos de reetiquetação e de referência são introduzidos. Para manter a compatibilidade com versões anteriores (isto é, com o Microsoft Dynamics AX 2009 e anteriores), preservamos esse modelo. No entanto, é recomendável eliminar identificadores específicos a entidades legais sempre que possível e, em vez deles, usar o número de produto exclusivo como o identificador principal.

Além disso, uma grade de produto não pode ser exclusivamente identificada por um número de item. Ela sempre requer a combinação de um número de item e de todas as dimensões do produto definidas no produto mestre. Essa exigência pode se tornar complicada e retardar os processos de identificação. Por esse motivo também, é recomendável usar o número de produto exclusivo em vez do número do item sempre que possível.

Muitas páginas ainda têm o número do item e as dimensões do produto como os identificadores principais. No entanto, os números do produto podem ser usados para pesquisas. Em **Vendas e marketing** &gt; **Configuração** &gt; **Pesquisar** &gt; **Parâmetros de pesquisa**, você pode alterar a busca por pesquisa para que ela use números de produto em vez de números de item como estratégia de pesquisa principal. Se você definir a opção **Habilitar pesquisa para pesquisa de produtos** como **Sim**, a consulta mostrará não apenas os produtos mestres, mas também as grades de produtos. Para obter mais informações, consulte [Procurar produtos e grades de produtos durante uma entrada de ordem](search-products-product-variants.md).

Além disso, você poderá pesquisar e filtrar pelo número do produto, pelo nome e a descrição do produto e pelas IDs de dimensão do produto da grade de produto. Ao selecionar uma grade, o número do item relacionado e todas as IDs de dimensão do produto serão selecionados. Portanto, você poderá encontrar e selecionar a grade correta mais facilmente. Essa configuração é altamente recomendável se você usar as grades de produtos e o número de produto exclusivo como os identificadores principais de produtos. A única exceção talvez seja a indústria da moda, na qual os processos de negócios normalmente exigem a seleção do mestre antes de selecionar uma grade. Você deve avaliar essa opção com cuidado antes de implementar o sistema de numeração.

> [!NOTE]
> O número do item de um produto não pode ser alterado depois que uma ou mais transações existem para esse produto.

## <a name="product-name-and-description"></a>Nome e descrição do produto

O nome e a descrição do produto são os identificadores legíveis para humanos e podem ser mantidos em vários idiomas. Por padrão, o cliente do Supply Chain Management mostra todas as informações do produto no idioma padrão da empresa, não no idioma do usuário. No entanto, as descrições e os nomes do produto traduzidos são usados na comunicação com clientes e fornecedores. As traduções se baseiam no código de idioma das contas de cliente e de fornecedor.

No caso das grades de produtos, o nome do produto pode ser gerado por meio de um modelo de nomenclatura de produtos. Como não é exigido que os nomes de produtos sejam exclusivos, você poderá encontrar vários produtos com o mesmo nome.

## <a name="product-and-item-search-names"></a>Nomes de pesquisa do produto e do item

O Supply Chain Management oferece um nome de pesquisa secundário para os produtos e também para os itens (produtos liberados). Esse nome de pesquisa não precisa ser exclusivo, e pode ser alterado depois que um produto ou grade de produto forem criados. É recomendável usar o nome de pesquisa para pesquisar produtos por categorias. Os nomes de pesquisa habilitam as pesquisas rápidas, principalmente em processos de venda e de compra.

O nome de pesquisa também pode conter uma ID de produto do cliente ou fornecedor, ou outra ID de produto externa, se essa ID externa for o principal critério de pesquisa para um produto.

## <a name="external-product-identifiers-customer-and-vendor-identifiers"></a>Identificadores de produtos externos (Identificadores de cliente e fornecedor)

Para produtos liberados, você pode manter os números de item, nomes de item e descrições de item usados pelo cliente ou fornecedor. As referências são mostradas em documentos externos, como ordens de venda, ordens de compra, guias de remessa e faturas. Na versão atual do Supply Chain Management, as referências externas não são mostradas nas páginas de operações centrais. A única exceção é o número de item do fornecedor. Esse número será exibido na caixa de diálogo **Informações sobre o produto** se um fornecedor padrão for definido para o produto liberado.

Você pode manter os identificadores de produtos externos por produto liberado, grade de produto liberado, cliente, grupo de clientes, fornecedor ou grupo de fornecedores.

Na página **Produtos liberados**, siga uma destas etapas.

- Para clientes, na guia **Venda**, no grupo **Informações relacionadas**, selecione **Descrição externa de item**.
- Para fornecedores, na guia **Compra**, no grupo **Informações relacionadas**, selecione **Descrição externa de item**.

Na página **Descrições externas de item**, você pode associar o número de item do cliente ou do fornecedor a um produto liberado. Essa associação deve ser feita para cada entidade legal. As seguintes informações podem ser capturadas. Infelizmente, as etiquetas estão ligeiramente incorretas na versão atual do Supply Chain Management. No entanto, essas etiquetas poderão ser alteradas em uma versão futura.

| Campo | Informações correspondentes do cliente | Informações correspondentes do fornecedor |
|-------|------------------------------------|----------------------------------|
| Número do item externo | O número de item do cliente | O número de item do fornecedor |
| descrição | O nome que o cliente associa ao item | O nome que o fornecedor associa ao item |
| Texto de item externo | A descrição do item do cliente | A descrição do item do fornecedor |

Se vários clientes ou fornecedores usarem os mesmos números de item (como uma associação de compra ou um grupo de comércio, por exemplo), você poderá criar grupos de clientes ou fornecedores para simplificar a manutenção de informações sobre produtos externos.

- Para grupos de clientes, Acesse **Vendas** &gt; **Configuração** &gt; **Itens** &gt; **Descrição externa de item** para criar e manter os grupos e os números de itens relacionados. Para associar clientes a um grupo, Acesse **Contas a receber** &gt; **Clientes** &gt; **Todos os clientes** e, em seguida, na Guia Rápida **Padrões da ordem de venda**, especifique um valor no campo **Item - Grupo de clientes**.
- Para grupos de fornecedores, Acesse **Compras e Fornecimento** &gt; **Configuração** &gt; **Grupo de descrições externas de item** para criar e manter os grupos e os números de itens relacionados. Para associar fornecedores a um grupo, Acesse **Contas a pagar** &gt; **Fornecedores** &gt; **Todos os fornecedores** e, em seguida, na Guia Rápida **Padrões da ordem de compra**, especifique um valor no campo **Item - Grupo de fornecedores**.
 
## <a name="bar-codes"></a>Códigos de Barra

Se quiser usar um scanner de código de barras para identificar produtos, o identificador do produto deve atender aos requisitos do padrão de código de barras usado. Portanto, os códigos de barras normalmente não contêm o número do produto bruto, mas um número gerado especificamente para a tecnologia de código de barras selecionada. Você pode manter vários códigos de barras por tipo de código de barras. Você pode até associar o mesmo código de barras a vários produtos e depois selecionar a associação ativa real quando digitalizar um código de barras.

Antes de definir os códigos de barras, você pode definir uma ou mais configurações de código de barras. As configurações de código de barras podem ajudar a verificar se os códigos de barras seguem as diretrizes necessárias e se, consequentemente, podem ser efetivamente impressos e digitalizados. Você também pode manter códigos de barras especiais para quantidades específicas de produto.

É recomendável usar a configuração de código de barras para manter os códigos GTIN (Número global de item comercial) ou EAN (Número de artigo internacional).

Para manter códigos de barras, na página **Produtos liberados**, na guia **Gerenciar estoque**, no grupo **Depósito**, selecione **Códigos de barras**.

## <a name="gtin-codes"></a>Códigos GTIN

No comércio eletrônico, é essencial que todos os participantes falem a mesma língua e refiram-se aos produtos usando um conjunto comum de identificadores. Portanto, algumas indústrias dependem do [GTIN](https://www.gs1.org/id-keys/gtin), um sistema global de número de item que é facilitado por GS1.

Recomendamos manter o GTIN como um código de barras. No entanto, também é possível mantê-lo na página **Item - GTIN**. Para abrir essa página, na página **Produtos liberados**, na guia **Gerenciar estoque**, no grupo **Depósito**, selecione **Códigos GTIN**. O GTIN não é mantido como um número global. Em vez disso, é mantido por entidade legal.

No Supply Chain Management, você define as grades de embalagens nas operações de depósito, definindo unidades de medida específicas. Por exemplo, um item pode ser armazenado em partes, em pacotes de seis, em bandejas de 18 ou em paletes cheios. Uma unidade de medida específica será definida para cada uma dessas grades de embalagens. Como o GTIN normalmente está relacionado à unidade de embalagem de um produto, a página **Item - GTIN** permite manter vários códigos GTIN por produto e unidade de medida. No entanto, você não pode usar o mesmo código GTIN mais de uma vez para itens ou grades de produtos diferentes de uma entidade legal.

Para manter **Códigos GTIN**, na página **Produtos liberados**, na guia **Gerenciar estoque**, no grupo **Depósito**, selecione **GTIN**.

## <a name="external-codes"></a>Códigos Externos

Os códigos externos podem ser definidos para várias entidades. Por exemplo, você pode definir códigos externos para identificar produtos e produtos liberados. Esses códigos externos podem ser usados para associar códigos estatísticos ou códigos de imposto a produtos liberados e grades de produtos liberados. Os códigos externos são definidos por entidade legal e tipo de código. Eles devem ser exclusivos por entidade legal, tipo de código e referência de tabela.

Infelizmente, não há nenhuma funcionalidade padrão que permite pesquisar produtos por códigos externos.

## <a name="data-entities-that-are-used-to-import-and-export-product-identifiers"></a>Entidades de dados usadas para importar e exportar identificadores de produtos

| Nome da entidade | Importar identificadores | Exportar identificadores | Comentários |
|-------------|--------------------|--------------------|----------|
| Produtos V2 | Número do produto, nome de pesquisa do produto, nome do produto, descrição do produto | Número do produto, nome de pesquisa do produto, nome do produto, descrição do produto | Dependendo das configurações da entidade e da sequência numérica do número do produto, o número do produto pode ser criado automaticamente no momento da importação. |
| Variantes de produtos | Número do produto, nome de pesquisa do produto, nome do produto, descrição do produto | Número do produto, nome de pesquisa do produto, nome do produto, descrição do produto | Dependendo do modelo de nomenclatura de produtos, o número do produto pode ser criado automaticamente no momento da importação. No entanto, você pode importar qualquer número de produto exclusivo, e esse número de produto não precisa seguir a estrutura dos modelos de nomenclatura de produtos. |
| Traduções do produto | Nome do produto, descrição do produto | Nome do produto, descrição do produto | Essa entidade substitui qualquer idioma. Quando o nome ou a descrição do idioma principal de uma entidade legal são substituídos, o nome e a descrição do produto são alterados. |
| Criação de produtos liberados V2 | Número do item, número do produto, nome de pesquisa do item| Número do item, número do produto, nome de pesquisa do item, nome de pesquisa do produto, nome do produto | Essa entidade pode ser um desafio quando sequências numéricas são usadas durante a criação de novos produtos liberados. Tanto a sequência numérica **Número do item** quanto a sequência numérica **Número do produto** têm uma influência. No entanto, a sequência numérica **Número do item** é por entidade legal, enquanto a sequência numérica **Número do produto** é global. Portanto, não é recomendável usar a sequência numérica **Número do item** ao implantar novos produtos liberados. Obviamente, quando a entidade é usada para liberar um produto existente, o número do produto deve ser fornecido na entidade. Para obter mais informações, consulte a seção “Sequências numéricas do item e do produto” neste tópico. |
| Grades de produtos liberadas | Número do item, dimensões do produto, número do produto | Número do produto, nome de pesquisa do produto, nome do produto, descrição do produto, dimensões do produto | Assim como a entidade **Grades de produtos**, essa entidade pode ser usada para criar novos produtos que seguem o modelo de nomenclatura de produtos ou usam seus próprios números de produto para a grade. |
| Descrição de itens externos para clientes | Número de item do cliente, nome de item do cliente, descrição do cliente, conta de cliente | Número de item do cliente, nome de item do cliente, descrição do cliente, conta de cliente | Um grupo de clientes (por exemplo, uma associação de compradores) pode ser agregado em um grupo usando a entidade **Grupos de clientes para descrição de item externo**. |
| Descrição de itens externos para fornecedores | Número de item do fornecedor, nome de item do fornecedor, descrição do fornecedor, conta de fornecedor | Número de item do fornecedor, nome de item do fornecedor, descrição do fornecedor, conta de fornecedor | Um grupo de fornecedores (por exemplo, uma associação de vendas ou organização da indústria) pode ser agregado em um grupo usando a entidade **Grupos de fornecedores para descrição de item externo**. |
| Código de barras do item | Código de barras | Código de barras | No momento da importação, você deve fazer referência a uma configuração de código de barras definida no sistema de destino. As referências de código de barras importadas são validadas em relação a essa configuração de código de barras e serão rejeitadas se os códigos de barras não corresponderem aos requisitos definidos nessa configuração. |
| Códigos externos para produtos liberados | Código externo | Código externo, classes de código externo, número do item | Os códigos externos são por entidade legal. Para importar, você deve fazer referência a uma classe de código definida. Importe as classes de código usando a entidade **Classes de código externo para produtos liberados**. |
| Códigos externos para grades de produtos liberados | Código externo | Código externo, classes de código externo, número do item, dimensões do produto | Os códigos externos são por entidade legal. Para importar, você deve fazer referência a uma classe de código definida. Importe as classes de código usando a entidade **Classes de código externo para produtos liberados**. Essa entidade se refere a grades de produtos pelo número do item e pelas dimensões do produto. |
| Códigos externos para grades de produtos liberados por identificador de número do produto | Código externo | Código externo, classes de código externo, número do produto | Os códigos externos são por entidade legal. Para importar, você deve fazer referência a uma classe de código definida. Importe as classes de código usando a entidade **Classes de código externo para produtos liberados**. Essa entidade se refere a grades de produtos pelo número do produto da grade. (Da próxima versão principal) |
| GTIN | Não Aplicável | Não Aplicável | No momento, não há nenhuma entidade específica usada para importar e exportar códigos GTIN. Em vez disso, é recomendável usar a entidade **Código de barras do item**. |
| Entidade de identificador de Common Data Service de entidade de produto | Não Aplicável | Número do item, nome de pesquisa do item, nome de pesquisa do produto, número de item do fornecedor, número de item do cliente, códigos externos, códigos GTIN, códigos de barras | Essa entidade consolida todos os identificadores em um modelo de dados, para que uma interface possa ser usada para exportar facilmente todos os identificadores e seus tipos relacionados. Use a entidade **Código de identificador de entidade Produto** para exportar os códigos e as descrições dos identificadores. Use a entidade **Escopo de identificador de entidade Produto** para exportar informações adicionais sobre o escopo para um identificador, como o participante, a entidade legal, a quantidade ou a unidade. |

### <a name="product-and-item-number-sequences"></a>Sequências numéricas do item e do produto

Você pode definir duas sequências numéricas diferentes:

- A sequência numérica **Número do produto** para o número do produto global
- A sequência numérica **Número do item** para o número do item por entidade legal

> [!NOTE]
> Você deve usar o número do item como um identificador separado apenas quando migrar entidades legais diferentes de fontes diferentes com sistemas de numeração diferentes. Você sempre deve tentar usar um identificador de produto que seja exclusivo em todas as entidades legais. Portanto, você deve definir a opção **Manual** como **Sim** para a sequência numérica **Número do item**. Dessa forma, o número do item acompanhará o número do produto na criação. Se o Supply Chain Management não for o sistema principal para novos números de produto, você deverá definir a opção **Manual** como **Sim** para as sequências numéricas **Número do item** e **Número do produto**.

Quando você usa a entidade **Criação de produtos liberados V2** para criar produtos, várias configurações podem afetar a maneira como as sequências numéricas são usadas para criar o número do produto e o número do item:

- Configurações da sequência numérica **Número do produto**
- Configurações da sequência numérica **Número do item**
- O mapeamento do número do item 
- O mapeamento do número do produto

A tabela a seguir fornece uma visão geral dos resultados de importação e criação manual com combinações específicas da sequência numérica e das configurações de mapeamento de campos.

| Sequência numérica de número do produto | Sequência numérica de número do item | Mapeamento do número do item | Mapeamento do número do produto | Resultado da importação da entidade | Resultado da criação manual | Conclusão |
|--------------------------------|-----------------------------|----------------------------|-------------------------------|-------------------------|----------------------------|-----------|
| Manual = Não | Manual = Não | Nenhum mapeamento | Nenhum mapeamento | Os números do produto usam a sequência numérica **Número do produto**. Os números do item usam a sequência numérica **Número do item**. | Os números do produto usam a sequência numérica **Número do produto**. Os números do item usam a sequência numérica **Número do item**. | Com essa configuração, os números do produto seguirão a sequência do número do produto e os números do item seguirão a sequência do número do item. No entanto, essa configuração não funcionará se houver mais de um item (linha) a ser importado. |
| Manual = Não | Manual = Sim | Gerar automaticamente | Nenhum mapeamento | Os números do produto e os números do item usam a sequência numérica **Número do item**. | Os números do produto e os números do item usam a sequência numérica **Número do produto**. | Os números do produto e do item seguirão a sequência do número do produto. Essa é a abordagem recomendada para importar produtos em massa com a entidade de dados Criação de produtos liberados V2.<br><br>Você só pode usar essa abordagem ao importar itens em massa (várias linhas) e quando não estiver criando itens por meio da interface do usuário. Se você precisar importar em massa e criar produtos por meio da interface do usuário, use o procedimento na próxima linha desta tabela. Para fazer a transição de uma abordagem de importação em massa para a interface do usuário a fim de importar e criar produtos de forma manual, você deve ajustar manualmente o **Próximo número** na sequência numérica do número do item para que corresponda ao **Próximo número** na sequência numérica do número do produto. Em seguida, você pode alternar para a abordagem na próxima linha desta tabela. |
| Manual = Não | Manual = Sim | Nenhum mapeamento | Nenhum mapeamento | Os números do produto e os números do item usam a sequência numérica **Número do produto**. | Os números do produto e os números do item usam a sequência numérica **Número do produto**. | Os números do produto e do item usarão a sequência do número do produto. No entanto, essa configuração não funcionará se houver mais de um item (linha) a ser importado.<br><br>Você deve usar essa abordagem se precisar importar produtos usando as entidades (somente uma linha pode ser importada por vez) e criar produtos por meio da interface do usuário. |
| Manual = Sim | Não Aplicável | Não Aplicável | Gerar automaticamente | Você recebe a seguinte mensagem de erro: "A sequência numérica não pode ser detectada." | De acordo com a sequência numérica **Número do item** | Essa configuração não tem suporte para importação. |

## <a name="product-entity-identifier-export-all-product-identifiers"></a>Identificador de entidade Produto (Exportar todos os identificadores do produto)

O modelo do identificador de entidade Produto foi criado para habilitar a versão 1.0 do Dataverse a ser provisionada com todos os identificadores usados para fazer referência a um produto. Para simplificar essa tarefa, todos os identificadores são agregados em uma tabela global de identificadores, para que possam ser exportados como um modelo. Observe que essa versão do Dataverse não usa o modelo de identificadores de produtos. Portanto, a entidade **Entidade de identificador de Common Data Service de entidade de produto** e esse processo têm uso prático limitado e provavelmente estarão sujeitos a alterações futuramente.

A tabela de identificadores de produtos é uma tabela global preenchida a partir de todas as tabelas de referência da Entidade legal principal por meio de um trabalho em lotes recorrente. Você deve selecionar uma entidade legal e uma hierarquia de categoria de produto como a definição do escopo global do produto mestre. A geração da tabela global de identificadores de produtos limita-se aos produtos que são liberados para a entidade legal selecionada e aos produtos que são membros da hierarquia de produtos selecionada para a função **Common Data Service** na hierarquia de categoria de produto.

Esse processo pressupõe que os dados mestres do produto são mantidos principalmente em uma entidade legal central. (No entanto, essa entidade legal pode ser uma entidade legal virtual usada somente para manter dados mestres globais.)

Siga estas etapas para configurar o ambiente.

1. Selecione a hierarquia de categoria para o Dataverse. Na página **Associações de funções de hierarquia de categoria**, se nenhuma hierarquia estiver associada à função **Common Data Service**, você deverá criar uma nova associação. Selecione a função **Common Data Service** e associe a hierarquia de categoria que representa o portfólio de produtos que deverá ser sincronizado com o Dataverse.
2. Selecione a entidade legal para dados mestres globais do produto. Na página **Parâmetros de gerenciamento de informações do produto**, na guia **Atributos do produto**, selecione a empresa mestre na qual os identificadores do produto e do item são mantidos principalmente.
3. Defina os tipos de código de identificadores e os códigos que devem ser exportados. Acesse **Gerenciamento de informações sobre produtos** &gt; **Configuração** &gt; **Códigos de identificador de produtos**. Para gerar os tipos de código de identificadores, selecione **Gerar códigos**. Uma entrada de tipo de código é gerada para cada tipo do identificador encontrado na entidade legal selecionada.

    Para códigos de barras, um tipo de código é gerado para cada configuração de código de barras. Para códigos externos, um tipo de código é gerado para cada classe de código externo.

    Agora você pode manter a lista de tipos de código. Você pode alterar o código, o nome e a descrição. Também é possível excluir os tipos de código. Os tipos de código excluídos não serão usados para preencher as tabelas globais de identificadores de entidade Produto.

4. Quando terminar de definir os tipos de código de identificadores de produtos, você poderá criar os identificadores na tabela global iniciando o trabalho **Criar identificadores de entidade Produto** na página **Códigos de identificador de entidade Produto**. Você deve executar esse trabalho em um lote. Esse trabalho deve ser configurado como um trabalho em lotes periódico para que a tabela seja preenchida de acordo com as entradas novas.

Agora você pode usar as entidades de dados **Entidade de identificador de Common Data Service de entidade de produto**, **Código de identificador de entidade Produto** e **Escopo de identificador de entidade Produto** para exportar os identificadores para qualquer sistema de destino.

## <a name="related-topic"></a>Tópico relacionado

[Procurar produtos e grades de produtos durante uma entrada de ordem](search-products-product-variants.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
