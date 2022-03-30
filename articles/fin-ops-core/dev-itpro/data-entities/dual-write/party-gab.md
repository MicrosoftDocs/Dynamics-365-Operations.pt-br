---
title: Catálogo de endereços global e dos participantes
description: Este tópico descreve o recurso Catálogo de endereços global e de participantes de gravação dupla.
author: RamaKrishnamoorthy
ms.date: 03/10/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: 2e0d16b29a71da23acc925c09c87f0bb4776759c
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407756"
---
# <a name="party-and-global-address-book"></a>Catálogo de endereços global e de participantes

[!include [banner](../../includes/banner.md)]



*Participante* e *catálogo de endereços global* são conceitos nos aplicativos de Finanças e Operações. Um participante pode ser uma organização ou uma pessoa. É conveniente armazenar e gerenciar globalmente propriedades de um participante, como nome, idioma, contatos e endereços. Quando um valor de propriedade é alterado em um local, a alteração se reflete em todos os locais em que o participante está envolvido.

## <a name="party"></a>Participante

Um participante é uma pessoa ou uma organização que está envolvida em uma empresa. Quando o conceito de participante é usado, uma pessoa ou organização pode realizar mais de uma função em uma empresa (por exemplo, trabalhador, cliente, fornecedor ou contato). A função se baseia no contexto e na finalidade. Estes são alguns exemplos de funções de duas empresas fictícias, a Contoso e a Fabrikam:

+ **Trabalhador** – um funcionário. Um exemplo é um funcionário da Contoso.
+ **Fornecedor** – uma organização fornecedora ou um único proprietário que fornece mercadorias ou serviços a uma empresa. Por exemplo, se a Fabrikam vender suprimentos para a Contoso, a Fabrikam será um fornecedor da Contoso.
+ **Contato** – uma pessoa para contato. Por exemplo, se a Contoso comprar equipamentos da Fabrikam, os funcionários da Contoso falarão com o contato na Fabrikam.
+ **Cliente** – uma pessoa ou empresa que compra itens de uma empresa. Por exemplo, se a Contoso comprar suprimentos da Fabrikam, a Contoso será uma cliente da Fabrikam.

O modelo de participante geralmente é usado para representar relacionamentos médios e complexos entre organizações e pessoas, especialmente quando um participante realiza mais de uma função. Veja aqui alguns exemplos comuns:

+ Um participante pode ser tanto um cliente quanto um fornecedor. Por exemplo, na América do Norte, a Fabrikam vende fios elétricos para a Contoso e compra caixas de som montadas da Contoso. Na Europa, a Fabrikam vende peças para a Contoso, mas não compra itens da Contoso.
+ Um participante pode ser tanto um funcionário quanto um cliente. Por exemplo, um funcionário da Contoso compra eletrônicos da Contoso para uso pessoal.
+ Pode haver um relacionamento de muitos para muitos (N:N) entre uma pessoa e uma organização. Por exemplo, a Fabrikam fornece especialistas em serviço e emprega um coordenador de posicionamento. O coordenador de posicionamento faz a correspondência de especialistas com solicitações de diversos clientes da Fabrikam. A Contoso é um dos clientes da Fabrikam. Quando a Contoso solicita um especialista em serviço, ela fala com o coordenador de posicionamento, que facilita a solicitação. Como o coordenador de posicionamento controla as solicitações de todos os clientes, há um relacionamento N:N envolvido.

A ilustração a seguir mostra o modelo de dados de participante.

![Modelo de dados de participante.](media/party-gab-image1.png)

> [!TIP]
> Ao tentar criar um novo registro de conta, use o campo **Participante** para procurar o registro pelo nome. Dessa forma, se você encontrar o registro, bastará selecioná-lo. O sistema preenche automaticamente todos os dados do participante. Não é necessário definir manualmente todos os campos obrigatórios. Esse comportamento pode ser encontrado nas páginas **Conta**, **Contato** e **Fornecedor**.

A gravação dupla não dá suporte a todas as funções de participante de aplicativos de Finanças e Operações. Para obter uma lista completa das funções do participante, consulte [Visão geral do catálogo de endereços global](../../../fin-ops/organization-administration/overview-global-address-book.md).

### <a name="global-address-book"></a>Catálogo de endereços global

