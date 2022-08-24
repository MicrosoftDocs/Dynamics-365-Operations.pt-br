---
title: Componentes de Relatório eletrônico
description: Este artigo descreve os componentes de ER (Relatório eletrônico).
author: kfend
ms.date: 09/28/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58941
ms.assetid: 5d51b6a6-ad12-4af9-a66d-a1eb820ae57f
ms.search.form: ERWorkspace
ms.openlocfilehash: 4851374ca4943a84d35f063e0ee65b537ec3b6cd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285021"
---
# <a name="electronic-reporting-components"></a>Componentes de Relatório eletrônico

[!include [banner](../includes/banner.md)]

O ER (Relatório eletrônico) oferece suporte aos seguintes tipos de componentes:

- Modelo de dados
- Mapeamento de modelo
- Formatar
- Metadados

## <a name="data-model-component"></a>Componente do modelo de dados

Um componente de modelo de dados é uma representação abstrata de uma estrutura de dados. Ele descreve uma área específica de domínio corporativo em detalhes suficientes para atender aos requisitos de relatórios para o domínio. Um componente de modelo de dados é composto pelas seguintes partes:

- **Modelo de dados** – um conjunto de entidades comerciais específicas de domínio, bem como a definição hierarquicamente estruturada de relações entre essas entidades.
- **Mapeamento de modelo** – as fontes de dados selecionadas do aplicativo estão vinculadas a elementos individuais de um modelo de dados que especifica, em runtime, o fluxo de dados e as regras de inserção de dados comerciais em um componente do modelo de dados.

A entidade comercial do modelo de dados é representada por um contêiner ou registro. As propriedades da entidade comercial são representadas como itens de dados ou campos. Cada item de dados tem um nome exclusivo, um rótulo, uma descrição e um valor. O valor de cada item de dados pode ser projetado para que seja reconhecido como cadeia de caracteres, inteiro, real, data, enumeração ou booliano. Além disso, o item de dados pode ser outro registro ou lista de registros.

Um único componente de modelo de dados pode conter várias hierarquias de entidades comerciais específicas de domínio. Também pode conter mapeamentos de modelo que oferecem suporte a um fluxo de dados específico do relatório em runtime. As hierarquias são diferenciadas por um único registro selecionado como uma raiz de mapeamento de modelo. Por exemplo, o modelo de dados da área de domínio de pagamento pode dar suporte aos seguintes mapeamentos:


- Empresa \> Fornecedor \> Transações de pagamento de domínio AP
- Cliente \> Empresa \> Transações de pagamento de domínio AR

As entidades de negócios, como transações de pagamento e de empresa, são projetadas somente uma vez. Diferentes mapeamentos podem reutilizá-las conforme necessário.

## <a name="model-mapping-component"></a>Componente de mapeamento de modelos

O mapeamento de modelo vincula fontes de dados selecionadas do aplicativo a elementos individuais de um modelo de dados que especifica, em runtime, o fluxo de dados e as regras de inserção de dados comerciais em um componente do modelo de dados.

Um mapeamento de modelo que oferece suporte a documentos eletrônicos de saída tem os seguintes recursos:

- Ele pode usar diferentes tipos de dados como fontes de dados para um modelo de dados. Esses tipos de dados incluem tabelas, entidades de dados, métodos e enumerações.
- Ele dá suporte a parâmetros de entrada do usuário que podem ser definidos como fontes para um modelo de dados quando alguns dados devem ser especificados em runtime.
- Ele dá suporte à transformação de dados para os grupos necessários. Você também pode filtrar, classificar e somar dados, além de acrescentar, com lógica calculada, campos projetados por meio de fórmulas que se assemelham às do Microsoft Excel. Para obter mais informações, consulte [Designer de fórmulas em ER (Relatório eletrônico)](general-electronic-reporting-formula-designer.md).

Um mapeamento de modelo que oferece suporte a documentos eletrônicos de entrada tem os seguintes recursos:

- Pode usar elementos de dados atualizáveis diferentes como metas. Esses elementos de dados incluem tabelas, entidades de dados e exibições. Os dados podem ser atualizados pelos dados de entrada de documentos eletrônicos. Diversos destinos podem ser usados em um único mapeamento de modelo.
- Ele dá suporte a parâmetros de entrada do usuário que podem ser definidos como fontes para um modelo de dados quando alguns dados devem ser especificados em runtime.

Um componente de modelo de dados é criado para cada domínio comercial usado como uma fonte de dados unificada para relatórios. A fonte de dados unificada isola a emissão de relatórios da implementação física das fontes de dados. O componente representa conceitos e funcionalidades comerciais específicas de domínio de uma forma que torna o design inicial do formato de relatório e a manutenção adicional mais eficientes.

