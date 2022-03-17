---
title: Trabalhar com configurações de recursos
description: Este tópico explica como configurar os recursos de Faturamento eletrônico.
author: dkalyuzh
ms.date: 12/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 41ffc9c7009291a55392e50c5e490d3288d122bc
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371488"
---
# <a name="work-with-feature-setups"></a>Trabalhar com configurações de recursos

[!include [banner](../includes/banner.md)]

Configurar a geração de arquivos eletrônicos e outras etapas de processamento (por exemplo, assinar arquivos digitalmente, enviá-los ao serviço Web do governo e receber uma resposta ou armazená-los), configurar o pipeline de processamento, as regras de aplicabilidade e variáveis para os recursos de faturamento eletrônico.

As informações de configuração são combinadas no conceito de *configuração do recurso* e podem ser criadas, excluídas, ajustadas. Para as versões concluídas dos recursos de faturamento eletrônico, as informações também podem ser exibidas.

É possível criar o número de itens de configuração de recursos necessários para definir diferentes cenários de geração, processamento e recebimento de arquivos eletrônicos. Embora esses itens de configuração de recursos tenham ações e condições de processamento independentes para execução, eles são criados como parte de um único recurso de faturamento eletrônico e herdam seu ciclo de vida e processo de implantação.

## <a name="add-a-feature-setup"></a>Adicionar uma configuração de recurso

1. Entre na conta RCS (serviço de configuração regulatória).
2. No espaço de trabalho **Recurso de globalização** na seção **Recursos**, selecione o bloco **Faturamento eletrônico**.
3. Na página **Recursos de Faturamento eletrônico**, selecione uma versão de recurso de Faturamento eletrônico que tenha um status de **Rascunho**.
4. Na guia **Configurações**, selecione **Adicionar**.
5. Na caixa de diálogo **Criar configuração do recurso**, no grupo de campos **Novo**, selecione uma das seguintes opções:
 
    - **Configuração personalizada** – Crie uma nova configuração de recurso que tenha canais vazios, uma lista de pipeline de processamento vazia, uma seção vazia das regras de aplicabilidade e um conjunto de variáveis padrão, dependendo do tipo de configuração.
    - **Configuração a partir do recurso** – Crie uma cópia de outra configuração de recurso no escopo do recurso de faturamento eletrônico atual.

6. Se você selecionou a opção **Configuração personalizada** na última etapa, digite um nome e uma descrição do item de configuração do recurso e, em seguida, no grupo de campos **Tipo de configuração**, selecione uma das seguintes opções:

    - **Pipeline de processamento** – Selecione esta opção para gerar e processar documentos eletrônicos de saída. Para esse tipo de configuração, o sistema cria uma lista de pipeline de processamento vazia, uma seção vazia para regras de aplicabilidade e um conjunto de variáveis padrão. Não será possível trabalhar com os canais para documentos eletrônicos de entrada.
    - **Canal de dados** – Selecione esta opção para configurar o processo de recebimento de documentos eletrônicos de entrada de um dos canais definidos e transferência deles diretamente para o Microsoft Dynamics 365 Finance ou Dynamics 365 Supply Chain Management sem ações adicionais. Para esse tipo de configuração, o sistema cria uma lista predefinida de parâmetros para os canais de dados, uma seção vazia para regras de aplicabilidade e um conjunto de variáveis padrão. Não será possível adicionar ações ao pipeline de processamento.
    - **Canal de dados e pipeline de processamento** – Esse tipo de configuração é semelhante ao tipo **Canal de dados**. No entanto, antes que um documento eletrônico de entrada seja passado para o Finance ou Supply Chain Management, você pode configurar ações adicionais no pipeline de processamento.

7. Se você selecionou a opção **Canal de dados** ou **Canal de dados e processamento de pipeline** na última etapa, no campo **Selecionar canal de dados**, você deve selecionar o canal com o qual ocorrerá a integração.
8. Selecione **Criar**.

Depois que uma configuração de recurso for criada, você poderá selecionar **Editar** para configurá-la.

## <a name="edit-a-feature-setup"></a>Editar uma configuração de recurso

Dependendo do tipo de configuração do recurso, você pode configurar o processo de geração de arquivos eletrônicos de saída e de seu envio a canais externos, ou o recebimento de documentos de entrada e a transferência deles para o seu aplicativo Finance ou Supply Chain Management.

### <a name="data-channel"></a>Canal de dados

Um *Canal de dados* pega o arquivo eletrônico e o processa ou o transmite diretamente para o Finance ou Supply Chain Management. Esta opção não está disponível para configurações de recurso do tipo **Pipeline de processamento**.