O catálogo de endereços global é um diretório de endereços postais e eletrônicos das organizações e dos indivíduos que participam de uma empresa.

O catálogo de endereços global armazena e trata endereços postais e eletrônicos, conforme necessário. Por exemplo, a Fabrikam tem postos de gasolina em 50 locais. Cada local tem um endereço postal, endereço email e número de telefone diferente. Todas as compras comerciais são cobradas do posto de gasolina principal, mas são enviadas diretamente para o posto de gasolina específico que solicitou a compra. O catálogo de endereços global armazena o posto de gasolina principal como o endereço de cobrança da Fabrikam e armazena cada posto de gasolina como um endereço de remessa. Os endereços podem ser armazenados uma vez e recuperados conforme necessário para cotações e ordens.

Dependendo do contexto comercial, uma pessoa ou uma organização pode executar mais de uma função, e o mesmo endereço postal e endereço eletrônico podem ser usados para todas as funções. Nesse caso, uma alteração no endereço de uma função deve aparecer em todas as outras funções. O catálogo de endereços global armazena e administra os endereços globalmente.

A ilustração a seguir mostra o modelo de dados para o catálogo de endereços global.

![Modelo de dados do catálogo de endereços global.](media/party-gab-image2.png)

## <a name="contact"></a>Contato

Em aplicativos Customer Engagement, um contato é uma pessoa. No entanto, a tabela **Contato** foi sobrecarregada para representar uma pessoa, um usuário do portal, um cliente do business-to-consumer (B2C) ou um fornecedor. A representação é implícita e não é possível diferenciá-la, a menos que você examine transações relacionadas. A tabela **Contatos** foi limitada a um relacionamento um para um (1:1) com a tabela **Contas**. Como parte do modelo participante e catálogo de endereços global, a gravação dupla apresenta propriedades explícitas para a classificação e permite relacionamentos N:N entre um contato que é uma pessoa e uma organização (entidade **Conta** ou **Fornecedor**).

Há dois tipos de linhas **Contato**:

+ **Contato distribuído** – Uma linha **Contato** em que o campo **Empresa** tem um valor obrigatório.
+ **Contato não distribuído** – Uma linha **Contato** em que o campo **Empresa** está em branco.

A tabela **Contato** pode conter os tipos de linhas a seguir.

| Tipo de linha | Descrição |
|----------|-------------|
| Uma pessoa que é um cliente (por exemplo, um contato comercializável ou um cliente B2C) | Um registro de contato distribuído em que o campo **Empresa** não está em branco e o campo **É Cliente** está definido como **Sim**. |
| Uma pessoa que é um fornecedor (por exemplo, um único proprietário, como um fornecedor) | Um registro de contato distribuído em que o campo **Empresa** não está em branco o campo **É Fornecedor** está definido como **Sim**. |
| Uma pessoa que é cliente e fornecedor | Um registro de contato distribuído em que o campo **Empresa** não está em branco, o campo **É Cliente** está definido como **Sim** e o campo **É Fornecedor** está definido como **Sim**. Uma pessoa pode ser um produtor de produto e um cliente de outro produto. Tanto os aplicativos de Finanças e Operações quanto a gravação dupla oferecem suporte a esse relacionamento. |
| Uma pessoa que é um contato de uma organização, mas não é um cliente ou um fornecedor | Um registro de contato não distribuído em que o campo **Empresa** não está em branco, o campo **É Cliente** está definido como **Não** e o campo **É Fornecedor** está definido como **Não**. |

## <a name="contact-for-party-table"></a>Tabela Contato do participante

A tabela **Contato do participante** armazena e trata relacionamentos N:N entre as linhas **Conta** e **Contato**. Ela pode filtrar as linhas **Contato** distribuídas de linhas não distribuídas e associar apenas as linhas **Contato** não distribuídas com as linhas **Conta** ou **Fornecedor**.

Por exemplo, Natasha Jones e Miguel Reyes são veterinários que atendem fazendas na área. Natasha atende a área de Seattle e Miguel atende a área de Kent. No aplicativo Customer Engagement, as fazendas são representadas como clientes e os veterinários são representados como pessoas de contato. Um único registro de **contato** de Natasha está associado a todas as fazendas com as quais ela trabalha. Da mesma forma, um único registro **Contato** de Miguel é associado a todas as fazendas com as quais Miguel trabalha.

