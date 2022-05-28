---
title: Configurar Mensagens eletrônicas
description: Este tópico fornece informações sobre como configurar a funcionalidade Mensagens eletrônicas (EM).
author: liza-golub
ms.date: 11/18/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2021-06-23
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 652d8684473d1c1505a80eb1d860c57a214b9488
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2022
ms.locfileid: "8734209"
---
# <a name="set-up-electronic-messages"></a>Configurar Mensagens eletrônicas

[!include [banner](../includes/banner.md)]

A funcionalidade **Mensagens eletrônicas** (EM) ajuda você a manter diferentes processos de relatórios eletrônicos para diferentes tipos de documento. Em alguns cenários complexos que oferecem suporte a [recursos de relatórios específicos do país/região](electronic-messaging.md#country-specific-regulatory-features-supported-by-the-em-functionality), a funcionalidade EM é configurada de forma que ela tenha uma combinação de vários status de mensagens, status de itens de mensagem, ações, campos adicionais e classes executáveis. Para esses cenários, os pacotes de entidades de dados estão disponíveis para importação. Se usar esses pacotes de entidade de dados, importe-os para uma entidade legal usando a ferramenta Gerenciamento de dados. Para obter mais informações sobre como usar a Ferramenta de gerenciamento de dados, consulte [Gerenciamento de dados](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).

Se não importar um pacote de entidades de dados, você poderá configurar a funcionalidade EM manualmente. Nesse caso, você deve configurar os seguintes elementos:

- [Sequências numéricas](#sequences)
- [Tipos de item de mensagem](#types)
- [Status de itens de mensagem](#item)
- [Status de mensagens](#statuses)
- [Campos adicionais](#additional)
- [Configurações de classe executável](#executable)
- [Ações de preencher registros](#populate)
- [Preencher registros de várias empresas](#multiple-companies-populate)
- [Aplicativos Web](#applications)
- [Configurações de serviço Web](#settings)
- [Ações de processamento de mensagens](#actions)
- [Processamento de mensagem eletrônica](#processing)

As seções a seguir fornecem mais informações sobre cada um desses elementos.

## <a name="number-sequences"></a><a id="sequences"></a>Sequências numéricas

Configure as sequências numéricas para mensagens e itens de mensagem. As sequências numéricas são então usadas para numerar automaticamente as mensagens e os itens de mensagem. Os números atribuídos são usados como identificadores exclusivos para as mensagens e os itens de mensagem no sistema. É possível configurar sequências numéricas para as mensagens eletrônicas acessando **Contabilidade** \> **Configuração do razão** \> **Parâmetros da contabilidade**.

## <a name="message-item-types"></a><a id="types"></a>Tipos de item de mensagem

Os tipos de item de mensagem identificam os tipos de registros que são usados nas mensagens eletrônicas. É possível configurar tipos de item de mensagem acessando **Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Tipos de item de mensagem**.

## <a name="message-item-statuses"></a><a id="item"></a>Status de itens de mensagem

Os status de itens de mensagem identificam os status que se aplicam aos itens de mensagem no processamento que você está configurando. É possível configurar os status de item de mensagem acessando **Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Status de itens de mensagem**.

O parâmetro **Permitir exclusão** de um status de item de mensagem define se você pode excluir itens de mensagens que tenham esse status na página **Mensagens eletrônicas** ou na página **Itens de mensagem eletrônica**.

## <a name="message-statuses"></a><a id="statuses"></a>Status de mensagens

Configure os status de mensagens que devem estar disponíveis no processamento de mensagens. É possível configurar os status das mensagens acessando **Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Status de mensagens**.

A tabela a seguir descreve os campos da página **Status de mensagens**.

| Nome do campo          | Descrição |
|---------------------|-------------|
| Status da Mensagem      | Insira um nome exclusivo para o status da mensagem. Os status de mensagens são usados para caracterizar o estado de uma mensagem eletrônica a cada momento. O nome que você inserir será exibido na página **Mensagens eletrônicas** e em um log relacionado às mensagens eletrônicas. |
| Descrição         | Insira uma descrição do status da mensagem. |
| Tipo de resposta       | Selecione o tipo de resposta para o status da mensagem. Algumas ações em um processamento podem produzir mais de um tipo de resposta. Por exemplo, uma ação do tipo **Serviço Web** pode produzir respostas do tipo **Executado com êxito** ou do tipo **Erro técnico**, dependendo do resultado da execução. Nesse caso, defina os status da mensagem para os dois tipos de resposta. Para obter mais informações sobre tipos de ação e os tipos de resposta relacionados a elas, consulte os [Tipos de ação de processamento de mensagens](#action-types). |
| Status de item de mensagem | Ocasionalmente, o status de uma mensagem eletrônica deve influenciar o status dos itens relacionados à mensagem. Selecione um status do item de mensagem neste campo para associá-lo com o status da mensagem. |
| Permitir exclusão        | Marque esta caixa de seleção se os usuários puderem excluir mensagens eletrônicas com este status na página **Mensagens eletrônicas** . |

## <a name="additional-fields"></a><a id="additional"></a>Campos adicionais

A funcionalidade EM permite que você colete registros de tabelas transacionais no Microsoft Dynamics 365 Finance como itens de mensagem. Assim, você pode preparar os registros para relatórios e então relatá-los. No entanto, as tabelas transacionais às vezes não têm informações suficientes para preencher registros de uma forma que atenda aos requisitos de relatório. Para preencher todas as informações que devem ser relatadas para um registro, você pode configurar campos adicionais. Os campos adicionais podem ser associados a mensagens e a itens de mensagem. É possível configurar campos adicionais acessando **Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Campos adicionais**.

A tabela a seguir descreve os campos gerais da página **Campos adicionais**.

| Campo       | descrição |
|-------------|-------------|
| Nome do campo  | Insira o nome de um campo adicional para mensagens eletrônicas ou itens de mensagem relacionados ao processo. Este nome será exibido na interface de usuário (IU) enquanto você trabalha com o processo. O nome também pode ser usado nas configurações de Relatório Eletrônico (ER) relacionadas ao processo. |
| descrição | Insira uma descrição do campo adicional. |
| Edição do usuário   | Defina esta opção como **Sim** se os usuários puderem alterar o valor do campo adicional na interface do usuário. |
| Contador     | Defina esta opção como **Sim** se o campo adicional deve conter uma sequência numérica em uma mensagem eletrônica. O valor do campo adicional será preenchido automaticamente quando uma ação do tipo **Exportação de relatório eletrônico** for executada. |
| Oculto      | Defina esta opção como **Sim** se o campo adicional deve ficar oculto na interface do usuário na página **Mensagens eletrônicas** ou na página **Itens de mensagem eletrônica**. |

Na Guia Rápida **Valores**, você pode predefinir os valores que um campo adicional pode ter. Esses valores ficarão disponíveis para seleção pelos usuários. Portanto, eles não precisarão ser preenchidos manualmente durante o processamento. A tabela a seguir descreve os campos.

| Campo                | descrição |
|----------------------|-------------|
| Valor do campo          | Insira o valor do campo a ser usado para uma mensagem ou item de mensagem durante o relatório. |
| Descrição          | Insira uma descrição do valor do campo. |
| Tipo de conta         | Alguns valores de campo podem ser limitados a tipos de conta específicos. Selecione um destes valores: **Tudo**, **Cliente** ou **Fornecedor**. |
| Código da conta         | Se você selecionou **Cliente** ou **Fornecedor** no campo **Tipo de conta** , poderá limitar ainda mais o uso do valor do campo a um grupo ou a uma tabela específica. |
| Número de conta/grupo | Se você tiver selecionado **Cliente** ou **Fornecedor** no campo **Tipo de conta** e se tiver inserido um grupo ou uma tabela no campo **Código de conta**, poderá inserir um grupo ou uma contramedida específico nesse campo. |
| Efetivação            | Especifique a data em que o valor deve começar a ser considerado. |
| Vencimento           | Especifique a data em que o valor deve parar a ser considerado. |

Por padrão, as combinações de critérios que são definidas pelos campos **Número de conta/grupo**, **Código da conta**, **Efetivação** e **Vencimento** não influenciam a seleção de valores para os campos adicionais. No entanto, essas combinações podem ser usadas em uma classe executável para implementar a lógica específica que calcula valores para os campos adicionais.

## <a name="executable-class-settings"></a><a id="executable"></a>Configurações de classe executável

Uma classe executável é um método ou uma classe X++ que o processamento de mensagens eletrônicas pode chamar em relação a uma ação se alguma avaliação for necessária para o processo.

É possível configurar manualmente uma classe executável que deve ser chamada durante o processamento, acessando **Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Configurações de classe executável**. Na página **Configurações de classe executável**, crie uma linha e defina os campos a seguir.

| Campo                 | descrição |
|-----------------------|-------------|
| Classe executável      | Insira o nome que será usado durante a instalação de uma ação de processamento de mensagens em relação à qual essa classe é chamada. |
| descrição           | Insira uma descrição da classe executável. |
| Nome de classe executável | Selecione uma classe executável X++. |
| Nível de execução       | Esse campo é automaticamente configurado porque o valor está predefinido para a classe executável selecionada. Esse campo limita o nível em que a avaliação relacionada é executada. |
| Descrição da classe     | Esse campo é automaticamente configurado porque o valor está predefinido para a classe executável selecionada. |
| Tipo de ação           | Esse campo está disponível quando o recurso **Tipo de ação de classe executável da \[EM\]** está ativado no espaço de trabalho **Gerenciamento de recursos**. Use esse campo para especificar o tipo de ação para a classe executável. Esse campo fornece controle mais preciso sobre as próximas ações que estão disponíveis para a mensagem eletrônica na página **Mensagens eletrônicas**. |

Algumas classes executáveis podem ter parâmetros obrigatórios que devem ser definidos antes que a classe executável seja executada pela primeira vez. Para definir esses parâmetros, no Painel de Ações, selecione **Parâmetros**. Na caixa de diálogo exibida, defina os campos e selecione **OK**. É importante que você selecione **OK**. Caso contrário, os parâmetros não serão salvos no banco de dados, e a classe executável não será chamada corretamente.

## <a name="populate-records-actions"></a><a id="populate"></a>Ações de preencher registros

Você usa ações de preencher registros para configurar ações que adicionam registros à tabela Itens de mensagem para que eles possam ser adicionados a uma mensagem eletrônica. Por exemplo, se a sua mensagem eletrônica tiver que relatar faturas de cliente, você deverá configurar uma ação de preencher registros que esteja vinculada ao campo **Fonte de dados** na tabela Diário de faturas de clientes

É possível configurar ações de preencher registros acessando **Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Ações de preencher registros**. Crie um novo registro para cada ação que deverá adicionar registros a tabela e defina os campos a seguir.

| Campo       | Descrição |
|-------------|-------------|
| Nome        | Insira um nome para a ação que preenche registros em seu processo. |
| Descrição | Insira uma descrição da ação de preencher registros. |

Na FastTab **Configuração de fontes de dados**, adicione uma linha para cada fonte de dados usada para o processo e defina os campos a seguir.

| Campo                  | descrição |
|------------------------|-------------|
| Nome                   | Insira um nome para a fonte de dados. |
| Tipo de item de mensagem      | Selecione o tipo de item de mensagem a ser usado quando os registros forem criados para a fonte de dados. |
| Tipo de conta           | Selecione o tipo de conta a ser associada aos registros da fonte de dados. |
| Nome da tabela mestra      | Selecione a tabela que deverá ser uma fonte de dados. |
| Campo de número do documento  | Selecione o campo de onde o número do documento será retirado na tabela mestra selecionada. O valor desse campo será usado como o valor do campo **Número do documento** para o item da mensagem. |
| Campo de data do documento    | Selecione o campo de onde a data do documento será retirada na tabela mestra selecionada. O valor desse campo será usado como o valor do campo **Data do item de mensagem** para o item da mensagem. |
| Campo de conta do documento | Selecione o campo de onde a conta do documento será retirada na tabela mestra selecionada. O valor desse campo será usado como o valor do campo **Número da conta** para o item da mensagem. |
| Empresa                | Esse campo está disponível quando o recurso **Consultas interempresariais para ações de preencher registros** está ativado no espaço de trabalho **Gerenciamento de recursos**. Use este recurso para configurar fontes de dados entre empresas para as ações de preencher registros. Os dados podem ser obtidos de várias empresas. |
| Consulta do usuário             | <p>Se você configurar uma consulta selecionando **Editar consulta** acima da grade e especificar os critérios que devem ser aplicados à tabela mestra selecionada da qual os dados são preenchidos, esta caixa de seleção será marcada automaticamente. Caso contrário, todos os registros serão preenchidos a partir da tabela mestra selecionada.</p><p>Quando o recurso **Consultas interempresariais para ações de preencher registros** está ativado no espaço de trabalho **Gerenciamento de recursos** e os registros devem ser coletados de várias empresas, adicione uma linha para cada entidade legal adicional que deve ser incluída no relatório. Para cada nova linha, selecione **Editar consulta** e especifique um critério relacionado que seja específico para a entidade legal especificada no campo **Empresa** na linha. Quando terminar, a grade de **Configuração de fontes de dados** conterá linhas para todas as entidades legais que devem ser incluídas no relatório.</p> |

## <a name="populate-records-from-multiple-companies"></a><a id="multiple-companies-populate"></a>Preencher registros de várias empresas

Se a sua empresa dever relatar várias pessoas jurídicas no mesmo banco de dados de Finanças, configure a opção [preencher ações de registros](#populate) para todas as pessoas jurídicas das quais os dados devem ser incluídos no relatório.

Para habilitar esta capacidade no ambiente de Finanças, siga estas etapas. 

1. Acesse **Espaços de trabalho** \> **Gerenciamento de recursos**.
2. Localize e selecione as **Consultas interempresariais para o recurso de ações de preencher registros** na lista.
3. Selecione **Habilitar agora**. 

Para configurar as ações de [preencher registros](#populate) para várias empresas das quais os dados devem ser incluídos no relatório, siga estas etapas.

1. Acesse **Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Ações de preencher registros**.

    Quando o recurso **Consultas interempresariais para as ações de preencher registros** está habilitada, a grade de **Configuração de fontes de dados** na página **Ação de preencher registros** inclui um campo **Empresa**. Para os registros existentes que foram criados durante a configuração geral das [ações de preencher registros](#populate), este campo mostra o identificador da entidade legal atual.

2. Na grade **Configuração de fontes de dados**, adicione uma linha para cada entidade legal da subsidiária que deve ser incluída no relatório e defina os campos a seguir.

    | Nome do campo             | Valor |
    |------------------------|-------|
    | Nome                   | Insira um texto que o ajudará a compreender a origem deste registro. Por exemplo, insira um **Nome para a fonte de dados - Subsidiária 1**. |
    | Tipo de item de mensagem      | Selecione o tipo de item de mensagem necessário para o processamento de EM. |
    | Tipo de conta           | Especifique o tipo de conta necessário para o processamento de EM. Se o processamento de EM não tiver tipos de conta específicos, selecione **Todos**. |
    | Nome da tabela mestra      | Especifique o nome da tabela mestra necessária para o processamento de EM. |
    | Campo de número do documento  | Especifique o campo que contém o número do documento em registros de seu processamento de EM. |
    | Campo de data do documento    | Especifique o campo que contém a data do documento em registros de seu processamento de EM. |
    | Campo de conta do documento | Especifique o campo que contém a conta do documento em registros de seu processamento de EM. |
    | Empresa                | Selecione o ID da entidade legal da subsidiária. |
    | Consulta do usuário             | Esta caixa de seleção é selecionada automaticamente quando você define critérios selecionando **Editar consulta**. |

3. Para cada nova linha, selecione **Editar consulta** e especifique os critérios relacionados para a entidade legal especificada no campo **Empresa** na linha.

## <a name="web-applications"></a><a id="applications"></a>Aplicativos Web

Use configurações de aplicativo Web para configurar um aplicativo Web de modo que ele ofereça suporte ao Open Authorization (OAuth) 2.0. OAuth é o padrão aberto que permite que os usuários concedam "acesso delegado seguro" ao aplicativo em seu nome, sem compartilhar as credenciais de acesso. Você também pode passar pelo processo de autorização obtendo um código de autorização e um token de acesso. É possível definir configurações de aplicativo Web acessando **Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Aplicativos Web**.

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
| O token de acesso vai expirar em  | O tempo restante antes que o token de acesso expire. Este campo é atualizado automaticamente. | 
| Aceitar                       | Especifique a propriedade **Aceitar** da solicitação da Web. Por exemplo, insira **application/vnd.hmrc.1.0+json**. |
| Tipo de conteúdo                 | Especifique o tipo de conteúdo. Por exemplo, insira **application/json**. |

Além disso, os seguintes botões estão disponíveis no Painel de Ação da página **Aplicativos Web** para oferecer suporte ao processo de autorização:

- **Obter o código da autorização** — inicialize a autorização do aplicativo Web. Esta função usa o formato ER especificado no campo **Mapeamento do formato da autorização** para gerar uma solicitação de autorização.
- **Obter o token de acesso** — inicialize o processo de obtenção de um token de acesso.
- **Atualizar o token de acesso** — atualize um token de acesso. Esta função usa o formato ER especificado no campo **Importar mapeamento do modelo do token** para importar informações sobre o token de acesso recebido.

Quando um token de acesso a um aplicativo Web é armazenado no banco de dados do sistema em formato criptografado, ele pode ser usado para solicitações a um serviço Web. Para fins de segurança, o acesso ao token deve ser limitado às funções de segurança que têm permissão para atender a essas solicitações. Se alguém fora do grupo de segurança tentar atender a uma solicitação, a pessoa receberá um erro indicando que ela não têm permissão para interoperar usando o aplicativo Web selecionado. Para configurar as funções de segurança com acesso ao token de acesso, use a Guia Rápida **Funções de segurança** na página **Aplicativos Web** . Se as funções de segurança não forem definidas para um aplicativo Web, somente um administrador do sistema poderá interoperar usando o aplicativo Web.

Para cada ação com o aplicativo Web selecionado, a Guia Rápida **Log de ações** salva as informações sobre o usuário, a data e a hora.

Alguns serviços Web podem exigir que diferentes cabeçalhos sejam incluídos nas solicitações. O administrador do sistema pode configurar cabeçalhos adicionais e seus valores na Guia Rápida **Cabeçalhos suplementares** e usá-los durante a geração da solicitação.

## <a name="web-service-settings"></a><a id="settings"></a>Configurações de serviço Web

Use configurações de serviço Web para configurar a transmissão direta de dados para um serviço Web. É possível definir configurações de serviço Web acessando **Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Configurações de serviço Web**.

A tabela a seguir descreve os campos da página **Configurações do serviço Web**.

| Campo                          | descrição |
|--------------------------------|-------------|
| Serviço Web                    | Insira um nome para o serviço Web. |
| descrição                    | Insira uma descrição do serviço Web. |
| Endereço na Internet               | <p>Insira o endereço da internet do serviço Web. Se um aplicativo Web for especificado para o serviço Web e se o endereço da Internet do serviço Web for o mesmo que o endereço da Internet definido para esse aplicativo Web, selecione **Copiar a URL base**. A URL base do aplicativo Web será copiada para este campo.</p><p>**Aviso:** serviços de terceiros ou outros serviços configurados aqui não exigem certificação e podem não atender aos padrões de privacidade da Microsoft. Você deve examinar a documentação de privacidade de cada serviço e trabalhar com cada provedor de serviços para saber mais sobre o nível de conformidade que seu serviço oferece. Você é responsável por garantir que esses serviços atendam à sua segurança, à privacidade e aos padrões legais. Você assume o risco de usar os serviços. A Microsoft não oferece nenhuma garantia ou condições expressas. É altamente recomendável que você use somente serviços que forneçam conexões seguras e autorizadas, como HTTPS.</p> |
| Certificado                    | Selecione um certificado do Azure Key Vault previamente configurado. |
| Aplicativo Web                | Selecione um aplicativo Web previamente configurado. |
| O tipo de resposta - XML        | Defina essa opção como **Sim** se o tipo de resposta for XML. |
| Método de solicitação                 | Especifique o método da solicitação. O HTTP define um conjunto de métodos de solicitação que indicam a ação que deve ser executada para um recurso específico. O método de solicitação pode ser **GET**, **POST** ou outro método HTTP. |
| Cabeçalhos de solicitação                | Especifique cabeçalhos de solicitação. Um cabeçalho de solicitação é um cabeçalho HTTP que pode ser usado em uma solicitação HTTP. Ele não está relacionado ao conteúdo da mensagem. |
| Aceitar                         | Especifique a propriedade de aceitação da solicitação da Web. |
| Aceitar codificação                | Especifique o valor de accept-encoding. O cabeçalho HTTP da solicitação Accept-Encoding anuncia a codificação de conteúdo que o cliente pode compreender. Geralmente, a codificação de conteúdo é um algoritmo de compactação. |
| Tipo de conteúdo                   | Especifique o tipo de conteúdo. O cabeçalho HTTP da entidade Content-Type indica o tipo de mídia do recurso. |
| Código de resposta bem-sucedida       | Especifique o código de status HTTP que indica que a solicitação foi bem-sucedida. |
| Mapeamento do formato dos cabeçalhos de solicitação | Selecione o formato de ER usado para gerar os cabeçalhos de solicitação da Web |

## <a name="message-processing-actions"></a><a id="actions"></a>Ações de processamento de mensagens

Você usará as ações de processamento de mensagens para criar ações para os processos e configurar seus parâmetros. É possível configurar ações de processamento de mensagens acessando **Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Ações de processamento de mensagens**.

As tabelas a seguir descrevem os campos da página **Ações de processamento de mensagens**.

### <a name="general-fasttab"></a>FastTab Geral

| Campo                                     | descrição |
|-------------------------------------------|-------------|
| Tipo de ação                               | Selecione o tipo de ação. Para obter informações sobre as opções disponíveis, consulte a seção [Tipos de ação de processamento de mensagens](#action-types) posteriormente neste tópico. |
| Mapeamento de formato                            | Selecione o formato de ER a ser chamado para a ação. Esse campo só está disponível para ações dos tipos **Exportação de relatórios eletrônicos**, **Importação de relatórios eletrônicos** e **Mensagem de exportação de relatórios eletrônicos** . |
| Mapeamento do formato para caminho da URL               | Selecione o formato de ER a ser chamado para a ação. Esse formato é usado para compor o caminho do endereço da URL que será adicionado ao endereço de Internet básico especificado para o servidor Web selecionado. Esse campo só está disponível para ações do tipo **Serviço Web**. |
| Tipo de item de mensagem                         | Selecione o tipo de registros para os quais a ação deve ser avaliada. Este campo está disponível para ações dos tipos **Nível de execução do item da mensagem**, **Exportação de relatório eletrônico**, **Importação de relatório eletrônico**, **Serviço Web** e outros tipos. Se deixar esse campo em branco, todos os tipos de item da mensagem definidos para o processamento de mensagens são avaliados. |
| Classe executável                          | Selecione uma configuração de classe executável existente. Este campo só está disponível para ações dos tipos **Nível de execução de item de mensagem** e **Nível de execução de item de mensagem** . |
| Ação de preencher registros                   | Selecione uma ação de preencher registros existente. Esse campo só está disponível para ações do tipo **Preencher registros**. |
| Serviço Web                               | Selecione um serviço Web existente. Esse campo só está disponível para ações do tipo **Serviço Web**. |
| Nome do arquivo a ser enviado                         | Insira o nome do anexo para uma mensagem eletrônica que deve ser enviada por esta ação. Se vários anexos tiverem o mesmo nome de arquivo original, o mais recente será enviado. Se não for encontrado nenhum anexo com o nome de arquivo original especificado, a solicitação será enviada sem conteúdo. Esse campo só está disponível para ações do tipo **Serviço Web**. |
| Nome do arquivo                                 | Especifique o nome do arquivo que será o resultado da ação. Esse arquivo pode ser a resposta do servidor Web ou o relatório que é gerado. Este campo só está disponível para ações dos tipos **Serviço Web** e **Mensagem de exportação de relatório eletrônico**. |
| Anexar arquivos a documentos de origem          | Marque esta caixa de seleção para anexar os arquivos gerados aos registros em uma tabela mestra referenciada para itens de EM. Este campo só está disponível para ações dos tipos **Exportação de relatório eletrônico** e **Serviço Web**. |
| Anexar arquivos do arquivo morto de saída aos itens | Marque esta caixa de seleção para extrair arquivos XML separados do arquivo de saída e anexá-los aos itens de mensagem eletrônica correspondentes. Este campo só está disponível para ações do tipo **Exportação de relatório eletrônico**. |
| Número de itens de mensagem por exportação        | Especifique o limite para o número de itens de mensagem que deve ser incluído em um arquivo (mensagem). Este campo só está disponível para ações do tipo **Exportação de relatório eletrônico**. |
| Usar a origem de ER                             | Marque esta caixa de seleção para usar parâmetros de origem de ER para importação. Caso contrário, o anexo da mensagem eletrônica será usado. Este campo só está disponível para ações do tipo **Importação de relatório eletrônico**. |
| Mostrar caixa de diálogo                               | Defina esta opção como **Sim** se uma caixa de diálogo deve ser mostrada aos usuários antes que o relatório seja gerado. Este campo só está disponível para ações do tipo **Mensagem de exportação de relatório eletrônico**. |

#### <a name="message-processing-action-types"></a><a id="action-types"></a>Tipos de ação de processamento de mensagens

As seguintes opções estão disponíveis no campo **Tipo de ação**:

- **Criar mensagem** — use este tipo de ação para permitir que os usuários criem manualmente mensagens na página **Mensagem eletrônica**. Um status inicial não pode ser configurado para uma ação desse tipo.
- **Preencher registros** — esse tipo de ação já deve estar configurada. Associe-a a uma ação de preencher registros para permitir que ela seja incluída no processamento. Presume-se que esse tipo de ação seja usado para a primeira ação no processamento de mensagens (quando nenhuma mensagem eletrônica foi criada antecipadamente) ou para uma ação que adiciona itens de mensagem a uma mensagem que foi criada anteriormente pelo tipo de ação **Criar mensagem**. Portanto, para ações desse tipo, um status de resultado pode ser configurado somente para itens de mensagem. Um status inicial pode ser configurado somente para as mensagens.
- **Nível de execução da mensagem** — use esse tipo de ação para configurar uma classe executável que deve ser avaliada no nível da mensagem.
- **Nível de execução do item da mensagem** — use esse tipo de ação para configurar uma classe executável que deve ser avaliada no nível do item da mensagem.
- **Exportação de relatório eletrônico** — use esse tipo de ação para as ações que devem gerar um relatório com base em uma configuração de exportação de ER no nível do item da mensagem.
- **Mensagem de exportação de relatório eletrônico** — use esse tipo de ação para as ações que devem um gerar relatório com base em uma configuração de exportação de ER no nível da mensagem (por exemplo, quando uma mensagem não tiver itens de mensagem).
- **Importação de relatório eletrônico** — use esse tipo de ação para as ações que devem gerar um relatório com base em uma configuração de exportação de ER no nível do item da mensagem.
- **Processamento de usuário de nível de mensagem** — use esse tipo de ação para as ações que supõem algumas ações manuais do usuário no nível de mensagem. Por exemplo, o usuário pode atualizar o status de mensagens.
- **Processamento de usuário** — use esse tipo de ação para as ações que supõem algumas ações manuais do usuário no nível do item da mensagem. Por exemplo, o usuário pode atualizar o status de itens de mensagem.
- **Serviço Web** — use esse tipo de ação para as ações que devem transmitir um relatório gerado para um serviço Web. Esse tipo de ação não é usado para o relatório de comunicação de faturas de compra e venda italiano. Para esse tipo de ação, a página **Ações de processamento de mensagens** inclui uma Guia Rápida **Detalhes diversos**, em que você pode especificar um texto de confirmação. Esse texto de confirmação será exibido para os usuários antes que as solicitações sejam atendidas para o serviço Web selecionado.
- **Verificação da solicitação** — use esse tipo de ação para solicitar a verificação de um servidor.

### <a name="initial-statuses-fasttab"></a>FastTab Status iniciais

> [!NOTE]
> A FastTab **Status iniciais** não está disponível para ações que têm um tipo de ação inicial de **Criar mensagem**.

| Campo               | Descrição |
|---------------------|-------------|
| Status de item de mensagem | Selecione o status do item de mensagem para o qual a ação de processamento de mensagens deve ser avaliada. |
| descrição         | Uma descrição do status do item de mensagem selecionado. |

### <a name="result-statuses-fasttab"></a>FastTab Status de resultados

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

## <a name="electronic-message-processing"></a><a id="processing"></a>Processamento de mensagem eletrônica

O processamento de mensagens eletrônicas é um conceito básico da funcionalidade EM. Agrega ações que devem ser avaliadas para a mensagem eletrônica. As ações que podem ser vinculadas usando um status inicial e um status de resultado. Alternativamente, as ações do tipo **Processamento de usuário** podem ser iniciadas de forma independente. Para configurar o processamento de mensagens eletrônicas, acesse **Imposto** \> **Configuração** \> **Mensagens eletrônicas** \> **Processamento de mensagens eletrônicas**.

A FastTab **Ação** permite adicionar ações predefinidas ao processamento. Você pode especificar se uma ação deve ser executada separadamente, ou se ela pode ser iniciada pelo processamento. Para especificar que uma ação no processamento pode ser inicializada somente por um usuário, defina o campo **Executar separadamente** como **Sim** para essa ação. Se uma ação deve ser iniciada pelo processamento de mensagens ou itens de mensagem que estão no status que foi definido como o status inicial para a ação, defina o campo **Executar separadamente** como **Não**. Ações do tipo **Ação do usuário** devem sempre ser executadas separadamente.

Às vezes, várias ações devem ser agregadas em uma sequência, mesmo que a primeira ação esteja configurada para ser executada separadamente. Por exemplo, um usuário deve inicializar a geração de relatórios. No entanto, depois que o relatório for gerado, ele deverá ser enviado imediatamente para um serviço Web, e a resposta do serviço Web deverá ser refletida no sistema. Nesse caso, você pode criar uma sequência inseparável para as ações que devem ser sempre executadas juntas. Na FastTab **Ação**, selecione **Sequências inseparáveis** acima da grade e crie uma sequência. Em seguida, para todas as ações que devem ser executadas juntas em uma sequência, selecione a sequência no campo **Sequência inseparável**. Para este exemplo, o campo **Executar separadamente** pode ser definido como **Sim** para a primeira ação na sequência, e como **Não** para todas as outras ações.

As ações dos tipos **Exportação de relatório eletrônico** e **Mensagem de exportação de relatório eletrônico** executam um formato ER que tem parâmetros de entrada. Se o seu processamento de mensagens eletrônicas incluir ações de qualquer um desses tipos, você deverá especificar os valores para os parâmetros de entrada antes da geração do relatório. Dessa forma, o sistema poderá usar um regime de lote para gerar o relatório. Você pode selecionar **Parâmetros** acima da grade para configurar os parâmetros para o tipo de ação selecionado (**Exportação de relatório eletrônico** ou **Mensagem de exportação de relatório eletrônico**). Marque a caixa de seleção **Usar parâmetros** para a ação que deve ser executada com os parâmetros especificados em um regime de lote.

Use a Guia Rápida **Campos adicionais do item de mensagem** para adicionar campos adicionais predefinidos relacionados aos itens de mensagem. Você deve adicionar outros campos para cada tipo de item de mensagem ao qual os campos estão relacionados. É possível especificar um valor padrão que será atribuído ao campo adicional durante o processamento.

A Guia Rápida **Campos adicionais da mensagem** para adicionar campos adicionais predefinidos relacionados às mensagens. É possível especificar um valor padrão que será atribuído ao campo adicional durante o processamento.

Use a Guia Rápida **Funções de segurança** para configurar as funções de segurança predefinidas no sistema para o processamento específico. Os usuários com uma função específica verão somente o processamento definido para a função.

A Guia Rápida **Lote** para configurar o processamento para funcionar em um regime de lote. É recomendável configurar um regime de lote para o seu processamento diretamente na página **Mensagens eletrônicas** ou **Itens de mensagem eletrônica** quando você selecionar **Executar processamento** no Painel de Ações para iniciar o processamento.
