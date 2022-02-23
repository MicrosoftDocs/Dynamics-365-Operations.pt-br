---
title: Sistema de mensagens eletrônicas
description: Este tópico contém uma visão geral e informações de configuração de mensagens eletrônicas no Microsoft Dynamics 365 Finance.
author: ShylaThompson
manager: AnnBe
ms.date: 11/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-10-28
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: d4ecc29e47d68129df424c4212505413cf6c8889
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968970"
---
# <a name="electronic-messaging"></a>Mensagens eletrônicas

[!include [banner](../includes/banner.md)]

Este tópico apresenta uma visão geral e informações de mensagens eletrônicas.

Recentemente, as instituições governamentais e as autoridades legislativas de vários países e regiões do mundo implementaram requisitos de relatório para as empresas registradas nesses países ou regiões. A finalidade de requisitos é habilitar os dados que devem ser obtidos das empresas no formato eletrônico, diretamente dos sistemas onde foram contabilizados, armazenados e processados.

A funcionalidade Mensagens eletrônicas do Finance dá suporte a diversos processos de interoperação eletrônica entre o Finance e os sistemas que as autoridades governamentais e legislativas oferecem para relatórios, envios e recebimento de informações oficiais.

A funcionalidade Sistema de mensagens eletrônicas está integrada ao módulo **Relatório Eletrônico** (ER). Portanto, você pode configurar formatos de ER para mensagens eletrônicas. Para obter mais informações, consulte [Relatório eletrônico (ER)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/general-electronic-reporting).

O sistema de mensagens eletrônicas se baseia nestas entidades:

- **Mensagem eletrônica** – um relatório ou uma declaração que deve ser relatados e/ou transmitido internamente. Um exemplo é um relatório que foi enviado para a Secretaria da Receita Federal.
- **Itens da mensagem eletrônica** – os registros a serem incluídos na mensagem que é relatada.
- **Processamento de mensagens eletrônicas** — uma cadeia de ações que devem ser executadas para coletar os dados necessários, gerar relatórios, armazenar dados no armazenamento de Blob do Microsoft Azure, transmitir relatórios para fora do sistema, receber respostas de fora do sistema e, com base nas informações recebidas, atualizar o banco de dados. As ações na cadeia podem ser vinculadas ou desvinculadas

A ilustração a seguir mostra o fluxo de dados do sistema de mensagens eletrônicas.

![Fluxo de dados do sistema de mensagens eletrônicas](media/electronic-messaging-data-flow.png)

A funcionalidade Mensagens eletrônicas dá suporte aos seguintes cenários:

- Criar mensagens manualmente e gerar relatórios com base em formatos de ER de exportação associados de vários tipos: Microsoft Excel, XML, JavaScript Object Notation (JSON), PDF, texto e Microsoft Word.
- Criar e processar automaticamente as mensagens baseadas em informações solicitadas e recebidas de uma autoridade em um formato de ER de importação associado.
- Coletar e processar informações de uma fonte de dados como itens da mensagem. A fonte de dados é uma tabela do Finance.
- Armazene informações adicionais e avalie diversos valores ao chamar as classes executáveis definidas especificamente em relação a mensagens ou a itens de mensagem.
- Agregue as informações coletadas em itens de mensagem, divida essas informações por mensagem e gere relatórios que estejam em formatos de ER de exportação associados.
- Transmita os relatórios gerados para um serviço Web usando as informações de segurança armazenadas no Azure Key Vault.
- Receba uma resposta de um serviço Web, interprete a resposta e atualize os dados no Finance conforme apropriado.
- Armazene e analise todos os relatórios gerados.
- Armazene e analise todas as informações de log relacionadas a ações executadas para uma mensagem ou um item de mensagem.
- Controle o processamento entre vários status de mensagens e status de itens de mensagem.

## <a name="set-up-electronic-messaging"></a>Configurar o sistema de mensagens eletrônicas

O sistema de mensagens eletrônicas pode ajudar você a manter diferentes processos de relatórios eletrônicos para tipos de documento diferentes. Em alguns cenários complexos, o sistema de mensagens eletrônicas é configurado de forma que ele tenha uma combinação de um status de mensagens, status de itens de mensagem, ações, campos adicionais e classes executáveis. Para esses cenários, os pacotes de entidades de dados estão disponíveis para importação. Se usar esses pacotes de entidade de dados, você deverá importá-los para uma entidade legal usando a Ferramenta de gerenciamento de dados. Para obter mais informações sobre como usar a Ferramenta de gerenciamento de dados, consulte [Gerenciamento de dados](../../dev-itpro/data-entities/data-entities-data-packages.md).

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

Configure as sequências numéricas para mensagens e itens de mensagem. As sequências numéricas são usadas para numerar automaticamente as mensagens e os itens de mensagem. Os números atribuídos serão usados como identificadores exclusivos para mensagens e os itens de mensagem no sistema. Você pode configurar sequências numéricas para o sistema de mensagens eletrônicas na página **Parâmetros de contabilidade** (**Contabilidade** \> **Configuração do razão** \> **Parâmetros de contabilidade**).