Esses relacionamentos estão registrados na tabela **Contato do participante**. Você pode localizar as informações nas páginas **Conta**, **Contato** e **Fornecedor** prontos para uso​:

+ Na página **Conta**, você pode usar a guia **Contatos Associados** para associar um ou mais contatos à linha **Conta**. Dessa forma, você atribui pessoas de contato a uma organização. Você poderá selecionar um contato como o contato principal da conta. Se você usar a página **Criação rápida**, só poderá selecionar uma pessoa de contato. O comportamento é o mesmo quando você usa a página **Fornecedor** e o tipo de registro é **Organização**.
+ Na página **Contato**, quando a linha é um cliente, um fornecedor ou ambos (um contato distribuído), você pode usar a guia **Contatos Associados** para associar um ou mais contatos. Assim, você atribui pessoas de contato a um cliente ou fornecedor B2C. Você pode selecionar um contato como o contato principal. Se você usar a página **Criação rápida**, só poderá selecionar uma pessoa de contato.
+ Na página **Contato**, quando a linha é uma pessoa de contato (um contato não distribuído), você pode usar a guia **Organizações Associadas** para associar um ou mais clientes ou fornecedores. Assim, você atribui clientes ou fornecedores a uma pessoa de contato subjacente. O cliente ou fornecedor pode ser uma organização, uma pessoa ou ambos. Você pode selecionar um valor em apenas um dos quatro campos de cada vez:

    + Se você selecionar um valor no campo **ID do participante**, o contato subjacente será atribuído a todas as funções do participante selecionado.
    + Se você selecionar um valor no campo **Contato Associado**, estará selecionando um contato distribuído do tipo **Pessoa**.
    + Se você selecionar um valor no campo **Conta Associada** ou **Fornecedor Associado**, estará selecionando uma organização.

    ![Guia Organizações Associadas na página Contato.](media/party-gab-image3.png)

    Independentemente da sua seleção, a associação é criada no nível do participante, ela se aplica a todas as funções do participante e ela é armazenada na entidade **Contato do participante**.

> [!NOTE]
> O nome de exibição da tabela **Contato do participante** no aplicativo Customer Engagement é **Contato do Cliente/Fornecedor**.

Quando você abre uma linha **Contato** em que os campos **É Cliente** e **É Fornecedor** estão definidos como **Não**, a guia **Organizações Associadas** é mostrada. Use esta guia para associar uma ou mais organizações de clientes ou fornecedores ao contato.

Quando você abre uma linha **Contato** em que o campo **É Cliente** ou **É Fornecedor** está definido como **Sim**, a guia **Contatos Associados** é mostrada. Use essa guia para associar um ou mais contatos.

## <a name="postal-addresses"></a>Endereços postais

Uma nova guia **Endereços** foi apresentada nas páginas **Conta**, **Contato** e **Fornecedor**. Esta guia dá suporte a vários endereços postais usando uma grade, conforme mostrado na ilustração a seguir.

![Grade para endereços postais.](media/party-gab-image4.png)

A grade inclui as seguintes colunas:

+ **Funções de endereços postais** – A finalidade do endereço postal.
+ **É Principal** – um valor que indica se o endereço é o endereço principal.
+ **Número do endereço** – a ordem de endereço.

Você pode usar o botão **Novo Endereço** acima da grade para criar o número de endereços postais desejados.

Os campos **Endereço 1** e **Endereço 2** na guia **Resumo** da página **Conta** correspondem aos endereços **Entrega** e **Fatura**, respectivamente.

![Guia Resumo para endereços postais.](media/party-gab-image5.png)

Os campos **Endereço 1**, **Endereço 2** e **Endereço 3** na guia **Resumo** da página **Contato** correspondem aos endereços de **Negócios**, **Entrega** e **Fatura**, respectivamente.

## <a name="electronic-addresses"></a>Endereços eletrônicos

Uma nova guia **Endereços Eletrônicos** foi apresentada nas páginas **Conta**, **Contato** e **Fornecedor**. Esta guia dá suporte a vários endereços eletrônicos usando uma grade, conforme mostrado na ilustração a seguir.

![Grade para endereços eletrônicos.](media/party-gab-image6.png)

A grade inclui as seguintes colunas:

+ **Tipo** – o tipo de endereço eletrônico.
+ **É Principal** – um valor que indica se o endereço é o endereço principal.
+ **Finalidade** – a finalidade do endereço eletrônico.

Você pode usar o botão **Novo Endereço Eletrônico** acima da grade para criar o número de endereços desejados.

Os endereços eletrônicos estão disponíveis somente nesta grade. Nos próximos lançamentos, todos os campos de endereço eletrônico e postal serão removidos de outras guias, por exemplo, as guias **Resumo** e **Detalhes**. Os detalhes de contato exibidos na guia **Detalhes** são cópias somente leitura do endereço eletrônico principal, como telefone principal, email principal, telefone principal, fax principal e ID do Twitter principal. Durante o processo de qualificação de clientes potenciais, você pode fornecer um telefone comercial e um número do telefone celular. O telefone comercial é considerado o telefone principal se **IsMobile=No** e o número do telefone celular é considerado o telefone secundário se **IsMobile=Yes**.

> [!TIP]
> Use as guias **Endereços** e **Endereços Eletrônicos** nos formulários de **Conta** e **Contato** para gerenciar os endereços postal e eletrônico. Isso garante que os dados de endereço sejam sincronizados com os aplicativos de Finanças e Operações.

## <a name="setup"></a>Configuração

1. Abra o ambiente do aplicativo de participação do cliente.

