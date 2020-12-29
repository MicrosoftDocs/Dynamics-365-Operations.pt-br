---
title: Configurar materiais perigosos
description: Este tópico explica como configurar os dados necessários para classificar itens como materiais perigosos. Quando você cria uma ordem de venda que inclui um item classificado como um material perigoso, o sistema gera uma documentação de materiais perigosos para essa ordem de venda quando ela é enviada.
author: dasani-madipalli
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: b049559b64045e80a40afd99bac30a9cfe1d0580
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422368"
---
# <a name="set-up-hazardous-materials"></a>Configurar materiais perigosos

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Para usar a funcionalidade de materiais perigosos, você deve primeiro configurar os dados necessários para classificar itens como materiais perigosos. Quando você cria uma ordem de venda que inclui um item classificado como um material perigoso, o sistema gera uma documentação de materiais perigosos para essa ordem de venda quando ela é enviada.

## <a name="turn-on-the-hazardous-materials-feature-for-your-system"></a>Ativar o recurso materiais perigosos para o sistema

Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Gerenciamento de informações sobre produtos*
- **Nome do recurso:** *Informações do produto e documentação de remessa sobre materiais perigosos*

## <a name="hazardous-material-regulations"></a>Regulamentações de materiais perigosos

Para usar os processos de materiais perigosos, você deve primeiro criar uma regulamentação. As regulamentações definem como o texto impresso de remessa é criado para um item. Elas também definem os modos de entrega associados.

Estas são algumas regulamentações comuns:

- **ADR** – regulamentações relacionadas ao transporte internacional de mercadorias perigosas por rodovias
- **CFR 49** – regulamentações nos Estados Unidos para o transporte de mercadorias perigosas
- **IMDG** – o código International Marine Dangerous Goods (Código Marítimo Internacional de Mercadorias Perigosas)
- **IATA** – os regulamentos de mercadorias perigosas da International Air Transport Association (Associação Internacional de Transportes Aéreos)

Essas regulamentações ajudam a determinar quais informações devem ser exibidas ao imprimir o texto de remessa de um item. É possível definir quantas regulamentações você deve cumprir.

> [!IMPORTANT]
> A funcionalidade para configurar códigos de informação relacionados a materiais perigosos não torna a empresa em conformidade com as regulamentações. Ela é apenas uma ferramenta que ajuda a criar processos para a sua empresa.

Em geral, uma regulamentação está disponível para um modo de transporte específico, como frete marítimo, frete rodoviário ou frete aéreo. Portanto, você pode associar cada regulamentação a um modo de entrega. O modo de entrega será usado quando documentos específicos forem impressos no gerenciamento de depósito. No gerenciamento de depósito, cada remessa é vinculada a uma transportadora e serviço de transportadora configurados no módulo **Transporte**. O modo de entrega é associado à transportadora e ao serviço da transportadora. Quando você executa um relatório, o modo de entrega é usado para localizar o texto impresso da remessa associado a um item liberado.

Esses dados de configuração não são específicos de cada entidade legal (empresa). Portanto, você pode ter um conjunto comum de informações de materiais perigosos que é compartilhado entre todas as entidades legais.

Para cada regulamentação, você pode definir uma lista de materiais e usá-la como uma lista de modelos associada a itens liberados. Para cada regulamentação, você também pode definir uma configuração de impressão. Uma configuração de impressão permite definir como o texto de remessa de um item é construído. A configuração de impressão é usada para construir o texto impresso da remessa para um item liberado.

Para configurar regulamentações de materiais perigosos, vá para **Gerenciamento de informações do produto \> Configuração \> Documentação de remessa de materiais perigosos \> Regulamentação de materiais perigosos**. Na página **Regulamentação de materiais perigosos**, você pode criar qualquer quantidade de regulamentações e configurar cada uma delas usando os campos descritos nas subseções a seguir.

### <a name="hazardous-material-regulation-header"></a>Cabeçalho da regulamentação de materiais perigosos

Cada regulamentação tem um código e uma descrição. A tabela a seguir descreve os campos disponíveis no cabeçalho.

