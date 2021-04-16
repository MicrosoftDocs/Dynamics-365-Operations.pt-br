---
title: Catálogo de endereços global e dos participantes
description: Este tópico descreve o recurso Catálogo de endereços global e de participantes de gravação dupla.
author: RamaKrishnamoorthy
ms.date: 02/22/2021
ms.topic: article
ms.service: dynamics-ax-applications
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: e7bec58f8094a1448017822e7d8840368cc482b8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750779"
---
# <a name="party-and-global-address-book"></a>Catálogo de endereços global e dos participantes

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Catálogo de endereços global e de participantes são conceitos em aplicativos de Finance and Operations. Um participante pode ser uma organização ou uma pessoa. É conveniente armazenar e gerenciar globalmente as propriedades de um **participante**, como nome, idioma, contatos e endereços. Quando um valor de propriedade é alterado em um local, ele reflete em todos os locais onde o **participante** está envolvido.

## <a name="party"></a>Participante

Um *participante* é uma pessoa ou uma organização envolvida no negócio. Usando o conceito de participante, uma pessoa ou organização pode realizar mais de uma função (trabalhador, cliente, fornecedor ou contato) em uma empresa. A função se baseia no contexto e na finalidade. Veja aqui alguns exemplos de duas empresas fictícias, Contoso e Fabrikam.

+ **Trabalhador**: um funcionário. Por exemplo, um funcionário da Contoso.
+ **Fornecedor**: uma organização fornecedora ou um único proprietário que fornece bens ou serviços a uma empresa. Por exemplo, se a Fabrikam vende equipamentos para a Contoso, a Fabrikam está na função de fornecedora.
+ **Contato**: uma pessoa para entrar em contato. Por exemplo, se a Contoso compra equipamentos da Fabrikam, um funcionário na Contoso entra em contato com o contato na Fabrikam.
+ **Cliente**: um cliente é uma pessoa ou empresa que compra itens de uma organização. Por exemplo, se a Contoso comprar equipamentos da Fabrikam, a Contoso será uma cliente da Fabrikam.

O modelo de participante geralmente é usado para representar relacionamentos médios e complexos entre organizações e pessoas, principalmente quando um participante realiza mais de uma função. Veja aqui alguns exemplos comuns:

+ Um participante pode ser tanto um cliente quanto um fornecedor. Por exemplo, na América do Norte, a Fabrikam vende fios elétricos para a Contoso e compra caixas de som montadas da Contoso. Na Europa, a Fabrikam vende peças para a Contoso, mas não compra itens da empresa.
+ Um participante pode ser tanto um funcionário quanto um cliente. Por exemplo, um funcionário da Contoso compra eletrônicos da Contoso para uso pessoal.
+ Pode haver um relacionamento de muitos para muitos entre uma pessoa e uma organização. Por exemplo, a Fabrikam fornece especialistas em serviço e emprega um coordenador de posicionamento. O coordenador indica os especialistas em serviço a solicitação de trabalho ideal para eles feita por vários clientes da Fabrikam. A Contoso é uma das contas de cliente. Quando a Contoso precisa de um especialista, ela entre em contato com o coordenador, que facilita a solicitação. O coordenador administra solicitações de todos os clientes, criando um relacionamento de muitos para muitos.

A imagem a abaixo mostra o modelo de dados de participante:

![Modelo de dados de participante](media/party-gab-image1.png)

> [!Tip]
> Ao tentar criar um registro de conta, use o campo "Participante" para procurar o registro pelo nome. Caso encontre o registro, você só precisará selecioná-lo. O sistema preenche todos os dados do participante automaticamente. Não é necessário preencher manualmente todos os campos obrigatórios. Esse comportamento pode ser encontrado nos formulários Conta, Contato ou Fornecedor que foram enviados de forma integrada.

Nem todas as funções de participante dos aplicativos de Finance and Operations são compatíveis com gravação dupla. Para obter uma lista completa das funções do participante, consulte [Visão geral do catálogo de endereços global](../../../fin-ops/organization-administration/overview-global-address-book.md).

### <a name="global-address-book"></a>Catálogo de endereços global

O catálogo de endereços global é um diretório de endereços postais e eletrônicos das organizações e dos indivíduos que fazem parte de uma empresa.

