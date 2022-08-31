---
title: Códigos de barras de GS1
description: Este artigo descreve como configurar códigos de barras de GS1 e códigos QR para que os rótulos possam ser digitalizados em um depósito.
author: Mirzaab
ms.date: 03/21/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: e1c1c274054ed1c14c9b3fc0595baa029bf3124d
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336355"
---
# <a name="gs1-bar-codes"></a>Códigos de barras de GS1

[!include [banner](../includes/banner.md)]

Geralmente, os trabalhadores de depósito precisam concluir várias tarefas quando usam um scanner de dispositivo móvel para registrar movimentos de um item, uma paleta ou um contêiner. Essas tarefas podem incluir os códigos de barra de verificação e a inserção manual das informações no dispositivo móvel. Os códigos de barras usam um formato específico da empresa que você define e gerencia usando o Microsoft Dynamics 365 Supply Chain Management.

Os códigos de barras de GS1 foram desenvolvidos para fornecer um padrão global para a troca de dados entre empresas. Eles estão disponíveis em simbologias lineares (1D) (formatos de código de barras), como GS1-128, e simbologias 2D, como DataMatrix de GS1 e códigos QR de GS1. Os códigos de barras de GS1 não só codificam os dados, mas também permitem usar uma lista predefinida de *identificadores de aplicativos* para definir o significado desses dados. O padrão GS1 define o formato dos dados e os vários tipos de dados que podem ser usados para codificar. Ao contrário dos padrões mais antigos de códigos de barras, os códigos de barras de GS1 podem ter vários elementos de dados. Portanto, uma única verificação de código de barras pode capturar vários tipos de informações sobre o produto, como o lote e a data de vencimento.

O suporte GS1 no Supply Chain Management simplifica muito o processo de digitalização em depósitos nos quais paletes e contêineres são rotulados usando códigos de barras no formato GS1. Os trabalhadores de depósito podem extrair todas as informações necessárias através de uma única verificação de um código de barras de GS1. Ao eliminar a necessidade de realizar várias varreduras e/ou inserir manualmente as informações, os códigos de barras GS1 ajudam a reduzir o tempo associado às tarefas. Ao mesmo tempo, elas também ajudam a melhorar a precisão.

Os gerentes de logística devem configurar a lista necessária de identificadores de aplicativos e associá-los aos itens de menu de dispositivo móvel apropriados. Os identificadores de aplicativo podem ser usados em todos os depósitos como uma configuração global para fins de movimentação e de embalagem. Portanto, todas as etiquetas de remessa terão um formulário unificado.

A menos que especificado de outra forma, este artigo usa o termo *código de barras* para se referir a códigos de barras lineares (1D) e 2D.

## <a name="the-gs1-bar-code-format"></a>O formato do código de barras de GS1

