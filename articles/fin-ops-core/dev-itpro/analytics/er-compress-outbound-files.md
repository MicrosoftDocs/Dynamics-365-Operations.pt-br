---
title: Compactar documentos grandes que são gerados em relatórios eletrônicos
description: Este tópico explica como compactar grandes documentos gerados por um formato de relatório eletrônico (ER).
author: NickSelin
manager: kfend
ms.date: 09/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner, ERFormatDestinationTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 30de55f9e55911290750c148621fd3d4531686c2
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680845"
---
# <a name="compress-large-documents-that-are-generated-in-electronic-reporting"></a>Compactar documentos grandes que são gerados em relatórios eletrônicos 

[!include [banner](../includes/banner.md)]

Você pode usar a [estrutura de relatórios eletrônicos (ER)](general-electronic-reporting.md) para configurar uma solução que busca dados transacionais para gerar um documento de saída. Este documento gerado pode ser muito grande. Quando esse tipo de documento é gerado, a memória do [Servidor de Objetos de Aplicativo (AOS)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/dev-tools/access-instances#location-of-packages-source-code-and-other-aos-configurations) é usada para mantê-lo. Em algum ponto, o documento deve ser baixado de seu aplicativo do Microsoft Dynamics 365 Finance. Atualmente, o tamanho máximo de um único documento gerado no ER é limitado a 2 gigabytes (GB). Além disso, o Finance atualmente [limita](https://fix.lcs.dynamics.com/Issue/Details?bugId=489291) o tamanho de um arquivo baixado a 1 GB. Portanto, é preciso configurar uma solução de ER que reduza a probabilidade de que essas limitações sejam excedidas e de que você receba uma exceção **O fluxo era muito longo** ou **Sobrefluxo ou subfluxo na operação aritmética**.

Ao configurar uma solução, é possível ajustar o formato ER no designer de operações adicionando um elemento raiz do tipo **Pasta** para compactar o conteúdo gerado por qualquer um dos seus elementos aninhados. A compactação funciona "na hora certa" para que o pico de uso da memória e o tamanho do arquivo que será baixado possam ser reduzidos.

> [!NOTE]
> A compactação de arquivos exige uma porcentagem adicional de uso da CPU.

Para obter mais informações sobre essa abordagem, conclua o exemplo neste tópico.

## <a name="example-compress-an-outbound-document"></a>Exemplo: compactar um documento de saída

Este exemplo mostra como um usuário atribuído à função **Administrador do sistema** ou **Consultor funcional de relatório eletrônico** pode configurar um formato de ER para compactar um documento gerado.

### <a name="prerequisites"></a>Pré-requisitos

Antes de concluir os procedimentos deste tópico, as etapas a seguir devem ser concluídas.

1. [Ativar um provedor de configuração](er-defer-xml-element.md#activate-a-configuration-provider).
2. [Importar o exemplo de configurações de ER](er-defer-xml-element.md#import-the-sample-er-configurations).
3. [Examinar o formato importado](er-defer-xml-element.md#review-the-imported-format).

> [!NOTE]
> Atualmente, a estrutura de formato começa no elemento **Relatório** do tipo **Arquivo** e contém elementos XML. Portanto, um documento de saída será gerado no formato XML e nenhuma compactação será usada.

### <a name="generate-an-er-format-to-get-an-uncompressed-document"></a>Gerar um formato ER para obter um documento descompactado

1. [Executar o formato importado](er-defer-xml-element.md#run-the-imported-format).
2. Observe que o tamanho do documento gerado no formato XML é de 3 kilobytes (KB).

    ![Visualização do documento de saída descompactado](./media/er-compress-outbound-files1.png)

### <a name="modify-the-format-to-compress-the-generated-output"></a>Modificar o formato para compactar a saída gerada

1. Vá para **Administração da organização** \> **Relatório eletrônico** \> **Configurações**.
2. Na página **Configurações**, na árvore de configuração, expanda **Modelo para conhecer elementos adiados**.
3. Selecione a configuração **Formato para conhecer elementos XML adiados**.
4. Selecione **Designer** para modificar a estrutura do formato.
5. Na página **Designer de formato**, na guia **Formatar**, selecione **Adicionar raiz** para adicionar um elemento de formato raiz.
6. Na caixa de diálogo **Adicionar**, selecione **Comum\\Pasta**.
7. Selecione **OK** para confirmar a adição do novo elemento raiz.
8. Selecione **Salvar**.

> [!NOTE]
> A estrutura do formato começa a partir do elemento do tipo **Pasta**. Esse elemento gerará a saída como um arquivo compactado (zip). Quando um documento gerado pelo elemento **Relatório** é colocado em um arquivo zip de saída, seu conteúdo é compactado para reduzir o tamanho do arquivo de saída.

### <a name="generate-an-er-format-to-get-a-compressed-document"></a>Gerar um formato ER para obter um documento compactado

1. Na página **Designer de formato**, selecione **Executar**.
2. Baixe o arquivo zip oferecido pelo navegador da Web e abra-o para revisão.
3. Observe que o tamanho do documento gerado no formato ZIP é de 1 KB.

    > [!NOTE] 
    > A taxa de compactação do arquivo XML que esse arquivo zip contém é de 87%. A taxa de compactação depende dos dados que estão sendo compactados.

    ![Visualização do documento de saída compactado](./media/er-compress-outbound-files2.png)

> [!NOTE]
> Se o [destino](electronic-reporting-destinations.md) de ER for configurado para o elemento de formato que gera a saída (o elemento **Relatório** neste exemplo), a compactação da saída será ignorada.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral de Relatório eletrônico (ER)](general-electronic-reporting.md)

[Destinos de Relatório eletrônico (ER)](electronic-reporting-destinations.md)

[Adiar a execução de elementos XML nos formatos ER](er-defer-xml-element.md)
