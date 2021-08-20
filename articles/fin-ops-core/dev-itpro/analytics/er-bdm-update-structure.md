---
title: Atualizar a estrutura de um modelo de documento comercial
description: Este tópico explica como atualizar a estrutura de um modelo de documento comercial usando o recurso de gerenciamento de documentos comerciais.
author: NickSelin
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-12-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 2f57e3f3a84a6e767755c69074bc194e90793e6edd79d0e07ae7449d45ec7539
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6775277"
---
# <a name="update-the-structure-of-a-business-document-template"></a>Atualizar a estrutura de um modelo de documento comercial 

[!include[banner](../includes/banner.md)]

No painel **Estrutura de modelos** do editor de modelos de [gerenciamento de documentos comerciais](er-business-document-management.md), você pode modificar um modelo de documento comercial [adicionando novos campos ](er-bdm-add-field-to-excel-template.md)a um modelo no Microsoft Excel. Depois, a estrutura do modelo é atualizada automaticamente no Dynamics 365 Finance para refletir as alterações feitas no painel **Estrutura de modelos**.

Você também pode modificar um modelo usando a funcionalidade online do Office 365. Por exemplo, é possível adicionar um novo item nomeado, como uma imagem ou forma, à planilha editável. Nesse caso, a estrutura do modelo não é atualizada automaticamente no Finance, e o item incluído não aparece no painel **Estrutura de modelos**. Atualize manualmente a estrutura de modelos no Finance selecionando **Atualizar estrutura** na página Editor de modelos.

Para obter mais informações sobre esse recurso, conclua o exemplo a seguir.

## <a name="example-update-the-structure-of-a-business-document-template"></a>Exemplo: Atualizar a estrutura de um modelo de documento comercial

Este exemplo mostra como um administrador do sistema pode atualizar a estrutura de um modelo de documento comercial no Finance após a modificação do modelo no Office Online. Veja nas seções a seguir as etapas envolvidas.

### <a name="prepare-a-business-document-template-for-editing"></a>Preparar um modelo de documento comercial para edição

Conclua os seguintes procedimentos na [visão geral de gerenciamento de documentos comerciais](er-business-document-management.md).

1. [Configurar parâmetros de ER](er-business-document-management.md#configure-er-parameters)
2. [Importar soluções de ER](er-business-document-management.md#import-er-solutions)
3. [Habilitar gerenciamento de documentos comerciais](er-business-document-management.md#enable-business-document-management)
4. [Configurar parâmetros](er-business-document-management.md#configure-parameters)

### <a name="edit-a-business-document-template"></a>Editar um modelo de documento comercial

1. No espaço de trabalho **Gerenciamento de documentos comerciais**, selecione **Novo documento**.
2. Na página **Criar um novo modelo**, selecione o modelo **Fatura de texto livre (exemplo de ER) (Excel)**.
3. Selecione **Criar documento**.
4. No campo **Título**, insira **FTI sample Litware**.
5. Selecione **OK** para criar o novo modelo.

    > [!NOTE]
    > Se ainda não tiver feito login no Office Online, você será [direcionado para a página de entrada do Office 365](er-business-document-management.md#frequently-asked-questions). Para retornar ao seu ambiente do Finance, selecione o botão **Voltar** no navegador.

    O novo modelo é aberto para edição no controle incorporado do Excel Online na página Editor de modelos.

[![Usando o espaço de trabalho de gerenciamento de documentos comerciais para iniciar a edição de um modelo de documento comercial.](./media/er-bdm-update-structure1.gif)](./media/er-bdm-update-structure1.gif)

### <a name="review-the-current-structure-of-the-editable-template"></a>Analisar a estrutura atual do modelo editável

1. No Excel Online, na guia **Exibição** da faixa de opções, grupo **Mostrar**, selecione **Linhas de grade**.
2. No modelo editável, selecione o retângulo acima do título do modelo. Esse retângulo é uma imagem chamada **rptHeaderCompLogo**.
3. Se o painel **Estrutura de modelos** estiver oculto, selecione **Mostrar estrutura**.
4. No painel **Estrutura de modelos**, expanda **Relatório \> Fatura \> rptHeader \> rptHeaderPart1**.
5. Observe que, na estrutura de modelos no Finance, o item **rptHeaderCompLogo** tem um item filho de **Relatório \> Fatura \> rptHeader \> rptHeaderPart1**.

[![Usando o espaço de trabalho de gerenciamento de documentos comerciais para analisar a estrutura atual de um modelo editável.](./media/er-bdm-update-structure2.gif)](./media/er-bdm-update-structure2.gif)

### <a name="update-the-structure-of-a-business-document-template-by-deleting-a-picture"></a>Atualizar a estrutura de um modelo de documento comercial excluindo uma imagem

1. No modelo editável do Excel Online, selecione a imagem **rptHeaderCompLogo**.
2. Siga uma destas etapas para excluir a imagem selecionada do modelo editável:

    - Pressione a tecla **Delete** no seu teclado.
    - Selecione e segure (ou clique com o botão direito do mouse) na imagem e selecione **Recortar**.

    > [!NOTE]
    > Embora a imagem não seja mais incluída no modelo do Excel, o item **rptHeaderCompLogo** ainda é exibido na estrutura de modelos no Finance.

3. Selecione **Atualizar estrutura** para sincronizar a estrutura do modelo editável no Excel e no Finance.
4. No painel **Estrutura de modelos**, expanda **Relatório \> Fatura \> rptHeader \> rptHeaderPart1**.
5. Observe que o item **rptHeaderCompLogo** não está mais incluído na estrutura de modelos no Finance.

[![Usando o espaço de trabalho de gerenciamento de documentos comerciais para excluir uma imagem de um modelo de documento comercial.](./media/er-bdm-update-structure3.gif)](./media/er-bdm-update-structure3.gif)

### <a name="update-the-structure-of-a-business-document-template-by-adding-a-picture"></a>Atualizar a estrutura de um modelo de documento comercial adicionando uma imagem

1. No Excel Online, na guia **Inserir** da faixa de opções, grupo **Ilustrações**, selecione **Imagem**.
2. Selecione **Escolher arquivo**, procure a imagem que deseja adicionar, selecione-a e clique em **OK**.
3. Selecione **Inserir**.
4. Mova a nova imagem até que ela esteja no local correto. O Excel nomeia a imagem por padrão. Por exemplo, ele pode nomear a imagem como **Imagem 2**.
5. Selecione **Atualizar estrutura** para sincronizar a estrutura do modelo editável no Excel e no Finance.
6. No painel **Estrutura de modelos**, expanda **Relatório \> Fatura \> rptHeader \> rptHeaderPart1**.
7. Observe que a nova imagem agora está incluída como um item na estrutura de modelos no Finance.

[![Usando o espaço de trabalho de gerenciamento de documentos comerciais para adicionar uma imagem a um modelo de documento comercial.](./media/er-bdm-update-structure4.gif)](./media/er-bdm-update-structure4.gif)

## <a name="related-links"></a>Links relacionados

[Visão geral de Relatório eletrônico (ER)](general-electronic-reporting.md)

[Visão geral de gerenciamento de documentos comerciais](er-business-document-management.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]