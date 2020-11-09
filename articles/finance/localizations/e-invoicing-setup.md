---
title: Configurar o complemento de faturamento eletrônico
description: Este tópico explica como configurar o complemento de faturamento eletrônico no Microsoft Dynamics 365 Finance e no Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 7e631f1bf64b47b5f3e85d4f98c6edafe67d627a
ms.sourcegitcommit: d6250ee5ced43be39e789324a895fd1c07178935
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2020
ms.locfileid: "4039883"
---
# <a name="set-up-the-electronic-invoicing-add-on"></a>Configurar o complemento de faturamento eletrônico

[!include [banner](../includes/banner.md)]


A configuração do recurso complemento eletrônico de faturamento é o processo de criação da configuração necessária por meio do ambiente Regulatory Configuration Services (RCS) e da publicação dessa configuração no servidor de complemento de faturamento eletrônico. A configuração permite criar as regras configuráveis que permitem ao complemento de faturamento eletrônico usar um protocolo seguro na Internet para comunicar e trocar dados com uma entidade de terceiros por meio de serviços Web.

A capacidade de configuração depende da configuração do formato de relatório eletrônico (ER) como um meio de criar um conteúdo enviado e recebido por meio de arquivos digitais. Ela também depende da orquestração das ações de comunicação para enviar solicitações e receber respostas de serviços Web de terceiros sem exigir que você escreva código.

## <a name="overview"></a>Visão Geral

O recurso "Complemento de faturamento eletrônico" é o nome genérico do recurso configurado e publicado para consumir o servidor do complemento de faturamento eletrônico. A configuração do recurso combina, entre outras coisas, o uso de formatos de configuração de ER para criar arquivos de exportação e importação configuráveis, e o uso de ações e de fluxos de ações para habilitar a criação de regras configuráveis para enviar solicitações, importar respostas e analisar o conteúdo de respostas.

A ilustração a seguir mostra os principais componentes de um recurso Complemento de faturamento eletrônico.

![Visão geral do recurso Complemento de faturamento eletrônico](media/e-Invoicing-services-feature-setup-Overview-e-Invoicing-feature.png)

Devido a variações nos formatos de fatura e fluxos de ação, a configuração do recurso varia de acordo com o país ou a região, ou de acordo com as necessidades comerciais.

## <a name="set-up-the-electronic-invoicing-add-on-feature"></a>Configurar o recurso Complemento de faturamento eletrônico

O processo de configuração deve ser concluído no ambiente RCS. Siga estas etapas para criar um novo recurso Complemento de faturamento eletrônico.

1. Entre no ambiente RCS.
2. No espaço de trabalho **Recursos de globalização** , na seção **Recursos** , selecione o bloco **Complemento de faturamento eletrônico**.
3. Na página **Recursos do Complemento de faturamento eletrônico** , selecione **Importar** para importar a configuração do modelo de dados ER do Repositório global.
4. Selecione **Adicionar** para criar um recurso Complemento de faturamento eletrônico. Você pode criar o recurso do zero ou derivá-lo de um recurso Complemento de faturamento eletrônico existente.

    ![Adicionar um recurso Complemento de faturamento eletrônico](media/e-Invoicing-services-feature-setup-Select-Add-e-Invoicing-feature.png)

> [!NOTE]
> Quando você cria um novo recurso Complemento de faturamento eletrônico, ele tem um número de versão e o status padrão é definido como **Rascunho**.

### <a name="configurations"></a>Configurações

As configurações contêm as configurações de formato ER que são necessárias para transformações e para criar os arquivos que serão trocados durante a comunicação com serviços Web de terceiros. Um recurso Complemento de faturamento eletrônico pode ter tantas configurações de formato de arquivo ER quantas forem necessárias, com base na especificação técnica de integração fornecida pelo provedor de serviços Web.

Siga estas etapas para adicionar formatos ER ao recurso Complemento de faturamento eletrônico.

