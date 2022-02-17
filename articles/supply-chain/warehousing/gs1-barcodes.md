---
title: Códigos de barras de GS1 e códigos QR
description: Este tópico descreve como configurar códigos de barras de GS1 e códigos QR para que os rótulos possam ser digitalizados em um depósito.
author: Mirzaab
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 702985ef9726690829e35e43d270477be318fc41
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075205"
---
# <a name="gs1-bar-codes-and-qr-codes"></a>Códigos de barras de GS1 e códigos QR

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- Preview until 10.0.25 GA -->

Geralmente, os trabalhadores de depósito precisam concluir várias tarefas quando usam um scanner de dispositivo móvel para registrar movimentos de um item, uma paleta ou um contêiner. Essas tarefas podem incluir os códigos de barra de verificação e a inserção manual das informações no dispositivo móvel. Os códigos de barras usam um formato específico da empresa que você define e gerencia usando o Microsoft Dynamics 365 Supply Chain Management.

O código de barras de GS1 e os formatos de código QR para etiquetas de remessa foram desenvolvidos para fornecer um padrão global para a troca de dados entre empresas. Os formatos de GS1 não só codificam os dados, mas também permitem usar uma lista predefinida de *identificadores de aplicativos* para definir o significado dos dados. O padrão GS1 define o formato dos dados e os vários tipos de dados que podem ser usados para codificar. Ao contrário dos códigos de barra antigos, os códigos de barras de GS1 podem ter vários elementos de dados. Portanto, uma única verificação de código de barras pode capturar vários tipos de informações sobre o produto, como o lote e a data de vencimento.

O suporte GS1 no Supply Chain Management simplifica muito o processo de digitalização em depósitos nos quais paletes e contêineres são rotulados usando códigos no formato GS1. Os trabalhadores de depósito podem extrair todas as informações necessárias através de uma única verificação de um código de barras de GS1. Ao eliminar a necessidade de realizar várias varreduras e/ou inserir manualmente as informações, os códigos de barras GS1 ajudam a reduzir o tempo associado às tarefas. Ao mesmo tempo, elas também ajudam a melhorar a precisão.

Os gerentes de logística devem configurar a lista necessária de identificadores de aplicativos e associá-los aos itens de menu de dispositivo móvel apropriados. Os identificadores de aplicativo podem ser usados em todos os depósitos como uma configuração global para fins de movimentação e de embalagem. Portanto, todas as etiquetas de remessa terão um formulário unificado.

A menos que especificado de outra forma, este tópico usa o termo *código de barras* para se referir a códigos de barras e códigos QR.

## <a name="turn-on-the-gs1-feature"></a>Ativar o recurso GS1

Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema. Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo. No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:

- **Módulo:** *Gerenciamento de depósito*
- **Nome do recurso:** *Verificar códigos de barras de GS1*

## <a name="set-up-global-gs1-options"></a>Configurar opções de GS1 globais

A página **Parâmetros de gerenciamento de depósito** fornece algumas configurações que estabelecem opções de GS1 globais.

Para configurar as opções de GS1 globais, siga estas etapas.

1. Acesse **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**.
1. Na Guia Rápida **Códigos de barras**, defina os seguintes campos:

    - **Caractere de FNC1** – especifique os caracteres que devem ser interpretados como um prefixo quando um código de barras é analisado.
    - **Caractere de datamatrix** – especifique os caracteres que devem ser interpretados como um prefixo quando um datamatrix é analisado.
    - **Caractere de código QR** – especifique os caracteres que devem ser interpretados como um prefixo quando um código QR é analisado.
    - **Separador de grupo** – especifique o caractere que identifica partes separadas de um código de barras ou código QR.
    - **Tamanho máximo do identificador** – especifique o número máximo de caracteres permitido para o identificador do aplicativo.

> [!NOTE]
> Os prefixos informam ao sistema que um código de barras é criptografado, de acordo com o padrão GS1. Até três prefixos (**caractere de FNC1**, **caractere de Datamatrix** e **caractere de código QR**) podem ser usados simultaneamente e para vários fins.

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

    - **Identificador do aplicativo** – Insira o código de identificação do identificador do aplicativo. Normalmente, esse código é um inteiro de dois dígitos, mas pode ser mais longo. Para valores decimais, o último dígito indica o número de casas decimais. Para obter mais informações, consulte a descrição da caixa de seleção **Decimal** mais adiante nesta lista.
    - **Descrição** – insira uma breve descrição do identificador.
    - **Tamanho fixo** – marque esta caixa de seleção se os valores que são verificados usando esse identificador de aplicativo tiverem um número fixo de caracteres. Desmarque esta caixa de seleção se o tamanho dos valores for variável. Nesse caso, você deve indicar o final do valor usando o caractere separador de grupo especificado na página **Parâmetros de gerenciamento de depósito**.
    - **Tamanho** – Insira o número máximo de caracteres que podem aparecer nos valores verificados usando este identificador de aplicativo. Se a caixa de seleção **Tamanho fixo** estiver marcada, será esperado exatamente este número de caracteres.
    - **Tipo** – selecione o tipo de valor que é verificado usando este identificador de aplicativo (*Numérico*, *Alfanumérico* ou *Data*). Para datas, o formato esperado é AAMMDD (sem espaços ou hifens).
    - **Decimal** – marque esta caixa de seleção se o valor incluir um ponto decimal implícito. Se esta caixa estiver marcada, o sistema usará o último dígito do identificador do aplicativo para determinar o número de casas decimais. Por exemplo, se o identificador do aplicativo for *3205*, a maioria dos cinco dígitos do valor será interpretada como próximo ao ponto decimal.

> [!NOTE]
> O separador de grupo especificado na página **Parâmetros de gerenciamento de depósito** será opcional se um valor seguido por um identificador de aplicativo tiver um tamanho fixo, ou se seu tamanho for maximizado (ou seja, se o comprimento for igual ao valor do **Tamanho** definido para o identificador do aplicativo).

## <a name="establish-the-generic-gs1-setup"></a>Estabelecer a configuração de GS1 genérica

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

## <a name="set-up-gs1-policies-that-you-can-assign-to-mobile-device-menu-items"></a>Configurar políticas de GS1 que podem ser atribuídas a itens de menu de dispositivo móvel

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
1. Selecione o campo **Item** e verifique o seguinte código de barras: *\]C10100000012345678\~3030\~10b1\~17220215*.

Por causa das configurações estabelecidas para este exemplo, o sistema analisa o código de barras digitalizado da seguinte maneira.

| Chave de campo | ID do Aplicativo | Alíquota | Observação |
|---|---|---|---|
| ItemId | 01 | 00000012345678 | Como o trabalhador é verificado para o campo **Item**, o primeiro valor no código de barras é mapeado para aquele campo. O mapeamento é obtido da configuração de GS1 genérica. |
| Qtd. | 30 | 30 | Como vários valores de campo estão sendo capturados em uma única verificação, esse mapeamento e todos os mapeamentos restantes são obtidos da diretiva GS1 atribuída ao item de menu **Recebimento de compra**. Este valor é a quantidade que foi recebida. |
| InventBatchId | 10 | b1 | Este valor é o ID do lote. |
| ExpDate | 17 | 220215 | O formato da data é AAMMDD. Portanto, a data de vencimento é 15 de fevereiro de 2022. |

Em seguida, o recebimento é registrado e os valores relevantes do banco de dados são inseridos após a verificação única.