As especificações gerais de GS1 determinam quais simbologias podem ser usadas em códigos de barras de GS1 e como codificar os dados no código de barras. Esta seção fornece uma breve introdução ao artigo. Para ver todos os detalhes, consulte as [especificações gerais de GS1](https://www.gs1.org/docs/barcodes/GS1_General_Specifications.pdf) publicadas por GS1. O documento especificações de GS1 é atualizado regularmente, e as informações fornecidas estão atualizadas com a versão 22.0 das Especificações gerais de GS1.

Os códigos de barras de GS1 usam as seguintes simbologias:

- **Códigos de barras linear ou 1D**: GS1-128 e GS1 DataBar
- **códigos de barras 2D**: GS1 DataMatrix, código QR de GS1 e GS1 Dotcode

Há menções especiais de GS1 em GS1-128, que é um caso especial do código de barras linear comum Code-128, GS1 DataMatrix e código QR de GS1. A diferença entre a versão GS1 e a versão não GS1 é a presença de um caractere especial (FNC1) como o primeiro caractere nos dados do código de barras. A presença de um caractere FNC1 indica que os dados no código de barras devem ser interpretados de acordo com a especificação de GS1.

Os dados no próprio código de barras consistem em vários elementos de dados, sendo que cada um deles é identificado por um identificador de aplicativo no início do campo. Normalmente, os dados também são apresentados sob o código de barras em um formato legível por humanos, em que o identificador do aplicativo é mostrado entre parênteses. Este é um exemplo: `(01) 09521101530001 (17) 210119 (10) AB-123`. Esse código de barras contém três elementos:

- **Identificador de aplicativo 01**: o GTIN (Número global de item comercial) de GS1 do item.
- **Identificador do aplicativo 17**: a data de vencimento.
- **Identificador de aplicativo 10**: o número do lote.

Para cada elemento, os dados podem ter um tamanho predefinido ou variável. Há uma lista fixa de identificadores de aplicativo com tamanhos predefinidos. Todos os outros identificadores de aplicativos têm tamanho variável, e a lista de identificadores de aplicativos de GS1 especifica o tamanho máximo e o formato dos dados. Por exemplo, o identificador de aplicativo 01 tem um tamanho pré-definido de 16 caracteres (dois para o próprio identificador de aplicativo e, em seguida, 14 para o GTIN), e o identificador do aplicativo 17 tem um comprimento predefinido de oito caracteres (dois para o próprio identificador de aplicativo e, em seguida, seis para a data). No entanto, o identificador de aplicativo 10 tem dois números para o próprio identificador de aplicativo e, em seguida, até 20 caracteres alfanuméricos.

Quando elementos são agrupados, se um elemento segue um elemento de comprimento variável, um caractere separador deve ser usado. Esse separador pode ser o caractere FNC1 especial ou o caractere separador de grupo (um caractere não imprimível que tem um código ASCII 29 e um código hexadecimal 1D). O separador não deve ser usado após o último elemento. Embora o separador também não deva ser usado após elementos com tamanho predefinido, sua presença não é um erro crítico.

Nos dados do código de barras do exemplo anterior de um código de barras que contém os identificadores de aplicativo 01, 17 e 10, os dados em um código QR Code-128 ou um símbolo DataMatrix serão codificados como `<FNC1>`**`01`**`09521101530001`**`17`**`210119`**`10`**`AB-123` (identificadores de aplicativos são mostrados em negrito). Como prática recomendada, qualquer elemento com comprimento variável deve ser colocado no final para eliminar a necessidade de um caractere separador de grupo adicional. No entanto, o código de barras também pode ter uma ordem diferente de elementos, na qual o separador é obrigatório. Este é um exemplo: `<FNC1>`**`01`**`09521101530001`**`10`**`AB-123<GS>`**`17`**`210119`.

### <a name="dates-and-decimal-numbers"></a>Datas e números decimais

As datas são sempre representadas no formato *AAMMDD*, onde o século do ano é determinado pelas especificações de GS1. Somente as datas de 49 anos no passado para 50 anos no futuro (em relação ao ano atual) podem ser representadas.

Alguns elementos de dados contêm números decimais. Por exemplo, os identificadores de aplicativo 3100, 3101, ... 3105 representam um peso líquido em quilogramas. Como esses identificadores de aplicativos têm um comprimento pré-definido de 10, seis números estão disponíveis para a quantidade. A posição do ponto decimal é especificada pelo último número do identificador do aplicativo. Portanto, essa família de identificadores de aplicativos também pode ser representada como *310n*. Como o padrão de GS1 especifica que deve haver sempre pelo menos um número à esquerda da vírgula decimal, é permitido um máximo de cinco casas decimais.

Veja alguns exemplos que mostram como o número *123456* será interpretado por diferentes identificadores de aplicativos (mostrados em negrito):

- **`3100`**`123456` &rarr; 123456 (inteiro)
- **`3101`**`123456` &rarr; 12345,6 (uma casa decimal)
- **`3102`**`123456` &rarr; 1234,56 (duas casas decimais)
- **`3103`**`123456` &rarr; 123,456 (três casas decimais)
- **`3104`**`123456` &rarr; 12,3456 (quatro casas decimais)
- **`3105`**`123456` &rarr; 1,23456 (cinco casas decimais)

## <a name="scanning-gs1-bar-codes-in-supply-chain-management"></a>Lendo códigos de barras de GS1 no Supply Chain Management

Para ler códigos de barras de GS1, os operadores de depósito usam um scanner integrado ou conectado a um dispositivo móvel. O scanner transmite o código de barras lido para o aplicativo móvel Warehouse Management como uma série de eventos de teclado. Esse modo de operação também é conhecido como *leitura do teclado* ou *leitura*. O aplicativo móvel envia o texto recebido como está para o Supply Chain Management. Quando o sistema recebe dados de entrada, ele primeiro determina se os dados começam com um dos prefixos configurados que indicam que os dados são um código de barras de GS1 (consulte a seção [Configurar opções de GS1 globais](#set-gs1-options)). Se os dados lidos começarem com um desses prefixos, o sistema usará um analisador de GS1 para analisar os dados e extrair elementos de dados individuais de acordo com seus identificadores de aplicativo. Depois que os dados tiverem sido analisados, o campo de entrada atual ou vários campos serão preenchidos com os dados digitalizados.

### <a name="configuration-of-bar-code-scanner-hardware-and-software"></a>Configuração de hardware e software do scanner de código de barras

Para que o Supply Chain Management reconheça e decodifique corretamente códigos de barras de GS1, o scanner de hardware ou o software de suporte deve ser configurado para realizar as seguintes ações:

- Adicione um prefixo aos códigos de barras lidos para que o sistema possa reconhecer um código de barras de GS1.
- Converta o caractere separador de grupo ASCII não imprimível (código ASCII 29 ou código hexadecimal 1D) para um caractere imprimível, como um til (~).

Embora seja possível adicionar qualquer prefixo ao código de barras lido, uma opção é adicionar um identificador de simbologia ISO/IEC 15424, também conhecido como um *identificador de AIM*. Esse identificador de três caracteres começa com `]`, tem um caractere que identifica a simbologia usada e, em seguida, tem um número que é usado como um modificador adicional. Por exemplo, o identificador de AIM `]C1` especifica um código de barras de Código 128 (por causa do caractere `C`) e o modificador `1` especifica que há um caractere FNC1 na primeira posição dos dados. Por outro lado, `]C0` é um código de barras de Código 128 que tem qualquer outro caractere como o primeiro caractere dos dados.

Os cinco identificadores de simbologia a seguir correspondem aos códigos de barras de GS1 que têm elementos identificadores de aplicativos:

- `]C1`: Código 128 (`C`) com o caractere FNC1 na primeira posição (`1`), também conhecido como GS1-128.
- `]e0`: GS1 DataBar.
- `]d2`: DataMatrix (`d`) com ECC 200 e FNC1 na primeira posição (`2`), também conhecido como DataMatrix GS1.
- `]Q3`: Símbolo de modelo 2 de código QR (`Q`) com FNC1 na primeira posição (`3`), também conhecido como código QR de GS1.
- `]J1`: GS1 DotCode.

Se você usar esses identificadores, a compatibilidade com códigos de barras não GS1 exigirá que os scanners ou o software de leitura sejam configurados para remover os identificadores que não correspondem aos identificadores de GS1. Por exemplo, ao ler um código de barras de código 39 "normal", o prefixo `]A0` será adicionado. Como o sistema não compreenderá esse prefixo como um dos prefixos de GS1, ele irá interpretá-lo como dados e produzirá resultados inesperados.

> [!NOTE]
> Por conveniência, a versão 2.0.17.0 e posteriores do aplicativo móvel Warehouse Management removerá todos os prefixos do AIM que não estejam incluídos na lista anterior. Esse comportamento oferece suporte a casos em que você pode configurar o mecanismo de leitura para adicionar o prefixo AIM, mas não para remover os prefixos indesejados.

### <a name="single-and-multiple-field-scanning"></a>Leitura de campo único e múltiplo

Depois que os dados tiverem sido analisados do código de barras, eles serão inseridos nos controles de fluxo do dispositivo móvel. Há dois métodos que serão processados:

- **Leitura de campo único**: esse método preenche somente o campo no qual o código de barras foi lido. Por exemplo, ao ler o código de barras `<FNC1>`**`01`**`09521101530001`**`17`**`210119`**`10`**`AB-123` enquanto o cursor estiver no campo **Item**, o GTIN `09521101530001` do código de barras será inserido nesse campo. Ao ler o mesmo código de barras enquanto o cursor estiver no campo **Id do lote**, o número do lote `AB-123` do código de barras será inserido. Esse modo funciona para todos os campos em todos os fluxos e requer apenas que a definição genérica de GS1 seja configurada. Se um código de barras contiver vários elementos, ele ainda deverá ser lido várias vezes, porque somente um código de barras por vez será inserido no fluxo do dispositivo móvel. Esse comportamento é controlado pela configuração genérica de GS1, conforme descrito na seção [Estabelecer a configuração genérica de GS1](#generic-gs1-setup).
- **Leitura de campo múltiplo**: esse método preenche vários campos quando um código de barras é lido, enviando dados adicionais para o estado de fluxo do dispositivo móvel. Por exemplo, a política é configurada para enviar o identificador de aplicativo 01 para o controle `ItemId` e o identificador de aplicativo 10 para o campo `InventBatchId`. Nesse caso, ao ler o código de barras `<FNC1>`**`01`**`09521101530001`**`17`**`210119`**`10`**`AB-123`, os dados de ambas as variáveis serão enviados ao mesmo tempo. Portanto, o sistema não solicitará o número do item e/ou do lote no fluxo. Esse comportamento é controlado por políticas de GS1 vinculadas a itens de menu, conforme descrito na seção [Configurar políticas de GS1 para serem enviadas a itens de menu de dispositivo móvel](#policies-for-menus).

> [!WARNING]
> As políticas de GS1 padrão foram testadas para funcionar sem comportamentos inesperados. No entanto, a personalização de políticas de GS1 vinculadas a itens de menu pode causar um comportamento inesperado, pois o fluxo pode não esperar que alguns dados estejam disponíveis em um momento específico.

## <a name="turn-on-the-gs1-feature"></a>Ativar o recurso GS1

Para poder usar esse recurso, você deve habilitá-lo para o seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Gerenciamento de depósito*
- **Nome do recurso:** *Verificar códigos de barras de GS1*

### <a name="turn-on-the-enhanced-parser-for-gs1-barcodes-feature"></a>Ativar o Analisador avançado para o recurso de códigos de barras de GS1

Se usar códigos de barras de GS1, recomendamos que você também ative o recurso *Analisador aprimorado de códigos de barra GS1*. Esse recurso oferece uma implementação aprimorada do analisador de código de barras de GS1. Ele acrescenta os seguintes aperfeiçoamentos:

- Ele segue o algoritmo de especificação geral de GS1 para a análise de dados de símbolo e valida os dados no símbolo de acordo com a especificação.
- Não é necessário configurar um valor de **Tamanho máximo do identificador** e usar correspondência de prefixo mais longa a partir de identificadores de aplicativo configurados.
- Ele permite configurar mais facilmente identificadores de aplicativos decimais usando a letra *n* para coincidir com qualquer número. Por exemplo, você pode configurar apenas um identificador de aplicativo (*310n*) em vez de identificadores de aplicativos separados (*3101*, *3102*, *3103* e assim por diante).
- Ele corrige um problema no qual dados codificados incorretamente são interpretados como dados de campo.
- Ele é uma classe separada que pode ser reutilizada em outros contextos e permite que um ponto de extensibilidade seja usado para manipular dados lidos antes que os campos de fluxo sejam preenchidos.

## <a name="set-up-global-gs1-options"></a><a name="set-gs1-options"></a>Configurar opções de GS1 globais

A página **Parâmetros de gerenciamento de depósito** fornece algumas configurações que estabelecem opções de GS1 globais.

Para configurar as opções de GS1 globais, siga estas etapas.

1. Acesse **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**.
1. Na Guia Rápida **Códigos de barras**, defina os seguintes campos:

    - **Caractere de FNC1**, **Caractere DataMatrix** e **Caractere de código QR**: especifique caracteres que devem ser interpretados como um prefixo para cada tipo de GS1 código de barras.
    - **Separador de grupo**: especifique o caractere que substitui o caractere separador de grupo ASCII.
    - **Tamanho máximo do identificador** – especifique o número máximo de caracteres permitido para o identificador do aplicativo. Este campo não será obrigatório se o recurso *Analisador aprimorado de GS1* estiver ativado para seu sistema.

> [!NOTE]
> Os prefixos informam ao sistema que um código de barras é codificado, de acordo com o padrão GS1. Até três prefixos (**caractere de FNC1**, **caractere de Datamatrix** e **caractere de código QR**) podem ser usados simultaneamente e para vários fins.

## <a name="gs1-application-identifiers"></a>Identificadores de aplicativo GS1

Os formatos de GS1 não só codificam os dados, mas também permitem usar uma lista predefinida de identificadores de aplicativos para definir o significado dos dados. Os gerentes de logística devem configurar a lista necessária de identificadores de aplicativos e associá-los aos itens de menu de dispositivo móvel apropriados. Os identificadores podem ser usados em todos os depósitos como uma configuração global para fins de movimentação e de embalagem. Portanto, todas as etiquetas de remessa terão um formulário unificado.

O sistema usa os dados, especialmente os identificadores de aplicativos predefinidos, para estabelecer as regras que devem ser aplicadas à parte relevante das informações verificadas.

Cada identificador de aplicativo sinaliza ao sistema que os caracteres subsequentes no código de barras digitalizados devem ser considerados um bloco de informações criptografadas. A configuração dos identificadores de aplicativo define como o sistema deve interpretar um código de barras e salvá-lo como um valor no sistema.

Os gerentes de logística podem usar os identificadores de aplicativos internacionais padrão e/ou criar seus próprios.

### <a name="load-the-standard-application-identifiers"></a>Carregar os identificadores de aplicativo padrão

Para iniciar rapidamente, você pode carregar uma lista de identificadores de aplicativos internacionais comuns. Em seguida, você poderá estender ou editar a lista posteriormente, conforme necessário.

Para carregar os identificadores de aplicativo padrão, siga estas etapas.

1. Vá para **Gerenciamento de depósito \> Configuração \> GS1 \> Identificadores de aplicativo de GS1**.
1. No Painel de Ação, selecione **Criar configuração padrão**.

> [!WARNING]
> O comando **Criar configuração padrão** exclui todos os identificadores de aplicativo definidos no momento e os substitui pela lista padrão. No entanto, depois de carregar a configuração padrão, você poderá personalizar a lista conforme necessário.

### <a name="set-up-custom-application-identifiers"></a>Configurar identificadores de aplicativos personalizados

Se alguns ou todos os identificadores de aplicativos que sua empresa usa forem diferentes do conjunto padrão, você poderá criar seus próprios códigos a partir do zero ou personalizar o conjunto padrão, conforme necessário.

Para configurar e personalizar seus próprios identificadores de aplicativos de GS1, siga estas etapas.

1. Vá para **Gerenciamento de depósito \> Configuração \> GS1 \> Identificadores de aplicativo de GS1**.
1. Siga uma destas etapas:

    - Para criar um novo identificador: no Painel de Ações, selecione **Novo**.
    - Para editar um identificador existente: selecione o identificador e, no Painel de Ações, selecione **Editar**.

1. Defina os seguintes campos para o identificador novo ou selecionado:

    - **Identificador do aplicativo** – Insira o código de identificação do identificador do aplicativo. Normalmente, esse código é um inteiro de dois dígitos, mas pode ser mais longo. Para valores decimais, o último dígito indica o número de casas decimais. Para obter mais informações, consulte a descrição da caixa de seleção **Decimal** mais adiante nesta lista. Se o recurso *Analisador aprimorado de códigos de barra GS1* estiver habilitado, você poderá criar um único identificador de aplicativo para todas as variantes de casas decimais usando a letra *n* como o último caractere no identificador do aplicativo. Por exemplo, você pode configurar apenas um identificador de aplicativo (*310n*) em vez de um identificador de aplicativo separado para cada número de casas decimais (*3101*, *3102*, *3103* e assim por diante).
    - **Descrição** – insira uma breve descrição do identificador.
    - **Tamanho fixo** – marque esta caixa de seleção se os valores que são verificados usando esse identificador de aplicativo tiverem um número fixo de caracteres. Desmarque esta caixa de seleção se o tamanho dos valores for variável. Nesse caso, você deve indicar o final do valor usando o caractere separador de grupo especificado na página **Parâmetros de gerenciamento de depósito**.
    - **Tamanho** – Insira o número máximo de caracteres que podem aparecer nos valores verificados usando este identificador de aplicativo. Se a caixa de seleção **Tamanho fixo** estiver marcada, será esperado exatamente este número de caracteres.
    - **Tipo** – selecione o tipo de valor que é verificado usando este identificador de aplicativo (*Numérico*, *Alfanumérico* ou *Data*). Para obter mais informações sobre como as datas e os números são representados em dados de código de barras, consulte a seção [Datas e casas decimais](#dates-and-decimal-numbers).
    - **Decimal** – marque esta caixa de seleção se o valor incluir um ponto decimal implícito. Se esta caixa estiver marcada, o sistema usará o último dígito do identificador do aplicativo para determinar o número de casas decimais. Para obter mais informações sobre como as datas e os números são representados em dados de código de barras, consulte a seção [Datas e casas decimais](#dates-and-decimal-numbers).

> [!WARNING]
> Embora o sistema permita definir a caixa de seleção **Tamanho fixo** como qualquer identificador de aplicativo, ele deve ser usado somente para o subconjunto de identificadores de aplicativos que têm um tamanho predefinido por as especificações gerais do GS1. O analisador aprimorado de GS1 já contém a lista de todos os identificadores de aplicativo com tamanhos predefinidos.

> [!NOTE]
> O valor de **Separador de grupo** especificado na página **Parâmetros do Warehouse Management** é opcional se um valor seguido por um identificador de aplicativo tiver um tamanho fixo.

## <a name="establish-the-generic-gs1-setup"></a><a name="generic-gs1-setup"></a>Estabelecer a configuração de GS1 genérica

A configuração de GS1 genérica estabelece uma coleção de mapeamentos comuns. Esses mapeamentos correspondem a cada campo de entrada relevante no aplicativo móvel para o identificador do aplicativo que controla como os valores dos códigos de barras digitalizados devem ser interpretados e armazenados nesse campo. Por padrão, essas configurações se aplicam a todas as verificações de todos os itens de menu do dispositivo móvel. No entanto, eles podem ser substituídos para um ou mais campos específicos por uma diretiva de GS1 atribuída a um item de menu específico.

A configuração de GS1 genérica permite que apenas um valor seja verificado de cada vez. Portanto, se você desejar carregar vários valores de campos de uma única verificação, deverá configurar uma diretiva de GS1 para os itens de menu relevantes.

Para obter mais informações sobre as políticas de GS1, consulte a próxima seção.

### <a name="load-the-standard-generic-gs1-setup"></a>Carregar a configuração de GS1 genérica padrão

A página **Configuração de GS1 genérica** permite carregar um conjunto padrão de mapeamentos entre campos de dispositivo móvel e identificadores de aplicativos padrão que são criados pela configuração padrão.

Para estabelecer a configuração de GS1 genérica, vá para **Gerenciamento de depósito \> Configuração \> GS1 \> Configuração de GS1 genérica**. Em seguida, selecione **Criar configuração padrão** para atribuir automaticamente um identificador de aplicativo adequado a cada campo que normalmente é usado por itens de menu de dispositivo móvel.

> [!WARNING]
> Se qualquer configuração de GS1 genérica já existir, o comando **Criar configuração padrão** a excluirá completamente e carregará a configuração padrão.

### <a name="customize-the-standard-generic-gs1-setup"></a>Personalizar a configuração de GS1 genérica padrão

Para personalizar a configuração de GS1 genérica, siga estas etapas.

1. Vá para **Gerenciamento de depósito \> Configuração \> GS1 \> Configuração de GS1 genérica**.
1. Siga uma destas etapas:

    - Para criar um novo mapeamento: no Painel de Ações, selecione **Novo** para criar uma nova política.
    - Para editar um mapeamento existente: selecione o mapeamento e, no Painel de Ações, selecione **Editar**.

1. Defina os seguintes campos para o mapeamento novo ou selecionado:

    - **Campo** – Selecione ou insira o campo de entrada do aplicativo móvel ao qual o valor de entrada deve ser atribuído. O valor não é o nome de exibição que os trabalhadores veem. Em vez disso, é o nome da chave que é atribuído ao campo no código subjacente. A configuração padrão fornece uma coleção de campos que provavelmente serão úteis e inclui nomes de chave intuitivos para cada campo e a funcionalidade programada correspondente. No entanto, você pode precisar conversar com seus parceiros de desenvolvimento para encontrar as seleções corretas para sua implementação.
    - **Identificador do aplicativo** – selecione o identificador de aplicativo aplicável, conforme definido na página **Identificadores de aplicativos de GS1**. O identificador estabelece como o código de barras será interpretado e armazenado como um valor para o campo nomeado. Depois de selecionar um identificador de aplicativo, o campo **Descrição** mostra a descrição dele.

## <a name="set-up-gs1-policies-to-be-to-mobile-device-menu-items"></a><a name="policies-for-menus"></a>Configurar políticas de GS1 como itens de menu de dispositivo móvel

A finalidade do padrão de GS1 é habilitar os trabalhadores a carregar vários valores quando examinam um único código de barras uma vez. Para isso, os gerentes de logística devem configurar políticas de GS1 que informam ao sistema como interpretar códigos de barras de vários valores. Posteriormente, você pode atribuir políticas a itens de menu do dispositivo móvel para controlar como um código de barras será interpretado quando os trabalhadores a examinarem enquanto estiverem usando um item de menu específico.

Se nenhuma política de GS1 for atribuída a um item de menu, o sistema só poderá capturar um valor único. Esse valor é aplicado à entrada de aplicativo móvel selecionada quando o trabalhador faz a verificação, conforme especificado na configuração de GS1 genérica. Se uma política de GS1 for atribuída ao item de menu, o sistema ainda usará a configuração GS1 genérica para mapear o primeiro valor de código de barras para o campo selecionado. No entanto, ele pode capturar valores de campo adicionais, conforme especificado pela política aplicável.

### <a name="load-the-standard-specific-gs1-policies"></a>Carregar as políticas de GS1 específicas padrão

Para iniciar rapidamente, você pode carregar um conjunto de políticas de GS1. Em seguida, você poderá estender ou editar as políticas posteriormente, conforme necessário.

Para carregar os identificadores de aplicativo padrão, siga estas etapas.

1. Vá para **Gerenciamento de depósito \> Configuração \> GS1 \> Política de GS1**.
1. No Painel de Ação, selecione **Criar configuração padrão**.

> [!WARNING]
> O comando **Criar configuração padrão** exclui todas as políticas definidas no momento e as substitui pelo conjunto de políticas padrão. No entanto, depois de carregar a configuração padrão, você poderá personalizar as políticas, conforme necessário.

### <a name="set-up-custom-specific-gs1-policies"></a>Configurar políticas de GS1 específicas

> [!WARNING]
> Algumas políticas de GS1 podem não funcionar com todos os fluxos móveis que você usa. Ao configurar políticas de GS1 personalizadas, você deve testar o fluxo do dispositivo móvel usando diferentes informações que são lidas em diferentes pontos do fluxo. Dessa forma, você pode determinar se o fluxo se comporta conforme o esperado.

Para configurar e personalizar suas políticas de GS1, siga estas etapas.

1. Vá para **Gerenciamento de depósito \> Configuração \> GS1 \> Política de GS1**.
1. Siga uma destas etapas:

    - Para criar uma nova política: no Painel de Ações, selecione **Novo**.
    - Para editar uma política existente, selecione-a no painel de lista.

1. No cabeçalho da política nova ou selecionada, defina os seguintes campos:

    - **Nome da política** – Insira um nome para a política.
    - **Descrição** – insira uma breve descrição da política.

1. Na Guia Rápida abaixo do cabeçalho, mapeie os nomes dos campos para os identificadores de aplicativo, conforme necessário para a política atual. Use os botões da barra de ferramentas para adicionar e remover linhas, conforme necessário. Para cada linha, defina os seguintes campos:

    - **Campo** – Selecione ou insira o campo de entrada do aplicativo móvel ao qual o valor de entrada deve ser atribuído. O valor não é o nome de exibição que os trabalhadores veem. Em vez disso, é o nome da chave que é atribuído ao campo no código subjacente. A configuração padrão fornece uma coleção de campos que provavelmente serão úteis e inclui nomes de chave intuitivos para cada campo e a funcionalidade programada correspondente. No entanto, você pode precisar conversar com seus parceiros de desenvolvimento para encontrar as seleções corretas para sua implementação.
    - **Identificador do aplicativo** – selecione o identificador de aplicativo aplicável, conforme definido na página **Identificadores de aplicativos de GS1**. O identificador estabelece como o código de barras será interpretado e armazenado como um valor para o campo nomeado. Depois de selecionar um identificador de aplicativo, o campo **Descrição** mostra a descrição dele.
    - **Classificação** – cada código de barras de valores múltiplos inclui uma série de identificadores de aplicativos, cada um deles seguido por um valor. A política de GS1 aplicável identifica qual identificador de aplicativo é mapeado para cada campo de banco de dados. No entanto, se um código de barras usar o mesmo identificador de aplicativo mais de uma vez, o sistema usará a ordem em que os identificadores de aplicativo aparecem no código para mapeá-los para os campos. Para linhas que compartilham um identificador de aplicativo com uma ou mais linhas, use este campo para estabelecer a ordem em que as linhas correspondentes são processadas. A linha que tem o menor valor de classificação será processada primeiro.

> [!NOTE]
> Para códigos de barras que incluem mais de um identificador de aplicativo idêntico, você *deve* usar o campo **Classificação** para estabelecer a ordem dos campos.

## <a name="assign-gs1-policies-to-mobile-device-menu-items"></a>Atribuir políticas de GS1 a itens de menu de dispositivo móvel

Por padrão, todos os itens de menu de dispositivo móvel fornecem campos de entrada nos quais os trabalhadores podem verificar um único valor, de acordo com a configuração de GS1 genérica. Se você deseja que os trabalhadores possam verificar mais de um valor de campo em uma única verificação para qualquer item de menu de dispositivo móvel, você deve atribuir uma diretiva de GS1 seguindo essas etapas.

1. Acesse **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.
1. Crie ou abra um item de menu.
1. Na Guia Rápida **Geral**, defina o campo **Política de GS1** como a política que se aplica ao item de menu.

## <a name="gs1-setup-example"></a>Exemplo de configuração de GS1

Este exemplo se aplica a um sistema em que as opções GS1 são configuradas da seguinte maneira:

- Na página **Parâmetros de gerenciamento de depósito**, as seguintes configurações globais são estabelecidas:

    - **Caractere FNC1:** *\]C1*
    - **Separador de grupo:** *\~*

- Na pagina **Identificadores de aplicativos GS1**, os seguintes identificadores de aplicativos são relevantes para este exemplo.

    | Identificador de aplicativo | descrição | Tamanho fixo | Extensão | Tipo | Decimal |
    |---|---|---|---|---|---|
    | 01 | GTIN | Selecionadas | 14 | Numérico | Compensado |
    | 10 | Nº do lote | Compensado | 20 | Alfanumérico | Compensado |
    | 17 | Data de vencimento  | Selecionadas | 6 | Data  | Compensado |
    | 30 | Quantidade recebida | Compensado | 8 | Numérico | Compensado |

- Na página **Configuração de GS1 genérica**, as configurações a seguir para a política de GS1 genérica são relevantes para este exemplo.

    | Campo | Identificador de aplicativo | descrição |
    |---|---|---|
    | ItemId | 01 | GTIN |

- Na página **Política de GS1**, há uma política em que o campo **Nome da política** está definido como *Recebimento de compra*. Esta política inclui as seguintes linhas.

    | Campo | Identificador de aplicativo | descrição | Classificação |
    |---|---|---|---|
    | ExpDate | 17 | Data de vencimento  | 0 |
    | InventBatchId | 10 | Nº do lote | 0 |
    | Qtd. | 30 | Quantidade recebida | 0 |

- Na página **Itens de menu do dispositivo móvel**, há um item de menu chamado *Recebimento de compra*. Seu campo **Política de GS1** está definido como *Recebimento de compra*.

Depois que as mercadorias de uma ordem de compra chegarem no depósito, o trabalhador seguirá essas etapas.

1. No dispositivo móvel, selecione o item de menu **Recebimento de compra**.
1. Inserir o número da ordem de compra.
1. Selecione o campo **Item** e leia o seguinte código de barras: `]C10100000012345678~3030~10b1~17220215`.

Por causa das configurações estabelecidas para este exemplo, o sistema analisa o código de barras digitalizado da seguinte maneira.

| Chave de campo | ID do Aplicativo | Alíquota | Observação |
|---|---|---|---|
| ItemId | 01 | 00000012345678 | Como o trabalhador é verificado para o campo **Item**, o primeiro valor no código de barras é mapeado para aquele campo. O mapeamento é obtido da configuração de GS1 genérica. |
| Qtd. | 30 | 30 | Como vários valores de campo estão sendo capturados em uma única verificação, esse mapeamento e todos os mapeamentos restantes são obtidos da diretiva GS1 atribuída ao item de menu **Recebimento de compra**. Este valor é a quantidade que foi recebida. |
| InventBatchId | 10 | b1 | Este valor é o ID do lote. |
| ExpDate | 17 | 220215 | O formato da data é AAMMDD. Portanto, a data de vencimento é 15 de fevereiro de 2022. |

Em seguida, o recebimento é registrado e os valores relevantes do banco de dados são inseridos após a verificação única.