## <a name="format-component"></a>Componente de formato

### <a name="format-components-for-outgoing-electronic-documents"></a>Componentes de formato para documentos eletrônicos de saída

Um componente de formato é o esquema de saída do relatório gerado em runtime. Um esquema é composto dos seguintes elementos:

- Um formato que define a estrutura e o conteúdo do documento eletrônico de saída gerado em runtime.
- Fontes de dados, como um conjunto de parâmetros de entrada do usuário e um modelo de dados de domínio específico que usa um mapeamento de modelo selecionado.
- Um mapeamento de formato, como um conjunto de associações de fontes de dados do formato, com elementos individuais de formato que especificam, em runtime, o fluxo de dados e as regras para a geração de saída do formato.
- Uma validação de formato, como um conjunto de regras configuráveis que controla a geração de relatórios em runtime, dependendo do contexto em execução. Por exemplo, pode haver uma regra que interrompe a geração de saída de pagamentos de um fornecedor e lança uma exceção quando os atributos específicos do fornecedor selecionado estão pendentes, como o número da conta bancária.

Um componente de formato suporta as seguintes funções:

- Criação de relatórios de saída como arquivos individuais em vários formatos, como texto, XML, documento do Microsoft Word ou planilha
- Criação de vários arquivos separadamente e o encapsulamento deles em arquivos zip

Um componente de formato permite anexar arquivos específicos que podem ser usados na saída do relatório da seguinte maneira:

- Contendo pastas de trabalho da planilha do Excel como um modelo para saídas no formato de planilha OPENXML;
- Arquivos de Word contendo um documento que pode ser usado como modelo para saída no formato de documento do Microsoft Word
- Os arquivos que podem ser incorporados na saída do formato como arquivos predefinidos

A ilustração a seguir mostra como os dados fluem para esses formatos.

[![Fluxo de dados para os componentes de formato de saída](./media/ER-overview-02.png)](./media/ER-overview-02.png)

Para executar uma única configuração de formato ER e gerar um documento eletrônico de saída é preciso identificar o mapeamento da configuração de formato.

#### <a name="format-components-for-incoming-electronic-documents"></a>Componentes de formato para documentos eletrônicos de entrada
Um componente de formato é o esquema do documento de entrada que é importado em tempo de execução. Um esquema é composto dos seguintes elementos:

- Um formato que define a estrutura e o conteúdo do documento eletrônico de entrada que contém dados importados em tempo de execução. Um componente de formato é usado para analisar um documento de entrada em vários formatos, como texto e XML.
- Um mapeamento de formato que vincula os elementos de formato individuais aos elementos de um modelo de dados de domínio específico. Em tempo de execução, os elementos no modelo de dados especificam o fluxo de dados e as regras para importar dados de um documento de entrada e, em seguida, armazenar os dados em um modelo de dados.
- Uma validação de formato, como um conjunto de regras configuráveis que controla a importação de dados em tempo de execução, dependendo do contexto em execução. Por exemplo, pode haver uma regra que interrompe a importação de dados de um extrato bancário com os pagamentos do fornecedor e lança uma exceção quando os atributos de um fornecedor específico estão pendentes, como o código de identificação do fornecedor.

A ilustração a seguir mostra como os dados fluem para esses formatos.

[![Fluxo de dados para os componentes de formato de entrada](./media/ER-overview-03.png)](./media/ER-overview-03.png)

Para executar uma única configuração de formato de ER para importar dados de um documento eletrônico de entrada, é preciso identificar o mapeamento desejado de uma configuração de formato, e também o ponto de integração de um mapeamento de modelo. Você pode usar o mesmo mapeamento de modelo e destinos juntamente com diferentes formatos para diferentes tipos de documentos recebidos.


## <a name="component-versioning"></a>Controle de versão em componentes

Controle de versão tem suporte para componentes ER. O seguinte fluxo de trabalho é fornecido para gerenciar alterações em componentes ER:

1. A versão que foi originalmente criada está marcada como uma versão **Rascunho**. Essa versão pode ser editada e está disponível para a execução do teste.
2. A versão **Rascunho** pode ser convertida em uma versão **Concluída**. Essa versão pode ser usada em processos de geração de relatórios locais.
3. A versão **Concluída** pode ser convertida em uma versão **Compartilhada**. Essa versão é publicada no Microsoft Dynamics LCS (Lifecycle Services) e pode ser usada em processos de relatórios globais.
4. A versão **Compartilhada** pode ser convertida em uma versão **Descontinuada**. Essa versão pode ser excluída.