1. Na página **Recursos de Complemento de faturamento eletrônico** , na guia **Configurações** , selecione **Adicionar** para adicionar configurações de formato de arquivo ER file para o recurso de Complemento de faturamento eletrônico.

    ![Adicionar configurações do recurso de Complemento de faturamento eletrônico](media/e-Invoicing-services-feature-setup-Select-Add-e-Invoicing-feature-Configurations.png)

    > [!NOTE]
    > Ao criar um recurso de Complemento de faturamento eletrônico do zero, você deve adicionar manualmente todas as configurações de formato de arquivo ER. Quando você deriva um recurso de complemento de faturamento eletrônico de um recurso existente, as configurações de formato de arquivo ER são criadas automaticamente, pois são herdadas do recurso de complemento de faturamento eletrônico original.

2. Selecione **Editar** para abrir a página **Designer de formato** , na qual você pode editar a configuração de formato de arquivo ER.

    ![Editar configurações do recurso Complemento de faturamento eletrônico](media/e-Invoicing-services-feature-setup-Select-Edit-e-Invoicing-feature-Configurations.png)

    > [!NOTE]
    > Enquanto você edita o formato, o status da versão da configuração é definido como **Rascunho**.

3. Use a página **Designer de formato** para alterar a configuração de formato de arquivo. Para obter mais informações, consulte [Criar configurações do documento eletrônico](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/electronic-reporting-configuration).

    ![Página do designer de formatos](media/e-Invoicing-services-feature-setup-ER-Format-designer.png)

### <a name="feature-setups"></a>Configurações do recurso

As configurações de recursos encapsulam as regras de comunicação e segurança com um serviço Web de terceiros. Um recurso Complemento de faturamento eletrônico pode ter a quantidade de configurações de recursos necessárias, com base na regra comercial que você deseja realizar.

Siga estas etapas para adicionar configurações de recurso ao recurso Complemento de faturamento eletrônico.

1. Na página **Recursos de Complemento de faturamento eletrônico** , na guia **Configurações** , selecione **Adicionar** para adicionar configurações de recurso para o recurso de Complemento de faturamento eletrônico.

    ![Adicionar configurações de recurso Complemento de faturamento eletrônico](media/e-Invoicing-services-feature-setup-Select-Add-e-Invoicing-feature-Setups.png)

    > [!NOTE]
    > Ao criar um recurso de Complemento de faturamento eletrônico do zero, você deve adicionar manualmente todas as configurações de recurso necessárias. Quando você deriva um recurso de Complemento de faturamento eletrônico de um recurso existente, todas as configurações de recurso são criadas automaticamente, pois são herdadas do recurso de Complemento de faturamento eletrônico original.

2. Selecione **Editar** para editar a configuração da versão do recurso.

    ![Editar configurações de recurso Complemento de faturamento eletrônico](media/e-Invoicing-services-feature-setup-Select-Edit-e-Invoicing-feature-Setups.png)

3. Use a página **Configuração de versão do recurso** para configurar ações, regras de aplicabilidade e variáveis.

    ![Ações, regras de aplicabilidade e variáveis](media/e-Invoicing-services-feature-setup-View-Actions-Applicability-Rules-Variables.png)

### <a name="actions"></a>Ações

As ações são uma lista predefinida de operações que são executadas em ordem sequencial. Esta lista representa a divisão das etapas necessárias para a execução total do recurso de Complemento de faturamento eletrônico. As ações podem ser encapsuladas, no mesmo recurso de Complemento de faturamento eletrônico, comunicação nas duas direções: enviar uma solicitação para um destino, receber uma resposta e analisar o conteúdo.

Cada ação contém uma lista predefinida de parâmetros necessários para a ação que cumprirá a finalidade. Parâmetros adicionais podem ser fornecidos opcionalmente.

#### <a name="actions-fasttab"></a>Guia Rápida Ações

Na página **Configuração de versões do recurso** , na guia **Ações** , na Guia Rápida **Ações** , siga uma ou ambas as etapas para gerenciar ações:

- Selecione **Novo** ou **Excluir** para adicionar novas ações ou excluir ações existentes.
- Selecione **Para cima** ou **Para baixo** para mover ações selecionadas para cima ou para baixo na grade e alterar a ordem em que são executadas. As ações são executadas na ordem em que aparecem na grade, de cima para baixo.