### <a name="message-item-types-and-statuses"></a>Tipos e status de itens de mensagem

Os tipos de item de mensagem identificam os tipos de registros que serão usados em mensagens eletrônicas. Você pode configurar tipos de item de mensagem na página **Tipos de item de mensagem** (**Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Tipos de item de mensagem**).

Os status de item de mensagem identificam os status que se aplicarão a itens de mensagem no processamento que você está configurando. Você pode configurar tipos de item de mensagem na página **Status de itens de mensagem** (**Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Status de itens de mensagem**).

O parâmetro **Permitir exclusão** de status de um item de mensagem define se os usuários podem excluir itens de mensagens que tenham esse status na página **Mensagens eletrônicas** ou na página **Itens de mensagem eletrônica**.

### <a name="message-statuses"></a>Status de mensagens

Configure os status de mensagens que devem estar disponíveis no processamento de mensagens. Você pode configurar status de mensagens na página **Status de itens de mensagem** (**Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Status de mensagens**).

A tabela a seguir descreve os campos da página **Status de mensagens**.

| Nome do campo          | Descrição |
|---------------------|-------------|
| Status da Mensagem      | Insira um nome exclusivo para o status da mensagem. Os status de mensagens são usados para caracterizar o estado de uma mensagem eletrônica a cada momento. O nome que você inserir será exibido na página **Mensagens eletrônicas** e em um log relacionado às mensagens eletrônicas. |
| Descrição         | Insira uma descrição do status da mensagem. |
| Tipo de resposta       | Selecione o tipo de resposta para o status da mensagem. Algumas ações em um processamento podem produzir mais de um tipo de resposta. Por exemplo, ações do tipo **Serviço Web** pode produzir respostas do tipo **Execução bem-sucedida** ou do tipo **Erro técnico**, dependendo do resultado da execução. Nesse caso, você deve definir os status da mensagem para os dois tipos de resposta. Para obter mais informações sobre tipos de ação e os tipos de resposta relacionados a elas, consulte [Tipos de ação de processamento de mensagens](#message-processing-action-types). |
| Status de item de mensagem | Ocasionalmente, o status de uma mensagem eletrônica deve influenciar o status dos itens relacionados à mensagem. Selecione um status do item de mensagem neste campo para associá-lo com o status da mensagem. |
| Permitir exclusão        | Marque esta caixa de seleção se os usuários puderem excluir mensagens eletrônicas com este status na página **Mensagens eletrônicas** . |

### <a name="additional-fields"></a>Campos adicionais

A funcionalidade Mensagens eletrônicas permite que você preencha registros de uma tabela transacional. Assim, você pode preparar os registros para relatórios e então relatá-los. No entanto, as tabelas transacionais às vezes não têm informações suficientes para preencher registros de uma forma que atenda aos requisitos de relatório. Para preencher todas as informações que devem ser relatadas para um registro, você pode configurar campos adicionais. Os campos adicionais podem ser associados a mensagens e a itens de mensagem. Você pode configurar os campos adicionais na página **Campos adicionais** (**Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Campos adicionais**).

A tabela a seguir descreve os campos gerais da página **Campos adicionais**.

| Campo       | Descrição |
|-------------|-------------|
| Nome do campo  | Insira o nome de um atributo adicional de itens de mensagem relacionados ao processo. Este nome será exibido na interface de usuário (IU) enquanto você trabalha com o processo. Também pode ser usado nas configurações de ER relacionadas ao processo. |
| Descrição | Insira uma descrição do campo adicional. |
| Edição do usuário   | Defina esta opção como **Sim** se os usuários puderem alterar o valor do campo adicional usando a interface do usuário. |
| Contador     | Defina esta opção como **Sim** se o campo adicional deve conter uma sequência numérica em uma mensagem eletrônica. O valor do campo adicional será preenchido automaticamente quando uma ação da **Exportação de relatório eletrônico** for executada. |
| Oculto      | Definir esta opção como **Sim** se o campo adicional deve ficar oculto na interface do usuário. |

Cada campo adicional pode ter valores diferentes para o processamento. Você pode definir esses valores na FastTab **Valores**. A tabela a seguir descreve os campos.

| Campo                | Descrição |
|----------------------|-------------|
| Valor do campo          | Insira o valor do campo a ser usado para uma mensagem ou item de mensagem durante o relatório. |
| Descrição          | Insira uma descrição do valor do campo. |
| Tipo de conta         | Alguns valores de campo podem ser limitados a tipos de conta específicos. Selecione um destes valores: **Tudo**, **Cliente** ou **Fornecedor**. |
| Código da conta         | Se você selecionou **Cliente** ou **Fornecedor** no campo **Tipo de conta** , poderá limitar ainda mais o uso do valor do campo a um grupo ou a uma tabela específica. |
| Número de conta/grupo | Se você tiver selecionado **Cliente** ou **Fornecedor** no campo **Tipo de conta** e se tiver inserido um grupo ou uma tabela no campo **Código de conta**, poderá inserir um grupo ou uma contramedida específico nesse campo. |
| Efetivação            | Especifique a data em que o valor deve começar a ser considerado. |
| Vencimento           | Especifique a data em que o valor deve parar a ser considerado. |

Por padrão, as combinações de critérios que são definidas pelos campos **Número de conta/grupo**, **Código da conta**, **Efetivação** e **Vencimento** não influenciam a seleção de valores para os campos adicionais. No entanto, essas combinações podem ser usadas em uma classe executável para implementar a lógica específica que calcula valores para os campos adicionais.

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

Algumas classes executáveis podem ter parâmetros obrigatórios que devem ser definidos antes que a classe executável seja executada pela primeira vez. Para definir esses parâmetros, selecione **Parâmetros** no Painel de Ação, configure os campos da caixa de diálogo que for exibida, e selecione **OK**. É importante que você selecione **OK**. Caso contrário, os parâmetros não serão salvos no banco de dados, e a classe executável não será chamada corretamente.

### <a name="populate-records-actions"></a>Ações de preencher registros

Você usa ações de preencher registros para configurar ações que adicionam registros à tabela Itens de mensagem para que eles possam ser adicionados a uma mensagem eletrônica. Por exemplo, se a sua mensagem eletrônica tiver que relatar faturas de cliente, você deverá configurar uma ação de preencher registros que esteja vinculada ao campo **Fonte de dados** na tabela Diário de faturas de clientes Você pode configurar ações de preencher registros na página **Ação de preencher registros** (**Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Ações de preencher registros**). Crie um novo registro para cada ação que deverá adicionar registros a tabela e defina os campos a seguir.

| Campo       | Descrição |
|-------------|-------------|
| Nome        | Insira um nome para a ação que preenche registros em seu processo. |
| Descrição | Insira uma descrição da ação de preencher registros. |

Na FastTab **Configuração de fontes de dados**, adicione uma linha para cada fonte de dados usada para o processo e defina os campos a seguir.

| Campo                  | descrição |
|------------------------|-------------|
| Nome                   | Insira um nome para a fonte de dados. |
| Tipo de item de mensagem      | Selecione o tipo de item de mensagem a ser usado quando os registros são criados para a fonte de dados. |
| Tipo de conta           | Selecione o tipo de conta que deve ser associado aos registros da fonte de dados. |
| Nome da tabela mestra      | Selecione a tabela que deve ser uma fonte de dados. |
| Campo de número do documento  | Selecione o campo de onde o número de documento deve ser retirado na tabela selecionada. |
| Campo de data do documento    | Selecione o campo de onde a data de documento deve ser retirada na tabela selecionada. |
| Campo de conta do documento | Selecione o campo de onde a conta de documento deve ser retirada na tabela selecionada. |
| Consulta do usuário             | Se essa caixa de seleção estiver marcada, você poderá configurar uma consulta selecionando **Editar consulta** acima da grade. Caso contrário, todos os registros serão preenchidos a partir da fonte de dados selecionada. |

### <a name="web-applications"></a>Aplicativos Web

Você usa configurações de aplicativo Web para configurar um aplicação Web de modo que ele ofereça suporte ao Open Authorization (OAuth) 2.0. OAuth é o padrão aberto que permite que os usuários concedam "acesso delegado seguro" ao aplicativo em seu nome, sem compartilhar as credenciais de acesso. Você também pode passar pelo processo de autorização obtendo um código de autorização e um token de acesso. Você pode definir configurações de aplicativo Web na página **Aplicativos Web** (**Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Aplicativos Web**).

A tabela a seguir descreve os campos da página **Aplicativos Web**.

| Campo                        | Descrição |
|------------------------------|-------------|
| Nome do aplicativo             | Insira um nome para o aplicativo Web. |
| Descrição                  | Insira uma descrição do aplicativo Web. |
| URL base                     | Insira o endereço de internet básico do aplicativo Web. |
| Caminho da URL de autorização       | Especifique o caminho usado para compor a URL para a autorização. |
| Caminho da URL do token               | Especifique o caminho usado para compor a URL para o token. |
| URL de redirecionamento                 | Insira a URL de redirecionamento. |
| ID do cliente                    | Insira a ID do cliente do aplicativo Web. |
| Segredo do cliente                | Insira o segredo do cliente do aplicativo Web. |
| Token do servidor                 | Insira o token do servidor do aplicativo Web. |
| Mapeamento do formato da autorização | Selecione o formato de ER usado para gerar a solicitação de autorização. |
| Importar mapeamento do modelo do token   | Selecione o mapeamento de modelo de importação ER usado para armazenar o token de acesso. |
| Escopo concedido                | O escopo que é concedido para solicitações ao aplicativo. Este campo é atualizado automaticamente. |
| O token de acesso vai expirar em  | O tempo restante antes que o token de acesso expire. | 
| Aceitar                       | Especifique a propriedade **Aceitar** da solicitação da Web. Por exemplo, insira **application/vnd.hmrc.1.0+json**. |
| Tipo de conteúdo                 | Especifique o tipo de conteúdo. Por exemplo, insira **application/json**. |

Além disso, os seguintes botões estão disponíveis no Painel de Ação da página **Aplicativos Web** para oferecer suporte ao processo de autorização:

- **Obter o código da autorização** — inicialize a autorização do aplicativo Web.
- **Obter o token de acesso** — inicialize o processo de obtenção de um token de acesso.
- **Atualizar o token de acesso** — atualize um token de acesso.

Quando um token de acesso a um aplicativo Web é armazenado no banco de dados do sistema em formato criptografado, ele pode ser usado para solicitações a um serviço Web. Para fins de segurança, o acesso ao token de acesso deve ser limitado às funções de segurança que devem ter permissão para endereçar essas solicitações. Se os usuários fora do grupo de segurança tentarem endereçar uma solicitação, receberão um erro indicando que eles não têm permissão para interoperação por meio do aplicativo Web selecionado. Para configurar as funções de segurança que devem ter acesso ao token de acesso, use a FastTab **Funções de segurança** na página **Aplicativos Web** . Se as funções de segurança não forem definidas para um aplicativo Web, somente um administrador do sistema poderá interoperar por meio desse aplicativo Web.

### <a name="web-service-settings"></a>Configurações de serviço Web

Você usa configurações de serviço Web para configurar a transmissão de dados direta para um serviço Web. Você pode definir configurações de serviço Web na página **Configurações do serviço Web** (**Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Configurações do serviço Web**).

A tabela a seguir descreve os campos da página **Configurações do serviço Web**.

| Campo                          | descrição |
|--------------------------------|-------------|
| Serviço Web                    | Insira um nome para o serviço Web. |
| descrição                    | Insira uma descrição do serviço Web. |
| Endereço na Internet               | Insira o endereço da internet do serviço Web. Se um aplicativo Web for especificado para o serviço Web e se o endereço da Internet do serviço Web for o mesmo que o endereço da Internet definido para esse aplicativo Web, selecione **Copiar a URL base** para copiar a URL base do aplicativo Web neste campo. |
| Certificado                    | Selecione um certificado do Key Vault previamente configurado. |
| Aplicativo Web                | Selecione um certificado do Key Vault previamente configurado. |
| O tipo de resposta - XML        | Defina essa opção como **Sim** se o tipo de resposta for XML. |
| Método de solicitação                 | Especifique o método da solicitação. O HTTP define um conjunto de métodos de solicitação que indicam a ação que deve ser executada para um recurso específico. O método de solicitação pode ser **GET**, **POST** ou outro método HTTP. |
| Cabeçalhos de solicitação                | Especifique cabeçalhos de solicitação. Um cabeçalho de solicitação é um cabeçalho HTTP que pode ser usado em uma solicitação HTTP, e que não está relacionado ao conteúdo da mensagem. |
| Aceitar                         | Especifique a propriedade **Aceitar** da solicitação da Web. |
| Aceitar codificação                | Especifique o valor de **Accept-Encoding**. O cabeçalho HTTP da solicitação Accept-Encoding anuncia a codificação de conteúdo que o cliente pode compreender. Geralmente, a codificação de conteúdo é um algoritmo de compactação. |
| Tipo de conteúdo                   | Especifique o tipo de conteúdo. O cabeçalho HTTP da entidade Content-Type indica o tipo de mídia do recurso. |
| Código de resposta bem-sucedida       | Especifique o código de status HTTP que indica que a solicitação foi bem-sucedida. |
| Mapeamento do formato dos cabeçalhos de solicitação | Selecione o formato de ER usado para gerar os cabeçalhos de solicitação da Web |

### <a name="message-processing-actions"></a>Ações de processamento de mensagens

Você usará as ações de processamento de mensagens para criar ações para os processos e configurar seus parâmetros. Você pode configurar as ações de processamento na página **Ações de processamento de mensagens** (**Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Ações de processamento de mensagens**).

As tabelas a seguir descrevem os campos da página **Ações de processamento de mensagens**.

#### <a name="general-fasttab"></a>FastTab Geral

| Campo                       | descrição |
|-----------------------------|-------------|
| Tipo de ação                 | Selecione o tipo de ação. Para obter informações sobre as opções disponíveis, consulte a seção [Tipos de ação de processamento de mensagens](#message-processing-action-types). |
| Mapeamento de formato              | Selecione o formato de ER a ser chamado para a ação. Esse campo só está disponível para ações dos tipos **Exportação de relatórios eletrônicos**, **Importação de relatórios eletrônicos** e **Mensagem de exportação de relatórios eletrônicos** . |
| Mapeamento do formato para caminho da URL | Selecione o formato de ER a ser chamado para a ação. Esse campo só está disponível para ações do tipo **Serviço Web**. Ele é usado para compor o caminho do endereço da URL que será adicionado ao endereço de Internet básico especificado para o servidor Web selecionado. |
| Tipo de item de mensagem           | Selecione o tipo de registros para os quais a ação deve ser avaliada. Esse campo está disponível para ações dos tipos **Nível de execução do item da mensagem**, **Exportação de relatório eletrônico**, **Importação de relatório eletrônico**, **Serviço Web** e também para alguns outros tipos. Se deixar esse campo em branco, todos os tipos de item da mensagem definidos para o processamento de mensagens são avaliados. |
| Classe executável            | Selecione as configurações de classe executável previamente criadas. Este campo só está disponível para ações dos tipos **Nível de execução de item de mensagem** e **Nível de execução de item de mensagem** . |
| Ação de preencher registros     | Selecione uma ação de preencher registros previamente configurada. Esse campo só está disponível para ações do tipo **Preencher registros**. |
| Serviço Web                 | Selecione um serviço Web previamente configurado. Esse campo só está disponível para ações do tipo **Serviço Web**. |
| Nome do arquivo                   | Especifique o nome do arquivo que será o resultado da ação. Esse arquivo pode ser a resposta do servidor Web ou o relatório que é gerado. Este campo só está disponível para ações dos tipos **Serviço Web** e **Mensagem de exportação de relatório eletrônico**. |
| Mostrar caixa de diálogo                 | Defina esta opção como **Sim** se uma caixa de diálogo deve ser mostrada aos usuários antes da geração do relatório. Este campo só está disponível para ações do tipo **Mensagem de exportação de relatório eletrônico**. |

##### <a name="message-processing-action-types"></a>Tipos de ação de processamento de mensagens

As seguintes opções estão disponíveis no campo **Tipo de ação**:

- **Criar mensagem** — use este tipo de ação para permitir que os usuários criem manualmente mensagens na página **Mensagem eletrônica**. Um status inicial não pode ser configurado para uma ação desse tipo.
- **Preencher registros** — uma ação do tipo **Preencher registros** deve ser previamente configurada. Associe esse tipo de ação com uma ação de preencher registros para permitir que ela seja incluída no processamento. Presume-se que esse tipo de ação seja usado para a primeira ação no processamento de mensagens (quando nenhuma mensagem eletrônica foi criada antecipadamente) ou para uma ação que adiciona itens de mensagem em uma mensagem que foi criada anteriormente por uma ação do tipo **Criar mensagem**. Portanto, para ações desse tipo, um status de resultado pode ser configurado somente para itens de mensagem. Um status inicial pode ser configurado somente para as mensagens.
- **Nível de execução da mensagem** — use esse tipo de ação para configurar uma classe executável que deve ser avaliada no nível da mensagem.
- **Nível de execução do item da mensagem** — use esse tipo de ação para configurar uma classe executável que deve ser avaliada no nível do item da mensagem.
- **Exportação de relatório eletrônico** — use esse tipo de ação para as ações que devem gerar um relatório com base em uma configuração de ER de exportação no nível do item da mensagem.
- **Mensagem de exportação de relatório eletrônico** — use esse tipo de ação para as ações que devem um gerar relatório com base em uma configuração de ER de exportação no nível da mensagem (por exemplo, quando uma mensagem não tiver itens de mensagem).
- **Importação de relatório eletrônico** — use esse tipo de ação para as ações que devem gerar um relatório com base em uma configuração de ER de exportação no nível do item da mensagem.
- **Processamento de usuário de nível de mensagem** — use esse tipo de ação para as ações que supõem algumas ações manuais do usuário no nível de mensagem. Por exemplo, o usuário pode atualizar o status de mensagens.
- **Processamento de usuário** — use esse tipo de ação para as ações que supõem algumas ações manuais do usuário no nível do item da mensagem. Por exemplo, o usuário pode atualizar o status de itens de mensagem.
- **Serviço Web** — use esse tipo de ação para as ações que devem transmitir um relatório gerado para um serviço Web. Esse tipo de ação não é usado para o relatório de comunicação de faturas de compra e venda italiano. Para ações do tipo **Serviço Web**, a página **Ações de processamento de mensagens** inclui uma FastTab **Detalhes diversos**, onde você pode especificar um texto de confirmação. Esse texto de confirmação será exibido para os usuários antes que as solicitações para o serviço Web selecionado sejam endereçadas.
- **Verificação da solicitação** — use esse tipo de ação para solicitar a verificação de um servidor.

#### <a name="initial-statuses-fasttab"></a>FastTab Status iniciais

> [!NOTE]
> A FastTab **Status iniciais** não está disponível para ações que têm um tipo de ação inicial de **Criar mensagem**.

| Campo               | Descrição |
|---------------------|-------------|
| Status de item de mensagem | Selecione o status do item de mensagem para o qual a ação de processamento de mensagens deve ser avaliada. |
| descrição         | Uma descrição do status do item de mensagem selecionado. |

#### <a name="result-statuses-fasttab"></a>FastTab Status de resultados

| Campo               | descrição |
|---------------------|-------------|
| Status da mensagem      | Selecione os status da mensagem para o qual a ação de processamento de mensagens deve ser avaliada. Esse campo só está disponível para ações de processamento de mensagens que são avaliadas no nível da mensagem. Por exemplo, está disponível para tipos de ações **Exportação de relatório eletrônico** e **Importação de relatório eletrônico**, mas não está disponível para tipos de ações **Processamento de usuário** e **Nível de execução do item da mensagem** . |
| descrição         | Uma descrição do status da mensagem selecionada. |
| Tipo de resposta       | O tipo de resposta do status da mensagem selecionada. |
| Status de item de mensagem | Selecione os status resultantes que devem estar disponíveis após a avaliação da ação de processamento de mensagens. Esse campo só está disponível para ações de processamento de mensagens que são avaliadas no nível de item de mensagem. Por exemplo, está disponível para as ações dos tipos **Processamento de usuário** e **Nível de execução de item de mensagem**. Para ações de processamento de mensagens que são avaliadas no nível da mensagem, esse campo mostra o status do item de mensagem que foi configurado para o status da mensagem selecionado. |

A tabela a seguir mostra os status dos resultados que devem ser configurados para diferentes tipos de ação e tipos de resposta.

| Tipo de ação/resposta de mensagem eletrônica | Execução bem-sucedida | Erro de negócios | Erro técnico | Definido pelo Usuário | Cancelar |
|----------------------------------------------|-----------------------|----------------|-----------------|--------------|--------|
| Criar mensagem                               | X                     |                |                 |              |        |
| Exportação de relatório eletrônico                  | X                     |                |                 |              |        |
| Importação de relatório eletrônico                  |                       |                |                 |              |        |
| Serviço Web                                  | X                     |                | X               |              |        |
| Processamento do usuário                              |                       |                |                 |              |        |
| Nível de execução da mensagem                      |                       |                |                 |              |        |
| Preencher registros                             |                       |                |                 |              |        |
| Nível de execução do item da mensagem                 |                       |                |                 |              |        |
| Verificação da solicitação                         | X                     | X              | X               |              |        |
| Mensagem de exportação de relatório eletrônico          | X                     |                |                 |              |        |
| Processamento de usuário de nível de mensagem                |                       |                |                 |              |        |

### <a name="electronic-message-processing"></a>Processamento de mensagem eletrônica

O processamento de mensagens eletrônicas é um conceito básico da funcionalidade Mensagens eletrônicas. Agrega ações que devem ser avaliadas para a mensagem eletrônica. As ações que podem ser vinculadas por meio de um status inicial e um status de resultado. Alternativamente, as ações do tipo **Processamento de usuário** podem ser iniciadas de forma independente. Na página **Processamento de mensagens eletrônica** (**Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Processamento de mensagem eletrônica**), é possível selecionar os campos adicionais que devem ter suporte para o processamento no nível da mensagem ou no nível dos itens da mensagem.

A FastTab **Ação** permite adicionar ações predefinidas ao processamento. Você pode especificar se uma ação deve ser executada separadamente, ou se ela pode ser iniciada pelo processamento. Para especificar que uma ação no processamento pode ser inicializada somente por um usuário, defina o campo **Executar separadamente** como **Sim** para essa ação. Se uma ação deve ser iniciada pelo processamento de mensagens ou itens de mensagem que estão no status que foi definido como o status inicial para a ação, defina o campo **Executar separadamente** como **Não**. Ações do tipo **Ação do usuário** devem sempre ser executadas separadamente.

Às vezes, várias ações devem ser agregadas em uma sequência, mesmo que a primeira ação esteja configurada de forma que seja executada separadamente. Por exemplo, um usuário deve inicializar a geração de relatórios, mas, imediatamente após a geração do relatório, ele deverá ser enviado para um serviço Web, e a resposta do serviço Web deverá ser refletida no sistema. Nessa situação, você pode criar uma sequência inseparável para as ações que devem ser sempre executadas juntas. Na FastTab **Ação**, selecione **Sequências inseparáveis** acima da grade e crie uma sequência. Em seguida, para todas as ações que devem ser executadas juntas, selecione a sequência no campo **Sequência inseparável** . Nesse caso, o campo **Executar separadamente** pode ser definido como **Sim** para a primeira ação na sequência, mas como **Não** para todas as outras ações.

A FastTab **Campos adicionais do item de mensagem** permite adicionar os campos adicionais predefinidos relacionados a itens de mensagem. Você deve adicionar outros campos para cada tipo de item de mensagem ao qual os campos estão relacionados.

A FastTab **Campos adicionais da mensagem** permite adicionar outros campos predefinidos relacionados a mensagens.

A FastTab **Funções de segurança** permite que você configure as funções de segurança predefinidas no sistema para processamento específico. Os usuários com uma função específica verão apenas o processamento definido para a função.

A FastTab **Lote** permite que você configure o processamento para funcionar em um regime de lote.

## <a name="work-with-the-electronic-messages-functionality"></a>Trabalhar com a funcionalidade Mensagens eletrônicas

Se você estiver trabalhando no nível da mensagem, a página **Mensagens eletrônicas** (**Imposto** \> **Consultas e relatórios** \> **Mensagens eletrônicas** \> **Mensagens eletrônicas**) é mais útil. Se você estiver operando no nível da coleta de dados (item de mensagem), a página **Itens de mensagem eletrônica** (**Imposto** \> **Consultas e relatórios** \> **Mensagens eletrônicas** \> **Itens de mensagem eletrônica**) é mais útil.

### <a name="electronic-messages"></a>Mensagens eletrônicas

A página **Mensagens eletrônicas** apresenta o processamento que está disponível para você, com base em sua função. As funções de segurança estão associadas ao processamento na configuração desse processamento. Para cada processamento disponível para você, a página mostra mensagens eletrônicas e informações relacionadas a ele.

A FastTab **Mensagens** mostra mensagens eletrônicas para o processamento selecionado. Dependendo do status da mensagem selecionada e do processamento predefinido, você pode executar algumas ações usando os botões acima da grade:

- **Novo** – esse botão está associado a ações do tipo **Criar mensagem**.
- **Excluir** – esse botão estará disponível se a caixa de seleção **Permitir exclusão** estiver marcada para o status atual da mensagem selecionada.
- **Coletar dados** — esse botão está associado com ações do tipo **Preencher registros**.
- **Gerar relatório** – esse botão está associado a ações do tipo **Mensagem de exportação de relatórios eletrônicos**.
- **Enviar relatório** – esse botão está associado a ações do tipo **Serviço Web**.
- **Importar a resposta** — esse botão está associado com ações do tipo **Importação de relatório eletrônico**.
- **Status da atualização** – esse botão está associado a ações do tipo **Processamento de usuário no nível da mensagem**.
- **Itens de mensagem** – abra a página **Itens de mensagem eletrônica**.

A FastTab **Log de ação** mostra informações sobre todas as ações executadas para a mensagem selecionada. Se uma ação causar em um erro, as informações sobre o erro serão anexadas à linha relacionada na grade. Para examinar as informações sobre o erro, selecione a linha na grade, selecione o botão **Anexo** (o símbolo de clipe de papel) no canto superior direito na página.

A FastTab **Campos adicionais da mensagem** mostra todos os campos adicionais definidos para mensagens na configuração de processamento. Também mostra os valores desses campos adicionais.

A FastTab **Itens de mensagem** mostra todos os itens de mensagem relacionados à mensagem selecionada. Dependendo do status do item de mensagem selecionado, você pode executar algumas ações usando os botões acima da grade:

- **Excluir** – Este botão estará disponível se a caixa de seleção **Permitir exclusão** estiver marcada para o o status atual do item de mensagem selecionado.
- **Status da atualização** – Este botão está associado a ações do tipo **Processamento do usuário**.
- **Documento original** — abre uma página que exibe o documento original para o item de mensagem selecionado.

Todos os relatórios que já foram já gerados e recebidos de uma mensagem são anexados à mensagem. Para examinar os anexos relacionados a uma mensagem, selecione a mensagem, selecione o botão **Anexo** (o símbolo de clipe de papel) no canto superior direito da página.

![Botão Anexo](media/attachment-icon.png)

A página **Anexos** mostra todos os anexos relacionados à mensagem selecionada. Para exibir um arquivo, selecione-o na lista à esquerda e então selecione **Abrir** no Painel de Ações.

![Botão Abrir](media/open-button.png)

Você também pode examinar os anexos relacionadas a uma ação específica que foi executada anteriormente para uma mensagem. Na página **Mensagens eletrônicas**, selecione a mensagem na FastTab **Mensagens**, selecione a ação na FastTab **Log de ações** e selecione o botão **Anexo** no canto superior direito da página.

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
<td>O número da conta de um cliente ou fornecedor (ou outro valor de campo, dependendo do campo definido na ação de preencher registros). Esse campo só poderá ser preenchido automaticamente quando uma fatura for adicionada à tabela Itens de mensagem.</td>
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
<td>As próxima ações que podem ser iniciadas para o status atual do item da mensagem.</td>
</tr>
</tbody>
</table>

A guia **Campos adicionais** mostra os campos adicionais para o item de mensagem selecionado e seus valores.

#### <a name="run-processing"></a>Executar processamento

Selecione **Executar processamento** no Painel de Ações para executar o processamento para itens de mensagem. Para executar uma ação específica, na caixa de diálogo **Executar processamento** , defina a opção **Escolher ação** como **Sim**, e selecione uma ação. Para executar o processamento inteiro, deixe a opção **Escolher ação** definida como **Não**.

#### <a name="generate-report"></a>Gerar relatório

Selecione **Gerar relatório** no Painel de Ações para gerar um relatório. Esse botão está associado a ações do tipo **Exportação de relatórios eletrônicos**.

#### <a name="update-status"></a>Atualizar Status

Selecione **Atualizar status** no Painel de Ações para atualizar o status de um ou mais itens de mensagem. Na caixa de diálogo **Atualizar status**, use a FastTab **Registros a serem incluídos** para selecionar os itens de mensagem a serem atualizados. Cerifique-se de definir corretamente os critérios de seleção, porque os status de itens de mensagem serão atualizados de acordo com esses critérios, o status inicial da ação selecionada e o valor de **Novo status** que você especificar. Depois que uma atualização de status for concluída, será difícil determinar quais itens foram atualizados. Portanto, será difícil reverter a atualização de status.

#### <a name="electronic-messages"></a>Mensagens eletrônicas

Selecione **Mensagens eletrônicas** no Painel de Ação para examinar uma mensagem eletrônica que esteja relacionada ao item de mensagem selecionado.

Você também pode examinar todos os arquivos relacionados a um item de mensagem específico. Selecione o campo **Mensagem** no item da mensagem ou selecione **Mensagens eletrônicas** no Painel de Ação. Na página **Mensagem eletrônica**, selecione a mensagem para examinar os arquivos e selecione o botão **Anexo** (o símbolo de clipe de papel) no canto superior direito da página.

![Botão Anexo](media/attachment-icon.png)

A página **Anexos** mostra todos os anexos relacionados à mensagem. Para exibir um arquivo, selecione-o na lista à esquerda e então selecione **Abrir** no Painel de Ações.

![Botão Abrir](media/open-button.png)

#### <a name="original-document"></a>Documento original

Selecione **Documento original** no Painel de Ações para abrir o documento original para o item de mensagem selecionado.

## <a name="example-set-up-and-run-processing-to-call-a-simple-er-exporting-format-to-generate-an-excel-report"></a>Exemplo: configurar e executar processamento para chamar um formato de exportação de ER simples para gerar um relatório do Excel

Depois de criar seu formato de ER, o mapear para fontes de dados e o concluir, você poderá executá-lo usando o espaço de trabalho **Relatórios eletrônicos**. É gerado um relatório, e você pode salvá-lo localmente.

Para controlar os seguintes aspectos do processo de relatórios, você deverá configurar o processamento de mensagens eletrônicas:

- Registre em log informações sobre quem gerou o relatório.
- Registre em log informações sobre quando o relatório foi gerado.
- Salve os relatórios que foram gerados para períodos anteriores.

Essa seção fornece um exemplo que mostra como é possível configurar mensagens eletrônicas para gerar um relatório baseado em um formato de ER de exportação para o Excel. Se quiser seguir este exemplo, o formato de exportação do Excel de ER já deve ter sido criado, mapeado para as fontes de dados e concluído. Além disso, uma sequência numérica já deverá ter ser configurada para mensagens eletrônicas.

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
    - Na FastTab **Status de resultados**, adicione uma linha separada para cada um dos dois status de mensagem (**Preparado** e **Novo**). Para ambas as linhas, defina o campo **Tipo de resposta** como **Execução bem-sucedida**.

#### <a name="electronic-message-processing"></a>Processamento de mensagem eletrônica

Neste exemplo, todas as ações devem ser configurados de forma que sejam executadas separadamente. A suposição é que cada usuário inicializará cada ação.

1. Vá para **Imposto \> Configuração \> Mensagens eletrônicas \> Processamento de mensagens eletrônicas**.
2. Adicione um registro para o processamento e adicione todas as ações definidas anteriormente e um campo adicional.
3. Opcional: na FastTab **Funções de segurança**, defina funções de segurança para que seu processamento limite o acesso para o relatório específico.
4. Vá para **Imposto \> Consultas e relatórios \> Mensagens eletrônicas \> Mensagens eletrônicas**.
5. Selecione **Nova** para criar uma mensagem. Nesse ponto, você pode adicionar datas e uma descrição. Você também pode atualizar o valor do campo adicional como necessário.

    ![Criar uma mensagem eletrônica](media/create-electronic-message.png)

A grade da FastTab **Log de ação** é automaticamente preenchida com um log de todas as ações realizadas na mensagem.

Agora você pode excluir ou atualizar o status da mensagem. Para atualizar o status da mensagem, selecione **Atualizar status**. No campo **Novo status** , selecione **Preparado** e, em seguida, **OK**.

![Atualizar o status da mensagem](media/update-status.png)

O status da mensagem é atualizado para **Preparado** e agora você pode gerar o relatório ao selecionar **Gerar relatório**. O relatório é gerado, e o status da mensagem e o log de ação são atualizados. Para exibir o relatório gerado, selecione o botão **Anexo** (o símbolo de clipe de papel) no canto superior direito da página.
