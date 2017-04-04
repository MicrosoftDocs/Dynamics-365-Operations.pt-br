---
title: "Nota fiscal eletrônico de serviço para O Brasil"
description: "Este tópico fornece uma visão geral de documento fiscal eletrônico de serviço."
author: ShylaThompson
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BrazilParameters, ConfDefGroups_BR, ConfDefGroupWizard_BR, ConfDefLayout_BR, ConfExportDialog_BR, FiscalDocumentType_BR, RPSExport_BR, RPSImport_BR, TaxServiceCode_BR
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269984
ms.assetid: 46e40a3a-784f-4a1e-b185-c4b8ad63518f
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 51f3a4495396f9144dddad48bf83989860118b98
ms.lasthandoff: 03/31/2017


---

# <a name="electronic-fiscal-document-for-services"></a>Nota fiscal eletrônica para serviços

Este tópico fornece uma visão geral de documento fiscal eletrônico de serviço.

Quando um documento for imposto sobre serviço no Brasil, regras diferentes se aplicam a um documento fiscal eletrônico normal. O esquema de um documento fiscal de serviços no Brasil se SE e inclui impostos de ISS, de, PIS e COFINS. [] (https://msdynamics.blob.core.windows.net/media/2017/02/ServiceFiscalDocument.jpg)

## <a name="recibo-provisorio-de-servicos-rps-document"></a>Documento de Recebimento Provisorio de Servicos (RPS)
Quando uma empresa liquida uma nota fiscal de serviço, dependendo da cidade onde a nota fiscal foi emitida, algumas regras e formatos podem ser aplicados. Por exemplo, a cidade de Sao Paulo, a nota fiscal de serviços é emitido como uma fatura de serviço ou um RPS temporário. O documento se um documento fiscal eletrônico oficial de serviço é aprovada pela autoridade fiscal da cidade. Depois de ser aprovado, a empresa liquida uma nota fiscal eletrônico oficial de serviço.

## <a name="rps-file"></a>Arquivo RPS
Todas as cidades em O Brasil têm sua própria comunicação de serviço (integração) e o layout. formatam Não há um método padronizado de comunicação e o formato. Por esse motivo, a localização brasileira atual usa um exemplo do layout da cidade de Sao Paulo. Para gerar um arquivo de RPS, gerencia os seguintes arquivos:

-   Um arquivo de saída que inclua uma ou mais notas fiscais de serviço com um status em aberto (RPS).
-   Um arquivo de entrada que o arquivo seja retornado original mas inclui o número de nota fiscal oficial atribuído pela autoridade de impostos da cidade.

### <a name="rps-with-configurator"></a>RPS com configurador

A ferramenta de configurador gerencia o método de formatos de arquivo de pagamento para pagamentos eletrônicos e notas fiscais eletrônicos para serviços. Para configurar o configurador, rastrear estas etapas:

-   Crie grupos de layouts e grupos de definições do configurador para os formatos de arquivo.
-   Exporte ou importe os grupos de layouts.
-   Exporte dados dos grupos de definições ou grupos de layouts usando o utilitário de exportação Configurador.

Você pode criar um grupo de definição a tabelas e campos que são usados para configurar o layout para o processo da exportação ou importação. É possível criar um grupo de layout que define a estrutura de arquivo usados para importar ou exportar dados. Um grupo de definições será anexado a um grupo do layout. O configurador pode ser usado para gerar arquivos de saída e de entrada que atualizam o documento fiscal de serviço existente.

### <a name="rps-with-electronic-reporting"></a>RPS com relatório eletrônico

Um arquivo de saída de RPS pode ser gerado usando o relatório eletrônico, em cada formato de arquivo de .txt é definido com um designer modelo específico e o formato do relatório eletrônico. Essas configurações podem ser importados na empresa atual para gerar arquivos XML ** repositórios ** na página. Você também pode importar essas configurações serviços (LCS) do ciclo de vida ** na biblioteca de ativo compartilhado ** e ** tipo de ativo ** = ** configurações de GER **. O seguinte armazenamento modelagem e os formatos forem ser cobrados:

-   Modelo de documento fiscal de serviços (configuração modelo)
-   RPS Sao Paulo V.002 (BR) (configuração de formato)

Depois que a loja está disponível, em parâmetros ** ** brasileiros página ** relatório, em eletrônico **, ** tipo = ** ** selecione NFeServices **. Detalhes de modelo representam o conjunto de serviços para transações do documento. ** Tipo de documento fiscal ** na página, você pode identificar o formato de arquivo. Selecione ** documento fiscal para eletrônico serviços ** a opção e, no mapeamento ** exportar formatar ** campo, selecione ** formato de configuração de ER **. ** Nota **: Esta configuração se aplica quando um arquivo de saída de RPS precisa ser gerado. Você pode usar o modelo existente e criar outro formato para atender os requisitos das cidades outras não suporte na localização brasileira atual.

## <a name="prerequisites"></a>Pré-requisitos
#### <a name="service-code-configuration"></a>Configuração de código de serviço

** ** Código de serviço na página, é possível configurar o código de serviço relacionados necessário para a autoridade de impostos sobre cidade da maioria. Um código de serviço é obrigatório quando um tipo de documento fiscal com modelos = ** ** SE for lançado. Além disso, você pode configurar um código de serviço específico por país/região, estado e cidade, pois a classificação pode ser diferente as cidades.

#### <a name="services-on-delivery-address"></a>Serviços do endereço de entrega

Talvez seja necessário considerar o endereço de entrega da tributação de serviço correta em vez de endereço padrão. Em caso, em ordem de venda ** **, página em ** informações fiscais, grupos ** ** de serviço ao código do endereço de entrega em ** campo, insira o endereço de entrega.

## <a name="export-and-import-rps-files"></a>Exportar e importar arquivos de RPS
** Exportação e importação de RPS ** na página, é possível gerar arquivos de saída e de entrada de RPS. Criar o arquivo para enviar para a autoridade fiscal para processar os documentos emissores RPS para a transformação de notas fiscais de serviço eletrônicos válidos. Depois que suzana, você consegue um arquivo de importação. Após o arquivo é importado, os documentos originais são atualizadas para refletirem correto o status de qualquer RPS e notas fiscais de serviço eletrônicos.

#### <a name="export"></a>Exportar

** RPS de arquivo de exportação ** na página, insira as seguintes informações.

-   ** De data ** - insira a data inicial do período para os arquivos de RPS serão exportados.
-   ** Até ** - insira a data final do período para o qual os arquivos de RPS serão exportados.
-   ** De clientes ** - selecione o primeiro número de conta de cliente no intervalo de contas de cliente para incluir.
-   ** O cliente ** - selecione o número de conta do cliente no último intervalo de contas de cliente para incluir.
-   ** De RPS ** - insira o primeiro número de nota fiscal no intervalo de notas fiscais.
-   ** O RPS ** - insira o número da o último em intervalo de notas fiscais.
-   ** ID estabelecimento fiscal ** - selecione o identificador do estabelecimento fiscal.
-   ** Tipo de documento fiscal ** - selecione o tipo de documento fiscal.
-   ** O inclua selecione RPS exportado anteriormente ** a opção incluir um arquivo de RPS que seja processado.
-   ** ** Clique em OK para exportar o arquivo de RPS.

Quando você exporta RPS de um arquivo, um arquivo de texto é gerado com base em grupo de leiaute de arquivo de exportação selecionado ** exportar o grupo de leiaute ** de arquivo no campo ou ** mapeamento formato de exportação em campo ** ** tipos de documento fiscal ** na página para o tipo de documento fiscal selecionado.

#### <a name="import"></a>Importar

** RPS de arquivo de importação ** na página, insira as seguintes informações:

-   ** ID estabelecimento fiscal ** - marque o estabelecimento fiscal para importar o documento fiscal para eletrônico para serviços.
-   ** Tipo de documento fiscal ** - selecione o tipo de documento fiscal para a nota fiscal eletrônico para serviços.

Quando você importa um documento fiscal para eletrônico serviços, informações sobre a nota fiscal eletrônico de serviço, como a data de importação de RPS, número de nota fiscal, data de documento fiscal, número e validação, é atualizado com base em grupo de leiaute de arquivo especificado ** retornar o grupo de leiaute ** de arquivo no campo ** tipos de documento fiscal ** na página.