2. Instale a versão mais recente (2.2.2.60 ou posterior) da [solução de orquestração de aplicativos de gravação dupla](https://aka.ms/dual-write-app).

3. Instale [Soluções de gravação dupla de catálogo de endereços global e de participante](https://aka.ms/dual-write-gab).

4. Abra o aplicativo de finanças e operações. Navegue até o módulo Gerenciamento de Dados e selecione a guia de gravação dupla. A página de administração de gravação dupla será aberta.

5. Aplique ambas as soluções instaladas nas etapas 2 e 3 utilizando a função [Aplicar solução](link-your-environment.md).

6. Interrompa os seguintes mapas, pois eles não são mais necessários. Execute o mapa `Contacts V2 (msdyn_contactforparties)`.

    + Contatos V2 do CDS e Contatos (refere-se aos contatos de clientes)
    + Contatos V2 do CDS e Contatos (refere-se aos contatos de fornecedores)

7. Os mapeamentos de entidade abaixo são atualizados de acordo com os recursos do participante, portanto, a versão mais recente deve ser aplicada a esses mapeamentos.

    Mapa | Atualize para esta versão | Alterações
    ---|---|---
    `CDS Parties (msdyn_parties)`| 1.0.0.0 | Este é um novo mapa adicionado como parte desta versão.
    `Contacts V2 (msdyn_contactforparties)`| 1.0.0.5 | Este é um novo mapa adicionado como parte desta versão.
    `Customers V3 (accounts)` | 1.0.0.5 |Remoção de `PartyNumber` e de outros campos relacionados ao participante, como os campos de nome, detalhes pessoais, endereço postal e endereço de contato eletrônico.
    `Customer V3 (contacts)` | 1.0.0.5 | Remoção de `PartyNumber` e de outros campos relacionados ao participante, como os campos de nome, detalhes pessoais, endereço postal e endereço de contato eletrônico.
    `Vendors V2 (msdyn_vendors)` | 1.0.0.6 | Remoção de `PartyNumber` e de outros campos relacionados ao participante, como os campos de nome, detalhes pessoais, endereço postal e endereço de contato eletrônico.
    `CDS Sales quotation headers (quotes)` | 1.0.0.7 | Substituição da pessoa de contato pela referência `ContactforParty`.
    `Sales invoice headers V2 (invoices)` | 1.0.0.4 | Substituição da pessoa de contato pela referência `ContactforParty`.
    `CDS Sales order headers (salesorders)` | 1.0.0.5 | Substituição da pessoa de contato pela referência `ContactforParty`.
    `CDS Party postal address locations (msdyn_partypostaladdresses)` | 1.0.0.1  | Este é um novo mapa adicionado como parte desta versão.
    `CDS postal address history V2 (msdyn_postaladdresses)` | 1.0.0.1 | Este é um novo mapa adicionado como parte desta versão.
    `CDS postal address locations (msdyn_postaladdresscollections)` | 1.0.0.0 | Este é um novo mapa adicionado como parte desta versão.
    `Party Contacts V3 (msdyn_partyelectronicaddresses)` | 1.0.0.0 | Este é um novo mapa adicionado como parte desta versão.
    `Complimentary Closings ( msdyn_compliemntaryclosings)` | 1.0.0.0 | Este é um novo mapa adicionado como parte desta versão.
    `Decision making roles (msdyn_decisionmakingroles)` | 1.0.0.0 | Este é um novo mapa adicionado como parte desta versão.
    `Loyalty levels (msdyn_loyaltylevels)` | 1.0.0.0 | Este é um novo mapa adicionado como parte desta versão.
    `Contact person titles (msdyn_salescontactpersontitles)` | 1.0.0.0 | Este é um novo mapa adicionado como parte desta versão.
    `Personal character types (msdyn_personalcharactertypes)` | 1.0.0.0 | Este é um novo mapa adicionado como parte desta versão.
    `Salutations (msdyn_salutations)` | 1.0.0.0 | Este é um novo mapa adicionado como parte desta versão.
    `Employment job functions (msdyn_employmentjobfunctions)` | 1.0.0.0 | Este é um novo mapa adicionado como parte desta versão.

8. Antes de executar os mapas acima, você deve atualizar as chaves de integração manualmente, conforme descrito nas etapas a seguir. Selecione **Salvar**.

    | Mapa | Chaves |
    |-----|------|
    | Conta |  accountnumber [Account Number]<br>msdyn_company.cdm_companycode [Company (Company Code)] |
    | Contato | msdyn_contactpersonid [Account Number/Contact Person ID]<br>msdyn_company.cdm_companycode [Company (Company Code)] |
    | Contato para cliente/fornecedor | msdyn_contactforpartynumber [contato do número do participante]<br>msdyn_associatedcompanyid.cdm_companycode [empresa associada (código da empresa)] |
    | Fornecedor | msdyn_vendoraccountnumber [Número de conta do fornecedor]<br>msdyn_company.cdm_companycode [Company (Company Code)]|

9. No Dataverse, os limites de caracteres de regras de detecção de duplicidades aumentaram de 450 para 700 caracteres. Esse limite permite adicionar uma ou mais chaves às regras de detecção de duplicidades. Expanda a regra de detecção de duplicidades para a tabela **Contas**, definindo os campos a seguir.

    | Campo | Alíquota |
    |-------|-------|
    | Organização | Contas com o mesmo nome de conta. |
    | Descrição | Detecta registros de conta que têm o mesmo valor no atributo Nome da Conta. |
    | Tipo de registro básico | Conta |
    | Tipo de registro correspondente | Conta |
    | Nome da conta (campo) | Correspondência exata |
    | Empresa (campo) | Correspondência exata |
    | Tipo de relacionamento (campo) | Correspondência exata |
    | ID do participante (campo) | Correspondência exata |
    | Selecionar (campo) | (em branco) |

    ![Regra de duplicação para contas.](media/duplicate-rule-1.PNG)

10. Expanda a regra de detecção de duplicidades para a tabela **Contatos**, definindo os campos a seguir.

    | Campo | Alíquota |
    |-------|-------|
    | Organização | Contatos com o mesmo nome e sobrenome. |
    | Descrição | Detecta registros de contato que têm os mesmos valores nos campos Nome e Sobrenome. |
    | Tipo de registro básico | Contato |
    | Tipo de registro correspondente | Contato |
    | Nome (campo) | Correspondência exata |
    | Sobrenome (campo) | Correspondência exata |
    | Empresa (campo) | Correspondência exata |
    | ID do participante (campo) | Correspondência exata |
    | Selecionar (campo) | (em branco) |

    ![Regra de duplicação para contatos.](media/duplicate-rule-2.PNG)

11. Se você for um usuário de gravação dupla existente, siga as instruções em [Atualizar para o modelo de catálogo de endereços global e de participantes](upgrade-party-gab.md) e atualize seus dados. **Não prossiga para a etapa 12 sem concluir esta etapa.** Se você for um novo usuário de gravação dupla, prossiga para a etapa 12.

12. Se você for um usuário de gravação dupla existente, conclua a etapa 11 e execute os mapas na ordem a seguir. Se você for um novo cliente de gravação dupla, poderá prosseguir diretamente. Se você receber uma mensagem de erro indicando "Falha ao validar projeto. Campo de destino ausente...", abra o mapa e selecione **Atualizar Tabelas**. Depois, execute o mapa.

    Aplicativo de Finanças e Operações | Aplicativo Customer Engagement  
    ----------------------------|------------------------
    [Participantes do CDS](mapping-reference.md#220) | msdyn_parties
    [Localizações de endereço postal do CDS](mapping-reference.md#234) | msdyn_postaladdresscollections
    [Histórico de endereço postal do CDS V2](mapping-reference.md#235) | msdyn_postaladdresses
    [Localizações de endereço postal do participante do CDS](mapping-reference.md#233) | msdyn_partypostaladdresses
    [Contatos do participante V3](mapping-reference.md#236) | msdyn_partyelectronicaddresses
    [Clientes V3](mapping-reference.md#101) | contas
    [Clientes V3](mapping-reference.md#116) | contatos
    [Fornecedores V2](mapping-reference.md#202) | msdyn_vendors
    [Títulos da pessoa de contato](mapping-reference.md#223) | msdyn_salescontactpersontitles
    [Fechamentos complementares](mapping-reference.md#222) | msdyn_complimentaryclosings
    [Saudações](mapping-reference.md#228) | msdyn_salutations
    [Funções de tomada de decisão](mapping-reference.md#224) | msdyn_decisionmakingroles
    [Funções de trabalho de emprego](mapping-reference.md#225) | msdyn_employmentjobfunctions
    [Níveis de fidelidade](mapping-reference.md#226) | msdyn_loyaltylevels
    [Tipos de caracteres pessoais](mapping-reference.md#227) | msdyn_personalcharactertypes
    [Contatos V2](mapping-reference.md#221) | msdyn_contactforparties
    [Cabeçalho de cotação de venda CDS](mapping-reference.md#215) | cotações
    [Cabeçalhos de ordens de venda CDS](mapping-reference.md#217) | salesorders
    [Cabeçalhos de fatura de venda V2](mapping-reference.md#118) | faturas

> [!NOTE]
> O mapa `CDS Contacts V2 (contacts)` é o mapa interrompido na etapa 1. Ao tentar executar outros mapas, esses dois mapas podem aparecer na lista de dependentes. Não execute esses mapas.
>
> Se a solução de catálogo de endereços global e de participantes estiver instalada, você deverá desabilitar o plug-in denominado `Microsoft.Dynamics.SCMExtended.Plugins.Plugins.LeadPrimaryContactPostCreate: QualifyLead of lead`. Se você desinstalar a solução de catálogo de endereços global e de participantes, deverá reativar o plug-in.
>
> O campo `msdyn_*partynumber` (um campo de texto de linha única) incluído nas tabelas **Conta**, **Contato** e **Fornecedor** não devem ser usadas no futuro. O nome da etiqueta tem um prefixo **(Preterido)** para fins de clareza. Em vez disso, use o campo **msdyn_partyid**. O campo é uma pesquisa na tabela **msdyn_party**.

> Nome da Tabela | Campo antigo | Novo campo
> --------|-------|--------
> Conta | `msdyn_partynumber` | `msdyn_partyid`
> Contato | `msdyn_partynumber` | `msdyn_partyid`
> msdyn_vendor | `msdyn_vendorpartynumber` | `msdyn_partyid`

## <a name="templates"></a>Modelos

Um conjunto de mapas de tabelas funcionam juntos para a interação do participante com o catálogo de endereços global, conforme mostrado na tabela a seguir.

| Aplicativo de Finanças e Operações | Aplicativo Customer Engagement | Descrição |
|----------------------------|-------------------------|-------------|
| [Títulos da pessoa de contato](mapping-reference.md#223) | msdyn\_salescontactpersontitles |
| [Clientes V3](mapping-reference.md#101) | contas |
| [Clientes V3](mapping-reference.md#116) | contatos |
| [Participantes do CDS](mapping-reference.md#220) | msdyn\_parties |
| [Localizações de endereço postal do participante do CDS](mapping-reference.md#233) | msdyn\_partypostaladdresses |
| [Histórico de endereço postal do CDS V2](mapping-reference.md#235) | msdyn\_postaladdresses |
| [Localizações de endereço postal do CDS](mapping-reference.md#234) | msdyn\_postaladdresscollections |
| [Cabeçalho de cotação de venda CDS](mapping-reference.md#215) | cotações |
| [Cabeçalhos de ordens de venda CDS](mapping-reference.md#217) | salesorders |
| [Fechamentos complementares](mapping-reference.md#222) | msdyn\_complimentaryclosings |
| [Contatos V2](mapping-reference.md#221) | msdyn\_contactforparties |
| [Funções de tomada de decisão](mapping-reference.md#224) | msdyn\_decisionmakingroles |
| [Funções de trabalho de emprego](mapping-reference.md#225) | msdyn\_employmentjobfunctions |
| [Níveis de fidelidade](mapping-reference.md#226) | msdyn\_loyaltylevels |
| [Contatos do participante V3](mapping-reference.md#236) | msdyn\_partyelectronicaddresses |
| [Tipos de caracteres pessoais](mapping-reference.md#227) | msdyn\_personalcharactertypes |
| [Cabeçalhos de fatura de venda V2](mapping-reference.md#118) | faturas |
| [Saudações](mapping-reference.md#228) | msdyn\_salutations |
| [Fornecedores V2](mapping-reference.md#202) | msdyn\_vendors |

Para obter mais informações, consulte [Referência de mapeamento de gravação dupla](mapping-reference.md).

## <a name="known-issues-and-limitations"></a>Limitações e problemas conhecidos

+ Em aplicativos de Finanças e Operações, quando você cria um cliente junto com o endereço e o salva, o endereço talvez não seja sincronizado com a tabela **Endereço**. Isso ocorre devido a um problema de sequenciamento de plataforma de gravação dupla. Para solucionar o problema, crie o cliente primeiro e salve-o. Em seguida, adicione o endereço.
+ Em aplicativos de Finanças e Operações, quando um registro de cliente tem um endereço principal e você cria um novo contato para esse cliente, o registro de contato herda um endereço principal do registro de cliente associado. Isso ocorre para o contato do fornecedor. O Dataverse no momento não dá suporte a esse comportamento. Se a gravação dupla estiver habilitada, os contatos de clientes herdados com um endereço principal do aplicativo de Finanças e Operações serão sincronizados com o Dataverse junto com o endereço.
+ Os endereços eletrônicos definidos na guia endereço eletrônico dos formulários **Conta**, **Contato** e **Fornecedor** são obtidos da tabela `msdyn_partyelectronicaddress`. Essas informações não fluem para as transações associadas, como ordem de venda, cotação e ordem de compra. Pretendemos corrigir esse problema em uma versão incremental. Os dados existentes nos campos de endereço eletrônico nos registros de conta e contato continuarão a funcionar em transações como ordem de venda, cotação e ordem de compra.
+ Em aplicativos de Finanças e Operações, você pode criar um registro de contato do formulário **Adicionar Contato**. Quando você tenta criar um novo contato no formulário **Exibir Contato**, a ação falha. Este é um problema conhecido.

    ![Problema conhecido com Adicionar Contato.](media/party-gab-contact-issue.png)

+ A **sincronização inicial** não dá suporte aos campos de tempo **Disponível de** e **Disponível até** em **ContactForParty** porque DIXF converte o valor em uma cadeia de caracteres em vez de um inteiro. A conversão dispara o erro `Cannot convert the literal '<say 08:00:00>’ to the expected type edm.int32`.
+ Quando um endereço postal é usado por mais de um motivo (por exemplo, endereço de comunicação comercial e endereço de cobrança), ele deve aparecer como `Business;Invoice`, conforme mostrado na imagem a seguir. Se você adicionar um espaço entre os valores, obterá um erro.

    ![Problema conhecido com o endereço.](media/party-gab-address-issue.png)

+ Não é possível inserir um endereço postal com data posterior usando um aplicativo de Finanças e Operações com gravação dupla porque o Dataverse não dá suporte à efetivação de data. Se você inserir um endereço postal com data futura usando um aplicativo de Finanças e Operações, ele será totalmente sincronizado com o Dataverse e você verá logo o endereço na interface do usuário. Todas as atualizações deste registro resultarão em um erro, pois ele tem data futura e não atual no aplicativo de Finanças e Operações.
