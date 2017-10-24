---
title: "Nota fiscal eletrônica para serviços do Brasil"
description: "Este tópico oferece uma visão geral da nota fiscal eletrônica de serviço."
author: sndray
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BrazilParameters, ConfDefGroups_BR, ConfDefGroupWizard_BR, ConfDefLayout_BR, ConfExportDialog_BR, FiscalDocumentType_BR, RPSExport_BR, RPSImport_BR, TaxServiceCode_BR
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 269984
ms.assetid: 46e40a3a-784f-4a1e-b185-c4b8ad63518f
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3110c602b0e5cefa56d7248da8199a6160170b09
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="electronic-fiscal-document-for-services"></a>Nota fiscal eletrônica para serviços

[!include[banner](../includes/banner.md)]


Este tópico oferece uma visão geral da nota fiscal eletrônica de serviço.

Quando uma nota fiscal for sobre serviços no Brasil, regras diferentes serão aplicadas a uma nota fiscal eletrônica comum. O modelo de uma nota fiscal de serviços no Brasil é SE e inclui os impostos ISS, PIS e COFINS. 
[![Documento fiscal de serviço](./media/ServiceFiscalDocument.png)](./media/ServiceFiscalDocument.png) 

## <a name="recibo-provisorio-de-servicos-rps-document"></a>Documento RPS (Recibo Provisório de Serviços)
Quando uma empresa emite uma nota fiscal de serviço, dependendo da cidade na qual a fatura foi emitida, alguma regras e formatos podem ser aplicados. Por exemplo, na cidade de São Paulo, a nota fiscal de serviço é emitida como uma fatura de serviço temporária ou RPS. Esse documento torna-se uma nota fiscal eletrônica de serviço oficial quando ele é aprovado pela autoridade fiscal da cidade. Depois de aprovada, a empresa emite uma nota fiscal eletrônica de serviço oficial.

## <a name="rps-file"></a>Arq. RPS
Todas as cidades do Brasil têm sua própria comunicação de serviço (integração) e layout de formato. Não há um método padronizado de comunicação e formato. Por esse motivo, a localização brasileira atual usa um exemplo do layout da cidade de São Paulo. Para gerar um arquivo de RPS, gere os seguintes arquivos:

-   Um arquivo de saída que inclui uma ou mais notas fiscais de serviço com um status Em aberto (RPS).
-   Um arquivo de entrada no qual o arquivo original é retornado, mas inclui o número de nota fiscal oficial atribuído pela autoridade de impostos da cidade.

### <a name="rps-with-configurator"></a>RPS com configurador

A ferramenta Configurador gerencia o método de formatos de arquivo de pagamento para pagamentos eletrônicos e notas fiscais eletrônicas para serviços. Para configurar o Configurador, siga essas etapas:

-   Crie grupos de layouts e grupos de definições do configurador para os formatos de arquivo.
-   Exporte ou importe os grupos de layouts.
-   Exporte dados dos grupos de definições ou grupos de layouts usando o utilitário de exportação Configurador.

Você pode criar um grupo de definições configurando as tabelas e os campos que são usados para configurar o layout para o processo de exportação ou importação. Em seguida, é possível criar um grupo de layouts que define a estrutura do arquivo usada para importar ou exportar dados. Um grupo de definições será associado a um grupo de layout. O Configurador pode ser usado para gerar arquivos de saída e de entrada que atualizam a nota fiscal de serviço existente.

### <a name="rps-with-electronic-reporting"></a>RPS com relatórios eletrônicos

Um arquivo de saída de RPS pode ser gerado usando o relatório eletrônico, no qual cada formato de arquivo .txt é definido usando um modelo específico e um designer de formato do relatório eletrônico. Essas configurações podem ser importadas na empresa atual para gerar arquivos XML na página **Repositórios**. Também é possível importar essas configurações do Lifecycle Services (LCS) em **Biblioteca de ativos compartilhados** e **Tipo de ativo** = **Configurações de GER**. Os seguintes modelos e formatos do repositório devem ser carregados:

-   Modelo de documento fiscal de serviços (configuração do modelo)
-   RPS São Paulo V.002 (BR) (configuração de formato)

