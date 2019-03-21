---
title: Sistema de mensagens eletrônicas
description: Este tópico contém uma visão geral e informações de configuração de mensagens eletrônicas no Microsoft Dynamics 365 for Finance and Operations.
author: ShylaThompson
manager: AnnBe
ms.date: 11/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2018-10-28
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 5326642553c7efcebc6c6af953e2dafe9e62e9ec
ms.sourcegitcommit: f6fc90585632918d9357a384b27028f2aebe9b5a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2019
ms.locfileid: "832186"
---
# <a name="electronic-messaging"></a>Mensagens eletrônicas

[!include [banner](../includes/banner.md)]

Este tópico contém uma visão geral e informações de configuração de mensagens eletrônicas no Microsoft Dynamics 365 for Finance and Operations.

Recentemente, as instituições governamentais e as autoridades legislativas de vários países e regiões do mundo implementaram requisitos de relatório para as empresas registradas nesses países ou regiões. A finalidade de requisitos é habilitar os dados que devem ser obtidos das empresas no formato eletrônico, diretamente dos sistemas onde foram contabilizados, armazenados e processados.

A funcionalidade Sistema de mensagens eletrônicas do Finance and Operations dá suporte a diversos processos para interoperação eletrônica entre o Finance and Operations e os sistemas que as autoridades governamentais e legislativas oferecem para relatórios, envios e recebimento de informações oficiais.

A funcionalidade Sistema de mensagens eletrônicas está integrada ao módulo **Relatório Eletrônico** (ER). Portanto, você pode configurar formatos de ER para mensagens eletrônicas. Para obter mais informações, consulte [Relatório eletrônico (ER)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/general-electronic-reporting).

O sistema de mensagens eletrônicas se baseia nestas entidades:

- **Mensagem eletrônica** – um relatório ou uma declaração que deve ser relatados e/ou transmitido internamente. Um exemplo é um relatório que foi enviado para a Secretaria da Receita Federal.
- **Itens da mensagem eletrônica** – os registros a serem incluídos na mensagem que é relatada.
- **Processamento de mensagens eletrônicas** – uma cadeia de ações, vinculadas ou desvinculadas, que devem ser executadas para coletar os dados necessários, gerar relatórios, armazenar dados no armazenamento de Blob do Microsoft Azure, transmitir relatórios para fora do sistema, obter respostas de fora do sistema e atualizar o banco de dados com base nas informações recebidas.

A ilustração a seguir mostra o fluxo de dados do sistema de mensagens eletrônicas.

![Fluxo de dados do sistema de mensagens eletrônicas](media/electronic-messaging-data-flow.png)

A funcionalidade Mensagens eletrônicas dá suporte aos seguintes cenários:

- Crie mensagens manualmente e gere relatórios com base em formatos de ER de exportação associados de vários tipos: Microsoft Excel, XML, JavaScript Object Notation (JSON), PDF, texto e Microsoft Word.
- Criar e processar automaticamente as mensagens baseadas em informações solicitadas e obtidas de uma autoridade em um formato de ER de importação associado.
- Colete e processe informações de uma fonte de dados (tabela do Finance and Operations) como itens da mensagem.
- Armazene informações adicionais e avalie diversos valores ao chamar as classes executáveis definidas especificamente em relação a mensagens ou a itens de mensagem.
- Agregue as informações coletadas em itens de mensagem, divida essas informações por mensagem e gere relatórios que estejam em formatos de ER de exportação associados.
- Transmita os relatórios gerados para um serviço Web usando as informações de segurança armazenadas no Azure Key Vault.
- Obtenha uma resposta de um serviço Web, interprete a resposta e atualize os dados no Finance and Operations como apropriado.
- Armazene e analise todos os relatórios gerados.
- Armazene e analise todas as informações de log relacionadas a ações executadas para uma mensagem ou um item de mensagem.
- Controle o processamento entre vários status de mensagens e status de itens de mensagem.

## <a name="set-up-electronic-messaging"></a>Configurar o sistema de mensagens eletrônicas

O sistema de mensagens eletrônicas pode ajudar você a manter diferentes processos de relatórios eletrônicos para tipos de documento diferentes. Em alguns cenários complexos, o sistema de mensagens eletrônicas é configurado para ter uma combinação de um status de mensagens, status de itens de mensagem, ações, campos adicionais e classes executáveis. Para esses cenários, os pacotes de entidades de dados estão disponíveis para importação. Se usar esses pacotes de entidade de dados, você deverá importá-los para uma entidade legal usando a Ferramenta de gerenciamento de dados. Para obter mais informações sobre como usar a Ferramenta de gerenciamento de dados, consulte [Gerenciamento de dados](../../dev-itpro/data-entities/data-entities-data-packages.md).

Se não importar um pacote de entidades de dados, você poderá configurar manualmente a funcionalidade Sistema de mensagens eletrônicas. Nesse caso, você deve configurar os seguintes elementos: 