![Gerenciar ações](media/e-Invoicing-services-feature-setup-Manage-Actions.png)

A tabela a seguir descreve os campos disponíveis na Guia Rápida **Ações**.

| Campo        | Descrição |
|--------------|-------------|
| Ação       | Existem oito ações predefinidas:<ul><li><strong>Assinar documento</strong></li><li><strong>FileStoreActionName</strong></li><li><strong>Transformar documento</strong></li><li><strong>Processar resposta</strong></li><li><strong>Chamar serviço Web de REST</strong></li><li><strong>Chamar serviço da PAC mexicana</strong></li><li><strong>Chamar serviço da SEFAZ do Brasil</strong></li><li><strong>Chamar serviço de SDI italiano</strong></li></ul> |
| Nome da ação  | O nome da ação e a ordem de execução. |
| descrição  | Uma descrição da ação. |
| Habilitar repetição | Uma caixa de seleção marcada indica que a ação poderá ser repetida se a tentativa anterior não tiver êxito. |
| Repetir ação | No caso de uma nova tentativa, a ação a partir da qual ocorre a repetição. A repetição é encerrada na ação atual (tentativa inclusiva). Para ações com os parâmetros **Retirada mínima** e **Retirada máxima** , eles especificam o número mínimo e o número máximo de tentativas. |

#### <a name="parameters-fasttab"></a>Guia Rápida Parâmetros

A Guia Rápida **Parâmetros** lista os parâmetros para a ação selecionada na Guia Rápida **Ações**.

![Guia Rápida Parâmetros](media/e-Invoicing-services-feature-setup-View-Actions-Parameters.png)

A tabela a seguir descreve os campos disponíveis na Guia Rápida **Parâmetros**.

