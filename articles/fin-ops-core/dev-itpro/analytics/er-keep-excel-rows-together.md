---
title: Criar um formato ER para manter as linhas juntas na mesma página do Excel
description: Este artigo explica como criar um formato de Relatório Eletrônico (ER) que mantém linhas juntas na mesma página do Microsoft Excel.
author: kfend
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2022-03-01
ms.dyn365.ops.version: Version 10.0.26
ms.custom: 220314
ms.assetid: ''
ms.search.form: EROperationDesigner
ms.openlocfilehash: 7ecc4358a0d4d9ae9e729393bd3ac4cefbf15ad2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287948"
---
# <a name="design-an-er-format-to-keep-rows-together-on-the-same-excel-page"></a>Criar um formato ER para manter as linhas juntas na mesma página do Excel

[!include [banner](../includes/banner.md)]


Este artigo explica como um usuário na função de Administrador do Sistema ou de Consultor Funcional de Relatório Eletrônico pode configurar um [formato](er-overview-components.md#format-component) de [Relatório eletrônico (ER)](general-electronic-reporting.md) que gera documentos de saída no Microsoft Excel e gerenciar a paginação de documentos para que linhas criadas sejam mantidas na mesma página.

Neste exemplo, você modificará o formato ER fornecido pela Microsoft, que é usado para imprimir faturas de texto livre no Excel. Suas modificações permitirão gerenciar a paginação de um relatório de fatura de texto livre gerado para que todas as linhas de uma única linha da fatura sejam mantidas na mesma página, sempre que possível.

Os procedimentos deste artigo podem ser concluídos na empresa **USMF**. Nenhum código é necessário.

Neste exemplo, você criará as [configurações](general-electronic-reporting.md#Configuration) do ER necessárias para a empresa **Litware, Inc.** de exemplo. Verifique se o provedor de configuração da empresa **Litware, Inc.** (`http://www.litware.com`) de exemplo está listado na estrutura de ER e marcado como **Ativo**. Se esse provedor de configuração não estiver listado, ou se ele não estiver marcado como **Ativo**, siga as etapas em [Criar um provedor de configuração e marcá-lo como ativo](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="enter-a-new-free-text-invoice"></a>Inserir uma nova fatura de texto livre

1. Siga as etapas em [Criar uma fatura de texto livre](../../../finance/accounts-receivable/create-free-text-invoice-new.md#create-a-free-text-invoice-1) para adicionar uma fatura de texto livre.

    1. Adicione uma única linha à fatura.
    2. Adicione cinco notas à linha da fatura.

    ![Revise as notas da linha da fatura na página Anexos.](./media/er-keep-excel-rows-together-notes.png)

2. Siga as etapas em [Copiar linhas](../../../finance/accounts-receivable/create-free-text-invoice-new.md#copy-lines) para criar cinco linhas de fatura adicionais que são cópias da linha da fatura que você adicionou na etapa anterior.

    ![Revisando as linhas da fatura de texto livre na página Fatura de texto livre.](./media/er-keep-excel-rows-together-invoice.png)

## <a name="configure-the-er-framework"></a>Configurar a estrutura de ER

Siga as etapas em [Configurar a estrutura de ER](er-quick-start2-customize-report.md#ConfigureFramework) para configurar o conjunto mínimo de parâmetros de ER. Você deve concluir essa configuração antes de começar a usar a estrutura de ER para criar uma versão personalizada de um formato de ER padrão.

## <a name="import-the-standard-er-format-configuration"></a>Importar a configuração do formato de ER padrão

Siga as etapas em [Importar a configuração do formato de ER padrão](er-quick-start2-customize-report.md#ImportERSolution1) para adicionar as configurações de ER padrão à sua instância atual do Dynamics 365 Finance. Por exemplo, importe a versão **252.116** da configuração de formato da **Fatura de texto livre (Excel)**. A versão básica **252** da configuração do **Modelo de fatura** básico é automaticamente importada do repositório junto com a configuração necessária de **Mapeamento de modelo de fatura**.

## <a name="set-up-print-management-to-use-the-standard-er-format"></a>Configurar o gerenciamento de impressão para usar o formato ER padrão

Siga as etapas em [Configurar gerenciamento de impressão](er-embed-images-header-footer-excel-reports.md#ConfigurePrintManagement1) para configurar o gerenciamento de impressão para o módulo **Contas a receber** para que o formato ER padrão seja usado para imprimir faturas de texto livre.

## <a name="configure-a-format-destination-for-the-standard-er-format"></a>Configurar um destino de formato para o formato ER padrão

Siga as etapas em [Configurar um destino de formato para visualização na tela](er-quick-start1-new-solution.md#ConfigureDestination) para configurar o destino ER da [Tela](er-destination-type-screen.md) do formato ER padrão para que os relatórios gerados sejam convertidos em formato PDF e visualizados em uma nova guia do navegador.

## <a name="print-a-free-text-invoice-by-using-the-standard-er-format"></a>Imprimir uma fatura de texto livre usando o formato de ER padrão

1. Siga as etapas em [Imprimir uma fatura de texto livre](er-embed-images-header-footer-excel-reports.md#ProcessInvoice1) para usar o formato ER padrão para gerar um relatório de fatura de texto livre no formato Excel para a fatura adicionada.
2. Baixe a pasta de trabalho do Excel gerada e revise-a no aplicativo de área de trabalho do Excel.

    Observe que a sexta linha da fatura começa na primeira página do relatório e continua na segunda página. A última nota aparece na segunda página e não é evidente que ela pertence à sexta linha da fatura. Portanto, a quebra de página no meio do conteúdo da linha da fatura dificulta a leitura do documento.

    ![Revisando a paginação da fatura de texto livre gerada no aplicativo de área de trabalho do Excel.](./media/er-keep-excel-rows-together-invoice1.gif)

Os procedimentos restantes neste artigo mostram como você pode ajustar o formato ER padrão para melhorar a aparência e a legibilidade do relatório de fatura, mantendo todo o conteúdo para uma única linha de fatura na mesma página.

## <a name="create-a-custom-format"></a>Criar uma formato personalizado

Siga as etapas em [Criar um formato personalizado](er-embed-images-header-footer-excel-reports.md#DeriveProvidedFormat) para derivar um formato do formato ER importado e criar uma configuração de ER de **Fatura de texto livre (Excel) personalizada** que está disponível para edição e modificação.

## <a name="edit-the-custom-format"></a>Editar o formato personalizado

1. Siga as etapas em [Criar um formato personalizado](er-embed-images-header-footer-excel-reports.md#ConfigureDerivedFormat) para abrir o formato ER derivado para edição no designer de formato ER.
2. Na página **Designer de formato**, na árvore de componentes de formato no painel esquerdo, expanda **Fatura de texto livre \> Planilha \> InvoiceLines** e selecione o componente **InvoiceLines_Values**.
3. Na guia **Formato**, defina a opção **Manter linhas juntas** como **Sim**.

    ![Defina a opção Manter linhas juntas para o formato do ER editável na página Designer de formato.](./media/er-keep-excel-rows-together-format.png)

4. Selecione **Salvar** e feche a página.

## <a name="mark-the-custom-format-as-runnable"></a>Marcar o formato personalizado como executável

Siga as etapas em [Marcar o formato personalizado como executável](er-embed-images-header-footer-excel-reports.md#MarkFormatRunnable) para tornar a versão modificada do formato ER personalizado executável.

## <a name="set-up-print-management-to-use-the-custom-er-format"></a>Configurar o gerenciamento de impressão para usar o formato ER personalizado

Siga as etapas em [Configurar gerenciamento de impressão](er-embed-images-header-footer-excel-reports.md#ConfigurePrintManagement2) para configurar o gerenciamento de impressão para o módulo **Contas a receber** para que o formato ER personalizado seja usado para imprimir faturas de texto livre.

## <a name="configure-a-format-destination-for-the-custom-er-format"></a>Configurar um destino de formato para o formato ER personalizado

Siga as etapas em [Configurar um destino de formato para visualização na tela](er-quick-start1-new-solution.md#ConfigureDestination) para configurar o destino ER da **Tela** do formato ER personalizado para que os relatórios gerados sejam convertidos em formato PDF e visualizados em uma nova guia do navegador.

## <a name="print-a-free-text-invoice-by-using-the-custom-er-format"></a>Imprimir uma fatura de texto livre usando o formato de ER personalizado

1. Siga as etapas em [Imprimir uma fatura de texto livre](er-embed-images-header-footer-excel-reports.md#ProcessInvoice2) para usar o formato ER personalizado para gerar um relatório de fatura de texto livre no formato Excel para a fatura adicionada.
2. Baixe a pasta de trabalho do Excel gerada e revise-a no aplicativo de área de trabalho do Excel.

    Observe que a sexta linha da fatura começa na segunda página e todas as linhas do Excel que representam essa linha de fatura aparecem juntas nessa página.

    ![Revisando a paginação atualizada da fatura de texto livre gerada no aplicativo de área de trabalho do Excel.](./media/er-keep-excel-rows-together-invoice2.gif)

## <a name="additional-resources"></a>Recursos adicionais

[Criar uma configuração para gerar documentos no formato Excel](er-fillable-excel.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
