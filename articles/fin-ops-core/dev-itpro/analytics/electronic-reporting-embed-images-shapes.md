---
title: Inserir imagens e formas em documentos que você gerar usando ER
description: Este tópico explica como usar a ferramenta de Relatórios eletrônicos (ER) para gerar documentos comerciais que têm imagens e formas incorporadas.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: bfa8137de7b782ba80a0d80c987a96c37b3a7d86
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6361369"
---
# <a name="embed-images-and-shapes-in-documents-that-you-generate-by-using-er"></a>Inserir imagens e formas em documentos que você gerar usando ER

[!include [banner](../includes/banner.md)]

Você pode usar a ferramenta de Relatório eletrônico (ER) e criar relatórios que podem ser executados para gerar os documentos eletrônicos necessários. Você pode usar o Microsoft Excel ou Microsoft Word ou para especificar o layout de um relatório. O designer de Operações de ER permite anexar o documento do Excel ou do Word como um modelo para o relatório. Os elementos nomeados no modelo anexado estão associados aos elementos de formato do relatório de ER. Os elementos de formato do relatório são vinculados a fontes de dados. Esses elementos especificam os dados que serão inseridos, no tempo de execução, nos documentos gerados que forem gerados.

Essa nova funcionalidade vai além dos recursos de ER existentes para criar documentos em formatos do Microsoft Office. Para obter mais informações, execute os seguintes guias de tarefas. Você pode encontrar essas guias de tarefas no processo de negócios 7.5.4.3 Adquirir/Desenvolver componentes de soluções e serviços de TI (10677).

- O ER cria uma configuração para gerar relatórios no formato OPENXML
- ER Criar uma configuração para gerar relatórios no formato Microsoft WORD

## <a name="embed-an-image-in-an-excel-document"></a>Incorporar uma imagem em um documento do Excel

### <a name="embed-an-image-in-an-excel-worksheet"></a>Incorporar uma imagem em uma planilha do Excel

Primeiro, você deve adicionar um espaço reservado para a imagem em um documento do Excel. Abra uma pasta de trabalho do Excel e adicione uma imagem como um espaço reservado para a imagem que será adicionada posteriormente. Em seguida, use a ferramenta de ER para adicionar uma nova configuração de formato de ER e incluir o relatório que você está criando. Anexe a pasta de trabalho do Excel como um modelo para o formato do relatório e importe o conteúdo da pasta de trabalho no formato de ER. A definição de formato será criada automaticamente. O espaço reservado de imagem adicionado será incluído na definição de formato de ER como um elemento **CÉLULA**.

> [!NOTE]
> Você pode especificar manualmente a definição de formato em vez de importá-la. Quando você salvar as alterações, o formato será validado.