Depois que o repositório estiver disponível na página **Parâmetros brasileiros**, no **Relatório eletrônico**, selecione **Tipo =** **NFe de serviços**. Os detalhes do modelo representam o conjunto de serviços para transações da nota fiscal. Na página **Tipo de documentos fiscais**, é possível identificar o formato do arquivo. Selecione a opção **Nota fiscal eletrônica para serviços** e no campo **Formato para exportar arquivo**, selecione **Formato de configuração de ER**. **Observação**: Esta configuração se aplica quando um arquivo de saída de RPS precisa ser gerado. Você pode usar o modelo existente e criar outro formato para atender aos requisitos de outras cidades não suportadas na localização brasileira atual.

## <a name="prerequisites"></a>Pré-requisitos
#### <a name="service-code-configuration"></a>Configuração de código de serviço

Na página **Código de serviço**, é possível configurar o código de serviço relacionado necessário para a maioria da autoridade fiscal da cidade. Um código de serviço é obrigatório quando um tipo de documento fiscal tem modelo = **SE** é lançado. Além disso, você pode configurar um código de serviço específico por país/região, estado e cidade, pois a classificação pode ser diferente nas cidades.

#### <a name="services-on-delivery-address"></a>Serviços no endereço de entrega

Talvez seja necessário considerar o endereço de entrega da tributação de serviço correta, em vez de o endereço padrão. Nesses casos, na página **Ordem de Venda**, no grupo **Informações Fiscais**, no campo **Código de serviço no endereço de entrega**, insira o endereço de entrega.

## <a name="export-and-import-rps-files"></a>Exportação e importação de arquivos de RPS
Na página **Exportação e importação de RPS**, você pode gerar arquivos RPS de entrada e saída. Você cria o arquivo para enviar para a autoridade fiscal para processar todos os documentos RPS emitidos para tornar os documentos fiscais de serviços eletrônicos válidos. Após o processamento, você obtém um arquivo para importação. Depois que o arquivo é importado, os documentos originais são atualizados para refletir o status correto de todas as notas fiscais eletrônicas de serviços e RPS.

#### <a name="export"></a>Exportar

Na página **Exportar arquivo de RPS**, insira as seguintes informações.

-   **Data inicial** - Insira a data inicial do período para a qual os arquivos RPS serão exportados.
-   **Data final** - Insira a data final do período para a qual os arquivos RPS serão exportados.
-   **Do cliente** - Selecione o primeiro número da conta do cliente no intervalo de contas de cliente para inclusão.
-   **Até o cliente** - Selecione o último número da conta do cliente no intervalo de contas de cliente para inclusão.
-   **De RPS** - Insira o primeiro número de nota fiscal no intervalo de notas fiscais.
-   **Até o RPS** - Insira o último número de nota fiscal no intervalo de notas fiscais.
-   **ID do estabelecimento fiscal** - Selecione o identificador do estabelecimento fiscal.
-   **Tipo de documento fiscal** - Selecione o tipo de documento fiscal.
-   Selecione a opção **Incluir RPS previamente exportados** para incluir um arquivo RPS que já foi processado.
-   Clique em **OK** para exportar o arquivo RPS.

Quando você exporta um arquivo RPS, um arquivo de texto é gerado com base no grupo de layout do arquivo de exportação que é selecionado no campo **Exportar grupo de layouts de arquivo** ou no campo **Formato para exportar arquivo** na página **Tipos de documento fiscal** do tipo de documento fiscal selecionado.

#### <a name="import"></a>Importar

Na página **Importar arquivo RPS**, insira as seguintes informações:

-   **ID do estabelecimento fiscal** - Selecione o estabelecimento fiscal para o qual será importada a nota fiscal eletrônica.
-   **Tipo de documento fiscal** - Selecione o tipo de documento fiscal para a nota fiscal eletrônica de serviços.

Quando você importa uma nota fiscal eletrônica para serviços, as informações sobre essa nota fiscal, como a data de importação de RPS, o número da nota fiscal, a data da nota fiscal e o número de validação, são atualizadas com base no grupo do layout de arquivo de retorno especificado no campo **Grupo de layouts de arquivo de retorno** na página **Tipos de documento fiscal**.




