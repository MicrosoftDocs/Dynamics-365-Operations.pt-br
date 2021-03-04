---
title: Importar arquivos no formato XML com atributos opcionais
description: Este tópico fornece informações sobre como criar formatos de ER que especificam atributos XML para analisar documentos eletrônicos de entrada no formato XML.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 14b14dd609805a7cf9331427012b991791698cfd
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686652"
---
# <a name="import-files-in-xml-format-with-optional-attributes"></a>Importar arquivos no formato XML com atributos opcionais

[!include [banner](../includes/banner.md)]

Você pode criar formatos de relatórios eletrônicos (ER) para analisar documentos eletrônicos de entrada no formato XML. Certos atributos de elementos XML podem ser especificados em formato de ER criado como opcional. Ele permitirá que você trate arquivos de entrada com e sem esses atributos XML corretamente. Você pode usar o conteúdo desses arquivos para atualizar dados do aplicativo.

Para saber mais sobre este recurso, conclua as etapas no tópico [(RCS) Importação de arquivos em formato XML com atributos opcionais](tasks/import-files-xml-format-optional-attributes.md), que faz parte do processo empresarial 7.5.4.3 Adquirir/Desenvolver componentes de serviço/solução de TI (10677). É possível baixar os arquivos desta guia de tarefas e do exemplo associado no [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).


| Descrição do conteúdo       | Arquivo                                                         |
|---------------------------|--------------------------------------------------------------|
| Arquivo de exemplo no formato XML | IncomingDocumentToLearnHowToHandleOptionalAttributes.xml     |
| Guias de tarefas                | RCS Importar arquivos no formato XML com atributos opcionais.axtr |


As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de formato ER para importar arquivos no formato XML contendo atributos opcionais. Para concluir estas etapas, primeiro conclua as etapas do procedimento [Criar provedores de configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md). Antes de começar, baixe e salve localmente o arquivo IncomingDocumentToLearnHowToHandleOptionalAttributes.xml do Centro de Download da Microsoft (https://go.microsoft.com/fwlink/?linkid=874684).

1. Vá para **Administração da organização** > **Espaços de trabalho** > **Relatório eletrônico**.
2. Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como **Ativo**. Se você não visualizar este provedor de configuração, conclua as etapas no tópico [Criar provedores de configuração e marcá-los como ativos](tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. Clique em **Configurações de relatórios**.

## <a name="create-a-new-data-model-configuration"></a>Criar uma nova configuração de modelo de dados
1. Clique em **Criar configuração** para abrir a caixa de diálogo suspensa.
2. No campo **Nome**, digite 'Modelo para importar arquivo xml'.
3. Clique em **Criar configuração**.
4. Clique em **Designer**.
5. Clique em **Novo** para abrir a caixa de diálogo suspensa.
6. No campo **Nome**, digite 'Raiz'.
7. Clique em **Adicionar**.
8. Clique em **Novo** para abrir a caixa de diálogo suspensa.
9. No campo **Nome**, digite 'Lista'.
10.    No campo **Tipo de item**, selecione **Lista de registros**.
11.    Clique em **Adicionar**.
12.    Clique em **Novo** para abrir a caixa de diálogo suspensa.
13.    No campo **Nome**, digite 'Código'.
14.    No campo **Tipo de item**, selecione **String**.
15.    Clique em **Adicionar**.
16.    Clique em **Salvar**.
17.    Feche a página.
18.    Clique em **Alterar status**.
19.    Clique em **Concluir**.
20.    Clique em **OK**.

## <a name="create-a-format-for-data-import"></a>Crie um formato de importação de dados
1. Clique em **Criar configuração** para abrir a caixa de diálogo suspensa.
2. No campo **Novo**, insira 'Formato baseado no modelo de dados. Modelo para importar arquivo xml'.
3. No campo **Nome**, digite 'Formatar para importar arquivo xml'. 
4. Selecione **Sim** no campo **Dá suporte à importação de dados**.
5. Clique em **Criar configuração**.

## <a name="design-a-format-to-parse-incoming-file-in-xml-format"></a>Crie um formato para analisar o arquivo de entrada no formato xml
1. Clique em **Designer**.
2. Clique em **Adicionar raiz** para abrir a caixa de diálogo suspensa.
3. Na árvore, selecione **XML\Elemento**.
4. No campo **Nome**, digite 'raiz'.
5. Clique em **OK**.
6. Clique em **Adicionar** para abrir a caixa de diálogo suspensa.
7. Na árvore, selecione **XML\Elemento**.
8. No campo **Nome**, digite 'documento'.
9. No campo **Multiplicidade**, selecione **Um muitos**.
10.    Clique em **OK**.
11.    Na árvore, selecione **raiz\documento**.
12.    Clique em **Adicionar** para abrir a caixa de diálogo suspensa.
13.    Na árvore, selecione **XML\Attribute**.
14.    No campo **Nome**, digite 'id'.
15.    Clique em **OK**.
16.    Clique em **Salvar**.

## <a name="design-a-format-mapping-to-save-parsed-information-to-data-model"></a>Crie um mapeamento de formato para salvar informações analisadas modelo de dados
1.    Clique em **Mapear formato para modelo**.
2.    Clique em **Novo**.
3.    No campo **Definição**, insira ou selecione um valor.
4.    No campo **Nome**, digite 'Mapeamento'.
5.    Clique em **Salvar**.
6.    Clique em **Designer**.
7.    Na árvore, expanda **formato**.
8.    Na árvore, expanda **format\root: XML Element(root)**.
9.    Na árvore, selecione **format\root: XML Element(root)\document: XML Element 1..* (documento)**.
10.    Clique em **Associar**.
11.    Na árvore, expanda **format\root: XML Element(root)\document: XML Element 1..* (documento)**.
12.    Na árvore, selecione **format\root: XML Element(root)\document: XML Element 1..* (documento)\id**.
13.    Na árvore, expanda **List = format.root.document**.
14.    Na árvore, selecione **List = format.root.document\Code**.
15.    Clique em **Associar**.
16.    Clique em **Salvar**.
17.    Feche a página.

## <a name="run-format-mapping"></a>Execute o mapeamento de formato
1. Clique em **Executar**.
2. Clique em **Procurar** e selecione o arquivo **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.
3. Clique em **OK**.

> [!NOTE]
> O arquivo selecionado não foi importado porque o design de formato supõe a existência do atributo 'id' para o elemento 'documento', mas o arquivo importado não contém esse atributo.

## <a name="modify-format-structure-to-handle-xml-attribute-as-optional"></a>Modifique a estrutura do formato para tratar o atributo xml como opcional
1. Feche a página.
2. Na árvore, expanda **raiz\documento**.
3. Na árvore, selecione **raiz\documento\id**.
4. No campo **Cadeia de caracteres vazia para atributo ausente**, selecione **Sim**.
5. Clique em **Salvar**.

## <a name="run-format-mapping-to-test-changes"></a>Execute o mapeamento de formato para testar alterações
1. Clique em **Mapear formato para modelo**.
2. Clique em **Executar**.
3. Clique em **Procurar** e selecione o arquivo **IncomingDocumentToLearnHowToHandleOptionalAttributes.xml**.
4. Clique em **OK**.
5. Revise o arquivo gerado. Note que o mesmo arquivo foi importado, já que o design do formato agora considera o atributo 'id' para o elemento 'document' como opcional.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]