Em seguida, vincule o elemento **CÉLULA** do formato de ER ao campo da fonte de dados do formato, que fornece os dados da imagem no formato binário no tempo de execução. Quando um modelo de dados de ER é usado como uma fonte de dados de formato, o tipo de dados do campo deve ser [Contêiner](er-formula-supported-data-types-composite.md#container). No momento, um campo de modelo de dados ER que tem o tipo de dados [Contêiner](er-formula-supported-data-types-composite.md#container) pode ser vinculado a vários tipos de fontes de dados que retornam imagens no formato binário. Você pode acessar um campo em uma tabela de dados e um arquivo anexado ao registro da tabela de dados usando a Estrutura de gerenciamento de documentos.

> [!IMPORTANT]
> - Se você deseja preencher o espaço reservado de imagem no documento que está criando usando o modelo do Excel, o formato de ER deve conter o elemento **CÉLULA** que se refere ao elemento de imagem nomeado no modelo do Excel. Caso contrário, nenhum espaço reservado de imagem será exibido na saída do relatório. Se a associação de um elemento **CÉLULA** não retornar dados no tempo de execução, o documento gerado mostrará o espaço reservado de imagem com base no modelo. Para ocultar uma imagem no documento que está sendo gerado, defina um elemento **CÉLULA** e especifique que a expressão **Habilitação** deve retornar um valor **FALSO**.
> - No modelo do Excel, use um nome exclusivo para cada elemento. Esses elementos incluem imagens e células. Se você duplicar um nome de elemento, o conteúdo do relatório gerado será ambíguo e confuso.

### <a name="embed-images-in-the-header-and-footer-of-an-excel-worksheet"></a>Incorporar imagens no cabeçalho e no rodapé de uma planilha do Excel

Use o documento de pasta de trabalho do Excel como um modelo para especificar o layout de um relatório. A pasta de trabalho pode conter várias planilhas, e cada uma delas pode ser criada para ter um cabeçalho e um rodapé. O Excel oferece suporte a até três imagens no cabeçalho e no rodapé de cada planilha. As imagens podem ser alinhadas à esquerda e direita ou no centro.

Na versão 10.0.21 do Finance, você pode gerenciar as imagens de cabeçalho e rodapé geradas por uma solução de ER que tem um modelo do Excel.

Se desejar que uma imagem padrão apareça no cabeçalho ou no rodapé de um documento gerado, você poderá adicionar uma imagem ao cabeçalho ou rodapé de uma planilha de um modelo de ER. Para acessar essa imagem no formato de ER, você deve adicionar o componente **Imagem** no componente [Cabeçalho](er-fillable-excel.md#header-component) ou [Rodapé](er-fillable-excel.md#footer-component) do formato. Configure o alinhamento do componente **Imagem** conforme apropriado. 

Você também pode usar o componente **Imagem** para colocar uma imagem no cabeçalho ou no rodapé de um documento gerado no tempo de execução, mesmo que o modelo não tenha uma imagem padrão. Para especificar o conteúdo de mídia que deve ser inserido no cabeçalho ou rodapé de um documento gerado como uma nova imagem ou substituição de uma imagem padrão, você deve vincular o componente **Imagem** a uma fonte de dados do tipo [Contêiner](er-formula-supported-data-types-composite.md#container) que representa uma imagem no formato binário.

Cada componente **Cabeçalho** ou **Rodapé** pode conter um componente **Imagem** para cada alinhamento aceito: **Esquerda**, **Centro** e **Direita**.

A propriedade **Dimensionar a altura** do componente **Imagem** permite usar a associação configurada para controlar o tamanho de uma imagem:

- Selecione **Original** para manter o tamanho inicial da imagem.
- Selecione **Relativo** para ajustar a escala de altura da imagem em proporção à altura do cabeçalho ou rodapé que contêm a imagem.

    - Nesse caso, a altura da imagem deve ser definida como uma porcentagem do cabeçalho ou rodapé pai.
    - Se o valor de escala exceder 100%, a imagem poderá se sobrepor à área de dados da planilha correspondente.
    - Se a altura da imagem for alterada quando a escala for aplicada, a largura também será alterada para manter a taxa de proporção original da imagem.

- Selecione **Absoluto** para redimensionar a imagem de acordo com os valores de altura e largura (em pixels) fornecidos no momento da criação.

    - Se a altura especificada exceder a altura do cabeçalho ou rodapé pai, a imagem poderá se sobrepor à área de dados da planilha correspondente.

Você também pode usar a propriedade **Habilitado** do componente **Imagem** para controlar a visibilidade de uma imagem que é inserida em um documento gerado usando esse componente.

> [!NOTE]
> É necessário usar o designer de formato de ER para adicionar um componente **Imagem** ao formato de ER editável. Você não pode adicionar o componente ao usar o espaço de trabalho [Gerenciamento de documentos comerciais](er-business-document-management.md) para editar o modelo de um documento comercial.

Para saber mais sobre essa funcionalidade, siga as etapas em [Criar um formato de ER para gerar um relatório no formato do Excel com imagens incorporadas em cabeçalhos ou rodapés de página](er-embed-images-header-footer-excel-reports.md).

## <a name="embed-a-shape-in-an-excel-document"></a>Incorporar uma forma em um documento do Excel

Primeiro, você deve adicionar um espaço reservado para a forma em um documento do Excel. Abra uma pasta de trabalho do Excel e selecione **Forma**, **Caixa de texto** ou a **WordArt** como um espaço reservado para a forma. Em seguida, use a ferramenta de ER para adicionar uma nova configuração de formato de ER e incluir o relatório que você está criando. Anexe a pasta de trabalho do Excel como um modelo para o formato do relatório e importe o conteúdo da pasta de trabalho no formato de ER. A definição de formato será criada automaticamente. O espaço reservado da forma adicionado será incluído na definição do formato de ER como um elemento **CÉLULA** que se refere ao elemento de forma nomeado do Excel.

> [!NOTE]
> Você pode especificar manualmente a definição de formato em vez de importá-la. Quando você salvar as alterações, o formato será validado.

Em seguida, vincule o elemento **CÉLULA** do formato de ER ao campo da fonte de dados do formato, que fornece os dados no tempo de execução. Esses dados podem ser convertidos em uma sequência de texto. Quando o elemento **CÉLULA** no formato de ER se referir a um elemento de forma no modelo do Excel que oferece suporte ao texto, o texto fornecido por essa associação no tempo de execução será mostrado em uma forma no documento que for gerado.

> [!IMPORTANT]
> - Se você quiser usar o modelo do Excel que inclui o espaço reservado para forma para gerar um novo documento, o formato de ER deve conter um elemento **CÉLULA** que faça referência ao elemento de forma do Excel. Caso contrário, nenhum espaço reservado de forma será exibido na saída do relatório. Se a associação de um elemento **CÉLULA** que faz referência ao elemento de forma do Excel nomeado não retornar dados no tempo de execução, o documento gerado mostrará o texto do espaço reservado da forma do modelo do Excel. Para ocultar uma forma no documento que está sendo gerado, defina um elemento **CÉLULA** que faz referência ao elemento de forma nomeado do Excel e especifique que a expressão **Habilitação** deve retornar um valor **FALSO**.
> - No modelo do Excel, use um nome exclusivo para cada elemento. Esses elementos incluem formas e células. Se você duplicar um nome de elemento, o conteúdo do relatório gerado será ambíguo e confuso.

## <a name="embed-an-image-in-a-word-document"></a>Incorporar uma imagem em um documento do Word
> [!IMPORTANT]
> Você pode reutilizar o formato de ER que usa um modelo do Excel para criar documentos que incluam imagens incorporadas. No formato de ER, certifique-se de que um nome esteja especificado para o elemento **CÉLULA** que se refere a um elemento de imagem nomeado no Excel e que esteja associado a uma fonte de dados que retorne uma imagem no tempo de execução.

Primeiro, você deve configurar o layout do documento do Word. Use o controle **Conteúdo de imagem** para criar um espaço reservado para a imagem incorporada. Para acessar este controle, você deve primeiro tornar a guia **Desenvolvedor** visível na faixa de opções do Word.

Em seguida, exclua o modelo do Excel do formato de ER e anexe o documento de modelo do Word. Atualize a referência ao modelo e salve as alterações. A estrutura hierárquica do formato de ER atual é salvo no modelo do Word como uma nova parte XML personalizada chamada **Relatório**.

Em seguida, salve o modelo do Word para o formato de ER atual no seu computador local. Abra o modelo e abra o painel **Mapeamento de XML**. Localize o componente XML personalizado que chamado **Relatório** e depois aponte para o elemento **CÉLULA** no relatório de ER que está associado a uma fonte de dados que retorna uma imagem no formato binário. Mapeie este item da parte XML para o controle **Conteúdo de imagem** selecionado e salve suas alterações.

[![incorporar imagens.](./media/embed-images-shapes-01.png)](./media/embed-images-shapes-01.png)

Por fim, exclua o modelo do Word do formato de ER e anexe o documento do Word que inclui as partes XML personalizadas mapeadas. Atualize a referência de formato para o modelo e salve as alterações feitas no formato de ER.

## <a name="more-information"></a>Mais informações
Para se familiarizar com os detalhes desse recurso, execute o conjunto de guias de tarefas, **ER Criar relatórios nos formatos do MS Office com imagens incorporadas**. Essas guias de tarefas mostram como você pode incorporar as imagens do logotipo da empresa e a assinatura de uma pessoa autorizada nos cheques de pagamento que são gerados usando a ferramenta de ER no Excel e nos documentos do Word.

A tabela a seguir lista os arquivos necessários para concluir os guias de tarefas **ER Criar relatórios nos formatos do MS Office com imagens incorporadas**. Baixe e salve os arquivos no computador local.

| descrição                                          | Nome do arquivo                   |
|------------------------------------------------------|-----------------------------|
| Configuração do modelo de dados de ER                          | [Modelo para cheques.xml](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)       |
| Configuração de formato ER                              | [Formato de impressão de cheques.xml](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |
| Imagem do logotipo da empresa                                   | [Company logo.png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png)            |
| Imagem de assinatura                                      | [Signature image.png](https://download.microsoft.com/download/5/0/9/509151b3-06fc-4870-9408-7c9a43b72771/Signatureimage.png)         |
| Imagem de assinatura alternativa                          | [Signature image 2.png](https://download.microsoft.com/download/3/0/0/30045bf1-0ff6-4215-9162-b77c2f5dcc7c/Signatureimage2.png)       |
| Modelo do Microsoft Word para imprimir cheques de pagamento  | [Cheque template Word.docx](https://download.microsoft.com/download/4/4/d/44d9d255-9ad1-42fe-87db-23f319fd8e89/ChequetemplateWord.docx)   |
| Modelo do Microsoft Excel para imprimir cheques de pagamento | [Modelo de cheque.xlsx](https://download.microsoft.com/download/1/f/6/1f671963-73aa-48d5-ae69-45f21fe7dfb4/Cheque%20template.xlsx)        |

O gráfico a seguir fornece um exemplo do teste impresso para uma verificação de pagamento gerada com base no modelo do Excel.

[![Impressão do teste de verificação de pagamento.](./media/embed-images-shapes-02.png)](./media/embed-images-shapes-02.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