| Campo | descrição |
|---|---|
| Código de regulamentação | Insira um código para identificar o registro da regulamentação de materiais perigosos. |
| descrição | Insira uma descrição da regulamentação de materiais perigosos. |

### <a name="print-setup-fasttab"></a>FastTab Configuração de impressão

Cada regulamentação pode ter qualquer quantidade de configurações de impressão. Defina as configurações de impressão na FastTab **Configuração de impressão**. A tabela a seguir descreve os campos disponíveis para cada configuração de impressão.

| Campo | descrição |
|---|---|
| Seqüência | Defina a ordem na qual os campos serão referenciados no texto de remessa. |
| Imprimir campo | Selecione o campo a ser incluído no texto de remessa. Nem todos os campos de materiais perigosos estarão disponíveis para impressão. Somente os campos comuns usados para definir o texto de remessa nas várias regulamentações estarão disponíveis. Você deve definir o primeiro campo de impressão como um separador de campo com um valor de **Sequência** como *0* (zero), para que possa ser usado como separador entre outros campos. É necessária apenas uma referência ao separador de campo.<p>Os valores a seguir estão disponíveis:</p><ul></li><li>**Separador de campo** – este campo impresso é usado como separador de campo para o texto. É necessário apenas um separador de campo na sequência. Em geral, você deve definir o valor de **Sequência** para este campo de impressão como *0* (zero). O sistema procurará um separador de campo e usará o primeiro que encontrar na lista. O valor de texto usado na cadeia de caracteres será obtido do campo **Imprimir depois**.</li><li>**Identificação** – este campo de impressão coloca o [código de identificação e/ou descrição](#identification) no texto impresso.</li><li>**Classe** – este campo de impressão coloca o [código de classe e/ou descrição](#classes) no texto impresso.</li><li>**Divisão** – este campo de impressão coloca o [código de divisão e/ou descrição](#divisions) no texto impresso.</li><li>**Grupo de embalagens** – este campo de impressão coloca o [código de grupo de embalagens e/ou descrição](#packing-group) no texto impresso.</li><li>**Código de túnel e/ou descrição** – este campo de impressão coloca o [código de túnel e/ou descrição](#tunnel) no texto impresso.</li><li>**Nome de remessa apropriado** – este campo de impressão coloca o [nome de remessa apropriado](hazmat-items.md#hazmat-description) no texto impresso.</li><li>**Nome técnico** – este campo de impressão coloca o [nome técnico e/ou descrição](#technical-name) no texto impresso.</li><li>**Categoria de transporte** – este campo de impressão coloca o [categoria de transporte e/ou descrição](#transport-category) no texto impresso.</li><li>**Acondicionamento** – este campo de impressão coloca o [código de acondicionamento e/ou descrição](#stowage) no texto impresso.</li><li>**Texto fixo** – este campo de impressão insere o texto definido no campo **Texto fixo** para essa linha.</li><li>**Código de etiqueta e/ou descrição** – este campo de impressão coloca o [código de etiqueta e/ou descrição](#label) no texto impresso.</li><li>**Embalagens para aeronaves** – este campo de impressão coloca o [código de instruções de embalagens para aeronaves e/ou descrição](#packing-instruction) no texto impresso.</li><li>**Quantidade limitada** – este campo de impressão verifica se o item está marcado como um [item de quantidade limitada](hazmat-items.md#material-management) e, se for, inserirá o texto definido no campo **Texto fixo** para essa linha.</li><li>**Descrição da embalagem** – este campo de impressão coloca a [descrição da embalagem](#packing-description) no texto impresso.</li></ul> |
| Imprimir antes | Insira o texto que deve ser impresso antes do conteúdo definido pela configuração do **campo Imprimir**. |
| Imprimir após | Insira o texto que deve ser impresso depois do conteúdo definido pela configuração do **campo Imprimir**. |
| Imprimir com anterior | Marque esta caixa de seleção para impedir que o separador de campos seja impresso entre o campo anterior e este campo. Use esta caixa de seleção para imprimir campos opcionais ou incluídos em outro campo de impressão. |
| Texto fixo | Se você definir o **campo Imprimir** como **Texto fixo** ou **Quantidade limitada**, insira o texto que deve ser impresso. |
| Incluir na impressão | Selecione um ou mais valores do campo de impressão selecionado que devem ser impressos para esta linha. Você pode imprimir o código, a descrição ou ambos. |

### <a name="mode-of-delivery-fasttab"></a>FastTab Modo de entrega

A regulamentação é uma tabela compartilhada e não é específica de cada entidade legal. No entanto, os modos de entrega são específicos da entidade legal. Portanto, ao configurar um modo de entrega, você deve selecionar o relacionamento entre a regulamentação, a entidade legal e o modo de entrega.

A tabela a seguir descreve os campos disponíveis na FastTab **Modo de entrega**.

| Campo | descrição |
|---|---|
| Empresa | Selecione uma entidade legal para associar a essa regulamentação. |
| Modo de entrega | Com base na entidade legal selecionada, selecione o modo de entrega que deve ser associado à regulamentação. |

### <a name="country-fasttab"></a>FastTab País

Para fins de referência, você pode listar os países ou regiões para os quais a regulamentação é relevante. No entanto, quando os relatórios de remessa são executados, somente o modo de entrega é usado para determinar a regulamentação. Quando você revisa uma remessa de depósito, não há um link direto para o modo de entrega. A remessa pode ser associada a uma transportadora e a um serviço da transportadora. Ao definir um serviço da transportadora, você deve associá-lo a um modo de entrega. Esse relacionamento será usado em relatórios de remessa, como o conhecimento de embarque para localizar o texto impresso de remessa de um item.

A tabela a seguir descreve o campo disponível na FastTab **País**.

| Campo | descrição |
|---|---|
| País/região | Selecione um país/região para associar à regulamentação. |

## <a name="material-codes"></a><a name="hazmat-codes"></a>Códigos de material

Os códigos de material estabelecem configurações relacionadas a um componente perigoso específico que pode ser incluído em um produto liberado. Cada código de material pertence a uma regulamentação específica de materiais perigosos e sua definição deve cumprir essa regulamentação. Quando você aplica um código de material a um produto liberado usando o campo **Código de material**, todas as configurações de materiais perigosos do código de material são aplicadas automaticamente ao produto. Portanto, o processo de configuração de produtos liberados é mais rápido e menos propenso a erros.

Para gerenciar suas definições de materiais perigosos, siga estas etapas.

1. Vá para **Gerenciamento de informações do produto \> Configuração \> Documentação de remessa de materiais perigosos \> Regulamentação de materiais perigosos**.
2. Selecione a regulamentação para configurar uma definição de materiais perigosos.
3. No Painel de Ações, na guia **Configuração**, selecione **Materiais perigosos**.
4. No campo **Código de material**, insira um código de material para a definição de materiais perigosos. Você selecionará este valor ao aplicar o código de material a um produto liberado.

    O campo **Código de regulamentação** é somente leitura e mostra a regulamentação selecionada na etapa 2.

5. Use os campos restantes desta página para criar e configurar cada material perigoso que se aplica à regulamentação selecionada. Os campos disponíveis são um subconjunto dos campos de materiais perigosos que estão disponíveis para produtos individuais liberados. Para obter mais informações, consulte [Materiais perigosos em produtos, ordens, remessas e cargas](hazmat-items.md).

## <a name="hazardous-material-classification-groups"></a><a name="classification-groups"></a>Grupos de classificação de materiais perigosos

Cada grupo de classificação de materiais perigosos define um grupo de valores de campo que definem um modelo. Você pode usar esse modelo posteriormente, quando configurar informações de materiais perigosos para um item liberado.

Quando você atribuir o código de um grupo de classificação de materiais perigosos a um item liberado, as informações associadas a esse grupo de classificação serão copiadas para os campos adequados do item. Portanto, para simplificar os processos de configuração, defina um conjunto de valores de campo relacionados que costuma usar juntos.

Esses dados de configuração não são específicos de cada entidade legal. Portanto, você pode ter um conjunto comum de informações de materiais perigosos que é compartilhado entre todas as entidades legais.

Para configurar grupos de classificação de materiais perigosos, vá para **Gerenciamento de informações do produto \> Configuração \> Documentação de remessa de materiais perigosos \> Grupo de classificação de materiais perigosos**. Na página **Grupo de classificação de materiais perigosos**, você pode criar qualquer quantidade de grupos e configurar cada um deles usando os campos descritos na tabela a seguir.

| Campo | descrição |
|---|---|
| Código do grupo | Insira um código para identificar o grupo. |
| descrição | Insira uma descrição do grupo. |
| Código de classe | Associe um [código de classe](#classes) de materiais perigosos ao grupo. |
| Código de divisão | Associe um [código de divisão](#divisions) de materiais perigosos ao grupo. |
| Código de grupo de embalagens | Associe um [código de grupo de embalagens](#packing-group) ao grupo. |
| Código da categoria de transporte | Associe um [código de categoria de transporte](#transport-category) ao grupo. |
| Multiplicador | Insira o multiplicador de materiais perigosos que se aplica à classe selecionada e à divisão de materiais perigosos, de acordo com a regulamentação aplicável. Esse multiplicador é usado como parte da fórmula que calcula o total de *pontos de materiais perigosos* incluídos em uma carga ou remessa. Para obter mais informações sobre pontos de materiais perigosos e esse multiplicador, consulte [FastTab Gerenciamento de material](hazmat-items.md#material-management). |

## <a name="hazardous-material-classes"></a><a name="classes"></a>Classes de materiais perigosos

Geralmente, uma classe de material perigoso é mapeada para a lista de classes fornecida na regulamentação que você cumpre. Por exemplo, a regulamentação dos EUA da CFR 49 lista "classe 3" como líquidos inflamáveis e combustíveis. Você pode configurar as classes que são relevantes para os materiais que devem ser classificados.

Cada classe será atribuída a uma configuração de material na lista de materiais relacionada à regulamentação. Você atribuirá uma classe a cada item liberado, conforme necessário, para descrever a natureza perigosa de um produto.

Esses dados de configuração não são específicos de cada entidade legal. Portanto, você pode ter um conjunto comum de informações de materiais perigosos que é compartilhado entre todas as entidades legais.

As classes de materiais perigosos funcionam em conjunto com divisões, grupos e grupos de compatibilidade da seguinte maneira:

- Ao atribuir uma classe de material perigoso a um item liberado, você também deve atribuir uma [divisão de material perigoso](#divisions).
- Você pode usar classes de materiais perigosos em conjunto com [grupos de classificação de materiais perigosos](#classification-groups) para estabelecer um modelo de códigos para a configuração de itens.
- Você pode usar [grupos de compatibilidade de materiais perigosos](#compatibility-groups) para estabelecer quais classes e divisões de materiais perigosos podem ser enviadas juntas.

Para configurar classes de materiais perigosos, vá para **Gerenciamento de informações do produto \> Configuração \> Documentação de remessa de materiais perigosos \> Classe de materiais perigosos**. Na página **Classe de materiais perigosos**, você pode criar qualquer quantidade de classes e configurar cada uma delas usando os campos descritos na tabela a seguir.

| Campo | descrição |
|---|---|
| Código de classe | Insira um código para identificar esta classe. Você define esse código para o item. Em seguida, ele será usado em listas de pesquisa quando você atribuir uma classe de materiais perigosos a um item liberado. |
| descrição | Insira uma descrição da classe. |

## <a name="hazardous-material-divisions"></a><a name="divisions"></a>Divisões de materiais perigosos

Uma divisão de materiais perigosos é um subconjunto de uma classe de materiais perigosos. Você deve atribuir uma divisão e uma classe a cada produto que inclui materiais perigosos.

Para classes que não têm divisões, crie uma divisão na qual o código é *0*. Por exemplo, na regulamentação da IATA, materiais radioativos de classe 7 não têm subdivisões. Nesse caso, você criará uma divisão *0* que poderá associar a um produto liberado quando atribuir a classe.

Esses dados de configuração não são específicos de cada entidade legal. Portanto, você pode ter um conjunto comum de informações de materiais perigosos que é compartilhado entre todas as entidades legais.

As divisões de materiais perigosos funcionam em conjunto com classes, grupos e grupos de compatibilidade das seguintes maneiras:

- Ao atribuir uma divisão de material perigoso a um item liberado, você também deve atribuir uma [classe de material perigoso](#classes).
- Você pode usar divisões de materiais perigosos em conjunto com [grupos de classificação de materiais perigosos](#classification-groups) para estabelecer um modelo de códigos para a configuração de itens.
- Você pode usar [grupos de compatibilidade de materiais perigosos](#compatibility-groups) para estabelecer quais classes e divisões de materiais perigosos podem ser enviadas juntas.

Para configurar divisões de materiais perigosos, vá para **Gerenciamento de informações do produto \> Configuração \> Documentação de remessa de materiais perigosos \> Divisão de materiais perigosos**. Na página **Divisão de materiais perigosos**, você pode criar qualquer quantidade de divisões e configurar cada uma delas usando os campos descritos na tabela a seguir.

| Campo | descrição |
|---|---|
| Divisão | Insira um código a ser usado como um número de referência para a divisão. |
| descrição | Insira uma descrição da divisão. |
| Classe | Pesquise e atribua a classe à qual a divisão pertence. |

## <a name="hazardous-material-compatibility-groups"></a><a name="compatibility-groups"></a>Grupos de compatibilidade de materiais perigosos

Grupos de compatibilidade de materiais perigosos estabelecem quais classes e divisões de materiais perigosos podem ser enviadas juntas. Quando os operadores criarem cargas ou remessas de depósito, eles poderão executar uma verificação de compatibilidade que emitirá um aviso se a carga ou a remessa incluir itens que não pertençam a mesmo grupo de compatibilidade.

Esses dados de configuração não são específicos de cada entidade legal. Portanto, você pode ter um conjunto comum de informações de materiais perigosos que é compartilhado entre todas as entidades legais.

Para configurar grupos de compatibilidade de materiais perigosos, vá para **Gerenciamento de informações do produto \> Configuração \> Documentação de remessa de materiais perigosos \> Grupo de compatibilidade de materiais perigosos**. Na página **Grupo de compatibilidade de materiais perigosos**, você pode criar qualquer quantidade de grupos de compatibilidade e configurar cada uma delas usando os campos descritos nas subseções a seguir.

### <a name="hazardous-material-compatibility-group-header"></a>Cabeçalho de grupos de compatibilidade de materiais perigosos

Cada grupo de compatibilidade tem um código e uma descrição. A tabela a seguir descreve os campos disponíveis no cabeçalho.

| Campo | descrição |
|---|---|
| Grupo de compatibilidade | Inserir um código para identificar o grupo de compatibilidade |
| descrição | Insira uma descrição do grupo de compatibilidade. |

### <a name="compatibility-group-details"></a>Detalhes do grupo de compatibilidade

Cada grupo de compatibilidade estabelece uma lista de classes e divisões de materiais perigosos que podem ser enviados juntos.

| Campo | descrição |
|---|---|
| Classe | Selecione uma classe de materiais perigosos que seja compatível com todas as outras classes do grupo. |
| Divisão | Selecione uma divisão de materiais perigosos que pertença à classe selecionada. |

## <a name="hazardous-material-specification-values"></a>Valores de especificação de materiais perigosos

O Microsoft Dynamics 365 Supply Chain Management fornece vários tipos de especificações de materiais perigosos. Para cada tipo, você deve estabelecer um conjunto centralizado de valores para cada campo relevante. Os usuários podem selecionar entre esses valores quando configuram definições de materiais perigosos ou produtos liberados. O Supply Chain Management fornece um conjunto de páginas nas quais você pode estabelecer os valores. Cada página é dedicada a um tipo de especificação. Para obter uma descrição de cada especificação disponível e informações sobre como estabelecer os valores disponíveis para ela, consulte as subseções a seguir.

Um exemplo de uma especificação de materiais perigosos é o _código de acondicionamento_, que especifica como determinado material pode ser armazenado durante o transporte. Usando as informações desta seção, você estabelecerá uma coleção central de códigos de acondicionamento. Essa coleção será, então, apresentada aos usuários em uma lista suspensa quando eles definirem o código de acondicionamento para um produto liberado.

Esses valores de especificação de materiais perigosos não são específicos de cada entidade legal. Portanto, você pode ter um conjunto de valores comuns que são compartilhados entre todas as entidades legais.

Você usará [códigos de material](#hazmat-codes) para estabelecer coleções comuns de configurações para cada especificação conforme aplicação a determinada regulamentação. Você pode aplicar o código apropriado a cada produto liberado, conforme necessário. Para obter informações sobre como aplicar um código de materiais perigosos a um produto liberado específico e como definir configurações individuais desse produto para qualquer especificação descrita aqui, consulte [Materiais perigosos em produtos, ordens, remessas e cargas](hazmat-items.md).

### <a name="hazardous-material-emergency-response"></a>Resposta de emergência de materiais perigosos

A especificação de *Resposta de emergência de materiais perigosos* indica o que deverá ser feito se algo der errado durante o transporte de um produto contendo determinado material perigoso.

Para configurar valores para esta especificação, vá para **Gerenciamento de informações do produto \> Configuração \> Documentação de remessa de materiais perigosos \> Resposta de emergência de materiais perigosos**. Na página **Resposta de emergência de materiais perigosos**, você pode criar qualquer quantidade de valores e configurar cada um com um código de classificação e uma breve descrição.

### <a name="hazardous-material-identification"></a><a name="identification"></a>Identificação de material perigoso

A especificação *Identificação de materiais perigosos* identifica a classe ou a natureza de um material perigoso. O valor costuma ser um código que se baseia em um padrão das Nações Unidas (ONU). Cada classe é identificada por um código e uma descrição, e pode definir limites para os métodos de transporte. Por exemplo, para identificar um material ou item inflamável, crie uma classe de materiais perigosos que use o código *FL* e a descrição *Inflamável*. Também é possível especificar que a classe não deve ser transportada pelo ar.

Para configurar valores para esta especificação, vá para **Gerenciamento de informações do produto \> Configuração \> Documentação de remessa de materiais perigosos \> Identificação de materiais perigosos**. Na página **Identificação de materiais perigosos**, você pode criar qualquer quantidade de valores e configurar cada um deles usando os campos descritos na tabela a seguir.

| Campo | descrição |
|---|---|
| Identificação | Insira um código a ser usado como um número de referência que identifique essa classe de materiais perigosos. |
| descrição | Insira uma descrição dessa classe. |
| Restringir de transporte aéreo | Marque esta caixa de seleção para indicar que essa classe de materiais perigosos não deve ser transportada pelo ar. |
| Restringir de transporte marítimo | Marque esta caixa de seleção para indicar que essa classe de materiais perigosos não deve ser transportada pelo mar. |

### <a name="hazardous-material-label"></a><a name="label"></a>Etiqueta de material perigoso

A especificação *Etiqueta de material perigoso* identifica a etiqueta de mercadorias perigosas que deve ser aplicada a produtos liberados relevantes. As etiquetas em si descreverão como o produto deve ser manipulado. Por exemplo, você tem um produto que contém um gás venenoso. Nesse caso, você configura um código de etiqueta que representa a etiqueta de gás venenoso. Você também cria seu processo empresarial para que ele pesquise esse valor quando você enviar produtos.

Para configurar valores para esta especificação, vá para **Gerenciamento de informações do produto \> Configuração \> Documentação de remessa de materiais perigosos \> Etiqueta de materiais perigosos**. Na página **Etiqueta de materiais perigosos**, você pode criar qualquer quantidade de etiquetas e configurar cada uma com um código de identificação e uma breve descrição.

### <a name="hazardous-material-packing-descriptions"></a><a name="packing-description"></a>Descrições de embalagem de material perigoso

A especificação *Descrições de embalagens de materiais perigosos* indica como um item perigoso deve ser embalado. Por exemplo, talvez ele precise ser embalado em um tipo específico de tambor de aço ou outro tipo de embalagem especial.

Para configurar valores para esta especificação, vá para **Gerenciamento de informações do produto \> Configuração \> Documentação de remessa de materiais perigosos \> Descrições de embalagens de materiais perigosos**. Na página **Descrições de embalagens de materiais perigosos**, você pode criar qualquer quantidade de descrições de embalagens e configurar cada uma com um código de identificação e uma breve descrição.

### <a name="hazardous-material-packing-group"></a><a name="packing-group"></a>Grupo de embalagens de material perigoso

A especificação *Grupo de embalagens de materiais perigosos* identifica o grupo de embalagens de um item perigoso. O grupo de embalagens permite definir um código e uma descrição para indicar como os itens de materiais perigosos devem ser embalados durante o transporte ou a remessa. O grupo de embalagens é atribuído ao item por meio da página **Materiais perigosos do item**.

Para configurar valores para esta especificação, vá para **Gerenciamento de informações do produto \> Configuração \> Documentação de remessa de materiais perigosos \> Grupo de embalagens de materiais perigosos**. Na página **Grupo de embalagens de materiais perigosos**, você pode criar qualquer quantidade de grupos de embalagens e configurar cada uma com um código de identificação e uma breve descrição.

### <a name="hazardous-material-packing-instruction"></a><a name="packing-instruction"></a>Instruções de embalagem de material perigoso

A especificação *Instrução de embalagem de materiais perigosos* identifica as instruções de embalagem que devem ser seguidas quando determinado item perigoso é preparado para transporte pelo ar.

Para configurar valores para esta especificação, vá para **Gerenciamento de informações do produto \> Configuração \> Documentação de remessa de materiais perigosos \> Instrução de embalagens de materiais perigosos**. Na página **Instrução de embalagens de materiais perigosos**, você pode criar qualquer quantidade de identificadores de instruções de embalagens e configurar cada um com um código de identificação e uma breve descrição.

### <a name="hazardous-material-stowage"></a><a name="stowage"></a>Estiva de material perigoso

A especificação *Acondicionamento de materiais perigosos* indica como um produto deve ser armazenado em um navio quando ele é transportado por frete marítimo.

Para configurar valores para esta especificação, vá para **Gerenciamento de informações do produto \> Configuração \> Documentação de remessa de materiais perigosos \> Acondicionamento de materiais perigosos**. Na página **Acondicionamento de materiais perigosos**, você pode criar qualquer quantidade de identificadores de acondicionamento e configurar cada um com um código de identificação e uma breve descrição.

### <a name="hazardous-material-transport-category"></a><a name="transport-category"></a>Categoria de transporte de material perigoso

A especificação *Categoria de transporte de materiais perigosos* costuma ser usada para agrupar produtos perigosos semelhantes em relatórios. Por exemplo, as categorias de transporte são usadas no relatório **Resumo de remessa**, que pode ser impresso no registro de remessa do depósito.

Para configurar valores para esta especificação, vá para **Gerenciamento de informações do produto \> Configuração \> Documentação de remessa de materiais perigosos \> Categoria de transporte de materiais perigosos**. Na página **Categoria de transporte de materiais perigosos**, você pode criar qualquer quantidade de categorias de transporte e configurar cada uma com um nome de exibição e uma breve descrição.

### <a name="hazardous-material-technical-name"></a><a name="technical-name"></a>Nome técnico do material perigoso

A especificação *Nome técnico de materiais perigosos* pode ser usada para fornecer um nome da empresa usado com frequência ou interno que descreve cada material.

Para configurar valores para esta especificação, vá para **Gerenciamento de informações do produto \> Configuração \> Documentação de remessa de materiais perigosos \> Nome técnico de materiais perigosos**. Na página **Nome técnico de materiais perigosos**, você pode criar qualquer quantidade de nomes técnicos e configurar cada um com um nome de exibição e uma breve descrição.

### <a name="hazardous-material-tunnel"></a><a name="tunnel"></a>Túnel de material perigoso

A especificação *Túnel de materiais perigosos* limita os tipos de túneis em que um material perigoso pode ser transportado, identificando os tipos de túneis que devem ser usados. As categorias de túnel são estabelecidas pelas regulamentações aplicáveis para o transporte de materiais perigosos. Esta especificação em geral se aplica apenas ao transporte rodoviário.

Para configurar valores para esta especificação, vá para **Gerenciamento de informações do produto \> Configuração \> Documentação de remessa de materiais perigosos \> Túnel de materiais perigosos**. Na página **Túnel de materiais perigosos**, você pode criar qualquer quantidade de identificadores de túnel e configurar cada um com um código de identificação e uma breve descrição.