O catálogo de endereços global armazena e administra endereços postais e eletrônicos, conforme necessário. Por exemplo, digamos que a Fabrikam tenha postos de gasolina em 50 locais. Cada local tem um endereço postal, email e número de telefone diferente. Todas as compras comerciais são cobradas do posto principal, mas as compras são enviadas diretamente para o posto de gasolina específico que solicitou a compra. O catálogo de endereços global armazena o endereço do posto principal como o endereço de cobrança e salva o local dos outros postos de gasolina como um endereço de entrega da Fabrikam. Os endereços podem ser armazenados uma vez e recuperados conforme necessário para cotações e pedidos.

Uma pessoa ou organização pode realizar mais de uma função com base no contexto comercial. Quando isso acontece, os endereços postais e eletrônicos podem ser os mesmos. Nesse caso, uma alteração no endereço de uma função deverá aparecer no registro de outras funções e vice-versa. O catálogo de endereços global armazena e administra os endereços globalmente.

![Modelo de dados do catálogo de endereços global](media/party-gab-image2.png)

## <a name="contacts"></a>Contatos

Em aplicativos de interação com clientes, um *contato* é uma pessoa. No entanto, a tabela de **contatos** foi sobrecarregada para representar uma pessoa, um usuário do portal, um cliente do B2C ou um fornecedor. A representação é implícita e não é possível diferenciá-la sem investigar as transações relacionadas. A tabela **Contatos** foi limitada a ter uma relação direta com a tabela **Contas**. Como parte do modelo Participantes e catálogo de endereços global, a gravação dupla apresenta propriedades explícitas para a classificação e permite relacionamentos de muitos para muitos entre um **contato** e uma organização (entidade Conta ou entidade Fornecedor).

Há dois tipos de linhas **Contato**:

+ Contato distribuído – linha Contato com um valor obrigatório no campo **Empresa**.
+ Contato não distribuído – linha Contato com campo **Empresa** em branco.

A tabela **Contato** pode contar com estes tipos de linha:

Tipo de linha | descrição
---|---
Uma pessoa que é um cliente, como um contato comercializável ou um cliente B2C. | Um registro de contato distribuído em que o campo **Empresa** não está em branco e o campo **É Cliente** está preenchido com **Sim**.
Uma pessoa que é um fornecedor, como um fornecedor do tipo único proprietário. | Um registro de contato distribuído em que o campo **Empresa** não está em branco o campo **É Fornecedor** está preenchido com **Sim**.
Uma pessoa que é cliente e fornecedora. | Um registro de contato distribuído em que o campo **Empresa** não está em branco, o campo **É Cliente** está preenchido com **Sim** e o campo **É Fornecedor** está preenchido com **Sim**. Uma pessoa pode ser um produtor de produto e um cliente de outro produto. Tanto os aplicativos de Finance and Operations quanto a gravação dupla oferecem suporte a esse relacionamento.
Uma pessoa que é um contato de uma organização, mas não é um cliente nem um fornecedor. | Um registro de contato não distribuído em que o campo **Empresa** não está em branco, o campo **É Cliente** está preenchido com **Não** e o campo **É Fornecedor** está preenchido com **Não**.

## <a name="contact-for-party"></a>Contato do participante

O **Contato do participante** armazena e administra relacionamentos de muitos para muitos entre as linhas **Conta** e **Contato**. Ele pode filtrar as linhas **Contato** distribuídas de linhas não distribuídas e associar penas as linhas **Contato** não distribuídas às linhas **Conta** ou **Fornecedor**.

Por exemplo, Natasha Jones e Miguel Reyes são veterinários que atendem fazendas na área. Natasha atende a área de Seattle, e Miguel atende a área Kent. No aplicativo de engajamento do cliente, as fazendas são representadas como clientes e os veterinários são as pessoas de contato. Um único registro de **contato** de Natasha está associado a todas as fazendas com as quais ela trabalha. De forma similar, um único registro de **contato** de Miguel está associado a todas as fazendas com as quais ele trabalha.

Esses relacionamentos estão registrados na tabela **Contato do participante**. Você pode encontrar as informações nos formulários integrados:

+ No formulário **Conta**, há uma guia chamada **Contatos associados**. Use essa guia para associar um ou mais contatos à linha **Conta**. Neste formulário, você atribui uma pessoa de contato a uma organização. Depois de atribuir os contatos, você pode escolher um como contato principal para essa conta. No formulário **Criação rápida**, você pode selecionar apenas uma pessoa de contato. O comportamento é o mesmo que ocorre quando você usa o formulário **Fornecedor** e o tipo de registro é **Organização**.
+ No formulário **Contato**, em que a linha é um cliente, fornecedor ou ambos (um contato distribuído), há uma guia chamada **Contatos associados**. Use essa guia para associar um ou mais contatos. Nesse formulário, você atribui uma pessoa de contato a um cliente ou fornecedor B2C. Depois de atribuir os contatos, você pode escolher um como contato principal. No formulário **Criação rápida**, você pode selecionar apenas uma pessoa de contato.
+ No formulário **Contato**, em que a linha é uma pessoa de contato (um contato não distribuído), há uma guia chamada **Contatos associados**. Use essa guia para associar um ou mais clientes ou fornecedores. Nesse formulário, você atribui um cliente ou fornecedor a uma pessoa de contato subjacente. O cliente ou fornecedor pode ser uma organização, uma pessoa ou ambos. Você pode escolher somente um valor dos quatro campos em um determinado momento.

    ![Guia Organizações associadas](media/party-gab-image3.png)

    + Se você selecionar **ID do participante**, o contato subjacente será atribuído a todas as funções do participante selecionado.
    + Se você selecionar **Contato associado**, estará selecionando um contato distribuído do tipo pessoa.
    + Se você selecionar **Conta associada** ou **Fornecedor**, estará selecionando uma organização.

    Independentemente da sua escolha, a associação é criada no nível do participante e se aplica a todas as funções do participante e armazenada na entidade "Contato do participante".

> [!Note]
> O nome de exibição da tabela **Contato do participante** no aplicativo de engajamento do cliente é **Contato do cliente/fornecedor**.

Ao abrir uma linha **Contato** em que **É Cliente** está definido como **Não** e **É Fornecedor** está definido como **Não**, você verá a guia **Organizações associadas**. Use essa guia para associar um ou mais clientes ou organizações de fornecedores ao contato.

Ao abrir uma linha **Contato** em que **É Cliente** está definido como **Sim** ou **É Fornecedor** está definido como **Sim**, você verá a guia **Contatos**. Use essa guia para associar um ou mais clientes ou organizações de fornecedores aos contatos.

## <a name="postal-address"></a>Endereço postal

Uma nova guia denominada **Endereços** foi apresentada nos formulários **Conta**, **Contato** e **Fornecedor**. A coluna **Endereços** oferece suporte aos endereços N usando uma grade, conforme exibido nesta imagem:

![Grade para endereço postal](media/party-gab-image4.png)

+ A coluna **Funções de endereços postais** indica a finalidade do endereço.
+ A coluna **É Principal** indica o endereço principal.
+ A coluna **Número do endereço** indica a ordem do endereço.
+ O botão **Adicionar endereço** permite que você crie um endereço. Você pode criar quantos endereços desejar.

Os campos **Endereço 1** e **Endereço 2** na guia **Resumo** do formulário **Conta** correspondem aos endereços **Entrega** e **Fatura**, respectivamente.

![Guia Resumo para endereço postais](media/party-gab-image5.png)

Os campos **Endereço 1**, **Endereço 2** e **Endereço 3** na guia **Resumo** do formulário **Contato** correspondem aos endereços de **Negócios**, **Entrega** e **Fatura**, respectivamente.

## <a name="electronic-address"></a>Endereço eletrônico

Uma nova guia denominada **Endereços eletrônicos** foi apresentada nos formulários **Conta**, **Contato** e **Fornecedor**. A coluna **Endereços** oferece suporte aos endereços N usando uma grade, conforme exibido nesta imagem:

![Grade para endereço eletrônico](media/party-gab-image6.png)

+ A coluna **Tipo** indica o tipo de endereço.
+ A coluna **É Principal** indica o endereço principal.
+ A coluna **Finalidade** indica a finalidade do endereço eletrônico.
+ O botão **Adicionar endereço eletrônico** permite que você crie um endereço. Você pode criar quantos endereços desejar.

Os endereços eletrônicos estão disponíveis somente nesta grade. Nos próximos lançamentos, todos os campos de endereço eletrônico e postal serão removidos de outras guias, por exemplo, as guias **Resumo** e **Detalhes**.

## <a name="setup-instructions"></a>Instruções de configuração

Se você for um cliente de gravação dupla existente, estas instruções de configuração serão necessárias. Caso contrário, você poderá ignorar esta seção.

1. Interrompa os seguintes mapas, pois eles não são mais necessários. Em vez disso, execute o mapa Contatos V2 (msdyn_contactforparties).

    + Contatos V2 do CDS e Contatos (refere-se aos contatos de clientes)
    + Contatos V2 do CDS e Contatos (refere-se aos contatos de fornecedores)