As versões com o status **Concluída** ou **Compartilhada** estão disponíveis para outra troca de dados. As seguintes ações podem ser executadas em um componente que tem esse status:

- O componente pode ser serializado em formato XML e exportado como um arquivo no formato XML.
- O componente pode ser seriado novamente de um arquivo XML e importado para o aplicativo como uma nova versão de um componente de ER.

Para mais informações, consulte [Importar uma nova configuração de modelos de dados](er-quick-start1-new-solution.md#ImportDataModel) e [Exportar a versão de conclusão de um formato derivado](er-calculated-field-type.md#export-completed-version-of-a-derived-format).

### <a name="draft-versions-at-runtime"></a>Versões de rascunho no runtime

Nos parâmetros de usuário pessoal da estrutura ER, você pode habilitar a opção que permite especificar se a versão de rascunho de uma configuração ER deve ser usada no runtime. Para obter informações sobre como disponibilizar a opção disponível **Executar rascunho** para suas configurações de ER, consulte [Marcar um formato personalizado como executável](er-quick-start2-customize-report.md#MarkFormatRunnable).

> [!NOTE]
> Os parâmetros de usuário de ER são específicos do usuário e da empresa.

### <a name="draft-format-versions-at-runtime"></a>Versões de formato rascunho no runtime

Por padrão, quando você executa uma solução de ER, as versões de rascunho de seus componentes de formato são ignoradas. Em vez disso, somente a versão relevante que tem um status diferente de **Rascunho** é usada. Às vezes, você pode optar por forçar o ER a usar a versão de rascunho da configuração de formato ER no runtime. Por exemplo, depois de introduzir as alterações necessárias na sua versão de rascunho, você pode usar essa versão de rascunho para executar o teste. Dessa forma, você pode validar a exatidão de suas mudanças. Para começar a usar a versão do formato "rascunho", você deve [configurar](er-quick-start2-customize-report.md#MarkFormatRunnable) a opção **Executar rascunho** da configuração relevante de ER para **Sim**.

### <a name="draft-model-mapping-versions-at-runtime"></a>Versões de mapeamento de modelos de rascunho no runtime

Por padrão, quando você executa uma solução de ER, as versões de rascunho de seus componentes de mapeamento do modelo são sempre utilizadas. Às vezes, você pode optar por forçar o ER a ignorar a versão de rascunho da configuração de mapeamento do modelo de ER no runtime. Na **versão 10.0.29 e posterior**, você pode habilitar o recurso **Sempre levar em consideração a opção "Executar rascunho" para mapeamentos de modelo ER** a fim de controlar a versão de mapeamento de modelos usada no runtime. Quando este recurso é habilitado, o seguinte comportamento ocorre:

- Quando a opção **Executar rascunho** está definida como **Não** para uma configuração de mapeamento de modelo, a versão mais elevada sem rascunho dessa configuração é usada no runtime. Uma exceção será lançada se a configuração não estiver disponível na atual instância do Finance.
- Quando a opção **Executar rascunho** está definida como **Sim** para uma configuração de mapeamento de modelo, a versão de rascunho dessa configuração é usada no runtime.

## <a name="component-date-effectivity"></a>Efetivação de data de componente

Versões do componente ER com efetivação de data. Você pode definir a data de "efetivação a partir de" para que um componente do formato ER especifique a data em que esse componente entrará em vigor para os processos de relatório. A data da sessão do aplicativo é usada para definir se um componente é válido para execução. Se mais de uma versão for válida para uma data específica, a última versão será usada para processos de relatório.

## <a name="component-access"></a>Acesso ao componente

O acesso aos componentes de mapeamento do modelo do formato ER no runtime depende da configuração para o código de país/região da Organização Internacional de Normalização (ISO). Se essa configuração estiver em branco para uma versão selecionada de uma configuração de mapeamento do modelo, um componente de mapeamento do formato ou modelo poderá ser acessado de qualquer empresa em runtime. Se essa configuração contiver códigos de país/região ISO, um componente de mapeamento do formato ou modelo estará disponível apenas em empresas em que o endereço principal for definido para um dos códigos de país/região ISO do componente de formato.

Versões diferentes de um componente de mapeamento do formato ou modelo podem ter diferentes configurações de códigos de país/região ISO.

Para mais informações, consulte [Configurar mapeamentos do modelo ER dependente do contexto do país](er-country-dependent-model-mapping.md).

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