| Campo       | descrição |
|-------------|-------------|
| Nome        | Uma lista predefinida de parâmetros. Para obter mais informações, consulte a seção [Lista de parâmetros por ação](#list-of-parameters-by-action). |
| descrição | Uma descrição do parâmetro. |
| Alíquota       | O valor do parâmetro. |

#### <a name="list-of-parameters-by-action"></a>Lista de parâmetros por ação

Os parâmetros disponíveis variam de acordo com a ação selecionada na Guia Rápida **Ações**.

###### <a name="action-sign-document"></a>Ação: assinar documento

| Parâmetro                             | Descrição |
|---------------------------------------|-------------|
| Arquivo de entrada                            | O arquivo de documento XML de entrada que deve ser assinado usando uma assinatura eletrônica. |
| Nome do certificado                      | O nome do certificado no armazenamento. |
| Tipo de assinatura                        | O tipo de assinatura a ser usado. |
| Nome do método de assinatura                 | O nome do método de assinatura usado para gerar uma assinatura eletrônica. |
| Nome do método Digest                    | O método Digest usado para gerar uma sequência de caracteres de Digest na assinatura digital. |
| Nome de método de canonização          | O método de canonização usado para calcular o hash de assinatura. |
| Nome do atributo de referência              | O nome do atributo que indica onde a ID de referência deve ser inserida no elemento de assinatura. |
| Nome do elemento a ser assinado               | O nome do elemento XML no documento que deve ser assinado usando uma assinatura eletrônica. Se nenhum elemento for especificado, a raiz do documento será assinada. |
| Nome do elemento para inserir assinatura   | O nome do elemento XML em que uma assinatura digital gerada deve ser inserida. Se nenhum elemento for especificado, a assinatura será inserida na raiz do documento. |
| Arquivo XLST com transformação Digest       | O arquivo XSLT (Extensible Stylesheet Language Transformations) que contém regras de transformação Digest para gerar a sequência de caracteres Digest para uma assinatura eletrônica. |
| Caminho para inserir cadeia de caracteres Digest          | O caminho, em **\<elementName\>.\<Attribute.Path\>** formato do local em que a cadeia de caracteres Digest gerada deve ser inserida. |
| Local do número do certificado           | O nome do elemento e do atributo em que o número do certificado deve ser colocado. |
| Localização de dados do certificado          | O nome do elemento e do atributo em que dados do certificado (base64) devem ser inseridos. |
| O número do certificado está no formato ASCII | Um valor que especifica se o número do certificado é codificado no formato ASCII. |

###### <a name="action-filestoreactionname"></a>Ação: FileStoreActionName

| Parâmetro  | descrição |
|------------|-------------|
| Arquivo de entrada | O arquivo de entrada a ser armazenado. |

###### <a name="action-transform-document"></a>Ação: transformar o documento

| Parâmetro                       | Descrição |
|---------------------------------|-------------|
| Arquivo de entrada                      | O arquivo de origem que fornece os dados que devem ser executados para a ação. |
| Direção                       | Um valor que indica se o formato de importação ou o formato de exportação deve ser usado. |
| ID da Configuração                | O formato que deve ser executado. |
| Versão da configuração           | Se nenhuma versão de configuração for especificada, a versão mais recente será usada. |
| Ponto de integração de configuração | O arquivo de origem que fornece dados para o tempo de execução de relatórios. |

###### <a name="action-process-response"></a>Ação: processar resposta

| Parâmetro                    | descrição |
|------------------------------|-------------|
| Arquivo de entrada                   | A resposta a ser analisada. |
| Lista de configuração de relatórios | Uma lista de configurações usadas para analisar respostas. |

###### <a name="action-call-rest-web-service"></a>Ação: chamar serviço Web de REST

| Parâmetro                   | Descrição |
|-----------------------------|-------------|
| URL de serviço Web             | A URL para a qual as solicitações serão enviadas. |
| Tempo limite de solicitação da Web         | O valor máximo de tempo (em milissegundos) para aguardar uma resposta de serviço Web. |
| Tipo de operação de solicitação      | O tipo de operação de solicitação HTTP (por exemplo, **OBTER** , **LANÇAR** ou **EXCLUIR** ). |
| Nomes de certificado           | Os nomes de certificado. |
| Codificação do corpo da resposta      | A codificação esperada do corpo da resposta HTTP para que possa ser decodificada corretamente. |
| Tipo de conteúdo da solicitação HTTP   | A entrada do cabeçalho do tipo de conteúdo da solicitação HTTP. |
| Corpo de conteúdo da solicitação HTTP   | O corpo da solicitação de HTTP. (O corpo pode estar vazio.) |
| Valores da consulta de parâmetro HTTP | Valores de consulta de parâmetro usados para preencher a URL com parâmetros variáveis. |
| Solicitar roteiro               | O caminho do roteiro para a solicitação HTTP. Os parâmetros variáveis podem ser escritos na notação **\{paramName\}**. Este é um exemplo: **"api/{id}/submit"**. |
| Lista de parâmetros de roteiro        | Os parâmetros de roteiro, em notação de valor-chave, que são usados para inserir variáveis no roteiro. |
| Cabeçalhos HTTP personalizados         | Os cabeçalhos HTTP personalizados a serem inseridos na solicitação. |
| Cookies de solicitação HTTP        | Uma lista de cookies, em notação de valor-chave, para colocar na solicitação de cabeçalho de cookies HTTP. |
| Protocolo de segurança           | O protocolo de segurança a ser usado para solicitações HTTP na comunicação com o servidor. (Por padrão, é usado o Transport Layer Security \[TLS\] 1.2.) |

###### <a name="action-call-mexican-pac-service"></a>Ação: chamar serviço da PAC mexicana

| Parâmetro                | Descrição |
|--------------------------|-------------|
| Arquivo de entrada               | O arquivo que contém dados XML que serão enviados ao serviço Web como um parâmetro de entrada de método. |
| Endereço URL              | O endereço do serviço Web (ponto de extremidade). |
| Nome do método Web (ação) | O nome do método Web (ação) que deve ser executado. |
| Certificados             | A cadeia de certificados necessária para autenticação de cliente pelo serviço Web. O certificado de cliente deve ser o último certificado na cadeia. Os certificados raiz e intermediários devem ser os primeiros. |
| Tempo limite de solicitação da Web      | O valor máximo de tempo (em milissegundos) para aguardar uma resposta de serviço Web. |
| Intervalo de repetição           | O intervalo entre as tentativas de chamar e receber uma resposta do serviço Web. Se nenhum intervalo for especificado, não serão feitas tentativas adicionais após a primeira chamada ser malsucedida. |
| Número de tentativas              | O número máximo de tentativas de repetição para chamar e recuperar uma resposta do serviço Web. |
| Repetir até               | O tempo máximo (em milissegundos) que as chamadas de repetição podem continuar. |
| Retirada mínima         | A taxa de retirada mínima do cálculo exponencial de intervalos de repetição. |
| Retirada máxima         | A taxa de retirada máxima do cálculo exponencial de intervalos de repetição. |
| Protocolo de segurança        | O protocolo de segurança a ser usado para solicitações HTTP na comunicação com o servidor. (Por padrão, o TLS 1.2 é usado.) |

###### <a name="action-call-brazilian-sefaz-service"></a>Ação: chamar serviço da SEFAZ brasileira

| Parâmetro                | Descrição |
|--------------------------|-------------|
| Arquivo de entrada               | O arquivo que contém dados XML que serão enviados ao serviço Web como um parâmetro de entrada de método. |
| Endereço URL              | O endereço do serviço Web (ponto de extremidade). |
| Nome do método Web (ação) | O nome do método Web (ação) que deve ser executado. |
| Certificados             | A cadeia de certificados necessária para autenticação de cliente pelo serviço Web. O certificado de cliente deve ser o último certificado na cadeia. Os certificados raiz e intermediários devem ser os primeiros. |
| Tempo limite de solicitação da Web      | O valor máximo de tempo (em milissegundos) para aguardar uma resposta de serviço Web. |
| Intervalo de repetição           | O intervalo entre as tentativas de chamar e receber uma resposta do serviço Web. Se nenhum intervalo for especificado, não serão feitas tentativas adicionais após a primeira chamada ser malsucedida. |
| Número de tentativas              | O número máximo de tentativas de repetição para chamar e recuperar uma resposta do serviço Web. |
| Repetir até               | O tempo máximo (em milissegundos) que as chamadas de repetição podem continuar. |
| Retirada mínima         | A taxa de retirada mínima do cálculo exponencial de intervalos de repetição. |
| Retirada máxima         | A taxa de retirada máxima do cálculo exponencial de intervalos de repetição. |
| Protocolo de segurança        | O protocolo de segurança a ser usado para solicitações HTTP na comunicação com o servidor. (Por padrão, o TLS 1.2 é usado.) |

###### <a name="action-call-italian-sdi-service"></a>Ação: chamar serviço de SDI italiano

| Parâmetro                | descrição |
|--------------------------|-------------|
| Arquivo de entrada               | O arquivo que contém dados XML que serão enviados ao serviço Web como um parâmetro de entrada de método. |
| Endereço URL              | O endereço do serviço Web (ponto de extremidade). |
| Nome do método Web (ação) | O nome do método Web (ação) que deve ser executado. |
| Certificados             | A cadeia de certificados necessária para autenticação de cliente pelo serviço Web. O certificado de cliente deve ser o último certificado na cadeia. Os certificados raiz e intermediários devem ser os primeiros. |
| Tempo limite de solicitação da Web      | O valor máximo de tempo (em milissegundos) para aguardar uma resposta de serviço Web. |
| Intervalo de repetição           | O intervalo entre as tentativas de chamar e receber uma resposta do serviço Web. Se nenhum intervalo for especificado, não serão feitas tentativas adicionais após a primeira chamada ser malsucedida. |
| Número de tentativas              | O número máximo de tentativas de repetição para chamar e recuperar uma resposta do serviço Web. |
| Repetir até               | O tempo máximo (em milissegundos) que as chamadas de repetição podem continuar. |
| Retirada mínima         | A taxa de retirada mínima do cálculo exponencial de intervalos de repetição. |
| Retirada máxima         | A taxa de retirada máxima do cálculo exponencial de intervalos de repetição. |
| Protocolo de segurança        | O protocolo de segurança a ser usado para solicitações HTTP na comunicação com o servidor. (Por padrão, o TLS 1.2 é usado.) |

### <a name="applicability-rules"></a>Regras de aplicabilidade

As regras de aplicabilidade permitem criar regras lógicas que determinam o contexto de uso da configuração do recurso. Dessa forma, a correspondência entre o contexto fornecido pelo documento comercial enviado para processamento, juntamente com os critérios da regra de aplicabilidade, determina qual recurso de complemento eletrônico de faturamento é usado para processar esse envio.

#### <a name="set-up-applicability-rules"></a>Configurar regras de aplicabilidade

1. Na página **Configuração de versão do recurso** , na guia **Regras de aplicabilidade** , selecione **Novo** para adicionar uma regra de aplicabilidade.

    ![Gerenciar regras de aplicabilidade](media/e-Invoicing-services-feature-setup-Manage-Actions-Applicability-rules.png)

2. Na grade, selecione as cláusulas que devem ser agrupadas.
3. Selecione **Agrupar cláusula**.

    ![Agrupar cláusulas](media/e-Invoicing-services-feature-setup-Manage-Applicability-rules-Group-clause.png)

    Quando as cláusulas são agrupadas, uma nova coluna é adicionada à grade. Esta coluna especifica o operador lógico para as cláusulas agrupadas.

    ![Operador lógico para cláusulas agrupadas](media/e-Invoicing-services-feature-setup-Manage-Applicability-rules-Group-criterias.png)

Para desagrupar cláusulas, selecione as cláusulas agrupadas para desagrupá-las e selecione **Desagrupar cláusula**.

![Desagrupar cláusulas](media/e-Invoicing-services-feature-setup-Manage-Applicability-rules-UnGroup-criterias.png)

> [!NOTE]
> Ao desagrupar uma cláusula, sempre inicie do nível de agrupamento mais interno.

A tabela a seguir descreve os campos disponíveis na guia **Regras de aplicabilidade**.

| Campo         | Descrição |
|---------------|-------------|
| E/ou        | O operador lógico. |
| Campo         | O campo a ser usado para construir a regra. |
| Tipo de operador | O tipo de operador.<ul><li>Equivalente</li><li>Diferente</li><li>Maior que/menor que</li><li>Maior que ou igual a/Menor que ou igual a</li><li>Contém</li><li>Começa com</li></ul> |
| Alíquota         | O critério da regra. |

### <a name="variables"></a>Variáveis

Você pode criar variáveis e usá-las como o valor de entrada para um parâmetro de uma ação específica. Você também pode usá-las para trocar informações, entre os serviços de Complemento de faturamento eletrônico e o cliente, são o resultado da execução de uma ação específica como parte do fluxo de envios.

#### <a name="set-up-variables"></a>Configurar variáveis

- Na página **Configuração de versão do recurso** , na guia **Variáveis** , selecione **Nova** ou **Excluir** para gerenciar variáveis.

    ![Gerenciar variáveis](media/e-Invoicing-services-feature-setup-Manage-Variables.png)

A tabela a seguir descreve os campos disponíveis na guia **Variáveis**.

| Campo       | Descrição |
|-------------|-------------|
| Nome        | O nome da variável. |
| Descrição | Uma breve descrição da variável. |
| Tipo        | O tipo de variável:<ul><li><strong>Constante</strong> – o conteúdo da variável é fixo.</li><li><strong>De cliente</strong> – o conteúdo da variável é adquirido do cliente Microsoft Dynamics 365 durante a execução do processo de envio.</li><li><strong>Para cliente</strong> – o conteúdo da variável é disponibilizado para importação pelo cliente Microsoft Dynamics 365 durante a execução do processo de envio.</li></ul> |
| Tipo de dados   | O tipo de dados da variável:<ul><li>Booleano</li><li>Data </li><li>Número</li><li>UUID</li><li>Sequência de caracteres</li><li>Arquivo</li></ul> |
| Alíquota       | O valor da variável ou o nome da ação que define o valor da variável. |

### <a name="validate-the-feature-setup"></a>Validar a configuração do recurso

- Na página **Configuração de versão do recurso** , no Painel de Ações, selecione **Validar** para validar a configuração da versão do recurso.

   ![Selecionar o botão Validar](media/e-Invoicing-services-feature-setup-Select-Validate-Button.png)

A validação verifica a consistência da configuração inteira. Por exemplo, se um parâmetro específico de uma ação for obrigatório, mas seu valor permanecer em branco, a validação detectará essa inconsistência e você receberá um aviso.

## <a name="environments"></a>Ambientes

Um ambiente Complemento de faturamento eletrônico deve estar associado ao recurso Complemento de faturamento eletrônico e habilitado para ele. Os ambientes Complemento de faturamento eletrônico devem ser criados e publicados previamente, por meio da configuração de Recursos de globalização na conta RCS da organização.

Siga estas etapas para habilitar um ambiente Complemento de faturamento eletrônico para o recurso Complemento de faturamento eletrônico.

1. Na página **Recursos de Complemento de faturamento eletrônico** , na guia **Ambientes** , selecione **Habilitar** para adicionar um ambiente Complemento de faturamento eletrônico.
2. No campo **Efetivo a partir de** , insira a data em que o novo ambiente entra em vigor.

![Habilitar um ambiente de Complemento de faturamento eletrônico](media/e-Invoicing-services-feature-setup-Select-Enable-e-Invoicing-feature-Environment.png)

## <a name="organizations"></a>Organizações

O recurso Complemento de faturamento eletrônico pode ser compartilhado entre várias organizações.

- Na página **Recursos de Complemento de faturamento eletrônico** , na guia **Organizações** , selecione **Compartilhar com** para adicionar a organização com a qual deseja compartilhar o recurso de Complemento de faturamento eletrônico.

Para interromper o compartilhamento do recurso de Complemento de faturamento eletrônico com a organização, selecione **Descompartilhar**.

## <a name="versions"></a>Versões

As versões gerenciam o status para ajudar a controlar o ciclo de vida do recurso de Complemento de faturamento eletrônico. Você pode criar uma nova versão de um recurso de Complemento de faturamento eletrônico existente ou, quando todas as configurações do recurso Complemento de faturamento eletrônico forem concluídas, poderá alterar o status do recurso para **Concluir** e, depois, para **Publicar**.

### <a name="create-a-new-version-of-an-existing-electronic-invoicing-add-on-feature"></a>Criar uma nova versão de um recurso Complementar de faturamento eletrônico existente

1. Na página **Recursos de Complemento de faturamento eletrônico** , na grade à esquerda, selecione o recurso de Complemento de faturamento eletrônico.
2. Na guia **Versões** , selecione **Novo** para adicionar uma nova versão do recurso Complemento de faturamento eletrônico.

### <a name="change-the-status-of-the-electronic-invoicing-add-on-feature"></a>Alterar o status do recurso Complemento de faturamento eletrônico

Siga estas etapas para gerenciar o ciclo de vida do recurso Complemento de faturamento eletrônico.

1. Na página **Recursos de Complemento de faturamento eletrônico** , na grade à esquerda, selecione o recurso de Complemento de faturamento eletrônico.
2. Na guia **Versões** , selecione **Alterar status** e altere o status de **Rascunho** para **Concluído**.
3. Você é solicitado a confirmar que deseja preencher o recurso Complemento de faturamento eletrônico e todos os componentes dele. Selecione **Sim** para confirmar a ação ou **Não** para cancelá-la.

    > [!NOTE]
    > Quando você seleciona **Sim** , o status das versões de configuração, que são componentes do recurso Complemento de faturamento eletrônico, é alterado automaticamente de **Rascunho** para **Concluído**.

4. Selecione **Alterar status** e altere o status de **Concluir** para **Publicar**.
5. Você é solicitado a confirmar que deseja publicar o recurso Complemento de faturamento eletrônico e todos os componentes dele para o Repositório global. Selecione **Sim** para confirmar a ação ou **Não** para cancelá-la.

    > [!NOTE]
    > Quando você seleciona **Sim** , o status das versões da configuração é alterado automaticamente de **Concluído** para **Compartilhado**.