2. Os mapeamentos de entidade abaixo são atualizados de acordo com os recursos do participante, portanto, a versão mais recente deve ser aplicada a esses mapeamentos.

Mapa | Atualize para esta versão | Alterações
---|---|---
Clientes V3 (contas) | 1.0.0.5 |Remoção de PartyNumber e de outros campos relacionados ao participante, como nome, informações pessoais, campos de endereço postal, campo de endereço de contato eletrônico etc.
Clientes V3 (contatos) | 1.0.0.5 | Remoção de PartyNumber e de outros campos relacionados ao participante, como nome, informações pessoais, campos de endereço postal, campo de endereço de contato eletrônico etc.
Fornecedores V2 (msdyn_vendors) | 1.0.0.6 | Remoção de PartyNumber e de outros campos relacionados ao participante, como nome, informações pessoais, campos de endereço postal, campo de endereço de contato eletrônico etc.
Cabeçalho de cotação de venda do CDS (cotações) | 1.0.0.6 | Substituição da pessoa de contato pela referência ContactforParty.
Cabeçalhos de fatura de venda V2 (faturas) | 1.0.0.4 | Substituição da pessoa de contato pela referência ContactforParty.
Cabeçalhos de ordens de vendas do CDS (salesorders) | 1.0.0.5 | Substituição da pessoa de contato pela referência ContactforParty.
Contatos V2 (msdyn_contactforparties) | 1.0.0.2 | Este é um novo mapa. Se você tiver uma versão antiga da solução do participante, certifique-se de atualizar este mapa para a versão mais recente, conforme mencionado.
Locais de endereço postal de parceiros do CDS (msdyn_partypostaladdresses) | 1.0.0.1  | Este é um novo mapa adicionado como parte da versão antiga da visualização preliminar do participante.
Histórico de endereço postal V2 do CDS (msdyn_postaladdresses) | | Este é um novo mapa adicionado como parte da versão antiga da visualização preliminar do participante.
Locais de endereço postal de parceiros do CDS (msdyn_postaladdresscollections) | | Este é um novo mapa adicionado como parte da versão antiga da visualização preliminar do participante.
Contatos do participante V3 (msdyn_partyelectronicaddresses) | | Este é um novo mapa adicionado como parte desta versão.

## <a name="templates"></a>Modelos

Um conjunto de mapas de tabelas funcionam juntos para a interação do participante com o catálogo de endereços global, conforme mostrado na tabela a seguir.

Aplicativo Finance and Operations | Aplicativo Customer Engagement     | descrição
----------------------------|-----------------------------|------------
[Títulos da pessoa de contato](mapping-reference.md#223) | msdyn_salescontactpersontitles |
[Clientes V3](mapping-reference.md#101) | contas |
[Clientes V3](mapping-reference.md#116) | contatos |
[Participantes do CDS](mapping-reference.md#220) | msdyn_parties |
[Localizações de endereço postal do participante do CDS](mapping-reference.md#233) | msdyn_partypostaladdresses |
[Histórico de endereço postal do CDS V2](mapping-reference.md#235) | msdyn_postaladdresses |
[Localizações de endereço postal do CDS](mapping-reference.md#234) | msdyn_postaladdresscollections |
[Cabeçalho de cotação de venda CDS](mapping-reference.md#215) | cotações |
[Cabeçalhos de ordens de venda CDS](mapping-reference.md#217) | salesorders |
[Fechamentos complementares](mapping-reference.md#222) | msdyn_complimentaryclosings |
[Contatos V2](mapping-reference.md#221) | msdyn_contactforparties |
[Funções de tomada de decisão](mapping-reference.md#224) | msdyn_decisionmakingroles |
[Funções de trabalho de emprego](mapping-reference.md#225) | msdyn_employmentjobfunctions |
[Níveis de fidelidade](mapping-reference.md#226) | msdyn_loyaltylevels |
[Contatos do participante V3](mapping-reference.md#236) | msdyn_partyelectronicaddresses |
[Tipos de caracteres pessoais](mapping-reference.md#227) | msdyn_personalcharactertypes |
[Cabeçalhos de fatura de venda V2](mapping-reference.md#118) | faturas |
[Saudações](mapping-reference.md#228) | msdyn_salutations |
[Fornecedores V2](mapping-reference.md#202) | msdyn_vendors |

Para obter mais informações, consulte [Referência de mapeamento de gravação dupla](mapping-reference.md).