Para configurar um canal de dados, digite o nome do canal. Em seguida, defina os parâmetros, com base no tipo de canal selecionado. O identificador do canal de dados deve se referir à variável criada especificamente para identificar o canal de dados. Ele será usado como referência no Finance ou Supply Chain Management.

Na guia **Filtro de anexos**, você deve definir um conjunto de filtros para obter arquivos específicos do canal. Você pode criar várias linhas pretende que os arquivos tenham extensões de nome de arquivo diferentes ou se os arquivos tiverem de ser processados de forma diferente dependendo do nome do arquivo. Estes são os principais parâmetros:

- **Nome** – Insira o nome do arquivo ao qual o sistema fará referência durante o processamento. Nos aplicativos Finance and Supply Chain Management, você poderá ver os arquivos no log de envio.
- **Filtro** – Defina o filtro para selecionar arquivos.
- **Opcional** – Se esta caixa de seleção estiver desmarcada, o arquivo será obrigatório. Nesse caso, o sistema mostrará uma mensagem de erro se os canais não contiverem arquivos que correspondam ao filtro. Esse parâmetro é aplicável a emails.

Se o canal for uma caixa de correio e um email de entrada contiver vários anexos, você poderá configurar regras para definir como o serviço deve tratar os anexos. O serviço pode considerar cada anexo em uma fatura eletrônica separada ou pode tratar um anexo como uma fatura principal e todos os outros anexos como adições.

### <a name="processing-pipeline"></a>Pipeline de processamento

Um *pipeline de processamento* é um conjunto de *ações* que são executadas sequencialmente até serem concluídas com êxito. Você pode usar um pipeline de processamento para configurar o processo de geração de arquivos eletrônicos e a execução de outras etapas (por exemplo, assinatura digital de arquivos, o envio deles aos serviços Web externos e a análise da resposta e o recebimento e o processamento de documentos de entrada).

A lista de ações é predefinida. Você pode usar os botões **Novo** e **Excluir** para especificar a combinação de ações que define logicamente o processo necessário para enviar ou receber documentos.

A ordem das ações é importante. Você pode ajustar a ordem usando os botões **Para cima** e **Para baixo**.

Cada ação tem um conjunto de parâmetros que você pode definir ou ajustar. O conjunto específico de parâmetros depende do tipo de ação.

- **Ação** - Selecione o tipo de ação.
- **Nome** – insira o nome da ação da diretiva de localização. Esse nome aparecerá nos logs de envio e em mensagens nos aplicativos Finance e Supply Chain Management.
- **Descrição** – Fornece mais detalhes sobre a finalidade da ação no processo.
- **Habilitar nova tentativa** – Se você marcar esta caixa de seleção, poderá selecionar uma ação no campo **Ação de nova tentativa** e configurar parâmetros adicionais na guia **Parâmetros de nova tentativa**.

    A funcionalidade de repetição permite configurar o comportamento do serviço se uma ação específica não puder ser executada. Por exemplo, se o serviço Web externo ao qual você está tentando se conectar não responder, você poderá especificar quantas vezes o sistema deve tentar novamente a conexão, com que intervalo e em que ação no pipeline de processamento.

- **Exportar resultados** – Você pode marcar essa caixa de seleção para *uma* ação no pipeline de processamento. O arquivo eletrônico que a ação produz no aplicativo Finance ou Supply Chain Management pode ser exportado da página **Log de envio de documentos eletrônicos**.

### <a name="applicability-rules"></a>Regras de aplicabilidade

As *regras de aplicabilidade* são cláusulas configuráveis para fornecer um contexto para recursos de Faturamento eletrônico por meio do conjunto de recursos de faturamento eletrônico.
Os documentos de negócios enviados do Finance ou Supply Chain Management para o Faturamento eletrônico não possuem uma referência explícita que permita que o recurso de faturamento eletrônico chame uma versão específica do recurso de faturamento eletrônico e um item de configuração de recurso específico para processar o envio. No entanto, configurado corretamente, o documento de negócios contém os elementos necessários que permitem ao Faturamento para determinar qual versão de recurso de faturamento eletrônico e pipeline de processamento deve ser selecionada e executada.

As regras de aplicabilidade permitem que o serviço de Faturamento eletrônico encontre os recursos de Faturamento eletrônico exatos a serem usados para processar o envio. Para encontrar os recursos corretos, os campos **Contexto** do documento de negócios enviado são correspondidos com as cláusulas das regras de aplicabilidade.

Você pode trabalhar com as regras de aplicabilidade da seguinte maneira:

- Selecione **Novo** para adicionar uma nova cláusula a um conjunto de regras de aplicabilidade.
- Selecione **Excluir** para excluir a cláusula.
- Selecione vários registros e use o botão **Agrupar** ou **Desagrupar** para criar uma combinação de itens ou instruções lógicas. Por exemplo, selecione as linhas que deseja agrupar e selecione **Agrupar cláusula**. Quando as cláusulas são agrupadas, uma nova coluna é adicionada à grade. Esta coluna especifica o operador lógico para a cláusula agrupada. Há suporte disponível para os seguintes tipos de operadores:

    - Equal
    - Not equal
    - Maior que/menor que
    - Maior que ou igual a/Menor que ou igual a
    - Contains
    - Começa com

    > [!NOTE]
    > Ao desagrupar uma cláusula, sempre inicie do nível de agrupamento mais interno.

### <a name="variables"></a>Variáveis

As *Variáveis* dão mais flexibilidade ao configurar um pipeline de processamento e o fluxo de dados entre as ações. Você pode fazer referência a uma variável em alguns parâmetros de ação para armazenar temporariamente dados ou arquivos eletrônicos. Algumas variáveis são usadas para passar dados entre os aplicativos Finance ou Supply Chain Management e o serviço de faturamento eletrônico.

O sistema cria algumas variáveis por padrão. Por exemplo, a variável **BusinessDocumentDataModel** contém dados comerciais em uma estrutura JSON (JavaScript Object Notation) que vem na chamada do aplicativo conectado durante o processo de envio.

Estão disponíveis os seguintes tipos de variável:

- **Constante** – Um contêiner para armazenar dados temporários usados em ações do pipeline de processamento.
- **Do cliente** – O conteúdo da variável é adquirido do cliente do Dynamics 365 durante a execução do processo de envio.
- **Para o cliente** – O conteúdo da variável é disponibilizado para importação pelo cliente do Dynamics 365 durante a execução do processo de envio.
- **Tipo de dados** – Selecione o tipo de dados das informações armazenadas na variável.

### <a name="parameters"></a>Parâmetros

A opção **Desabilitar redução de dados de negócios** é usada para otimizar a estrutura da payload de dados de negócios que vem do aplicativo Finance ou Supply Chain Management durante o envio de documentos eletrônicos. A otimização ajuda a reduzir os dados que entram no serviço de Faturamento eletrônico para uma transformação adicional no arquivo eletrônico necessário. O valor padrão é **Não**.

- **Sim** – O Finance ou Supply Chain Management enviará um arquivo JSON da estrutura do **Modelo de fatura** ou **Modelo fiscal** (para o Brasil) definido no módulo de **Relatório eletrônico**. Todos os elementos do modelo são preenchidos com dados de negócios no lado do aplicativo, independentemente da estrutura de arquivo eletrônico final. Os modelos normalmente contêm mais dados de negócios do que a estrutura de arquivo de destino requer, e mais tempo pode ser necessário para gerar esses dados no aplicativo. O valor **Sim** é necessário para essa opção no evento raro de você desejar gerar arquivos de saída diferentes em um recurso de faturamento eletrônico e na configuração de recursos. O valor **Sim** é útil quando ao solucionar os problemas de seus cenários, a estrutura dos arquivos eletrônicos e a integridade dos dados de negócios.
- **Não** – O Finance ou Supply Chain Management fará a primeira chamada ao serviço sem qualquer dado de negócios. A finalidade dessa chamada é obter informações sobre a configuração de relatório eletrônico (ER) que será usada para a transformação eletrônica de arquivos no pipeline de processamento. Essas informações são retornadas ao aplicativo, que as usa para determinar o subconjunto de dados de negócios que devem ser incluídos no arquivo JSON da estrutura **Modelo de fatura** ou **Modelo fiscal** (para o Brasil). O valor **Não** para essa opção ajuda a reduzir o volume de dados de negócios que o aplicativo envia ao serviço, pois o aplicativo pode enviar somente os dados de negócios necessários para gerar com êxito um arquivo eletrônico.

### <a name="validate-a-feature-setup"></a>Validar uma configuração de recurso

Você pode executar uma validação para verificar a consistência de toda a configuração. Por exemplo, se um parâmetro obrigatório de uma ação tiver sido deixado em branco, a validação detectará essa inconsistência e você receberá uma mensagem de aviso.

- Na página **Configuração de versão do recurso**, no Painel de Ações, selecione **Validar**.

## <a name="delete-a-feature-setup"></a>Excluir uma configuração de recurso

1. Na página **Recursos de Faturamento eletrônico**, selecione uma versão de recurso de faturamento eletrônico que tenha um status de **Rascunho**.
2. Na guia **Configurações**, selecione **Excluir**.
3. Na caixa de mensagem exibida, selecione **Sim** para confirmar que você deseja excluir a configuração de recurso.