- [Sequências numéricas](#number-sequences)
- [Tipos e status de itens de mensagem](#message-item-types-and-statuses)
- [Status de mensagens](#message-statuses)
- [Campos adicionais](#additional-fields)
- [Configurações de classe executável](#executable-class-settings)
- [Ações de preencher registros](#populate-records-actions)
- [Aplicativos Web](#web-applications)
- [Configurações de serviço Web](#web-service-settings)
- [Ações de processamento de mensagens](#message-processing-actions)
- [Processamento de mensagem eletrônica](#electronic-message-processing)

As seções a seguir fornecem mais informações sobre cada um desses elementos.

### <a name="number-sequences"></a>Sequências numéricas

Configure as sequências numéricas para mensagens e itens de mensagem. As sequências numéricas são usadas para numerar automaticamente as mensagens e os itens de mensagem, e os números atribuídos serão usados como identificadores exclusivos para mensagens e itens de mensagem no sistema. Você pode configurar sequências numéricas para o sistema de mensagens eletrônicas na página **Parâmetros de contabilidade** (**Contabilidade** \> **Configuração do razão** \> **Parâmetros de contabilidade**).

### <a name="message-item-types-and-statuses"></a>Tipos e status de itens de mensagem

Os tipos de item de mensagem identificam os tipos de registros que serão usados em mensagens eletrônicas. Você pode configurar tipos de item de mensagem na página **Tipos de item de mensagem** (**Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Tipos de item de mensagem**).

Os status de item de mensagem identificam os status que se aplicarão a itens de mensagem no processamento que você está configurando. Você pode configurar tipos de item de mensagem na página **Status de itens de mensagem** (**Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Status de itens de mensagem**).

O parâmetro **Permitir exclusão** de status de um item de mensagem define se o usuário terá permissão para excluir um item de mensagem nesse status por meio do formulário **Mensagens eletrônicas** ou do formulário **Itens de mensagem eletrônica**. 

### <a name="message-statuses"></a>Status de mensagens

Configure os status de mensagens que devem estar disponíveis no processamento de mensagens. Você pode configurar status de mensagens na página **Status de itens de mensagem** (**Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Status de mensagens**).

Descrição dos campos:

| Nome do campo           | Descrição |
|----------------------|-------------|
|Status da Mensagem        | Nome exclusivo de um status de mensagem eletrônica que caracteriza o estado de uma mensagem em cada momento. Este nome é mostrado no formulário Mensagens eletrônicas e em um log relacionado à mensagem eletrônica. |
|Descrição           | Descrição relacionada ao status da mensagem eletrônica      |
|Tipo de resposta         | Algumas ações em um processamento podem resultar em mais de um tipo de resposta. Como exemplo, a ação de tipo **Serviço Web** pode resultar no tipo de resposta **Execução bem-sucedida** ou **Erro técnico** dependendo do resultado de sua execução. Nesse caso, o status da mensagem para os dois tipos de resposta deve ser definido. Consulte [Tipos de ação de processamento de mensagens](#message-processing-action-types) para obter mais informações sobre tipos de ação e tipos de resposta. |
|Status de item de mensagem   |Há casos em que o status da mensagem eletrônica deve influenciar, respectivamente, o status dos itens de mensagem relacionados. Associe esse status de item de mensagem nesse campo selecionando-o na pesquisa. |
|Permitir exclusão          | O parâmetro **Permitir exclusão** de status de mensagem eletrônica define se o usuário poderá excluir uma mensagem eletrônica nesse status por meio do formulário **Mensagens eletrônicas**.            |

### <a name="additional-fields"></a>Campos adicionais

A funcionalidade Mensagens eletrônicas permite que você popule registros de uma tabela transacional. Assim, você pode preparar os registros para relatórios e então relatá-los. Ocasionalmente, não há informações suficientes na tabela transacional para relatar um registro de acordo com os requisitos de relatório. Você pode preencher todas as informações que devem ser relatadas para um registro configurando campos adicionais. Os campos adicionais podem ser associados a mensagens e a itens de mensagem. Você pode configurar os campos adicionais na página **Campos adicionais** (**Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Campos adicionais**).

A tabela a seguir descreve os campos gerais da página **Campos adicionais**:

| Campo                | Descrição |
|----------------------|-------------|
| Nome do campo           | Insira o nome de um atributo adicional de itens de mensagem relacionados ao processo. Este nome será mostrado na interface de usuário enquanto você trabalha com o processo. Também pode ser usado nas configurações de ER relacionadas ao processo. |
| descrição          | Insira uma descrição do atributo adicional de itens de mensagem relacionados ao processo. |
| Edição do usuário            | Em um caso em que um usuário deve poder alterar o valor do campo adicional da interface do usuário, marque esta caixa de seleção como **Sim**; caso contrário, como **Não**. |
| Contador              | Quando o campo adicional precisar conter um número de sequência dentro de uma mensagem eletrônica, marque essa caixa de seleção. Os valores do campo adicional serão preenchidos automaticamente durante a execução de uma ação do tipo “Exportação de relatório eletrônico”.  |
| Oculto               | Quando o campo adicional precisar estar oculto na interface do usuário, marque essa caixa de seleção.  |

Cada campo adicional pode ter valores diferentes para o processamento. Você pode definir esses valores na guia rápida Valores:

| Campo                | Descrição |
|----------------------|-------------|
| Valor do campo          | Insira o valor de campo a ser usado em relação a uma mensagem ou item de mensagem durante o relatório. |
| Descrição do campo    | Insira uma descrição do valor de campo a ser usado em relação a uma mensagem ou um item de mensagem durante o relatório. |
| Tipo de conta         | Alguns valores dos campos adicionais podem ser limitados a tipos de conta específicos. Selecione um destes valores: **Tudo**, **Cliente** ou **Fornecedor**. |
| Código da conta         | Se você tiver selecionado **Cliente** ou **Fornecedor** no campo **Tipo de conta** , poderá limitar ainda mais o uso de valores de campo a um grupo ou a uma tabela específica. |
| Número de conta/grupo | Se você tiver selecionado **Cliente** ou **Fornecedor** no campo **Tipo de conta** e se tiver inserido um grupo ou uma tabela no campo **Código de conta**, poderá inserir um grupo ou uma contramedida específico nesse campo. |
| Efetivação            | Especifique a data em que o valor deve começar a ser considerado. |
| Vencimento           | Especifique a data em que o valor deve parar a ser considerado. |

Combinações de critérios definidos em **Número de conta/grupo**, **Código da conta**, **Efetivação**, **Vencimento** não influenciam por padrão na seleção de valor para o campo adicional, mas podem ser usadas na classe executável para implementar alguma lógica específica de cálculo de um valor de campo adicional.

### <a name="executable-class-settings"></a>Configurações de classe executável

Uma classe executável é um método ou uma classe X++ que o processamento de mensagens eletrônicas pode chamar em relação a uma ação se alguma avaliação for necessária para o processo.

Você pode configurar manualmente uma classe executável na página **Configurações de classe executável** (**Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Configurações de classe executável**). Crie uma linha e defina os campos a seguir.

| Campo                 | descrição |
|-----------------------|-------------|
| Classe executável      | Insira o nome que será usado durante a instalação de uma ação de processamento de mensagens em relação à qual essa classe é chamada. |
| descrição           | Insira uma descrição da classe executável. |
| Nome de classe executável | Selecione uma classe executável X++. |
| Nível de execução       | Esse campo é automaticamente configurado porque o valor deve ser predefinido para a classe executável selecionada. Esse campo limita o nível em que a avaliação relacionada é executada. |
| Descrição da classe     | Esse campo é automaticamente configurado porque o valor deve ser predefinido para a classe executável selecionada. |

Algumas classes executáveis podem ter parâmetros obrigatórios que devem ser definidos antes que a classe executável seja executada pela primeira vez. Para definir esses parâmetros, clique no botão **Parâmetros** no painel Ação, configure os valores correspondentes e os campos na janela de diálogo e clique no botão **OK**. É importante clicar no botão **OK** aqui; caso contrário, os parâmetros não serão salvos na base e a classe executável não será chamada corretamente.

### <a name="populate-records-actions"></a>Ações de preencher registros

Você usa ações de preencher registros para configurar ações que adicionam registros à tabela Itens de mensagem para que eles possam ser adicionados a uma mensagem eletrônica. Por exemplo, se a sua mensagem eletrônica tiver de relatar faturas de cliente, você deverá configurar uma ação **Preencher registros** que esteja vinculada na tabela **Diário de fatura de cliente** (no campo **Fonte de dados**). Você pode configurar ações de preencher registros na página **Ação de preencher registros** (**Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Ações de preencher registros**). Crie um novo registro para cada ação que deverá adicionar registros a tabela e defina os campos a seguir.

| Campo       | descrição                                                               |
|-------------|---------------------------------------------------------------------------|
| Nome        | Insira um nome para a ação que preenche registros no seu processo.       |
| descrição | Insira uma descrição da ação que preenche registros no seu processo. |

Na FastTab **Configuração de fontes de dados**, adicione uma linha para cada fonte de dados usada para o processo e defina os campos a seguir.

| Campo                  | descrição |
|------------------------|-------------|
| Nome                   | Insira um nome para a fonte de dados. |
| Tipo de item de mensagem      | Selecione o tipo de item de mensagem a ser usado quando os registros são criados para a fonte de dados. |
| Tipo de conta           | Selecione o tipo de conta que deve ser associado aos registros da fonte de dados. |
| Nome da tabela mestra      | Selecione a tabela no Finance and Operations que deve ser uma fonte de dados. |
| Campo de número do documento  | Selecione o campo de onde o número de documento deve ser retirado na tabela selecionada. |
| Campo de data do documento    | Selecione o campo de onde a data de documento deve ser retirada na tabela selecionada. |
| Campo de conta do documento | Selecione o campo de onde a conta de documento deve ser retirada na tabela selecionada. |
| Consulta do usuário             | Se essa caixa de seleção estiver marcada, você poderá configurar uma consulta selecionando **Editar consulta** acima da grade. Caso contrário, todos os registros serão preenchidos desde a fonte de dados. |

### <a name="web-applications"></a>Aplicativos Web

Use a página de aplicativos Web para configurar parâmetros de um aplicativo Web para oferecer suporte ao OAuth 2.0 padrão aberto que permite aos usuários conceder "acesso delegado seguro" ao aplicativo em seu nome, sem compartilhar suas credenciais de acesso. Nesta página, você também pode passar pelo processo de autorização obtendo um código de autorização e um token de acesso. Você pode definir configurações de aplicativo Web na página **Aplicativos Web** (**Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Aplicativos Web**).

A tabela a seguir descreve os campos da página **Aplicativos Web**.

| Campo                         | Descrição |
|-------------------------------|-------------|
| Nome do aplicativo              | Insira um nome para o aplicativo Web. |
| Descrição                   | Insira uma descrição do aplicativo Web. |
| URL base                      | Insira o endereço de internet básico do aplicativo Web. |
| Caminho da URL de autorização        | Especifique o caminho para compor a URL para autorização.  |
| Caminho da URL do token                | Especifique o caminho para compor a URL para token.  |
| URL de redirecionamento                  | Insira a URL de redirecionamento.  |
| ID do cliente                     | Insira a ID do cliente do aplicativo Web.  |
| Segredo do cliente                 | Insira o segredo do cliente do aplicativo Web.  |
| Token do servidor                  | Insira o token do servidor do aplicativo Web.  |
| Mapeamento do formato da autorização  | Selecione um formato ER (Relatório eletrônico) a ser usado para gerar a solicitação de autorização.   |
| Importar mapeamento do modelo do token    | Selecione um mapeamento de modelo de importação ER a ser usado para armazenar o token de acesso.  |
| Escopo concedido      O token de acesso expirará em  | Este campo será atualizado automaticamente. Seu valor mostra o escopo concedido de solicitações para o aplicativo Web.  |
| Aceitar                        | Especifique a propriedade de aceitação da solicitação Web. Por exemplo, "application/vnd.hmrc.1.0+json".  |
| Tipo de conteúdo           | Especifique o tipo de conteúdo. Por exemplo, "application/json".  |

As seguintes funções estão disponíveis na página **Aplicativos Web** para oferecer suporte ao processo de autorização:
-   **Obter código de autorização** - para inicializar a autorização do aplicativo Web.
-   **Obter token de acesso** - para inicializar a obtenção de um token de acesso.
-   **Atualizar token de acesso** - para atualizar um token de acesso.

Quando um token de acesso a um aplicativo Web é armazenado na base de dados do sistema em formato criptografado, ele pode ser usado para solicitações a um serviço Web. Para fins de segurança, o acesso ao token de acesso deve ser restrito apenas às funções de segurança que devem ter permissão para atender a essas solicitações. Quando um usuário fora do grupo de segurança está tentando endereçar uma solicitação, uma exceção informará ao usuário que ele não tem permissão para interoperação por meio do aplicativo Web selecionado.
Use a tabela rápida **Funções de segurança** da página Imposto > Configuração > Mensagens eletrônicas > Aplicativos Web para configurar funções que devem ter acesso ao token de acesso. Quando as funções de segurança não estão definidas para um aplicativo Web, um administrador do sistema só poderá interoperar por meio desse aplicativo Web.

### <a name="web-service-settings"></a>Configurações de serviço Web

Você usa configurações de serviço Web para configurar a transmissão de dados direta para um serviço Web. Você pode definir configurações de serviço Web na página **Configurações do serviço Web** (**Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Configurações do serviço Web**).

A tabela a seguir descreve os campos da página **Configurações do serviço Web**.

| Campo                   | descrição |
|-------------------------|-------------|
| Serviço Web             | Insira um nome para o serviço Web. |
| descrição             | Insira uma descrição do serviço Web. |
| Endereço na Internet        | Insira o endereço da internet do serviço Web. Se um aplicativo Web for especificado para um serviço Web e o endereço na Internet for o mesmo que o definido para o aplicativo Web selecionado, clique no botão **Copiar URL base** para copiar a **URL base** do aplicativo Web no campo **Endereço na Internet** do serviço Web.  |
| Certificado             | Selecione um certificado do Key Vault previamente configurado. |
| Aplicativo Web         | Selecione um certificado do Key Vault previamente configurado. |
| O tipo de resposta - XML | Defina essa opção como **Sim** se o tipo de resposta for XML. |
| Método de solicitação          | Especifique o método da solicitação. O HTTP define um conjunto de métodos de solicitação que indicam a ação que deve ser executada para um recurso específico. O método pode ser **GET**, **POST** ou outro método HTTP. |
| Cabeçalhos de solicitação         | Especifique cabeçalhos de solicitação. Um cabeçalho de solicitação é um cabeçalho HTTP que pode ser usado em uma solicitação HTTP, e que não está relacionado ao conteúdo da mensagem. |
| Aceitar                  | Especifique a propriedade de aceitação da solicitação Web. |
| Aceitar codificação         | Especifique a Accept-Encoding. O cabeçalho HTTP da solicitação Accept-Encoding anuncia a codificação de conteúdo que o cliente pode compreender. Geralmente, a codificação de conteúdo é um algoritmo de compactação. |
| Tipo de conteúdo            | Especifique o tipo de conteúdo. O cabeçalho da entidade Content-Type indica o tipo de mídia do recurso. |
| Código de resposta bem-sucedida   | Especifique o código de status HTTP indicando que a solicitação foi bem-sucedida. |
| Mapeamento do formato dos cabeçalhos de solicitação  | Selecione o formato ER para geração de cabeçalhos de solicitação Web. |

### <a name="message-processing-actions"></a>Ações de processamento de mensagens

Você usará as ações de processamento de mensagens para criar ações para os processos e configurar seus parâmetros. Você pode configurar as ações de processamento na página **Ações de processamento de mensagens** (**Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Ações de processamento de mensagens**).

As tabelas a seguir descrevem os campos da página **Ações de processamento de mensagens**.

#### <a name="general-fasttab"></a>FastTab Geral

| Campo                   | descrição |
|-------------------------|-------------|
| Tipo de ação             | Selecione o tipo de ação. Para obter informações sobre as opções disponíveis, consulte a seção [Tipos de ação de processamento de mensagens](#message-processing-action-types). |
| Mapeamento de formato          | Selecione o formato de ER a ser chamado para a ação. Esse campo só está disponível para ações dos tipos **Exportação de relatórios eletrônicos**, **Importação de relatórios eletrônicos** e **Mensagem de exportação de relatórios eletrônicos**. |
| Mapeamento do formato para caminho da URL | Selecione o formato de ER a ser chamado para a ação. Este campo está disponível apenas para ações dos tipos **Serviço Web** e é usado para compor o caminho do endereço da URL que será adicionado ao endereço de Internet básico especificado para o servidor Web selecionado. |
| Tipo de item de mensagem       | Selecione o tipo de registros para os quais a ação deve ser avaliada. Esse campo está disponível para ações dos tipos **Nível de execução de item de mensagem**, **Exportação de relatórios eletrônicos**, **Importação de relatórios eletrônicos**, **Serviço Web** e também para alguns outros tipos. Se deixar esse campo em branco, todos os tipos de item da mensagem definidos para o processamento de mensagens são avaliados. |
| Classe executável        | Selecione as configurações de classe executável previamente criadas. Este campo só está disponível para ações dos tipos **Nível de execução de item de mensagem** e **Nível de execução de item de mensagem** . |
| Ação de preencher registros | Selecione uma ação de preencher registros previamente configurada. Esse campo só está disponível para ações do tipo **Preencher registros**. |
| Serviço Web  | Selecione um serviço Web previamente configurado. Esse campo só está disponível para ações do tipo **Serviço Web**.  |
| Nome do arquivo  | Especifique o nome do arquivo que resultará na ação como uma resposta do servidor Web ou geração de um relatório. Este campo só está disponível para ações do tipo **Serviço Web** e **Mensagem de exportação de relatório eletrônico**.   |
| Mostrar caixa de diálogo  | Marque esta caixa de seleção se uma caixa de diálogo deve ser mostrada para um usuário antes da geração do relatório. Este campo só está disponível para ações do tipo **Mensagem de exportação de relatório eletrônico**.   |

##### <a name="message-processing-action-types"></a>Tipos de ação de processamento de mensagens

As seguintes opções estão disponíveis no campo **Tipo de ação**:

- **Criar mensagem** – use esse tipo para permitir que os usuários criem manualmente mensagens na página **Mensagem eletrônica**. Um status inicial não pode ser configurado para uma ação desse tipo.
- **Preencher registros** – a ação **Preencher registros** deve ser previamente configurada. Associe-a a uma ação do tipo **Preencher registros** para permitir que ela seja incluída no processamento. Presume-se que esse tipo de ação seja usado para a primeira ação no processamento de mensagens (quando nenhuma mensagem eletrônica é criada antecipadamente) ou como uma ação que inclui itens de mensagens em uma mensagem criada anteriormente (por uma ação do tipo**Criar mensagem**). Portanto, o status de resultado de apenas itens de mensagens pode ser configurado para uma ação desse tipo. Um status inicial pode ser configurado apenas para mensagem.
- **Nível de execução da mensagem** – use esse tipo para configurar uma classe executável que deve ser avaliada no nível da mensagem.
- **Nível de execução de item de mensagem** – use esse tipo para configurar uma classe executável que deve ser avaliada no nível do item de mensagem.
- **Exportação de relatórios eletrônicos** – use esse tipo para as ações que devem gerar um relatório com base em uma configuração de ER de exportação no nível do item da mensagem.
- **Mensagem de exportação de relatórios eletrônicos** – use esse tipo para as ações que devem um gerar relatório com base em uma configuração de ER de exportação no nível da mensagem (por exemplo, quando uma mensagem não tiver itens de mensagem).
- **Importação de relatórios eletrônicos** – use esse tipo para as ações que devem gerar um relatório com base em uma configuração de ER de exportação no nível do item da mensagem.
- **Processamento de usuário no nível da mensagem** – use esse tipo para as ações que supõem algumas ações manuais do usuário. Por exemplo, o usuário pode atualizar o status de mensagens.
- **Processamento de usuário** – use esse tipo para as ações que supõem alguma ação manual do usuário. Por exemplo, o usuário pode atualizar o status de itens de mensagem.
- **Serviço Web** – use esse tipo para as ações que devem transmitir um relatório gerado para um serviço Web. Esse tipo de ação não é usado para o relatório de comunicação de faturas de compra e venda italiano. Para ações de tipo **Serviço Web**, você pode especificar um **Texto de confirmação** na guia rápida **Detalhes diversos** de **Ações de processamento de mensagens**. Este texto de confirmação será mostrado ao usuário antes que a solicitação para o serviço Web selecionado seja endereçada.
- **Verificação de solicitação** – use esse tipo para solicitar a verificação de um servidor.

#### <a name="initial-statuses-fasttab"></a>FastTab Status iniciais

> [!NOTE]
> A FastTab **Status iniciais** não está disponível para ações que têm um tipo inicial de **Criar mensagem**.

| Campo               | Descrição                                                                                         |
|---------------------|-----------------------------------------------------------------------------------------------------|
| Status de item de mensagem | Selecione o status do item de mensagem para o qual a ação de processamento de mensagens deve ser avaliada. |
| descrição         | Uma descrição do status do item de mensagem selecionado.                                                  |

#### <a name="result-statuses-fasttab"></a>FastTab Status de resultados

| Campo               | descrição |
|---------------------|-------------|
| Status da mensagem      | Selecione os status da mensagem para o qual a ação de processamento de mensagens deve ser avaliada. Esse campo só está disponível para ações de processamento de mensagens que são avaliadas no nível da mensagem. Por exemplo, está disponível para as ações do tipo **Exportação de relatórios eletrônicos** e **Importação de relatórios eletrônicas**. Não está disponível para as ações dos tipos **Processamento de usuário** e **Nível de execução de item de mensagem**. |
| descrição         | Uma descrição do status da mensagem selecionada. |
| Tipo de resposta       | O tipo de resposta do status da mensagem selecionada. |
| Status de item de mensagem | Selecione os status resultantes que devem estar disponíveis após a avaliação da ação de processamento de mensagens. Esse campo só está disponível para ações de processamento de mensagens que são avaliadas no nível de item de mensagem. Por exemplo, está disponível para as ações dos tipos **Processamento de usuário** e **Nível de execução de item de mensagem**. Para ações de processamento de mensagens que são avaliadas no nível da mensagem, esse campo mostra o status do item de mensagem que foi configurado para o status da mensagem selecionado. |

A tabela a seguir ilustra quais status de resultados devem ser configurados em relação aos tipos de ações:

| Tipo de ação/resposta de mensagem eletrônica  | Execução bem-sucedida  | Erro de negócios  | Erro técnico  | Definido pelo Usuário  | Cancelar  |
|-------------------------------------------------|--------------|---------|-------|-----|-----------------|
| Criar mensagem                                  | X            |         |       |     |                 |
| Exportação de relatório eletrônico                     | X            |         |       |     |                 |
| Importação de relatório eletrônico                     |              |         |       |     |                 |
| Serviço Web                                     | X            |         | X     |     |                 |
| Processamento do usuário                                 |              |         |       |     |                 |
| Nível de execução da mensagem                         |              |         |       |     |                 |
| Preencher registros                                |              |         |       |     |                 |
| Nível de execução do item da mensagem                    |              |         |       |     |                 |
| Verificação da solicitação                            | X            |  X      | X     |     |                 |
| Mensagem de exportação de relatório eletrônico             | X            |         |       |     |                 |
| Processamento de usuário de nível de mensagem                   |              |         |       |     |                 |

### <a name="electronic-message-processing"></a>Processamento de mensagem eletrônica

O processamento de mensagens eletrônicas é um conceito básico da funcionalidade Mensagens eletrônicas. Agrega ações que devem ser avaliadas para a mensagem eletrônica. As ações que podem ser vinculadas por meio de um status inicial e um status de resultado. Alternativamente, as ações do tipo **Processamento de usuário** podem ser iniciadas de forma independente. Na página **Processamento de mensagens eletrônica** (**Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Processamento de mensagens eletrônicas**), é possível selecionar os campos adicionais que devem ter suporte para o processamento no nível da mensagem ou no nível dos itens da mensagem.

A FastTab **Ação** permite adicionar ações predefinidas ao processamento. Você pode especificar se uma ação deve ser executada separadamente, ou pode ser iniciada pelo processamento. Para definir se a ação pode ser inicializada apenas por um usuário, marque a caixa de seleção **Executar separadamente** para a ação no processamento. Desmarque o parâmetro **Executar separadamente** para que a ação seja iniciada por processamento em caso de mensagens ou itens de mensagem no status definido como status inicial para tal ação. A ação do tipo **Ação do usuário** só deverá ser executada separadamente. 

Às vezes, pode ser necessário agregar várias ações em uma sequência, mesmo quando a primeira delas é definida para ser executada separadamente. Por exemplo, quando é necessário que a geração de relatórios seja inicializada por um usuário, mas, uma vez gerado, o relatório deve ser enviado imediatamente para um serviço Web e a resposta do serviço Web deve ser refletida no sistema. Você pode usar para esta finalidade: **Sequência inseparável**. Para fazer isso, clique no botão **Sequência inseparável** no Painel de Ação da guia rápida **Ação** da página **Processamento de mensagem eletrônica**, crie uma sequência e selecione-a na coluna **Sequência inseparável** para as ações que devem ser executadas sempre juntas. A primeira ação nesse caso pode ser configurada como **Executar separadamente**, mas todas as outras não.

A FastTab **Campos adicionais do item de mensagem** permite adicionar os campos adicionais predefinidos relacionados a itens de mensagem. Você deve adicionar outros campos para cada tipo de item de mensagem ao qual os campos estão relacionados.

A FastTab **Campos adicionais da mensagem** permite adicionar outros campos predefinidos relacionados a mensagens.

A FastTab **Funções de segurança** permite que você configure as funções de segurança predefinidas no sistema para processamento específico. Os usuários com uma função específica verão apenas o processamento definido para a função.

A FastTab **Lote** permite que você configure o processamento para funcionar em um regime de lote.

## <a name="work-with-electronic-messages-functionality"></a>Trabalhar com a funcionalidade Mensagens eletrônicas

Se você estiver trabalhando no nível da mensagem, a página **Mensagens eletrônicas** (**Imposto** \> **Consultas e relatórios** \> **Mensagens eletrônicas** \> **Mensagens eletrônicas**) é mais útil. Se você estiver operando no nível da coleta de dados (item de mensagem), a página **Itens de mensagem eletrônica** (**Imposto** \> **Consultas e relatórios** \> **Mensagens eletrônicas** \> **Itens de mensagem eletrônica**) é mais útil.

### <a name="electronic-messages"></a>Mensagens eletrônicas

A página **Mensagens eletrônicas** apresenta o processamento que está disponível para você, com base em sua função. As funções de segurança estão associadas ao processamento na configuração desse processamento. Para cada processamento disponível para você, a página mostra mensagens eletrônicas e informações relacionadas a ele.

A FastTab **Mensagens** mostra mensagens eletrônicas para o processamento selecionado. Dependendo do status da mensagem selecionada e do processamento predefinido, você pode executar algumas ações aos selecionar os botões acima da grade:

- **Novo** – esse botão está associado a ações do tipo **Criar mensagem**.
- **Excluir** – esse botão estará disponível se a caixa de seleção **Permitir exclusão** estiver marcada para o status atual da mensagem selecionada.
- **Coletar dados** - Este botão está associado à ação do tipo **Preencher registros**.
- **Gerar relatório** – esse botão está associado a ações do tipo **Mensagem de exportação de relatórios eletrônicos**.
- **Enviar relatório** – esse botão está associado a ações do tipo **Serviço Web**.
- **Importar resposta** - Este botão está associado a ações do tipo **Importação de relatório eletrônico**.
- **Status da atualização** – esse botão está associado a ações do tipo **Processamento de usuário no nível da mensagem**.
- **Itens de mensagem** – abra a página **Itens de mensagem eletrônica**.

A FastTab **Log de ação** mostra informações sobre todas as ações executadas para a mensagem selecionada. Se uma ação resultou em um erro, as informações sobre o erro serão anexadas à linha de log de ação relacionada. Selecione a linha e clique no botão **clip** no canto superior direito da página para analisar as informações sobre o erro.

A FastTab **Campos adicionais da mensagem** mostra todos os campos adicionais definidos para mensagens na configuração de processamento. Também mostra os valores desses campos adicionais.

A FastTab **Itens de mensagem** mostra todos os itens de mensagem relacionados à mensagem selecionada. Para cada um dos itens de mensagem, a função seguinte pode ser usada dependendo do status desse item de mensagem:

- **Excluir** – Este botão estará disponível se a caixa de seleção **Permitir exclusão** estiver marcada para o o status atual do item de mensagem selecionado.
- **Status da atualização** – Este botão está associado a ações do tipo **Processamento do usuário**.
- **Documento original** - Este botão permite ao usuário abrir uma página com o documento original da mensagem selecionada.

Você pode examinar todos os anexos para a mensagem selecionada. Os anexos são relatórios que já foram já gerados e recebidos. Selecione a mensagem cujos anexos serão examinados e então selecione o botão **Anexo** no Painel de Ações.

![Botão Anexo](media/attachment-icon.png)

A página **Anexos** mostra todos os anexos relacionados à mensagem. Para exibir um arquivo, selecione-o na lista à esquerda e então selecione **Abrir** no Painel de Ações.

![Botão Abrir](media/open-button.png)

Para examinar um anexo relacionado a uma ação específica executada anteriormente para uma mensagem, selecione a mensagem na página **Mensagens eletrônicas** e então, na FastTab **Log de ação**, selecione a ação. Em seguida, selecione o botão **Anexo** no Painel de Ações.

Você também pode executar todo o processamento ou apenas uma ação específica, selecionando **Executar processamento** no Painel de Ações.

### <a name="electronic-message-items"></a>Itens de mensagem eletrônica

A página **Itens de mensagem eletrônica** apresenta todos os itens de mensagem e um log das ações executadas para cada item de mensagem. Também mostra os campos adicionais definidos para os itens de mensagem, e os valores desses campos adicionais.

A tabela a seguir descreve os campos na guia **Itens de mensagem**.

<table>
<thead>
<tr>
<th>Campo</th>
<th>descrição</th>
</tr>
</thead>
<tbody>
<tr>
<td>Processando</td>
<td>O nome de processamento usado para criar o item de mensagem.</td>
</tr>
<tr>
<td>Item de mensagem</td>
<td>A ID do item de mensagem. Essa ID é atribuída automaticamente, com base na sequência numérica do <strong>Item de mensagem</strong> definida na página <strong>Parâmetros de contabilidade</strong>.</td>
</tr>
<tr>
<td>Data do item de mensagem</td>
<td>A data em que o item de mensagem foi criado.</td>
</tr>
<tr>
<td>Tipo de item de mensagem</td>
<td>O tipo de item de mensagem. Vários tipos de itens de mensagem podem ser configurados para o mesmo processamento (por exemplo, <strong>Faturas de entrada</strong> e <strong>Faturas de saída</strong>). Esse campo só poderá ser preenchido automaticamente quando uma fatura for adicionada à tabela Itens de mensagem.</td>
</tr>
<tr>
<td>Status de item de mensagem</td>
<td>O status real do item de mensagem. Os status disponíveis variam, dependendo do tipo de item de mensagem. Eis alguns exemplos:
<ul>
<li><strong>Preenchido</strong> – um registro foi adicionado à tabela Itens de mensagem.</li>
<li><strong>Avaliado</strong> – atributos adicionais foram calculados para o item de mensagem.</li>
<li><strong>Relatado</strong> – o item de mensagem foi adicionado com êxito a um relatório.</li>
<li><strong>Excluído</strong> – o status poderá ser útil se você tiver de excluir alguns itens de mensagem de um relatório antes de exportar.</li>
</ul>
</td>
</tr>
<tr>
<td>Data de transmissão</td>
<td>Para o processamento que transmite automaticamente um relatório gerado fora do sistema, a data em que o item de mensagem foi transmitido.</td>
</tr>
<tr>
<td>Número do documento</td>
<td>Esse campo é preenchido automaticamente, com base na configuração da ação de preencher registros. Esse campo só poderá ser preenchido automaticamente quando uma fatura for adicionada à tabela Itens de mensagem.</td>
</tr>
<tr>
<td>Número da conta</td>
<td>O número da conta de um cliente ou fornecedor (ou outro valor do campo, dependendo do campo definido na ação <strong>Preencher registros</strong>). Esse campo só poderá ser preenchido automaticamente quando uma fatura for adicionada à tabela Itens de mensagem.</td>
</tr>
<tr>
<td>Mensagem</td>
<td>O número da mensagem. Esse número é atribuído automaticamente, com base na sequência numérica do <strong>Item de mensagem</strong> definida na página <strong>Parâmetros de contabilidade</strong>.</td>
</tr>
<tr>
<td>Status da mensagem</td>
<td>O status real da mensagem eletrônica.</td>
</tr>
<tr>
<td>Próxima ação</td>
<td>As seguintes ações que podem ser iniciadas para o status atual do item de mensagem.</td>
</tr>
</tbody>
</table>

A guia **Campos adicionais** mostra os campos adicionais para o item de mensagem selecionado e seus valores.

#### <a name="run-processing"></a>Executar processamento

Selecione **Executar processamento** no Painel de Ações para executar o processamento para itens de mensagem. Para executar uma ação específica, na caixa de diálogo **Executar processamento** , defina a opção **Selecionar ação** como **Sim**, e selecione uma ação. Para executar o processamento inteiro, deixe a opção **Selecionar ação** definida como **Não**.

#### <a name="generate-report"></a>Gerar relatório

Selecione **Gerar relatório** no Painel de Ações para gerar um relatório. Esse botão está associado a ações do tipo **Exportação de relatórios eletrônicos**.

#### <a name="update-status"></a>Atualizar Status

Selecione **Atualizar status** no Painel de Ações para atualizar o status de um ou mais itens de mensagem. Na caixa de diálogo **Atualizar status**, use a FastTab **Registros a incluir** para selecionar itens de mensagem para atualização. Defina corretamente os critérios de seleção, porque os status de itens de mensagem serão atualizados de acordo com esses critérios, o status inicial da ação selecionada e o valor **Novo status** que você definir. Depois que uma atualização de status for concluída, será difícil determinar quais itens foram atualizados. Portanto, será difícil reverter atualizações de status.

#### <a name="electronic-messages"></a>Mensagens eletrônicas

Selecione **Mensagem eletrônica** no Painel de Ações para examinar uma mensagem eletrônica que esteja relacionada ao item de mensagem selecionado.

Você também pode examinar todos os arquivos que correspondem ao item de mensagem. Selecione o campo **Mensagem** da mensagem ou selecione **Mensagem eletrônica** no Painel de Ações. Na página **Mensagem eletrônica**, selecione a mensagem para examinar um relatório e então selecione o botão **Anexo** no Painel de Ações.

![Botão Anexo](media/attachment-icon.png)

A página **Anexos** mostra todos os anexos relacionados à mensagem. Para exibir um arquivo, selecione-o na lista à esquerda e então selecione **Abrir** no Painel de Ações.

![Botão Abrir](media/open-button.png)

#### <a name="original-document"></a>Documento original

Selecione **Documento original** no Painel de Ações para abrir o documento original para o item de mensagem selecionado.

## <a name="example"></a>Exemplo

Depois de criar seu formato de ER, o mapear para fontes de dados e o concluir, você poderá executá-lo usando o espaço de trabalho **Relatórios eletrônicos**. É gerado um relatório que pode ser salvo localmente.

Para controlar os seguintes aspectos do processo de relatórios, você deverá configurar o processamento de mensagens eletrônicas:

- Registre em log informações sobre quem gerou o relatório.
- Registre em log quando o relatório foi gerado.
- Salve os relatórios que foram gerados para períodos anteriores.

Essa seção fornece um exemplo que mostra como você pode configurar a funcionalidade Mensagens eletrônicas para compilar um processo de relatórios.

### <a name="set-up-and-run-processing-to-call-a-simple-er-exporting-format-to-generate-an-excel-report"></a>Configurar e executar processamento para chamar um formato de exportação de ER simples para gerar um relatório do Excel

Essa seção fornece um exemplo que mostra como é possível configurar mensagens eletrônicas para gerar um relatório baseado em um formato de ER de exportação para o Excel. Para seguir este exemplo, o formato de exportação do Excel de ER já deve ter sido criado, mapeado para fontes de dados e concluído. Uma sequência numérica já deverá ter ser configurada para mensagens eletrônicas.

Quando você criar o processamento, será útil principalmente se você definir as ações e os status de processamento que serão configurados. A ilustração a seguir mostra que o processamento se parece com este exemplo.

![Esquema de processamento](media/processing-scheme.png)

#### <a name="create-message-statuses"></a>Criar status da mensagem

1. Vá para **Imposto \> Configuração \> Mensagens eletrônicas \> Status da mensagem**.
2. Crie os seguintes status da mensagem:

    - Nova
    - Preparado
    - Gerado

    ![Status de mensagens](media/message-statuses.png)

3. Na linha para o status **Novo**, marque a caixa de seleção **Permitir exclusão** para permitir que os usuários excluam as mensagens com esse status.

#### <a name="create-additional-fields"></a>Criar campos adicionais

1. Vá para **Imposto \> Configuração \> Mensagens eletrônicas \> Campos adicionais**.
2. Adicione outro campo e seus valores. Veja aqui um exemplo.

    ![Campos adicionais](media/additional-fields.png)

3. Defina a opção **Edição do usuário** como **Sim** para permitir que os usuários editem o campo.

#### <a name="create-message-processing-actions"></a>Criar ações de processamento de mensagens

Para este exemplo, você criará as seguintes ações:

- **Criar mensagem**
- **Atualizar como Preparado**
- **Gerar relatório**
- **Atualizar para status inicial** (opcional)

1. Vá para **Imposto \> Configuração \> Mensagens eletrônicas \> Ações de processamento de mensagens**.
2. Crie uma ação chamada **Criar mensagem**. Na FastTab **Geral**, no campo **Tipo de ação**, selecione **Criar mensagem**.
3. Crie uma ação chamada **Atualizado para Preparado** e defina os seguintes campos:

    - Na FastTab **Geral**, no campo **Tipo de ação**, selecione **Processamento de usuários no nível da mensagem**.
    - Na FastTab **Status iniciais**, no campo **Status da mensagem**, selecione **Novo**.
    - Na FastTab **Status resultantes**, no campo **Status da mensagem**, selecione **Preparado**. No campo **Tipo de resposta** , insira **Executado com êxito**.

4. Crie uma ação chamada **Gerar relatório** e defina os seguintes campos:

    - Na FastTab **Geral**, no campo **Tipo de ação**, selecione **Exportação de relatórios eletrônicos**. No campo **Formatar mapeamento**, selecione o formato de ER de exportação. As opções são **Excel**, **XML**, **JSON**, **Texto** e **Outro**.
    - Na FastTab **Status iniciais**, no campo **Status da mensagem**, selecione **Preparado**.
    - Na FastTab **Status resultantes**, no campo **Status da mensagem**, selecione **Gerado**. No campo **Tipo de resposta** , insira **Executado com êxito**.

    ![Ação de gerar relatório](media/generate-report-action.png)

5. Opcional: para deixar que os usuários regenerem um relatório várias vezes, você poderá criar uma ação **Atualizar para status inicial** e definir os seguintes campos:

    - Na FastTab **Geral**, no campo **Tipo de ação**, selecione **Processamento de usuários no nível da mensagem**.
    - Na FastTab **Status iniciais**, no campo **Status da mensagem**, selecione **Gerado**.
    - Na FastTab **Status resultantes**, no campo **Status da mensagem**, selecione **Preparado** ou (e) **Novo**. No campo **Tipo de resposta** , insira **Executado com êxito**.

#### <a name="electronic-message-processing"></a>Processamento de mensagem eletrônica

Neste exemplo, todas as ações devem ser configurados de forma que sejam executadas separadamente. A suposição é que cada ação será inicializada pelo usuário.

1. Vá para **Imposto \> Configuração \> Mensagens eletrônicas \> Processamento de mensagens eletrônicas**.
2. Adicione um registro para o processamento e adicione todas as ações definidas anteriormente e um campo adicional.
3. Opcional: na FastTab **Funções de segurança**, defina funções de segurança para que seu processamento restrinja o acesso ao relatório específico.
4. Vá para **Imposto \> Consultas e relatórios \> Mensagens eletrônicas \> Mensagens eletrônicas**.
5. Selecione **Nova** para criar uma mensagem. Nesse ponto, você pode adicionar datas e uma descrição. Você também pode atualizar o valor do campo adicional como necessário.

    ![Criar uma mensagem eletrônica](media/create-electronic-message.png)

A grade da FastTab **Log de ação** é automaticamente preenchida com um log de todas as ações realizadas na mensagem.

Agora você pode excluir ou atualizar o status da mensagem. Para atualizar o status da mensagem, selecione **Atualizar status** e, então, no campo **Novo status**, selecione **Preparado**. Em seguida, selecione **OK**.

![Atualizar o status da mensagem](media/update-status.png)

O status da mensagem é atualizado para **Preparado** e agora você pode gerar o relatório ao selecionar **Gerar relatório**. O relatório é gerado, e o status da mensagem e o log de ação são atualizados. Para exibir o relatório gerado, selecione o o botão **Anexo** no Painel de Ações.
